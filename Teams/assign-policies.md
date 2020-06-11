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
ms.openlocfilehash: 098e55aa5f4096ac80e6f54e191e6c9d48d90826
ms.sourcegitcommit: 54ce623c4db792b5e33f5db00e575afc88776b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "44698290"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="db7a7-103">Asignar directivas a los usuarios de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="db7a7-104">**Una de las características de Microsoft Teams descritas en este artículo, [asignación de directiva a grupos](#assign-a-policy-to-a-group), solo está disponible actualmente en la versión preliminar privada. Los cmdlets de PowerShell para esta característica se encuentran en el módulo PowerShell de la versión preliminar de Teams.**</span><span class="sxs-lookup"><span data-stu-id="db7a7-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in private preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span> <span data-ttu-id="db7a7-105">Para estar al día del estado de versión de esta característica, consulte la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="db7a7-105">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="db7a7-106">Como administrador, use directivas para controlar las características de teams que están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="db7a7-106">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="db7a7-107">Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por citar algunas.</span><span class="sxs-lookup"><span data-stu-id="db7a7-107">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="db7a7-108">Las organizaciones tienen diferentes tipos de usuarios con necesidades exclusivas y directivas personalizadas que usted crea y asigna le permiten adaptar la configuración de directivas a distintos conjuntos de usuarios según esas necesidades.</span><span class="sxs-lookup"><span data-stu-id="db7a7-108">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="db7a7-109">Para facilitar la administración de directivas de su organización, Teams ofrece varias formas de asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="db7a7-109">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="db7a7-110">Puede asignar una directiva directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes, o a un grupo del que el usuario sea miembro.</span><span class="sxs-lookup"><span data-stu-id="db7a7-110">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="db7a7-111">También puede usar paquetes de directivas para asignar una colección preconfigurada de directivas a los usuarios de su organización que tengan roles similares.</span><span class="sxs-lookup"><span data-stu-id="db7a7-111">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="db7a7-112">La opción que elija dependerá del número de directivas que esté administrando y del número de usuarios a los que va a asignar.</span><span class="sxs-lookup"><span data-stu-id="db7a7-112">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="db7a7-113">En este artículo se describen las diferentes maneras en las que puede asignar directivas a los usuarios y las situaciones recomendadas para Cuándo usarlas.</span><span class="sxs-lookup"><span data-stu-id="db7a7-113">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="db7a7-114">¿Qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="db7a7-114">Which policy takes precedence?</span></span>

<span data-ttu-id="db7a7-115">Un usuario tiene una directiva vigente para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="db7a7-115">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="db7a7-116">Es posible o incluso probable que un usuario tenga asignada directamente una directiva y también es miembro de uno o más grupos a los que se ha asignado una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-116">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="db7a7-117">En estos tipos de escenarios, ¿qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="db7a7-117">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="db7a7-118">La Directiva efectiva del usuario se determina según las reglas de prioridad, de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="db7a7-118">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="db7a7-119">Si un usuario tiene asignada directamente una directiva (ya sea de forma individual o mediante una asignación por lotes), tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="db7a7-119">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="db7a7-120">En el ejemplo siguiente, la Directiva efectiva del usuario es la Lincoln cuadrada de la reunión, que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-120">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva asignada directamente](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="db7a7-122">Si un usuario no tiene asignada directamente una directiva de un tipo determinado, tendrá prioridad la directiva asignada a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-122">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="db7a7-123">Si un usuario es miembro de varios grupos, tiene prioridad la Directiva que tiene la mayor [clasificación de asignación de grupo](#group-assignment-ranking) para el tipo de directiva determinado.</span><span class="sxs-lookup"><span data-stu-id="db7a7-123">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="db7a7-124">En este ejemplo, la Directiva efectiva del usuario es el equipo de ejecución y la Directiva de alta definición, que tiene la mayor clasificación de asignación relativa a otros grupos de los que el usuario es miembro y al que también se les ha asignado una directiva del mismo tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="db7a7-124">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama que muestra cómo tiene prioridad una directiva heredada del grupo](media/assign-policies-example-group.png)

<span data-ttu-id="db7a7-126">Si un usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario recibirá la directiva global (opción predeterminada para toda la organización) para ese tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="db7a7-126">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="db7a7-127">Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-127">Here's an example.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva global](media/assign-policies-example-global.png)

<span data-ttu-id="db7a7-129">Para obtener más información, vea [reglas de prioridad](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="db7a7-129">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="db7a7-130">Formas de asignar directivas</span><span class="sxs-lookup"><span data-stu-id="db7a7-130">Ways to assign policies</span></span>

<span data-ttu-id="db7a7-131">A continuación se ofrece una descripción general de las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno.</span><span class="sxs-lookup"><span data-stu-id="db7a7-131">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="db7a7-132">Haga clic en los vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="db7a7-132">Click the links to learn more.</span></span>

|<span data-ttu-id="db7a7-133">Haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="db7a7-133">Do this</span></span>  |<span data-ttu-id="db7a7-134">Si...</span><span class="sxs-lookup"><span data-stu-id="db7a7-134">If...</span></span>  | <span data-ttu-id="db7a7-135">Usar...</span><span class="sxs-lookup"><span data-stu-id="db7a7-135">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="db7a7-136">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="db7a7-136">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="db7a7-137">Ya está familiarizado con Teams y solo necesita asignar una o dos directivas a un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="db7a7-137">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="db7a7-138">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="db7a7-138">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="db7a7-139">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="db7a7-139">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="db7a7-140">Debe asignar varias directivas a conjuntos específicos de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="db7a7-140">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="db7a7-141">Por ejemplo, asigne el paquete de directivas Educación (profesor) a los profesores de su escuela para proporcionarles acceso completo a chats, llamadas y reuniones, y al paquete de directivas Educación (estudiante secundario escolar) a los estudiantes secundarios para limitar ciertas funciones como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="db7a7-141">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="db7a7-142">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-142">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="db7a7-143">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="db7a7-143">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="db7a7-144">Debe asignar directivas a grandes conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="db7a7-144">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="db7a7-145">Por ejemplo, desea asignar una directiva a cientos o miles de usuarios de su organización al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-145">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="db7a7-146">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-146">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="db7a7-147">[Asignar una directiva a un grupo](#assign-a-policy-to-a-group) (en versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="db7a7-147">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="db7a7-148">Debe asignar directivas en función de la pertenencia a grupos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-148">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="db7a7-149">Por ejemplo, desea asignar una directiva a todos los usuarios de un grupo de seguridad o de una unidad de organización.</span><span class="sxs-lookup"><span data-stu-id="db7a7-149">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="db7a7-150">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-150">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="db7a7-151">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="db7a7-151">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="db7a7-152">Debe asignar varias directivas a un lote de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="db7a7-152">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="db7a7-153">Por ejemplo, asigne el paquete de directivas Educación (profesor) a todos los profesores de su escuela mediante la asignación por lotes para proporcionarles acceso total a chats, llamadas y reuniones, y asigne el paquete de directivas Educación (estudiante secundario) a un lote de estudiantes secundarios para limitar ciertas capacidades como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="db7a7-153">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="db7a7-154">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-154">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="db7a7-155">Asignar un paquete de directivas a un grupo (próximamente)</span><span class="sxs-lookup"><span data-stu-id="db7a7-155">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="db7a7-156">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="db7a7-156">Assign a policy to individual users</span></span>

<span data-ttu-id="db7a7-157">Siga estos pasos para asignar una directiva a un usuario individual o a un número reducido de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="db7a7-157">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="db7a7-158">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-158">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="db7a7-159">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="db7a7-159">To assign a policy to a user:</span></span>

1. <span data-ttu-id="db7a7-160">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-160">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="db7a7-161">Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.</span><span class="sxs-lookup"><span data-stu-id="db7a7-161">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="db7a7-162">Seleccione la Directiva que desea asignar y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="db7a7-162">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="db7a7-163">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db7a7-163">Or, you can also do the following:</span></span>

1. <span data-ttu-id="db7a7-164">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="db7a7-164">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="db7a7-165">Seleccione la Directiva que desea asignar haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="db7a7-165">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="db7a7-166">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="db7a7-166">Select **Manage users**.</span></span>
4. <span data-ttu-id="db7a7-167">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="db7a7-167">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="db7a7-168">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="db7a7-168">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="db7a7-169">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="db7a7-169">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="db7a7-170">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="db7a7-170">Using PowerShell</span></span>

<span data-ttu-id="db7a7-171">Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-171">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="db7a7-172">Use el ```Grant-``` cmdlet para un tipo de directiva determinado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="db7a7-172">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="db7a7-173">Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una política de reunión de Teams a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="db7a7-173">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="db7a7-174">Estos cmdlets están incluidos en el módulo de PowerShell de Skype empresarial online y están documentados en la [Referencia del cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="db7a7-174">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="db7a7-175">Descargue e instale el [módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si todavía no lo ha hecho) y, a continuación, ejecute lo siguiente para conectarse a Skype empresarial online e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="db7a7-175">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="db7a7-176">En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiantes a un usuario denominado Reda.</span><span class="sxs-lookup"><span data-stu-id="db7a7-176">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="db7a7-177">Para obtener más información, vea [Administrar directivas mediante PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="db7a7-177">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="db7a7-178">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="db7a7-178">Assign a policy package</span></span>

<span data-ttu-id="db7a7-179">Un paquete de directivas de Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles iguales o similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="db7a7-179">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="db7a7-180">Cada paquete de directivas está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten actividades típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="db7a7-180">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="db7a7-181">Algunos ejemplos de paquetes de directivas son el paquete educativo (profesor) y el paquete de salud (trabajador clínico).</span><span class="sxs-lookup"><span data-stu-id="db7a7-181">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="db7a7-182">Cuando se asigna un paquete de directivas a los usuarios, se crean las directivas del paquete y, después, se puede personalizar la configuración de cada Directiva del paquete para satisfacer las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="db7a7-182">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="db7a7-183">Para obtener más información sobre los paquetes de directivas, incluidas las instrucciones paso a paso sobre cómo asignarlos y administrarlos, consulte [administrar paquetes de directivas en Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="db7a7-183">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="db7a7-184">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="db7a7-184">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="db7a7-185">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-185">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="db7a7-186">Para asignar una directiva a usuarios en bloque:</span><span class="sxs-lookup"><span data-stu-id="db7a7-186">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="db7a7-187">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="db7a7-187">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="db7a7-188">Busque los usuarios a los que desea asignar la Directiva o filtre la vista para mostrar los usuarios que desea.</span><span class="sxs-lookup"><span data-stu-id="db7a7-188">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="db7a7-189">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="db7a7-189">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="db7a7-190">Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="db7a7-190">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="db7a7-191">Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="db7a7-191">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="db7a7-192">Para ver el estado de la asignación de Directiva, en la pancarta que aparece en la parte superior de la página **usuarios** después de hacer clic en **aplicar** para enviar la asignación de Directiva, haga clic en **registro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="db7a7-192">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="db7a7-193">O bien, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel**y, a continuación, en **registro de actividades**, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="db7a7-193">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="db7a7-194">En el registro de actividades se muestran asignaciones de directivas de los lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="db7a7-194">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="db7a7-195">Para obtener más información, vea [ver las asignaciones de directivas en el registro de actividades](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="db7a7-195">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="db7a7-196">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="db7a7-196">Using PowerShell</span></span>
 
<span data-ttu-id="db7a7-197">Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="db7a7-197">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="db7a7-198">Use el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para enviar un lote de usuarios y la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="db7a7-198">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="db7a7-199">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="db7a7-199">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="db7a7-200">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="db7a7-200">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span> 

<span data-ttu-id="db7a7-201">Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="db7a7-201">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="db7a7-202">Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-202">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="db7a7-203">Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-203">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="db7a7-204">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="db7a7-204">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="db7a7-205">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="db7a7-205">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="db7a7-206">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="db7a7-206">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="db7a7-207">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="db7a7-207">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="db7a7-208">Actualmente, la asignación de directivas por lotes no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="db7a7-208">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="db7a7-209">Vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="db7a7-209">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="db7a7-210">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-210">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="db7a7-211">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="db7a7-211">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="db7a7-212">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="db7a7-212">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="db7a7-213">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="db7a7-213">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="db7a7-214">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="db7a7-214">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="db7a7-215">Instalar y conectarse al módulo de Azure AD PowerShell for Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="db7a7-215">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="db7a7-216">Es posible que también desee [Descargar e instalar el módulo Azure ad PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (si todavía no lo ha hecho) y conectarse a Azure ad para poder recuperar una lista de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="db7a7-216">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="db7a7-217">Ejecute lo siguiente para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="db7a7-217">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="db7a7-218">Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a teams.</span><span class="sxs-lookup"><span data-stu-id="db7a7-218">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="db7a7-219">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="db7a7-219">Assign a policy to a batch of users</span></span>

<span data-ttu-id="db7a7-220">En este ejemplo, usamos el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para asignar una directiva de configuración de aplicación denominada Directiva de configuración de la aplicación de RRHH a un lote de usuarios que aparece en el archivo Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="db7a7-220">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="db7a7-221">En este ejemplo, se conectará a Azure AD para recuperar una colección de usuarios y, a continuación, asignar una directiva de mensajería llamada nueva Directiva de mensajería de contratación a un lote de usuarios especificado mediante su dirección SIP.</span><span class="sxs-lookup"><span data-stu-id="db7a7-221">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="db7a7-222">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="db7a7-222">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="db7a7-223">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="db7a7-223">Get the status of a batch assignment</span></span>

<span data-ttu-id="db7a7-224">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="db7a7-224">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="db7a7-225">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="db7a7-225">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="db7a7-226">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="db7a7-226">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="db7a7-227">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="db7a7-227">Assign a policy to a group</span></span>

<span data-ttu-id="db7a7-228">**La asignación de directivas a grupos solo está disponible actualmente en Private Preview. Los cmdlets para esta característica se encuentran en el módulo PowerShell de la versión preliminar de Teams.**</span><span class="sxs-lookup"><span data-stu-id="db7a7-228">**Policy assignment to groups is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="db7a7-229">La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="db7a7-229">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="db7a7-230">La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="db7a7-230">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="db7a7-231">A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda.</span><span class="sxs-lookup"><span data-stu-id="db7a7-231">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="db7a7-232">Use el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-232">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="db7a7-233">Puede especificar un grupo mediante el identificador de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="db7a7-233">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="db7a7-234">Al asignar la Directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-234">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="db7a7-235">Sin embargo, ten en cuenta que la propagación de la asignación de directiva a miembros del grupo se realiza como una operación en segundo plano y puede llevar algún tiempo, según el tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-235">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="db7a7-236">Lo mismo sucede cuando se elimina la asignación de una directiva de un grupo, o cuando se agregan miembros a un grupo o se quitan de él.</span><span class="sxs-lookup"><span data-stu-id="db7a7-236">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="db7a7-237">Por el momento, la asignación de directivas a grupos no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="db7a7-237">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="db7a7-238">Vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="db7a7-238">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="db7a7-239">Lo que debe saber sobre la asignación de directivas a grupos</span><span class="sxs-lookup"><span data-stu-id="db7a7-239">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="db7a7-240">Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-240">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="db7a7-241">Reglas de prioridad</span><span class="sxs-lookup"><span data-stu-id="db7a7-241">Precedence rules</span></span>

<span data-ttu-id="db7a7-242">Para un tipo de directiva determinado, la Directiva efectiva del usuario se determina de acuerdo con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db7a7-242">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="db7a7-243">Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo que esté asignada a un grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-243">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="db7a7-244">En otras palabras, si un usuario tiene asignada directamente una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-244">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="db7a7-245">Esto también significa que si un usuario tiene una directiva de un determinado tipo que se le asignó directamente, tendrá que quitar esa Directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-245">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="db7a7-246">Si un usuario no tiene una directiva asignada directamente y es miembro de dos o más grupos y cada grupo tiene una directiva del mismo tipo que tiene asignada, el usuario hereda la Directiva de la asignación de grupo que tiene la clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="db7a7-246">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="db7a7-247">Si un usuario no es miembro de ningún grupo al que se le ha asignado una directiva, la directiva global (opción predeterminada para toda la organización) para ese tipo de Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-247">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="db7a7-248">La Directiva efectiva de un usuario se actualiza de acuerdo con estas reglas cuando se agrega o se quita un usuario de un grupo al que se asigna una directiva, se elimina la asignación de una directiva de un grupo o se quita una directiva que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-248">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="db7a7-249">Clasificación de asignación de grupo</span><span class="sxs-lookup"><span data-stu-id="db7a7-249">Group assignment ranking</span></span>
 
<span data-ttu-id="db7a7-250">Cuando se asigna una directiva a un grupo, se especifica una clasificación para la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-250">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="db7a7-251">Se usa para determinar qué directiva debe heredar un usuario como su Directiva efectiva si el usuario es miembro de dos o más grupos y se le asigna una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-251">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="db7a7-252">La clasificación de la asignación de grupo es relativa a otras asignaciones de grupo del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-252">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="db7a7-253">Por ejemplo, si va a asignar una directiva de llamadas a dos grupos, establezca la jerarquía de una asignación en 1 y la otra en 2, siendo 1 el ranking más alto.</span><span class="sxs-lookup"><span data-stu-id="db7a7-253">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="db7a7-254">La clasificación de la asignación de grupo indica qué pertenencia de grupo es más importante o más relevante que otras pertenencias a grupos en relación con la herencia.</span><span class="sxs-lookup"><span data-stu-id="db7a7-254">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="db7a7-255">Por ejemplo, supongamos que tiene dos grupos, guarda empleados y administradores de la tienda.</span><span class="sxs-lookup"><span data-stu-id="db7a7-255">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="db7a7-256">Ambos grupos tienen asignada una directiva de llamadas de equipo, almacenan empleados que llaman a la Directiva de llamadas y a los jefes de tienda, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="db7a7-256">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="db7a7-257">En el caso de un administrador de tienda que esté en ambos grupos, su rol como director es más relevante que su rol como empleado, por lo que la política de llamadas que se asigna al grupo de administradores de la tienda debería tener una clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="db7a7-257">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="db7a7-258">Mesa</span><span class="sxs-lookup"><span data-stu-id="db7a7-258">Group</span></span> |<span data-ttu-id="db7a7-259">Nombre de directiva de llamadas de equipo</span><span class="sxs-lookup"><span data-stu-id="db7a7-259">Teams calling policy name</span></span>  |<span data-ttu-id="db7a7-260">Clasificación</span><span class="sxs-lookup"><span data-stu-id="db7a7-260">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="db7a7-261">Administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="db7a7-261">Store Managers</span></span>   |<span data-ttu-id="db7a7-262">Directiva de llamadas a administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="db7a7-262">Store Managers Calling Policy</span></span>         |<span data-ttu-id="db7a7-263">1</span><span class="sxs-lookup"><span data-stu-id="db7a7-263">1</span></span>|
|<span data-ttu-id="db7a7-264">Almacenar empleados</span><span class="sxs-lookup"><span data-stu-id="db7a7-264">Store Employees</span></span>    |<span data-ttu-id="db7a7-265">Almacenar la política de llamadas</span><span class="sxs-lookup"><span data-stu-id="db7a7-265">Store Employees Calling Policy</span></span>      |<span data-ttu-id="db7a7-266">2</span><span class="sxs-lookup"><span data-stu-id="db7a7-266">2</span></span>|

<span data-ttu-id="db7a7-267">Si no especifica una clasificación, la asignación de directiva recibe la clasificación más baja.</span><span class="sxs-lookup"><span data-stu-id="db7a7-267">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="db7a7-268">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-268">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="db7a7-269">Los cmdlets se encuentran en la versión preliminar del módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="db7a7-269">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="db7a7-270">Siga estos pasos para desinstalar primero la versión disponible general del módulo de PowerShell de Teams (si está instalada) y, a continuación, instale la última versión preliminar del módulo de la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db7a7-270">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="db7a7-271">Si todavía no lo ha hecho, ejecute lo siguiente para registrar la galería de pruebas de PowerShell como fuente de confianza.</span><span class="sxs-lookup"><span data-stu-id="db7a7-271">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="db7a7-272">Si tiene instalada la versión general del módulo de PowerShell de Teams, ejecute lo siguiente para desinstalarla.</span><span class="sxs-lookup"><span data-stu-id="db7a7-272">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="db7a7-273">Ejecute lo siguiente para instalar el módulo de PowerShell más reciente de Microsoft Teams desde la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db7a7-273">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="db7a7-274">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="db7a7-274">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="db7a7-275">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="db7a7-275">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="db7a7-276">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="db7a7-276">Assign a policy to a group</span></span>

<span data-ttu-id="db7a7-277">En este ejemplo, usamos el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva de reunión de Teams denominada Directiva de reunión de directores minoristas a un grupo con una clasificación de asignación de 1.</span><span class="sxs-lookup"><span data-stu-id="db7a7-277">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="db7a7-278">Para obtener más información, vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="db7a7-278">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="db7a7-279">Obtener asignaciones de directivas para un grupo</span><span class="sxs-lookup"><span data-stu-id="db7a7-279">Get policy assignments for a group</span></span>

<span data-ttu-id="db7a7-280">Use el ```Get-CsGroupPolicyAssignment``` cmdlet para obtener todas las directivas asignadas a un grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-280">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="db7a7-281">Ten en cuenta que los grupos siempre aparecen en la lista por su identificador de grupo aunque su dirección SIP o dirección de correo electrónico se hayan usado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="db7a7-281">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="db7a7-282">En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="db7a7-282">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="db7a7-283">En este ejemplo, se devuelven todos los grupos que tienen asignada una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="db7a7-283">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="db7a7-284">Para obtener más información, vea [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="db7a7-284">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="db7a7-285">Quitar una directiva de un grupo</span><span class="sxs-lookup"><span data-stu-id="db7a7-285">Remove a policy from a group</span></span>

<span data-ttu-id="db7a7-286">Use el ```Remove-CsGroupPolicyAssignment``` cmdlet para quitar una directiva de un grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-286">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="db7a7-287">Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y con una clasificación menor.</span><span class="sxs-lookup"><span data-stu-id="db7a7-287">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="db7a7-288">Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tengan una jerarquía de 3 y 4 se actualizarán para reflejar su nueva clasificación.</span><span class="sxs-lookup"><span data-stu-id="db7a7-288">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="db7a7-289">En las dos tablas siguientes se muestra este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-289">The following two tables show this example.</span></span>

<span data-ttu-id="db7a7-290">A continuación se ofrece una lista de las asignaciones de directivas y las prioridades de una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="db7a7-290">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="db7a7-291">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="db7a7-291">Group name</span></span>  |<span data-ttu-id="db7a7-292">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="db7a7-292">Policy name</span></span>  |<span data-ttu-id="db7a7-293">Clasificación</span><span class="sxs-lookup"><span data-stu-id="db7a7-293">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="db7a7-294">Ventas</span><span class="sxs-lookup"><span data-stu-id="db7a7-294">Sales</span></span>    |<span data-ttu-id="db7a7-295">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="db7a7-295">Sales policy</span></span>       | <span data-ttu-id="db7a7-296">1</span><span class="sxs-lookup"><span data-stu-id="db7a7-296">1</span></span>        |
|<span data-ttu-id="db7a7-297">Región occidental</span><span class="sxs-lookup"><span data-stu-id="db7a7-297">West Region</span></span>     |<span data-ttu-id="db7a7-298">Política de la región occidental</span><span class="sxs-lookup"><span data-stu-id="db7a7-298">West Region policy</span></span>         |<span data-ttu-id="db7a7-299">2</span><span class="sxs-lookup"><span data-stu-id="db7a7-299">2</span></span>         |
|<span data-ttu-id="db7a7-300">Departamentos</span><span class="sxs-lookup"><span data-stu-id="db7a7-300">Division</span></span>    |<span data-ttu-id="db7a7-301">Política de división</span><span class="sxs-lookup"><span data-stu-id="db7a7-301">Division policy</span></span>         |<span data-ttu-id="db7a7-302">3</span><span class="sxs-lookup"><span data-stu-id="db7a7-302">3</span></span>         |
|<span data-ttu-id="db7a7-303">Secundaria</span><span class="sxs-lookup"><span data-stu-id="db7a7-303">Subsidiary</span></span>   |<span data-ttu-id="db7a7-304">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="db7a7-304">Subsidiary policy</span></span>        |<span data-ttu-id="db7a7-305">4</span><span class="sxs-lookup"><span data-stu-id="db7a7-305">4</span></span>         |

<span data-ttu-id="db7a7-306">Si quitamos la política de región occidental del grupo región oeste, las asignaciones y prioridades de directivas se actualizan de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="db7a7-306">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="db7a7-307">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="db7a7-307">Group name</span></span>  |<span data-ttu-id="db7a7-308">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="db7a7-308">Policy name</span></span>  |<span data-ttu-id="db7a7-309">Clasificación</span><span class="sxs-lookup"><span data-stu-id="db7a7-309">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="db7a7-310">Ventas</span><span class="sxs-lookup"><span data-stu-id="db7a7-310">Sales</span></span>    |<span data-ttu-id="db7a7-311">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="db7a7-311">Sales policy</span></span>       | <span data-ttu-id="db7a7-312">1</span><span class="sxs-lookup"><span data-stu-id="db7a7-312">1</span></span>        |
|<span data-ttu-id="db7a7-313">Departamentos</span><span class="sxs-lookup"><span data-stu-id="db7a7-313">Division</span></span>    |<span data-ttu-id="db7a7-314">Política de división</span><span class="sxs-lookup"><span data-stu-id="db7a7-314">Division policy</span></span>         |<span data-ttu-id="db7a7-315">2</span><span class="sxs-lookup"><span data-stu-id="db7a7-315">2</span></span>         |
|<span data-ttu-id="db7a7-316">Secundaria</span><span class="sxs-lookup"><span data-stu-id="db7a7-316">Subsidiary</span></span>   |<span data-ttu-id="db7a7-317">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="db7a7-317">Subsidiary policy</span></span>        |<span data-ttu-id="db7a7-318">3</span><span class="sxs-lookup"><span data-stu-id="db7a7-318">3</span></span>        |

<span data-ttu-id="db7a7-319">En este ejemplo, quitamos la política de reuniones de Teams de un grupo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-319">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="db7a7-320">Para obtener más información, consulte [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="db7a7-320">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="db7a7-321">Cambiar una asignación de directiva para un grupo</span><span class="sxs-lookup"><span data-stu-id="db7a7-321">Change a policy assignment for a group</span></span>

<span data-ttu-id="db7a7-322">Después de asignar una directiva a un grupo, puede usar el ```Set-CsGroupPolicyAssignmentd``` cmdlet para cambiar la asignación de directivas del grupo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="db7a7-322">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="db7a7-323">Cambiar la clasificación</span><span class="sxs-lookup"><span data-stu-id="db7a7-323">Change the ranking</span></span>
- <span data-ttu-id="db7a7-324">Cambiar la Directiva de un tipo de directiva determinado</span><span class="sxs-lookup"><span data-stu-id="db7a7-324">Change the policy of a given policy type</span></span>
- <span data-ttu-id="db7a7-325">Cambiar la Directiva de un determinado tipo de directiva y la clasificación</span><span class="sxs-lookup"><span data-stu-id="db7a7-325">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="db7a7-326">En este ejemplo, cambiamos la Directiva de los equipos de un grupo a una directiva llamada SupportCallPark y la clasificación de asignación a 3.</span><span class="sxs-lookup"><span data-stu-id="db7a7-326">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="db7a7-327">Para obtener más información, consulte [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="db7a7-327">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="db7a7-328">Cambiar la Directiva efectiva de un usuario</span><span class="sxs-lookup"><span data-stu-id="db7a7-328">Change the effective policy for a user</span></span>

<span data-ttu-id="db7a7-329">Este es un ejemplo de cómo cambiar la Directiva efectiva para un usuario que tiene asignada directamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="db7a7-329">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="db7a7-330">En primer lugar, usamos el ```Get-CsUserPolicyAssignment``` cmdlet junto con el ```PolicySource``` parámetro para obtener detalles de los equipos de reunión de las directivas de difusión asociados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-330">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="db7a7-331">Para obtener más información, vea [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="db7a7-331">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="db7a7-332">En la salida se muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada eventos de empleados, que tiene prioridad sobre la Directiva denominada eventos de proveedor que se asignan a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-332">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="db7a7-333">Ahora, quitamos la Directiva de eventos de empleados del usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-333">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="db7a7-334">Esto significa que el usuario ya no tiene una directiva de difusión de reunión de equipos que se les asignó directamente y heredará la Directiva de eventos en vivo de proveedores que se asigna al grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-334">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="db7a7-335">Use el siguiente cmdlet en el módulo de PowerShell de Skype empresarial para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="db7a7-335">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="db7a7-336">Puede usar el siguiente cmdlet en el módulo de PowerShell de Teams para hacerlo a escala mediante una asignación de Directiva por lotes, donde $users es una lista de los usuarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="db7a7-336">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="db7a7-337">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="db7a7-337">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="db7a7-338">Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directivas a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="db7a7-338">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="db7a7-339">Use el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para enviar un lote de usuarios y el paquete de directivas que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="db7a7-339">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="db7a7-340">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="db7a7-340">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="db7a7-341">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="db7a7-341">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="db7a7-342">Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="db7a7-342">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="db7a7-343">Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-343">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="db7a7-344">Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario.</span><span class="sxs-lookup"><span data-stu-id="db7a7-344">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="db7a7-345">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="db7a7-345">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="db7a7-346">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="db7a7-346">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="db7a7-347">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="db7a7-347">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="db7a7-348">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="db7a7-348">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="db7a7-349">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-349">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="db7a7-350">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si todavía no lo ha hecho).</span><span class="sxs-lookup"><span data-stu-id="db7a7-350">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="db7a7-351">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="db7a7-351">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="db7a7-352">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="db7a7-352">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="db7a7-353">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="db7a7-353">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="db7a7-354">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="db7a7-354">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="db7a7-355">En este ejemplo, usamos el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para asignar el paquete de directivas Education_PrimaryStudent a un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="db7a7-355">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="db7a7-356">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="db7a7-356">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="db7a7-357">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="db7a7-357">Get the status of a batch assignment</span></span>

<span data-ttu-id="db7a7-358">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="db7a7-358">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="db7a7-359">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="db7a7-359">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="db7a7-360">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="db7a7-360">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="db7a7-361">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="db7a7-361">Related topics</span></span>

- [<span data-ttu-id="db7a7-362">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="db7a7-362">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
