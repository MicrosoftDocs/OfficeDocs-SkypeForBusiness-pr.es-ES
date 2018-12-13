---
title: Consolidación de la nube para equipos y Skype para la empresa
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: En este artículo se describe cómo lograr que la consolidación para las organizaciones con implementaciones locales de Skype para empresas (o Lync) que buscan mover para mover su carga de trabajo de comunicaciones unificadas para los equipos o Skype para profesionales en línea.
ms.openlocfilehash: 09a19b884b67f9d6c3dbbe552f2576b6b5e68674
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247741"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidación de la nube para equipos y Skype para la empresa

> [!Note]
> Esta es una característica en versión preliminar o anticipada. 

Muchas grandes empresas tienen más de un local bosque de AD y, en algunos casos, los clientes tienen más de un Exchange o Skype para la implementación de Business Server (o Lync Server). Además, incluso las organizaciones con un solo bosque local se encuentra a sí mismos en una situación similar a través de una empresarial fusión o adquisición. Como estos clientes pasar a la nube, que desean consolidar el varias instancias de una carga de trabajo determinada local en la nube en un único inquilino de Office 365. En este artículo se describe cómo lograr que la consolidación para las organizaciones con varias implementaciones locales de Skype para empresas (o Lync) que desea mover su carga de trabajo de comunicaciones unificadas para la nube de Microsoft, por ejemplo, Microsoft Teams o Skype para profesionales en línea.

Históricamente, ha sido las instrucciones para que los clientes en esta situación consolidar las implementaciones locales en primer lugar y, a continuación, mover a la nube. Mientras sigue siendo una opción, en este artículo se describe una solución basada en la nueva funcionalidad que permite a las organizaciones con varios Skype para implementaciones empresariales para migrar una implementación en un momento en un único inquilino de Office 365, sin necesidad de hacer local consolidación. Tenga en cuenta que incluso con esta nueva funcionalidad, Skype para profesionales en línea y Teams Microsoft no admite varios Skype para bosques empresarial/Lync en modo híbrido con un único inquilino de Office 365. 

> [!Important]
> Antes de utilizar a esta guía para la configuración, asegúrese de revisar y comprender las [limitaciones](#limitations), como es posible que afectan a su organización.

## <a name="overview-of-cloud-consolidation"></a>Información general de la consolidación de la nube

Consolidación de todos los usuarios de local en la nube en un único inquilino de Office 365 se puede lograr para las organizaciones con varios Skype para las implementaciones empresariales, siempre que se cumplan los requisitos de la claves siguientes:

- Debe haber como máximo un inquilino de Office 365 implicados. No se admite la consolidación en escenarios con más de un inquilino de Office 365.
- En cualquier momento dado, sólo un local puede ser Skype para el bosque de negocio en modo híbrido (Shared espacio de direcciones SIP). Todos los demás Skype local para bosques de negocio debe permanecer local (y supuestamente federados con cada una de las demás). Tenga en cuenta que estos otro local las organizaciones *pueden* sincronizar con AAD si así lo desea con la [nueva funcionalidad para deshabilitar los dominios SIP en línea](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps) disponible a partir de diciembre de 2018.

Los clientes con las implementaciones de Skype para la empresa en varios bosques deben totalmente migrar todos los usuarios de un único híbrido Skype para el bosque de negocio individualmente en el inquilino de Office 365 con la funcionalidad de Shared espacio de direcciones SIP y, a continuación, deshabilitar híbrida con el implementación local, antes de pasar a migrar el siguiente local Skype para la implementación de la empresa. Antes de que se está migrando a la nube, los usuarios locales permanecen en un estado federado con todos los usuarios que no se representan en el mismo directorio del usuario local.  

## <a name="canonical-example-of-cloud-consolidation"></a>Ejemplo canónico de consolidación de la nube

Considere la posibilidad de una organización con dos independiente federada las implementaciones locales de Skype para la empresa que desea consolidar ellos en línea en Microsoft Teams o Skype para profesionales en línea.


|Detalles del estado original |Detalles de estado deseado |
|---------|---------|
|<ul><li>2 Skype independientes para la empresa local implementaciones en bosques separados de AD<li>Como máximo 1 bosque se encuentra en la implementación híbrida con Skype para profesionales en línea <li> Expandidas están federados con cada una de las demás <li>Los usuarios no están sincronizados entre estos bosques<li> La organización puede tener un inquilino de Office 365 y es posible que se está sincronizando los sus directorios en Azure AD</ul>|<ul> <li>1 inquilino de office 365<li>No hay más local de las implementaciones, por lo que no híbrida restante<li>Todos los usuarios de local están hospedados en Skype para profesionales en línea y, opcionalmente, es posible sólo los equipos de los usuarios <li>No hay espacio local de Skype para la empresa en cualquier lugar <li>Los usuarios seguirán teniendo la autenticación local</ul> |

![Consolidación de dos implementaciones independientes federadas local](../media/cloudconsolidationfig1.png)  

Los pasos básicos para obtener desde el estado original en el estado final deseado están por debajo.  Tenga en cuenta que algunas organizaciones posible que su punto de partida en algún lugar en medio de estos pasos. Vea [otros puntos de partida](#other-starting-points), más adelante en este artículo. Por último, en algunos casos el orden se puede ajustar, según la necesidad. [Limitaciones y restricciones de clave](#limitations) se describen más adelante.

1.  Obtenga a un inquilino de Office 365 si no existe uno aún.
2.  Asegúrese de que todos los dominios SIP relevantes entre ambas implementaciones locales estén comprobadas dominios de Office 365.
3.  Elija uno Skype para la implementación de empresa que será híbrida con Office 365. En este ejemplo, vamos a utilizar OriginalCompany. <span>com.
4.  [Habilitar AAD conectar para el bosque](configure-azure-ad-connect.md) que primero se convertirán en híbrida (OriginalCompany.<span> com). 
5.  Si se presentan los equipos en su organización, establezca la directiva de todo el inquilino de [TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) a SfBWithTeamsCollab o a uno de los otros modos de SfB (SfBOnly o SfBWithTeamsCollabAndMeetings). Esto es fundamental para garantizar el enrutamiento de llamadas y charlas de los usuarios que mover a los equipos sólo a los usuarios que permanezcan en local.
6.  Se recomienda en este momento (aunque aún no se requiere hasta el paso 11) para [Habilitar AAD Connect para el otro bosque](cloud-consolidation-aad-connect.md) (AcquiredCompany.<span> com). Suponiendo que AAD conectar está habilitada en ambos bosques, la organización tiene un aspecto **[Figura A](#figure-a)**, que es posible que un punto de partida común para algunos expandidas. 
7.  Para todos los dominios SIP hospedados por otras implementaciones locales (en este caso, AcquiredCompany.<span> com), [deshabilitar estos dominios SIP en Skype para profesionales Online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) utilizando `Disable-CsOnlineSipDomain` en PowerShell. (Esto es una nueva funcionalidad a partir de diciembre de 2018).
8.  [Configuración de Skype para entornos híbridos de negocio](configure-federation-with-skype-for-business-online.md) para OriginalCompany. <span>com (la misma implementación que aún haya habilitado dominios SIP en línea).
9.  En la implementación híbrida (OriginalCompany.<span> com), empezar a [mover los usuarios de Skype para la empresa local a la nube](move-users-between-on-premises-and-cloud.md) (si los equipos sólo o no) para que la cuenta está hospeda en Skype para profesionales en línea. Ahora la organización tiene un aspecto **[Figura B](#figure-b)**. Los cambios claves de la figura son:
    - Los usuarios de ambos directorios local están ahora en AAD.
    - AcquiredCompany. <span>com es un dominio SIP en línea deshabilitada.
    - Algunos usuarios se han movido en línea a cualquier Skype para profesionales en línea o los equipos. (Vea a usuario púrpura.)
10. Una vez que todos los usuarios se mueven a la nube, [Deshabilitar híbrida con la Skype para la implementación local de empresa](cloud-consolidation-disabling-hybrid.md) para OriginalCompany. <span>com de Office 365:  
    - Deshabilitar dominio dividido en el inquilino de Office 365.
    - Deshabilitar la capacidad de comunicarse con Office 365 en OriginalCompany. <span>com local.
    - Actualizar registros DNS para OriginalCompany. <span>com para que apunte a Office 365.
11. Si no lo ha hecho ya, [Habilitar AAD conectar para el siguiente bosque](cloud-consolidation-aad-connect.md) que se realizarán híbrida (AcquiredCompany.<span> com). En este momento, la organización tiene un aspecto **[Figura C](#figure-c)**. Esto puede ser otro punto de partida común para algunas organizaciones. 
12. En PowerShell, [Habilitar los dominios SIP para la implementación local siguiente](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) que se realizarán híbrido, AcquiredCompany. <span>com. Esto se realiza utilizando `Enable-CsOnlineSipDomain`, que es una nueva funcionalidad disponible a partir de diciembre de 2018.
13. Si utiliza federación cerrada, debe agregar todos los dominios SIP (excluyendo *. microsoftonline.com) del inquilino online puro como dominios permitidos en **mismo** Office 365. Tenga en cuenta que puede tardar algún tiempo antes de que el cambio tendrá efecto y no hay ningún riesgo en hacerlo pronto, por lo que es recomendable hacerlo antes de continuar con el paso 14.
14. Actualizar el entorno local para aceptar todos los dominios SIP desde el inquilino en línea, de manera que coincidan con.
    - [Actualizar el SAN en todos los certificados de borde](cloud-consolidation-edge-certificates.md) para tener el mismo valor que antes, además de los valores de los dominios SIP en línea existentes (excepto *. microsoftonline.com), en este caso, Sip.OriginalCompany. <span>com.
    - Asegúrese de que OriginalCompany. <span>com es un [permitido dominio](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain) en la implementación local, AcquiredCompany. Agregar dominios permitidos.
15. [Habilitar Skype para entornos híbridos de negocio](configure-federation-with-skype-for-business-online.md) entre local AcquiredCompany. <span>com y la nube.
16. Como deseada, [migre los usuarios de local a la nube](move-users-between-on-premises-and-cloud.md). Puede migrar los usuarios ya sea directamente a [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) modo o se pueden migrar ellos primero a Skype para profesionales en línea. Durante este estado, la organización tiene un aspecto **[Figura D](#figure-d)**.
17. Una vez que todos los usuarios se migran, [Deshabilitar híbrida con el entorno local](cloud-consolidation-disabling-hybrid.md) para *realizar la nube puro organización*!

Los diagramas siguientes muestran la configuración en varios puntos claves durante este proceso.

##### <a name="figure-a"></a>Figura A:

- Ambos sincronización de las organizaciones a través de AAD conectar, por lo que AAD ahora tiene todos los usuarios de ambos local implementaciones.
- Todos los usuarios alojados local.  
- Skype para entornos híbridos de negocio aún *no* está configurado.
- Si los usuarios en cualquier implementación de usar los equipos, no podrá federarse con los demás (o cualquier organización) ni tendrán la interoperabilidad con cualquier Skype para los usuarios empresariales. Mientras que en esta etapa, Microsoft recomienda únicamente por medio de los equipos de los canales.<br><br>
    ![Diagrama de la figura A](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figura B:

- AcquiredCompany. <span>com es un dominio SIP en línea [deshabilitado](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) . Todos los usuarios se encuentran en local. Si usan los equipos que no tengan federación o interoperabilidad. Mientras que en esta etapa, Microsoft recomienda únicamente por medio de los equipos de los canales.
- Skype para entornos híbridos de negocio se ha habilitado para una de las organizaciones locales.
- Algunos usuarios de la organización híbrida se han movido a la nube (usuario A como se indica mediante el sombreado de color púrpura). Estos usuarios pueden ser Skype para usuarios profesionales en línea o los equipos sólo los usuarios con interoperabilidad total y compatibilidad con la federación.<br><br>
    ![Diagrama de la figura B](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figura C:

- Todos los usuarios de OriginalCompany. <span>com están ahora en la nube (hospeda en Skype para profesionales en línea). Se recomienda que también sean sólo los equipos.
- Skype para la configuración híbrida de negocio con la OriginalCompany. <span>se ha deshabilitado la implementación de com. La implementación local ya no existe.
- Si AcquiredCompany. <span>com anteriormente no era sincronización con AAD, para continuar desde aquí que necesita para sincronizar ahora. Pero aún no está híbrida (espacio de direcciones SIP compartido), y hasta que esté preparada para pasar a entornos híbridos de la organización, el dominio SIP en línea para la organización local puro (AcquiredCompany.com) debe permanecer deshabilitado, por lo que los usuarios de los equipos en línea pueden comunicarse con usuarios locales.<br><br>
    ![Diagrama de la figura C](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figura D:

- AcquiredCompany. <span>com ahora está habilitado como un dominio SIP en línea.
- Local se ha actualizado para aceptar OriginalCompany. <span>com. (Ambas permiten dominio, y se actualizan los certificados perimetrales).
- Espacio de direcciones SIP compartido está habilitado entre AcquiredCompany. <span>com e inquilino de Office 365.
- Algunos usuarios de la organización híbrida es posible que se ha movido a la nube, como usuario D siguiente (que se indican mediante el sombreado de color púrpura).<br><br>
    ![Diagrama de la figura D](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Otros puntos de partida

Los pasos descritos en el ejemplo canónico anterior se suponen que la organización se inicia con dos federada las implementaciones locales con ningún presencia de Office 365. Sin embargo, algunas organizaciones pueden tener un espacio existente de Office 365, y puede haber puntos de entrada diferentes en la secuencia anterior. Existen cuatro configuraciones típicas:

- Varias organizaciones federadas local con ningún inquilino de Office 365. En este caso, comience en el paso 1.
- Varias organizaciones federadas local que ya están sincronizando varios Skype para el bosque de negocio en un único Azure AD de inquilinos. Este tipo de organización es similar a la organización hipotética en la figura A, que se ha completado los pasos 1 al 6 y debe comenzar con el paso 7.
- Una organización híbrida que permite la federación con 1 o más otras organizaciones puro local, ninguno de los cuales la sincronización a AAD. Este tipo de organización sería similar a la organización hipotética en **E de la figura**, se muestra a continuación.
    - Esta organización es similar a la figura B, que se ha completado los pasos 1 a 9, excepto:
        - Su Skype no híbridas para implementaciones empresariales son *no* aún sincronización con Azure AD.
        -  Dominios SIP en línea no están deshabilitados aún. 
    - Estas organizaciones deben ya sea:
        - Completar la migración de la organización híbrida existente y especifique la secuencia anterior en el paso 10.  OR,
        - Si se desea sincronizar cualquier otra Skype para bosques de negocio en AAD antes de completar la migración de la organización híbrida, a continuación, la organización debe llevar a cabo paso 7 (deshabilitar en línea de todos los dominios SIP en cualquier otro Skype local para la implementación de empresa que se va a sincronización en AAD) y, a continuación, habilite AAD conectar y sólo a continuación, continúe con el paso 10 (retirar la implementación híbrida original).       
                **Figura E**<br>
                ![Diagrama de la figura E](../media/cloudconsolidationfige.png)
- Skype puro para la organización en línea de negocio (que puede o no puede usar los equipos) que permite la federación con un Skype independiente local para la organización empresarial. Una vez que esta organización deshabilita el dominio SIP en línea para la organización local y permite conectar AAD para el Skype local para la organización empresarial, es similar a la que se muestra en **[La figura C](#figure-c)** que se ha completado los pasos de organización hipotética 1-11.

## <a name="limitations"></a>Limitaciones

- Debe haber como máximo un inquilino de Office 365 implicados. No se admite la consolidación en escenarios con más de un inquilino de Office 365.
- Una sola local puede ser Skype para el bosque de negocio en modo híbrido (espacio de direcciones SIP compartido) a la vez. Todos los demás local Skype para bosques de negocio debe permanecer puramente local y debe federado con entre sí y con el inquilino de Office 365.
- Antes de que se está migrando a la nube, hay una experiencia asimétrica para los usuarios en esta implementación, debido a que no todos los usuarios en línea son representado local:
    - La experiencia se puede resumir como sigue:
        - Cualquier usuario hospedado en línea interactuarán con los usuarios locales en el entorno híbrido como si el usuario es un entorno híbrido.
        - Usuarios locales en la implementación híbrida interactuarán con los usuarios en línea que se representan en su directorio local como si fueran híbrida. 
        - Local que los usuarios en la implementación híbrida interactuarán con los usuarios en línea que no se representan en AD local como federados.
    - En **[La figura D](#figure-d)** anterior, usuario E es local en AcquiredCompany. <span>com.  Usuario E interactuarán con usuario D (hospedado en línea) utilizando la experiencia de híbrido estándar, pero el usuario E tendrán una experiencia federada con los usuarios A, B y C debido a que no se representan en el directorio local. Sin embargo, los usuarios A, B y C interactuarán con el usuario E como si el usuario se encontraban en híbrida.
    - Implicaciones de interacción con el que se va a híbrida y federación:
        - Presencia no automáticamente suscrito a para los usuarios federados a menos que el usuario se marca como un contacto.
        - No funciona el desvío de llamadas entre dominios federados.
        - Escenarios de transferencia de llamada están más limitados.
        - Limitación de peticiones se puede aplicar a tráfico federado.
- Dada esta experiencia asimétrica, oficial de soporte técnico para la funcionalidad de llamada en escenarios entre entornos entre un usuario local y un usuario en la nube que no es en el directorio local está limitado a sólo punto a punto. 
    - Llame al desvío de llamadas, transferencia, colas de llamadas, etc. entre estos usuarios no se admite.
    - Estos escenarios llamados no admitidos seguirá apareciendo habilitados, pero en muchos casos se producirá un error de manera impredecible. 
    - En **[D de la figura](#figure-d)** anterior, el usuario E es local y se admitirá llamadas con los usuarios A, B o C sólo como punto a punto. (Llamadas con usuario D no tendría limitaciones de compatibilidad).  Sin embargo, después de que el usuario local E se mueve a la nube, esta restricción ya no se aplica.
- Si tiene más de una implementación de Skype para Business Server 2019 en su entorno, sólo 1 de esos implementación puede configurarse para usar el operador automático de organización, ya que esa característica requiere Skype para la configuración híbrida de Business Server. 
- Se puede ajustar el orden de algunos de los pasos anteriores. El requisito de clave que se debe cumplir es si se cumplen todas estas condiciones:
    - Más de un local Skype para la sincronización de bosque de negocio a un único inquilino AAD
    - Dominio dividido está habilitado con un bosque local
    - Al menos un usuario en la organización híbrida se ha migrado a la nube<br>   A continuación, *debe* deshabilitar todos los demás dominios SIP en línea desde cualquier otro Skype local para el bosque de negocio. De lo contrario, se interrumpirá la federación entre usuarios en línea en el híbrido local y organización a los usuarios de otras organizaciones en una dirección.

## <a name="implications"></a>Implicaciones

- Debido a que no existen limitaciones en la compatibilidad con la funcionalidad llamada avanzada como se describió anteriormente, **las organizaciones deben tratar estos Estados asimétricos como transitorios como parte de la migración y no procesarlas como estado estable**.  
- Las organizaciones con varios Skype local para implementaciones empresariales generalmente deben comenzar con una implementación que se puede migrar completamente a la nube, para que pueda continuar la consolidación. Se entiende que en algunos casos habrá holdouts de determinados grupos de usuarios para los que aún no está viable para mover a los equipos. Cuando se trata de una consideración en escenarios que implican varios Skype para bosques de negocio, empezar a migrar con otro bosque que no tiene estas limitaciones, si es posible.
- Al pasar de local a la nube, los usuarios que tienen relaciones de delegación o suelen ser participan en escenarios se va a mover juntos como una unidad de desvío de llamadas.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Consideraciones para pasar a modo de TeamsOnly

Al mover usuarios de local a la nube en un entorno híbrido, pueden trasladarse al puede ser Skype para el modo sólo empresarial o TeamsOnly. *Si va a mover los usuarios al modo TeamsOnly, asegúrese de leer esta sección en primer lugar.*

- Cuando se asigna el modo TeamsOnly a un usuario, todas las charlas y las llamadas procedentes de cualquier otro usuario se colocarán en el cliente de los equipos de dicho usuario. 
- Para asegurarse de enrutamiento correcto de chats y llamadas entre los usuarios que están TeamsOnly y los usuarios que aún están usando Skype para la empresa local, debe asegurarse de que los usuarios locales tienen TeamsUpgradePolicy con uno de los modos de SfB, en lugar de islas (que es el valor predeterminado ). 
    - Para ello, *en primer lugar debe establecer la instancia global de la multiempresa de TeamsUpgradePolicy a uno de estos valores*:
        - SfBWithTeamsCollab (recomendado)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Puede conceder todo el inquilino directiva mediante el uso de este comando:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Nota: Actualmente, debe hacerlo en un nivel de todo el inquilino debido a que la directiva no se pueden asignar a usuarios individuales que no tienen una dirección SIP en el directorio en línea. Mientras se han deshabilitado los dominios SIP en línea para sus implementaciones puro local, usuarios en esos dominios no tienen direcciones SIP en el directorio en línea por diseño. Por lo tanto, la única forma de aplicar la directiva a los usuarios locales es mediante la asignación en el nivel de inquilino. Por el contrario, del entorno híbrido de implementación los usuarios tendrán una dirección SIP en el directorio en línea por lo que pueden tener asignados explícitamente una directiva si se desea que cuentan con un valor distinto de la directiva global del inquilino.
- La experiencia de usuario de cliente de los equipos no respeta aún los modos de SfB de TeamsUpgradePolicy. Por ejemplo, cuando en estos modos, inicio de llamadas y conversaciones en los equipos es actualmente posible, aunque en el futuro no sea el caso. Debido a que las respuestas podrán llegar a veces en los equipos y, a veces, Skype para la empresa, según las circunstancias, esto puede causar confusión entre los usuarios. Se recomienda por separado deshabilite las llamadas y conversaciones a través de TeamsMessagingPolicy y TeamsCallingPolicy para los usuarios que están todavía en local.

## <a name="see-also"></a>Vea también

[Actualizar el certificado de servidor perimetral](cloud-consolidation-edge-certificates.md)

[Actualizar AAD conectar para incluir más de un bosque](cloud-consolidation-aad-connect.md)

[Deshabilitar híbrido para completar la migración a la nube](cloud-consolidation-disabling-hybrid.md)