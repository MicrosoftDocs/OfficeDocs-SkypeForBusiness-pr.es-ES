---
title: 'Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams'
author: arachmanGitHub
ms.author: Rowille
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: Rowille, lolaj
search.appverid: MET150
description: Guía de inicio rápido para configurar Planes de llamada en Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6c719d17938986ff6568b73864bc131667e4e7
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401986"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="159bb-103">Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="159bb-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="159bb-104">Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar Planes de llamada en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="159bb-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="159bb-105">Lea el anuncio del 12 de diciembre de 2017 sobre Planes de llamada en Microsoft Teams: [El avance de la comunicación inteligente con las llamadas en Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="159bb-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="159bb-106">Se recomienda que, en paralelo con esta guía de inicio rápido, lea [Sistema telefónico con planes de llamada](calling-plan-landing-page.md) y [FastTrack](https://aka.ms/cloudvoice) para planear y unidad de una implementación correcta.</span><span class="sxs-lookup"><span data-stu-id="159bb-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="159bb-107">Ahora, al agregar Planes de llamada (una función de Office 365 con tecnología de Skype Empresarial), puede usar Microsoft Teams para hacer y recibir llamadas telefónicas a números nacionales y móviles o desde ellos a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="159bb-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Llamar en Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="159bb-109">Requisitos previos para habilitar la ficha **Llamadas** en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="159bb-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="159bb-110">Para habilitar la ficha de **llamadas** en los equipos de los usuarios necesitan tener habilitada en los equipos de llamada y utilizando a un cliente de los equipos que admite una llamada a los equipos de 1:1 de 1:1.</span><span class="sxs-lookup"><span data-stu-id="159bb-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="159bb-111">Para obtener información sobre cómo administrar las llamadas a 1:1 en los equipos, lea [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="159bb-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="159bb-112">Para obtener información sobre los clientes que admiten las llamadas, lea [los límites y las especificaciones de los equipos de Microsoft](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="159bb-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="159bb-113">En la actualidad, correo de voz no estará disponible en la ficha llamadas a menos que el usuario está habilitado para las llamadas de RTC.</span><span class="sxs-lookup"><span data-stu-id="159bb-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="159bb-114">Requisitos previos para habilitar el **Teclado de marcado** en los equipos</span><span class="sxs-lookup"><span data-stu-id="159bb-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="159bb-115">Para habilitar la ficha de **Teclado de marcado** en los equipos y permitir que los usuarios a realizar y recibir llamadas de RTC debe abastecer a los usuarios para el sistema telefónico y planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="159bb-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="159bb-116">Para obtener información sobre cómo configurar planes de llamada, lea [Configurar planes de llamada](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="159bb-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="159bb-117">También puede usar el enrutamiento directo para permitir a los usuarios a realizar y recibir llamadas de RTC.</span><span class="sxs-lookup"><span data-stu-id="159bb-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="159bb-118">Para obtener información sobre cómo configurar el enrutamiento directo, leer la [Configuración de enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="159bb-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="159bb-119">Uso de TeamsUpgradePolicy para control donde land llamadas</span><span class="sxs-lookup"><span data-stu-id="159bb-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="159bb-120">Para controlar si las llamadas entrantes (y chats) land en los equipos o Skype para la empresa, los administradores usan TeamsUpgradePolicy, mediante cualquiera de [Centro de administración de equipos de Microsoft](https://aka.ms/teamsadmincenter) o mediante una sesión remota de Windows PowerShell con el [Skype para la empresa](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span><span class="sxs-lookup"><span data-stu-id="159bb-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="159bb-121">La configuración predeterminada de TeamsUpgradePolicy es el modo islas, que está diseñado para asegurarse de que los flujos de trabajo no se interrumpen durante una implementación de los equipos de negocio existentes.</span><span class="sxs-lookup"><span data-stu-id="159bb-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="159bb-122">De forma predeterminada, VoIP, RTC y las llamadas a los usuarios federadas seguirán deben enrutarse a Skype para la empresa hasta que actualice la directiva para habilitar las llamadas entrantes a los equipos.</span><span class="sxs-lookup"><span data-stu-id="159bb-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="159bb-123">Cuando los destinatarios se encuentran en modo de islas:</span><span class="sxs-lookup"><span data-stu-id="159bb-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="159bb-124">VOIP entrante llama a ese originadas en Skype para la empresa siempre land en Skype del destinatario para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="159bb-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="159bb-125">VOIP entrante llama a se ha originado en el mundo de los equipos en los equipos, *Si el remitente y el destinatario se encuentran en el mismo arrendatario*.</span><span class="sxs-lookup"><span data-stu-id="159bb-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="159bb-126">Entrante federados VOIP (independientemente del cliente que se origina) y llamadas RTC siempre land en Skype del destinatario para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="159bb-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="159bb-127">Para asegurarse de que entrante VOIP y RTC llama siempre land en los equipos cliente de un usuario, actualizar el modo de coexistencia del usuario para que sea TeamsOnly (lo que significa que les asigne la instancia de "UpgradeToTeams" de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="159bb-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="159bb-128">Para obtener más información sobre los modos de coexistencia y TeamsUpgradePolicy, vea [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="159bb-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="159bb-129">**NOTAS**</span><span class="sxs-lookup"><span data-stu-id="159bb-129">**NOTES**</span></span>
 - <span data-ttu-id="159bb-130">Skype para teléfonos IP empresarial va a recibir llamadas, incluso si el usuario está en modo de TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="159bb-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="159bb-131">Usuarios que ya han aprovisionados con el sistema telefónico y llamar a los planes de licencias para su uso con Skype para profesionales en línea (por ejemplo, se les ha asignado un valor de OnlineVoiceRoutingPolicy), tendrá la ficha llamadas habilitada en los equipos y puede colocar las llamadas RTC salientes desde Equipos sin tener que realizar ninguna acción administrativa de los administradores.</span><span class="sxs-lookup"><span data-stu-id="159bb-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="159bb-132">Cómo configurar usuarios para recibir todos los entrantes VOIP y RTC llama en los equipos</span><span class="sxs-lookup"><span data-stu-id="159bb-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="159bb-133">Para asegurarse de que los usuarios reciben todas las llamadas entrantes de VOIP y RTC en los equipos, establezca el modo de coexistencia del usuario como TeamsOnly en el centro de administración de Microsoft Teams o usar Skype para la sesión remota de Windows PowerShell de negocio para actualizar TeamsUpgradePolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="159bb-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="159bb-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="159bb-134">See also</span></span>
[<span data-ttu-id="159bb-135">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="159bb-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="159bb-136">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="159bb-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="159bb-137">Sistema telefónico con planes de llamada</span><span class="sxs-lookup"><span data-stu-id="159bb-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="159bb-138">Skype para referencia del cmdlet de PowerShell de negocio</span><span class="sxs-lookup"><span data-stu-id="159bb-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

