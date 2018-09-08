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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86a4862a547df6f50d0831616a42824d9f8c3287
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882101"
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

## <a name="teams-interop-policy-configuration"></a>Configuración de la directiva de interoperabilidad de Microsoft Teams
Para habilitar los equipos para empezar a recibir llamadas, que necesitará para actualizar la directiva de actualización de los equipos y la directiva de interoperabilidad de los equipos, uso de [los equipos de Microsoft & Skype para el centro de administración de negocio](https://aka.ms/teamsadmincenter) o mediante una sesión remota de Windows PowerShell con el Skype para la empresa [ `*-CsTeamsUpgradePolicy`y `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) cmdlets, para redirigir las llamadas a los equipos.

Para obtener más información acerca de la directiva de actualización de los equipos y la directiva de interoperabilidad de los equipos, vea [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

> [!TIP]
> Para buscar los cmdlets de PowerShell que necesita, escriba "CsTeamsUpgradePolicy" o "CsTeamsInteropPolicy" en el cuadro **filtro** en el [Skype para obtener documentación sobre el cmdlet de PowerShell de negocio](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-upgrade-and-interop-policies"></a>Valor predeterminado de los equipos de las directivas de actualización y la interoperabilidad
Microsoft Teams tiene una configuración de directiva predeterminada diseñada para garantizar que no se interrumpan los flujos de trabajo empresariales existentes durante el proceso de implementación de Microsoft Teams. De forma predeterminada, VoIP, RTC y las llamadas federadas a los usuarios se seguirán dirigiendo a Skype Empresarial hasta que actualice la directiva para permitir las llamadas entrantes en Microsoft Teams. De este modo se garantiza que no se producirán interrupciones no deseadas en los servicios de voz cuando inicie el proyecto piloto de Microsoft Teams o comience la implementación.

Directiva de actualización de forma predeterminada se mantiene en modo heredado que respeta la directiva de interoperabilidad de los equipos para determinar dónde están los chats y las llamadas deben enrutarse--los equipos de los equipos o Skype para la empresa.

> [!NOTE]
> Directiva de actualización de los comportamientos de los equipos y directiva de interoperabilidad de los equipos cambiarán pronto como se describe en la [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

La directiva de interoperabilidad de Microsoft Teams tiene la siguiente configuración predeterminada:

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Los comportamientos de la configuración predeterminada son los siguientes:
* **Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para garantizar que las llamadas de Skype Empresarial se dirijan a Skype Empresarial y las de Microsoft Teams a Microsoft Teams. RTC y las llamadas federadas se dirigirán a Skype Empresarial si se aplica esta directiva.
* **Para los clientes sin Skype Empresarial**, si se aplica, además de llamadas entre usuarios de Microsoft Teams, solo se podrán realizar llamadas RTC salientes en Microsoft Teams. Tendrá que modificar la directiva de interoperabilidad de Microsoft Teams asignada a sus usuarios para que puedan recibir llamadas RTC en Microsoft Teams.

> [!NOTE]
> Los usuarios aprovisionados con licencias de Sistema telefónico y Planes de llamada para el uso con Skype Empresarial Online que tengan configurada la directiva de interoperabilidad global predeterminada de Microsoft Teams tendrán habilitada la ficha Llamadas en Microsoft Teams y podrán realizar llamadas RTC salientes desde la aplicación sin que un administrador tenga que realizar ninguna acción específica.

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Configurar Microsoft Teams para recibir llamadas RTC entrantes
Para recibir las llamadas RTC entrantes en los equipos, debe configurar los equipos como el valor predeterminado al llamar a la aplicación mediante la aplicación de directiva de actualización de los equipos con la directiva de interoperabilidad de los equipos correspondiente que establece `CallingDefaultClient` parámetro para los equipos.

> [!IMPORTANT]
> Recomendamos aplicar esta configuración a un conjunto inicial de usuarios para explorar las excitantes nuevas funcionalidades de llamada que ofrece Microsoft Teams antes de realizar cambios en un grupo más grande o en toda la organización.

Si elige seguir usando la directiva heredada de actualización de los equipos, use la siguiente directiva preconfigurada de interoperabilidad de los equipos para enrutar las llamadas RTC entrantes a los equipos:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Si decide utilizar la directiva de actualización de los equipos actualizada, debe asignar el modo de TeamsOnly a los usuarios.

Los comportamientos de la directiva anterior son los siguientes:
* **Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para redirigir las llamadas entrantes a Microsoft Teams. Esto afecta tanto a las llamadas VoIP (desde Microsoft Teams y Skype Empresarial) como a las RTC. 
* **Para los clientes sin Skype Empresarial**, al aplicar esta directiva, las llamadas RTC se recibirán en Microsoft Teams.

> [!WARNING]
> Actualmente, cambiar `CallingDefaultClient` a Teams afectará también a las llamadas a teléfonos IP de Skype Empresarial. Las llamadas entrantes no se recibirán en los teléfonos y solo sonarán en los clientes de Microsoft Teams. Consulte [De Skype Empresarial a Microsoft Teams: mapa de ruta de las opciones](https://aka.ms/skype2teamsroadmap) para obtener información sobre compatibilidad con teléfonos SIP existentes.

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Cómo configurar usuarios para recibir RTC llama en los equipos
Cuando se usa la directiva heredada de actualización de los equipos, aplicar la directiva de interoperabilidad de los equipos como se describió anteriormente a través de Skype para la sesión remota de Windows PowerShell de negocio para redirigir las llamadas a los equipos:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

Si decide usar el modo de TeamsOnly, puede cambiar el modo de coexistencia del usuario a TeamsOnly a Microsoft Teams & Skype para el centro de administración de negocio, o a través de Skype para la sesión remota de Windows PowerShell de negocio para redirigir las llamadas a los equipos:

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>Vea también
[Configurar Planes de llamada](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guía de interoperabilidad y migración para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Guía práctica para Sistema telefónico con planes de llamada en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Referencia de cmdlets de PowerShell para Skype Empresarial](https://docs.microsoft.com/powershell/module/skype)

[Referencia de cmdlets de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams)
