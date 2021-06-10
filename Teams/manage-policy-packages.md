---
title: Administrar paquetes de directivas en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar paquetes de directivas en Microsoft Teams simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios.
ms.openlocfilehash: 63900f301a8b3a48a8c17c6278808cd52e2445da
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52810171"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="f2615-103">Administrar paquetes de directivas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2615-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="f2615-104">Un paquete de directivas en Microsoft Teams es una colección de directivas y configuraciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en la organización.</span><span class="sxs-lookup"><span data-stu-id="f2615-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="f2615-105">Hemos creado paquetes de directivas para simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="f2615-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="f2615-106">Puede usar los [paquetes de directiva incluidos en Teams](#policy-packages-included-in-teams) o [crear sus propios paquetes de directiva personalizados.](#custom-policy-packages)</span><span class="sxs-lookup"><span data-stu-id="f2615-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Captura de pantalla de la página Paquetes de directivas en el Centro de administración":::

<span data-ttu-id="f2615-108">Puede personalizar la configuración de las directivas de un paquete de directivas para adaptarla a las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f2615-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="f2615-109">Al cambiar la configuración de directivas de un paquete, todos los usuarios que están asignados a ese paquete obtienen la configuración actualizada.</span><span class="sxs-lookup"><span data-stu-id="f2615-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="f2615-110">Puede administrar paquetes de directivas mediante el centro Microsoft Teams de administración o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2615-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="f2615-111">Cada usuario necesitará el complemento de Comunicaciones avanzadas para recibir una tarea de paquete personalizado de directiva.</span><span class="sxs-lookup"><span data-stu-id="f2615-111">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="f2615-112">Para más información, consulte [Complemento de Comunicaciones avanzadas para Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span><span class="sxs-lookup"><span data-stu-id="f2615-112">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="f2615-113">¿Qué es un paquete de directivas?</span><span class="sxs-lookup"><span data-stu-id="f2615-113">What is a policy package?</span></span>

<span data-ttu-id="f2615-114">Los paquetes de directivas le permiten controlar Teams características que desea permitir o restringir para conjuntos específicos de personas de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="f2615-114">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="f2615-115">Cada paquete de directivas de Teams está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten las actividades de colaboración y comunicación que son típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="f2615-115">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="f2615-116">Los paquetes de directiva admiten los siguientes Teams de directiva:</span><span class="sxs-lookup"><span data-stu-id="f2615-116">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="f2615-117">Directiva de mensajería</span><span class="sxs-lookup"><span data-stu-id="f2615-117">Messaging policy</span></span>
- <span data-ttu-id="f2615-118">Directiva de reuniones</span><span class="sxs-lookup"><span data-stu-id="f2615-118">Meeting policy</span></span>
- <span data-ttu-id="f2615-119">Directiva de configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f2615-119">App setup policy</span></span>
- <span data-ttu-id="f2615-120">Directiva de llamadas</span><span class="sxs-lookup"><span data-stu-id="f2615-120">Calling policy</span></span>
- <span data-ttu-id="f2615-121">Directiva de eventos en directo</span><span class="sxs-lookup"><span data-stu-id="f2615-121">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="f2615-122">Paquetes de directiva incluidos en Teams</span><span class="sxs-lookup"><span data-stu-id="f2615-122">Policy packages included in Teams</span></span>

<span data-ttu-id="f2615-123">Teams incluye actualmente los siguientes paquetes de directivas.</span><span class="sxs-lookup"><span data-stu-id="f2615-123">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="f2615-124">Nombre del paquete</span><span class="sxs-lookup"><span data-stu-id="f2615-124">Package name</span></span> | <span data-ttu-id="f2615-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2615-125">Description</span></span> |
|---------|---------|
|<span data-ttu-id="f2615-126">Educación (estudiante de educación superior)</span><span class="sxs-lookup"><span data-stu-id="f2615-126">Education (Higher education student)</span></span>    |<span data-ttu-id="f2615-127">Crea un conjunto de directivas y configuraciones de directivas que se aplican a los estudiantes de educación superior.</span><span class="sxs-lookup"><span data-stu-id="f2615-127">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="f2615-128">Educación (alumno de la escuela primaria)</span><span class="sxs-lookup"><span data-stu-id="f2615-128">Education (Primary school student)</span></span>   |<span data-ttu-id="f2615-129">Crea un conjunto de directivas y configuraciones de directiva que se aplican a los alumnos de primaria.</span><span class="sxs-lookup"><span data-stu-id="f2615-129">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="f2615-130">Educación (estudiante de secundaria)</span><span class="sxs-lookup"><span data-stu-id="f2615-130">Education (Secondary school student)</span></span>    |<span data-ttu-id="f2615-131">Crea un conjunto de directivas y configuraciones de directiva que se aplican a los alumnos secundarios.</span><span class="sxs-lookup"><span data-stu-id="f2615-131">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="f2615-132">Educación (profesor)</span><span class="sxs-lookup"><span data-stu-id="f2615-132">Education (Teacher)</span></span>    |<span data-ttu-id="f2615-133">Crea un conjunto de directivas y configuraciones de directiva que se aplican a los profesores.</span><span class="sxs-lookup"><span data-stu-id="f2615-133">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="f2615-134">Educación (profesor de escuela primaria que usa el aprendizaje remoto)</span><span class="sxs-lookup"><span data-stu-id="f2615-134">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="f2615-135">Crea un conjunto de directivas que se aplican a los profesores de primaria para maximizar la seguridad y colaboración de los alumnos al usar la formación remota.</span><span class="sxs-lookup"><span data-stu-id="f2615-135">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="f2615-136">Educación (alumno de la escuela primaria que usa el aprendizaje remoto)</span><span class="sxs-lookup"><span data-stu-id="f2615-136">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="f2615-137">Crea un conjunto de directivas que se aplican a los alumnos de primaria para maximizar la seguridad y colaboración de los alumnos al usar la formación remota.</span><span class="sxs-lookup"><span data-stu-id="f2615-137">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="f2615-138">Administrador de primera línea</span><span class="sxs-lookup"><span data-stu-id="f2615-138">Frontline manager</span></span> |<span data-ttu-id="f2615-139">Crea un conjunto de directivas y aplica esa configuración a los administradores de frontline de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2615-139">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="f2615-140">Trabajador en primera línea</span><span class="sxs-lookup"><span data-stu-id="f2615-140">Frontline worker</span></span> |<span data-ttu-id="f2615-141">Crea un conjunto de directivas y aplica esa configuración a los trabajadores de Frontline de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2615-141">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="f2615-142">Trabajador clínico de la sanidad</span><span class="sxs-lookup"><span data-stu-id="f2615-142">Healthcare clinical worker</span></span>  |<span data-ttu-id="f2615-143">Crea un conjunto de directivas y configuraciones de directivas que proporciona a los trabajadores clínicos como los profesionales clínicos registrados, las enfermeras de cargo, los médico y los trabajadores sociales acceso completo al chat, a las llamadas, a la administración de turnos y a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="f2615-143">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="f2615-144">Trabajador de la información sanitaria</span><span class="sxs-lookup"><span data-stu-id="f2615-144">Healthcare information worker</span></span>  |<span data-ttu-id="f2615-145">Crea un conjunto de directivas y configuraciones de directivas que dan a los trabajadores de la información como el personal de TI, el personal informático, el personal del departamento financiero y los responsables de cumplimiento normativo, acceso completo a chat, llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="f2615-145">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="f2615-146">Sala de pacientes de cuidado de la salud</span><span class="sxs-lookup"><span data-stu-id="f2615-146">Healthcare patient room</span></span>  |<span data-ttu-id="f2615-147">Crea un conjunto de directivas y configuraciones de directivas que se aplican a las salas de pacientes de su organización de cuidados de la salud.</span><span class="sxs-lookup"><span data-stu-id="f2615-147">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="f2615-148">Usuario de pequeñas y medianas empresas (Business Voice)</span><span class="sxs-lookup"><span data-stu-id="f2615-148">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="f2615-149">Crea una directiva de configuración de aplicaciones que incluye las aplicaciones para una experiencia de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="f2615-149">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="f2615-150">Usuario de pequeñas y medianas empresas (sin Business Voice)</span><span class="sxs-lookup"><span data-stu-id="f2615-150">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="f2615-151">Crea una directiva de configuración de aplicaciones relevante para una pequeña y mediana empresa Teams usuarios (experiencia de voz no empresarial).</span><span class="sxs-lookup"><span data-stu-id="f2615-151">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="f2615-152">Oficial de seguridad pública</span><span class="sxs-lookup"><span data-stu-id="f2615-152">Public safety officer</span></span>   |<span data-ttu-id="f2615-153">Crea un conjunto de directivas y configuraciones de directiva que se aplican a los responsables de seguridad pública de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2615-153">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="f2615-154">Agregaremos más paquetes de directiva en futuras versiones de Teams, así que vuelve a comprobar la información más actualizada.</span><span class="sxs-lookup"><span data-stu-id="f2615-154">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="f2615-155">Cada directiva individual se indica con el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="f2615-155">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="f2615-156">Por ejemplo, cuando asigna el paquete de directivas Educación (profesor) a los profesores de su centro educativo, se crea una directiva denominada Education_Teacher para cada directiva del paquete.</span><span class="sxs-lookup"><span data-stu-id="f2615-156">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Captura de pantalla del paquete de directivas educación (profesor)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="f2615-158">Paquetes de directivas personalizados</span><span class="sxs-lookup"><span data-stu-id="f2615-158">Custom policy packages</span></span>

<span data-ttu-id="f2615-159">**Los paquetes de directivas personalizados aún no están disponibles para el Government Community Cloud (GCC)**</span><span class="sxs-lookup"><span data-stu-id="f2615-159">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="f2615-160">Los paquetes de directivas personalizados le permiten agrupar su propio conjunto de directivas para usuarios con roles similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="f2615-160">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="f2615-161">Cree sus propios paquetes de directivas agregando los tipos de directiva y las directivas que necesita.</span><span class="sxs-lookup"><span data-stu-id="f2615-161">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="f2615-162">Para crear un nuevo paquete de directiva personalizada:</span><span class="sxs-lookup"><span data-stu-id="f2615-162">To create a new custom policy package:</span></span>

1. <span data-ttu-id="f2615-163">En el panel de navegación izquierdo del Microsoft Teams de administración, seleccione **Paquetes de directivas** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f2615-163">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="Captura de pantalla del botón Agregar en la página Paquetes de directiva en el Centro de administración":::

2. <span data-ttu-id="f2615-165">Escriba un nombre y una descripción para el paquete.</span><span class="sxs-lookup"><span data-stu-id="f2615-165">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Captura de pantalla de agregar un nuevo paquete de directiva personalizada":::

3. <span data-ttu-id="f2615-167">Seleccione los tipos de directiva y los nombres de directiva que desea incluir en el paquete.</span><span class="sxs-lookup"><span data-stu-id="f2615-167">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="f2615-168">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f2615-168">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="f2615-169">Cómo usar paquetes de directivas</span><span class="sxs-lookup"><span data-stu-id="f2615-169">How to use policy packages</span></span>

<span data-ttu-id="f2615-170">A continuación se describe cómo usar paquetes de directivas en su organización.</span><span class="sxs-lookup"><span data-stu-id="f2615-170">The following outlines how to use policy packages in your organization.</span></span>

![Información general sobre cómo usar paquetes de directivas](media/manage-policy-packages-overview.png)

- <span data-ttu-id="f2615-172">**[Ver:](#view-the-settings-of-a-policy-in-a-policy-package)** Ver las directivas de un paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="f2615-172">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="f2615-173">Después, vea la configuración de cada directiva de un paquete antes de asignar el paquete.</span><span class="sxs-lookup"><span data-stu-id="f2615-173">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="f2615-174">Asegúrese de que comprende cada configuración.</span><span class="sxs-lookup"><span data-stu-id="f2615-174">Make sure that you understand each setting.</span></span> <span data-ttu-id="f2615-175">Decida si los valores predefinidos son adecuados para su organización o si necesita cambiarlos para que sean más restrictivos o más indulgentes en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2615-175">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="f2615-176">Si se elimina una directiva, aún puede ver la configuración, pero no podrá cambiar ninguna configuración.</span><span class="sxs-lookup"><span data-stu-id="f2615-176">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="f2615-177">Se vuelve a crear una directiva eliminada con la configuración predefinida al asignar el paquete de directiva.</span><span class="sxs-lookup"><span data-stu-id="f2615-177">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="f2615-178">**[Personalizar:](#customize-policies-in-a-policy-package)** Personalice la configuración de directivas del paquete de directivas para que se ajuste a las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2615-178">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="f2615-179">**[Asignar:](#assign-a-policy-package)** Asigne el paquete de directiva a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f2615-179">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="f2615-180">También puede cambiar la configuración de directivas de un paquete de directiva después de asignar un paquete.</span><span class="sxs-lookup"><span data-stu-id="f2615-180">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="f2615-181">Los cambios que realice en la configuración de directivas se aplican automáticamente a los usuarios a los que se les asigna el paquete.</span><span class="sxs-lookup"><span data-stu-id="f2615-181">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="f2615-182">Estos son los pasos para ver, asignar y personalizar paquetes de directivas en el centro Microsoft Teams administración.</span><span class="sxs-lookup"><span data-stu-id="f2615-182">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="f2615-183">Ver la configuración de una directiva en un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="f2615-183">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="f2615-184">En el panel de navegación izquierdo del centro de administración de Microsoft Teams, seleccione Paquetes de directiva y, después, seleccione un paquete de directiva haciendo clic a la izquierda del nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="f2615-184">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="f2615-185">Haga clic en la directiva que desea ver.</span><span class="sxs-lookup"><span data-stu-id="f2615-185">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="f2615-186">Personalizar directivas en un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="f2615-186">Customize policies in a policy package</span></span>

<span data-ttu-id="f2615-187">Puede editar la configuración de  una directiva a través de la página Paquetes de directiva o yendo directamente a la página de directiva del centro de administración Microsoft Teams directiva.</span><span class="sxs-lookup"><span data-stu-id="f2615-187">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="f2615-188">En el panel de navegación izquierdo del Microsoft Teams de administración, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f2615-188">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="f2615-189">Haga **clic en Paquetes** de directiva y, a continuación, seleccione el paquete de directiva haciendo clic a la izquierda del nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="f2615-189">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="f2615-190">Haga clic en el tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="f2615-190">Click the policy type.</span></span>  <span data-ttu-id="f2615-191">Por ejemplo, haga clic en **Directivas de mensajería.**</span><span class="sxs-lookup"><span data-stu-id="f2615-191">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="f2615-192">Seleccione la directiva que desea editar.</span><span class="sxs-lookup"><span data-stu-id="f2615-192">Select the policy you want to edit.</span></span> <span data-ttu-id="f2615-193">Las directivas vinculadas a un paquete de directivas tienen el mismo nombre que el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="f2615-193">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="f2615-194">Realice los cambios que desee y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="f2615-194">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="f2615-195">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="f2615-195">Assign a policy package</span></span>

<span data-ttu-id="f2615-196">Puede asignar un paquete de directiva a un usuario individual, un grupo o un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f2615-196">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="f2615-197">Para obtener más información sobre cómo asignar paquetes de directiva, vea [Asignar paquetes de directiva a usuarios y grupos.](assign-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="f2615-197">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2615-198">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f2615-198">Related topics</span></span>

- [<span data-ttu-id="f2615-199">Asignar paquetes de directiva</span><span class="sxs-lookup"><span data-stu-id="f2615-199">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="f2615-200">Teams de directivas para administradores de EDU</span><span class="sxs-lookup"><span data-stu-id="f2615-200">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="f2615-201">Paquetes de directivas de Teams para sanidad</span><span class="sxs-lookup"><span data-stu-id="f2615-201">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="f2615-202">Teams paquetes de directivas para el gobierno</span><span class="sxs-lookup"><span data-stu-id="f2615-202">Teams policy packages for government</span></span>](policy-packages-gov.md)
