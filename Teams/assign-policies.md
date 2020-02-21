---
title: Asignar directivas a los usuarios en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre las diferentes formas de asignar directivas a los usuarios en Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: cb1c5fd43379388327de5e517409f01f7f52ed1b
ms.sourcegitcommit: d7be89019dd5a3b88b0840bddf1b88fea8598ea7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170766"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="af4d2-103">Asignar directivas a los usuarios en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af4d2-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="af4d2-104">**Dos de las características de Microsoft Teams descritas en este artículo, [asignación de Directiva por lotes](#assign-a-policy-to-a-batch-of-users) y [asignación de directiva a grupos](#assign-a-policy-to-a-group), actualmente están en versión preliminar.**</span><span class="sxs-lookup"><span data-stu-id="af4d2-104">**Two of the Microsoft Teams features discussed in this article, [batch policy assignment](#assign-a-policy-to-a-batch-of-users) and [policy assignment to groups](#assign-a-policy-to-a-group), are currently in preview.**</span></span>

<span data-ttu-id="af4d2-105">Como administrador, use directivas para controlar las características de teams que están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="af4d2-105">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="af4d2-106">Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por citar algunas.</span><span class="sxs-lookup"><span data-stu-id="af4d2-106">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="af4d2-107">Las organizaciones tienen diferentes tipos de usuarios con necesidades exclusivas y directivas personalizadas que usted crea y asigna le permiten adaptar la configuración de directivas a distintos conjuntos de usuarios según esas necesidades.</span><span class="sxs-lookup"><span data-stu-id="af4d2-107">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="af4d2-108">Para facilitar la administración de directivas de su organización, Teams ofrece varias formas de asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="af4d2-108">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="af4d2-109">Puede asignar una directiva directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes, o a un grupo del que el usuario sea miembro.</span><span class="sxs-lookup"><span data-stu-id="af4d2-109">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="af4d2-110">También puede usar paquetes de directivas para asignar una colección preconfigurada de directivas a los usuarios de su organización que tengan roles similares.</span><span class="sxs-lookup"><span data-stu-id="af4d2-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="af4d2-111">La opción que elija dependerá del número de directivas que esté administrando y del número de usuarios a los que va a asignar.</span><span class="sxs-lookup"><span data-stu-id="af4d2-111">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="af4d2-112">En este artículo se describen las diferentes maneras en las que puede asignar directivas a los usuarios y las situaciones recomendadas para Cuándo usarlas.</span><span class="sxs-lookup"><span data-stu-id="af4d2-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="af4d2-113">¿Qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="af4d2-113">Which policy takes precedence?</span></span>

<span data-ttu-id="af4d2-114">Un usuario tiene una directiva vigente para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="af4d2-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="af4d2-115">Es posible o incluso probable que un usuario tenga asignada directamente una directiva y también es miembro de uno o más grupos a los que se ha asignado una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="af4d2-116">En estos tipos de escenarios, ¿qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="af4d2-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="af4d2-117">La Directiva efectiva del usuario se determina según las reglas de prioridad, de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="af4d2-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="af4d2-118">Si un usuario tiene asignada directamente una directiva (ya sea de forma individual o mediante una asignación por lotes), tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="af4d2-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="af4d2-119">En el ejemplo siguiente, la Directiva efectiva del usuario es la Lincoln cuadrada de la reunión, que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="af4d2-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva asignada directamente](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="af4d2-121">Si un usuario no tiene asignada directamente una directiva de un tipo determinado, tendrá prioridad la directiva asignada a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="af4d2-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="af4d2-122">Si un usuario es miembro de varios grupos, tiene prioridad la Directiva que tiene la mayor [clasificación de asignación de grupo](#group-assignment-ranking) para el tipo de directiva determinado.</span><span class="sxs-lookup"><span data-stu-id="af4d2-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="af4d2-123">En este ejemplo, la Directiva efectiva del usuario es el equipo de ejecución y la Directiva de alta definición, que tiene la mayor clasificación de asignación relativa a otros grupos de los que el usuario es miembro y al que también se les ha asignado una directiva del mismo tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="af4d2-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama que muestra cómo tiene prioridad una directiva heredada del grupo](media/assign-policies-example-group.png)

<span data-ttu-id="af4d2-125">Si un usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario recibirá la directiva global (opción predeterminada para toda la organización) para ese tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="af4d2-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="af4d2-126">Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-126">Here's an example.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva global](media/assign-policies-example-global.png)

<span data-ttu-id="af4d2-128">Para obtener más información, vea [reglas de prioridad](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="af4d2-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="af4d2-129">Formas de asignar directivas</span><span class="sxs-lookup"><span data-stu-id="af4d2-129">Ways to assign policies</span></span>

<span data-ttu-id="af4d2-130">A continuación se ofrece una descripción general de las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno.</span><span class="sxs-lookup"><span data-stu-id="af4d2-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="af4d2-131">Haga clic en los vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="af4d2-131">Click the links to learn more.</span></span>

|<span data-ttu-id="af4d2-132">Haga esto</span><span class="sxs-lookup"><span data-stu-id="af4d2-132">Do this</span></span>  |<span data-ttu-id="af4d2-133">Si...</span><span class="sxs-lookup"><span data-stu-id="af4d2-133">If...</span></span>  | <span data-ttu-id="af4d2-134">Usar...</span><span class="sxs-lookup"><span data-stu-id="af4d2-134">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="af4d2-135">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="af4d2-135">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="af4d2-136">Ya está familiarizado con Teams y solo necesita asignar una o dos directivas a un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="af4d2-136">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="af4d2-137">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="af4d2-137">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="af4d2-138">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="af4d2-138">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="af4d2-139">Debe asignar varias directivas a conjuntos específicos de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="af4d2-139">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="af4d2-140">Por ejemplo, asigne el paquete de directivas Educación (profesor) a los profesores de su escuela para proporcionarles acceso completo a chats, llamadas y reuniones y al paquete de directivas Educación (estudiante secundario escolar) a los estudiantes secundarios para limitar ciertas capacidades como llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="af4d2-140">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="af4d2-141">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="af4d2-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="af4d2-142">[Asignar una directiva a un lote de usuarios](#assign-a-policy-to-a-batch-of-users) (en versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="af4d2-142">[Assign a policy to a batch of users](#assign-a-policy-to-a-batch-of-users) (in preview)</span></span>   | <span data-ttu-id="af4d2-143">Debe asignar directivas a grandes conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="af4d2-143">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="af4d2-144">Por ejemplo, desea asignar una directiva a cientos o miles de usuarios de su organización al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-144">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="af4d2-145">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="af4d2-145">PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="af4d2-146">[Asignar una directiva a un grupo](#assign-a-policy-to-a-group) (en versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="af4d2-146">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="af4d2-147">Debe asignar directivas en función de la pertenencia a grupos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="af4d2-147">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="af4d2-148">Por ejemplo, desea asignar una directiva a todos los usuarios de un grupo de seguridad o de una unidad de organización.</span><span class="sxs-lookup"><span data-stu-id="af4d2-148">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="af4d2-149">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="af4d2-149">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="af4d2-150">Asignar un paquete de directivas a un lote de usuarios (próximamente)</span><span class="sxs-lookup"><span data-stu-id="af4d2-150">Assign a policy package to a batch of users (coming soon)</span></span> |||
| <span data-ttu-id="af4d2-151">Asignar un paquete de directivas a un grupo (próximamente)</span><span class="sxs-lookup"><span data-stu-id="af4d2-151">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="af4d2-152">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="af4d2-152">Assign a policy to individual users</span></span>

<span data-ttu-id="af4d2-153">Siga estos pasos para asignar una directiva a un usuario individual o a un número reducido de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="af4d2-153">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="af4d2-154">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af4d2-154">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="af4d2-155">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="af4d2-155">To assign a policy to a user:</span></span>

1. <span data-ttu-id="af4d2-156">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="af4d2-156">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="af4d2-157">Seleccione el usuario haciendo clic a la izquierda del nombre de usuario y, a continuación, haga clic en **Editar configuración**.</span><span class="sxs-lookup"><span data-stu-id="af4d2-157">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="af4d2-158">Seleccione la Directiva que desea asignar y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="af4d2-158">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="af4d2-159">Para asignar una directiva a un máximo de 20 usuarios a la vez, vea [editar la configuración de usuario de Teams en masa](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="af4d2-159">To assign a policy to up to 20 users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="af4d2-160">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af4d2-160">Or, you can also do the following:</span></span>

1. <span data-ttu-id="af4d2-161">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="af4d2-161">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="af4d2-162">Seleccione la Directiva que desea asignar haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="af4d2-162">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="af4d2-163">Seleccione **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="af4d2-163">Select **Manage users**.</span></span>
4. <span data-ttu-id="af4d2-164">En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="af4d2-164">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="af4d2-165">Repita este paso para cada usuario que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="af4d2-165">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="af4d2-166">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="af4d2-166">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="af4d2-167">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="af4d2-167">Using PowerShell</span></span>

<span data-ttu-id="af4d2-168">Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-168">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="af4d2-169">Use el ```Grant-``` cmdlet para un tipo de directiva determinado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="af4d2-169">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="af4d2-170">Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una política de reunión de Teams a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="af4d2-170">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="af4d2-171">Estos cmdlets están incluidos en el módulo de PowerShell de Skype empresarial online y están documentados en la [Referencia del cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="af4d2-171">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="af4d2-172">Descargue e instale el [módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si todavía no lo ha hecho) y, a continuación, ejecute lo siguiente para conectarse a Skype empresarial online e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="af4d2-172">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="af4d2-173">En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiantes a un usuario denominado Reda.</span><span class="sxs-lookup"><span data-stu-id="af4d2-173">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="af4d2-174">Para obtener más información, vea [Administrar directivas mediante PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="af4d2-174">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="af4d2-175">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="af4d2-175">Assign a policy package</span></span>

<span data-ttu-id="af4d2-176">Un paquete de directivas de Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles iguales o similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="af4d2-176">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="af4d2-177">Cada paquete de directivas está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten actividades típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="af4d2-177">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="af4d2-178">Algunos ejemplos de paquetes de directivas son el paquete educativo (profesor) y el paquete de salud (trabajador clínico).</span><span class="sxs-lookup"><span data-stu-id="af4d2-178">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="af4d2-179">Cuando se asigna un paquete de directivas a los usuarios, se crean las directivas del paquete y, después, se puede personalizar la configuración de cada Directiva del paquete para satisfacer las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="af4d2-179">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="af4d2-180">Para obtener más información sobre los paquetes de directivas, incluidas las instrucciones paso a paso sobre cómo asignarlos y administrarlos, consulte [administrar paquetes de directivas en Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="af4d2-180">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="af4d2-181">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="af4d2-181">Assign a policy to a batch of users</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]
 
<span data-ttu-id="af4d2-182">Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="af4d2-182">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="af4d2-183">Use el ```New-CsBatchPolicyAssignmentOperationd``` cmdlet para enviar un lote de usuarios y la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="af4d2-183">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="af4d2-184">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="af4d2-184">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="af4d2-185">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="af4d2-185">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="af4d2-186">Un lote puede contener hasta 20.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="af4d2-186">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="af4d2-187">Puede especificar los usuarios por el identificador de objeto, el nombre principal de usuario (UPN), la dirección del Protocolo de inicio de sesión (SIP) o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="af4d2-187">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="af4d2-188">Actualmente, la asignación de directivas por lotes no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="af4d2-188">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="af4d2-189">Vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="af4d2-189">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="af4d2-190">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af4d2-190">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="af4d2-191">Los cmdlets se encuentran en la versión preliminar del módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="af4d2-191">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="af4d2-192">Siga estos pasos para desinstalar primero la versión disponible general del módulo de PowerShell de Teams (si está instalada) y, a continuación, instale la última versión preliminar del módulo de la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af4d2-192">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="af4d2-193">Si todavía no lo ha hecho, ejecute lo siguiente para registrar la galería de pruebas de PowerShell como fuente de confianza.</span><span class="sxs-lookup"><span data-stu-id="af4d2-193">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="af4d2-194">Si tiene instalada la versión general del módulo de PowerShell de Teams, ejecute lo siguiente para desinstalarla.</span><span class="sxs-lookup"><span data-stu-id="af4d2-194">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="af4d2-195">Ejecute lo siguiente para instalar el módulo de PowerShell más reciente de Microsoft Teams desde la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af4d2-195">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="af4d2-196">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="af4d2-196">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="af4d2-197">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="af4d2-197">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="af4d2-198">Instalar y conectarse al módulo de Azure AD PowerShell for Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="af4d2-198">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="af4d2-199">Es posible que también desee [Descargar e instalar el módulo Azure ad PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (si todavía no lo ha hecho) y conectarse a Azure ad para poder recuperar una lista de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="af4d2-199">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="af4d2-200">Ejecute lo siguiente para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="af4d2-200">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="af4d2-201">Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a teams.</span><span class="sxs-lookup"><span data-stu-id="af4d2-201">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="af4d2-202">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="af4d2-202">Assign a policy to a batch of users</span></span>

<span data-ttu-id="af4d2-203">En este ejemplo, usamos el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para asignar una directiva de configuración de aplicación denominada Directiva de configuración de la aplicación de RRHH a un lote de usuarios que aparece en el archivo Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="af4d2-203">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="af4d2-204">En este ejemplo, se conectará a Azure AD para recuperar una colección de usuarios y, a continuación, asignar una directiva de mensajería llamada nueva Directiva de mensajería de contratación a un lote de usuarios especificado mediante los UPN.</span><span class="sxs-lookup"><span data-stu-id="af4d2-204">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="af4d2-205">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="af4d2-205">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="af4d2-206">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="af4d2-206">Get the status of a batch assignment</span></span>

<span data-ttu-id="af4d2-207">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto ```New-CsBatchPolicyAssignmentOperation``` por el cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="af4d2-207">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="af4d2-208">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que ```UserState``` están en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="af4d2-208">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="af4d2-209">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="af4d2-209">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="af4d2-210">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="af4d2-210">Assign a policy to a group</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="af4d2-211">La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="af4d2-211">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="af4d2-212">La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="af4d2-212">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="af4d2-213">A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda.</span><span class="sxs-lookup"><span data-stu-id="af4d2-213">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="af4d2-214">Use el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-214">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="af4d2-215">Puede especificar un grupo mediante el identificador de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="af4d2-215">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="af4d2-216">Al asignar la Directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-216">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="af4d2-217">Sin embargo, ten en cuenta que la propagación de la asignación de directiva a miembros del grupo se realiza como una operación en segundo plano y puede llevar algún tiempo, según el tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-217">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="af4d2-218">Lo mismo sucede cuando se elimina la asignación de una directiva de un grupo, o cuando se agregan miembros a un grupo o se quitan de él.</span><span class="sxs-lookup"><span data-stu-id="af4d2-218">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="af4d2-219">Por el momento, la asignación de directivas a grupos no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="af4d2-219">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="af4d2-220">Vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="af4d2-220">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="af4d2-221">Lo que debe saber sobre la asignación de directivas a grupos</span><span class="sxs-lookup"><span data-stu-id="af4d2-221">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="af4d2-222">Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-222">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="af4d2-223">Reglas de prioridad</span><span class="sxs-lookup"><span data-stu-id="af4d2-223">Precedence rules</span></span>

<span data-ttu-id="af4d2-224">Para un tipo de directiva determinado, la Directiva efectiva del usuario se determina de acuerdo con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af4d2-224">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="af4d2-225">Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo que esté asignada a un grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-225">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="af4d2-226">En otras palabras, si un usuario tiene asignada directamente una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-226">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="af4d2-227">Esto también significa que si un usuario tiene una directiva de un determinado tipo que se le asignó directamente, tendrá que quitar esa Directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-227">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="af4d2-228">Si un usuario no tiene una directiva asignada directamente y es miembro de dos o más grupos y cada grupo tiene una directiva del mismo tipo que tiene asignada, el usuario hereda la Directiva de la asignación de grupo que tiene la clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="af4d2-228">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="af4d2-229">Si un usuario no es miembro de ningún grupo al que se le ha asignado una directiva, la directiva global (opción predeterminada para toda la organización) para ese tipo de Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="af4d2-229">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="af4d2-230">La Directiva efectiva de un usuario se actualiza de acuerdo con estas reglas cuando se agrega o se quita un usuario de un grupo al que se asigna una directiva, se elimina la asignación de una directiva de un grupo o se quita una directiva que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="af4d2-230">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="af4d2-231">Clasificación de asignación de grupo</span><span class="sxs-lookup"><span data-stu-id="af4d2-231">Group assignment ranking</span></span>
 
<span data-ttu-id="af4d2-232">Cuando se asigna una directiva a un grupo, se especifica una clasificación para la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-232">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="af4d2-233">Se usa para determinar qué directiva debe heredar un usuario como su Directiva efectiva si el usuario es miembro de dos o más grupos y se le asigna una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-233">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="af4d2-234">La clasificación de la asignación de grupo es relativa a otras asignaciones de grupo del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-234">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="af4d2-235">Por ejemplo, si va a asignar una directiva de llamadas a dos grupos, establezca la jerarquía de una asignación en 1 y la otra en 2, siendo 1 el ranking más alto.</span><span class="sxs-lookup"><span data-stu-id="af4d2-235">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="af4d2-236">La clasificación de la asignación de grupo indica qué pertenencia de grupo es más importante o más relevante que otras pertenencias a grupos en relación con la herencia.</span><span class="sxs-lookup"><span data-stu-id="af4d2-236">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="af4d2-237">Por ejemplo, supongamos que tiene dos grupos, guarda empleados y administradores de la tienda.</span><span class="sxs-lookup"><span data-stu-id="af4d2-237">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="af4d2-238">Ambos grupos tienen asignada una directiva de llamadas de equipo, almacenan empleados que llaman a la Directiva de llamadas y a los jefes de tienda, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="af4d2-238">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="af4d2-239">En el caso de un administrador de tienda que esté en ambos grupos, su rol como director es más relevante que su rol como empleado, por lo que la política de llamadas que se asigna al grupo de administradores de la tienda debería tener una clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="af4d2-239">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="af4d2-240">Mesa</span><span class="sxs-lookup"><span data-stu-id="af4d2-240">Group</span></span> |<span data-ttu-id="af4d2-241">Nombre de directiva de llamadas de equipo</span><span class="sxs-lookup"><span data-stu-id="af4d2-241">Teams calling policy name</span></span>  |<span data-ttu-id="af4d2-242">Clasificación</span><span class="sxs-lookup"><span data-stu-id="af4d2-242">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="af4d2-243">Administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="af4d2-243">Store Managers</span></span>   |<span data-ttu-id="af4d2-244">Directiva de llamadas a administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="af4d2-244">Store Managers Calling Policy</span></span>         |<span data-ttu-id="af4d2-245">1</span><span class="sxs-lookup"><span data-stu-id="af4d2-245">1</span></span>|
|<span data-ttu-id="af4d2-246">Almacenar empleados</span><span class="sxs-lookup"><span data-stu-id="af4d2-246">Store Employees</span></span>    |<span data-ttu-id="af4d2-247">Almacenar la política de llamadas</span><span class="sxs-lookup"><span data-stu-id="af4d2-247">Store Employees Calling Policy</span></span>      |<span data-ttu-id="af4d2-248">2</span><span class="sxs-lookup"><span data-stu-id="af4d2-248">2</span></span>|

<span data-ttu-id="af4d2-249">Si no especifica una clasificación, la asignación de directiva recibe la clasificación más baja.</span><span class="sxs-lookup"><span data-stu-id="af4d2-249">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="af4d2-250">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af4d2-250">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="af4d2-251">Los cmdlets se encuentran en la versión preliminar del módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="af4d2-251">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="af4d2-252">Siga estos pasos para desinstalar primero la versión disponible general del módulo de PowerShell de Teams (si está instalada) y, a continuación, instale la última versión preliminar del módulo de la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af4d2-252">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="af4d2-253">Si todavía no lo ha hecho, ejecute lo siguiente para registrar la galería de pruebas de PowerShell como fuente de confianza.</span><span class="sxs-lookup"><span data-stu-id="af4d2-253">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="af4d2-254">Si tiene instalada la versión general del módulo de PowerShell de Teams, ejecute lo siguiente para desinstalarla.</span><span class="sxs-lookup"><span data-stu-id="af4d2-254">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="af4d2-255">Ejecute lo siguiente para instalar el módulo de PowerShell más reciente de Microsoft Teams desde la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af4d2-255">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="af4d2-256">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="af4d2-256">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="af4d2-257">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="af4d2-257">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="af4d2-258">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="af4d2-258">Assign a policy to a group</span></span>

<span data-ttu-id="af4d2-259">En este ejemplo, usamos el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva de reunión de Teams denominada Directiva de reunión de directores minoristas a un grupo con una clasificación de asignación de 1.</span><span class="sxs-lookup"><span data-stu-id="af4d2-259">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="af4d2-260">Para obtener más información, vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="af4d2-260">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="af4d2-261">Obtener asignaciones de directivas para un grupo</span><span class="sxs-lookup"><span data-stu-id="af4d2-261">Get policy assignments for a group</span></span>

<span data-ttu-id="af4d2-262">Use el ```Get-CsGroupPolicyAssignment``` cmdlet para obtener todas las directivas asignadas a un grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-262">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="af4d2-263">Ten en cuenta que los grupos siempre aparecen en la lista por su identificador de grupo aunque su dirección SIP o dirección de correo electrónico se hayan usado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="af4d2-263">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="af4d2-264">En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="af4d2-264">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="af4d2-265">En este ejemplo, se devuelven todos los grupos que tienen asignada una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="af4d2-265">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="af4d2-266">Para obtener más información, vea [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="af4d2-266">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="af4d2-267">Quitar una directiva de un grupo</span><span class="sxs-lookup"><span data-stu-id="af4d2-267">Remove a policy from a group</span></span>

<span data-ttu-id="af4d2-268">Use el ```Remove-CsGroupPolicyAssignment``` cmdlet para quitar una directiva de un grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-268">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="af4d2-269">Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y con una clasificación menor.</span><span class="sxs-lookup"><span data-stu-id="af4d2-269">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="af4d2-270">Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tengan una jerarquía de 3 y 4 se actualizarán para reflejar su nueva clasificación.</span><span class="sxs-lookup"><span data-stu-id="af4d2-270">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="af4d2-271">En las dos tablas siguientes se muestra este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-271">The following two tables show this example.</span></span>

<span data-ttu-id="af4d2-272">A continuación se ofrece una lista de las asignaciones de directivas y las prioridades de una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="af4d2-272">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="af4d2-273">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="af4d2-273">Group name</span></span>  |<span data-ttu-id="af4d2-274">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="af4d2-274">Policy name</span></span>  |<span data-ttu-id="af4d2-275">Clasificación</span><span class="sxs-lookup"><span data-stu-id="af4d2-275">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="af4d2-276">Ventas</span><span class="sxs-lookup"><span data-stu-id="af4d2-276">Sales</span></span>    |<span data-ttu-id="af4d2-277">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="af4d2-277">Sales policy</span></span>       | <span data-ttu-id="af4d2-278">1</span><span class="sxs-lookup"><span data-stu-id="af4d2-278">1</span></span>        |
|<span data-ttu-id="af4d2-279">Región occidental</span><span class="sxs-lookup"><span data-stu-id="af4d2-279">West Region</span></span>     |<span data-ttu-id="af4d2-280">Política de la región occidental</span><span class="sxs-lookup"><span data-stu-id="af4d2-280">West Region policy</span></span>         |<span data-ttu-id="af4d2-281">2</span><span class="sxs-lookup"><span data-stu-id="af4d2-281">2</span></span>         |
|<span data-ttu-id="af4d2-282">Departamentos</span><span class="sxs-lookup"><span data-stu-id="af4d2-282">Division</span></span>    |<span data-ttu-id="af4d2-283">Política de división</span><span class="sxs-lookup"><span data-stu-id="af4d2-283">Division policy</span></span>         |<span data-ttu-id="af4d2-284">3</span><span class="sxs-lookup"><span data-stu-id="af4d2-284">3</span></span>         |
|<span data-ttu-id="af4d2-285">Secundaria</span><span class="sxs-lookup"><span data-stu-id="af4d2-285">Subsidiary</span></span>   |<span data-ttu-id="af4d2-286">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="af4d2-286">Subsidiary policy</span></span>        |<span data-ttu-id="af4d2-287">4</span><span class="sxs-lookup"><span data-stu-id="af4d2-287">4</span></span>         |

<span data-ttu-id="af4d2-288">Si quitamos la política de región occidental del grupo región oeste, las asignaciones y prioridades de directivas se actualizan de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="af4d2-288">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="af4d2-289">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="af4d2-289">Group name</span></span>  |<span data-ttu-id="af4d2-290">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="af4d2-290">Policy name</span></span>  |<span data-ttu-id="af4d2-291">Clasificación</span><span class="sxs-lookup"><span data-stu-id="af4d2-291">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="af4d2-292">Ventas</span><span class="sxs-lookup"><span data-stu-id="af4d2-292">Sales</span></span>    |<span data-ttu-id="af4d2-293">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="af4d2-293">Sales policy</span></span>       | <span data-ttu-id="af4d2-294">1</span><span class="sxs-lookup"><span data-stu-id="af4d2-294">1</span></span>        |
|<span data-ttu-id="af4d2-295">Departamentos</span><span class="sxs-lookup"><span data-stu-id="af4d2-295">Division</span></span>    |<span data-ttu-id="af4d2-296">Política de división</span><span class="sxs-lookup"><span data-stu-id="af4d2-296">Division policy</span></span>         |<span data-ttu-id="af4d2-297">2</span><span class="sxs-lookup"><span data-stu-id="af4d2-297">2</span></span>         |
|<span data-ttu-id="af4d2-298">Secundaria</span><span class="sxs-lookup"><span data-stu-id="af4d2-298">Subsidiary</span></span>   |<span data-ttu-id="af4d2-299">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="af4d2-299">Subsidiary policy</span></span>        |<span data-ttu-id="af4d2-300">3</span><span class="sxs-lookup"><span data-stu-id="af4d2-300">3</span></span>        |

<span data-ttu-id="af4d2-301">En este ejemplo, quitamos la política de reuniones de Teams de un grupo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-301">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="af4d2-302">Para obtener más información, consulte [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="af4d2-302">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="af4d2-303">Cambiar una asignación de directiva para un grupo</span><span class="sxs-lookup"><span data-stu-id="af4d2-303">Change a policy assignment for a group</span></span>

<span data-ttu-id="af4d2-304">Después de asignar una directiva a un grupo, puede usar el cmdlet ```Set-CsGroupPolicyAssignmentd``` para cambiar la asignación de directivas del grupo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="af4d2-304">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="af4d2-305">Cambiar la clasificación</span><span class="sxs-lookup"><span data-stu-id="af4d2-305">Change the ranking</span></span>
- <span data-ttu-id="af4d2-306">Cambiar la Directiva de un tipo de directiva determinado</span><span class="sxs-lookup"><span data-stu-id="af4d2-306">Change the policy of a given policy type</span></span>
- <span data-ttu-id="af4d2-307">Cambiar la Directiva de un determinado tipo de directiva y la clasificación</span><span class="sxs-lookup"><span data-stu-id="af4d2-307">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="af4d2-308">En este ejemplo, cambiamos la Directiva de los equipos de un grupo a una directiva llamada SupportCallPark y la clasificación de asignación a 3.</span><span class="sxs-lookup"><span data-stu-id="af4d2-308">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="af4d2-309">Para obtener más información, consulte [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="af4d2-309">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="af4d2-310">Cambiar la Directiva efectiva de un usuario</span><span class="sxs-lookup"><span data-stu-id="af4d2-310">Change the effective policy for a user</span></span>

<span data-ttu-id="af4d2-311">Este es un ejemplo de cómo cambiar la Directiva efectiva para un usuario que tiene asignada directamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="af4d2-311">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="af4d2-312">En primer lugar, usamos ```Get-CsUserPolicyAssignment``` el cmdlet junto con ```PolicySource``` el parámetro para obtener detalles de los equipos de reunión de las directivas de difusión asociados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="af4d2-312">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="af4d2-313">Para obtener más información, vea [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="af4d2-313">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="af4d2-314">En la salida se muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada eventos de empleados, que tiene prioridad sobre la Directiva denominada eventos de proveedor que se asignan a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="af4d2-314">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="af4d2-315">Ahora, quitamos la Directiva de eventos de empleados del usuario.</span><span class="sxs-lookup"><span data-stu-id="af4d2-315">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="af4d2-316">Esto significa que el usuario ya no tiene una directiva de difusión de reunión de equipos que se les asignó directamente y heredará la Directiva de eventos en vivo de proveedores que se asigna al grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="af4d2-316">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="af4d2-317">Use el siguiente cmdlet en el módulo de PowerShell de Skype empresarial para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="af4d2-317">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="af4d2-318">Puede usar el siguiente cmdlet en el módulo de PowerShell de Teams para hacerlo a escala mediante una asignación de Directiva por lotes, donde $users es una lista de los usuarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="af4d2-318">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a><span data-ttu-id="af4d2-319">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="af4d2-319">Related topics</span></span>

- [<span data-ttu-id="af4d2-320">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="af4d2-320">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)