---
title: Asignar y cambiar lugares para ubicaciones de emergencia para los usuarios
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
description: En este artículo, aprenderá a asignar o cambiar el lugar de una ubicación de emergencia para los usuarios de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff328f07a69676a4dbaf1c1370d9e225e9d67810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120832"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="6b8fa-103">Asignar o cambiar el lugar de una ubicación de emergencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="6b8fa-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="6b8fa-104">Cada número de teléfono activo debe tener una ubicación de emergencia asociada al asignar el número de teléfono a un usuario.</span><span class="sxs-lookup"><span data-stu-id="6b8fa-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="6b8fa-105">(Se asocia la dirección al obtener un número de teléfono en Office 365 o al transferir un número de teléfono). Al asociar el número a una ubicación de emergencia, también puede agregar un lugar para proporcionar una ubicación más exacta dentro de una ubicación física.</span><span class="sxs-lookup"><span data-stu-id="6b8fa-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="6b8fa-106">Un lugar puede ser el piso, el ala del edificio u número de oficina donde se encuentra el usuario.</span><span class="sxs-lookup"><span data-stu-id="6b8fa-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="6b8fa-107">Puede tener un número ilimitado de lugares para una ubicación de emergencia determinada y puede cambiar el lugar si el usuario se mueve a otra oficina o edificio.</span><span class="sxs-lookup"><span data-stu-id="6b8fa-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="6b8fa-108">Por ejemplo, si el usuario se mueve del piso 34 al piso 35.</span><span class="sxs-lookup"><span data-stu-id="6b8fa-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="6b8fa-109">Para obtener información sobre cómo obtener planes de llamadas y cuánto cuestan, consulte Teams [licencias de complementos.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="6b8fa-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="6b8fa-110">Puede asignar o cambiar el lugar de una ubicación de emergencia para un usuario en el centro de administración de Microsoft Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b8fa-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6b8fa-111">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b8fa-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6b8fa-112">En el panel de navegación izquierdo del centro Microsoft Teams de administración, haga **clic**  >  **en Teléfono números.**</span><span class="sxs-lookup"><span data-stu-id="6b8fa-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="6b8fa-113">En la **Teléfono números,** haga  clic en la pestaña Números, seleccione un número de usuario en la lista y, a continuación, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="6b8fa-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="6b8fa-114">En el **panel Editar,** en **Ubicación de emergencia**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="6b8fa-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="6b8fa-115">Para asignar un lugar, busque la ubicación o el lugar y, a continuación, seleccione el lugar en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6b8fa-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="6b8fa-116">Para cambiar el lugar que ya está asignado al usuario, haga clic en **X** para quitar la ubicación y el lugar existentes, busque y seleccione el lugar que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="6b8fa-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="6b8fa-117">Dependiendo de si desea enviar un correo electrónico al usuario con su información de número de teléfono, desactive o active Usuario de correo electrónico con información **de número de teléfono.**</span><span class="sxs-lookup"><span data-stu-id="6b8fa-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="6b8fa-118">De forma predeterminada, está en.</span><span class="sxs-lookup"><span data-stu-id="6b8fa-118">By default, this is on.</span></span>

5. <span data-ttu-id="6b8fa-119">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6b8fa-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="6b8fa-120">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b8fa-120">Using PowerShell</span></span>

<span data-ttu-id="6b8fa-121">Vea [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="6b8fa-121">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="6b8fa-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6b8fa-122">Related topics</span></span>

- [<span data-ttu-id="6b8fa-123">Administrar llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="6b8fa-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="6b8fa-124">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="6b8fa-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="6b8fa-125">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="6b8fa-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="6b8fa-126">Asignar o cambiar la ubicación de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="6b8fa-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="6b8fa-127">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="6b8fa-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="6b8fa-128">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="6b8fa-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)