---
title: Paquetes de directivas de Teams para administración pública
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar paquetes de directivas de Teams para su organización gubernamental.
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804048"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="8bd2c-103">Paquetes de directivas de Teams para administración pública</span><span class="sxs-lookup"><span data-stu-id="8bd2c-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="8bd2c-104">Los paquetes de directivas actualmente no están disponibles en las implementaciones de Microsoft 365 gubernamentales GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="8bd2c-105">Información general</span><span class="sxs-lookup"><span data-stu-id="8bd2c-105">Overview</span></span>

<span data-ttu-id="8bd2c-106">Un [paquete de directivas](manage-policy-packages.md) de Microsoft Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="8bd2c-107">Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="8bd2c-108">Puede personalizar la configuración de las directivas en el paquete para satisfacer las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="8bd2c-109">Al cambiar la configuración de las directivas en un paquete de directivas, todos los usuarios asignados a ese paquete obtienen la configuración actualizada.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="8bd2c-110">Puede administrar paquetes de directivas mediante el centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="8bd2c-111">Los paquetes de directivas predefinen directivas para los siguientes elementos, según el paquete:</span><span class="sxs-lookup"><span data-stu-id="8bd2c-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="8bd2c-112">Mensajería </span><span class="sxs-lookup"><span data-stu-id="8bd2c-112">Messaging</span></span>
- <span data-ttu-id="8bd2c-113">Reuniones</span><span class="sxs-lookup"><span data-stu-id="8bd2c-113">Meetings</span></span>
- <span data-ttu-id="8bd2c-114">Llamadas</span><span class="sxs-lookup"><span data-stu-id="8bd2c-114">Calling</span></span>
- <span data-ttu-id="8bd2c-115">Configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="8bd2c-115">App setup</span></span>
- <span data-ttu-id="8bd2c-116">Eventos en directo</span><span class="sxs-lookup"><span data-stu-id="8bd2c-116">Live events</span></span>

<span data-ttu-id="8bd2c-117">Actualmente, Teams incluye los siguientes paquetes de directivas para administración pública.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="8bd2c-118">Nombre del paquete en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bd2c-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="8bd2c-119">Recomendado para</span><span class="sxs-lookup"><span data-stu-id="8bd2c-119">Best used for</span></span>|<span data-ttu-id="8bd2c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bd2c-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="8bd2c-121">Funcionario de seguridad pública</span><span class="sxs-lookup"><span data-stu-id="8bd2c-121">Public safety officer</span></span>  |<span data-ttu-id="8bd2c-122">Funcionarios de seguridad pública de su organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="8bd2c-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="8bd2c-123">Crea un conjunto de directivas y parámetros de directivas que se aplican a los directores de seguridad pública de su organización.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="8bd2c-124">Los Firstline Manager</span><span class="sxs-lookup"><span data-stu-id="8bd2c-124">Firstline manager</span></span>  |<span data-ttu-id="8bd2c-125">Los Firstline managers en su organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="8bd2c-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="8bd2c-126">Crea un conjunto de directivas y aplica esta configuración a los administradores de los Firstline de su organización.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="8bd2c-127">Trabajador de los Firstline</span><span class="sxs-lookup"><span data-stu-id="8bd2c-127">Firstline worker</span></span>  |<span data-ttu-id="8bd2c-128">Trabajadores de los Firstline en su organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="8bd2c-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="8bd2c-129">Crea un conjunto de directivas y aplica esta configuración a los trabajadores de los Firstline de su organización.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Captura de pantalla de paquetes de política sanitaria](media/policy-packages-gov.png)

<span data-ttu-id="8bd2c-131">A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="8bd2c-132">Por ejemplo, cuando se asigna el paquete de directiva del oficial de seguridad pública a los usuarios de su organización, se crea una directiva denominada PublicSafety_Officer para cada Directiva del paquete.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Captura de pantalla de directivas en el paquete de trabajadores clínico de cuidado de la salud](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="8bd2c-134">Administrar los paquetes de directivas </span><span class="sxs-lookup"><span data-stu-id="8bd2c-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="8bd2c-135">Ver</span><span class="sxs-lookup"><span data-stu-id="8bd2c-135">View</span></span>

<span data-ttu-id="8bd2c-136">Vea la configuración de cada directiva en un paquete de directivas antes de asignar un paquete.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="8bd2c-137">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **paquetes de directivas**, seleccione el nombre del paquete y, a continuación, seleccione el nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="8bd2c-138">Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="8bd2c-139">Personalizar</span><span class="sxs-lookup"><span data-stu-id="8bd2c-139">Customize</span></span>

<span data-ttu-id="8bd2c-140">Personalice la configuración de las directivas en el paquete de directivas según sea necesario para adaptarse a las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="8bd2c-141">Los cambios que realice en la configuración de la Directiva se aplican automáticamente a los usuarios que tienen asignado el paquete.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="8bd2c-142">Para editar la configuración de una directiva en un paquete de directivas, en el centro de administración de Microsoft Teams, seleccione el paquete de directivas, seleccione el nombre de la Directiva que desea editar y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="8bd2c-143">Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="8bd2c-144">Para obtener más información, consulte [personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="8bd2c-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="8bd2c-145">Asignar</span><span class="sxs-lookup"><span data-stu-id="8bd2c-145">Assign</span></span>

<span data-ttu-id="8bd2c-146">Asignar el paquete de directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-146">Assign the policy package to users.</span></span> <span data-ttu-id="8bd2c-147">Para asignar un paquete de directivas a uno o varios usuarios, haga clic en **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="8bd2c-148">También puede [usar PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para asignar un paquete de directivas a lotes grandes de usuarios.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-148">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="8bd2c-149">Para conocer los pasos sobre cómo asignar un paquete de directivas mediante el centro de administración de Microsoft Teams o PowerShell, consulte [asignar un paquete de directivas](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="8bd2c-149">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Captura de pantalla de cómo asignar un paquete de directivas en el centro de administración](media/policy-packages-gov-assign.png)

<span data-ttu-id="8bd2c-151">Si un usuario tiene asignada una directiva y posteriormente asigna otra, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8bd2c-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8bd2c-152">Related topics</span></span>

[<span data-ttu-id="8bd2c-153">Administrar los paquetes de directivas para Teams</span><span class="sxs-lookup"><span data-stu-id="8bd2c-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="8bd2c-154">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="8bd2c-154">Assign policies to your users in Teams</span></span>](assign-policies.md) 
