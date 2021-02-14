---
title: Agregar, cambiar, quitar ubicaciones de emergencia
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
description: 'Obtenga información sobre cómo agregar, cambiar o quitar una ubicación de emergencia de su organización en el Centro de administración de Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a470a75d367bc47d4063a2a99171a4a09e052fca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799950"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="92af7-103">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="92af7-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="92af7-104">Una ubicación de emergencia debe estar asociada a un número de teléfono, pero cuando esto ocurre puede variar entre países y regiones.</span><span class="sxs-lookup"><span data-stu-id="92af7-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="92af7-105">Por ejemplo, en Estados Unidos, necesita asociar una ubicación de emergencia al asignar el número de teléfono al usuario.</span><span class="sxs-lookup"><span data-stu-id="92af7-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="92af7-106">En el Reino Unido, debe asociar una ubicación de emergencia al número de teléfono cuando obtiene los números de teléfono de Microsoft 365 u Office 365 o los transfiere desde su proveedor de servicios actual.</span><span class="sxs-lookup"><span data-stu-id="92af7-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="92af7-107">No importa en qué país o región se encuentra, puede agregar un lugar o lugares a una ubicación de emergencia y quitar una ubicación de emergencia.</span><span class="sxs-lookup"><span data-stu-id="92af7-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="92af7-108">Según el número de ubicaciones físicas de su organización, puede crear lugares para edificios, pisos y oficinas.</span><span class="sxs-lookup"><span data-stu-id="92af7-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="92af7-109">Vea [Administrar llamadas de emergencia.](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="92af7-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="92af7-110">Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, consulte licencias [de complementos de Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="92af7-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="92af7-111">Puede administrar las ubicaciones de emergencia de su organización en el centro de administración de Microsoft Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92af7-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="92af7-112">Agregar una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="92af7-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="92af7-113">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92af7-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="92af7-114">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="92af7-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="92af7-115">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="92af7-115">Click **Add**.</span></span>
3. <span data-ttu-id="92af7-116">Escriba un nombre y una descripción para la ubicación.</span><span class="sxs-lookup"><span data-stu-id="92af7-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="92af7-117">Selecciona el país o la región y, a continuación, escribe la dirección.</span><span class="sxs-lookup"><span data-stu-id="92af7-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="92af7-118">En Bélgica, Francia, Alemania, Irlanda, Países Bajos y España, es importante comprender que para activar correctamente un número de teléfono en Microsoft 365 u Office 365, la dirección configurada en la ubicación de emergencia, que se utiliza para adquirir el número, debe coincidir con el código de área del número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="92af7-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

5. <span data-ttu-id="92af7-119">Si no encuentra la dirección y quiere editarla manualmente, active Editar manualmente la **dirección.**</span><span class="sxs-lookup"><span data-stu-id="92af7-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="92af7-120">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92af7-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="92af7-121">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="92af7-121">Using PowerShell</span></span>

<span data-ttu-id="92af7-122">Vea [New-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="92af7-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="92af7-123">Cambiar una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="92af7-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="92af7-124">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92af7-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="92af7-125">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="92af7-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="92af7-126">En la lista, seleccione la ubicación que desea cambiar y, a continuación, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="92af7-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="92af7-127">Realice los cambios que desee.</span><span class="sxs-lookup"><span data-stu-id="92af7-127">Make the changes you want.</span></span>
4. <span data-ttu-id="92af7-128">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92af7-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="92af7-129">Solo puede cambiar la información de dirección de una ubicación si la dirección no está validada.</span><span class="sxs-lookup"><span data-stu-id="92af7-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="92af7-130">Si la dirección ya está validada y necesita cambiarla, elimine la ubicación y, a continuación, cree una nueva ubicación con la dirección correcta.</span><span class="sxs-lookup"><span data-stu-id="92af7-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="92af7-131">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="92af7-131">Using PowerShell</span></span>

<span data-ttu-id="92af7-132">Vea [Set-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="92af7-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="92af7-133">Quitar una ubicación de emergencia</span><span class="sxs-lookup"><span data-stu-id="92af7-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="92af7-134">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92af7-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="92af7-135">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en  >  **Ubicaciones, Direcciones de emergencia.**</span><span class="sxs-lookup"><span data-stu-id="92af7-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="92af7-136">En la lista, seleccione la ubicación que desea quitar y, a continuación, haga clic en **Eliminar.**</span><span class="sxs-lookup"><span data-stu-id="92af7-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="92af7-137">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="92af7-137">Using PowerShell</span></span>

<span data-ttu-id="92af7-138">Vea [Remove-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)</span><span class="sxs-lookup"><span data-stu-id="92af7-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="92af7-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="92af7-139">Related topics</span></span>

- [<span data-ttu-id="92af7-140">Administrar llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="92af7-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="92af7-141">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="92af7-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="92af7-142">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="92af7-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="92af7-143">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="92af7-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
