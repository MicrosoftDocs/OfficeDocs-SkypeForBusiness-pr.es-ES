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
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87670ea398150e4895f2d87ccc48f60aba2d1377
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516483"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="85512-103">Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85512-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="85512-104">Esta guía le ayudará a poner en funcionamiento un conjunto de usuarios para que puedan explorar Planes de llamada en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85512-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="85512-105">Lea el anuncio del 12 de diciembre de 2017 sobre Planes de llamada en Microsoft Teams: [El avance de la comunicación inteligente con las llamadas en Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="85512-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="85512-106">Le recomendamos que, en paralelo con esta guía de inicio rápido, lea el [sistema telefónico con los planes de llamadas](calling-plan-landing-page.md) y [FastTrack](https://aka.ms/cloudvoice) para planear y dirigir una correcta implantación.</span><span class="sxs-lookup"><span data-stu-id="85512-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="85512-107">Ahora, al agregar Planes de llamada (una función de Office 365 con tecnología de Skype Empresarial), puede usar Microsoft Teams para hacer y recibir llamadas telefónicas a números nacionales y móviles o desde ellos a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="85512-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Captura de pantalla que muestra la página contactos en Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="85512-109">Requisitos previos para habilitar la ficha **Llamadas** en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85512-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="85512-110">Para habilitar la pestaña **llamadas** en Teams, los usuarios deben tener habilitadas las llamadas de 1:1 en Teams y usar un cliente de teams que admita las llamadas de 1:1 equipos.</span><span class="sxs-lookup"><span data-stu-id="85512-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="85512-111">Para obtener información sobre cómo administrar las llamadas de 1:1 en Teams, lea [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="85512-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="85512-112">Para saber qué clientes son compatibles con las llamadas, lea [límites y especificaciones de Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="85512-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="85512-113">En la actualidad, el buzón de voz no estará disponible en la ficha llamadas, a menos que el usuario tenga habilitada la opción de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="85512-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="85512-114">Requisitos previos para habilitar el **teclado de marcado** en Teams</span><span class="sxs-lookup"><span data-stu-id="85512-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="85512-115">Para habilitar la pestaña **teclado de marcado** en Teams y permitir que los usuarios realicen y reciban llamadas RTC, necesitará aprovisionar usuarios para los planes de llamadas y del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="85512-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="85512-116">Para obtener información sobre cómo configurar planes de llamadas, consulte [configurar planes de llamadas](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="85512-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="85512-117">También puede usar el enrutamiento directo para permitir que los usuarios realicen y reciban llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="85512-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="85512-118">Para obtener información sobre cómo configurar el enrutamiento directo, lea [configurar el enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="85512-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="85512-119">Uso de TeamsUpgradePolicy para controlar dónde se encuentran las llamadas</span><span class="sxs-lookup"><span data-stu-id="85512-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="85512-120">Para controlar si las llamadas (y chats) entrantes en Teams o Skype empresarial, los administradores usan TeamsUpgradePolicy, ya sea con el [centro de administración de Microsoft Teams](https://aka.ms/teamsadmincenter) o mediante una sesión remota de Windows PowerShell con [Skype empresarial](https://docs.microsoft.com/powershell/module/skype) . cmdlets.</span><span class="sxs-lookup"><span data-stu-id="85512-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="85512-121">La configuración predeterminada de TeamsUpgradePolicy es el modo islas, que está diseñado para garantizar que los flujos de trabajo empresariales existentes no se interrumpan durante una implementación de Teams.</span><span class="sxs-lookup"><span data-stu-id="85512-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="85512-122">De forma predeterminada, las llamadas VoIP, RTC y federadas a los usuarios se seguirán redirigiendo a Skype empresarial hasta que actualice la Directiva para habilitar las llamadas entrantes a teams.</span><span class="sxs-lookup"><span data-stu-id="85512-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="85512-123">Cuando los destinatarios se encuentran en el modo islas:</span><span class="sxs-lookup"><span data-stu-id="85512-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="85512-124">Las llamadas de VOIP entrantes originadas en Skype empresarial siempre se encuentran en el cliente de Skype empresarial del destinatario.</span><span class="sxs-lookup"><span data-stu-id="85512-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="85512-125">Llamadas VOIP entrantes originadas en Teams en los equipos, *si el remitente y el receptor están en el mismo inquilino*.</span><span class="sxs-lookup"><span data-stu-id="85512-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="85512-126">La telefonía VOIP federada entrante (con independencia de qué cliente se origina) y las llamadas de RTC siempre se encuentran en el cliente de Skype empresarial del destinatario.</span><span class="sxs-lookup"><span data-stu-id="85512-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="85512-127">Para garantizar que las llamadas RTC y VOIP entrantes siempre se encuentran en el cliente de equipos de un usuario, actualice el modo de coexistencia del usuario para que sea TeamsOnly (lo que significa, asígneles la instancia "UpgradeToTeams" de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="85512-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="85512-128">Para obtener más información sobre los modos de coexistencia y TeamsUpgradePolicy, consulte [Guía de migración e interoperabilidad para las organizaciones que usan Teams conjuntamente con Skype empresarial](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="85512-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="85512-129">**Lotus**</span><span class="sxs-lookup"><span data-stu-id="85512-129">**NOTES**</span></span>
 - <span data-ttu-id="85512-130">Los teléfonos IP de Skype empresarial recibirán llamadas, incluso si el usuario está en modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="85512-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="85512-131">Los usuarios que se han suministrado con el sistema telefónico y las licencias de planes de llamadas para su uso con Skype empresarial online (por ejemplo, se les ha asignado un valor de OnlineVoiceRoutingPolicy), tienen la ficha llamadas habilitada en Teams y pueden realizar llamadas RTC salientes desde Teams sin administradores tengan que realizar ninguna acción administrativa.</span><span class="sxs-lookup"><span data-stu-id="85512-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="85512-132">Cómo configurar los usuarios para que reciban todas las llamadas de VOIP y RTC entrantes en Teams</span><span class="sxs-lookup"><span data-stu-id="85512-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="85512-133">Para asegurarse de que los usuarios reciban todas las llamadas de VOIP y RTC entrantes en Teams, establezca el modo de coexistencia del usuario en TeamsOnly en el centro de administración de Microsoft Teams o use la sesión de Windows PowerShell remota de Skype empresarial para actualizar TeamsUpgradePolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="85512-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="85512-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="85512-134">See also</span></span>
[<span data-ttu-id="85512-135">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="85512-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="85512-136">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="85512-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="85512-137">Sistema telefónico con Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="85512-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="85512-138">Referencia del cmdlet de PowerShell de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="85512-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

