---
title: Agregar, cambiar o quitar lugares para ubicaciones de emergencia
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
description: Obtenga información sobre cómo agregar, cambiar o quitar un lugar para una ubicación de emergencia de su organización en el Centro de administración de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806280"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="afac6-103">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="afac6-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="afac6-104">Según el número de ubicaciones físicas de su organización, puede agregar lugares para edificios, pisos y oficinas con el objetivo de crear una ubicación de emergencia más específica.</span><span class="sxs-lookup"><span data-stu-id="afac6-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="afac6-105">Vea [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="afac6-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="afac6-106">Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, consulte licencias [de complementos de Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="afac6-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="afac6-107">Puede administrar las ubicaciones de emergencia de su organización en el centro de administración de Microsoft Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afac6-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="afac6-108">Agregar un lugar a una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="afac6-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="afac6-109">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afac6-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="afac6-110">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="afac6-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="afac6-111">En la lista, haga clic en el nombre de la ubicación a la que desea agregar un lugar.</span><span class="sxs-lookup"><span data-stu-id="afac6-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="afac6-112">En la **pestaña Lugares,** haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="afac6-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="afac6-113">Escriba un nombre de lugar y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="afac6-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="afac6-114">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="afac6-114">Using PowerShell</span></span>

<span data-ttu-id="afac6-115">Vea [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="afac6-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="afac6-116">Cambiar un lugar para una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="afac6-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="afac6-117">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afac6-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="afac6-118">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="afac6-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="afac6-119">En la lista, haga clic en el nombre de la ubicación para la que desea cambiar un lugar.</span><span class="sxs-lookup"><span data-stu-id="afac6-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="afac6-120">En la **pestaña** Lugares, seleccione el lugar que desea cambiar y, a continuación, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="afac6-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="afac6-121">Actualice la información del lugar y, a continuación, haga clic en **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="afac6-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="afac6-122">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="afac6-122">Using PowerShell</span></span>

<span data-ttu-id="afac6-123">Vea [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="afac6-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="afac6-124">Quitar un lugar de una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="afac6-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="afac6-125">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afac6-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="afac6-126">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="afac6-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="afac6-127">En la lista, haga clic en el nombre de la ubicación para la que desea quitar un lugar.</span><span class="sxs-lookup"><span data-stu-id="afac6-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="afac6-128">En la **pestaña** Lugares, seleccione el lugar que desea quitar y, a continuación, haga clic en **Eliminar.**</span><span class="sxs-lookup"><span data-stu-id="afac6-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="afac6-129">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="afac6-129">Using PowerShell</span></span>

<span data-ttu-id="afac6-130">Vea [Remove-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="afac6-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="afac6-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="afac6-131">Related topics</span></span>

- [<span data-ttu-id="afac6-132">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="afac6-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="afac6-133">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="afac6-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="afac6-134">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="afac6-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
