---
title: Asignar o cambiar lugares para ubicaciones de emergencia para los usuarios
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
description: En este artículo aprenderá a asignar o cambiar el lugar para una ubicación de emergencia para los usuarios de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 385855c456d3a4e5c2de53fb2605e4d5d30d84a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809530"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="020ec-103">Asignar o cambiar el lugar de una ubicación de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="020ec-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="020ec-104">Cada número de teléfono activo debe tener una ubicación de emergencia asociada cuando asigne el número de teléfono a un usuario.</span><span class="sxs-lookup"><span data-stu-id="020ec-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="020ec-105">(Asocie la dirección al obtener un número de teléfono en Office 365 o al transferir un número de teléfono). Al asociar el número a una ubicación de emergencia, también puede agregar un lugar para proporcionar una ubicación más exacta dentro de una ubicación física.</span><span class="sxs-lookup"><span data-stu-id="020ec-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="020ec-106">Un lugar puede ser el piso, el ala del edificio o el número de oficina donde se encuentra el usuario.</span><span class="sxs-lookup"><span data-stu-id="020ec-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="020ec-107">Puede tener un número ilimitado de lugares para una ubicación de emergencia determinada, y puede cambiar el lugar si el usuario se traslada a otra oficina o edificio.</span><span class="sxs-lookup"><span data-stu-id="020ec-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="020ec-108">Por ejemplo, si el usuario pasa de la planta 34 a la 35.</span><span class="sxs-lookup"><span data-stu-id="020ec-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="020ec-109">Para obtener información sobre cómo obtener planes de llamadas y cuánto cuestan, consulte [licencias de complementos de Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="020ec-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="020ec-110">Puede asignar o cambiar la ubicación de una ubicación de emergencia para un usuario en el Centro de administración de Microsoft Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="020ec-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="020ec-111">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="020ec-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="020ec-112">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Números de** teléfono  >  **de voz.**</span><span class="sxs-lookup"><span data-stu-id="020ec-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="020ec-113">En la **página Números de** teléfono, haga clic en la **pestaña** Números, seleccione un número de usuario de la lista y, a continuación, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="020ec-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="020ec-114">En el **panel de** edición, en **Ubicación de** emergencia, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="020ec-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="020ec-115">Para asignar un lugar, busque la ubicación o el lugar y, a continuación, seleccione el lugar en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="020ec-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="020ec-116">Para cambiar el lugar que ya está asignado al usuario, haga clic en **X** para quitar la ubicación y el lugar existentes, busque y seleccione el lugar que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="020ec-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="020ec-117">En función de si desea enviar un correo electrónico al usuario con la información de su número de teléfono, desactive o active el usuario de Correo electrónico con la información del número **de teléfono.**</span><span class="sxs-lookup"><span data-stu-id="020ec-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="020ec-118">De forma predeterminada, está disponible.</span><span class="sxs-lookup"><span data-stu-id="020ec-118">By default, this is on.</span></span>

5. <span data-ttu-id="020ec-119">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="020ec-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="020ec-120">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="020ec-120">Using PowerShell</span></span>

<span data-ttu-id="020ec-121">Vea [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="020ec-121">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="020ec-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="020ec-122">Related topics</span></span>

- [<span data-ttu-id="020ec-123">Administrar llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="020ec-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="020ec-124">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="020ec-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="020ec-125">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="020ec-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="020ec-126">Asignar o cambiar la ubicación de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="020ec-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="020ec-127">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="020ec-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="020ec-128">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="020ec-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
