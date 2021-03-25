---
title: Consolidación en la nube para Teams y Skype Empresarial
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: En este artículo se describe cómo lograr esa consolidación para las organizaciones con implementaciones locales de Skype Empresarial (o Lync) que buscan mover su carga de trabajo de UC a Teams o Skype Empresarial Online.
ms.openlocfilehash: 5533b1780edd2ab8a997d0f04665876c2f85f149
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119029"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidación de la nube para Teams y Skype Empresarial

Muchas grandes empresas tienen más de un bosque de AD local y, en algunos casos, los clientes tienen más de una implementación de Exchange o Skype Empresarial Server (o Lync Server). Además, incluso las organizaciones con un solo bosque local pueden encontrarse en una situación similar por una fusión o una adquisición empresarial. A medida que estos clientes se mueven a la nube, desean consolidar las varias instancias de una carga de trabajo local determinada en la nube en una sola organización de Microsoft 365 u Office 365. En este artículo se describe cómo lograr esa consolidación para organizaciones con varias implementaciones locales de Skype Empresarial (o Lync) que desean mover su carga de trabajo de UC a la nube de Microsoft, por ejemplo, Microsoft Teams o Skype Empresarial Online.

Históricamente, las instrucciones para los clientes en esta situación han sido consolidar primero las implementaciones locales y luego migrar a la nube. Aunque esta opción sigue siendo una opción, en este artículo se describe una solución basada en una nueva funcionalidad que permite a las organizaciones con varias implementaciones de Skype Empresarial migrar una implementación a la vez a una sola organización de Microsoft 365 u Office 365, sin realizar la consolidación local. Tenga en cuenta que, incluso con esta nueva funcionalidad, Skype Empresarial Online y Microsoft Teams no admiten varios bosques de Skype Empresarial/Lync en modo híbrido con una sola organización de Microsoft 365 u Office 365. 

> [!Important]
> Antes de usar esta guía para la [](#limitations)configuración, asegúrese de revisar y comprender las limitaciones, ya que pueden afectar a su organización.

## <a name="overview-of-cloud-consolidation"></a>Información general sobre la consolidación en la nube

La consolidación de todos los usuarios locales en la nube en una sola organización de Microsoft 365 u Office 365 se puede lograr para cualquier organización con varias implementaciones de Skype Empresarial, siempre que se cumplen los siguientes requisitos clave:

- Debe haber como máximo una organización de Microsoft 365 u Office 365 implicada. No se admite la consolidación en escenarios con más de una organización.
- En cualquier momento, solo puede haber un bosque local de Skype Empresarial en modo híbrido (espacio de direcciones SIP compartido). El resto de los bosques locales de Skype Empresarial deben permanecer en local (y presumiblemente federados entre sí). Tenga en cuenta que  estas otras organizaciones locales pueden sincronizarse con AAD si lo desean con nuevas funciones para deshabilitar los dominios [SIP](/powershell/module/skype/disable-csonlinesipdomain) en línea disponibles a partir de diciembre de 2018.

Los clientes con implementaciones de Skype Empresarial en varios bosques deben migrar por completo todos los usuarios de un único bosque híbrido de Skype Empresarial individualmente a la organización de Microsoft 365 u Office 365 mediante la funcionalidad espacio de direcciones SIP compartido y, a continuación, deshabilitar la implementación híbrida con esa implementación local, antes de migrar la siguiente implementación local de Skype Empresarial. Antes de migrar a la nube, los usuarios locales permanecen en un estado federado con los usuarios que no están representados en el directorio local del mismo usuario.  

## <a name="canonical-example-of-cloud-consolidation"></a>Ejemplo canónico de consolidación de la nube

Considere la posibilidad de una organización con dos implementaciones locales federadas independientes de Skype Empresarial que quiera consolidarlas en línea en Microsoft Teams o Skype Empresarial Online.


|Detalles de estado originales |Detalles de estado deseados |
|---------|---------|
|<ul><li>2 implementaciones locales independientes de Skype Empresarial en bosques de AD independientes<li>Como máximo 1 bosque está en híbrido con Skype Empresarial Online <li> Las organizaciones están federadas entre sí <li>Los usuarios no están sincronizados en estos bosques<li> La organización puede tener una organización de Microsoft 365 u Office 365 y puede estar sincronizando su directorio con Azure AD</ul>|<ul> <li>1 Organización de Microsoft 365 u Office 365<li>No más implementaciones locales, por lo que no queda ninguna híbrida<li>Todos los usuarios locales se encuentran en Skype Empresarial Online y, opcionalmente, pueden ser usuarios solo de Teams <li>Sin superficie local de Skype Empresarial en cualquier lugar <li>Los usuarios aún tienen autenticación local</ul> |

![Consolidación de dos implementaciones locales federadas independientes](../media/cloudconsolidationfig1.png)  

A continuación se indican los pasos básicos para obtener del estado original al estado final deseado.  Tenga en cuenta que algunas organizaciones pueden encontrar que su punto de partida está en algún lugar en medio de estos pasos. Vea [Otros puntos iniciales](#other-starting-points), más adelante en este artículo. Por último, en algunos casos, el orden se puede ajustar, según la necesidad. [Las restricciones y limitaciones clave se](#limitations) describen más adelante.

1.  Obtenga una organización de Microsoft 365 u Office 365 si aún no existe.
2.  Asegúrese de que todos los dominios SIP relevantes en ambas implementaciones locales estén comprobados como dominios de Microsoft 365 u Office 365.
3.  Elija una implementación de Skype Empresarial que sea híbrida con Microsoft 365 u Office 365. En este ejemplo, usaremos OriginalCompany. <span> com.
4.  [Habilite AAD Connect para el bosque que](configure-azure-ad-connect.md) primero se convertirá en híbrido (OriginalCompany. <span> com). 
5.  Si va a introducir Teams en su organización, establezca la directiva de todo el espacio empresarial para [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy) en SfBWithTeamsCollab o en uno de los otros modos SfB (SfBOnly o SfBWithTeamsCollabAndMeetings). Esto es fundamental para garantizar el enrutamiento de llamadas y chats de usuarios que se mueven a Teams solo a usuarios que permanecen en las instalaciones.
6.  Se recomienda en este momento (pero aún no es necesario hasta el paso 11) habilitar [AAD Connect para](cloud-consolidation-aad-connect.md) el otro bosque (AcquiredCompany. <span> com). Suponiendo que AAD Connect está habilitado en ambos bosques, la organización tiene el aspecto de la figura **[A](#figure-a)**, que puede ser un punto de partida común para algunas organizaciones. 
7.  Para los dominios SIP hospedados por otras implementaciones locales (en este caso, AcquiredCompany. <span> com), [deshabilite estos dominios SIP en Skype Empresarial Online](/powershell/module/skype/disable-csonlinesipdomain) con `Disable-CsOnlineSipDomain` PowerShell. (Esta es una nueva funcionalidad a partir de diciembre de 2018).
8.  [Configurar Skype Empresarial híbrido](configure-federation-with-skype-for-business-online.md) para OriginalCompany. <span> com (la única implementación que aún tiene dominios SIP en línea habilitados).
9.  En la implementación híbrida (OriginalCompany. <span> com), empiece a [mover usuarios](move-users-between-on-premises-and-cloud.md) de Skype Empresarial local a la nube (independientemente de que teams solo o no) para que la cuenta se alome en Skype Empresarial Online. Ahora la organización tiene el aspecto **[de la figura B](#figure-b)**. Los cambios clave de la figura A son:
    - Los usuarios de ambos directorios locales ahora están en AAD.
    - AcquiredCompany. <span> com es un dominio SIP en línea deshabilitado.
    - Algunos usuarios se han movido en línea a Skype Empresarial Online o Teams. (Vea el usuario púrpura A.)
10. Una vez que todos los usuarios se mueven a la nube, [deshabilite](cloud-consolidation-disabling-hybrid.md) la implementación híbrida con la implementación local de Skype Empresarial para OriginalCompany. <span> com desde Office 365:  
    - Deshabilite el dominio dividido en la organización de Microsoft 365 u Office 365.
    - Deshabilite la capacidad de comunicarse con Microsoft 365 u Office 365 en OriginalCompany. <span> com local.
    - Actualizar registros DNS para OriginalCompany. <span> com para apuntar a Microsoft 365 u Office 365.
11. Si aún no lo ha hecho, [habilite AAD Connect para el siguiente](cloud-consolidation-aad-connect.md) bosque que vaya híbrido (AcquiredCompany. <span> com). En este punto, la organización tiene el aspecto **[de la figura C](#figure-c)**. Este puede ser otro punto de partida común para algunas organizaciones. 
12. En PowerShell, [habilite los dominios SIP para la](/powershell/module/skype/enable-csonlinesipdomain) siguiente implementación local que vaya híbrida, AcquiredCompany. <span> com. Esto se hace con `Enable-CsOnlineSipDomain` , que es una nueva funcionalidad disponible a partir de diciembre de 2018.
13. Si usa la federación cerrada, debe agregar cualquier dominio SIP (excepto .microsoftonline.com) del espacio empresarial en línea puro como Dominios permitidos en el mismo \* Microsoft 365 u Office 365.  Tenga en cuenta que puede tardar algún tiempo antes de que el cambio entre en vigor y no haya ningún daño al hacerlo antes de tiempo, por lo que le recomendamos que lo haga bien antes de pasar al paso 14.
14. Actualice el entorno local para aceptar los dominios SIP del inquilino en línea, de modo que coincidan.
    - [Actualice el SAN](cloud-consolidation-edge-certificates.md) en todos los certificados perimetrales para que sea el mismo valor que antes, además de los valores para los dominios SIP en línea existentes (excepto *.microsoftonline.com), en este caso, Sip.OriginalCompany. <span> com.
    - Asegúrese de OriginalCompany. <span> com es un [dominio permitido en](/powershell/module/skype/new-csalloweddomain) la implementación local, AcquiredCompany. Agregar dominios permitidos.
15. [Habilitar Skype Empresarial híbrido entre](configure-federation-with-skype-for-business-online.md) AcquiredCompany local. <span> com y la nube.
16. Como desee, [migre los usuarios desde local a la nube.](move-users-between-on-premises-and-cloud.md) Puede migrar usuarios directamente al modo [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) o puede migrarlos primero a Skype Empresarial Online. Durante este estado, la organización tiene el aspecto **[de figura D](#figure-d)**.
17. Una vez que se migren todos los usuarios, [deshabilite](cloud-consolidation-disabling-hybrid.md) el entorno híbrido con el entorno local para que la *organización sea pura nube.*

Los diagramas siguientes muestran la configuración en varios puntos clave durante este proceso.

##### <a name="figure-a"></a>Figura A:

- Ambas organizaciones se sincronizan a través de AAD Connect, por lo que AAD ahora tiene todos los usuarios de ambas implementaciones locales.
- Todos los usuarios albergados localmente.  
- Skype Empresarial Híbrido aún *no está* configurado.
- Si los usuarios de cualquiera de las implementaciones usan Teams, no podrán federarse entre sí (ni con ninguna organización) ni tendrán interoperabilidad con usuarios de Skype Empresarial. Mientras se encuentra en esta fase, Microsoft recomienda usar Solo Teams para canales.<br><br>
    ![Figura un diagrama](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figura B:

- AcquiredCompany. <span> com es un [dominio](/powershell/module/skype/disable-csonlinesipdomain) SIP en línea deshabilitado. Todos los usuarios son locales. Si usan Teams, no tienen federación ni interoperabilidad. Mientras se encuentra en esta fase, Microsoft recomienda usar Solo Teams para canales.
- Skype Empresarial Híbrido se ha habilitado para una de las organizaciones locales.
- Algunos usuarios de la organización híbrida se han movido a la nube (usuario A como se indica mediante sombreado púrpura). Estos usuarios pueden ser usuarios de Skype Empresarial Online o solo de Teams con compatibilidad completa con la interoperabilidad y la federación.<br><br>
    ![Diagrama de la figura B](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figura C:

- Todos los usuarios de OriginalCompany. <span> com están ahora en la nube (en skype empresarial online). Se recomienda que también sean Solo Teams.
- Configuración híbrida de Skype Empresarial con OriginalCompany. <span> se ha deshabilitado la implementación de com. La implementación local ha desaparecido.
- Si AcquiredCompany. <span> com no se estaba sincronizando anteriormente con AAD, para continuar desde aquí debe sincronizarse ahora. Pero aún no es híbrido (espacio de direcciones SIP compartido) y hasta que la organización esté lista para pasar a híbrido, el dominio SIP en línea para la organización local pura (AcquiredCompany.com) debe permanecer deshabilitado, de modo que los usuarios de Teams en línea puedan comunicarse con usuarios locales.<br><br>
    ![Diagrama de la figura C](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figura D:

- AcquiredCompany. <span> com ahora está habilitado como un dominio SIP en línea.
- Local se actualiza para aceptar OriginalCompany. <span> com. (Se actualizan los certificados perimetrales y de dominio permitidos).
- El espacio de direcciones SIP compartido está habilitado entre AcquiredCompany. <span> com y la organización de Microsoft 365 u Office 365.
- Es posible que algunos usuarios de la organización híbrida se hayan movido a la nube, como el usuario D a continuación (indicado por sombreado púrpura).<br><br>
    ![Diagrama de la figura D](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Otros puntos iniciales

Los pasos del ejemplo canónico anterior suponen que la organización comienza con dos implementaciones locales federadas sin presencia de Microsoft u Office 365. Sin embargo, algunas organizaciones pueden tener una superficie de Microsoft 365 u Office 365 existente, y puede haber diferentes puntos de entrada en la secuencia anterior. Hay cuatro configuraciones típicas:

- Varias organizaciones locales federadas sin ninguna organización de Microsoft 365 u Office 365. En este caso, comience en el paso 1.
- Varias organizaciones locales federadas que ya están sincronizando varios bosques de Skype Empresarial en un único inquilino de Azure AD. Esta organización se asemeja a la organización hipotética de la figura A, que ha completado los pasos 1-6 y debe comenzar en el paso 7.
- Una organización híbrida que se federa con 1 o más organizaciones locales puras, ninguna de las cuales se sincroniza con AAD. Dicha organización se parecería a la organización hipotética de **la figura E**, que se muestra a continuación.
    - Esta organización es similar a la figura B, que ha completado los pasos 1-9, excepto:
        - Sus implementaciones de Skype Empresarial no híbrido aún *no* se sincronizan con Azure AD.
        -  Los dominios SIP en línea aún no están deshabilitados. 
    - Estas organizaciones deben:
        - Complete la migración de la organización híbrida existente y escriba la secuencia anterior en el paso 10.  OR,
        - Si se desea sincronizar otros bosques de Skype Empresarial en AAD antes de completar la migración de la organización híbrida, la organización debe realizar el paso 7 (deshabilitar todos los dominios SIP en línea en cualquier otra implementación local de Skype Empresarial que se sincronice en AAD) y, a continuación, habilitar AAD Connect y, a continuación, continuar con el paso 10 (retirar la implementación híbrida original).       
                **Figura E**<br>
                ![Diagrama de figura E](../media/cloudconsolidationfige.png)
- Una organización pura de Skype Empresarial Online (que puede o no usar Teams) que se federa con una organización local independiente de Skype Empresarial. Una vez que esta organización deshabilita el dominio SIP en línea para la organización local y habilita AAD Connect para la organización local de Skype Empresarial, se asemeja a la organización hipotética que se muestra en la figura **[C](#figure-c)** que ha completado los pasos 1 a 11.

## <a name="limitations"></a>Limitaciones

- Debe haber como máximo una organización de Microsoft 365 u Office 365 implicada. No se admite la consolidación en escenarios con más de una organización.
- Solo un bosque local de Skype Empresarial puede estar en modo híbrido (espacio de direcciones SIP compartido) a la vez. Todos los demás bosques locales de Skype Empresarial deben permanecer exclusivamente locales y deben estar federados entre sí y con la organización de Microsoft 365 u Office 365.
- Antes de migrarse a la nube, hay una experiencia asimétrica para los usuarios en esta implementación, ya que no todos los usuarios en línea están representados localmente:
    - La experiencia se puede resumir de la siguiente manera:
        - Cualquier usuario conectado a casa interactuará con los usuarios locales en el entorno híbrido como si el usuario fuera híbrido.
        - Los usuarios locales de la implementación híbrida interactuarán con usuarios en línea representados en su directorio local como si fueran híbridos. 
        - Los usuarios locales de la implementación híbrida interactuarán con usuarios en línea que no están representados en AD local como federados.
    - En **[la figura D](#figure-d)** anterior, el usuario E es local en AcquiredCompany. <span> com.  El usuario E interactuará con el usuario D (en línea) mediante la experiencia híbrida estándar, pero el usuario E tendrá una experiencia federada con los usuarios A, B y C porque no están representados en el directorio local. Sin embargo, los usuarios A, B y C interactuarán con el usuario E como si el usuario estuviera en híbrido.
    - Implicaciones de que la interacción sea híbrida frente a la federación:
        - La presencia no se suscribe automáticamente para los usuarios federados a menos que el usuario esté marcado como contacto.
        - El reenvío de llamadas no funciona entre dominios federados.
        - Los escenarios de transferencia de llamadas son más limitados.
        - La limitación puede aplicarse al tráfico federado.
- Dada esta experiencia asimétrica, la compatibilidad oficial para llamar a la funcionalidad en escenarios entre locales entre un usuario local y un usuario en la nube que no está en el directorio local se limita solo al punto a punto. 
    - No se admite el reenvío de llamadas, la transferencia, las colas de llamadas, etc. entre estos usuarios.
    - Estos escenarios de llamadas no compatibles seguirán estando habilitados, pero en muchos casos producirán errores de maneras impredecibles. 
    - En **[la figura D](#figure-d)** anterior, el usuario E es local y las llamadas con los usuarios A, B o C solo se admiten como punto a punto. (Las llamadas con el usuario D no tendrían limitaciones de compatibilidad).  Sin embargo, después de mover el usuario local E a la nube, esta restricción ya no se aplica.
- Si tiene más de una implementación de Skype Empresarial Server 2019 en su entorno, solo 1 de ellas se puede configurar para usar el Operador automático organizativo, ya que esa característica requiere la configuración híbrida de Skype Empresarial Server. 
- Se puede ajustar el orden de algunos de los pasos anteriores. El requisito clave que debe cumplirse es que si todos estos son verdaderos:
    - Más de un bosque de Skype Empresarial local se sincroniza con un único inquilino de AAD
    - El dominio dividido está habilitado con un bosque local
    - Al menos un usuario de la organización híbrida se ha migrado a la nube<br>   A continuación, *debe* deshabilitar todos los demás dominios SIP en línea de cualquier otro bosque local de Skype Empresarial. De lo contrario, la federación entre los usuarios en línea de la organización híbrida y los usuarios locales de otras organizaciones se interrumpirá en una dirección.

## <a name="implications"></a>Implicaciones

- Dado que hay limitaciones en la compatibilidad con la funcionalidad de llamada avanzada, como se describió anteriormente, las organizaciones deben tratar estos estados asimétricos como **transitorios** como parte de la migración y no perseguirlos como estado estable .  
- Las organizaciones con varias implementaciones locales de Skype Empresarial deberían comenzar por lo general con una implementación que se pueda migrar completamente a la nube, de modo que la consolidación pueda continuar. Se entiende que en algunos casos habrá retenciones de determinados grupos de usuarios para los que aún no es viable pasar a Teams. Cuando esto sea una consideración en escenarios que impliquen varios bosques de Skype Empresarial, comience a migrar con otro bosque que no tenga estas limitaciones, si es posible.
- Al pasar de local a la nube, los usuarios que tienen relaciones de delegación o normalmente participan en escenarios de reenvío de llamadas deben moverse juntos como una unidad.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Consideraciones para pasar al modo TeamsOnly

Al mover usuarios de local a la nube en un entorno híbrido, puede moverlos al modo Solo Skype Empresarial o TeamsOnly. *Si planea mover usuarios al modo TeamsOnly, asegúrese de leer primero esta sección.*

- Al asignar el modo TeamsOnly a un usuario, todos los chats y llamadas de cualquier otro usuario llegarán al cliente de Teams de ese usuario. 
- Si los usuarios con Skype Empresarial local usan principalmente el cliente de Skype Empresarial y no Teams, considere la posibilidad de establecer TeamsUpgradePolicy para que el enrutamiento a esos usuarios locales siempre aterrice en Skype Empresarial en lugar de en Teams. Para garantizar el enrutamiento correcto de chats y llamadas entre usuarios que son TeamsOnly y usuarios que siguen usando Skype Empresarial local, los usuarios locales deben tener un valor efectivo de TeamsUpgradePolicy con uno de los modos SfB, en lugar de Islas (que es el valor predeterminado). 
    - Para ello, primero debe establecer la instancia global del inquilino *de TeamsUpgradePolicy en uno de estos valores:*
        - SfBWithTeamsCollab (recomendado)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Puede conceder una directiva para todo el espacio empresarial mediante este comando:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Nota: Debe hacerlo en un nivel de espacio empresarial porque la directiva no se puede asignar a usuarios individuales que no tienen una dirección SIP en el directorio en línea. Aunque ha deshabilitado los dominios SIP en línea para sus implementaciones locales puras, los usuarios de esos dominios no tendrán direcciones SIP en el directorio en línea por diseño. Por lo tanto, la única forma de aplicar la directiva a los usuarios locales es mediante la asignación en el nivel de inquilino. En cambio, en la implementación híbrida, los usuarios tendrán una dirección SIP en el directorio en línea para que se les pueda asignar explícitamente una directiva si se desea que tengan un valor diferente a la directiva global del espacio empresarial.
- La experiencia de usuario del cliente de Teams aún no respeta los modos SfB de TeamsUpgradePolicy. Por ejemplo, cuando en estos modos, el inicio de llamadas y chat en Teams es actualmente posible, aunque en el futuro no será así. Esto puede causar confusión entre los usuarios porque las respuestas a veces pueden llegar a Teams y, a veces, Skype Empresarial, según las circunstancias. Se recomienda deshabilitar por separado las llamadas y el chat a través de TeamsMessagingPolicy y TeamsCallingPolicy para los usuarios que aún están en las instalaciones.

## <a name="see-also"></a>Vea también

[Actualizar el certificado de límite](cloud-consolidation-edge-certificates.md)

[Actualización de AAD Connect para incluir más de un bosque](cloud-consolidation-aad-connect.md)

[Deshabilitar híbridos para completar la migración a la nube](cloud-consolidation-disabling-hybrid.md)