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
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1d2fd7a9b999d98109e732b3bdbbba16f26e3bf
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460575"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="27cc9-103">Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="27cc9-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="27cc9-104">Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar Planes de llamada en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27cc9-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="27cc9-105">Lea el anuncio del 12 de diciembre de 2017 sobre Planes de llamada en Microsoft Teams: [El avance de la comunicación inteligente con las llamadas en Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="27cc9-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="27cc9-106">Se recomienda que, en paralelo con esta guía de inicio rápido, lea [Sistema telefónico con planes de llamada](calling-plan-landing-page.md) y [FastTrack](https://aka.ms/cloudvoice) para planear y unidad de una implementación correcta.</span><span class="sxs-lookup"><span data-stu-id="27cc9-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="27cc9-107">Ahora, al agregar Planes de llamada (una función de Office 365 con tecnología de Skype Empresarial), puede usar Microsoft Teams para hacer y recibir llamadas telefónicas a números nacionales y móviles o desde ellos a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="27cc9-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Llamar en Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="27cc9-109">Requisitos previos para habilitar la ficha **Llamadas** en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27cc9-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="27cc9-110">Para habilitar la ficha de **llamadas** en los equipos de los usuarios necesitan tener habilitada en los equipos de llamada y utilizando a un cliente de los equipos que admite una llamada a los equipos de 1:1 de 1:1.</span><span class="sxs-lookup"><span data-stu-id="27cc9-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="27cc9-111">Para obtener información sobre cómo administrar las llamadas a 1:1 en los equipos, lea [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="27cc9-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="27cc9-112">Para obtener información sobre los clientes que admiten las llamadas, lea [los límites y las especificaciones de los equipos de Microsoft](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="27cc9-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="27cc9-113">En la actualidad, correo de voz no estará disponible en la ficha llamadas a menos que el usuario está habilitado para las llamadas de RTC.</span><span class="sxs-lookup"><span data-stu-id="27cc9-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="27cc9-114">Requisitos previos para habilitar el **Teclado de marcado** en los equipos</span><span class="sxs-lookup"><span data-stu-id="27cc9-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="27cc9-115">Para habilitar la ficha de **Teclado de marcado** en los equipos y permitir que los usuarios a realizar y recibir llamadas de RTC debe abastecer a los usuarios para el sistema telefónico y planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="27cc9-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="27cc9-116">Para obtener información sobre cómo configurar planes de llamada, lea [Configurar planes de llamada](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="27cc9-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="27cc9-117">También puede usar el enrutamiento directo para permitir que a los usuarios obli y recibir llamadas de RTC.</span><span class="sxs-lookup"><span data-stu-id="27cc9-117">You can also use Direct Routing to allow your users to mand and receive PSTN calls.</span></span> <span data-ttu-id="27cc9-118">Para obtener información sobre cómo configurar el enrutamiento directo, leer la [Configuración de enrutamiento directo](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="27cc9-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="27cc9-119">Configuración de la directiva de interoperabilidad de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="27cc9-119">Teams interop policy configuration</span></span>
<span data-ttu-id="27cc9-120">Para habilitar los equipos para empezar a recibir llamadas, que necesitará para actualizar la directiva de actualización de los equipos y la directiva de interoperabilidad de los equipos mediante el [Centro de administración de equipos de Microsoft](https://aka.ms/teamsadmincenter) o mediante una sesión remota de Windows PowerShell con el Skype para la empresa [ `*-CsTeamsUpgradePolicy` y `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) cmdlets, para redirigir las llamadas a los equipos.</span><span class="sxs-lookup"><span data-stu-id="27cc9-120">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="27cc9-121">Para obtener más información acerca de la directiva de actualización de los equipos y la directiva de interoperabilidad de los equipos, vea [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="27cc9-121">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="27cc9-122">Para buscar los cmdlets de PowerShell que necesita, escriba "CsTeamsUpgradePolicy" o "CsTeamsInteropPolicy" en el cuadro **filtro** en el [Skype para obtener documentación sobre el cmdlet de PowerShell de negocio](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="27cc9-122">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="27cc9-123">Valor predeterminado de los equipos de las directivas de actualización y la interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="27cc9-123">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="27cc9-124">Microsoft Teams tiene una configuración de directiva predeterminada diseñada para garantizar que no se interrumpan los flujos de trabajo empresariales existentes durante el proceso de implementación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27cc9-124">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="27cc9-125">De forma predeterminada, VoIP, RTC y las llamadas federadas a los usuarios se seguirán dirigiendo a Skype Empresarial hasta que actualice la directiva para permitir las llamadas entrantes en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27cc9-125">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="27cc9-126">De este modo se garantiza que no se producirán interrupciones no deseadas en los servicios de voz cuando inicie el proyecto piloto de Microsoft Teams o comience la implementación.</span><span class="sxs-lookup"><span data-stu-id="27cc9-126">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="27cc9-127">Directiva de actualización de forma predeterminada se mantiene en modo heredado que respeta la directiva de interoperabilidad de los equipos para determinar dónde están los chats y las llamadas deben enrutarse--los equipos de los equipos o Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="27cc9-127">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="27cc9-128">Directiva de actualización de los comportamientos de los equipos y directiva de interoperabilidad de los equipos cambiarán pronto como se describe en la [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="27cc9-128">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="27cc9-129">La directiva de interoperabilidad de Microsoft Teams tiene la siguiente configuración predeterminada:</span><span class="sxs-lookup"><span data-stu-id="27cc9-129">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="27cc9-130">Los comportamientos de la configuración predeterminada son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="27cc9-130">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="27cc9-131">**Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para garantizar que las llamadas de Skype Empresarial se dirijan a Skype Empresarial y las de Microsoft Teams a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27cc9-131">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="27cc9-132">RTC y las llamadas federadas se dirigirán a Skype Empresarial si se aplica esta directiva.</span><span class="sxs-lookup"><span data-stu-id="27cc9-132">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="27cc9-133">**Para los clientes sin Skype Empresarial**, si se aplica, además de llamadas entre usuarios de Microsoft Teams, solo se podrán realizar llamadas RTC salientes en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27cc9-133">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="27cc9-134">Tendrá que modificar la directiva de interoperabilidad de Microsoft Teams asignada a sus usuarios para que puedan recibir llamadas RTC en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27cc9-134">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="27cc9-135">Los usuarios aprovisionados con licencias de Sistema telefónico y Planes de llamada para el uso con Skype Empresarial Online que tengan configurada la directiva de interoperabilidad global predeterminada de Microsoft Teams tendrán habilitada la ficha Llamadas en Microsoft Teams y podrán realizar llamadas RTC salientes desde la aplicación sin que un administrador tenga que realizar ninguna acción específica.</span><span class="sxs-lookup"><span data-stu-id="27cc9-135">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="27cc9-136">Configurar Microsoft Teams para recibir llamadas RTC entrantes</span><span class="sxs-lookup"><span data-stu-id="27cc9-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="27cc9-137">Para recibir las llamadas RTC entrantes en los equipos, debe configurar los equipos como el valor predeterminado al llamar a la aplicación mediante la aplicación de directiva de actualización de los equipos con la directiva de interoperabilidad de los equipos correspondiente que establece `CallingDefaultClient` parámetro para los equipos.</span><span class="sxs-lookup"><span data-stu-id="27cc9-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27cc9-138">Recomendamos aplicar esta configuración a un conjunto inicial de usuarios para explorar las excitantes nuevas funcionalidades de llamada que ofrece Microsoft Teams antes de realizar cambios en un grupo más grande o en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="27cc9-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="27cc9-139">Si elige seguir usando la directiva heredada de actualización de los equipos, use la siguiente directiva preconfigurada de interoperabilidad de los equipos para enrutar las llamadas RTC entrantes a los equipos:</span><span class="sxs-lookup"><span data-stu-id="27cc9-139">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="27cc9-140">Si decide utilizar la directiva de actualización de los equipos actualizada, debe asignar el modo de sólo los equipos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="27cc9-140">If you choose to use the updated Teams upgrade policy, you need to assign Teams Only mode to your users.</span></span>

<span data-ttu-id="27cc9-141">Los comportamientos de la directiva anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="27cc9-141">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="27cc9-142">**Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para redirigir las llamadas entrantes a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27cc9-142">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="27cc9-143">Esto afecta tanto a las llamadas VoIP (desde Microsoft Teams y Skype Empresarial) como a las RTC.</span><span class="sxs-lookup"><span data-stu-id="27cc9-143">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="27cc9-144">**Para los clientes sin Skype Empresarial**, al aplicar esta directiva, las llamadas RTC se recibirán en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27cc9-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="27cc9-145">Actualmente, cambiar `CallingDefaultClient` a Teams afectará también a las llamadas a teléfonos IP de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="27cc9-145">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="27cc9-146">Las llamadas entrantes no se recibirán en los teléfonos y solo sonarán en los clientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27cc9-146">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="27cc9-147">Consulte la [Guía básica de 365 de Microsoft](https://aka.ms/O365Roadmap) para obtener información acerca de la compatibilidad con los teléfonos SIP certificadas existentes.</span><span class="sxs-lookup"><span data-stu-id="27cc9-147">Please consult the [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="27cc9-148">Cómo configurar usuarios para recibir RTC llama en los equipos</span><span class="sxs-lookup"><span data-stu-id="27cc9-148">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="27cc9-149">Cuando se usa la directiva heredada de actualización de los equipos, aplicar la directiva de interoperabilidad de los equipos como se describió anteriormente a través de Skype para la sesión remota de Windows PowerShell de negocio para redirigir las llamadas a los equipos:</span><span class="sxs-lookup"><span data-stu-id="27cc9-149">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="27cc9-150">Si decide usar el modo de sólo los equipos, puede cambiar el modo de coexistencia del usuario a sólo los equipos a través del centro de acmin Teams Microsoft o a través de un Skype para la sesión remota de Windows PowerShell de negocio para redirigir las llamadas a los equipos:</span><span class="sxs-lookup"><span data-stu-id="27cc9-150">If you choose to use Teams Only mode, you can change the user's coexistence mode to Teams Only via the Microsoft Teams acmin center or via a Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="27cc9-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="27cc9-151">See also</span></span>
[<span data-ttu-id="27cc9-152">Configurar Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="27cc9-152">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="27cc9-153">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="27cc9-153">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="27cc9-154">Sistema telefónico con Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="27cc9-154">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="27cc9-155">Referencia de cmdlets de PowerShell para Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="27cc9-155">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="27cc9-156">Referencia de cmdlets de PowerShell para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="27cc9-156">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
