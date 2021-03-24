---
title: 'Guía de inicio rápido: Configurar planes de llamadas'
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guía de inicio rápido para configurar planes de llamadas en Microsoft Teams para que pueda poner en marcha un conjunto de usuarios.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101186"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams
==============================================================

Esta guía le ayudará a poner en marcha un conjunto de usuarios para que puedan explorar planes de llamadas en Teams.

Lea el anuncio del 12 de diciembre de 2017 sobre planes de llamadas en Teams: [Comunicaciones inteligentes da](https://aka.ms/ipyqus) el siguiente paso con las llamadas en Teams

> [!NOTE]
> Le recomendamos que, en paralelo con esta [](calling-plan-landing-page.md) guía de inicio rápido, lea Sistema telefónico con planes de llamadas y [FastTrack](https://aka.ms/cloudvoice) para planear e impulsar una implementación correcta.

Al agregar planes de llamadas (una característica de Microsoft 365 y Office 365 con tecnología de Skype Empresarial), ahora puede usar Teams para realizar y recibir llamadas telefónicas desde o hacia líneas terrestres y teléfonos móviles a través de la red telefónica conmutada (RTC) pública.

![Captura de pantalla que muestra la página Contactos en Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Requisitos previos para habilitar la **pestaña Llamadas** en Teams
Para habilitar la **pestaña** Llamadas en Teams, los usuarios deben tener habilitadas las llamadas 1:1 en Teams y usar un cliente de Teams compatible con las llamadas de Teams 1:1. Para obtener información sobre cómo administrar las llamadas 1:1 en Teams, lea [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Para saber qué clientes admiten llamadas, lea [Límites y especificaciones de Microsoft Teams.](./limits-specifications-teams.md)

> [!NOTE]
> Actualmente, el correo de voz no estará disponible en la pestaña Llamadas a menos que el usuario esté habilitado para las llamadas RTC. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Requisitos previos para habilitar el **teclado de marcado** en Teams
Para habilitar la pestaña **Teclado** de marcado en Teams y permitir que los usuarios realicen y reciban llamadas RTC, tendrá que aprovisionar a los usuarios para sistemas telefónicos y planes de llamadas. Para obtener información sobre cómo configurar planes de llamadas, lea [Configurar planes de llamadas.](./set-up-calling-plans.md)
Además, para los usuarios solo de Teams, debe asegurarse de que "Permitir llamadas privadas" está habilitado en la directiva de llamadas de Teams. Vea [Administrar Teams durante la transición al nuevo Centro de](./manage-teams-skypeforbusiness-admin-center.md) administración de Microsoft Teams para obtener más información.
> [!NOTE]
> También puede usar enrutamiento directo para permitir que los usuarios realicen y reciban llamadas RTC. Para obtener información sobre cómo configurar enrutamiento directo, lea [Configurar enrutamiento directo.](./direct-routing-configure.md)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Usar TeamsUpgradePolicy para controlar la tierra de las llamadas
Para controlar si las llamadas entrantes (y chats) se desplome en Teams o Skype Empresarial, los administradores usan TeamsUpgradePolicy, con el Centro de administración de [Microsoft Teams](https://aka.ms/teamsadmincenter) o con una sesión de Windows PowerShell remota con los cmdlets de [Skype](/powershell/module/skype) Empresarial.


La configuración predeterminada de TeamsUpgradePolicy es el modo Islas, que está diseñado para asegurarse de que los flujos de trabajo empresariales existentes no se interrumpen durante una implementación de Teams. De forma predeterminada, voIP, RTC y llamadas federadas a los usuarios seguirán enrutadas a Skype Empresarial hasta que actualice la directiva para habilitar las llamadas entrantes a Teams.  Cuando los destinatarios están en modo islas:

 - Las llamadas VOIP entrantes que se originaron en Skype Empresarial siempre se reciben en el cliente de Skype Empresarial del destinatario.
 - Las llamadas VOIP entrantes que se originaron en Teams se encuentran en Teams, si el remitente y el receptor *se encuentran en el mismo espacio empresarial.*
 - El VOIP federado entrante (independientemente del cliente que se origine) y las llamadas RTC siempre se reciben en el cliente de Skype Empresarial del destinatario.
 
Para asegurarse de que las llamadas VOIP y RTC entrantes siempre se aterricen en el cliente de Teams de un usuario, actualice el modo de coexistencia del usuario para que sea TeamsOnly (es decir, asígneles la instancia "UpgradeToTeams" de TeamsUpgradePolicy).  Para obtener más información sobre los modos de coexistencia y TeamsUpgradePolicy, vea Instrucciones de migración e interoperabilidad para organizaciones que usan Teams junto [con Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md)

**NOTAS**
 - Los teléfonos IP de Skype Empresarial recibirán llamadas, incluso si el usuario está en modo TeamsOnly.  
 - Los usuarios a los que se les ha aprovisionado licencias de sistemas telefónicos y planes de llamadas para su uso con Skype Empresarial Online (por ejemplo, se les ha asignado un valor de OnlineVoiceRoutingPolicy), tendrán la pestaña Llamadas habilitada en Teams y podrán realizar llamadas RTC salientes desde Teams sin que los administradores tengan que realizar ninguna acción administrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Cómo configurar a los usuarios para que reciban todas las llamadas VOIP y RTC entrantes en Teams
Para asegurarse de que los usuarios reciben todas las llamadas VOIP y RTC entrantes en Teams, establezca el modo de coexistencia del usuario en TeamsOnly en el Centro de administración de Microsoft Teams o use la sesión remota de Windows PowerShell de Skype Empresarial para actualizar TeamsUpgradePolicy de la siguiente manera:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Vea también
[Configurar planes de llamadas](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md)

[PBX en la nube con Planes de llamada](calling-plan-landing-page.md)

[Referencia de cmdlet de PowerShell de Skype Empresarial](/powershell/module/skype)