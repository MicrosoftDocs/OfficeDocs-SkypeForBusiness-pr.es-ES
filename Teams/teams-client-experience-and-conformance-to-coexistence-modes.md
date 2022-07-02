---
title: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Obtenga información sobre la experiencia del cliente de Teams y la conformidad con los modos de coexistencia (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
ms.localizationpriority: medium
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
ms.openlocfilehash: 91ea07d74bf9b08f627d86191ea08fc0eda1ac4c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605839"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia

<a name="about-upgrade-basic"></a>

El propósito de los modos de coexistencia de Skype Empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) es proporcionar una experiencia sencilla y predecible para los usuarios finales a medida que las organizaciones pasan de Skype Empresarial a Teams.  Para una organización que pasa a Teams, el modo **Solo equipos** es el destino final para cada usuario, aunque no todos los usuarios necesitan que se les asigne **solo Teams** (o cualquier otro modo) al mismo tiempo.  Antes de que los usuarios lleguen al modo TeamsOnly, las organizaciones pueden usar cualquiera de los modos de coexistencia de Skype Empresarial para garantizar una comunicación predecible entre los usuarios que son **solo Teams** y los que aún no lo están. 

Cuando un usuario se encuentra en cualquiera de los modos Skype Empresarial, todos los chats y llamadas entrantes se enrutan al cliente Skype Empresarial del usuario. Para evitar confusiones con el usuario final y garantizar que la funcionalidad correcta de enrutamiento, llamadas y chat en el cliente de Teams está deshabilitada cuando un usuario se encuentra en cualquiera de los modos Skype Empresarial. De forma similar, la programación de reuniones en Teams se deshabilita explícitamente cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y se habilitan explícitamente cuando un usuario está en el modo SfBWithTeamsCollabAndMeetings.

Dado que la presencia es una indicación de la accesibilidad a través del chat y las llamadas, cuando se deshabilitan el chat y las llamadas, la auto presencia en Teams (es decir, la visualización de su propia presencia en el cliente de Teams en la imagen del usuario) también está oculta. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Cómo cambia la funcionalidad disponible en el cliente de Teams en función del modo

La funcionalidad disponible en Teams depende del modo de coexistencia del usuario, establecido por TeamsUpgradePolicy. En la tabla siguiente se resume el comportamiento:

|Modo eficaz del usuario|Experiencia en el cliente de Teams|
|---|---|
|Cualquier modo de Skype Empresarial|Las llamadas, el chat y la presencia propia están deshabilitadas.|
|SfBWithTeamsCollabAndMeetings|La programación de reuniones está disponible|
|SfBWithTeamsCollab o SfBOnly<sup>1</sup>|La programación de reuniones no está disponible|
|||

Las capturas de pantalla siguientes muestran la diferencia entre el modo **Solo teams** o **Islas** y todos los demás modos. Tenga en cuenta que los iconos de chat y llamada están disponibles de forma predeterminada con **el modo Solo Teams** o **El modo islas** (captura de pantalla izquierda), pero no con los otros modos (captura de pantalla derecha):

![Comparación en paralelo de los modos de Teams.](media/teams-mode-comparison.png)

Además, la presencia propia no está disponible en los otros modos, como se muestra aquí.

![Captura de pantalla de la presencia propia en Reuniones en primer lugar.](media/meetings-first-no-self-presence-general.png)
 
**Nota:**
 <sup>1</sup> En este momento, SfBwithTeamsCollab y SfBOnly se comportan de la misma manera, pero la intención es que el modo SfBOnly deshabilite también la funcionalidad de Canales y Archivos en Teams. Mientras tanto, los canales se pueden ocultar mediante la directiva Permisos de aplicación.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impacto del modo en otras opciones de configuración de directiva
Como se describió anteriormente, el modo de coexistencia de un usuario afecta a la funcionalidad disponible en el cliente de Teams del usuario. Esto significa que el valor del modo puede tener prioridad sobre el valor de otras configuraciones de directiva, dependiendo del modo. Específicamente, el modo de coexistencia afecta a si se respetan las siguientes configuraciones de directiva:

|**Modalidad (App)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Llamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Programación de reuniones|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Los administradores *no* necesitan establecer explícitamente estas configuraciones de directiva al usar el modo de existencia común, pero es importante comprender que estas configuraciones se comportan de la manera siguiente para un modo determinado. 

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly o Islas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Deshabilitado|Deshabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab o SfBOnly|Deshabilitado|Deshabilitado|Deshabilitado|Deshabilitado|
||||||

Al usar PowerShell, el `Grant-CsTeamsUpgradePolicy` cmdlet comprueba la configuración de la configuración correspondiente en TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy para determinar si dicha configuración se sustituiría por TeamsUpgradePolicy y, en ese caso, se proporciona un mensaje informativo en PowerShell.  Como se mencionó anteriormente, ya no es necesario establecer estas otras opciones de configuración de directiva. El siguiente es un ejemplo de la apariencia de la advertencia de PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Temas relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md)