---
title: "Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Guía de inicio rápido para configurar Planes de llamada en Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: e38317132190b3035f37509d1fa7b2da5e4785c7
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2017
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
Para habilitar la ficha **Llamadas** en Microsoft Teams y permitir que los usuarios hagan y reciban llamadas RTC, deberá preparar a los usuarios para que puedan utilizar Sistema telefónico y Planes de llamada. Para aprender a realizar esta configuración, lea [Configurar Planes de llamada](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).

> [!IMPORTANT]
> Antes de configurar Planes de llamada en Microsoft Teams, tenga en cuenta las siguientes limitaciones:
> * **Voz híbrida no es compatible con Microsoft Teams**: actualmente no se admite Voz híbrida en Microsoft Teams. Los clientes de Voz híbrida no reciben notificación alguna para cambiar las directivas para recibir llamadas en Microsoft Teams, dado que esto provocaría interrupciones en el servicio.
> * **Las llamadas federadas no son compatibles con Microsoft Teams**: actualmente no se admiten las llamadas federadas (llamadas entre inquilinos/compañías) en Microsoft Teams. Hasta que esta característica sea compatible con Microsoft Teams, las llamadas federadas se dirigirán siempre a Skype Empresarial sin importar su configuración de llamadas.

## <a name="teams-interop-policy-configuration"></a>Configuración de la directiva de interoperabilidad de Microsoft Teams
Para que Microsoft Teams pueda empezar a recibir llamadas, tendrá que actualizar la directiva de interoperabilidad de Microsoft Teams utilizando una sesión de Windows PowerShell remota con los cmdlets [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) de Skype Empresarial para redirigir las llamadas a esta plataforma. Para obtener más información sobre la directiva de interoperabilidad de Microsoft Teams, consulte [Interoperabilidad entre Microsoft Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).

> [!TIP]
> Para buscar los cmdlets de PowerShell que necesita, escriba "CsTeamsInteropPolicy" en el cuadro **Filtrar** en la [documentación sobre los cmdlets de PowerShell para Skype Empresarial](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-interop-policy"></a>Directiva de interoperabilidad predeterminada de Microsoft Teams
Microsoft Teams tiene una configuración de directiva predeterminada diseñada para garantizar que no se interrumpan los flujos de trabajo empresariales existentes durante el proceso de implementación de Microsoft Teams. De forma predeterminada, VoIP, RTC y las llamadas federadas a los usuarios se seguirán dirigiendo a Skype Empresarial hasta que actualice la directiva para permitir las llamadas entrantes en Microsoft Teams. De este modo se garantiza que no se producirán interrupciones no deseadas en los servicios de voz cuando inicie el proyecto piloto de Microsoft Teams o comience la implementación.

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

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a>Cómo configurar Microsoft Teams para usar la directiva predeterminada
De forma predeterminada, la directiva de interoperabilidad global de Microsoft Teams se aplica a todos los usuarios del inquilino y está configurada con los ajustes predeterminados descritos anteriormente. Si por algún motivo ha establecido directivas diferentes para sus usuarios y desea revertir los ajustes a la configuración predeterminada, tendrá que aplicar la directiva de interoperabilidad global de Microsoft Teams a través de una sesión de Windows PowerShell remota para Skype Empresarial:

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> Aunque es posible modificar los valores predeterminados de la directiva de interoperabilidad global de Microsoft Teams, recomendamos encarecidamente no hacerlo. 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Configurar Microsoft Teams para recibir llamadas RTC entrantes
Para recibir llamadas RTC entrantes en Microsoft Teams, deberá configurar Microsoft Teams como la aplicación de llamadas predeterminada aplicando la directiva de interoperabilidad de Microsoft Teams con el parámetro `CallingDefaultClient` establecido en Teams.

> [!IMPORTANT]
> Recomendamos aplicar esta configuración a un conjunto inicial de usuarios para explorar las excitantes nuevas funcionalidades de llamada que ofrece Microsoft Teams antes de realizar cambios en un grupo más grande o en toda la organización.

Puede utilizar la siguiente directiva de interoperabilidad preconfigurada de Microsoft Teams para dirigir las llamadas RTC entrantes a Microsoft Teams:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Los comportamientos de la directiva anterior son los siguientes:
* **Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para redirigir las llamadas entrantes a Microsoft Teams. Esto afecta tanto a las llamadas VoIP (desde Microsoft Teams y Skype Empresarial) como a las RTC. Las llamadas federadas se seguirán recibiendo en Skype Empresarial. 
* **Para los clientes sin Skype Empresarial**, al aplicar esta directiva, las llamadas RTC se recibirán en Microsoft Teams. Actualmente las llamadas federadas **no se admiten** en Microsoft Teams.

> [!WARNING]
> Actualmente, cambiar `CallingDefaultClient` a Teams afectará también a las llamadas a teléfonos IP de Skype Empresarial. Las llamadas entrantes no se recibirán en los teléfonos y solo sonarán en los clientes de Microsoft Teams. Consulte [De Skype Empresarial a Microsoft Teams: mapa de ruta de las opciones](https://aka.ms/skype2teamsroadmap) para obtener información sobre compatibilidad con teléfonos SIP existentes.

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a>Cómo configurar Microsoft Teams para recibir llamadas RTC
Aplique la directiva de interoperabilidad de Microsoft Teams del modo descrito con anterioridad a través de una sesión de Windows PowerShell remota para Skype Empresarial para redirigir las llamadas a Microsoft Teams:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a>Configurar Microsoft Teams para permitir que los usuarios cambien su experiencia de llamada preferida
Para permitir que los usuarios tomen sus propias decisiones en cuanto a la experiencia de llamada preferida (recibir llamadas en Microsoft Teams o Skype Empresarial) debe crear una directiva de interoperabilidad de Microsoft Teams personalizada que habilite el parámetro `AllowEndUserClientOverride`.

A continuación se muestra un ejemplo de la directiva de interoperabilidad de Microsoft Teams para permitir que los usuarios elijan la experiencia de llamada preferida:

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Una vez que se aplica esta directiva personalizada a los usuarios, la opción de cambiar la aplicación de llamada preferida estará disponible en el cliente de Microsoft Teams para que los usuarios realicen los cambios ellos mismos.

![Opción de aplicación de llamadas preferida](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> Recomendamos aplicar esta configuración a un conjunto inicial de usuarios antes de realizar cambios en un grupo más grande o en toda la organización.

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a>Cómo crear y aplicar la directiva de interoperabilidad personalizada de Microsoft Teams
Para crear la directiva de interoperabilidad personalizada de Microsoft Teams del modo descrito con anterioridad a través de una sesión de Windows PowerShell remota para Skype Empresarial, realice lo siguiente:

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a>Vea también
[Configurar Planes de llamada](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[Interoperabilidad entre Microsoft Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[Guía práctica para Sistema telefónico con planes de llamada en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Referencia de cmdlets de PowerShell para Skype Empresarial](https://docs.microsoft.com/powershell/module/skype)

[Referencia de cmdlets de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams)
