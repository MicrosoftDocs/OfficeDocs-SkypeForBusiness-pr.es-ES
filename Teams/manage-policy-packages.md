---
title: Administrar paquetes de directivas en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo usar y administrar paquetes de directivas en Microsoft Teams.
ms.openlocfilehash: 428e3b9d68064beb70b80603df573aa7df9e59c3
ms.sourcegitcommit: d955406a55cdc4c7abb193f1af90ebd4913c47bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/04/2019
ms.locfileid: "35542368"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="bc641-103">Administrar paquetes de directivas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc641-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="bc641-104">Un paquete de directivas de Microsoft Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="bc641-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="bc641-105">Hemos creado paquetes de directivas para simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="bc641-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="bc641-106">Cuando se asigna un paquete de directivas a los usuarios, se crean las directivas del paquete y, después, se puede personalizar la configuración de las directivas en el paquete para satisfacer las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="bc641-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="bc641-107">¿Qué es un paquete de directivas?</span><span class="sxs-lookup"><span data-stu-id="bc641-107">What is a policy package?</span></span>

<span data-ttu-id="bc641-108">Los paquetes de directivas le permiten controlar las características de teams que desea permitir o restringir a conjuntos de personas específicas de su organización.</span><span class="sxs-lookup"><span data-stu-id="bc641-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="bc641-109">Cada paquete de directivas de Teams está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten las actividades de colaboración y comunicación típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="bc641-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="bc641-110">Actualmente, Teams incluye los siguientes paquetes de directivas.</span><span class="sxs-lookup"><span data-stu-id="bc641-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="bc641-111">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="bc641-111">**Package name**</span></span>  |<span data-ttu-id="bc641-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bc641-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="bc641-113">Paquete Education_Teacher</span><span class="sxs-lookup"><span data-stu-id="bc641-113">Education_Teacher package</span></span>     |<span data-ttu-id="bc641-114">Crea un conjunto de directivas y configuraciones de directivas que se aplican a los profesores.</span><span class="sxs-lookup"><span data-stu-id="bc641-114">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="bc641-115">Paquete Education_PrimaryStudent</span><span class="sxs-lookup"><span data-stu-id="bc641-115">Education_PrimaryStudent package</span></span>    |<span data-ttu-id="bc641-116">Crea un conjunto de directivas y opciones de directiva que se aplican a los alumnos principales.</span><span class="sxs-lookup"><span data-stu-id="bc641-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="bc641-117">Paquete Education_SecondaryStudent</span><span class="sxs-lookup"><span data-stu-id="bc641-117">Education_SecondaryStudent package</span></span>    |<span data-ttu-id="bc641-118">Crea un conjunto de directivas y opciones de directiva que se aplican a los alumnos secundarios.</span><span class="sxs-lookup"><span data-stu-id="bc641-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="bc641-119">Paquete Education_HigherEducationStudent</span><span class="sxs-lookup"><span data-stu-id="bc641-119">Education_HigherEducationStudent package</span></span>    |<span data-ttu-id="bc641-120">Crea un conjunto de directivas y opciones de directiva que se aplican a estudiantes de educación superior.</span><span class="sxs-lookup"><span data-stu-id="bc641-120">Creates a set of policies and policy settings that apply to higher education students.</span></span>|

> [!NOTE]
> <span data-ttu-id="bc641-121">Agregaremos más paquetes de directivas en versiones futuras de Teams, así que vuelve a consultar la información más actualizada.</span><span class="sxs-lookup"><span data-stu-id="bc641-121">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="bc641-122">A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="bc641-122">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="bc641-123">Por ejemplo, al asignar el paquete de directivas Education_Teacher a los profesores de su escuela, se crea una directiva denominada Education_Teacher para cada Directiva del paquete.</span><span class="sxs-lookup"><span data-stu-id="bc641-123">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Captura de pantalla del paquete de directivas Education_Teacher](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="bc641-125">Cómo usar paquetes de directivas</span><span class="sxs-lookup"><span data-stu-id="bc641-125">How to use policy packages</span></span>

<span data-ttu-id="bc641-126">A continuación se describe cómo usar paquetes de directivas en su organización.</span><span class="sxs-lookup"><span data-stu-id="bc641-126">The following outlines how to use policy packages in your organization.</span></span>

![Información general sobre cómo usar paquetes de directivas](media/manage-policy-packages-overview.png)

- <span data-ttu-id="bc641-128">**[Ver](#view-the-settings-of-a-policy-in-a-policy-package)**: ver la configuración de cada directiva en un paquete de directivas antes de asignar un paquete.</span><span class="sxs-lookup"><span data-stu-id="bc641-128">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="bc641-129">Asegúrese de comprender cada configuración y, a continuación, decida si los valores predefinidos son adecuados para su organización o si necesita cambiarlos de forma más restrictiva o flexible según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="bc641-129">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="bc641-130">Si se elimina una directiva, puede seguir viendo la configuración, pero no podrá cambiar la configuración.</span><span class="sxs-lookup"><span data-stu-id="bc641-130">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="bc641-131">Una directiva eliminada se vuelve a crear con la configuración predefinida al asignar el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="bc641-131">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="bc641-132">**[Asignar](#assign-a-policy-package)**: asignar el paquete de directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bc641-132">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="bc641-133">Recuerde que las directivas de un paquete de directivas no se crean hasta que usted asigne el paquete, después de que puede cambiar la configuración de directivas individuales en el paquete.</span><span class="sxs-lookup"><span data-stu-id="bc641-133">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="bc641-134">**[Personalizar](#customize-policies-in-a-policy-package)**: personalizar la configuración de directivas en el paquete de directivas para satisfacer las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="bc641-134">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="bc641-135">Los cambios que realice en la configuración de la Directiva se aplican automáticamente a los usuarios que tienen asignado el paquete.</span><span class="sxs-lookup"><span data-stu-id="bc641-135">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="bc641-136">Estos son los pasos para ver, asignar y personalizar paquetes de directivas en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bc641-136">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="bc641-137">Ver la configuración de una directiva en un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="bc641-137">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="bc641-138">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en **paquetes de directivas**y, a continuación, seleccione un paquete de directivas haciendo clic a la izquierda del nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="bc641-138">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="bc641-139">Haga clic en la Directiva que desea ver.</span><span class="sxs-lookup"><span data-stu-id="bc641-139">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="bc641-140">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="bc641-140">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="bc641-141">Asignar un paquete de directivas a un usuario</span><span class="sxs-lookup"><span data-stu-id="bc641-141">Assign a policy package to one user</span></span>

1. <span data-ttu-id="bc641-142">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="bc641-142">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="bc641-143">En la página del usuario, haga clic en **directivas**y, a continuación, junto a **paquete de directivas**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bc641-143">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="bc641-144">En el panel **asignar paquete de directivas** , seleccione el paquete que desea asignar y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bc641-144">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="bc641-145">Asignar un paquete de directivas a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="bc641-145">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="bc641-146">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **paquetes de directivas**y, a continuación, seleccione el paquete de directivas que desea asignar haciendo clic a la izquierda del nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="bc641-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="bc641-147">Haga clic en **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="bc641-147">Click **Manage users**.</span></span>
3. <span data-ttu-id="bc641-148">En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bc641-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="bc641-149">Repita este paso para cada usuario que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="bc641-149">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="bc641-150">Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bc641-150">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="bc641-151">Personalizar directivas en un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="bc641-151">Customize policies in a policy package</span></span>

<span data-ttu-id="bc641-152">Puede editar la configuración de una directiva a través de la página **paquetes de directivas** o yendo directamente a la página de directivas en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bc641-152">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="bc641-153">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="bc641-153">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="bc641-154">Haga clic en **paquetes de directivas**y, a continuación, seleccione el paquete de directivas haciendo clic a la izquierda del nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="bc641-154">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="bc641-155">Haga clic en el tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="bc641-155">Click the policy type.</span></span>  <span data-ttu-id="bc641-156">Por ejemplo, haga clic en **directivas de mensajería**.</span><span class="sxs-lookup"><span data-stu-id="bc641-156">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="bc641-157">Haga clic en la Directiva que desea editar.</span><span class="sxs-lookup"><span data-stu-id="bc641-157">Click the policy you want to edit.</span></span> <span data-ttu-id="bc641-158">Las directivas vinculadas a un paquete de directivas tienen el mismo nombre que el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="bc641-158">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="bc641-159">Realice los cambios que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bc641-159">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bc641-160">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="bc641-160">Troubleshooting</span></span>

<span data-ttu-id="bc641-161">**Recibe un error cuando asigna un paquete de directivas**</span><span class="sxs-lookup"><span data-stu-id="bc641-161">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="bc641-162">Esto puede ocurrir si una o más directivas del paquete no se han creado o aplicado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bc641-162">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="bc641-163">Reasigne el paquete de directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bc641-163">Reassign the policy package to your users.</span></span> <span data-ttu-id="bc641-164">El reintento de la operación normalmente soluciona este problema.</span><span class="sxs-lookup"><span data-stu-id="bc641-164">Retrying the operation typically fixes this issue.</span></span>
