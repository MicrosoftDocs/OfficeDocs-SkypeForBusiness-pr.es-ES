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
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799770"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams
==============================================================

Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar Planes de llamada en Microsoft Teams.

Lea el anuncio del 12 de diciembre de 2017 sobre Planes de llamada en Microsoft Teams: [El avance de la comunicación inteligente con las llamadas en Microsoft Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Le recomendamos que, en paralelo con esta [](calling-plan-landing-page.md) guía de inicio rápido, lea Sistema telefónico con planes de llamadas y [FastTrack](https://aka.ms/cloudvoice) para planear e impulsar una implementación correctamente.

Al agregar planes de llamadas, una característica de Microsoft 365 y Office 365 con tecnología de Skype Empresarial, ahora puede usar Teams para realizar y recibir llamadas telefónicas a líneas fijas y teléfonos móviles a través de la red telefónica conmutada pública (RTC).

![Captura de pantalla que muestra la página Contactos en Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Requisitos previos para habilitar la ficha **Llamadas** en Microsoft Teams.
Para habilitar la **pestaña** Llamadas en Teams, los usuarios deben tener habilitada la llamada 1:1 en Teams y usar un cliente de Teams que admita las llamadas de Teams 1:1. Para obtener información sobre cómo administrar las llamadas 1:1 en Teams, lea [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Para saber qué clientes admiten llamadas, lea límites y especificaciones [para Microsoft Teams.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)

> [!NOTE]
> Actualmente, el correo de voz no estará disponible en la pestaña Llamadas a menos que el usuario esté habilitado para las llamadas RTC. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Requisitos previos para habilitar el **teclado de marcado** en Teams
Para habilitar la **pestaña** Teclado de marcado en Teams y permitir que los usuarios realicen y reciban llamadas RTC, deberá aprovisionar los usuarios para planes de llamadas y sistema telefónico. Para obtener información sobre cómo configurar planes de llamadas, lea [Configurar planes de llamadas.](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)
Además, para los usuarios solo de Teams, debe asegurarse de que la opción "Permitir llamadas privadas" está habilitada en la directiva de llamadas de Teams. Vea [Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) para obtener más información.
> [!NOTE]
> También puede usar el enrutamiento directo para permitir que los usuarios realicen y reciban llamadas RTC. Para obtener información sobre cómo configurar el enrutamiento directo, lea [Configurar enrutamiento directo.](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Usar TeamsUpgradePolicy para controlar la tierra de las llamadas
Para controlar si las llamadas entrantes (y los chats) se descargan en Teams o en Skype Empresarial, los administradores usan TeamsUpgradePolicy, ya sea mediante el centro de administración de [Microsoft Teams](https://aka.ms/teamsadmincenter) o mediante una sesión remota de Windows PowerShell con los cmdlets de [Skype](https://docs.microsoft.com/powershell/module/skype) Empresarial.


La configuración predeterminada de TeamsUpgradePolicy es el modo Islas, que está diseñada para garantizar que los flujos de trabajo empresariales existentes no se interrumpen durante una implementación de Teams. De forma predeterminada, las llamadas VoIP, RTC y federadas a los usuarios seguirán enrutadas a Skype Empresarial hasta que actualice la directiva para habilitar las llamadas entrantes a Teams.  Cuando los destinatarios están en el modo de islas:

 - Las llamadas VOIP entrantes que se originaron en Skype Empresarial siempre se reciben en el cliente de Skype Empresarial del destinatario.
 - Las llamadas VOIP entrantes que se originaron en Teams se fijon en Teams, si el remitente y el receptor *se encuentran en el mismo espacio empresarial.*
 - Las llamadas RTC y VOIP federadas entrantes (independientemente del cliente que se originen) y las llamadas RTC siempre se reciben en el cliente de Skype Empresarial del destinatario.
 
Para asegurarse de que las llamadas entrantes VOIP y RTC siempre se llegaron al cliente de Teams de un usuario, actualice el modo de coexistencia del usuario a TeamsOnly (es decir, asígneles la instancia "UpgradeToTeams" de TeamsUpgradePolicy).  Para obtener más información sobre los modos de coexistencia y TeamsUpgradePolicy, consulte la guía de migración e interoperabilidad para las organizaciones que usan [Teams junto con Skype Empresarial.](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**NOTAS**
 - Los teléfonos IP de Skype Empresarial recibirán llamadas, incluso si el usuario se encuentra en modo TeamsOnly.  
 - Los usuarios a los que se les ha aprovisionado licencias de Sistema telefónico y Planes de llamadas para su uso con Skype Empresarial Online (por ejemplo, se les ha asignado el valor OnlineVoiceRoutingPolicy), tendrán la pestaña Llamadas habilitada en Teams y pueden realizar llamadas RTC salientes desde Teams sin que los administradores tengan que realizar ninguna acción administrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Cómo configurar los usuarios para que reciban todas las llamadas ENTRANTES VOIP y RTC en Teams
Para asegurarse de que los usuarios reciben todas las llamadas ENTRANTES VOIP y RTC en Teams, establezca el modo de coexistencia del usuario en TeamsOnly en el Centro de administración de Microsoft Teams o use la sesión Windows PowerShell remota de Skype Empresarial para actualizar TeamsUpgradePolicy de la siguiente manera:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Consulte también
[Configurar planes de llamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[PBX en la nube con Planes de llamada](calling-plan-landing-page.md)

[Referencia de cmdlet de PowerShell de Skype Empresarial](https://docs.microsoft.com/powershell/module/skype)

