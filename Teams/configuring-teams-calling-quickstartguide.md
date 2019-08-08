---
title: 'Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Guía de inicio rápido para configurar Planes de llamada en Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e043633749e0ef2dba41b5b3b18776cfbe1c497
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236576"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams
==============================================================

Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar Planes de llamada en Microsoft Teams.

Lea el anuncio del 12 de diciembre de 2017 sobre Planes de llamada en Microsoft Teams: [El avance de la comunicación inteligente con las llamadas en Microsoft Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Le recomendamos que, en paralelo con esta guía de inicio rápido, lea el [sistema telefónico con los planes de llamadas](calling-plan-landing-page.md) y [FastTrack](https://aka.ms/cloudvoice) para planear y dirigir una correcta implantación.

Ahora, al agregar Planes de llamada (una función de Office 365 con tecnología de Skype Empresarial), puede usar Microsoft Teams para hacer y recibir llamadas telefónicas a números nacionales y móviles o desde ellos a través de la red telefónica conmutada (RTC).

![Captura de pantalla que muestra la página contactos en Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Requisitos previos para habilitar la ficha **Llamadas** en Microsoft Teams.
Para habilitar la pestaña **llamadas** en Teams, los usuarios deben tener habilitadas las llamadas de 1:1 en Teams y usar un cliente de teams que admita las llamadas de 1:1 equipos. Para obtener información sobre cómo administrar las llamadas de 1:1 en Teams, lea [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Para saber qué clientes son compatibles con las llamadas, lea [límites y especificaciones de Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> En la actualidad, el buzón de voz no estará disponible en la ficha llamadas, a menos que el usuario tenga habilitada la opción de llamadas RTC. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Requisitos previos para habilitar el **teclado de marcado** en Teams
Para habilitar la pestaña **teclado de marcado** en Teams y permitir que los usuarios realicen y reciban llamadas RTC, necesitará aprovisionar usuarios para los planes de llamadas y del sistema telefónico. Para obtener información sobre cómo configurar planes de llamadas, consulte [configurar planes de llamadas](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).

> [!NOTE]
> También puede usar el enrutamiento directo para permitir que los usuarios realicen y reciban llamadas RTC. Para obtener información sobre cómo configurar el enrutamiento directo, lea [configurar el enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Uso de TeamsUpgradePolicy para controlar dónde se encuentran las llamadas
Para controlar si las llamadas (y chats) entrantes en Teams o Skype empresarial, los administradores usan TeamsUpgradePolicy, ya sea con el [centro de administración de Microsoft Teams](https://aka.ms/teamsadmincenter) o mediante una sesión remota de Windows PowerShell con [Skype empresarial](https://docs.microsoft.com/powershell/module/skype) . cmdlets.


La configuración predeterminada de TeamsUpgradePolicy es el modo islas, que está diseñado para garantizar que los flujos de trabajo empresariales existentes no se interrumpan durante una implementación de Teams. De forma predeterminada, las llamadas VoIP, RTC y federadas a los usuarios se seguirán redirigiendo a Skype empresarial hasta que actualice la Directiva para habilitar las llamadas entrantes a teams.  Cuando los destinatarios se encuentran en el modo islas:

 - Las llamadas de VOIP entrantes originadas en Skype empresarial siempre se encuentran en el cliente de Skype empresarial del destinatario.
 - Llamadas VOIP entrantes originadas en Teams en los equipos, *si el remitente y el receptor están en el mismo inquilino*.
 - La telefonía VOIP federada entrante (con independencia de qué cliente se origina) y las llamadas de RTC siempre se encuentran en el cliente de Skype empresarial del destinatario.
 
Para garantizar que las llamadas RTC y VOIP entrantes siempre se encuentran en el cliente de equipos de un usuario, actualice el modo de coexistencia del usuario para que sea TeamsOnly (lo que significa, asígneles la instancia "UpgradeToTeams" de TeamsUpgradePolicy.  Para obtener más información sobre los modos de coexistencia y TeamsUpgradePolicy, consulte [Guía de migración e interoperabilidad para las organizaciones que usan Teams conjuntamente con Skype empresarial](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**Lotus**
 - Los teléfonos IP de Skype empresarial recibirán llamadas, incluso si el usuario está en modo TeamsOnly.  
 - Los usuarios que se han suministrado con el sistema telefónico y las licencias de planes de llamadas para su uso con Skype empresarial online (por ejemplo, se les ha asignado un valor de OnlineVoiceRoutingPolicy), tienen la ficha llamadas habilitada en Teams y pueden realizar llamadas RTC salientes desde Teams sin administradores tengan que realizar ninguna acción administrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Cómo configurar los usuarios para que reciban todas las llamadas de VOIP y RTC entrantes en Teams
Para asegurarse de que los usuarios reciban todas las llamadas de VOIP y RTC entrantes en Teams, establezca el modo de coexistencia del usuario en TeamsOnly en el centro de administración de Microsoft Teams o use la sesión de Windows PowerShell remota de Skype empresarial para actualizar TeamsUpgradePolicy de la siguiente manera:

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>Vea también
[Configurar planes de llamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Sistema telefónico con planes de llamadas](calling-plan-landing-page.md)

[Referencia del cmdlet de PowerShell de Skype empresarial](https://docs.microsoft.com/powershell/module/skype)

