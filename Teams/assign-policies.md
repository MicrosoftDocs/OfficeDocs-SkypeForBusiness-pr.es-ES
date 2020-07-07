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
ms.openlocfilehash: 161a979578f24b351c93e870a562e6c4104b52d0
ms.sourcegitcommit: ac36d3923095a4321dad14fdf23c98358affd10c
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049447"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="f503f-103">Asignar directivas a los usuarios de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="f503f-104">Una de las características descritas en este artículo, [asignación de directiva a grupos con el centro de administración de Microsoft Teams](#using-the-microsoft-teams-admin-center-3)todavía no se ha publicado.</span><span class="sxs-lookup"><span data-stu-id="f503f-104">One of the features discussed in this article, [policy assignment to groups using the Microsoft Teams admin center](#using-the-microsoft-teams-admin-center-3), hasn't yet been released.</span></span> <span data-ttu-id="f503f-105">Se ha anunciado y pronto estará disponible.</span><span class="sxs-lookup"><span data-stu-id="f503f-105">It's been announced, and it's coming soon.</span></span>
> <span data-ttu-id="f503f-106">Para estar al día del estado de versión de esta característica, consulte la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="f503f-106">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="f503f-107">Como administrador, use directivas para controlar las características de teams que están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="f503f-107">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="f503f-108">Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por citar algunas.</span><span class="sxs-lookup"><span data-stu-id="f503f-108">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="f503f-109">Las organizaciones tienen diferentes tipos de usuarios con necesidades exclusivas y directivas personalizadas que usted crea y asigna le permiten adaptar la configuración de directivas a distintos conjuntos de usuarios según esas necesidades.</span><span class="sxs-lookup"><span data-stu-id="f503f-109">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="f503f-110">Para facilitar la administración de directivas de su organización, Teams ofrece varias formas de asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f503f-110">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="f503f-111">Puede asignar una directiva directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes, o a un grupo del que son miembros los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f503f-111">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="f503f-112">También puede usar paquetes de directivas para asignar una colección preconfigurada de directivas a los usuarios de su organización que tengan roles similares.</span><span class="sxs-lookup"><span data-stu-id="f503f-112">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="f503f-113">La opción que elija dependerá del número de directivas que esté administrando y del número de usuarios a los que va a asignar.</span><span class="sxs-lookup"><span data-stu-id="f503f-113">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="f503f-114">Al configurar las directivas globales (predeterminada para toda la organización) de modo que se apliquen al mayor número de usuarios de su organización, solo tiene que asignar directivas a aquellos usuarios que requieran directivas especializadas.</span><span class="sxs-lookup"><span data-stu-id="f503f-114">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="f503f-115">En este artículo se describen las diferentes maneras en las que puede asignar directivas a los usuarios y las situaciones recomendadas para Cuándo usarlas.</span><span class="sxs-lookup"><span data-stu-id="f503f-115">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="f503f-116">¿Qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="f503f-116">Which policy takes precedence?</span></span>

<span data-ttu-id="f503f-117">Un usuario tiene una directiva vigente para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-117">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="f503f-118">Es posible o incluso probable que un usuario tenga asignada directamente una directiva y también es miembro de uno o más grupos a los que se ha asignado una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="f503f-118">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="f503f-119">En estos tipos de escenarios, ¿qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="f503f-119">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="f503f-120">La Directiva efectiva del usuario se determina según las reglas de prioridad, de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="f503f-120">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="f503f-121">Si un usuario tiene asignada directamente una directiva (ya sea de forma individual o mediante una asignación por lotes), tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="f503f-121">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="f503f-122">En el ejemplo siguiente, la Directiva efectiva del usuario es la Lincoln cuadrada de la reunión, que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-122">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva asignada directamente](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="f503f-124">Si un usuario no tiene asignada directamente una directiva de un tipo determinado, tendrá prioridad la directiva asignada a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-124">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="f503f-125">Si un usuario es miembro de varios grupos, tiene prioridad la Directiva que tiene la mayor [clasificación de asignación de grupo](#group-assignment-ranking) para el tipo de directiva determinado.</span><span class="sxs-lookup"><span data-stu-id="f503f-125">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="f503f-126">En este ejemplo, la Directiva efectiva del usuario es el equipo de ejecución y la Directiva de alta definición, que tiene la mayor clasificación de asignación relativa a otros grupos de los que el usuario es miembro y al que también se les ha asignado una directiva del mismo tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-126">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama que muestra cómo tiene prioridad una directiva heredada del grupo](media/assign-policies-example-group.png)

<span data-ttu-id="f503f-128">Si un usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario recibirá la directiva global (opción predeterminada para toda la organización) para ese tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-128">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="f503f-129">Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f503f-129">Here's an example.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva global](media/assign-policies-example-global.png)

<span data-ttu-id="f503f-131">Para obtener más información, vea [reglas de prioridad](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="f503f-131">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="f503f-132">Formas de asignar directivas</span><span class="sxs-lookup"><span data-stu-id="f503f-132">Ways to assign policies</span></span>

<span data-ttu-id="f503f-133">A continuación se ofrece una descripción general de las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno.</span><span class="sxs-lookup"><span data-stu-id="f503f-133">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="f503f-134">Haga clic en los vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f503f-134">Click the links to learn more.</span></span>

<span data-ttu-id="f503f-135">Antes de asignar directivas a usuarios individuales o grupos, primero [establezca las directivas globales (valor predeterminado de organización)](#set-the-global-policies) para que se apliquen al mayor número de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="f503f-135">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="f503f-136">Una vez configuradas las directivas globales, solo tendrá que asignar directivas a aquellos usuarios que requieran directivas especializadas.</span><span class="sxs-lookup"><span data-stu-id="f503f-136">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="f503f-137">Haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="f503f-137">Do this</span></span>  |<span data-ttu-id="f503f-138">Si...</span><span class="sxs-lookup"><span data-stu-id="f503f-138">If...</span></span>  | <span data-ttu-id="f503f-139">Usar...</span><span class="sxs-lookup"><span data-stu-id="f503f-139">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="f503f-140">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="f503f-140">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="f503f-141">Ya está familiarizado con Teams y solo necesita asignar una o dos directivas a un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f503f-141">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="f503f-142">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="f503f-142">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="f503f-143">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="f503f-143">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="f503f-144">Debe asignar varias directivas a conjuntos específicos de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="f503f-144">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="f503f-145">Por ejemplo, asigne el paquete de directivas Educación (profesor) a los profesores de su escuela para proporcionarles acceso completo a chats, llamadas y reuniones, y al paquete de directivas Educación (estudiante secundario escolar) a los estudiantes secundarios para limitar ciertas funciones como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="f503f-145">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="f503f-146">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-146">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="f503f-147">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="f503f-147">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="f503f-148">Debe asignar directivas a grandes conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f503f-148">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="f503f-149">Por ejemplo, desea asignar una directiva a cientos o miles de usuarios de su organización al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f503f-149">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="f503f-150">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-150">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="f503f-151">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="f503f-151">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="f503f-152">Debe asignar directivas en función de la pertenencia a grupos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-152">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="f503f-153">Por ejemplo, desea asignar una directiva a todos los usuarios de un grupo de seguridad o de una unidad de organización.</span><span class="sxs-lookup"><span data-stu-id="f503f-153">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="f503f-154">El centro de administración de Microsoft Teams (próximamente) o cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-154">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="f503f-155">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="f503f-155">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="f503f-156">Debe asignar varias directivas a un lote de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="f503f-156">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="f503f-157">Por ejemplo, asigne el paquete de directivas Educación (profesor) a todos los profesores de su escuela mediante la asignación por lotes para proporcionarles acceso total a chats, llamadas y reuniones, y asigne el paquete de directivas Educación (estudiante secundario) a un lote de estudiantes secundarios para limitar ciertas capacidades como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="f503f-157">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="f503f-158">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-158">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="f503f-159">Asignar un paquete de directivas a un grupo (próximamente)</span><span class="sxs-lookup"><span data-stu-id="f503f-159">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="f503f-160">Establecer las directivas globales</span><span class="sxs-lookup"><span data-stu-id="f503f-160">Set the global policies</span></span>

<span data-ttu-id="f503f-161">Siga estos pasos para establecer las directivas globales (valor predeterminado de la organización) para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f503f-162">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="f503f-163">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de directivas del tipo de directiva que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="f503f-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="f503f-164">Por ejemplo, **Teams**  >  **Policies**, directivas de reuniones de **reuniones**  >  **Meetings policies**, **directivas de mensajería**o directivas de llamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="f503f-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="f503f-165">Seleccione la directiva **global (opción predeterminada para toda la organización)** para ver la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="f503f-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="f503f-166">Actualice la Directiva según sea necesario y, a continuación, seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f503f-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f503f-167">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f503f-167">Using PowerShell</span></span>

<span data-ttu-id="f503f-168">Para establecer las directivas globales mediante PowerShell, use el identificador global.</span><span class="sxs-lookup"><span data-stu-id="f503f-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="f503f-169">Para empezar, revisamos la directiva global actual para determinar qué configuración desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="f503f-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="f503f-170">A continuación, actualice la directiva global según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f503f-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="f503f-171">Solo tiene que especificar los valores de la configuración que quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="f503f-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="f503f-172">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="f503f-172">Assign a policy to individual users</span></span>

<span data-ttu-id="f503f-173">Siga estos pasos para asignar una directiva a un usuario individual o a un número reducido de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="f503f-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f503f-174">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f503f-175">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="f503f-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="f503f-176">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="f503f-177">Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.</span><span class="sxs-lookup"><span data-stu-id="f503f-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="f503f-178">Seleccione la Directiva que desea asignar y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f503f-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="f503f-179">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f503f-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="f503f-180">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="f503f-181">Seleccione la Directiva que desea asignar haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="f503f-182">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f503f-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="f503f-183">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f503f-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="f503f-184">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="f503f-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="f503f-185">Cuando haya terminado de agregar usuarios, seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f503f-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f503f-186">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f503f-186">Using PowerShell</span></span>

<span data-ttu-id="f503f-187">Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo.</span><span class="sxs-lookup"><span data-stu-id="f503f-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="f503f-188">Use el ```Grant-``` cmdlet para un tipo de directiva determinado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="f503f-189">Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una política de reunión de Teams a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f503f-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="f503f-190">Estos cmdlets están incluidos en el módulo de PowerShell de Skype empresarial online y están documentados en la [Referencia del cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f503f-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="f503f-191">Descargue e instale el [módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si todavía no lo ha hecho) y, a continuación, ejecute lo siguiente para conectarse a Skype empresarial online e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="f503f-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="f503f-192">En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiantes a un usuario denominado Reda.</span><span class="sxs-lookup"><span data-stu-id="f503f-192">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="f503f-193">Para obtener más información, lea [Administración de directivas a través de PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="f503f-193">To learn more, read [Managing policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="f503f-194">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="f503f-194">Assign a policy package</span></span>

<span data-ttu-id="f503f-195">Un paquete de directivas de Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles iguales o similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="f503f-195">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="f503f-196">Cada paquete de directivas está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten actividades típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="f503f-196">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="f503f-197">Algunos ejemplos de paquetes de directivas son el paquete educativo (profesor) y el paquete de salud (trabajador clínico).</span><span class="sxs-lookup"><span data-stu-id="f503f-197">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="f503f-198">Cuando se asigna un paquete de directivas a los usuarios, se crean las directivas del paquete y, después, se puede personalizar la configuración de cada Directiva del paquete para satisfacer las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f503f-198">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="f503f-199">Para obtener más información sobre los paquetes de directivas, incluidas las instrucciones paso a paso sobre cómo asignarlos y administrarlos, consulte [administrar paquetes de directivas en Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f503f-199">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="f503f-200">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="f503f-200">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f503f-201">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-201">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f503f-202">Para asignar una directiva a usuarios en bloque:</span><span class="sxs-lookup"><span data-stu-id="f503f-202">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="f503f-203">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f503f-203">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="f503f-204">Busque los usuarios a los que desea asignar la Directiva o filtre la vista para mostrar los usuarios que desea.</span><span class="sxs-lookup"><span data-stu-id="f503f-204">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="f503f-205">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f503f-205">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="f503f-206">Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="f503f-206">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="f503f-207">Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f503f-207">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="f503f-208">Para ver el estado de la asignación de Directiva, en la pancarta que aparece en la parte superior de la página **usuarios** después de hacer clic en **aplicar** para enviar la asignación de Directiva, haga clic en **registro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="f503f-208">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="f503f-209">O bien, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel**y, a continuación, en **registro de actividades**, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="f503f-209">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="f503f-210">En el registro de actividades se muestran asignaciones de directivas de los lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="f503f-210">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="f503f-211">Para obtener más información, vea [ver las asignaciones de directivas en el registro de actividades](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="f503f-211">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f503f-212">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f503f-212">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="f503f-213">Actualmente, la asignación de directivas por lotes con PowerShell no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="f503f-213">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="f503f-214">Vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="f503f-214">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="f503f-215">Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="f503f-215">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="f503f-216">Use el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para enviar un lote de usuarios y la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f503f-216">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="f503f-217">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="f503f-217">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="f503f-218">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="f503f-218">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="f503f-219">Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="f503f-219">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="f503f-220">Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="f503f-220">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="f503f-221">Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-221">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="f503f-222">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="f503f-222">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="f503f-223">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="f503f-223">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="f503f-224">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="f503f-224">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="f503f-225">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="f503f-225">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f503f-226">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-226">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="f503f-227">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="f503f-227">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="f503f-228">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f503f-228">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="f503f-229">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="f503f-229">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="f503f-230">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="f503f-230">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="f503f-231">Instalar y conectarse al módulo de Azure AD PowerShell for Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="f503f-231">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="f503f-232">Es posible que también desee [Descargar e instalar el módulo Azure ad PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (si todavía no lo ha hecho) y conectarse a Azure ad para poder recuperar una lista de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="f503f-232">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="f503f-233">Ejecute lo siguiente para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f503f-233">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="f503f-234">Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a teams.</span><span class="sxs-lookup"><span data-stu-id="f503f-234">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="f503f-235">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="f503f-235">Assign a policy to a batch of users</span></span>

<span data-ttu-id="f503f-236">En este ejemplo, usamos el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para asignar una directiva de configuración de aplicación denominada Directiva de configuración de la aplicación de RRHH a un lote de usuarios que aparece en el archivo Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="f503f-236">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="f503f-237">En este ejemplo, se conectará a Azure AD para recuperar una colección de usuarios y, a continuación, asignar una directiva de mensajería llamada nueva Directiva de mensajería de contratación a un lote de usuarios especificado mediante su dirección SIP.</span><span class="sxs-lookup"><span data-stu-id="f503f-237">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="f503f-238">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f503f-238">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="f503f-239">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="f503f-239">Get the status of a batch assignment</span></span>

<span data-ttu-id="f503f-240">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="f503f-240">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="f503f-241">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="f503f-241">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="f503f-242">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f503f-242">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="f503f-243">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="f503f-243">Assign a policy to a group</span></span>

<span data-ttu-id="f503f-244">La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="f503f-244">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="f503f-245">La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="f503f-245">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="f503f-246">A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda.</span><span class="sxs-lookup"><span data-stu-id="f503f-246">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="f503f-247">La asignación de directivas a grupos se recomienda para grupos de hasta 50.000 usuarios, pero también funciona con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="f503f-247">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="f503f-248">Al asignar la Directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-248">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="f503f-249">Sin embargo, ten en cuenta que la propagación de la asignación de directiva a miembros del grupo se realiza como una operación en segundo plano y puede llevar algún tiempo, según el tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-249">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="f503f-250">Lo mismo sucede cuando se elimina la asignación de una directiva de un grupo, o cuando se agregan miembros a un grupo o se quitan de él.</span><span class="sxs-lookup"><span data-stu-id="f503f-250">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="f503f-251">Lo que debe saber sobre la asignación de directivas a grupos</span><span class="sxs-lookup"><span data-stu-id="f503f-251">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="f503f-252">Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-252">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="f503f-253">Reglas de prioridad</span><span class="sxs-lookup"><span data-stu-id="f503f-253">Precedence rules</span></span>

<span data-ttu-id="f503f-254">Para un tipo de directiva determinado, la Directiva efectiva del usuario se determina de acuerdo con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f503f-254">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="f503f-255">Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo que esté asignada a un grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-255">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="f503f-256">En otras palabras, si un usuario tiene asignada directamente una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-256">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="f503f-257">Esto también significa que si un usuario tiene una directiva de un determinado tipo que se le asignó directamente, tendrá que quitar esa Directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-257">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="f503f-258">Si un usuario no tiene una directiva asignada directamente y es miembro de dos o más grupos y cada grupo tiene una directiva del mismo tipo que tiene asignada, el usuario hereda la Directiva de la asignación de grupo que tiene la clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="f503f-258">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="f503f-259">Si un usuario no es miembro de ningún grupo al que se le ha asignado una directiva, la directiva global (opción predeterminada para toda la organización) para ese tipo de Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-259">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="f503f-260">La Directiva efectiva de un usuario se actualiza de acuerdo con estas reglas cuando se agrega o se quita un usuario de un grupo al que se asigna una directiva, se elimina la asignación de una directiva de un grupo o se quita una directiva que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-260">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="f503f-261">Clasificación de asignación de grupo</span><span class="sxs-lookup"><span data-stu-id="f503f-261">Group assignment ranking</span></span>
 
<span data-ttu-id="f503f-262">Cuando se asigna una directiva a un grupo, se especifica una clasificación para la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-262">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="f503f-263">Se usa para determinar qué directiva debe heredar un usuario como su Directiva efectiva si el usuario es miembro de dos o más grupos y se le asigna una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="f503f-263">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="f503f-264">La clasificación de la asignación de grupo es relativa a otras asignaciones de grupo del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="f503f-264">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="f503f-265">Por ejemplo, si va a asignar una directiva de llamadas a dos grupos, establezca la jerarquía de una asignación en 1 y la otra en 2, siendo 1 el ranking más alto.</span><span class="sxs-lookup"><span data-stu-id="f503f-265">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="f503f-266">La clasificación de la asignación de grupo indica qué pertenencia de grupo es más importante o más relevante que otras pertenencias a grupos en relación con la herencia.</span><span class="sxs-lookup"><span data-stu-id="f503f-266">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="f503f-267">Por ejemplo, supongamos que tiene dos grupos, guarda empleados y administradores de la tienda.</span><span class="sxs-lookup"><span data-stu-id="f503f-267">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="f503f-268">Ambos grupos tienen asignada una directiva de llamadas de equipo, almacenan empleados que llaman a la Directiva de llamadas y a los jefes de tienda, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f503f-268">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="f503f-269">En el caso de un administrador de tienda que esté en ambos grupos, su rol como director es más relevante que su rol como empleado, por lo que la política de llamadas que se asigna al grupo de administradores de la tienda debería tener una clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="f503f-269">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="f503f-270">Mesa</span><span class="sxs-lookup"><span data-stu-id="f503f-270">Group</span></span> |<span data-ttu-id="f503f-271">Nombre de directiva de llamadas de equipo</span><span class="sxs-lookup"><span data-stu-id="f503f-271">Teams calling policy name</span></span>  |<span data-ttu-id="f503f-272">Clasificación</span><span class="sxs-lookup"><span data-stu-id="f503f-272">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="f503f-273">Administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="f503f-273">Store Managers</span></span>   |<span data-ttu-id="f503f-274">Directiva de llamadas a administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="f503f-274">Store Managers Calling Policy</span></span>         |<span data-ttu-id="f503f-275">1</span><span class="sxs-lookup"><span data-stu-id="f503f-275">1</span></span>|
|<span data-ttu-id="f503f-276">Almacenar empleados</span><span class="sxs-lookup"><span data-stu-id="f503f-276">Store Employees</span></span>    |<span data-ttu-id="f503f-277">Almacenar la política de llamadas</span><span class="sxs-lookup"><span data-stu-id="f503f-277">Store Employees Calling Policy</span></span>      |<span data-ttu-id="f503f-278">2</span><span class="sxs-lookup"><span data-stu-id="f503f-278">2</span></span>|

<span data-ttu-id="f503f-279">Si no especifica una clasificación, la asignación de directiva recibe la clasificación más baja.</span><span class="sxs-lookup"><span data-stu-id="f503f-279">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f503f-280">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-280">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f503f-281">**Aún no se ha publicado esta característica. Se ha anunciado y pronto estará disponible.**</span><span class="sxs-lookup"><span data-stu-id="f503f-281">**This feature hasn't yet been released. It's been announced, and it's coming soon.**</span></span>

> [!NOTE]
> <span data-ttu-id="f503f-282">Por el momento, la asignación de directivas a grupos con el centro de administración de Microsoft Teams solo está disponible para la Directiva de llamadas de equipos, la Directiva de reunión de Teams y la Directiva de mensajería de Teams.</span><span class="sxs-lookup"><span data-stu-id="f503f-282">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="f503f-283">Para otros tipos de directivas, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f503f-283">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="f503f-284">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-284">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="f503f-285">Por ejemplo, vaya a **Meetings**  >  **las directivas de reunión**de reuniones.</span><span class="sxs-lookup"><span data-stu-id="f503f-285">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="f503f-286">Seleccione la pestaña **asignación de directiva de grupo** .</span><span class="sxs-lookup"><span data-stu-id="f503f-286">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="f503f-287">Seleccione **Agregar grupo**y, a continuación, en el panel **asignar Directiva a grupo** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f503f-287">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="f503f-288">Busque y agregue el grupo al que desea asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-288">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="f503f-289">Establezca la clasificación de la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-289">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="f503f-290">Seleccione la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f503f-290">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="f503f-291">Seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f503f-291">Select **Apply**.</span></span>

<span data-ttu-id="f503f-292">Para quitar una asignación de directiva de grupo, en la pestaña **asignación de directiva de grupo** de la página de Directiva, seleccione la asignación de grupo y, a continuación, seleccione **quitar**.</span><span class="sxs-lookup"><span data-stu-id="f503f-292">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="f503f-293">Para cambiar la jerarquía de una asignación de grupo, primero debe quitar la asignación de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-293">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="f503f-294">Después, siga los pasos anteriores para asignar la Directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-294">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f503f-295">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f503f-295">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="f503f-296">Por el momento, la asignación de directivas a grupos con PowerShell no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="f503f-296">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="f503f-297">Vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="f503f-297">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f503f-298">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-298">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="f503f-299">Para obtener instrucciones paso a paso, consulte [instalar Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="f503f-299">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="f503f-300">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="f503f-300">Assign a policy to a group</span></span>

<span data-ttu-id="f503f-301">Use el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-301">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="f503f-302">Puede especificar un grupo mediante el identificador de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f503f-302">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="f503f-303">En este ejemplo, usamos el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva de reunión de Teams denominada Directiva de reunión de directores minoristas a un grupo con una clasificación de asignación de 1.</span><span class="sxs-lookup"><span data-stu-id="f503f-303">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="f503f-304">Para obtener más información, vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f503f-304">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="f503f-305">Obtener asignaciones de directivas para un grupo</span><span class="sxs-lookup"><span data-stu-id="f503f-305">Get policy assignments for a group</span></span>

<span data-ttu-id="f503f-306">Use el ```Get-CsGroupPolicyAssignment``` cmdlet para obtener todas las directivas asignadas a un grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-306">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="f503f-307">Ten en cuenta que los grupos siempre aparecen en la lista por su identificador de grupo aunque su dirección SIP o dirección de correo electrónico se hayan usado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-307">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="f503f-308">En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="f503f-308">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="f503f-309">En este ejemplo, se devuelven todos los grupos que tienen asignada una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="f503f-309">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="f503f-310">Para obtener más información, vea [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f503f-310">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="f503f-311">Quitar una directiva de un grupo</span><span class="sxs-lookup"><span data-stu-id="f503f-311">Remove a policy from a group</span></span>

<span data-ttu-id="f503f-312">Use el ```Remove-CsGroupPolicyAssignment``` cmdlet para quitar una directiva de un grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-312">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="f503f-313">Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y con una clasificación menor.</span><span class="sxs-lookup"><span data-stu-id="f503f-313">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="f503f-314">Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tengan una jerarquía de 3 y 4 se actualizarán para reflejar su nueva clasificación.</span><span class="sxs-lookup"><span data-stu-id="f503f-314">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="f503f-315">En las dos tablas siguientes se muestra este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f503f-315">The following two tables show this example.</span></span>

<span data-ttu-id="f503f-316">A continuación se ofrece una lista de las asignaciones de directivas y las prioridades de una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="f503f-316">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="f503f-317">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="f503f-317">Group name</span></span>  |<span data-ttu-id="f503f-318">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="f503f-318">Policy name</span></span>  |<span data-ttu-id="f503f-319">Clasificación</span><span class="sxs-lookup"><span data-stu-id="f503f-319">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f503f-320">Ventas</span><span class="sxs-lookup"><span data-stu-id="f503f-320">Sales</span></span>    |<span data-ttu-id="f503f-321">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="f503f-321">Sales policy</span></span>       | <span data-ttu-id="f503f-322">1</span><span class="sxs-lookup"><span data-stu-id="f503f-322">1</span></span>        |
|<span data-ttu-id="f503f-323">Región occidental</span><span class="sxs-lookup"><span data-stu-id="f503f-323">West Region</span></span>     |<span data-ttu-id="f503f-324">Política de la región occidental</span><span class="sxs-lookup"><span data-stu-id="f503f-324">West Region policy</span></span>         |<span data-ttu-id="f503f-325">2</span><span class="sxs-lookup"><span data-stu-id="f503f-325">2</span></span>         |
|<span data-ttu-id="f503f-326">Departamentos</span><span class="sxs-lookup"><span data-stu-id="f503f-326">Division</span></span>    |<span data-ttu-id="f503f-327">Política de división</span><span class="sxs-lookup"><span data-stu-id="f503f-327">Division policy</span></span>         |<span data-ttu-id="f503f-328">3</span><span class="sxs-lookup"><span data-stu-id="f503f-328">3</span></span>         |
|<span data-ttu-id="f503f-329">Secundaria</span><span class="sxs-lookup"><span data-stu-id="f503f-329">Subsidiary</span></span>   |<span data-ttu-id="f503f-330">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="f503f-330">Subsidiary policy</span></span>        |<span data-ttu-id="f503f-331">4</span><span class="sxs-lookup"><span data-stu-id="f503f-331">4</span></span>         |

<span data-ttu-id="f503f-332">Si quitamos la política de región occidental del grupo región oeste, las asignaciones y prioridades de directivas se actualizan de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="f503f-332">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="f503f-333">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="f503f-333">Group name</span></span>  |<span data-ttu-id="f503f-334">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="f503f-334">Policy name</span></span>  |<span data-ttu-id="f503f-335">Clasificación</span><span class="sxs-lookup"><span data-stu-id="f503f-335">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f503f-336">Ventas</span><span class="sxs-lookup"><span data-stu-id="f503f-336">Sales</span></span>    |<span data-ttu-id="f503f-337">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="f503f-337">Sales policy</span></span>       | <span data-ttu-id="f503f-338">1</span><span class="sxs-lookup"><span data-stu-id="f503f-338">1</span></span>        |
|<span data-ttu-id="f503f-339">Departamentos</span><span class="sxs-lookup"><span data-stu-id="f503f-339">Division</span></span>    |<span data-ttu-id="f503f-340">Política de división</span><span class="sxs-lookup"><span data-stu-id="f503f-340">Division policy</span></span>         |<span data-ttu-id="f503f-341">2</span><span class="sxs-lookup"><span data-stu-id="f503f-341">2</span></span>         |
|<span data-ttu-id="f503f-342">Secundaria</span><span class="sxs-lookup"><span data-stu-id="f503f-342">Subsidiary</span></span>   |<span data-ttu-id="f503f-343">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="f503f-343">Subsidiary policy</span></span>        |<span data-ttu-id="f503f-344">3</span><span class="sxs-lookup"><span data-stu-id="f503f-344">3</span></span>        |

<span data-ttu-id="f503f-345">En este ejemplo, quitamos la política de reuniones de Teams de un grupo.</span><span class="sxs-lookup"><span data-stu-id="f503f-345">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="f503f-346">Para obtener más información, consulte [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f503f-346">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="f503f-347">Cambiar una asignación de directiva para un grupo</span><span class="sxs-lookup"><span data-stu-id="f503f-347">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="f503f-348">El ```Set-CsGroupPolicyAssignment``` cmdlet estará disponible pronto.</span><span class="sxs-lookup"><span data-stu-id="f503f-348">The ```Set-CsGroupPolicyAssignment``` cmdlet will be available soon.</span></span> <span data-ttu-id="f503f-349">Mientras tanto, para cambiar una asignación de directiva de grupo, puede quitar la asignación de directiva actual del grupo y, a continuación, agregar una nueva asignación de directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-349">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="f503f-350">Después de asignar una directiva a un grupo, puede usar el ```Set-CsGroupPolicyAssignment``` cmdlet para cambiar la asignación de directivas del grupo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f503f-350">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignment``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="f503f-351">Cambiar la clasificación</span><span class="sxs-lookup"><span data-stu-id="f503f-351">Change the ranking</span></span>
- <span data-ttu-id="f503f-352">Cambiar la Directiva de un tipo de directiva determinado</span><span class="sxs-lookup"><span data-stu-id="f503f-352">Change the policy of a given policy type</span></span>
- <span data-ttu-id="f503f-353">Cambiar la Directiva de un determinado tipo de directiva y la clasificación</span><span class="sxs-lookup"><span data-stu-id="f503f-353">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="f503f-354">En este ejemplo, cambiamos la Directiva de los equipos de un grupo a una directiva llamada SupportCallPark y la clasificación de asignación a 3.</span><span class="sxs-lookup"><span data-stu-id="f503f-354">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="f503f-355">Para obtener más información, consulte [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f503f-355">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>



#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="f503f-356">Cambiar la Directiva efectiva de un usuario</span><span class="sxs-lookup"><span data-stu-id="f503f-356">Change the effective policy for a user</span></span>

<span data-ttu-id="f503f-357">Este es un ejemplo de cómo cambiar la Directiva efectiva para un usuario que tiene asignada directamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="f503f-357">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="f503f-358">En primer lugar, usamos el ```Get-CsUserPolicyAssignment``` cmdlet junto con el ```PolicySource``` parámetro para obtener detalles de los equipos de reunión de las directivas de difusión asociados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-358">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="f503f-359">Para obtener más información, vea [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f503f-359">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="f503f-360">En la salida se muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada eventos de empleados, que tiene prioridad sobre la Directiva denominada eventos de proveedor que se asignan a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-360">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="f503f-361">Ahora, quitamos la Directiva de eventos de empleados del usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-361">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="f503f-362">Esto significa que el usuario ya no tiene una directiva de difusión de reunión de equipos que se les asignó directamente y heredará la Directiva de eventos en vivo de proveedores que se asigna al grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-362">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="f503f-363">Use el siguiente cmdlet en el módulo de PowerShell de Skype empresarial para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f503f-363">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="f503f-364">Puede usar el siguiente cmdlet en el módulo de PowerShell de Teams para hacerlo a escala mediante una asignación de Directiva por lotes, donde $users es una lista de los usuarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="f503f-364">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="f503f-365">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="f503f-365">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="f503f-366">Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directivas a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="f503f-366">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="f503f-367">Use el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para enviar un lote de usuarios y el paquete de directivas que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f503f-367">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="f503f-368">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="f503f-368">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="f503f-369">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="f503f-369">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="f503f-370">Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="f503f-370">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="f503f-371">Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="f503f-371">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="f503f-372">Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario.</span><span class="sxs-lookup"><span data-stu-id="f503f-372">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="f503f-373">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="f503f-373">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="f503f-374">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="f503f-374">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="f503f-375">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="f503f-375">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="f503f-376">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="f503f-376">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f503f-377">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-377">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="f503f-378">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si todavía no lo ha hecho).</span><span class="sxs-lookup"><span data-stu-id="f503f-378">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="f503f-379">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f503f-379">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="f503f-380">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="f503f-380">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="f503f-381">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="f503f-381">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="f503f-382">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="f503f-382">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="f503f-383">En este ejemplo, usamos el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para asignar el paquete de directivas Education_PrimaryStudent a un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f503f-383">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="f503f-384">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f503f-384">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="f503f-385">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="f503f-385">Get the status of a batch assignment</span></span>

<span data-ttu-id="f503f-386">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="f503f-386">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="f503f-387">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="f503f-387">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="f503f-388">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f503f-388">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="f503f-389">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f503f-389">Related topics</span></span>

[<span data-ttu-id="f503f-390">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="f503f-390">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
