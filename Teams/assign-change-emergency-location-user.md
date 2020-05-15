---
title: Asignar o cambiar la ubicación de emergencia de un usuario
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
description: En este artículo, obtendrá información sobre cómo asignar o cambiar una ubicación de emergencia para los usuarios de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 096e2dead1ede4f9769dafd85dfac23d6c44f399
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232481"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="6dc60-103">Asignar o cambiar la ubicación de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="6dc60-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="6dc60-104">Cuando configuras planes de llamadas, deberás asignar una ubicación de emergencia a cada número de teléfono o usuario.</span><span class="sxs-lookup"><span data-stu-id="6dc60-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="6dc60-105">En los países de Europa, la ubicación de emergencia está asociada con el número de teléfono cuando lo obtiene de Office 365 o cuando transfiere un número de teléfono a Office 365.</span><span class="sxs-lookup"><span data-stu-id="6dc60-105">In European countries, the emergency location is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="6dc60-106">En los Estados Unidos, la ubicación de emergencia está asociada al número de teléfono cuando se le asigna al usuario.</span><span class="sxs-lookup"><span data-stu-id="6dc60-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="6dc60-107">La dirección de emergencia se puede cambiar si el usuario al que está asignada se mueve a una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="6dc60-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="6dc60-108">Para obtener más información sobre las direcciones y ubicaciones de emergencia, consulte [Manage Emergency Call](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="6dc60-108">For more about emergency addresses and locations, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="6dc60-109">Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, vea [licencias complementarias de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="6dc60-109">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="6dc60-110">Puede asignar o cambiar una ubicación de emergencia para un usuario en el centro de administración de Microsoft Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6dc60-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6dc60-111">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6dc60-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6dc60-112">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en números de teléfono de **voz**  >  **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="6dc60-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="6dc60-113">En la página **números de teléfono** , seleccione un número de usuario en la lista y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6dc60-113">On the **Phone numbers** page, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="6dc60-114">En el panel de **edición** , en **Ubicación de emergencia**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="6dc60-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="6dc60-115">Para asignar una ubicación de emergencia, busque y seleccione una ubicación de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6dc60-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="6dc60-116">Para cambiar la ubicación de emergencia que ya está asignada al usuario, haga clic en **X** para quitar la ubicación existente y, a continuación, busque y seleccione la ubicación que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="6dc60-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="6dc60-117">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="6dc60-117">Click **Save**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="6dc60-118">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6dc60-118">Using PowerShell</span></span>

<span data-ttu-id="6dc60-119">Consulte [set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="6dc60-119">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="6dc60-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6dc60-120">Related topics</span></span>

- [<span data-ttu-id="6dc60-121">Administrar las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="6dc60-121">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="6dc60-122">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="6dc60-122">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="6dc60-123">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="6dc60-123">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="6dc60-124">Asignar o cambiar la ubicación de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="6dc60-124">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="6dc60-125">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="6dc60-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="6dc60-126">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="6dc60-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="6dc60-127">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="6dc60-127">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
