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
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="3e313-103">Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e313-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="3e313-104">Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar Planes de llamada en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="3e313-105">Lea el anuncio del 12 de diciembre de 2017 sobre Planes de llamada en Microsoft Teams: [El avance de la comunicación inteligente con las llamadas en Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="3e313-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="3e313-106">Recomendamos usar en paralelo a esta guía de inicio rápido nuestra [guía práctica](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) y la herramienta [FastTrack](https://aka.ms/cloudvoice) para planificar y lograr un lanzamiento correcto.</span><span class="sxs-lookup"><span data-stu-id="3e313-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="3e313-107">Ahora, al agregar Planes de llamada (una función de Office 365 con tecnología de Skype Empresarial), puede usar Microsoft Teams para hacer y recibir llamadas telefónicas a números nacionales y móviles o desde ellos a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="3e313-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Llamar en Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="3e313-109">Requisitos previos para habilitar la ficha **Llamadas** en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="3e313-110">Para habilitar la ficha **Llamadas** en Microsoft Teams y permitir que los usuarios hagan y reciban llamadas RTC, deberá preparar a los usuarios para que puedan utilizar Sistema telefónico y Planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="3e313-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="3e313-111">Para aprender a realizar esta configuración, lea [Configurar Planes de llamada](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="3e313-111">To learn how to set this up, read [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="3e313-112">Configuración de la directiva de interoperabilidad de Teams</span><span class="sxs-lookup"><span data-stu-id="3e313-112">Teams interop policy configuration</span></span>
<span data-ttu-id="3e313-113">Para que Teams pueda comenzar a recibir llamadas, tendrá que actualizar la directiva de actualización y la de interoperabilidad de Teams, ya sea mediante el [Centro de administración de Microsoft Teams y Skype Empresarial](https://aka.ms/teamsadmincenter) o una sesión remota de Windows PowerShell con los cmdlets [`*-CsTeamsUpgradePolicy` y `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) de Skype Empresarial, con el fin de redirigir las llamadas a Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-113">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="3e313-114">Si necesita más información sobre la directiva de actualización y la directiva de interoperabilidad de Teams, consulte [Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="3e313-114">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="3e313-115">Para buscar los cmdlets de PowerShell que necesita, escriba "CsTeamsUpgradePolicy" o "CsTeamsInteropPolicy" en el cuadro **Filtrar** en la [documentación sobre los cmdlets de PowerShell para Skype Empresarial](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="3e313-115">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="3e313-116">Directivas de actualización e interoperabilidad predeterminadas de Teams</span><span class="sxs-lookup"><span data-stu-id="3e313-116">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="3e313-117">Microsoft Teams tiene una configuración de directiva predeterminada diseñada para garantizar que no se interrumpan los flujos de trabajo empresariales existentes durante el proceso de implementación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-117">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="3e313-118">De forma predeterminada, VoIP, RTC y las llamadas federadas a los usuarios se seguirán dirigiendo a Skype Empresarial hasta que actualice la directiva para permitir las llamadas entrantes en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-118">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="3e313-119">De este modo se garantiza que no se producirán interrupciones no deseadas en los servicios de voz cuando inicie el proyecto piloto de Microsoft Teams o comience la implementación.</span><span class="sxs-lookup"><span data-stu-id="3e313-119">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="3e313-120">La directiva de actualización de Teams se guarda de forma predeterminada en el modo heredado que permitirá que la directiva de interoperabilidad de Teams determine a dónde se enrutan los chats y llamadas: a Teams o Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="3e313-120">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="3e313-121">Los comportamientos de la directiva de actualización y la directiva de interoperabilidad de Teams se modificarán muy pronto, tal y como se explica en [Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="3e313-121">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="3e313-122">La directiva de interoperabilidad de Teams tiene la siguiente configuración predeterminada:</span><span class="sxs-lookup"><span data-stu-id="3e313-122">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="3e313-123">Los comportamientos de la configuración predeterminada son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3e313-123">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="3e313-124">**Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para garantizar que las llamadas de Skype Empresarial se dirijan a Skype Empresarial y las de Microsoft Teams a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-124">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="3e313-125">RTC y las llamadas federadas se dirigirán a Skype Empresarial si se aplica esta directiva.</span><span class="sxs-lookup"><span data-stu-id="3e313-125">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="3e313-126">**Para los clientes sin Skype Empresarial**, si se aplica, además de llamadas entre usuarios de Microsoft Teams, solo se podrán realizar llamadas RTC salientes en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-126">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="3e313-127">Tendrá que modificar la directiva de interoperabilidad de Microsoft Teams asignada a sus usuarios para que puedan recibir llamadas RTC en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-127">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="3e313-128">Los usuarios aprovisionados con licencias de Sistema telefónico y Planes de llamada para el uso con Skype Empresarial Online que tengan configurada la directiva de interoperabilidad global predeterminada de Microsoft Teams tendrán habilitada la ficha Llamadas en Microsoft Teams y podrán realizar llamadas RTC salientes desde la aplicación sin que un administrador tenga que realizar ninguna acción específica.</span><span class="sxs-lookup"><span data-stu-id="3e313-128">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="3e313-129">Configurar Teams para recibir llamadas RTC entrantes</span><span class="sxs-lookup"><span data-stu-id="3e313-129">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="3e313-130">Para recibir llamadas RTC entrantes en Teams, deberá configurar Teams como la aplicación de llamadas predeterminada. Para ello, tiene que aplicar la directiva de actualización de Teams con la correspondiente directiva de interoperabilidad de Teams que establece el parámetro `CallingDefaultClient` en Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-130">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e313-131">Recomendamos aplicar esta configuración a un conjunto inicial de usuarios para explorar las excitantes nuevas funcionalidades de llamada que ofrece Microsoft Teams antes de realizar cambios en un grupo más grande o en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="3e313-131">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="3e313-132">Si decide seguir usando la directiva de actualización de Teams heredada, emplee la siguiente directiva de interoperabilidad de Teams preconfigurada para dirigir las llamadas RTC entrantes a Teams:</span><span class="sxs-lookup"><span data-stu-id="3e313-132">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="3e313-133">Si decide usar la directiva de actualización de Teams actualizada, tendrá que asignar el modo TeamsOnly a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3e313-133">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="3e313-134">Los comportamientos de la directiva anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3e313-134">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="3e313-135">**Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para redirigir las llamadas entrantes a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-135">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="3e313-136">Esto afecta tanto a las llamadas VoIP (desde Microsoft Teams y Skype Empresarial) como a las RTC.</span><span class="sxs-lookup"><span data-stu-id="3e313-136">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="3e313-137">**Para los clientes sin Skype Empresarial**, al aplicar esta directiva, las llamadas RTC se recibirán en Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-137">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="3e313-138">Actualmente, cambiar `CallingDefaultClient` a Teams afectará también a las llamadas a teléfonos IP de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="3e313-138">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="3e313-139">Las llamadas entrantes no se recibirán en los teléfonos y solo sonarán en los clientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e313-139">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="3e313-140">Consulte [De Skype Empresarial a Microsoft Teams: mapa de ruta de las opciones](https://aka.ms/skype2teamsroadmap) para obtener información sobre compatibilidad con teléfonos SIP existentes.</span><span class="sxs-lookup"><span data-stu-id="3e313-140">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="3e313-141">Cómo configurar usuarios para recibir llamadas RTC en Teams</span><span class="sxs-lookup"><span data-stu-id="3e313-141">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="3e313-142">Cuando utilice la directiva de actualización de Teams heredada, aplique la directiva de interoperabilidad de Teams del modo descrito con anterioridad a través de una sesión de Windows PowerShell remota para Skype Empresarial para redirigir las llamadas a Teams:</span><span class="sxs-lookup"><span data-stu-id="3e313-142">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="3e313-143">Si decide utilizar el modo TeamsOnly, deberá cambiar el modo de coexistencia del usuario a TeamsOnly a través del Centro de administración de Microsoft Teams y Skype Empresarial o bien a través de una sesión remota de Windows PowerShell para Skype Empresarial para redirigir las llamadas a Teams:</span><span class="sxs-lookup"><span data-stu-id="3e313-143">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="3e313-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e313-144">See also</span></span>
[<span data-ttu-id="3e313-145">Configurar Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="3e313-145">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="3e313-146">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3e313-146">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="3e313-147">Guía práctica para Sistema telefónico con planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e313-147">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="3e313-148">Referencia de cmdlets de PowerShell para Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3e313-148">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="3e313-149">Referencia de cmdlets de PowerShell para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e313-149">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
