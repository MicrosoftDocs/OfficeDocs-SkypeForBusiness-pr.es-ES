---
title: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e2687f00a2d0ccb02e742d5077e472aa1dc37ed
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706620"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia

<a name="about-upgrade-basic"></a>

El propósito de los modos de coexistencia de Skype empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) es proporcionar una experiencia sencilla y predecible a los usuarios finales a medida que las organizaciones pasan de Skype empresarial a teams.  En el caso de una organización que se desplaza a Teams, el modo de **solo equipos** es el destino final de cada usuario, aunque no es necesario que todos los usuarios le asignen **solo equipos** (o cualquier otro modo) al mismo tiempo.  Antes de que los usuarios alcanzaran el modo TeamsOnly, las organizaciones pueden usar cualquiera de los modos de coexistencia de Skype empresarial para garantizar una comunicación predecible entre los usuarios que **solo sean equipos** y aquellos que aún no lo están. 

Cuando un usuario se encuentra en cualquiera de los modos de Skype empresarial, todas las conversaciones y llamadas entrantes se enrutan al cliente de Skype empresarial del usuario. Para evitar la confusión del usuario final y garantizar el enrutamiento adecuado, la funcionalidad de llamadas y chats en el cliente de equipos está deshabilitada cuando un usuario se encuentra en cualquiera de los modos de Skype empresarial. De forma similar, la programación de reuniones de Teams se deshabilita de forma explícita cuando los usuarios se encuentran en los modos SfBOnly o SfBWithTeamsCollab, y se habilita de forma explícita cuando un usuario está en el modo de SfBWithTeamsCollabAndMeetings.

Puesto que la presencia es una indicación de la posibilidad de comunicarse mediante chats y llamadas, cuando las llamadas y los chats están deshabilitadas, la presencia automática en Teams (es decir, la visualización de la propia presencia en el cliente de equipos en la imagen del usuario) también se oculta. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Cómo cambia la funcionalidad disponible en el cliente de Teams según el modo

La funcionalidad disponible en Teams depende del modo de coexistencia del usuario, establecido por TeamsUpgradePolicy. En la tabla siguiente se resume el comportamiento:

|Modo de efectividad del usuario|Experiencia en el cliente de Teams|
|---|---|
|Cualquier modo de Skype para empresas|Las llamadas, la conversación y la presencia automática están deshabilitadas.|
|SfBWithTeamsCollabAndMeetings|Programación de reuniones disponible|
|SfBWithTeamsCollab o SfBOnly<sup>1</sup>|La programación de reuniones no está disponible|
|||

En las siguientes capturas de pantallas se muestra la diferencia entre los **equipos solo** o el modo **islas** y todos los demás modos. Tenga en cuenta que los iconos de llamadas y chats están disponibles de forma predeterminada con **solo equipos** o con el modo **islas** (captura de pantalla izquierda), pero no con los otros modos (captura de pantalla derecha):

![Una comparación en paralelo de los modos de Teams](media/teams-mode-comparison.png)

Además, la presencia automática no está disponible en los otros modos, tal y como se muestra aquí.

![Captura de pantalla de la presencia propia en las reuniones primero](media/meetings-first-no-self-presence-general.png)
 
**Nota:**
<sup>1</sup> en este momento, SfBwithTeamsCollab y SfBOnly se comportan de la misma forma, pero el propósito es que el modo SfBOnly también deshabilite la funcionalidad de canales y archivos en Teams. En el medio, los canales se pueden ocultar con la Directiva de permisos de aplicación.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impacto del modo en otras configuraciones de Directiva
Como se describe anteriormente, el modo de coexistencia del usuario afecta a la funcionalidad que está disponible en el cliente de equipos del usuario. Esto significa que el valor de MODE puede tener prioridad sobre el valor de otras configuraciones de Directiva, según el modo. En concreto, el modo de coexistencia afecta al hecho de que se hayan respetado las siguientes configuraciones de directiva:

|**Modalidad (aplicación)**|**Policy. setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Llamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Programación de reuniones|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Los administradores *no* necesitan establecer explícitamente estas configuraciones de directiva al usar el modo de coexistencia, pero es importante comprender que esta configuración se comporta de la siguiente manera de forma eficaz para un modo determinado. 

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly o islas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Deshabilitado|Deshabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab o SfBOnly|Deshabilitado|Deshabilitado|Deshabilitado|Deshabilitado|
||||||

Al usar PowerShell, el `Grant-CsTeamsUpgradePolicy` cmdlet comprueba la configuración de los valores correspondientes en TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy para determinar si esa configuración sería reemplazada por TeamsUpgradePolicy y, si es así, se proporciona un mensaje informativo en PowerShell.  Como se indicó anteriormente, ya no es necesario establecer estas otras configuraciones de directiva. A continuación se muestra un ejemplo del aspecto de la advertencia de PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Temas relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




