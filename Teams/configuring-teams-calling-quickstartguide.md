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
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: eea3c6ed4084648877fd31b84bb9cdea26986565
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856102"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="9deac-103">Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9deac-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="9deac-104">Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar Planes de llamada en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9deac-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="9deac-105">Lea el anuncio del 12 de diciembre de 2017 sobre Planes de llamada en Microsoft Teams: [El avance de la comunicación inteligente con las llamadas en Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="9deac-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="9deac-106">Recomendamos usar en paralelo a esta guía de inicio rápido nuestra [guía práctica](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) y la herramienta [FastTrack](https://aka.ms/cloudvoice) para planificar y lograr un lanzamiento correcto.</span><span class="sxs-lookup"><span data-stu-id="9deac-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="9deac-107">Ahora, al agregar Planes de llamada (una función de Office 365 con tecnología de Skype Empresarial), puede usar Microsoft Teams para hacer y recibir llamadas telefónicas a números nacionales y móviles o desde ellos a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="9deac-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Llamar en Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="9deac-109">Requisitos previos para habilitar la ficha **Llamadas** en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9deac-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="9deac-110">Para habilitar la ficha **Llamadas** en Microsoft Teams y permitir que los usuarios hagan y reciban llamadas RTC, deberá preparar a los usuarios para que puedan utilizar Sistema telefónico y Planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="9deac-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="9deac-111">Para aprender a realizar esta configuración, lea [Configurar Planes de llamada](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="9deac-111">To learn how to set this up, read [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="9deac-112">Configuración de la directiva de interoperabilidad de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9deac-112">Teams interop policy configuration</span></span>
<span data-ttu-id="9deac-113">Para habilitar los equipos para empezar a recibir llamadas, que necesitará para actualizar la directiva de actualización de los equipos y la directiva de interoperabilidad de los equipos, uso de [los equipos de Microsoft & Skype para el centro de administración de negocio](https://aka.ms/teamsadmincenter) o mediante una sesión remota de Windows PowerShell con el Skype para la empresa [ `*-CsTeamsUpgradePolicy`y `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) cmdlets, para redirigir las llamadas a los equipos.</span><span class="sxs-lookup"><span data-stu-id="9deac-113">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="9deac-114">Para obtener más información acerca de la directiva de actualización de los equipos y la directiva de interoperabilidad de los equipos, vea [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="9deac-114">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="9deac-115">Para buscar los cmdlets de PowerShell que necesita, escriba "CsTeamsUpgradePolicy" o "CsTeamsInteropPolicy" en el cuadro **filtro** en el [Skype para obtener documentación sobre el cmdlet de PowerShell de negocio](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="9deac-115">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="9deac-116">Valor predeterminado de los equipos de las directivas de actualización y la interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="9deac-116">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="9deac-117">Microsoft Teams tiene una configuración de directiva predeterminada diseñada para garantizar que no se interrumpan los flujos de trabajo empresariales existentes durante el proceso de implementación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9deac-117">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="9deac-118">De forma predeterminada, VoIP, RTC y las llamadas federadas a los usuarios se seguirán dirigiendo a Skype Empresarial hasta que actualice la directiva para permitir las llamadas entrantes en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9deac-118">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="9deac-119">De este modo se garantiza que no se producirán interrupciones no deseadas en los servicios de voz cuando inicie el proyecto piloto de Microsoft Teams o comience la implementación.</span><span class="sxs-lookup"><span data-stu-id="9deac-119">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="9deac-120">Directiva de actualización de forma predeterminada se mantiene en modo heredado que respeta la directiva de interoperabilidad de los equipos para determinar dónde están los chats y las llamadas deben enrutarse--los equipos de los equipos o Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="9deac-120">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="9deac-121">Directiva de actualización de los comportamientos de los equipos y directiva de interoperabilidad de los equipos cambiarán pronto como se describe en la [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="9deac-121">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="9deac-122">La directiva de interoperabilidad de Microsoft Teams tiene la siguiente configuración predeterminada:</span><span class="sxs-lookup"><span data-stu-id="9deac-122">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="9deac-123">Los comportamientos de la configuración predeterminada son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9deac-123">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="9deac-124">**Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para garantizar que las llamadas de Skype Empresarial se dirijan a Skype Empresarial y las de Microsoft Teams a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9deac-124">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="9deac-125">RTC y las llamadas federadas se dirigirán a Skype Empresarial si se aplica esta directiva.</span><span class="sxs-lookup"><span data-stu-id="9deac-125">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="9deac-126">**Para los clientes sin Skype Empresarial**, si se aplica, además de llamadas entre usuarios de Microsoft Teams, solo se podrán realizar llamadas RTC salientes en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9deac-126">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="9deac-127">Tendrá que modificar la directiva de interoperabilidad de Microsoft Teams asignada a sus usuarios para que puedan recibir llamadas RTC en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9deac-127">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="9deac-128">Los usuarios aprovisionados con licencias de Sistema telefónico y Planes de llamada para el uso con Skype Empresarial Online que tengan configurada la directiva de interoperabilidad global predeterminada de Microsoft Teams tendrán habilitada la ficha Llamadas en Microsoft Teams y podrán realizar llamadas RTC salientes desde la aplicación sin que un administrador tenga que realizar ninguna acción específica.</span><span class="sxs-lookup"><span data-stu-id="9deac-128">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="9deac-129">Configurar Microsoft Teams para recibir llamadas RTC entrantes</span><span class="sxs-lookup"><span data-stu-id="9deac-129">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="9deac-130">Para recibir las llamadas RTC entrantes en los equipos, debe configurar los equipos como el valor predeterminado al llamar a la aplicación mediante la aplicación de directiva de actualización de los equipos con la directiva de interoperabilidad de los equipos correspondiente que establece `CallingDefaultClient` parámetro para los equipos.</span><span class="sxs-lookup"><span data-stu-id="9deac-130">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9deac-131">Recomendamos aplicar esta configuración a un conjunto inicial de usuarios para explorar las excitantes nuevas funcionalidades de llamada que ofrece Microsoft Teams antes de realizar cambios en un grupo más grande o en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="9deac-131">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="9deac-132">Si elige seguir usando la directiva heredada de actualización de los equipos, use la siguiente directiva preconfigurada de interoperabilidad de los equipos para enrutar las llamadas RTC entrantes a los equipos:</span><span class="sxs-lookup"><span data-stu-id="9deac-132">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="9deac-133">Si decide utilizar la directiva de actualización de los equipos actualizada, debe asignar el modo de TeamsOnly a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9deac-133">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="9deac-134">Los comportamientos de la directiva anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9deac-134">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="9deac-135">**Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para redirigir las llamadas entrantes a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9deac-135">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="9deac-136">Esto afecta tanto a las llamadas VoIP (desde Microsoft Teams y Skype Empresarial) como a las RTC.</span><span class="sxs-lookup"><span data-stu-id="9deac-136">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="9deac-137">**Para los clientes sin Skype Empresarial**, al aplicar esta directiva, las llamadas RTC se recibirán en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9deac-137">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="9deac-138">Actualmente, cambiar `CallingDefaultClient` a Teams afectará también a las llamadas a teléfonos IP de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="9deac-138">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="9deac-139">Las llamadas entrantes no se recibirán en los teléfonos y solo sonarán en los clientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9deac-139">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="9deac-140">Consulte [De Skype Empresarial a Microsoft Teams: mapa de ruta de las opciones](https://aka.ms/skype2teamsroadmap) para obtener información sobre compatibilidad con teléfonos SIP existentes.</span><span class="sxs-lookup"><span data-stu-id="9deac-140">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="9deac-141">Cómo configurar usuarios para recibir RTC llama en los equipos</span><span class="sxs-lookup"><span data-stu-id="9deac-141">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="9deac-142">Cuando se usa la directiva heredada de actualización de los equipos, aplicar la directiva de interoperabilidad de los equipos como se describió anteriormente a través de Skype para la sesión remota de Windows PowerShell de negocio para redirigir las llamadas a los equipos:</span><span class="sxs-lookup"><span data-stu-id="9deac-142">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="9deac-143">Si decide usar el modo de TeamsOnly, puede cambiar el modo de coexistencia del usuario a TeamsOnly a Microsoft Teams & Skype para el centro de administración de negocio, o a través de Skype para la sesión remota de Windows PowerShell de negocio para redirigir las llamadas a los equipos:</span><span class="sxs-lookup"><span data-stu-id="9deac-143">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="9deac-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="9deac-144">See also</span></span>
[<span data-ttu-id="9deac-145">Configurar Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="9deac-145">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="9deac-146">Guía de interoperabilidad y migración para las organizaciones que utilizan los equipos junto con Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="9deac-146">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="9deac-147">Guía práctica para Sistema telefónico con planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9deac-147">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="9deac-148">Referencia de cmdlets de PowerShell para Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="9deac-148">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="9deac-149">Referencia de cmdlets de PowerShell para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9deac-149">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
