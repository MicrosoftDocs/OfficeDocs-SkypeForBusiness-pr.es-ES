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
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="67eb3-103">Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67eb3-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="67eb3-104">Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar Planes de llamada en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="67eb3-105">Lea el anuncio del 12 de diciembre de 2017 sobre Planes de llamada en Microsoft Teams: [El avance de la comunicación inteligente con las llamadas en Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="67eb3-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="67eb3-106">Recomendamos usar en paralelo a esta guía de inicio rápido nuestra [guía práctica](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) y la herramienta [FastTrack](https://aka.ms/cloudvoice) para planificar y lograr un lanzamiento correcto.</span><span class="sxs-lookup"><span data-stu-id="67eb3-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="67eb3-107">Ahora, al agregar Planes de llamada (una función de Office 365 con tecnología de Skype Empresarial), puede usar Microsoft Teams para hacer y recibir llamadas telefónicas a números nacionales y móviles o desde ellos a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="67eb3-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Llamar en Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="67eb3-109">Requisitos previos para habilitar la ficha **Llamadas** en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="67eb3-110">Para habilitar la ficha **Llamadas** en Microsoft Teams y permitir que los usuarios hagan y reciban llamadas RTC, deberá preparar a los usuarios para que puedan utilizar Sistema telefónico y Planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="67eb3-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="67eb3-111">Para aprender a realizar esta configuración, lea [Configurar Planes de llamada](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span><span class="sxs-lookup"><span data-stu-id="67eb3-111">To learn how to set this up, read [Set up Calling Plans](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67eb3-112">Antes de configurar Planes de llamada en Microsoft Teams, tenga en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="67eb3-112">Before configuring Calling Plans in Teams, please be aware of the following limitations:</span></span>
> * <span data-ttu-id="67eb3-113">**Voz híbrida no es compatible con Microsoft Teams**: actualmente no se admite Voz híbrida en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-113">**Hybrid Voice is not supported in Teams** - Hybrid Voice is currently not supported in Teams.</span></span> <span data-ttu-id="67eb3-114">Los clientes de Voz híbrida no reciben notificación alguna para cambiar las directivas para recibir llamadas en Microsoft Teams, dado que esto provocaría interrupciones en el servicio.</span><span class="sxs-lookup"><span data-stu-id="67eb3-114">Hybrid Voice customers are not advised to change any of the policies to receive calls in Teams, as this will cause service interruptions.</span></span>
> * <span data-ttu-id="67eb3-115">**Las llamadas federadas no son compatibles con Microsoft Teams**: actualmente no se admiten las llamadas federadas (llamadas entre inquilinos/compañías) en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-115">**Federated calling is not supported in Teams** - Federated calling (calling between tenants/companies) is currently not supported in Teams.</span></span> <span data-ttu-id="67eb3-116">Hasta que esta característica sea compatible con Microsoft Teams, las llamadas federadas se dirigirán siempre a Skype Empresarial sin importar su configuración de llamadas.</span><span class="sxs-lookup"><span data-stu-id="67eb3-116">Federated calls will always be routed to Skype for Business regardless of how you configure calling, until it's supported in Teams.</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="67eb3-117">Configuración de la directiva de interoperabilidad de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67eb3-117">Teams interop policy configuration</span></span>
<span data-ttu-id="67eb3-118">Para que Microsoft Teams pueda empezar a recibir llamadas, tendrá que actualizar la directiva de interoperabilidad de Microsoft Teams utilizando una sesión de Windows PowerShell remota con los cmdlets [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) de Skype Empresarial para redirigir las llamadas a esta plataforma.</span><span class="sxs-lookup"><span data-stu-id="67eb3-118">To enable Teams to begin receiving calls, you'll need to update Teams interop policy, using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span> <span data-ttu-id="67eb3-119">Para obtener más información sobre la directiva de interoperabilidad de Microsoft Teams, consulte [Interoperabilidad entre Microsoft Teams y Skype Empresarial](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span><span class="sxs-lookup"><span data-stu-id="67eb3-119">For more information about Teams interop policy, see [Microsoft Teams and Skype for Business Interoperability](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span></span>

> [!TIP]
> <span data-ttu-id="67eb3-120">Para buscar los cmdlets de PowerShell que necesita, escriba "CsTeamsInteropPolicy" en el cuadro **Filtrar** en la [documentación sobre los cmdlets de PowerShell para Skype Empresarial](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="67eb3-120">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-interop-policy"></a><span data-ttu-id="67eb3-121">Directiva de interoperabilidad predeterminada de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67eb3-121">Default Teams interop policy</span></span>
<span data-ttu-id="67eb3-122">Microsoft Teams tiene una configuración de directiva predeterminada diseñada para garantizar que no se interrumpan los flujos de trabajo empresariales existentes durante el proceso de implementación de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-122">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="67eb3-123">De forma predeterminada, VoIP, RTC y las llamadas federadas a los usuarios se seguirán dirigiendo a Skype Empresarial hasta que actualice la directiva para permitir las llamadas entrantes en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-123">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="67eb3-124">De este modo se garantiza que no se producirán interrupciones no deseadas en los servicios de voz cuando inicie el proyecto piloto de Microsoft Teams o comience la implementación.</span><span class="sxs-lookup"><span data-stu-id="67eb3-124">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="67eb3-125">La directiva de interoperabilidad de Microsoft Teams tiene la siguiente configuración predeterminada:</span><span class="sxs-lookup"><span data-stu-id="67eb3-125">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="67eb3-126">Los comportamientos de la configuración predeterminada son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="67eb3-126">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="67eb3-127">**Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para garantizar que las llamadas de Skype Empresarial se dirijan a Skype Empresarial y las de Microsoft Teams a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-127">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="67eb3-128">RTC y las llamadas federadas se dirigirán a Skype Empresarial si se aplica esta directiva.</span><span class="sxs-lookup"><span data-stu-id="67eb3-128">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="67eb3-129">**Para los clientes sin Skype Empresarial**, si se aplica, además de llamadas entre usuarios de Microsoft Teams, solo se podrán realizar llamadas RTC salientes en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-129">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="67eb3-130">Tendrá que modificar la directiva de interoperabilidad de Microsoft Teams asignada a sus usuarios para que puedan recibir llamadas RTC en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-130">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="67eb3-131">Los usuarios aprovisionados con licencias de Sistema telefónico y Planes de llamada para el uso con Skype Empresarial Online que tengan configurada la directiva de interoperabilidad global predeterminada de Microsoft Teams tendrán habilitada la ficha Llamadas en Microsoft Teams y podrán realizar llamadas RTC salientes desde la aplicación sin que un administrador tenga que realizar ninguna acción específica.</span><span class="sxs-lookup"><span data-stu-id="67eb3-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a><span data-ttu-id="67eb3-132">Cómo configurar Microsoft Teams para usar la directiva predeterminada</span><span class="sxs-lookup"><span data-stu-id="67eb3-132">How to configure Teams to use the default policy</span></span>
<span data-ttu-id="67eb3-133">De forma predeterminada, la directiva de interoperabilidad global de Microsoft Teams se aplica a todos los usuarios del inquilino y está configurada con los ajustes predeterminados descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="67eb3-133">By default, global Teams interop policy is applied to all users in your tenant, and it is configured with the default settings as described above.</span></span> <span data-ttu-id="67eb3-134">Si por algún motivo ha establecido directivas diferentes para sus usuarios y desea revertir los ajustes a la configuración predeterminada, tendrá que aplicar la directiva de interoperabilidad global de Microsoft Teams a través de una sesión de Windows PowerShell remota para Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="67eb3-134">If for some reason you have granted different policies to your users and would like to revert to the default setting, you will need to apply the global Teams interop policy via Skype for Business remote Windows PowerShell session:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> <span data-ttu-id="67eb3-135">Aunque es posible modificar los valores predeterminados de la directiva de interoperabilidad global de Microsoft Teams, recomendamos encarecidamente no hacerlo.</span><span class="sxs-lookup"><span data-stu-id="67eb3-135">While it is possible to modify the global Teams interop policy from the default values, we strongly advise against it.</span></span> 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="67eb3-136">Configurar Microsoft Teams para recibir llamadas RTC entrantes</span><span class="sxs-lookup"><span data-stu-id="67eb3-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="67eb3-137">Para recibir llamadas RTC entrantes en Microsoft Teams, deberá configurar Microsoft Teams como la aplicación de llamadas predeterminada aplicando la directiva de interoperabilidad de Microsoft Teams con el parámetro `CallingDefaultClient` establecido en Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67eb3-138">Recomendamos aplicar esta configuración a un conjunto inicial de usuarios para explorar las excitantes nuevas funcionalidades de llamada que ofrece Microsoft Teams antes de realizar cambios en un grupo más grande o en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="67eb3-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="67eb3-139">Puede utilizar la siguiente directiva de interoperabilidad preconfigurada de Microsoft Teams para dirigir las llamadas RTC entrantes a Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="67eb3-139">Consider using the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="67eb3-140">Los comportamientos de la directiva anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="67eb3-140">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="67eb3-141">**Para los clientes existentes de Skype Empresarial**, esta directiva está diseñada para redirigir las llamadas entrantes a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-141">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="67eb3-142">Esto afecta tanto a las llamadas VoIP (desde Microsoft Teams y Skype Empresarial) como a las RTC.</span><span class="sxs-lookup"><span data-stu-id="67eb3-142">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> <span data-ttu-id="67eb3-143">Las llamadas federadas se seguirán recibiendo en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="67eb3-143">Federated calls will continue to be received in Skype for Business.</span></span> 
* <span data-ttu-id="67eb3-144">**Para los clientes sin Skype Empresarial**, al aplicar esta directiva, las llamadas RTC se recibirán en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span> <span data-ttu-id="67eb3-145">Actualmente las llamadas federadas **no se admiten** en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-145">Federated calling is currently **not supported** in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="67eb3-146">Actualmente, cambiar `CallingDefaultClient` a Teams afectará también a las llamadas a teléfonos IP de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="67eb3-146">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="67eb3-147">Las llamadas entrantes no se recibirán en los teléfonos y solo sonarán en los clientes de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67eb3-147">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="67eb3-148">Consulte [De Skype Empresarial a Microsoft Teams: mapa de ruta de las opciones](https://aka.ms/skype2teamsroadmap) para obtener información sobre compatibilidad con teléfonos SIP existentes.</span><span class="sxs-lookup"><span data-stu-id="67eb3-148">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a><span data-ttu-id="67eb3-149">Cómo configurar Microsoft Teams para recibir llamadas RTC</span><span class="sxs-lookup"><span data-stu-id="67eb3-149">How to configure Teams to receive PSTN calls</span></span>
<span data-ttu-id="67eb3-150">Aplique la directiva de interoperabilidad de Microsoft Teams del modo descrito con anterioridad a través de una sesión de Windows PowerShell remota para Skype Empresarial para redirigir las llamadas a Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="67eb3-150">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a><span data-ttu-id="67eb3-151">Configurar Microsoft Teams para permitir que los usuarios cambien su experiencia de llamada preferida</span><span class="sxs-lookup"><span data-stu-id="67eb3-151">Configuring Teams to allow users to change their preferred calling experience</span></span>
<span data-ttu-id="67eb3-152">Para permitir que los usuarios tomen sus propias decisiones en cuanto a la experiencia de llamada preferida (recibir llamadas en Microsoft Teams o Skype Empresarial) debe crear una directiva de interoperabilidad de Microsoft Teams personalizada que habilite el parámetro `AllowEndUserClientOverride`.</span><span class="sxs-lookup"><span data-stu-id="67eb3-152">To let users to make their own decision over the preferred calling experience, whether to receive calls in Teams or Skype for Business, you need to create a custom Teams interop policy that enables `AllowEndUserClientOverride` parameter.</span></span>

<span data-ttu-id="67eb3-153">A continuación se muestra un ejemplo de la directiva de interoperabilidad de Microsoft Teams para permitir que los usuarios elijan la experiencia de llamada preferida:</span><span class="sxs-lookup"><span data-stu-id="67eb3-153">The following is the example of Teams interop policy to enable user choice of the preferred calling experience:</span></span>

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="67eb3-154">Una vez que se aplica esta directiva personalizada a los usuarios, la opción de cambiar la aplicación de llamada preferida estará disponible en el cliente de Microsoft Teams para que los usuarios realicen los cambios ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="67eb3-154">Once this custom policy is applied to the users, the option to change the preferred calling application will be available in Teams client for users to make the changes themselves.</span></span>

![Opción de aplicación de llamadas preferida](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> <span data-ttu-id="67eb3-156">Recomendamos aplicar esta configuración a un conjunto inicial de usuarios antes de realizar cambios en un grupo más grande o en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="67eb3-156">It is recommended that you apply this configuration to an initial set of users prior to making wider or organization level changes.</span></span>

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a><span data-ttu-id="67eb3-157">Cómo crear y aplicar la directiva de interoperabilidad personalizada de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67eb3-157">How to create and apply the custom Teams interop policy</span></span>
<span data-ttu-id="67eb3-158">Para crear la directiva de interoperabilidad personalizada de Microsoft Teams del modo descrito con anterioridad a través de una sesión de Windows PowerShell remota para Skype Empresarial, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="67eb3-158">To create the custom Teams interop policy as described above via Skype for Business remote Windows PowerShell session, perform the following:</span></span>

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a><span data-ttu-id="67eb3-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="67eb3-159">See also</span></span>
[<span data-ttu-id="67eb3-160">Configurar Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="67eb3-160">Set up Calling Plans</span></span>](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[<span data-ttu-id="67eb3-161">Interoperabilidad entre Microsoft Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="67eb3-161">Microsoft Teams and Skype for Business Interoperability</span></span>](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[<span data-ttu-id="67eb3-162">Guía práctica para Sistema telefónico con planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67eb3-162">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="67eb3-163">Referencia de cmdlets de PowerShell para Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="67eb3-163">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="67eb3-164">Referencia de cmdlets de PowerShell para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67eb3-164">PowerShell cmdlet reference for Teams</span></span>](https://docs.microsoft.com/powershell/module/teams)
