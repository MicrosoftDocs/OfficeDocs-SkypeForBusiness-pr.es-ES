---
title: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Obtenga información sobre Teams cliente y la conformidad con los modos de coexistencia (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: e07d33b8aa1b379823ffa3aaa605dc26c31604c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119259"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia

<a name="about-upgrade-basic"></a>

El propósito de los modos de coexistencia Skype Empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) es proporcionar una experiencia sencilla y predecible para los usuarios finales a medida que las organizaciones transición de Skype Empresarial a Teams.  Para una organización que se mueve a Teams, el modo **solo Teams** es el destino final para cada usuario, aunque no todos los usuarios tienen que asignarse **Teams** Solo (o cualquier otro modo) al mismo tiempo.  Antes de que los usuarios lleguen al modo TeamsOnly, las organizaciones pueden usar cualquiera de los modos de coexistencia de Skype Empresarial para garantizar una comunicación predecible entre los usuarios que son **Teams Only** y los que aún no lo están. 

Cuando un usuario está en cualquiera de los modos Skype Empresarial, todos los chats y llamadas entrantes se enruta al cliente Skype Empresarial usuario. Para evitar confusiones de los usuarios finales y asegurarse de que la funcionalidad de enrutamiento, llamadas y chats del cliente de Teams está deshabilitada cuando un usuario está en cualquiera de los Skype Empresarial modos. De forma similar, la programación de reuniones en Teams se deshabilita explícitamente cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y se habilita explícitamente cuando un usuario está en el modo SfBWithTeamsCollabAndMeetings.

Como la presencia es una indicación de la capacidad de acceso a través del chat y las llamadas, cuando el chat y las llamadas están deshabilitados, la presencia personal en Teams (es decir, la presentación de su propia presencia en el cliente de Teams en la imagen del usuario) también está oculta. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Cómo cambia la funcionalidad disponible Teams cliente en función del modo

La funcionalidad disponible en Teams depende del modo de coexistencia del usuario, establecido por TeamsUpgradePolicy. En la tabla siguiente se resume el comportamiento:

|Modo efectivo del usuario|Experiencia en Teams cliente|
|---|---|
|Cualquier Skype Empresarial de datos|Las llamadas, el chat y la presencia propia están deshabilitadas.|
|SfBWithTeamsCollabAndMeetings|La programación de reuniones está disponible|
|SfBWithTeamsCollab o SfBOnly<sup>1</sup>|La programación de reuniones no está disponible|
|||

Las siguientes capturas de pantalla ilustran la **diferencia entre Teams modo Solo** o Islas y todos los demás modos.  Tenga en cuenta que los iconos de chat y  llamadas están disponibles de forma predeterminada con el modo **solo Teams** o Islas (captura de pantalla izquierda), pero no con los otros modos (captura de pantalla derecha):

![Una comparación en paralelo de los Teams modos](media/teams-mode-comparison.png)

Además, la presencia personal no está disponible en los otros modos, como se muestra aquí.

![Captura de pantalla de presencia personal en Reuniones Primero](media/meetings-first-no-self-presence-general.png)
 
**Nota:** 
 <sup>1</sup> En este momento, SfBwithTeamsCollab y SfBOnly se comportan igual, pero la intención es que el modo SfBOnly también deshabilite la funcionalidad Canales y archivos en Teams. Entre tanto, los canales se pueden ocultar con la directiva permisos de aplicación.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impacto del modo en otras configuraciones de directiva
Como se ha descrito anteriormente, el modo de coexistencia de un usuario afecta a la funcionalidad que está disponible en el cliente de Teams usuario. Esto significa que el valor del modo puede tener prioridad sobre el valor de otras configuraciones de directiva, dependiendo del modo. En concreto, el modo de coexistencia afecta a si se respetan las siguientes configuraciones de directiva:

|**Modalidad (aplicación)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Llamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Programación de reuniones|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Los administradores *no* necesitan establecer explícitamente esta configuración de directiva al usar el modo de coexistencia, pero es importante comprender que estas configuraciones se comportan de la manera siguiente para un modo determinado. 

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly o Islas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Deshabilitado|Deshabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab o SfBOnly|Deshabilitado|Deshabilitado|Deshabilitado|Deshabilitado|
||||||

Al usar PowerShell, el cmdlet comprueba la configuración de la configuración correspondiente en `Grant-CsTeamsUpgradePolicy` TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy para determinar si TeamsUpgradePolicy reemplazaría dicha configuración y, si es así, se proporciona un mensaje informativo en PowerShell.  Como se ha indicado anteriormente, ya no es necesario establecer estas otras configuraciones de directiva. A continuación se muestra un ejemplo de la apariencia de la advertencia de PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Temas relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md)