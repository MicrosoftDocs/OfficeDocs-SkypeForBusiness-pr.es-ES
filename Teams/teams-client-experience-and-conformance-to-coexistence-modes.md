---
title: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Experiencia de los equipos cliente y la compatibilidad con los modos de coexistencia
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e62dd8a19e2207f6b40864cab19a3fda48d184fe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204662"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia

> [!NOTE]
> Esta página describe los cambios importantes, lanzados recientemente en el comportamiento del cliente de los equipos cuando los usuarios están en cualquiera de los Skype para los modos de negocio (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).


El propósito de los modos de la coexistencia es proporcionar una experiencia sencilla y predecible para los usuarios finales como transición de las organizaciones de Skype para la empresa a los equipos.  Para una organización mover a los equipos, el modo de TeamsOnly es el destino final de cada usuario, aunque no todos los usuarios deben asignarse TeamsOnly (o cualquier otro modo) al mismo tiempo.  Antes de alcanzar el modo TeamsOnly de los usuarios, las organizaciones pueden usar cualquiera de los Skype para los modos de negocio (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantizar la comunicación entre los usuarios que están TeamsOnly y aquellos que no están todavía predecible. 

Cuando un usuario se encuentra en cualquiera de los Skype para los modos de negocio, todos los chats entrantes y las llamadas se enrutan a Skype del usuario para clientes empresariales. Para evitar confusiones al usuario final y garantizar el enrutamiento correcto, llamadas y conversaciones funcionalidad en el cliente de los equipos está deshabilitada cuando un usuario se encuentra en cualquiera de los Skype para los modos de negocio. De forma similar, programar reuniones en los equipos está deshabilitado de forma explícita cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y explícitamente habilitado cuando un usuario se encuentra en el modo de SfBWithTeamsCollabAndMeetings.   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>¿Cómo se cambia la funcionalidad disponible en el cliente de los equipos basada en el modo
Depende de la funcionalidad disponible en los equipos en modo de coexistencia del usuario, tal como lo establece TeamsUpgradePolicy. En la tabla siguiente se resume el comportamiento:

|Modo eficaz del usuario|Experiencia de cliente de los equipos|
|---|---|
|Cualquier Skype para el modo de negocio|Llamadas y conversaciones están deshabilitadas.|
|SfBWithTeamsCollabAndMeetings|Programación de la reunión está disponible|
|SfBWithTeamsCollab o SfBOnly<sup>1</sup>|Programación de la reunión no está disponible|
|||

Las capturas de pantalla siguientes ilustran la diferencia entre el modo de TeamsOnly o islas y todos los demás modos. Tenga en cuenta que están disponibles los iconos de chat y llamar al método con TeamsOnly o Islas modo (captura de pantalla de la izquierda), pero no con los demás modos (captura de pantalla derecha):

![Muestra las comparaciones de modo de equipos](media/teams-mode-comparison.png)


 
**Nota:**
<sup>1</sup> por ahora, SfBwithTeamsCollab y SfBOnly se comportan de la misma, pero la intención es para que el modo de SfBOnly deshabilitar también la funcionalidad de canales y los archivos en los equipos; Sin embargo, actualmente no hay ninguna opción que permite que esta funcionalidad en los equipos que va a deshabilitar.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impacto del modo en otras configuraciones de directiva
Como se describió anteriormente, del impacto del modo de coexistencia de un usuario qué funcionalidad está disponible en el cliente de los equipos del usuario. Esto significa que el valor del modo puede tener prioridad sobre el valor de otras configuraciones de directiva, según el modo. En concreto, afecta al modo de coexistencia si se respetan las siguientes opciones de directiva:

|**Modalidad (aplicación)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Llamar a|TeamsCallingPolicy.AllowPrivateCalling|
|Programación de reuniones|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Los administradores necesitan *no* establecer explícitamente estas configuraciones de directiva cuando se utiliza el modo de coexistencia, pero es importante comprender que estas opciones de configuración eficazmente se comportan como sigue para un modo determinado. 

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly o Islas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Deshabilitado|Deshabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab o SfBOnly|Deshabilitado|Deshabilitado|Deshabilitado|Deshabilitado|
||||||

Cuando se usa PowerShell, la `Grant-CsTeamsUpgradePolicy` cmdlet comprueba la configuración de los valores correspondientes en TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy para determinar si esa configuración podría ser reemplazada por TeamsUpgradePolicy y si es así, un mensaje informativo se proporciona en PowerShell.  Como se mencionó anteriormente, ya no es necesario establecer estas otras configuraciones de directiva. A continuación es un ejemplo del aspecto qué la advertencia de PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>Temas relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




