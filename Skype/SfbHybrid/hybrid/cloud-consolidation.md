---
title: Consolidación en la nube para Teams y Skype empresarial
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
description: En este artículo se describe cómo lograr esa consolidación para las organizaciones con implementaciones locales de Skype empresarial (o Lync) que buscan migrar para transferir su carga de trabajo de comunicaciones unificadas a Microsoft Teams o Skype empresarial online.
ms.openlocfilehash: d2733ffacf8b56a5cfe4217553f533950eb82e36
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221494"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidación de la nube para Teams y Skype Empresarial

Muchas grandes empresas tienen más de un bosque de AD local y, en algunos casos, los clientes tienen más de una implementación de Exchange o Skype Empresarial Server (o Lync Server). Además, incluso las organizaciones con un solo bosque local pueden encontrarse en una situación similar por una fusión o una adquisición empresarial. Como estos clientes se mueven a la nube, quieren consolidar las múltiples instancias de una carga de trabajo local determinada en la nube en una sola organización de Microsoft 365 u Office 365. En este artículo se describe cómo lograr esa consolidación para organizaciones con varias implementaciones locales de Skype empresarial (o Lync) que deseen mover su carga de trabajo de comunicaciones unificadas a la nube de Microsoft, por ejemplo, Microsoft Teams o Skype empresarial online.

Históricamente, las instrucciones para los clientes en esta situación han sido consolidar primero las implementaciones locales y luego migrar a la nube. Aunque todavía es una opción, en este artículo se describe una solución basada en una nueva funcionalidad que permite a las organizaciones con varias implementaciones de Skype empresarial migrar una implementación a la vez en una sola organización de Microsoft 365 u Office 365, sin realizar la consolidación local. Tenga en cuenta que, incluso con esta nueva funcionalidad, Skype empresarial online y Microsoft Teams no admiten varios bosques de Skype empresarial/Lync en modo híbrido con una sola organización de Microsoft 365 u Office 365. 

> [!Important]
> Antes de usar esta guía para la configuración, asegúrese de revisar y comprender las [limitaciones](#limitations), ya que pueden afectar a su organización.

## <a name="overview-of-cloud-consolidation"></a>Información general sobre la consolidación en la nube

Se puede consolidar la consolidación de todos los usuarios de forma local en la nube en una sola organización de Microsoft 365 u Office 365 para cualquier organización con varias implementaciones de Skype empresarial, siempre que se cumplan los siguientes requisitos clave:

- Debe haber una organización de Microsoft 365 u Office 365 como máximo implicado. No se admite la consolidación en escenarios con más de una organización.
- En cualquier momento, solo puede haber un bosque local de Skype Empresarial en modo híbrido (espacio de direcciones SIP compartido). El resto de los bosques locales de Skype Empresarial deben permanecer en local (y presumiblemente federados entre sí). Tenga en cuenta que estas organizaciones locales *pueden* sincronizarse con AAD si lo desea, con [nuevas funciones para deshabilitar los dominios SIP en línea](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) disponibles a partir de diciembre de 2018.

Los clientes con implementaciones de Skype empresarial en varios bosques deben migrar completamente todos los usuarios de un único bosque híbrido de Skype empresarial a la organización de Microsoft 365 u Office 365 mediante la funcionalidad de espacio de direcciones SIP compartido y, a continuación, deshabilitar la implementación híbrida con dicha implementación local antes de continuar para migrar la siguiente implementación local de Skype empresarial. Antes de migrar a la nube, los usuarios locales permanecen en un estado federado con los usuarios que no están representados en el directorio local del mismo usuario.  

## <a name="canonical-example-of-cloud-consolidation"></a>Ejemplo canónico de consolidación en la nube

Considere una organización con dos implementaciones locales federadas independientes de Skype empresarial que quiera consolidarlas en línea en Microsoft Teams o Skype empresarial online.


|Detalles de estado originales |Detalles de estado deseado |
|---------|---------|
|<ul><li>2 implementaciones locales independientes de Skype empresarial en bosques de AD independientes<li>Como máximo, el bosque está en un híbrido con Skype empresarial online <li> Organizaciones están federados entre sí <li>Los usuarios no se sincronizan entre estos bosques<li> Es posible que el org tenga una organización de Microsoft 365 u Office 365 y pueda estar sincronizando su directorio con Azure AD</ul>|<ul> <li>1 organización de Microsoft 365 u Office 365<li>No hay más implementaciones locales, por lo que no queda ningún híbrido<li>Todos los usuarios de local están hospedados en Skype empresarial online y, opcionalmente, solo pueden ser usuarios de Microsoft Teams. <li>Sin espacio local de Skype empresarial en cualquier lugar <li>Los usuarios aún tienen autenticación local</ul> |

![Consolidación de dos implementaciones locales federadas independientes](../media/cloudconsolidationfig1.png)  

A continuación se indican los pasos básicos para obtener desde el estado original hasta el estado final deseado.  Tenga en cuenta que algunas organizaciones pueden encontrar que su punto de partida está en algún lugar en la mitad de estos pasos. Consulte [otros puntos de inicio](#other-starting-points), más adelante en este artículo. Por último, en algunos casos, el orden puede ajustarse, según la necesidad. Las [restricciones y limitaciones clave](#limitations) se describen más adelante.

1.  Obtenga una organización de Microsoft 365 u Office 365 si aún no existe.
2.  Asegúrese de que todos los dominios SIP relevantes en todas las implementaciones locales se han comprobado con Microsoft 365 u Office 365 dominios.
3.  Elija una implementación de Skype empresarial que será híbrida con Microsoft 365 u Office 365. En este ejemplo, usaremos OriginalCompany. <span> Puerto.
4.  [Habilite AAD Connect para el bosque](configure-azure-ad-connect.md) que se convertirá primero en híbrido (OriginalCompany. <span> com). 
5.  Si va a presentar Teams en su organización, establezca la Directiva de todo el inquilino para [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy) en SfBWithTeamsCollab o en uno de los otros modos de SfB (SfBOnly o SfBWithTeamsCollabAndMeetings). Esto es esencial para garantizar el enrutamiento de llamadas y chats de usuarios que se mueven a Microsoft Teams solo para los usuarios que permanecen en el entorno local.
6.  En este punto se recomienda (pero todavía no es necesario hasta el paso 11) para [Habilitar AAD Connect para el otro bosque](cloud-consolidation-aad-connect.md) (AcquiredCompany. <span> com). Si se habilita AAD Connect en ambos bosques, la organización es similar a la **[de la figura a](#figure-a)**, que puede ser un punto de partida común para algunos organizaciones. 
7.  Para cualquier dominio SIP hospedado por otras implementaciones locales (en este caso, AcquiredCompany. <span> com), [deshabilite estos dominios SIP en Skype empresarial online](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) con `Disable-CsOnlineSipDomain` en PowerShell. (Esta es una nueva funcionalidad a partir del 2018 de diciembre).
8.  [Configurar Skype empresarial híbrido](configure-federation-with-skype-for-business-online.md) para OriginalCompany. <span> com (la única implementación que todavía tiene habilitados dominios SIP en línea).
9.  En la implementación híbrida (OriginalCompany. <span> com), empiece [a mover a los usuarios de Skype empresarial local a la nube](move-users-between-on-premises-and-cloud.md) (ya sea Teams o no) para que la cuenta se encuentre hospedada en Skype empresarial online. Ahora la organización tiene el aspecto de la **[figura B](#figure-b)**. Los cambios clave de la figura A son:
    - Los usuarios de ambos directorios locales están ahora en AAD.
    - AcquiredCompany. <span> com es un dominio SIP en línea deshabilitado.
    - Algunos usuarios se han movido en línea a Skype empresarial online o Teams. (Consulte el usuario púrpura A.)
10. Una vez que todos los usuarios se muevan a la nube, [deshabilite el entorno híbrido con la implementación local de Skype empresarial](cloud-consolidation-disabling-hybrid.md) para OriginalCompany. <span> com desde Office 365:  
    - Deshabilite el dominio dividido en la organización de Microsoft 365 u Office 365.
    - Deshabilite la capacidad de comunicarse con Microsoft 365 u Office 365 en OriginalCompany. <span> com local.
    - Actualizar registros DNS para OriginalCompany. <span> com para que apunte a Microsoft 365 u Office 365.
11. Si no lo ha hecho, [habilite AAD Connect para el siguiente bosque](cloud-consolidation-aad-connect.md) que se va a iniciar como híbrido (AcquiredCompany. <span> com). En este momento, la organización tiene el aspecto de la **[figura C](#figure-c)**. Este puede ser otro punto de partida común para algunas organizaciones. 
12. En PowerShell, [habilite los dominios SIP para la siguiente implementación local](https://docs.microsoft.com/powershell/module/skype/enable-csonlinesipdomain) que se va a implementar de forma híbrida, AcquiredCompany. <span> Puerto. Esto se realiza con `Enable-CsOnlineSipDomain` , que es una nueva funcionalidad disponible a partir del 2018 de diciembre.
13. Si usa Federación cerrada, debe agregar dominios SIP (excepto \* . microsoftonline.com) del inquilino en línea puro como dominios permitidos en el **mismo** Microsoft 365 u Office 365. Tenga en cuenta que puede tardar algún tiempo antes de que el cambio surta efecto y que no haya ningún perjuicio en cuanto a esto en principio, por lo que se recomienda hacerlo antes de avanzar al paso 14.
14. Actualice el entorno local para aceptar todos los dominios SIP del inquilino en línea, por lo que coinciden.
    - [Actualice el San de todos los certificados perimetrales](cloud-consolidation-edge-certificates.md) para que tengan el mismo valor que antes, además de los valores de los dominios SIP en línea existentes (excepto *. microsoftonline.com), en este caso, SIP. OriginalCompany. <span> Puerto.
    - Asegúrese de que OriginalCompany. <span> com es un [dominio permitido](https://docs.microsoft.com/powershell/module/skype/new-csalloweddomain) en la implementación local, AcquiredCompany. Agregar dominios permitidos.
15. [Habilitar Skype empresarial híbrido](configure-federation-with-skype-for-business-online.md) entre AcquiredCompany local. <span> com y la nube.
16. Si lo desea, [migre los usuarios de forma local a la nube](move-users-between-on-premises-and-cloud.md). Puede migrar los usuarios directamente al modo [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) o puede migrarlos primero a Skype empresarial online. Durante este estado, la organización tiene el aspecto de la **[figura D](#figure-d)**.
17. Una vez que se hayan migrado todos los usuarios, [deshabilite el entorno híbrido con el entorno local](cloud-consolidation-disabling-hybrid.md) para *convertir la nube en la organización pura*.

Los diagramas siguientes muestran la configuración en varios puntos clave durante este proceso.

##### <a name="figure-a"></a>Figura A:

- Ambas organizaciones se sincronizan mediante AAD Connect, por lo que AAD ahora tiene a todos los usuarios de implementaciones locales.
- Todos los usuarios hospedados en local.  
- Skype empresarial híbrido todavía *no* está configurado.
- Si los usuarios de cualquier implementación utilizan Teams, no podrán federar entre ellos (o cualquier otra organización), ni tendrán interoperabilidad con los usuarios de Skype empresarial. En esta fase, Microsoft recomienda usar Teams solo para los canales.<br><br>
    ![Ilustración de un diagrama](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figura B:

- AcquiredCompany. <span> com es un dominio SIP en línea [deshabilitado](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) . Todos los usuarios son locales. Si utilizan Teams, no tienen Federación ni interoperabilidad. En esta fase, Microsoft recomienda usar Teams solo para los canales.
- Skype empresarial híbrido se ha habilitado para una de las organizaciones locales.
- Algunos usuarios de la organización híbrida se han movido a la nube (el usuario A tal como lo indica el sombreado púrpura). Estos usuarios pueden ser usuarios de Skype empresarial online o solo usuarios de Microsoft Teams con una interoperabilidad completa y compatibilidad con la Federación.<br><br>
    ![Diagrama de la figura B](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figura C:

- Todos los usuarios de OriginalCompany. <span> com ahora están en la nube (hospedada en Skype empresarial online). Se recomienda que también sean equipos.
- Configuración híbrida de Skype empresarial con el OriginalCompany. <span> se ha deshabilitado la implementación com. La implementación local ha desaparecido.
- Si AcquiredCompany. <span> com no se sincronizó previamente con AAD; para continuar a partir de aquí, es necesario sincronizar ahora. Pero todavía no es híbrido (espacio de direcciones SIP compartido) y, hasta que la organización esté preparada para pasar a híbrido, el dominio SIP en línea de la organización local pura (AcquiredCompany.com) debe permanecer deshabilitado para que los usuarios de Teams en línea puedan comunicarse con los usuarios locales.<br><br>
    ![Diagrama figura C](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figura D:

- AcquiredCompany. <span> com está ahora habilitado como un dominio SIP en línea.
- La implementación local se actualiza para aceptar OriginalCompany. <span> Puerto. (Dominio permitido y los certificados de servidor perimetral actualizados).
- El espacio de direcciones SIP compartido está habilitado entre AcquiredCompany. <span> organización com y Microsoft 365 u Office 365.
- Es posible que algunos usuarios de la organización híbrida se hayan movido a la nube, como el usuario D a continuación (indicado por el sombreado púrpura).<br><br>
    ![Figura D diagrama](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Otros puntos de partida

Los pasos del ejemplo canónico anterior suponen que la organización comienza con dos implementaciones locales federadas que no tienen presencia de Microsoft u Office 365. Sin embargo, algunas organizaciones pueden tener un espacio de Microsoft 365 u Office 365 existente y puede haber distintos puntos de entrada en la secuencia anterior. Hay cuatro configuraciones típicas:

- Varias organizaciones federadas locales sin una organización de Microsoft 365 o de Office 365. En este caso, comience en el paso 1.
- Varias organizaciones locales federadas que ya están sincronizando un bosque de Skype empresarial en un solo inquilino de Azure AD. Esta organización es similar a la organización hipotética de la figura A, que ha completado los pasos 1-6 y debe empezar en el paso 7.
- Una organización híbrida que federa con 1 o más organizaciones locales puras, ninguna de las cuales se sincronizan con AAD. Esta organización sería similar a la organización hipotética de la **figura E**, que se muestra a continuación.
    - Esta organización es similar a la figura B, que ha completado los pasos 1-9, excepto:
        - Las implementaciones no híbridas de Skype empresarial todavía *no* se sincronizan con Azure ad.
        -  Los dominios SIP en línea todavía no están deshabilitados. 
    - Estas organizaciones deben:
        - Complete la migración de la organización híbrida existente y escriba la secuencia anterior en el paso 10.  O
        - Si se desea sincronizar otros bosques de Skype empresarial con AAD antes de completar la migración de la organización híbrida, la organización debe realizar el paso 7 (deshabilitar todos los dominios SIP en línea en cualquier otra implementación local de Skype empresarial que se sincronizará en AAD) y, a continuación, habilitar AAD Connect y solo entonces continuar con el paso 10 (retirar la implementación híbrida original).       
                **Figura E**<br>
                ![Diagrama Figura E](../media/cloudconsolidationfige.png)
- Una organización de Skype empresarial online pura (que puede o no use Teams) que federa con una organización de Skype empresarial local independiente. Una vez que esta organización deshabilita el dominio SIP en línea para la organización local y habilita AAD Connect para la organización de Skype empresarial local, es similar a la organización hipotética que se muestra en la **[figura C](#figure-c)** y que ha completado los pasos 1-11.

## <a name="limitations"></a>Limitaciones

- Debe haber una organización de Microsoft 365 u Office 365 como máximo implicado. No se admite la consolidación en escenarios con más de una organización.
- Solo un bosque de Skype empresarial local puede estar en modo híbrido (espacio de direcciones SIP compartido) a la vez. Todos los demás bosques locales de Skype empresarial deben permanecer exclusivamente en local y deben estar federados entre sí y con la organización de Microsoft 365 u Office 365.
- Antes de migrar a la nube, hay una experiencia asimétrica para los usuarios en esta implementación, porque no todos los usuarios en línea se representan de forma local:
    - La experiencia se puede sumar de la siguiente manera:
        - Cualquier usuario hospedado en línea interactuará con los usuarios locales en el entorno híbrido como si el usuario es híbrido.
        - Los usuarios locales de la implementación híbrida interactuarán con los usuarios en línea que se representan en su directorio local como si fueran híbridos. 
        - Los usuarios locales de la implementación híbrida interactuarán con los usuarios en línea que no están representados en AD local como federados.
    - En la **[figura D](#figure-d)** anterior, el usuario E es local en AcquiredCompany. <span> Puerto.  El usuario E interactuará con el usuario D (hospedado en línea) mediante la experiencia híbrida estándar, pero el usuario E tendrá una experiencia federada con los usuarios A, B y C porque no están representados en el directorio local. Sin embargo, los usuarios A, B y C interactuarán con el usuario E como si el usuario estuviera en un entorno híbrido.
    - Implicaciones de interacción híbrida frente a Federación:
        - La presencia no se suscribe automáticamente a los usuarios federados a menos que el usuario esté marcado como contacto.
        - El desvío de llamadas no funciona entre dominios federados.
        - Los escenarios de transferencia de llamadas son más limitados.
        - La limitación de peticiones puede aplicarse al tráfico federado.
- Dada esta experiencia asimétrica, la compatibilidad oficial para llamar a la funcionalidad en escenarios entre locales entre un usuario local y un usuario de la nube que no se encuentra en el directorio local se limita a peer to peer solamente. 
    - No se admite desvío de llamadas, transferencia, colas de llamadas, etc. entre estos usuarios.
    - Estos escenarios de llamada no admitidos seguirán apareciendo habilitados, pero en muchos casos se producirán de manera impredecible. 
    - En la **[figura D](#figure-d)** anterior, el usuario E es local y las llamadas con los usuarios a, B o C solo se admitirán como de par a par. (Las llamadas con el usuario D no podrían tener limitaciones de soporte técnico).  Sin embargo, después de que el usuario local E se mueva a la nube, esta restricción ya no se aplica.
- Si tiene más de una implementación de Skype empresarial Server 2019 en su entorno, solo 1 de esas implementaciones se puede configurar para que use el operador automático de la organización, ya que esta característica requiere la configuración híbrida de Skype empresarial Server. 
- Se puede ajustar el orden de algunos de los pasos anteriores. El requisito clave que debe cumplirse es que si todos estos elementos son verdaderos:
    - Más de un bosque de Skype empresarial local que se sincroniza con un solo espacio empresarial de AAD
    - El dominio dividido está habilitado con un bosque local
    - Se ha migrado al menos un usuario de la organización híbrida a la nube<br>   A continuación, *debe* deshabilitar todos los demás dominios SIP en línea de cualquier otro bosque local de Skype empresarial. De lo contrario, la Federación entre los usuarios en línea en la organización híbrida y los usuarios locales de otras organizaciones se romperá en una dirección.

## <a name="implications"></a>Percusión

- Debido a que existen limitaciones en la compatibilidad con la funcionalidad de llamadas avanzadas descritas anteriormente, **las organizaciones deben tratar estos Estados asimétricos como transitorios como parte de la migración y no seguirlos como un estado estable**.  
- Por lo general, las organizaciones con varias implementaciones de Skype empresarial local deben empezar con una implementación que se puede migrar completamente a la nube para que la consolidación pueda continuar. Se entiende que, en algunos casos, habrá holdouts de determinados grupos de usuarios para quienes todavía no es viable pasar a Microsoft Teams. Si se trata de una consideración en escenarios en los que intervienen varios bosques de Skype empresarial, empiece a migrar con otro bosque que no tenga estas limitaciones, si es posible.
- Al pasar de local a la nube, los usuarios con relaciones de delegación o que suelen participar en escenarios de desvío de llamadas se deben mover juntos como una unidad.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Consideraciones para cambiar al modo TeamsOnly

Al mover usuarios de local a la nube en un entorno híbrido, puede moverlos a Skype empresarial solo o al modo TeamsOnly. *Si tiene previsto mover usuarios al modo TeamsOnly, asegúrese de leer esta sección primero.*

- Cuando asigna el modo TeamsOnly a un usuario, todos los chats y las llamadas de cualquier otro usuario estarán en el cliente de Microsoft Teams del usuario. 
- Si los usuarios de Skype empresarial local usan principalmente el cliente de Skype empresarial y no los equipos, considere la posibilidad de establecer TeamsUpgradePolicy de modo que el enrutamiento a esos usuarios locales siempre aterriza en Skype empresarial en lugar de en Microsoft Teams. Para garantizar el enrutamiento correcto de los chats y las llamadas entre usuarios que son TeamsOnly y usuarios que todavía usan Skype empresarial local, los usuarios locales deben tener un valor efectivo de TeamsUpgradePolicy con uno de los modos de SfB, en lugar de islas (que es el valor predeterminado). 
    - Para ello, *primero debe configurar la instancia global del inquilino de TeamsUpgradePolicy en uno de estos valores*:
        - SfBWithTeamsCollab (recomendado)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Puede conceder directivas de todo el inquilino con este comando:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Nota: debe hacerlo en un nivel de inquilino, ya que la Directiva no se puede asignar a usuarios individuales que no tengan una dirección SIP en el directorio en línea. Mientras haya deshabilitado los dominios SIP en línea para las implementaciones locales puras, los usuarios de esos dominios no tendrán direcciones SIP en el directorio en línea por diseño. Por lo tanto, la única forma de aplicar la Directiva a los usuarios locales es asignar en el nivel de espacio empresarial. Por el contrario, en los usuarios de la implementación híbrida tendrán una dirección SIP en el directorio en línea, por lo que se les puede asignar de forma explícita una Directiva si desea que tengan un valor distinto al de la directiva global de inquilino.
- La experiencia de usuario del cliente de Microsoft Teams todavía no respeta los modos de SfB de TeamsUpgradePolicy. Por ejemplo, en estos modos, el inicio de llamadas y chats en Microsoft Teams es posible en la actualidad, aunque en el futuro no será el caso. Esto puede causar confusión entre los usuarios porque las respuestas a veces pueden estar en Microsoft Teams y, a continuación, en Skype empresarial, en función de las circunstancias. Se recomienda deshabilitar por separado las llamadas y el chat a través de TeamsMessagingPolicy y TeamsCallingPolicy para los usuarios que todavía están en local.

## <a name="see-also"></a>Vea también

[Actualizar el certificado de límite](cloud-consolidation-edge-certificates.md)

[Actualización de AAD Connect para incluir más de un bosque](cloud-consolidation-aad-connect.md)

[Deshabilitar híbridos para completar la migración a la nube](cloud-consolidation-disabling-hybrid.md)
