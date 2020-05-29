---
title: Asignar directivas a los usuarios de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: ae007641734b71a34d9021283704d6b210626a28
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410465"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="939d2-103">Asignar directivas a los usuarios de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="939d2-104">**Una de las características de Microsoft Teams descritas en este artículo, [asignación de directiva a grupos](#assign-a-policy-to-a-group), solo está disponible actualmente en la versión preliminar privada. Los cmdlets de PowerShell para esta característica se encuentran en el módulo PowerShell de la versión preliminar de Teams.**</span><span class="sxs-lookup"><span data-stu-id="939d2-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in private preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span> <span data-ttu-id="939d2-105">Para estar al día del estado de versión de esta característica, consulte la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="939d2-105">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="939d2-106">Como administrador, use directivas para controlar las características de teams que están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="939d2-106">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="939d2-107">Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por citar algunas.</span><span class="sxs-lookup"><span data-stu-id="939d2-107">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="939d2-108">Las organizaciones tienen diferentes tipos de usuarios con necesidades exclusivas y directivas personalizadas que usted crea y asigna le permiten adaptar la configuración de directivas a distintos conjuntos de usuarios según esas necesidades.</span><span class="sxs-lookup"><span data-stu-id="939d2-108">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="939d2-109">Para facilitar la administración de directivas de su organización, Teams ofrece varias formas de asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="939d2-109">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="939d2-110">Puede asignar una directiva directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes, o a un grupo del que el usuario sea miembro.</span><span class="sxs-lookup"><span data-stu-id="939d2-110">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="939d2-111">También puede usar paquetes de directivas para asignar una colección preconfigurada de directivas a los usuarios de su organización que tengan roles similares.</span><span class="sxs-lookup"><span data-stu-id="939d2-111">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="939d2-112">La opción que elija dependerá del número de directivas que esté administrando y del número de usuarios a los que va a asignar.</span><span class="sxs-lookup"><span data-stu-id="939d2-112">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="939d2-113">En este artículo se describen las diferentes maneras en las que puede asignar directivas a los usuarios y las situaciones recomendadas para Cuándo usarlas.</span><span class="sxs-lookup"><span data-stu-id="939d2-113">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="939d2-114">¿Qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="939d2-114">Which policy takes precedence?</span></span>

<span data-ttu-id="939d2-115">Un usuario tiene una directiva vigente para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="939d2-115">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="939d2-116">Es posible o incluso probable que un usuario tenga asignada directamente una directiva y también es miembro de uno o más grupos a los que se ha asignado una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="939d2-116">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="939d2-117">En estos tipos de escenarios, ¿qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="939d2-117">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="939d2-118">La Directiva efectiva del usuario se determina según las reglas de prioridad, de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="939d2-118">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="939d2-119">Si un usuario tiene asignada directamente una directiva (ya sea de forma individual o mediante una asignación por lotes), tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="939d2-119">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="939d2-120">En el ejemplo siguiente, la Directiva efectiva del usuario es la Lincoln cuadrada de la reunión, que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="939d2-120">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva asignada directamente](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="939d2-122">Si un usuario no tiene asignada directamente una directiva de un tipo determinado, tendrá prioridad la directiva asignada a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="939d2-122">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="939d2-123">Si un usuario es miembro de varios grupos, tiene prioridad la Directiva que tiene la mayor [clasificación de asignación de grupo](#group-assignment-ranking) para el tipo de directiva determinado.</span><span class="sxs-lookup"><span data-stu-id="939d2-123">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="939d2-124">En este ejemplo, la Directiva efectiva del usuario es el equipo de ejecución y la Directiva de alta definición, que tiene la mayor clasificación de asignación relativa a otros grupos de los que el usuario es miembro y al que también se les ha asignado una directiva del mismo tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="939d2-124">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama que muestra cómo tiene prioridad una directiva heredada del grupo](media/assign-policies-example-group.png)

<span data-ttu-id="939d2-126">Si un usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario recibirá la directiva global (opción predeterminada para toda la organización) para ese tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="939d2-126">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="939d2-127">Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="939d2-127">Here's an example.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva global](media/assign-policies-example-global.png)

<span data-ttu-id="939d2-129">Para obtener más información, vea [reglas de prioridad](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="939d2-129">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="939d2-130">Formas de asignar directivas</span><span class="sxs-lookup"><span data-stu-id="939d2-130">Ways to assign policies</span></span>

<span data-ttu-id="939d2-131">A continuación se ofrece una descripción general de las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno.</span><span class="sxs-lookup"><span data-stu-id="939d2-131">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="939d2-132">Haga clic en los vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="939d2-132">Click the links to learn more.</span></span>

|<span data-ttu-id="939d2-133">Haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="939d2-133">Do this</span></span>  |<span data-ttu-id="939d2-134">Si...</span><span class="sxs-lookup"><span data-stu-id="939d2-134">If...</span></span>  | <span data-ttu-id="939d2-135">Usar...</span><span class="sxs-lookup"><span data-stu-id="939d2-135">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="939d2-136">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="939d2-136">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="939d2-137">Ya está familiarizado con Teams y solo necesita asignar una o dos directivas a un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="939d2-137">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="939d2-138">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="939d2-138">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="939d2-139">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="939d2-139">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="939d2-140">Debe asignar varias directivas a conjuntos específicos de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="939d2-140">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="939d2-141">Por ejemplo, asigne el paquete de directivas Educación (profesor) a los profesores de su escuela para proporcionarles acceso completo a chats, llamadas y reuniones, y al paquete de directivas Educación (estudiante secundario escolar) a los estudiantes secundarios para limitar ciertas funciones como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="939d2-141">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="939d2-142">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-142">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="939d2-143">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="939d2-143">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="939d2-144">Debe asignar directivas a grandes conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="939d2-144">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="939d2-145">Por ejemplo, desea asignar una directiva a cientos o miles de usuarios de su organización al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="939d2-145">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="939d2-146">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-146">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="939d2-147">[Asignar una directiva a un grupo](#assign-a-policy-to-a-group) (en versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="939d2-147">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="939d2-148">Debe asignar directivas en función de la pertenencia a grupos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="939d2-148">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="939d2-149">Por ejemplo, desea asignar una directiva a todos los usuarios de un grupo de seguridad o de una unidad de organización.</span><span class="sxs-lookup"><span data-stu-id="939d2-149">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="939d2-150">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-150">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="939d2-151">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="939d2-151">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="939d2-152">Debe asignar varias directivas a un lote de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="939d2-152">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="939d2-153">Por ejemplo, asigne el paquete de directivas Educación (profesor) a todos los profesores de su escuela mediante la asignación por lotes para proporcionarles acceso total a chats, llamadas y reuniones, y asigne el paquete de directivas Educación (estudiante secundario) a un lote de estudiantes secundarios para limitar ciertas capacidades como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="939d2-153">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="939d2-154">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-154">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="939d2-155">Asignar un paquete de directivas a un grupo (próximamente)</span><span class="sxs-lookup"><span data-stu-id="939d2-155">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="939d2-156">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="939d2-156">Assign a policy to individual users</span></span>

<span data-ttu-id="939d2-157">Siga estos pasos para asignar una directiva a un usuario individual o a un número reducido de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="939d2-157">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="939d2-158">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-158">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="939d2-159">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="939d2-159">To assign a policy to a user:</span></span>

1. <span data-ttu-id="939d2-160">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="939d2-160">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="939d2-161">Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.</span><span class="sxs-lookup"><span data-stu-id="939d2-161">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="939d2-162">Seleccione la Directiva que desea asignar y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="939d2-162">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="939d2-163">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="939d2-163">Or, you can also do the following:</span></span>

1. <span data-ttu-id="939d2-164">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="939d2-164">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="939d2-165">Seleccione la Directiva que desea asignar haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="939d2-165">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="939d2-166">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="939d2-166">Select **Manage users**.</span></span>
4. <span data-ttu-id="939d2-167">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="939d2-167">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="939d2-168">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="939d2-168">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="939d2-169">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="939d2-169">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="939d2-170">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="939d2-170">Using PowerShell</span></span>

<span data-ttu-id="939d2-171">Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo.</span><span class="sxs-lookup"><span data-stu-id="939d2-171">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="939d2-172">Use el ```Grant-``` cmdlet para un tipo de directiva determinado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="939d2-172">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="939d2-173">Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una política de reunión de Teams a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="939d2-173">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="939d2-174">Estos cmdlets están incluidos en el módulo de PowerShell de Skype empresarial online y están documentados en la [Referencia del cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="939d2-174">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="939d2-175">Descargue e instale el [módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si todavía no lo ha hecho) y, a continuación, ejecute lo siguiente para conectarse a Skype empresarial online e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="939d2-175">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="939d2-176">En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiantes a un usuario denominado Reda.</span><span class="sxs-lookup"><span data-stu-id="939d2-176">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="939d2-177">Para obtener más información, vea [Administrar directivas mediante PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="939d2-177">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="939d2-178">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="939d2-178">Assign a policy package</span></span>

<span data-ttu-id="939d2-179">Un paquete de directivas de Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles iguales o similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="939d2-179">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="939d2-180">Cada paquete de directivas está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten actividades típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="939d2-180">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="939d2-181">Algunos ejemplos de paquetes de directivas son el paquete educativo (profesor) y el paquete de salud (trabajador clínico).</span><span class="sxs-lookup"><span data-stu-id="939d2-181">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="939d2-182">Cuando se asigna un paquete de directivas a los usuarios, se crean las directivas del paquete y, después, se puede personalizar la configuración de cada Directiva del paquete para satisfacer las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="939d2-182">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="939d2-183">Para obtener más información sobre los paquetes de directivas, incluidas las instrucciones paso a paso sobre cómo asignarlos y administrarlos, consulte [administrar paquetes de directivas en Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="939d2-183">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="939d2-184">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="939d2-184">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="939d2-185">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-185">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="939d2-186">Para asignar una directiva a usuarios en bloque:</span><span class="sxs-lookup"><span data-stu-id="939d2-186">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="939d2-187">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="939d2-187">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="939d2-188">Busque los usuarios a los que desea asignar la Directiva o filtre la vista para mostrar los usuarios que desea.</span><span class="sxs-lookup"><span data-stu-id="939d2-188">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="939d2-189">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="939d2-189">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="939d2-190">Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="939d2-190">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="939d2-191">Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="939d2-191">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="939d2-192">Para ver el estado de la asignación de Directiva, en la pancarta que aparece en la parte superior de la página **usuarios** después de hacer clic en **aplicar** para enviar la asignación de Directiva, haga clic en **registro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="939d2-192">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="939d2-193">O bien, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel**y, a continuación, en **registro de actividades**, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="939d2-193">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="939d2-194">En el registro de actividades se muestran asignaciones de directivas de los lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="939d2-194">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="939d2-195">Para obtener más información, vea [ver las asignaciones de directivas en el registro de actividades](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="939d2-195">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="939d2-196">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="939d2-196">Using PowerShell</span></span>
 
<span data-ttu-id="939d2-197">Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="939d2-197">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="939d2-198">Use el ```New-CsBatchPolicyAssignmentOperationd``` cmdlet para enviar un lote de usuarios y la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="939d2-198">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="939d2-199">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="939d2-199">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="939d2-200">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="939d2-200">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span> 

<span data-ttu-id="939d2-201">Puede especificar los usuarios por el identificador de objeto, el nombre principal de usuario (UPN), la dirección del Protocolo de inicio de sesión (SIP) o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="939d2-201">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="939d2-202">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="939d2-202">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="939d2-203">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="939d2-203">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="939d2-204">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="939d2-204">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="939d2-205">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="939d2-205">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="939d2-206">Actualmente, la asignación de directivas por lotes no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="939d2-206">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="939d2-207">Vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="939d2-207">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="939d2-208">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-208">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="939d2-209">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="939d2-209">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="939d2-210">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="939d2-210">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="939d2-211">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="939d2-211">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="939d2-212">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="939d2-212">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="939d2-213">Instalar y conectarse al módulo de Azure AD PowerShell for Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="939d2-213">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="939d2-214">Es posible que también desee [Descargar e instalar el módulo Azure ad PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (si todavía no lo ha hecho) y conectarse a Azure ad para poder recuperar una lista de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="939d2-214">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="939d2-215">Ejecute lo siguiente para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="939d2-215">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="939d2-216">Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a teams.</span><span class="sxs-lookup"><span data-stu-id="939d2-216">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="939d2-217">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="939d2-217">Assign a policy to a batch of users</span></span>

<span data-ttu-id="939d2-218">En este ejemplo, usamos el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para asignar una directiva de configuración de aplicación denominada Directiva de configuración de la aplicación de RRHH a un lote de usuarios que aparece en el archivo Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="939d2-218">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="939d2-219">En este ejemplo, se conectará a Azure AD para recuperar una colección de usuarios y, a continuación, asignar una directiva de mensajería llamada nueva Directiva de mensajería de contratación a un lote de usuarios especificado mediante los UPN.</span><span class="sxs-lookup"><span data-stu-id="939d2-219">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="939d2-220">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="939d2-220">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="939d2-221">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="939d2-221">Get the status of a batch assignment</span></span>

<span data-ttu-id="939d2-222">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="939d2-222">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="939d2-223">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="939d2-223">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="939d2-224">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="939d2-224">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="939d2-225">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="939d2-225">Assign a policy to a group</span></span>

<span data-ttu-id="939d2-226">**La asignación de directivas a grupos solo está disponible actualmente en Private Preview. Los cmdlets para esta característica se encuentran en el módulo PowerShell de la versión preliminar de Teams.**</span><span class="sxs-lookup"><span data-stu-id="939d2-226">**Policy assignment to groups is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="939d2-227">La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="939d2-227">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="939d2-228">La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="939d2-228">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="939d2-229">A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda.</span><span class="sxs-lookup"><span data-stu-id="939d2-229">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="939d2-230">Use el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-230">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="939d2-231">Puede especificar un grupo mediante el identificador de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="939d2-231">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="939d2-232">Al asignar la Directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-232">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="939d2-233">Sin embargo, ten en cuenta que la propagación de la asignación de directiva a miembros del grupo se realiza como una operación en segundo plano y puede llevar algún tiempo, según el tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-233">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="939d2-234">Lo mismo sucede cuando se elimina la asignación de una directiva de un grupo, o cuando se agregan miembros a un grupo o se quitan de él.</span><span class="sxs-lookup"><span data-stu-id="939d2-234">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="939d2-235">Por el momento, la asignación de directivas a grupos no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="939d2-235">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="939d2-236">Vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="939d2-236">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="939d2-237">Lo que debe saber sobre la asignación de directivas a grupos</span><span class="sxs-lookup"><span data-stu-id="939d2-237">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="939d2-238">Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-238">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="939d2-239">Reglas de prioridad</span><span class="sxs-lookup"><span data-stu-id="939d2-239">Precedence rules</span></span>

<span data-ttu-id="939d2-240">Para un tipo de directiva determinado, la Directiva efectiva del usuario se determina de acuerdo con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="939d2-240">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="939d2-241">Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo que esté asignada a un grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-241">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="939d2-242">En otras palabras, si un usuario tiene asignada directamente una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-242">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="939d2-243">Esto también significa que si un usuario tiene una directiva de un determinado tipo que se le asignó directamente, tendrá que quitar esa Directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-243">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="939d2-244">Si un usuario no tiene una directiva asignada directamente y es miembro de dos o más grupos y cada grupo tiene una directiva del mismo tipo que tiene asignada, el usuario hereda la Directiva de la asignación de grupo que tiene la clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="939d2-244">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="939d2-245">Si un usuario no es miembro de ningún grupo al que se le ha asignado una directiva, la directiva global (opción predeterminada para toda la organización) para ese tipo de Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="939d2-245">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="939d2-246">La Directiva efectiva de un usuario se actualiza de acuerdo con estas reglas cuando se agrega o se quita un usuario de un grupo al que se asigna una directiva, se elimina la asignación de una directiva de un grupo o se quita una directiva que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="939d2-246">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="939d2-247">Clasificación de asignación de grupo</span><span class="sxs-lookup"><span data-stu-id="939d2-247">Group assignment ranking</span></span>
 
<span data-ttu-id="939d2-248">Cuando se asigna una directiva a un grupo, se especifica una clasificación para la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-248">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="939d2-249">Se usa para determinar qué directiva debe heredar un usuario como su Directiva efectiva si el usuario es miembro de dos o más grupos y se le asigna una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="939d2-249">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="939d2-250">La clasificación de la asignación de grupo es relativa a otras asignaciones de grupo del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="939d2-250">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="939d2-251">Por ejemplo, si va a asignar una directiva de llamadas a dos grupos, establezca la jerarquía de una asignación en 1 y la otra en 2, siendo 1 el ranking más alto.</span><span class="sxs-lookup"><span data-stu-id="939d2-251">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="939d2-252">La clasificación de la asignación de grupo indica qué pertenencia de grupo es más importante o más relevante que otras pertenencias a grupos en relación con la herencia.</span><span class="sxs-lookup"><span data-stu-id="939d2-252">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="939d2-253">Por ejemplo, supongamos que tiene dos grupos, guarda empleados y administradores de la tienda.</span><span class="sxs-lookup"><span data-stu-id="939d2-253">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="939d2-254">Ambos grupos tienen asignada una directiva de llamadas de equipo, almacenan empleados que llaman a la Directiva de llamadas y a los jefes de tienda, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="939d2-254">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="939d2-255">En el caso de un administrador de tienda que esté en ambos grupos, su rol como director es más relevante que su rol como empleado, por lo que la política de llamadas que se asigna al grupo de administradores de la tienda debería tener una clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="939d2-255">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="939d2-256">Mesa</span><span class="sxs-lookup"><span data-stu-id="939d2-256">Group</span></span> |<span data-ttu-id="939d2-257">Nombre de directiva de llamadas de equipo</span><span class="sxs-lookup"><span data-stu-id="939d2-257">Teams calling policy name</span></span>  |<span data-ttu-id="939d2-258">Clasificación</span><span class="sxs-lookup"><span data-stu-id="939d2-258">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="939d2-259">Administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="939d2-259">Store Managers</span></span>   |<span data-ttu-id="939d2-260">Directiva de llamadas a administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="939d2-260">Store Managers Calling Policy</span></span>         |<span data-ttu-id="939d2-261">1</span><span class="sxs-lookup"><span data-stu-id="939d2-261">1</span></span>|
|<span data-ttu-id="939d2-262">Almacenar empleados</span><span class="sxs-lookup"><span data-stu-id="939d2-262">Store Employees</span></span>    |<span data-ttu-id="939d2-263">Almacenar la política de llamadas</span><span class="sxs-lookup"><span data-stu-id="939d2-263">Store Employees Calling Policy</span></span>      |<span data-ttu-id="939d2-264">2</span><span class="sxs-lookup"><span data-stu-id="939d2-264">2</span></span>|

<span data-ttu-id="939d2-265">Si no especifica una clasificación, la asignación de directiva recibe la clasificación más baja.</span><span class="sxs-lookup"><span data-stu-id="939d2-265">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="939d2-266">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-266">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="939d2-267">Los cmdlets se encuentran en la versión preliminar del módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="939d2-267">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="939d2-268">Siga estos pasos para desinstalar primero la versión disponible general del módulo de PowerShell de Teams (si está instalada) y, a continuación, instale la última versión preliminar del módulo de la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="939d2-268">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="939d2-269">Si todavía no lo ha hecho, ejecute lo siguiente para registrar la galería de pruebas de PowerShell como fuente de confianza.</span><span class="sxs-lookup"><span data-stu-id="939d2-269">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="939d2-270">Si tiene instalada la versión general del módulo de PowerShell de Teams, ejecute lo siguiente para desinstalarla.</span><span class="sxs-lookup"><span data-stu-id="939d2-270">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="939d2-271">Ejecute lo siguiente para instalar el módulo de PowerShell más reciente de Microsoft Teams desde la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="939d2-271">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="939d2-272">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="939d2-272">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="939d2-273">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="939d2-273">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="939d2-274">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="939d2-274">Assign a policy to a group</span></span>

<span data-ttu-id="939d2-275">En este ejemplo, usamos el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva de reunión de Teams denominada Directiva de reunión de directores minoristas a un grupo con una clasificación de asignación de 1.</span><span class="sxs-lookup"><span data-stu-id="939d2-275">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="939d2-276">Para obtener más información, vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="939d2-276">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="939d2-277">Obtener asignaciones de directivas para un grupo</span><span class="sxs-lookup"><span data-stu-id="939d2-277">Get policy assignments for a group</span></span>

<span data-ttu-id="939d2-278">Use el ```Get-CsGroupPolicyAssignment``` cmdlet para obtener todas las directivas asignadas a un grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-278">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="939d2-279">Ten en cuenta que los grupos siempre aparecen en la lista por su identificador de grupo aunque su dirección SIP o dirección de correo electrónico se hayan usado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="939d2-279">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="939d2-280">En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="939d2-280">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="939d2-281">En este ejemplo, se devuelven todos los grupos que tienen asignada una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="939d2-281">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="939d2-282">Para obtener más información, vea [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="939d2-282">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="939d2-283">Quitar una directiva de un grupo</span><span class="sxs-lookup"><span data-stu-id="939d2-283">Remove a policy from a group</span></span>

<span data-ttu-id="939d2-284">Use el ```Remove-CsGroupPolicyAssignment``` cmdlet para quitar una directiva de un grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-284">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="939d2-285">Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y con una clasificación menor.</span><span class="sxs-lookup"><span data-stu-id="939d2-285">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="939d2-286">Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tengan una jerarquía de 3 y 4 se actualizarán para reflejar su nueva clasificación.</span><span class="sxs-lookup"><span data-stu-id="939d2-286">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="939d2-287">En las dos tablas siguientes se muestra este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="939d2-287">The following two tables show this example.</span></span>

<span data-ttu-id="939d2-288">A continuación se ofrece una lista de las asignaciones de directivas y las prioridades de una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="939d2-288">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="939d2-289">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="939d2-289">Group name</span></span>  |<span data-ttu-id="939d2-290">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="939d2-290">Policy name</span></span>  |<span data-ttu-id="939d2-291">Clasificación</span><span class="sxs-lookup"><span data-stu-id="939d2-291">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="939d2-292">Ventas</span><span class="sxs-lookup"><span data-stu-id="939d2-292">Sales</span></span>    |<span data-ttu-id="939d2-293">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="939d2-293">Sales policy</span></span>       | <span data-ttu-id="939d2-294">1</span><span class="sxs-lookup"><span data-stu-id="939d2-294">1</span></span>        |
|<span data-ttu-id="939d2-295">Región occidental</span><span class="sxs-lookup"><span data-stu-id="939d2-295">West Region</span></span>     |<span data-ttu-id="939d2-296">Política de la región occidental</span><span class="sxs-lookup"><span data-stu-id="939d2-296">West Region policy</span></span>         |<span data-ttu-id="939d2-297">2</span><span class="sxs-lookup"><span data-stu-id="939d2-297">2</span></span>         |
|<span data-ttu-id="939d2-298">Departamentos</span><span class="sxs-lookup"><span data-stu-id="939d2-298">Division</span></span>    |<span data-ttu-id="939d2-299">Política de división</span><span class="sxs-lookup"><span data-stu-id="939d2-299">Division policy</span></span>         |<span data-ttu-id="939d2-300">3</span><span class="sxs-lookup"><span data-stu-id="939d2-300">3</span></span>         |
|<span data-ttu-id="939d2-301">Secundaria</span><span class="sxs-lookup"><span data-stu-id="939d2-301">Subsidiary</span></span>   |<span data-ttu-id="939d2-302">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="939d2-302">Subsidiary policy</span></span>        |<span data-ttu-id="939d2-303">4</span><span class="sxs-lookup"><span data-stu-id="939d2-303">4</span></span>         |

<span data-ttu-id="939d2-304">Si quitamos la política de región occidental del grupo región oeste, las asignaciones y prioridades de directivas se actualizan de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="939d2-304">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="939d2-305">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="939d2-305">Group name</span></span>  |<span data-ttu-id="939d2-306">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="939d2-306">Policy name</span></span>  |<span data-ttu-id="939d2-307">Clasificación</span><span class="sxs-lookup"><span data-stu-id="939d2-307">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="939d2-308">Ventas</span><span class="sxs-lookup"><span data-stu-id="939d2-308">Sales</span></span>    |<span data-ttu-id="939d2-309">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="939d2-309">Sales policy</span></span>       | <span data-ttu-id="939d2-310">1</span><span class="sxs-lookup"><span data-stu-id="939d2-310">1</span></span>        |
|<span data-ttu-id="939d2-311">Departamentos</span><span class="sxs-lookup"><span data-stu-id="939d2-311">Division</span></span>    |<span data-ttu-id="939d2-312">Política de división</span><span class="sxs-lookup"><span data-stu-id="939d2-312">Division policy</span></span>         |<span data-ttu-id="939d2-313">2</span><span class="sxs-lookup"><span data-stu-id="939d2-313">2</span></span>         |
|<span data-ttu-id="939d2-314">Secundaria</span><span class="sxs-lookup"><span data-stu-id="939d2-314">Subsidiary</span></span>   |<span data-ttu-id="939d2-315">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="939d2-315">Subsidiary policy</span></span>        |<span data-ttu-id="939d2-316">3</span><span class="sxs-lookup"><span data-stu-id="939d2-316">3</span></span>        |

<span data-ttu-id="939d2-317">En este ejemplo, quitamos la política de reuniones de Teams de un grupo.</span><span class="sxs-lookup"><span data-stu-id="939d2-317">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="939d2-318">Para obtener más información, consulte [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="939d2-318">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="939d2-319">Cambiar una asignación de directiva para un grupo</span><span class="sxs-lookup"><span data-stu-id="939d2-319">Change a policy assignment for a group</span></span>

<span data-ttu-id="939d2-320">Después de asignar una directiva a un grupo, puede usar el ```Set-CsGroupPolicyAssignmentd``` cmdlet para cambiar la asignación de directivas del grupo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="939d2-320">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="939d2-321">Cambiar la clasificación</span><span class="sxs-lookup"><span data-stu-id="939d2-321">Change the ranking</span></span>
- <span data-ttu-id="939d2-322">Cambiar la Directiva de un tipo de directiva determinado</span><span class="sxs-lookup"><span data-stu-id="939d2-322">Change the policy of a given policy type</span></span>
- <span data-ttu-id="939d2-323">Cambiar la Directiva de un determinado tipo de directiva y la clasificación</span><span class="sxs-lookup"><span data-stu-id="939d2-323">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="939d2-324">En este ejemplo, cambiamos la Directiva de los equipos de un grupo a una directiva llamada SupportCallPark y la clasificación de asignación a 3.</span><span class="sxs-lookup"><span data-stu-id="939d2-324">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="939d2-325">Para obtener más información, consulte [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="939d2-325">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="939d2-326">Cambiar la Directiva efectiva de un usuario</span><span class="sxs-lookup"><span data-stu-id="939d2-326">Change the effective policy for a user</span></span>

<span data-ttu-id="939d2-327">Este es un ejemplo de cómo cambiar la Directiva efectiva para un usuario que tiene asignada directamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="939d2-327">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="939d2-328">En primer lugar, usamos el ```Get-CsUserPolicyAssignment``` cmdlet junto con el ```PolicySource``` parámetro para obtener detalles de los equipos de reunión de las directivas de difusión asociados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="939d2-328">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="939d2-329">Para obtener más información, vea [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="939d2-329">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="939d2-330">En la salida se muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada eventos de empleados, que tiene prioridad sobre la Directiva denominada eventos de proveedor que se asignan a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="939d2-330">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="939d2-331">Ahora, quitamos la Directiva de eventos de empleados del usuario.</span><span class="sxs-lookup"><span data-stu-id="939d2-331">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="939d2-332">Esto significa que el usuario ya no tiene una directiva de difusión de reunión de equipos que se les asignó directamente y heredará la Directiva de eventos en vivo de proveedores que se asigna al grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="939d2-332">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="939d2-333">Use el siguiente cmdlet en el módulo de PowerShell de Skype empresarial para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="939d2-333">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="939d2-334">Puede usar el siguiente cmdlet en el módulo de PowerShell de Teams para hacerlo a escala mediante una asignación de Directiva por lotes, donde $users es una lista de los usuarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="939d2-334">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="939d2-335">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="939d2-335">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="939d2-336">Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directivas a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="939d2-336">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="939d2-337">Use el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para enviar un lote de usuarios y el paquete de directivas que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="939d2-337">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="939d2-338">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="939d2-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="939d2-339">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="939d2-339">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="939d2-340">Un lote puede contener hasta 20.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="939d2-340">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="939d2-341">Puede especificar los usuarios por su identificador de objeto, UPN, dirección SIP o dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="939d2-341">You can specify users by their object Id, UPN, SIP address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="939d2-342">Actualmente recomendamos que asigne paquetes de directivas en lotes de usuarios de 5.000 a la vez.</span><span class="sxs-lookup"><span data-stu-id="939d2-342">We're currently recommending that you assign policy packages in batches of 5,000 users at a time.</span></span> <span data-ttu-id="939d2-343">Durante estas horas de demanda aumentada, puede experimentar retrasos en los tiempos de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="939d2-343">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="939d2-344">Para minimizar el impacto de estos aumentos en los tiempos de procesamiento, le sugerimos que envíe tamaños de lotes más pequeños de hasta 5.000 usuarios y que envíe cada lote solo después de que se haya completado el anterior.</span><span class="sxs-lookup"><span data-stu-id="939d2-344">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="939d2-345">El envío de lotes fuera del horario laboral normal también puede ayudar.</span><span class="sxs-lookup"><span data-stu-id="939d2-345">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="939d2-346">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-346">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="939d2-347">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si todavía no lo ha hecho).</span><span class="sxs-lookup"><span data-stu-id="939d2-347">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="939d2-348">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="939d2-348">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="939d2-349">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="939d2-349">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="939d2-350">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="939d2-350">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="939d2-351">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="939d2-351">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="939d2-352">En este ejemplo, usamos el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para asignar el paquete de directivas Education_PrimaryStudent a un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="939d2-352">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="939d2-353">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="939d2-353">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="939d2-354">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="939d2-354">Get the status of a batch assignment</span></span>

<span data-ttu-id="939d2-355">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="939d2-355">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="939d2-356">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="939d2-356">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="939d2-357">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="939d2-357">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="939d2-358">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="939d2-358">Related topics</span></span>

- [<span data-ttu-id="939d2-359">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="939d2-359">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
