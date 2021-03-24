---
title: 'Guía de inicio rápido: Configurar planes de llamadas'
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guía de inicio rápido para configurar planes de llamadas en Microsoft Teams para que pueda poner en marcha un conjunto de usuarios.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101186"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="aadcf-103">Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aadcf-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="aadcf-104">Esta guía le ayudará a poner en marcha un conjunto de usuarios para que puedan explorar planes de llamadas en Teams.</span><span class="sxs-lookup"><span data-stu-id="aadcf-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="aadcf-105">Lea el anuncio del 12 de diciembre de 2017 sobre planes de llamadas en Teams: [Comunicaciones inteligentes da](https://aka.ms/ipyqus) el siguiente paso con las llamadas en Teams</span><span class="sxs-lookup"><span data-stu-id="aadcf-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="aadcf-106">Le recomendamos que, en paralelo con esta [](calling-plan-landing-page.md) guía de inicio rápido, lea Sistema telefónico con planes de llamadas y [FastTrack](https://aka.ms/cloudvoice) para planear e impulsar una implementación correcta.</span><span class="sxs-lookup"><span data-stu-id="aadcf-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="aadcf-107">Al agregar planes de llamadas (una característica de Microsoft 365 y Office 365 con tecnología de Skype Empresarial), ahora puede usar Teams para realizar y recibir llamadas telefónicas desde o hacia líneas terrestres y teléfonos móviles a través de la red telefónica conmutada (RTC) pública.</span><span class="sxs-lookup"><span data-stu-id="aadcf-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Captura de pantalla que muestra la página Contactos en Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="aadcf-109">Requisitos previos para habilitar la **pestaña Llamadas** en Teams</span><span class="sxs-lookup"><span data-stu-id="aadcf-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="aadcf-110">Para habilitar la **pestaña** Llamadas en Teams, los usuarios deben tener habilitadas las llamadas 1:1 en Teams y usar un cliente de Teams compatible con las llamadas de Teams 1:1.</span><span class="sxs-lookup"><span data-stu-id="aadcf-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="aadcf-111">Para obtener información sobre cómo administrar las llamadas 1:1 en Teams, lea [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="aadcf-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="aadcf-112">Para saber qué clientes admiten llamadas, lea [Límites y especificaciones de Microsoft Teams.](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="aadcf-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aadcf-113">Actualmente, el correo de voz no estará disponible en la pestaña Llamadas a menos que el usuario esté habilitado para las llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="aadcf-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="aadcf-114">Requisitos previos para habilitar el **teclado de marcado** en Teams</span><span class="sxs-lookup"><span data-stu-id="aadcf-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="aadcf-115">Para habilitar la pestaña **Teclado** de marcado en Teams y permitir que los usuarios realicen y reciban llamadas RTC, tendrá que aprovisionar a los usuarios para sistemas telefónicos y planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="aadcf-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="aadcf-116">Para obtener información sobre cómo configurar planes de llamadas, lea [Configurar planes de llamadas.](./set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="aadcf-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="aadcf-117">Además, para los usuarios solo de Teams, debe asegurarse de que "Permitir llamadas privadas" está habilitado en la directiva de llamadas de Teams.</span><span class="sxs-lookup"><span data-stu-id="aadcf-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="aadcf-118">Vea [Administrar Teams durante la transición al nuevo Centro de](./manage-teams-skypeforbusiness-admin-center.md) administración de Microsoft Teams para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="aadcf-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="aadcf-119">También puede usar enrutamiento directo para permitir que los usuarios realicen y reciban llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="aadcf-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="aadcf-120">Para obtener información sobre cómo configurar enrutamiento directo, lea [Configurar enrutamiento directo.](./direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="aadcf-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="aadcf-121">Usar TeamsUpgradePolicy para controlar la tierra de las llamadas</span><span class="sxs-lookup"><span data-stu-id="aadcf-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="aadcf-122">Para controlar si las llamadas entrantes (y chats) se desplome en Teams o Skype Empresarial, los administradores usan TeamsUpgradePolicy, con el Centro de administración de [Microsoft Teams](https://aka.ms/teamsadmincenter) o con una sesión de Windows PowerShell remota con los cmdlets de [Skype](/powershell/module/skype) Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aadcf-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="aadcf-123">La configuración predeterminada de TeamsUpgradePolicy es el modo Islas, que está diseñado para asegurarse de que los flujos de trabajo empresariales existentes no se interrumpen durante una implementación de Teams.</span><span class="sxs-lookup"><span data-stu-id="aadcf-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="aadcf-124">De forma predeterminada, voIP, RTC y llamadas federadas a los usuarios seguirán enrutadas a Skype Empresarial hasta que actualice la directiva para habilitar las llamadas entrantes a Teams.</span><span class="sxs-lookup"><span data-stu-id="aadcf-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="aadcf-125">Cuando los destinatarios están en modo islas:</span><span class="sxs-lookup"><span data-stu-id="aadcf-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="aadcf-126">Las llamadas VOIP entrantes que se originaron en Skype Empresarial siempre se reciben en el cliente de Skype Empresarial del destinatario.</span><span class="sxs-lookup"><span data-stu-id="aadcf-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="aadcf-127">Las llamadas VOIP entrantes que se originaron en Teams se encuentran en Teams, si el remitente y el receptor *se encuentran en el mismo espacio empresarial.*</span><span class="sxs-lookup"><span data-stu-id="aadcf-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="aadcf-128">El VOIP federado entrante (independientemente del cliente que se origine) y las llamadas RTC siempre se reciben en el cliente de Skype Empresarial del destinatario.</span><span class="sxs-lookup"><span data-stu-id="aadcf-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="aadcf-129">Para asegurarse de que las llamadas VOIP y RTC entrantes siempre se aterricen en el cliente de Teams de un usuario, actualice el modo de coexistencia del usuario para que sea TeamsOnly (es decir, asígneles la instancia "UpgradeToTeams" de TeamsUpgradePolicy).</span><span class="sxs-lookup"><span data-stu-id="aadcf-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="aadcf-130">Para obtener más información sobre los modos de coexistencia y TeamsUpgradePolicy, vea Instrucciones de migración e interoperabilidad para organizaciones que usan Teams junto [con Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="aadcf-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="aadcf-131">**NOTAS**</span><span class="sxs-lookup"><span data-stu-id="aadcf-131">**NOTES**</span></span>
 - <span data-ttu-id="aadcf-132">Los teléfonos IP de Skype Empresarial recibirán llamadas, incluso si el usuario está en modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="aadcf-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="aadcf-133">Los usuarios a los que se les ha aprovisionado licencias de sistemas telefónicos y planes de llamadas para su uso con Skype Empresarial Online (por ejemplo, se les ha asignado un valor de OnlineVoiceRoutingPolicy), tendrán la pestaña Llamadas habilitada en Teams y podrán realizar llamadas RTC salientes desde Teams sin que los administradores tengan que realizar ninguna acción administrativa.</span><span class="sxs-lookup"><span data-stu-id="aadcf-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="aadcf-134">Cómo configurar a los usuarios para que reciban todas las llamadas VOIP y RTC entrantes en Teams</span><span class="sxs-lookup"><span data-stu-id="aadcf-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="aadcf-135">Para asegurarse de que los usuarios reciben todas las llamadas VOIP y RTC entrantes en Teams, establezca el modo de coexistencia del usuario en TeamsOnly en el Centro de administración de Microsoft Teams o use la sesión remota de Windows PowerShell de Skype Empresarial para actualizar TeamsUpgradePolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="aadcf-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="aadcf-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="aadcf-136">See also</span></span>
[<span data-ttu-id="aadcf-137">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="aadcf-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="aadcf-138">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="aadcf-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="aadcf-139">PBX en la nube con Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="aadcf-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="aadcf-140">Referencia de cmdlet de PowerShell de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="aadcf-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)