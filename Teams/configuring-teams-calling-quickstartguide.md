---
title: 'Guía de inicio rápido: Configuración de planes de llamadas'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guía de inicio rápido para configurar planes de llamadas en Microsoft Teams para que pueda configurar y ejecutar un conjunto de usuarios.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ff6c85e337e2a3fe226347fc0b0ef68710d3d18
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789585"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams

Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar planes de llamadas en Teams.

Lea el anuncio del 12 de diciembre de 2017 de Planes de llamadas en Teams: [Las comunicaciones inteligentes da el siguiente paso con las llamadas en Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Le recomendamos que, en paralelo con esta guía de inicio rápido, lea [Sistema telefónico con planes de llamadas](calling-plan-landing-page.md) y [FastTrack](https://aka.ms/cloudvoice) para planear e impulsar una implementación correcta.

Al agregar planes de llamadas (una característica de Microsoft 365 y Office 365 con tecnología de Skype Empresarial), ahora puede usar Teams para realizar y recibir llamadas telefónicas a líneas terrestres y teléfonos móviles a través de la red telefónica conmutada (RTC) pública.

![Captura de pantalla que muestra la página Contactos en Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Requisitos previos para habilitar la pestaña **Llamadas** en Teams
Para habilitar la pestaña **Llamadas** en Teams, los usuarios deben tener habilitadas las llamadas individuales en Teams y usar un cliente de Teams compatible con las llamadas de teams individuales. Para obtener información sobre cómo administrar las llamadas individuales en Teams, lea [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy). Para obtener información sobre los clientes que admiten [llamadas, lea Límites y especificaciones de Microsoft Teams](./limits-specifications-teams.md).

> [!NOTE]
> Actualmente, el correo de voz no estará disponible en la pestaña Llamadas a menos que el usuario esté habilitado para llamadas RTC. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Requisitos previos para habilitar el **teclado de marcado** en Teams
Para habilitar la pestaña **Teclado de marcado** en Teams y permitir que los usuarios realicen y reciban llamadas RTC, necesitará aprovisionar a los usuarios para el sistema telefónico y los planes de llamadas. Para obtener información sobre cómo configurar planes de llamadas, lea [Configurar planes de llamadas](./set-up-calling-plans.md).
Además, solo para los usuarios de Teams, debe asegurarse de que la opción "Permitir llamadas privadas" está habilitada en la directiva de llamadas de Teams. Consulte [Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md) para obtener más información.
> [!NOTE]
> También puede usar el enrutamiento directo para permitir que los usuarios realicen y reciban llamadas RTC. Para obtener información sobre cómo configurar el enrutamiento directo, lea [Configurar enrutamiento directo](./direct-routing-configure.md).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Uso de TeamsUpgradePolicy para controlar dónde se posicionan las llamadas
Para controlar si las llamadas entrantes (y chats) llegan a Teams o Skype Empresarial, los administradores usan TeamsUpgradePolicy, ya sea mediante el [Centro de administración de Microsoft Teams](https://aka.ms/teamsadmincenter) o mediante una sesión Windows PowerShell remota con los cmdlets [de Skype Empresarial](/powershell/module/skype).


La configuración predeterminada de TeamsUpgradePolicy es el modo Islas, que está diseñado para garantizar que los flujos de trabajo existentes no se interrumpan durante una implementación de Teams. De forma predeterminada, las llamadas voIP, RTC y federadas a los usuarios se seguirán enrutando a Skype Empresarial hasta que actualice la directiva para habilitar las llamadas entrantes a Teams.  Cuando los destinatarios están en modo islas:

 - Las llamadas VOIP entrantes que se originan en Skype Empresarial siempre llegan al cliente Skype Empresarial del destinatario.
 - Las llamadas VOIP entrantes que se originan en Teams se realizan en Teams *, si el remitente y el receptor están en el mismo espacio empresarial*.
 - El VOIP federado entrante (independientemente del cliente que se origine) y las llamadas RTC siempre llegan al cliente de Skype Empresarial del destinatario.
 
Para asegurarse de que las llamadas VOIP y RTC entrantes siempre lleguen al cliente de Teams de un usuario, actualice el modo de coexistencia del usuario para que sea TeamsOnly (lo que significa asignarles la instancia de "UpgradeToTeams" de TeamsUpgradePolicy.  Para obtener más información sobre los modos de coexistencia y TeamsUpgradePolicy, consulte [Guía de migración e interoperabilidad para organizaciones que usan Teams junto con Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md)

**NOTAS**
 - Skype Empresarial teléfonos IP recibirán llamadas, incluso si el usuario está en modo TeamsOnly.  
 - Los usuarios aprovisionados con licencias de Sistema telefónico y Planes de llamadas para su uso con Skype Empresarial Online (por ejemplo, se les ha asignado un valor de OnlineVoiceRoutingPolicy), tendrán la pestaña Llamadas habilitada en Teams y podrán realizar llamadas RTC salientes de Teams sin que los administradores tengan que realizar ninguna acción administrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Cómo configurar los usuarios para que reciban todas las llamadas VOIP y RTC entrantes en Teams
Para asegurarse de que los usuarios reciben todas las llamadas VOIP y RTC entrantes en Teams, establezca el modo de coexistencia del usuario en TeamsOnly en el Centro de administración de Microsoft Teams o use Skype Empresarial sesión de Windows PowerShell remota para actualizar TeamsUpgradePolicy como se indica a continuación:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Vea también
[Configurar planes de llamadas](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md)

[PBX en la nube con Planes de llamada](calling-plan-landing-page.md)

[Skype Empresarial referencia de cmdlet de PowerShell](/powershell/module/skype)
