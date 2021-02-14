---
title: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Obtenga información sobre la experiencia del cliente de Teams y el cumplimiento de los modos de coexistencia (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20d1ff52fa59f31b796d2580a0e2819c80caaf42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821030"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia

<a name="about-upgrade-basic"></a>

El propósito de los modos de coexistencia de Skype Empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) es proporcionar una experiencia sencilla y predecible para los usuarios finales a medida que las organizaciones pasen de Skype Empresarial a Teams.  Para las organizaciones que  se muevan a Teams, el modo Solo equipos es el destino final para cada usuario, aunque no es necesario asignar a todos los usuarios solo **Teams** (o a cualquier otro modo) al mismo tiempo.  Antes de que los usuarios alcancen el modo TeamsOnly, las organizaciones pueden usar  cualquiera de los modos de coexistencia de Skype Empresarial para garantizar una comunicación predecible entre los usuarios que son Solo Teams y aquellos que aún no lo están. 

Cuando un usuario se encuentra en cualquiera de los modos de Skype Empresarial, todos los chats y llamadas entrantes se enruta al cliente de Skype Empresarial del usuario. Para evitar la confusión del usuario final y garantizar que la funcionalidad de enrutamiento, llamada y chat del cliente de Teams esté deshabilitada cuando un usuario se encuentra en cualquiera de los modos de Skype Empresarial. De forma similar, la programación de reuniones en Teams se deshabilita explícitamente cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y se habilitan explícitamente cuando un usuario está en el modo SfBWithTeamsCollabAndMeetings.

Dado que la presencia es un indicador de cómo llegar a través del chat y las llamadas, cuando se deshabilitan el chat y las llamadas, la presencia propia en Teams (es decir, la visualización de su propia presencia en el cliente de Teams en la imagen del usuario) también se oculta. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Cómo cambia la funcionalidad disponible en el cliente de Teams en función del modo

La funcionalidad disponible en Teams depende del modo de coexistencia del usuario, establecido por TeamsUpgradePolicy. En la tabla siguiente se resume el comportamiento:

|Modo efectivo del usuario|Experiencia en el cliente de Teams|
|---|---|
|Cualquier modo de Skype Empresarial|Las llamadas, el chat y la presencia propia están deshabilitadas.|
|SfBWithTeamsCollabAndMeetings|La programación de reuniones está disponible|
|SfBWithTeamsCollab o SfBOnly<sup>1</sup>|La programación de reuniones no está disponible|
|||

Las capturas de pantalla siguientes muestran la diferencia entre los modos **Solo equipos** o **Islas** y todos los demás. Tenga en cuenta que los iconos  de chat  y llamada están disponibles de forma predeterminada con los modos Solo equipos o Islas (captura de pantalla izquierda), pero no con los demás modos (captura de pantalla derecha):

![Una comparación en paralelo de los modos de Teams](media/teams-mode-comparison.png)

Además, la presencia propia no está disponible en los demás modos, como se muestra aquí.

![Captura de pantalla de presencia propia en Reuniones primero](media/meetings-first-no-self-presence-general.png)
 
**Nota:** 
 <sup>1</sup> En este momento, SfBwithTeamsCollab y SfBOnly se comportan de la misma manera, pero la intención es que el modo SfBOnly también deshabilite la funcionalidad de Canales y archivos en Teams. De forma provisional, los canales se pueden ocultar con la directiva de permisos de aplicación.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impacto del modo en otras opciones de configuración de directiva
Como se describió anteriormente, el modo de coexistencia de un usuario afecta a qué funcionalidad está disponible en el cliente de Teams del usuario. Esto significa que el valor del modo puede tener prioridad sobre el valor de otras opciones de configuración de directiva, dependiendo del modo. En concreto, el modo de coexistencia afecta a si se respetan las siguientes opciones de configuración de directiva:

|**Modalidad (aplicación)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Llamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Programación de reuniones|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Los administradores *no* necesitan establecer explícitamente estas configuraciones de directiva al usar el modo coexistencia, pero es importante comprender que estas opciones de configuración se comportan de la manera siguiente para un modo determinado. 

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly o Islas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Deshabilitado|Deshabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab o SfBOnly|Deshabilitado|Deshabilitado|Deshabilitado|Deshabilitado|
||||||

Al usar PowerShell, el cmdlet comprueba la configuración de las opciones correspondientes en `Grant-CsTeamsUpgradePolicy` TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy para determinar si teamsUpgradePolicy y, en ese caso, se proporciona un mensaje informativo en PowerShell.  Como se indicó anteriormente, ya no es necesario establecer estas otras opciones de configuración de directiva. A continuación se muestra un ejemplo del aspecto que tiene la advertencia de PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Temas relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




