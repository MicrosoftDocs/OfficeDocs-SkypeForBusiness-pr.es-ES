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
ms.openlocfilehash: fb9946f9954dc46d9d97137f707b7ad46c797fb9
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908529"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="84597-103">Asignar directivas a los usuarios de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84597-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="84597-104">Como administrador, use directivas para controlar las características de teams que están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="84597-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="84597-105">Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por citar algunas.</span><span class="sxs-lookup"><span data-stu-id="84597-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="84597-106">Las organizaciones tienen diferentes tipos de usuarios con necesidades exclusivas y directivas personalizadas que usted crea y asigna le permiten adaptar la configuración de directivas a distintos conjuntos de usuarios según esas necesidades.</span><span class="sxs-lookup"><span data-stu-id="84597-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="84597-107">Para facilitar la administración de directivas de su organización, Teams ofrece varias formas de asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="84597-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="84597-108">Puede asignar una directiva directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes, o a un grupo del que son miembros los usuarios.</span><span class="sxs-lookup"><span data-stu-id="84597-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="84597-109">También puede usar paquetes de directivas para asignar una colección preconfigurada de directivas a los usuarios de su organización que tengan roles similares.</span><span class="sxs-lookup"><span data-stu-id="84597-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="84597-110">La opción que elija dependerá del número de directivas que esté administrando y del número de usuarios a los que va a asignar.</span><span class="sxs-lookup"><span data-stu-id="84597-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="84597-111">Al configurar las directivas globales (predeterminada para toda la organización) de modo que se apliquen al mayor número de usuarios de su organización, solo tiene que asignar directivas a aquellos usuarios que requieran directivas especializadas.</span><span class="sxs-lookup"><span data-stu-id="84597-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="84597-112">En este artículo se describen las diferentes maneras en las que puede asignar directivas a los usuarios y las situaciones recomendadas para Cuándo usarlas.</span><span class="sxs-lookup"><span data-stu-id="84597-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="84597-113">¿Qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="84597-113">Which policy takes precedence?</span></span>

<span data-ttu-id="84597-114">Un usuario tiene una directiva vigente para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="84597-115">Es posible o incluso probable que un usuario tenga asignada directamente una directiva y también es miembro de uno o más grupos a los que se ha asignado una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="84597-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="84597-116">En estos tipos de escenarios, ¿qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="84597-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="84597-117">La Directiva efectiva del usuario se determina según las reglas de prioridad, de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="84597-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="84597-118">Si un usuario tiene asignada directamente una directiva (ya sea de forma individual o mediante una asignación por lotes), tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="84597-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="84597-119">En el ejemplo siguiente, la Directiva efectiva del usuario es la Lincoln cuadrada de la reunión, que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva asignada directamente](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="84597-121">Si un usuario no tiene asignada directamente una directiva de un tipo determinado, tendrá prioridad la directiva asignada a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="84597-122">Si un usuario es miembro de varios grupos, tiene prioridad la Directiva que tiene la mayor [clasificación de asignación de grupo](#group-assignment-ranking) para el tipo de directiva determinado.</span><span class="sxs-lookup"><span data-stu-id="84597-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="84597-123">En este ejemplo, la Directiva efectiva del usuario es el equipo de ejecución y la Directiva de alta definición, que tiene la mayor clasificación de asignación relativa a otros grupos de los que el usuario es miembro y al que también se les ha asignado una directiva del mismo tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama que muestra cómo tiene prioridad una directiva heredada del grupo](media/assign-policies-example-group.png)

<span data-ttu-id="84597-125">Si un usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario recibirá la directiva global (opción predeterminada para toda la organización) para ese tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="84597-126">Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="84597-126">Here's an example.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva global](media/assign-policies-example-global.png)

<span data-ttu-id="84597-128">Para obtener más información, vea [reglas de prioridad](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="84597-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="84597-129">Formas de asignar directivas</span><span class="sxs-lookup"><span data-stu-id="84597-129">Ways to assign policies</span></span>

<span data-ttu-id="84597-130">A continuación se ofrece una descripción general de las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno.</span><span class="sxs-lookup"><span data-stu-id="84597-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="84597-131">Haga clic en los vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="84597-131">Click the links to learn more.</span></span>

<span data-ttu-id="84597-132">Antes de asignar directivas a usuarios individuales o grupos, primero [establezca las directivas globales (valor predeterminado de organización)](#set-the-global-policies) para que se apliquen al mayor número de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="84597-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="84597-133">Una vez configuradas las directivas globales, solo tendrá que asignar directivas a aquellos usuarios que requieran directivas especializadas.</span><span class="sxs-lookup"><span data-stu-id="84597-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="84597-134">Haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="84597-134">Do this</span></span>  |<span data-ttu-id="84597-135">Si...</span><span class="sxs-lookup"><span data-stu-id="84597-135">If...</span></span>  | <span data-ttu-id="84597-136">Usar...</span><span class="sxs-lookup"><span data-stu-id="84597-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="84597-137">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="84597-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="84597-138">Ya está familiarizado con Teams y solo necesita asignar una o dos directivas a un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="84597-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="84597-139">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="84597-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="84597-140">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="84597-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="84597-141">Debe asignar directivas en función de la pertenencia a grupos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="84597-142">Por ejemplo, desea asignar una directiva a todos los usuarios de un grupo de seguridad o de una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="84597-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="84597-143">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="84597-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="84597-144">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="84597-145">Debe asignar directivas a grandes conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="84597-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="84597-146">Por ejemplo, desea asignar una directiva a cientos o miles de usuarios de su organización al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="84597-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="84597-147">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="84597-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="84597-148">Asignar un paquete de directivas a los usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="84597-149">Debe asignar varias directivas a conjuntos específicos de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="84597-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="84597-150">Por ejemplo, asigne el paquete de directivas Educación (profesor) a los profesores de su escuela para proporcionarles acceso completo a chats, llamadas y reuniones, y al paquete de directivas Educación (estudiante secundario escolar) a los estudiantes secundarios para limitar ciertas funciones como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="84597-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="84597-151">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="84597-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="84597-152">[Asignar un paquete de directivas a un grupo](#assign-a-policy-package-to-a-group) (en la versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="84597-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="84597-153">Debe asignar varias directivas a un grupo de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="84597-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="84597-154">Por ejemplo, desea asignar un paquete de directivas a todos los usuarios de un grupo de seguridad o de una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="84597-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="84597-155">El centro de administración de Microsoft Teams (próximamente) o cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="84597-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="84597-156">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="84597-157">Debe asignar varias directivas a un lote de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="84597-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="84597-158">Por ejemplo, asigne el paquete de directivas Educación (profesor) a todos los profesores de su escuela mediante la asignación por lotes para proporcionarles acceso total a chats, llamadas y reuniones, y asigne el paquete de directivas Educación (estudiante secundario) a un lote de estudiantes secundarios para limitar ciertas capacidades como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="84597-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="84597-159">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="84597-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="84597-160">Establecer las directivas globales</span><span class="sxs-lookup"><span data-stu-id="84597-160">Set the global policies</span></span>

<span data-ttu-id="84597-161">Siga estos pasos para establecer las directivas globales (valor predeterminado de la organización) para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="84597-162">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84597-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="84597-163">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de directivas del tipo de directiva que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="84597-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="84597-164">Por ejemplo, **Teams**  >  **Policies** , directivas de reuniones de **reuniones**  >  **Meetings policies** , **directivas de mensajería** o directivas de llamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="84597-164">For example, **Teams** > **Teams policies** , **Meetings** > **Meetings policies** , **Messaging policies** , or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="84597-165">Seleccione la directiva **global (opción predeterminada para toda la organización)** para ver la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="84597-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="84597-166">Actualice la Directiva según sea necesario y, a continuación, seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="84597-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="84597-167">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="84597-167">Using PowerShell</span></span>

<span data-ttu-id="84597-168">Para establecer las directivas globales mediante PowerShell, use el identificador global.</span><span class="sxs-lookup"><span data-stu-id="84597-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="84597-169">Para empezar, revisamos la directiva global actual para determinar qué configuración desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="84597-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

<span data-ttu-id="84597-170">A continuación, actualice la directiva global según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="84597-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="84597-171">Solo tiene que especificar los valores de la configuración que quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="84597-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="84597-172">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="84597-172">Assign a policy to individual users</span></span>

<span data-ttu-id="84597-173">Siga estos pasos para asignar una directiva a un usuario individual o a un número reducido de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="84597-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="84597-174">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84597-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="84597-175">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="84597-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="84597-176">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-176">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then click the user.</span></span>
2. <span data-ttu-id="84597-177">Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.</span><span class="sxs-lookup"><span data-stu-id="84597-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="84597-178">Seleccione la Directiva que desea asignar y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="84597-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="84597-179">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="84597-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="84597-180">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="84597-181">Seleccione la Directiva que desea asignar haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="84597-182">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="84597-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="84597-183">En el panel **Administrar usuarios** , busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="84597-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="84597-184">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="84597-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="84597-185">Cuando haya terminado de agregar usuarios, seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="84597-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="84597-186">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="84597-186">Using PowerShell</span></span>

<span data-ttu-id="84597-187">Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo.</span><span class="sxs-lookup"><span data-stu-id="84597-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="84597-188">Use el ```Grant-``` cmdlet para un tipo de directiva determinado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="84597-189">Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una política de reunión de Teams a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="84597-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="84597-190">Estos cmdlets están incluidos en el módulo de PowerShell de Skype empresarial online y están documentados en la [Referencia del cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="84597-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="84597-191">Descargue e instale el [módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/download/details.aspx?id=39366) (si todavía no lo ha hecho) y, a continuación, ejecute lo siguiente para conectarse a Skype empresarial online e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="84597-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="84597-192">En este momento, el conector de Skype empresarial online forma parte del módulo de PowerShell más reciente de Teams.</span><span class="sxs-lookup"><span data-stu-id="84597-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="84597-193">Si está usando la [versión pública de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)más reciente de PowerShell, no necesita instalar el conector de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="84597-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="84597-194">En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiantes a un usuario denominado Reda.</span><span class="sxs-lookup"><span data-stu-id="84597-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="84597-195">Para obtener más información, vea [Administrar directivas mediante PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="84597-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="84597-196">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="84597-196">Assign a policy to a group</span></span>

<span data-ttu-id="84597-197">La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="84597-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="84597-198">La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="84597-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="84597-199">A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda.</span><span class="sxs-lookup"><span data-stu-id="84597-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="84597-200">La asignación de directivas a grupos se recomienda para grupos de hasta 50.000 usuarios, pero también funciona con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="84597-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="84597-201">Al asignar la Directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="84597-202">Sin embargo, ten en cuenta que la propagación de la asignación de directiva a miembros del grupo se realiza como una operación en segundo plano y puede llevar algún tiempo, según el tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="84597-203">Lo mismo sucede cuando se elimina la asignación de una directiva de un grupo, o cuando se agregan miembros a un grupo o se quitan de él.</span><span class="sxs-lookup"><span data-stu-id="84597-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="84597-204">Lo que debe saber sobre la asignación de directivas a grupos</span><span class="sxs-lookup"><span data-stu-id="84597-204">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="84597-205">Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-205">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="84597-206">Reglas de prioridad</span><span class="sxs-lookup"><span data-stu-id="84597-206">Precedence rules</span></span>

<span data-ttu-id="84597-207">Para un tipo de directiva determinado, la Directiva efectiva del usuario se determina de acuerdo con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="84597-207">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="84597-208">Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo que esté asignada a un grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-208">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="84597-209">En otras palabras, si un usuario tiene asignada directamente una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-209">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="84597-210">Esto también significa que si un usuario tiene una directiva de un determinado tipo que se le asignó directamente, tendrá que quitar esa Directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-210">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="84597-211">Si un usuario no tiene una directiva asignada directamente y es miembro de dos o más grupos y cada grupo tiene una directiva del mismo tipo que tiene asignada, el usuario hereda la Directiva de la asignación de grupo que tiene la clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="84597-211">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="84597-212">Si un usuario no es miembro de ningún grupo al que se le ha asignado una directiva, la directiva global (opción predeterminada para toda la organización) para ese tipo de Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-212">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="84597-213">La Directiva efectiva de un usuario se actualiza de acuerdo con estas reglas cuando se agrega o se quita un usuario de un grupo al que se asigna una directiva, se elimina la asignación de una directiva de un grupo o se quita una directiva que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-213">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="84597-214">Clasificación de asignación de grupo</span><span class="sxs-lookup"><span data-stu-id="84597-214">Group assignment ranking</span></span>
 
<span data-ttu-id="84597-215">Cuando se asigna una directiva a un grupo, se especifica una clasificación para la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-215">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="84597-216">Se usa para determinar qué directiva debe heredar un usuario como su Directiva efectiva si el usuario es miembro de dos o más grupos y se le asigna una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="84597-216">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="84597-217">La clasificación de la asignación de grupo es relativa a otras asignaciones de grupo del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="84597-217">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="84597-218">Por ejemplo, si va a asignar una directiva de llamadas a dos grupos, establezca la jerarquía de una asignación en 1 y la otra en 2, siendo 1 el ranking más alto.</span><span class="sxs-lookup"><span data-stu-id="84597-218">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="84597-219">La clasificación de la asignación de grupo indica qué pertenencia de grupo es más importante o más relevante que otras pertenencias a grupos en relación con la herencia.</span><span class="sxs-lookup"><span data-stu-id="84597-219">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="84597-220">Por ejemplo, supongamos que tiene dos grupos, guarda empleados y administradores de la tienda.</span><span class="sxs-lookup"><span data-stu-id="84597-220">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="84597-221">Ambos grupos tienen asignada una directiva de llamadas de equipo, almacenan empleados que llaman a la Directiva de llamadas y a los jefes de tienda, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="84597-221">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="84597-222">En el caso de un administrador de tienda que esté en ambos grupos, su rol como director es más relevante que su rol como empleado, por lo que la política de llamadas que se asigna al grupo de administradores de la tienda debería tener una clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="84597-222">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="84597-223">Mesa</span><span class="sxs-lookup"><span data-stu-id="84597-223">Group</span></span> |<span data-ttu-id="84597-224">Nombre de directiva de llamadas de equipo</span><span class="sxs-lookup"><span data-stu-id="84597-224">Teams calling policy name</span></span>  |<span data-ttu-id="84597-225">Clasificación</span><span class="sxs-lookup"><span data-stu-id="84597-225">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="84597-226">Administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="84597-226">Store Managers</span></span>   |<span data-ttu-id="84597-227">Directiva de llamadas a administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="84597-227">Store Managers Calling Policy</span></span>         |<span data-ttu-id="84597-228">1</span><span class="sxs-lookup"><span data-stu-id="84597-228">1</span></span>|
|<span data-ttu-id="84597-229">Almacenar empleados</span><span class="sxs-lookup"><span data-stu-id="84597-229">Store Employees</span></span>    |<span data-ttu-id="84597-230">Almacenar la política de llamadas</span><span class="sxs-lookup"><span data-stu-id="84597-230">Store Employees Calling Policy</span></span>      |<span data-ttu-id="84597-231">2</span><span class="sxs-lookup"><span data-stu-id="84597-231">2</span></span>|

<span data-ttu-id="84597-232">Si no especifica una clasificación, la asignación de directiva recibe la clasificación más baja.</span><span class="sxs-lookup"><span data-stu-id="84597-232">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="84597-233">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84597-233">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="84597-234">Por el momento, la asignación de directivas a grupos que usan el centro de administración de Microsoft Teams solo está disponible para la Directiva de llamadas de Teams, la Directiva de Parque de llamadas de Teams, la Directiva de Teams, la Directiva de eventos en vivo de Teams, la Directiva de reuniones</span><span class="sxs-lookup"><span data-stu-id="84597-234">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="84597-235">Para otros tipos de directivas, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84597-235">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="84597-236">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-236">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="84597-237">Por ejemplo, vaya a **Meetings**  >  **las directivas de reunión** de reuniones.</span><span class="sxs-lookup"><span data-stu-id="84597-237">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="84597-238">Seleccione la pestaña **asignación de directiva de grupo** .</span><span class="sxs-lookup"><span data-stu-id="84597-238">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="84597-239">Seleccione **Agregar grupo** y, a continuación, en el panel **asignar Directiva a grupo** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="84597-239">Select **Add group** , and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="84597-240">Busque y agregue el grupo al que desea asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-240">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="84597-241">Establezca la clasificación de la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-241">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="84597-242">Seleccione la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="84597-242">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="84597-243">Seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="84597-243">Select **Apply**.</span></span>

<span data-ttu-id="84597-244">Para quitar una asignación de directiva de grupo, en la pestaña **asignación de directiva de grupo** de la página de Directiva, seleccione la asignación de grupo y, a continuación, seleccione **quitar**.</span><span class="sxs-lookup"><span data-stu-id="84597-244">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="84597-245">Para cambiar la jerarquía de una asignación de grupo, primero debe quitar la asignación de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-245">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="84597-246">Después, siga los pasos anteriores para asignar la Directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-246">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="84597-247">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="84597-247">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="84597-248">Por el momento, la asignación de directivas a grupos con PowerShell no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="84597-248">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="84597-249">Vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="84597-249">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="84597-250">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84597-250">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="84597-251">Para obtener instrucciones paso a paso, consulte [instalar Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="84597-251">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="84597-252">Asignar una directiva a un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-252">Assign a policy to a group of users</span></span>

<span data-ttu-id="84597-253">Use el cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para asignar una directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-253">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="84597-254">Puede especificar un grupo mediante el identificador de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="84597-254">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="84597-255">En este ejemplo, asignamos una directiva de reunión de Teams denominada política de reunión de directores minoristas a un grupo con una clasificación de asignación de 1.</span><span class="sxs-lookup"><span data-stu-id="84597-255">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="84597-256">Obtener asignaciones de directivas para un grupo</span><span class="sxs-lookup"><span data-stu-id="84597-256">Get policy assignments for a group</span></span>

<span data-ttu-id="84597-257">Use el cmdlet [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) para obtener todas las directivas asignadas a un grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-257">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="84597-258">Ten en cuenta que los grupos siempre aparecen en la lista por su identificador de grupo aunque su dirección SIP o dirección de correo electrónico se hayan usado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-258">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="84597-259">En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="84597-259">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="84597-260">En este ejemplo, se devuelven todos los grupos que tienen asignada una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="84597-260">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="84597-261">Quitar una directiva de un grupo</span><span class="sxs-lookup"><span data-stu-id="84597-261">Remove a policy from a group</span></span>

<span data-ttu-id="84597-262">Use el cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) para quitar una directiva de un grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-262">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="84597-263">Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y con una clasificación menor.</span><span class="sxs-lookup"><span data-stu-id="84597-263">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="84597-264">Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tengan una jerarquía de 3 y 4 se actualizarán para reflejar su nueva clasificación.</span><span class="sxs-lookup"><span data-stu-id="84597-264">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="84597-265">En las dos tablas siguientes se muestra este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="84597-265">The following two tables show this example.</span></span>

<span data-ttu-id="84597-266">A continuación se ofrece una lista de las asignaciones de directivas y las prioridades de una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="84597-266">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="84597-267">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="84597-267">Group name</span></span>  |<span data-ttu-id="84597-268">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="84597-268">Policy name</span></span>  |<span data-ttu-id="84597-269">Clasificación</span><span class="sxs-lookup"><span data-stu-id="84597-269">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="84597-270">Ventas</span><span class="sxs-lookup"><span data-stu-id="84597-270">Sales</span></span>    |<span data-ttu-id="84597-271">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="84597-271">Sales policy</span></span>       | <span data-ttu-id="84597-272">1</span><span class="sxs-lookup"><span data-stu-id="84597-272">1</span></span>        |
|<span data-ttu-id="84597-273">Región occidental</span><span class="sxs-lookup"><span data-stu-id="84597-273">West Region</span></span>     |<span data-ttu-id="84597-274">Política de la región occidental</span><span class="sxs-lookup"><span data-stu-id="84597-274">West Region policy</span></span>         |<span data-ttu-id="84597-275">2</span><span class="sxs-lookup"><span data-stu-id="84597-275">2</span></span>         |
|<span data-ttu-id="84597-276">Departamentos</span><span class="sxs-lookup"><span data-stu-id="84597-276">Division</span></span>    |<span data-ttu-id="84597-277">Política de división</span><span class="sxs-lookup"><span data-stu-id="84597-277">Division policy</span></span>         |<span data-ttu-id="84597-278">3</span><span class="sxs-lookup"><span data-stu-id="84597-278">3</span></span>         |
|<span data-ttu-id="84597-279">Secundaria</span><span class="sxs-lookup"><span data-stu-id="84597-279">Subsidiary</span></span>   |<span data-ttu-id="84597-280">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="84597-280">Subsidiary policy</span></span>        |<span data-ttu-id="84597-281">4</span><span class="sxs-lookup"><span data-stu-id="84597-281">4</span></span>         |

<span data-ttu-id="84597-282">Si quitamos la política de región occidental del grupo región oeste, las asignaciones y prioridades de directivas se actualizan de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="84597-282">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="84597-283">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="84597-283">Group name</span></span>  |<span data-ttu-id="84597-284">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="84597-284">Policy name</span></span>  |<span data-ttu-id="84597-285">Clasificación</span><span class="sxs-lookup"><span data-stu-id="84597-285">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="84597-286">Ventas</span><span class="sxs-lookup"><span data-stu-id="84597-286">Sales</span></span>    |<span data-ttu-id="84597-287">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="84597-287">Sales policy</span></span>       | <span data-ttu-id="84597-288">1</span><span class="sxs-lookup"><span data-stu-id="84597-288">1</span></span>        |
|<span data-ttu-id="84597-289">Departamentos</span><span class="sxs-lookup"><span data-stu-id="84597-289">Division</span></span>    |<span data-ttu-id="84597-290">Política de división</span><span class="sxs-lookup"><span data-stu-id="84597-290">Division policy</span></span>         |<span data-ttu-id="84597-291">2</span><span class="sxs-lookup"><span data-stu-id="84597-291">2</span></span>         |
|<span data-ttu-id="84597-292">Secundaria</span><span class="sxs-lookup"><span data-stu-id="84597-292">Subsidiary</span></span>   |<span data-ttu-id="84597-293">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="84597-293">Subsidiary policy</span></span>        |<span data-ttu-id="84597-294">3</span><span class="sxs-lookup"><span data-stu-id="84597-294">3</span></span>        |

<span data-ttu-id="84597-295">En este ejemplo, quitamos la política de reuniones de Teams de un grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-295">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="84597-296">Cambiar una asignación de directiva para un grupo</span><span class="sxs-lookup"><span data-stu-id="84597-296">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="84597-297">El cmdlet [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="84597-297">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="84597-298">Mientras tanto, para cambiar una asignación de directiva de grupo, puede quitar la asignación de directiva actual del grupo y, a continuación, agregar una nueva asignación de directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-298">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="84597-299">Después de asignar una directiva a un grupo, puede usar el cmdlet [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) para cambiar la asignación de directivas del grupo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="84597-299">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="84597-300">Cambiar la clasificación</span><span class="sxs-lookup"><span data-stu-id="84597-300">Change the ranking</span></span>
- <span data-ttu-id="84597-301">Cambiar la Directiva de un tipo de directiva determinado</span><span class="sxs-lookup"><span data-stu-id="84597-301">Change the policy of a given policy type</span></span>
- <span data-ttu-id="84597-302">Cambiar la Directiva de un determinado tipo de directiva y la clasificación</span><span class="sxs-lookup"><span data-stu-id="84597-302">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="84597-303">En este ejemplo, cambiamos la Directiva de los equipos de un grupo a una directiva llamada SupportCallPark y la clasificación de asignación a 3.</span><span class="sxs-lookup"><span data-stu-id="84597-303">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="84597-304">Cambiar la Directiva efectiva de un usuario</span><span class="sxs-lookup"><span data-stu-id="84597-304">Change the effective policy for a user</span></span>

<span data-ttu-id="84597-305">Este es un ejemplo de cómo cambiar la Directiva efectiva para un usuario que tiene asignada directamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="84597-305">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="84597-306">En primer lugar, usamos el cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) junto con el ```PolicySource``` parámetro para obtener detalles de los equipos de difusión de las directivas de difusión asociadas con el usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-306">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="84597-307">En la salida se muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada eventos de empleados, que tiene prioridad sobre la Directiva denominada eventos de proveedor que se asignan a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-307">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="84597-308">Ahora, quitamos la Directiva de eventos de empleados del usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-308">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="84597-309">Esto significa que el usuario ya no tiene una directiva de difusión de reunión de equipos que se les asignó directamente y heredará la Directiva de eventos en vivo de proveedores que se asigna al grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-309">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="84597-310">Use el siguiente cmdlet en el módulo de PowerShell de Skype empresarial para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="84597-310">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="84597-311">Puede usar el siguiente cmdlet en el módulo de PowerShell de Teams para hacerlo a escala mediante una asignación de Directiva por lotes, donde $users es una lista de los usuarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="84597-311">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="84597-312">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-312">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="84597-313">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84597-313">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="84597-314">Para asignar una directiva a usuarios en bloque:</span><span class="sxs-lookup"><span data-stu-id="84597-314">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="84597-315">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="84597-315">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="84597-316">Busque los usuarios a los que desea asignar la Directiva o filtre la vista para mostrar los usuarios que desea.</span><span class="sxs-lookup"><span data-stu-id="84597-316">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="84597-317">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="84597-317">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="84597-318">Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="84597-318">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="84597-319">Haga clic en **Editar configuración** , haga los cambios que desee y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="84597-319">Click **Edit settings** , make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="84597-320">Para ver el estado de la asignación de Directiva, en la pancarta que aparece en la parte superior de la página **usuarios** después de hacer clic en **aplicar** para enviar la asignación de Directiva, haga clic en **registro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="84597-320">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="84597-321">O bien, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel** y, a continuación, en **registro de actividades** , haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="84597-321">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard** , and then under **Activity log** , click **View details**.</span></span> <span data-ttu-id="84597-322">En el registro de actividades se muestran asignaciones de directivas de los lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="84597-322">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="84597-323">Para obtener más información, vea [ver las asignaciones de directivas en el registro de actividades](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="84597-323">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="84597-324">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="84597-324">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="84597-325">Actualmente, la asignación de directivas por lotes con PowerShell no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="84597-325">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="84597-326">Vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="84597-326">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="84597-327">Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="84597-327">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="84597-328">Use el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="84597-328">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="84597-329">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="84597-329">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="84597-330">Puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="84597-330">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="84597-331">Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="84597-331">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="84597-332">Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="84597-332">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="84597-333">Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-333">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="84597-334">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="84597-334">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="84597-335">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="84597-335">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="84597-336">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="84597-336">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="84597-337">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="84597-337">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="84597-338">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84597-338">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="84597-339">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="84597-339">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="84597-340">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="84597-340">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="84597-341">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="84597-341">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="84597-342">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="84597-342">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="84597-343">Instalar y conectarse al módulo de Azure AD PowerShell for Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="84597-343">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="84597-344">Es posible que también desee [Descargar e instalar el módulo Azure ad PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (si todavía no lo ha hecho) y conectarse a Azure ad para poder recuperar una lista de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="84597-344">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="84597-345">Ejecute lo siguiente para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="84597-345">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="84597-346">Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a teams.</span><span class="sxs-lookup"><span data-stu-id="84597-346">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="84597-347">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-347">Assign a policy to a batch of users</span></span>

<span data-ttu-id="84597-348">En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar una directiva de configuración de aplicación denominada política de configuración de la aplicación de RRHH a un lote de usuarios que aparece en el archivo Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="84597-348">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="84597-349">En este ejemplo, se conectará a Azure AD para recuperar una colección de usuarios y, a continuación, asignar una directiva de mensajería llamada nueva Directiva de mensajería de contratación a un lote de usuarios especificado mediante su dirección SIP.</span><span class="sxs-lookup"><span data-stu-id="84597-349">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="84597-350">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="84597-350">Get the status of a batch assignment</span></span>

<span data-ttu-id="84597-351">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="84597-351">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="84597-352">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="84597-352">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="84597-353">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="84597-353">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="84597-354">Asignar un paquete de directivas a los usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-354">Assign a policy package to users</span></span>

<span data-ttu-id="84597-355">Un paquete de directivas de Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles iguales o similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="84597-355">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="84597-356">Cada paquete de directivas está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten actividades típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="84597-356">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="84597-357">Algunos ejemplos de paquetes de directivas son el paquete educativo (profesor) y el paquete de salud (trabajador clínico).</span><span class="sxs-lookup"><span data-stu-id="84597-357">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="84597-358">Para obtener más información, vea [administrar paquetes de directivas en Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="84597-358">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="84597-359">Asignar un paquete de directivas a un usuario</span><span class="sxs-lookup"><span data-stu-id="84597-359">Assign a policy package to one user</span></span>

1. <span data-ttu-id="84597-360">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-360">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then click the user.</span></span>
2. <span data-ttu-id="84597-361">En la página del usuario, haga clic en **directivas** y, a continuación, junto a **paquete de directivas** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="84597-361">On the user's page, click **Policies** , and then next to **Policy package** , click **Edit**.</span></span>
3. <span data-ttu-id="84597-362">En el panel **asignar paquete de directivas** , seleccione el paquete que desea asignar y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="84597-362">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="84597-363">Asignar un paquete de directivas a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-363">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="84597-364">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **paquetes de directivas** y, a continuación, seleccione el paquete de directivas que desea asignar haciendo clic a la izquierda del nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="84597-364">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="84597-365">Haga clic en **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="84597-365">Click **Manage users**.</span></span>
3. <span data-ttu-id="84597-366">En el panel **Administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="84597-366">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="84597-367">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="84597-367">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="84597-368">Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="84597-368">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="84597-369">Asignar un paquete de directivas a un grupo</span><span class="sxs-lookup"><span data-stu-id="84597-369">Assign a policy package to a group</span></span>

<span data-ttu-id="84597-370">**Esta característica está en versión preliminar privada**</span><span class="sxs-lookup"><span data-stu-id="84597-370">**This feature is in private preview**</span></span>

<span data-ttu-id="84597-371">La asignación de paquetes de directivas a grupos le permite asignar varias directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="84597-371">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="84597-372">La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="84597-372">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="84597-373">A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda.</span><span class="sxs-lookup"><span data-stu-id="84597-373">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="84597-374">La asignación de paquetes de directivas a grupos se recomienda para grupos de hasta 50.000 usuarios, pero también funciona con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="84597-374">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="84597-375">Cuando asignes el paquete de directivas, se asignará al grupo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="84597-375">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="84597-376">Sin embargo, ten en cuenta que la propagación de la asignación de directiva a miembros del grupo se realiza como una operación en segundo plano y puede llevar algún tiempo, según el tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-376">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="84597-377">Lo mismo sucede cuando se elimina la asignación de una directiva de un grupo, o cuando se agregan miembros a un grupo o se quitan de él.</span><span class="sxs-lookup"><span data-stu-id="84597-377">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84597-378">Antes de empezar, es importante comprender [las reglas de prioridad](#precedence-rules) y la [clasificación de asignación de grupo](#group-assignment-ranking).</span><span class="sxs-lookup"><span data-stu-id="84597-378">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="84597-379">Asegúrese de leer y comprender los conceptos de lo que debe [saber sobre la asignación de directivas a grupos](#what-you-need-to-know-about-policy-assignment-to-groups) anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="84597-379">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="84597-380">Usar el centro de administración de Microsoft Teams (próximamente)</span><span class="sxs-lookup"><span data-stu-id="84597-380">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="84597-381">La asignación de paquetes de directivas a grupos en el centro de administración de Microsoft Teams estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="84597-381">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="84597-382">Vuelva a consultar aquí para obtener las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="84597-382">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="84597-383">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="84597-383">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="84597-384">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84597-384">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="84597-385">Para obtener instrucciones paso a paso, consulte [instalar Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="84597-385">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="84597-386">Asignar un paquete de directivas a un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-386">Assign a policy package to a group of users</span></span>

<span data-ttu-id="84597-387">Use el cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) para asignar un paquete de directivas a un grupo.</span><span class="sxs-lookup"><span data-stu-id="84597-387">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="84597-388">Puede especificar un grupo mediante el identificador de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="84597-388">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="84597-389">Cuando asigne el paquete de directivas, especifique una [clasificación de asignación de grupo](#group-assignment-ranking) para cada tipo de directiva en el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="84597-389">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="84597-390">En este ejemplo, asignamos el paquete de directivas Education_Teacher a un grupo con una clasificación de asignación de 1 para TeamsAppSetupPolicy y TeamsMeetingBroadcastPolicy y una clasificación de 2 para TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="84597-390">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="84597-391">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-391">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="84597-392">Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directivas a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="84597-392">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="84597-393">Use el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="84597-393">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="84597-394">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="84597-394">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="84597-395">Puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="84597-395">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="84597-396">Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="84597-396">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="84597-397">Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="84597-397">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="84597-398">Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario.</span><span class="sxs-lookup"><span data-stu-id="84597-398">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="84597-399">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="84597-399">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="84597-400">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="84597-400">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="84597-401">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="84597-401">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="84597-402">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="84597-402">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="84597-403">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84597-403">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="84597-404">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si todavía no lo ha hecho).</span><span class="sxs-lookup"><span data-stu-id="84597-404">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="84597-405">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="84597-405">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="84597-406">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="84597-406">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="84597-407">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="84597-407">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="84597-408">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="84597-408">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="84597-409">En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar el paquete de directivas Education_PrimaryStudent a un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="84597-409">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="84597-410">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="84597-410">Get the status of a batch assignment</span></span>

<span data-ttu-id="84597-411">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="84597-411">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="84597-412">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="84597-412">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="84597-413">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="84597-413">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="84597-414">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="84597-414">Related topics</span></span>

[<span data-ttu-id="84597-415">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="84597-415">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
