---
title: Asignar o cambiar la ubicación de emergencia de un usuario
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
description: En este artículo, aprenderá a asignar o cambiar una ubicación de emergencia para los usuarios de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102986"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="44000-103">Asignar o cambiar la ubicación de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="44000-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="44000-104">Cuando configura planes de llamadas, debe asignar una ubicación de emergencia a cada número de teléfono o usuario.</span><span class="sxs-lookup"><span data-stu-id="44000-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="44000-105">En los países europeos, la ubicación de emergencia está asociada con el número de teléfono cuando lo obtiene de Microsoft 365 o Office 365 o al transferir un número de teléfono a Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="44000-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="44000-106">En Estados Unidos, la ubicación de emergencia está asociada con el número de teléfono cuando se asigna al usuario.</span><span class="sxs-lookup"><span data-stu-id="44000-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="44000-107">La dirección de emergencia se puede cambiar si el usuario al que está asignada se mueve a una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="44000-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="44000-108">Para obtener más información sobre las direcciones y ubicaciones de emergencia, vea ¿Qué son las ubicaciones de emergencia, los lugares [y el enrutamiento de llamadas?](./what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="44000-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](./what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="44000-109">Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, consulte Teams [licencias de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="44000-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="44000-110">Puede asignar o cambiar una ubicación de emergencia para un usuario en el centro de Microsoft Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44000-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="44000-111">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="44000-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="44000-112">En el panel de navegación izquierdo del centro Microsoft Teams de administración, haga **clic**  >  **en Teléfono números.**</span><span class="sxs-lookup"><span data-stu-id="44000-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="44000-113">En la **Teléfono números,** haga  clic en la pestaña Números, seleccione un número de usuario en la lista y, a continuación, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="44000-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="44000-114">En el **panel Editar,** en **Ubicación de emergencia**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="44000-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="44000-115">Para asignar una ubicación de emergencia, busque y seleccione una ubicación de emergencia.</span><span class="sxs-lookup"><span data-stu-id="44000-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="44000-116">Para cambiar la ubicación de emergencia que ya está asignada al usuario, haga clic en **X** para quitar la ubicación existente y, después, busque y seleccione la ubicación que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="44000-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="44000-117">Dependiendo de si desea enviar un correo electrónico al usuario con su información de número de teléfono, desactive o active Usuario de correo electrónico con información **de número de teléfono.**</span><span class="sxs-lookup"><span data-stu-id="44000-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="44000-118">De forma predeterminada, está en.</span><span class="sxs-lookup"><span data-stu-id="44000-118">By default, this is on.</span></span>

5. <span data-ttu-id="44000-119">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="44000-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="44000-120">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="44000-120">Using PowerShell</span></span>

<span data-ttu-id="44000-121">Vea [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="44000-121">See [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="44000-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="44000-122">Related topics</span></span>

- [<span data-ttu-id="44000-123">Administrar llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="44000-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="44000-124">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="44000-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="44000-125">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="44000-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="44000-126">Asignar o cambiar la ubicación de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="44000-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="44000-127">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="44000-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="44000-128">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="44000-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)
- [<span data-ttu-id="44000-129">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="44000-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)