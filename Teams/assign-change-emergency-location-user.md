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
ms.openlocfilehash: f11bfd9762667823b4ec6b2883c9661f9f5754d0
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539507"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="e4b33-103">Asignar o cambiar la ubicación de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="e4b33-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="e4b33-104">Cuando configuras planes de llamadas, deberás asignar una ubicación de emergencia a cada número de teléfono o usuario.</span><span class="sxs-lookup"><span data-stu-id="e4b33-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="e4b33-105">En los países de Europa, la ubicación de emergencia está asociada con el número de teléfono cuando lo obtiene de Office 365 o cuando transfiere un número de teléfono a Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4b33-105">In European countries, the emergency location is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="e4b33-106">En los Estados Unidos, la ubicación de emergencia está asociada al número de teléfono cuando se le asigna al usuario.</span><span class="sxs-lookup"><span data-stu-id="e4b33-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="e4b33-107">La dirección de emergencia se puede cambiar si el usuario al que está asignada se mueve a una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="e4b33-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="e4b33-108">Para obtener más información sobre las direcciones y ubicaciones de emergencia, consulte [Manage Emergency Call](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e4b33-108">For more about emergency addresses and locations, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="e4b33-109">Para obtener información sobre cómo obtener un plan de llamadas y cuánto cuestan, vea [licencias complementarias de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e4b33-109">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="e4b33-110">Puede asignar o cambiar una ubicación de emergencia para un usuario en el centro de administración de Microsoft Teams o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4b33-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e4b33-111">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4b33-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e4b33-112">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en números de teléfono de **voz**  >  **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="e4b33-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="e4b33-113">En la página **números de teléfono** , haga clic en la pestaña **números** , seleccione un número de usuario en la lista y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e4b33-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="e4b33-114">En el panel de **edición** , en **Ubicación de emergencia**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e4b33-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="e4b33-115">Para asignar una ubicación de emergencia, busque y seleccione una ubicación de emergencia.</span><span class="sxs-lookup"><span data-stu-id="e4b33-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="e4b33-116">Para cambiar la ubicación de emergencia que ya está asignada al usuario, haga clic en **X** para quitar la ubicación existente y, a continuación, busque y seleccione la ubicación que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="e4b33-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="e4b33-117">En función de si desea enviar un correo electrónico al usuario con la información de su número de teléfono, desactive o Active el **usuario de correo electrónico con información sobre el número de**teléfono.</span><span class="sxs-lookup"><span data-stu-id="e4b33-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="e4b33-118">De forma predeterminada, esta opción está activada.</span><span class="sxs-lookup"><span data-stu-id="e4b33-118">By default, this is on.</span></span>

5. <span data-ttu-id="e4b33-119">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e4b33-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="e4b33-120">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4b33-120">Using PowerShell</span></span>

<span data-ttu-id="e4b33-121">Consulte [set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="e4b33-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="e4b33-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e4b33-122">Related topics</span></span>

- [<span data-ttu-id="e4b33-123">Administrar las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="e4b33-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="e4b33-124">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="e4b33-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="e4b33-125">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="e4b33-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="e4b33-126">Asignar o cambiar la ubicación de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="e4b33-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="e4b33-127">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="e4b33-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="e4b33-128">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="e4b33-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="e4b33-129">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="e4b33-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
