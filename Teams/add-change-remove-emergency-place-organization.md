---
title: Agregar, cambiar o quitar lugares de las ubicaciones de emergencia
author: lanachin
ms.author: v-lanac
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
description: Obtenga información sobre cómo agregar, cambiar o quitar un lugar para una ubicación de emergencia para su organización en el centro de administración de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232501"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="abbfb-103">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="abbfb-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="abbfb-104">Según el número de ubicaciones físicas de su organización, puede agregar lugares para edificios, plantas y oficinas para crear una ubicación de emergencia más específica.</span><span class="sxs-lookup"><span data-stu-id="abbfb-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="abbfb-105">Para obtener más información, consulta [administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md) .</span><span class="sxs-lookup"><span data-stu-id="abbfb-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="abbfb-106">Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, vea [licencias complementarias de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="abbfb-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="abbfb-107">Administre las ubicaciones de emergencia de su organización en el centro de administración de Microsoft Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="abbfb-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="abbfb-108">Agregar un lugar a una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="abbfb-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="abbfb-109">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="abbfb-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="abbfb-110">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en **ubicaciones**de  >  **emergencia**.</span><span class="sxs-lookup"><span data-stu-id="abbfb-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="abbfb-111">En la lista, haga clic en el nombre de la ubicación en la que desea agregar un lugar.</span><span class="sxs-lookup"><span data-stu-id="abbfb-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="abbfb-112">En la pestaña **posiciones** , haga clic en **Agregar lugar**.</span><span class="sxs-lookup"><span data-stu-id="abbfb-112">On the **Places** tab, click **Add place**.</span></span>
4. <span data-ttu-id="abbfb-113">Escriba un nombre para el sitio y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="abbfb-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="abbfb-114">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="abbfb-114">Using PowerShell</span></span>

<span data-ttu-id="abbfb-115">Vea [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="abbfb-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="abbfb-116">Cambiar un lugar para una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="abbfb-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="abbfb-117">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="abbfb-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="abbfb-118">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en **ubicaciones**de  >  **emergencia**.</span><span class="sxs-lookup"><span data-stu-id="abbfb-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="abbfb-119">En la lista, haga clic en el nombre de la ubicación para la que desea cambiar un lugar.</span><span class="sxs-lookup"><span data-stu-id="abbfb-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="abbfb-120">En la pestaña **lugares** , seleccione el lugar que desee cambiar y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="abbfb-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="abbfb-121">Actualice la información de ubicación y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="abbfb-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="abbfb-122">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="abbfb-122">Using PowerShell</span></span>

<span data-ttu-id="abbfb-123">Consulte [set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="abbfb-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="abbfb-124">Quitar un lugar de una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="abbfb-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="abbfb-125">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="abbfb-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="abbfb-126">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en **ubicaciones**de  >  **emergencia**.</span><span class="sxs-lookup"><span data-stu-id="abbfb-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="abbfb-127">En la lista, haga clic en el nombre de la ubicación para la que desea quitar un lugar.</span><span class="sxs-lookup"><span data-stu-id="abbfb-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="abbfb-128">En la pestaña **lugares** , seleccione el lugar que desea quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="abbfb-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="abbfb-129">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="abbfb-129">Using PowerShell</span></span>

<span data-ttu-id="abbfb-130">Consulte [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="abbfb-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="abbfb-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="abbfb-131">Related topics</span></span>

- [<span data-ttu-id="abbfb-132">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="abbfb-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="abbfb-133">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="abbfb-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="abbfb-134">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="abbfb-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
