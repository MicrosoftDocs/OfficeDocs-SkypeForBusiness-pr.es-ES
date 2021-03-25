---
title: Agregar, cambiar y quitar lugares para ubicaciones de emergencia
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo agregar, cambiar o quitar un lugar para una ubicación de emergencia para su organización en el Centro de administración de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121508"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="26ec8-103">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="26ec8-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="26ec8-104">Según el número de ubicaciones físicas de su organización, puede agregar lugares para edificios, pisos y oficinas para crear una ubicación de emergencia más específica.</span><span class="sxs-lookup"><span data-stu-id="26ec8-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="26ec8-105">Vea [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="26ec8-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="26ec8-106">Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, vea [Licencias de complementos de Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="26ec8-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="26ec8-107">Puede administrar ubicaciones de emergencia para su organización en el Centro de administración de Microsoft Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26ec8-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="26ec8-108">Agregar un lugar a una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="26ec8-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="26ec8-109">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="26ec8-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="26ec8-110">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Ubicaciones**  >  **Direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="26ec8-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="26ec8-111">En la lista, haga clic en el nombre de la ubicación a la que desea agregar un lugar.</span><span class="sxs-lookup"><span data-stu-id="26ec8-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="26ec8-112">En la **pestaña Lugares,** haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="26ec8-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="26ec8-113">Escriba un nombre de lugar y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="26ec8-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="26ec8-114">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="26ec8-114">Using PowerShell</span></span>

<span data-ttu-id="26ec8-115">Vea [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="26ec8-115">See [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="26ec8-116">Cambiar un lugar para una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="26ec8-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="26ec8-117">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="26ec8-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="26ec8-118">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Ubicaciones**  >  **Direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="26ec8-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="26ec8-119">En la lista, haga clic en el nombre de la ubicación para la que desea cambiar un lugar.</span><span class="sxs-lookup"><span data-stu-id="26ec8-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="26ec8-120">En la **pestaña Lugares,** seleccione el lugar que desea cambiar y, a continuación, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="26ec8-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="26ec8-121">Actualice la información de la posición y, a continuación, haga clic **en Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="26ec8-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="26ec8-122">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="26ec8-122">Using PowerShell</span></span>

<span data-ttu-id="26ec8-123">Vea [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="26ec8-123">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="26ec8-124">Quitar un lugar de una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="26ec8-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="26ec8-125">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="26ec8-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="26ec8-126">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Ubicaciones**  >  **Direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="26ec8-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="26ec8-127">En la lista, haga clic en el nombre de la ubicación para la que desea quitar un lugar.</span><span class="sxs-lookup"><span data-stu-id="26ec8-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="26ec8-128">En la **pestaña Lugares,** seleccione el lugar que desea quitar y, a continuación, haga clic en **Eliminar.**</span><span class="sxs-lookup"><span data-stu-id="26ec8-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="26ec8-129">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="26ec8-129">Using PowerShell</span></span>

<span data-ttu-id="26ec8-130">Vea [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="26ec8-130">See [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="26ec8-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="26ec8-131">Related topics</span></span>

- [<span data-ttu-id="26ec8-132">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="26ec8-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="26ec8-133">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="26ec8-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="26ec8-134">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="26ec8-134">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)