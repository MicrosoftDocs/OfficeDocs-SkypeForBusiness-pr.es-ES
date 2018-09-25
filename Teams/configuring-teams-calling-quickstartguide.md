---
title: 'Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams'
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Guía de inicio rápido para configurar Planes de llamada en Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a1fb82f57035f238ce222bf7f21b72983d21075
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015936"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams
==============================================================

Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar Planes de llamada en Microsoft Teams.

Lea el anuncio del 12 de diciembre de 2017 sobre Planes de llamada en Microsoft Teams: [El avance de la comunicación inteligente con las llamadas en Microsoft Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Recomendamos usar en paralelo a esta guía de inicio rápido nuestra [guía práctica](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) y la herramienta [FastTrack](https://aka.ms/cloudvoice) para planificar y lograr un lanzamiento correcto.

Ahora, al agregar Planes de llamada (una función de Office 365 con tecnología de Skype Empresarial), puede usar Microsoft Teams para hacer y recibir llamadas telefónicas a números nacionales y móviles o desde ellos a través de la red telefónica conmutada (RTC).

![Llamar en Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Requisitos previos para habilitar la ficha **Llamadas** en Microsoft Teams.
Para habilitar la ficha **Llamadas** en Microsoft Teams y permitir que los usuarios hagan y reciban llamadas RTC, deberá preparar a los usuarios para que puedan utilizar Sistema telefónico y Planes de llamada. Para aprender a realizar esta configuración, lea [Configurar Planes de llamada](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).

## <a name="teams-interop-policy-configuration"></a>Configuración de la directiva de interoperabilidad de Teams
Para que Teams pueda comenzar a recibir llamadas, tendrá que actualizar la directiva de actualización y la de interoperabilidad de Teams, ya sea mediante el [Centro de administración de Microsoft Teams y Skype Empresarial](https://aka.ms/teamsadmincenter) o una sesión remota de Windows PowerShell con los cmdlets [`*-CsTeamsUpgradePolicy` y `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) de Skype Empresarial, con el fin de redirigir las llamadas a Teams.

Si necesita más información sobre la directiva de actualización y la directiva de interoperabilidad de Teams, consulte [Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

> [!TIP]
> Para buscar los cmdlets de PowerShell que necesita, escriba "CsTeamsUpgradePolicy" o "CsTeamsInteropPolicy" en el cuadro **Filtrar** en la [documentación sobre los cmdlets de PowerShell para Skype Empresarial](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-upgrade-and-interop-policies"></a>Directivas de actualización e interoperabilidad predeterminadas de Teams
Microsoft Teams tiene una configuración de directiva predeterminada diseñada para garantizar que no se interrumpan los flujos de trabajo empresariales existentes durante el proceso de implementación de Microsoft Teams. De forma predeterminada, VoIP, RTC y las llamadas federadas a los usuarios se seguirán dirigiendo a Skype Empresarial hasta que actualice la directiva para permitir las llamadas entrantes en Microsoft Teams. De este modo se garantiza que no se producirán interrupciones no deseadas en los servicios de voz cuando inicie el proyecto piloto de Microsoft Teams o comience la implementación.

La directiva de actualización de Teams se guarda de forma predeterminada en el modo heredado que permitirá que la directiva de interoperabilidad de Teams determine a dónde se enrutan los chats y llamadas: a Teams o Skype Empresarial.

> [!NOTE]
> Los comportamientos de la directiva de actualización y la directiva de interoperabilidad de Teams se modificarán muy pronto, tal y como se explica en [Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

La directiva de interoperabilidad de Teams tiene la siguiente configuración predeterminada:

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Los comportamientos de la configuración predeterminada son los siguientes:
* **Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para garantizar que las llamadas de Skype Empresarial se dirijan a Skype Empresarial y las de Microsoft Teams a Microsoft Teams. RTC y las llamadas federadas se dirigirán a Skype Empresarial si se aplica esta directiva.
* **Para los clientes sin Skype Empresarial**, si se aplica, además de llamadas entre usuarios de Microsoft Teams, solo se podrán realizar llamadas RTC salientes en Microsoft Teams. Tendrá que modificar la directiva de interoperabilidad de Microsoft Teams asignada a sus usuarios para que puedan recibir llamadas RTC en Microsoft Teams.

> [!NOTE]
> Los usuarios aprovisionados con licencias de Sistema telefónico y Planes de llamada para el uso con Skype Empresarial Online que tengan configurada la directiva de interoperabilidad global predeterminada de Microsoft Teams tendrán habilitada la ficha Llamadas en Microsoft Teams y podrán realizar llamadas RTC salientes desde la aplicación sin que un administrador tenga que realizar ninguna acción específica.

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Configurar Teams para recibir llamadas RTC entrantes
Para recibir llamadas RTC entrantes en Teams, deberá configurar Teams como la aplicación de llamadas predeterminada. Para ello, tiene que aplicar la directiva de actualización de Teams con la correspondiente directiva de interoperabilidad de Teams que establece el parámetro `CallingDefaultClient` en Teams.

> [!IMPORTANT]
> Recomendamos aplicar esta configuración a un conjunto inicial de usuarios para explorar las excitantes nuevas funcionalidades de llamada que ofrece Microsoft Teams antes de realizar cambios en un grupo más grande o en toda la organización.

Si decide seguir usando la directiva de actualización de Teams heredada, emplee la siguiente directiva de interoperabilidad de Teams preconfigurada para dirigir las llamadas RTC entrantes a Teams:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Si decide usar la directiva de actualización de Teams actualizada, tendrá que asignar el modo TeamsOnly a los usuarios.

Los comportamientos de la directiva anterior son los siguientes:
* **Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para redirigir las llamadas entrantes a Microsoft Teams. Esto afecta tanto a las llamadas VoIP (desde Microsoft Teams y Skype Empresarial) como a las RTC. 
* **Para los clientes sin Skype Empresarial**, al aplicar esta directiva, las llamadas RTC se recibirán en Teams.

> [!WARNING]
> Actualmente, cambiar `CallingDefaultClient` a Teams afectará también a las llamadas a teléfonos IP de Skype Empresarial. Las llamadas entrantes no se recibirán en los teléfonos y solo sonarán en los clientes de Microsoft Teams. Consulte [De Skype Empresarial a Microsoft Teams: mapa de ruta de las opciones](https://aka.ms/skype2teamsroadmap) para obtener información sobre compatibilidad con teléfonos SIP existentes.

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Cómo configurar usuarios para recibir llamadas RTC en Teams
Cuando utilice la directiva de actualización de Teams heredada, aplique la directiva de interoperabilidad de Teams del modo descrito con anterioridad a través de una sesión de Windows PowerShell remota para Skype Empresarial para redirigir las llamadas a Teams:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

Si decide utilizar el modo TeamsOnly, deberá cambiar el modo de coexistencia del usuario a TeamsOnly a través del Centro de administración de Microsoft Teams y Skype Empresarial o bien a través de una sesión remota de Windows PowerShell para Skype Empresarial para redirigir las llamadas a Teams:

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>Vea también
[Configurar Planes de llamada](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Guía práctica para Sistema telefónico con planes de llamada en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Referencia de cmdlets de PowerShell para Skype Empresarial](https://docs.microsoft.com/powershell/module/skype)

[Referencia de cmdlets de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams)
