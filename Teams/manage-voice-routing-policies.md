---
title: Administrar directivas de enrutamiento de voz en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo crear y administrar directivas de enrutamiento de voz en Microsoft Teams.
ms.openlocfilehash: ac856ef05d425208af43307ebe12ff0c4776ca51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101076"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="5518d-103">Administrar directivas de enrutamiento de voz en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5518d-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="5518d-104">Si ha implementado [](direct-routing-landing-page.md) enrutamiento directo del sistema telefónico en su organización, use directivas de enrutamiento de voz para permitir que los usuarios de Teams y Skype Empresarial Online reciban y realicen llamadas telefónicas a la red telefónica conmutada (RTC) con su infraestructura de telefonía local.</span><span class="sxs-lookup"><span data-stu-id="5518d-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="5518d-105">Una directiva de enrutamiento de voz es un contenedor para los registros de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="5518d-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="5518d-106">Para crear y administrar directivas de enrutamiento de voz, vaya a Directivas de enrutamiento de voz en el Centro de administración de Microsoft Teams o mediante  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5518d-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="5518d-107">Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="5518d-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="5518d-108">Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="5518d-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="5518d-109">Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiar el nombre ni eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="5518d-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="5518d-110">Es importante saber que asignar una directiva de enrutamiento de voz a un usuario no le permite realizar llamadas RTC en Teams.</span><span class="sxs-lookup"><span data-stu-id="5518d-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="5518d-111">También tendrá que habilitar al usuario para el enrutamiento directo del sistema telefónico y completar otros pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="5518d-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="5518d-112">Para obtener más información, vea [Configurar enrutamiento directo.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="5518d-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="5518d-113">Crear una directiva de enrutamiento de voz personalizada</span><span class="sxs-lookup"><span data-stu-id="5518d-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="5518d-114">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5518d-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="5518d-115">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya **a** Directivas de enrutamiento de voz  >  **y,** a continuación, haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="5518d-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="5518d-116">![Captura de pantalla de la página Agregar directiva de enrutamiento de voz en el Centro de administración de Microsoft Teams ](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="5518d-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="5518d-117">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="5518d-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="5518d-118">En **Registros de uso de** RTC, haga clic en Agregar uso de **RTC** y, a continuación, seleccione los registros que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="5518d-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="5518d-119">Si necesita crear un nuevo registro de uso de RTC, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5518d-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="5518d-120">Si ha agregado varios registros de uso de RTC, organice los registros en el orden que desee.</span><span class="sxs-lookup"><span data-stu-id="5518d-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="5518d-121">Cuando haya terminado, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="5518d-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="5518d-122">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5518d-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="5518d-123">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5518d-123">Using PowerShell</span></span>

<span data-ttu-id="5518d-124">Vea [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="5518d-124">See [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="5518d-125">Editar una directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="5518d-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="5518d-126">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5518d-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="5518d-127">Puede editar la directiva global o las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="5518d-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="5518d-128">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de** enrutamiento  >  **de** voz.</span><span class="sxs-lookup"><span data-stu-id="5518d-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="5518d-129">Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5518d-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="5518d-130">Haga clic en Agregar o quitar registros de uso de **RTC,** realice los cambios que desee y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="5518d-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="5518d-131">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5518d-131">Using PowerShell</span></span>

<span data-ttu-id="5518d-132">Vea [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="5518d-132">See [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="5518d-133">Asignar una directiva de enrutamiento de voz personalizada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="5518d-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="5518d-134">Vea también [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="5518d-134">See also [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5518d-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5518d-135">Related topics</span></span>

[<span data-ttu-id="5518d-136">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="5518d-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="5518d-137">Configurar el enrutamiento de voz para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="5518d-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="5518d-138">Habilitar enrutamiento basado en la ubicación para el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="5518d-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="5518d-139">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="5518d-139">Assign policies to your users in Teams</span></span>](assign-policies.md)