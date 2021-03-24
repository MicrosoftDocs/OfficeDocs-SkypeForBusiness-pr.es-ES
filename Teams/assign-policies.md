---
title: Asignar directivas a los usuarios de Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: a77e1cd6a6caf562edcdca0a49f200e6678bd6f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111416"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="70f41-103">Asignar directivas a los usuarios de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="70f41-104">Como administrador, usa directivas para controlar las características de Teams que están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="70f41-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="70f41-105">Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por nombrar solo algunas.</span><span class="sxs-lookup"><span data-stu-id="70f41-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="70f41-106">Las organizaciones tienen diferentes tipos de usuarios con necesidades únicas.</span><span class="sxs-lookup"><span data-stu-id="70f41-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="70f41-107">Las directivas personalizadas que cree y asigne le permiten adaptar la configuración de directiva a diferentes conjuntos de usuarios en función de esas necesidades.</span><span class="sxs-lookup"><span data-stu-id="70f41-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="70f41-108">Para administrar fácilmente las directivas de su organización, Teams ofrece varias formas de asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="70f41-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="70f41-109">Asigne una directiva directamente a los usuarios, ya sea individualmente o a escala a través de una asignación por lotes, o a un grupo del que los usuarios sean miembros.</span><span class="sxs-lookup"><span data-stu-id="70f41-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="70f41-110">También puede usar paquetes de directivas para asignar una colección predefinida de directivas a los usuarios de su organización que tengan roles similares.</span><span class="sxs-lookup"><span data-stu-id="70f41-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="70f41-111">La opción que elija depende del número de directivas que administra y del número de usuarios a los que asigne directivas.</span><span class="sxs-lookup"><span data-stu-id="70f41-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="70f41-112">Las directivas globales (predeterminadas para toda la organización) se aplican al mayor número de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="70f41-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="70f41-113">Solo tiene que asignar directivas a los usuarios que requieren directivas especializadas.</span><span class="sxs-lookup"><span data-stu-id="70f41-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="70f41-114">En este artículo se describen las diferentes formas de asignar directivas a los usuarios y los escenarios recomendados para cuándo usar qué.</span><span class="sxs-lookup"><span data-stu-id="70f41-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="70f41-115">¿Qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="70f41-115">Which policy takes precedence?</span></span>

<span data-ttu-id="70f41-116">Un usuario tiene una directiva eficaz para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="70f41-117">Es posible, o incluso probable, que a un usuario se le asigne directamente una directiva y que también sea miembro de uno o varios grupos a los que se ha asignado una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="70f41-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="70f41-118">En estos tipos de escenarios, ¿qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="70f41-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="70f41-119">La directiva efectiva de un usuario se determina según las reglas de prioridad, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="70f41-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="70f41-120">Si a un usuario se le asigna directamente una directiva (ya sea individualmente o a través de una asignación por lotes), esa directiva tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="70f41-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="70f41-121">En el siguiente ejemplo visual, la directiva efectiva del usuario es la directiva de reunión de Lincoln Square, que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama que muestra cómo una directiva asignada directamente tiene prioridad](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="70f41-123">Si a un usuario no se le asigna directamente una directiva de un tipo determinado, la directiva asignada a un grupo del que el usuario es miembro tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="70f41-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="70f41-124">Si un usuario es miembro de varios grupos, [](#group-assignment-ranking) la directiva que tiene la clasificación de asignaciones de grupo más alta para el tipo de directiva determinado tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="70f41-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="70f41-125">En este ejemplo visual, la directiva efectiva del usuario es la directiva Exec Teams y HD, que tiene la clasificación de asignaciones más alta con respecto a otros grupos a los que el usuario es miembro y a los que también se les asigna una directiva del mismo tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama que muestra cómo una directiva heredada del grupo tiene prioridad](media/assign-policies-example-group.png)

<span data-ttu-id="70f41-127">Si a un usuario no se le asigna directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario obtiene la directiva global (predeterminada para toda la organización) para ese tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="70f41-128">Este es un ejemplo visual.</span><span class="sxs-lookup"><span data-stu-id="70f41-128">Here's a visual example.</span></span>

![Diagrama que muestra cómo una directiva global tiene prioridad](media/assign-policies-example-global.png)

<span data-ttu-id="70f41-130">Para obtener más información, vea [Reglas de prioridad](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="70f41-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="70f41-131">Formas de asignar directivas</span><span class="sxs-lookup"><span data-stu-id="70f41-131">Ways to assign policies</span></span>

<span data-ttu-id="70f41-132">A continuación se ofrece información general sobre las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="70f41-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="70f41-133">Seleccione los vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="70f41-133">Select the links to learn more.</span></span>

<span data-ttu-id="70f41-134">Antes de asignar directivas a usuarios o grupos individuales, empiece estableciendo las directivas globales (predeterminadas para toda la [organización)](#set-the-global-policies) para que se apliquen al mayor número de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="70f41-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="70f41-135">Una vez establecidas las directivas globales, solo tendrá que asignar directivas a los usuarios que requieran directivas especializadas.</span><span class="sxs-lookup"><span data-stu-id="70f41-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="70f41-136">Haga esto</span><span class="sxs-lookup"><span data-stu-id="70f41-136">Do this</span></span>  |<span data-ttu-id="70f41-137">Si...</span><span class="sxs-lookup"><span data-stu-id="70f41-137">If...</span></span>  | <span data-ttu-id="70f41-138">Usar...</span><span class="sxs-lookup"><span data-stu-id="70f41-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="70f41-139">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="70f41-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="70f41-140">Es nuevo en Teams y acaba de empezar o solo necesita asignar una o un par de directivas a un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="70f41-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="70f41-141">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="70f41-142">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="70f41-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="70f41-143">Asigne directivas basadas en la pertenencia a un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="70f41-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="70f41-144">Por ejemplo, asigne una directiva a todos los usuarios de un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="70f41-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="70f41-145">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="70f41-146">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="70f41-147">Asignar directivas a grandes conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="70f41-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="70f41-148">Por ejemplo, asigne una directiva a cientos o miles de usuarios de su organización a la vez.</span><span class="sxs-lookup"><span data-stu-id="70f41-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="70f41-149">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="70f41-150">Asignar un paquete de directiva a los usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="70f41-151">Asigne varias directivas a conjuntos específicos de usuarios de su organización que tengan los mismos roles o similares.</span><span class="sxs-lookup"><span data-stu-id="70f41-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="70f41-152">Por ejemplo, asigne el paquete de directivas educación (profesor) a los profesores de su escuela para darles acceso completo a chats, llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="70f41-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="70f41-153">Asigne el paquete de directivas Educación (estudiante de secundaria) a los alumnos secundarios para limitar ciertas capacidades, como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="70f41-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="70f41-154">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="70f41-155">[Asignar un paquete de directiva a un grupo](#assign-a-policy-package-to-a-group) (en versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="70f41-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="70f41-156">Asigne varias directivas a un grupo de usuarios de su organización que tengan los mismos roles o roles similares.</span><span class="sxs-lookup"><span data-stu-id="70f41-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="70f41-157">Por ejemplo, asigne un paquete de directiva a todos los usuarios de un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="70f41-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="70f41-158">El Centro de administración de Microsoft Teams (próximamente) o cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="70f41-159">Asignar un paquete de directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="70f41-160">Asigne varias directivas a un lote de usuarios de su organización que tengan los mismos roles o similares.</span><span class="sxs-lookup"><span data-stu-id="70f41-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="70f41-161">Por ejemplo, asigne el paquete de directivas Educación (Profesor) a todos los profesores de su escuela con asignación por lotes para darles acceso completo a chats, llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="70f41-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="70f41-162">Asigne el paquete de directivas Educación (estudiante de secundaria) a un lote de alumnos secundarios para limitar ciertas capacidades, como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="70f41-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="70f41-163">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="70f41-164">Establecer las directivas globales</span><span class="sxs-lookup"><span data-stu-id="70f41-164">Set the global policies</span></span>

<span data-ttu-id="70f41-165">Siga estos pasos para establecer las directivas globales (predeterminadas para toda la organización) para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="70f41-166">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="70f41-167">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la página de directiva del tipo de directiva que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="70f41-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="70f41-168">Por ejemplo, directivas **de Teams**  >  **Teams,** **directivas de**  >  reuniones, **directivas de** mensajería o directivas de **llamadas** de  >  **voz.**</span><span class="sxs-lookup"><span data-stu-id="70f41-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="70f41-169">Seleccione la **directiva Global (predeterminada para toda la organización)** para ver la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="70f41-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="70f41-170">Actualice la directiva según sea necesario y, a continuación, **seleccione Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="70f41-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="70f41-171">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="70f41-171">Using PowerShell</span></span>

<span data-ttu-id="70f41-172">Para establecer las directivas globales con PowerShell, use el identificador global.</span><span class="sxs-lookup"><span data-stu-id="70f41-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="70f41-173">Empiece revisando la directiva global actual para determinar qué configuración desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="70f41-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="70f41-174">A continuación, actualice la directiva global según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="70f41-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="70f41-175">Solo tiene que especificar valores para la configuración que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="70f41-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="70f41-176">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="70f41-176">Assign a policy to individual users</span></span>

<span data-ttu-id="70f41-177">Siga estos pasos para asignar una directiva a un usuario individual o a un pequeño número de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="70f41-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="70f41-178">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="70f41-179">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="70f41-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="70f41-180">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, a continuación, seleccione el usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="70f41-181">Seleccione el usuario haciendo clic a la izquierda del nombre de usuario y, a continuación, **seleccione Editar configuración.**</span><span class="sxs-lookup"><span data-stu-id="70f41-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="70f41-182">Seleccione la directiva que desea asignar y, a continuación, **seleccione Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="70f41-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="70f41-183">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70f41-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="70f41-184">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la página de directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="70f41-185">Seleccione la directiva que desea asignar haciendo clic a la izquierda del nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="70f41-186">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="70f41-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="70f41-187">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="70f41-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="70f41-188">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="70f41-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="70f41-189">Cuando haya terminado de agregar usuarios, seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="70f41-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="70f41-190">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="70f41-190">Use PowerShell</span></span>

<span data-ttu-id="70f41-191">Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo.</span><span class="sxs-lookup"><span data-stu-id="70f41-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="70f41-192">Use el ```Grant-``` cmdlet de un tipo de directiva determinado para asignar la directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="70f41-193">Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una directiva de reunión de Teams a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="70f41-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="70f41-194">Estos cmdlets se incluyen en el módulo de PowerShell de Teams y se documentan en la referencia de [cmdlet de Skype Empresarial.](/powershell/skype/intro?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="70f41-194">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="70f41-195">Descargue e instale la versión pública de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) de Teams (si aún no lo ha hecho) y ejecute lo siguiente para conectarse.</span><span class="sxs-lookup"><span data-stu-id="70f41-195">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="70f41-196">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="70f41-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="70f41-197">Si usa la última versión pública de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="70f41-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="70f41-198">En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiantes a un usuario denominado Reda.</span><span class="sxs-lookup"><span data-stu-id="70f41-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="70f41-199">Para obtener más información, lea [Administrar directivas a través de PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="70f41-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="70f41-200">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="70f41-200">Assign a policy to a group</span></span>

<span data-ttu-id="70f41-201">La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="70f41-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="70f41-202">La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="70f41-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="70f41-203">A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.</span><span class="sxs-lookup"><span data-stu-id="70f41-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="70f41-204">La asignación de directivas a grupos se recomienda para grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="70f41-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="70f41-205">Al asignar la directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="70f41-206">Sin embargo, la propagación de la asignación de directivas a los miembros del grupo se realiza como una operación en segundo plano y puede tardar algún tiempo, dependiendo del tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="70f41-207">Lo mismo ocurre cuando una directiva no está desasignada de un grupo o cuando se agregan o quitan miembros de un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="70f41-208">Las asignaciones de directivas de grupo solo se propagan a los usuarios que son miembros directos del grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="70f41-209">Las tareas no se propagan a los miembros de grupos anidados.</span><span class="sxs-lookup"><span data-stu-id="70f41-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="70f41-210">Qué necesita saber sobre la asignación de directivas a grupos</span><span class="sxs-lookup"><span data-stu-id="70f41-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="70f41-211">Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de las asignaciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="70f41-212">Reglas de prioridad</span><span class="sxs-lookup"><span data-stu-id="70f41-212">Precedence rules</span></span>

<span data-ttu-id="70f41-213">Para un tipo de directiva determinado, la directiva efectiva de un usuario se determina según lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70f41-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="70f41-214">Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo asignada a un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="70f41-215">En otras palabras, si a un usuario se le asigna directamente una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="70f41-216">Esto también significa que si un usuario tiene una directiva de un tipo determinado que se le asignó directamente, debe quitar esa directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="70f41-217">Si un usuario no tiene una directiva asignada directamente a ellos y es miembro de dos o más grupos y cada grupo tiene asignada una directiva del mismo tipo, el usuario hereda la directiva de la asignación de grupo que tiene la clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="70f41-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="70f41-218">Si un usuario no es miembro de ningún grupo al que se le haya asignado una directiva, la directiva global (predeterminada para toda la organización) para ese tipo de directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="70f41-219">La directiva efectiva de un usuario se actualiza según estas reglas:</span><span class="sxs-lookup"><span data-stu-id="70f41-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="70f41-220">cuando se agrega o quita un usuario de un grupo al que se le ha asignado una directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="70f41-221">una directiva no está desasignada de un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="70f41-222">se quita una directiva que está asignada directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="70f41-223">Clasificación de tareas de grupo</span><span class="sxs-lookup"><span data-stu-id="70f41-223">Group assignment ranking</span></span>

<span data-ttu-id="70f41-224">Al asignar una directiva a un grupo, se especifica una clasificación para la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="70f41-225">Esto se usa para determinar qué directiva debe heredar un usuario como su directiva efectiva si el usuario es miembro de dos o más grupos y a cada grupo se le asigna una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="70f41-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="70f41-226">La clasificación de asignaciones de grupo es relativa a otras asignaciones de grupo del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="70f41-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="70f41-227">Por ejemplo, si va a asignar una directiva de llamada a dos grupos, establezca la clasificación de una tarea en 1 y la otra en 2, siendo 1 la clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="70f41-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="70f41-228">La clasificación de asignaciones de grupo indica qué pertenencia a un grupo es más importante o más relevante que otras pertenencias de grupo con respecto a la herencia.</span><span class="sxs-lookup"><span data-stu-id="70f41-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="70f41-229">Por ejemplo, tiene dos grupos: Empleados de la Tienda y Administradores de tienda.</span><span class="sxs-lookup"><span data-stu-id="70f41-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="70f41-230">A ambos grupos se les asigna una directiva de llamadas de Teams, una directiva de llamadas de empleados de store y una directiva de llamadas de administradores de tienda, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="70f41-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="70f41-231">Para un administrador de tienda que está en ambos grupos, su rol como administrador es más relevante que su rol como empleado, por lo que la directiva de llamadas asignada al grupo Administradores de tienda debería tener una clasificación superior.</span><span class="sxs-lookup"><span data-stu-id="70f41-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="70f41-232">Grupo</span><span class="sxs-lookup"><span data-stu-id="70f41-232">Group</span></span> |<span data-ttu-id="70f41-233">Nombre de directiva de llamadas de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-233">Teams calling policy name</span></span>  |<span data-ttu-id="70f41-234">Clasificación</span><span class="sxs-lookup"><span data-stu-id="70f41-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="70f41-235">Administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="70f41-235">Store Managers</span></span>   |<span data-ttu-id="70f41-236">Directiva de llamadas de administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="70f41-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="70f41-237">1</span><span class="sxs-lookup"><span data-stu-id="70f41-237">1</span></span>|
|<span data-ttu-id="70f41-238">Almacenar empleados</span><span class="sxs-lookup"><span data-stu-id="70f41-238">Store Employees</span></span>    |<span data-ttu-id="70f41-239">Directiva de llamadas de empleados de store</span><span class="sxs-lookup"><span data-stu-id="70f41-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="70f41-240">2</span><span class="sxs-lookup"><span data-stu-id="70f41-240">2</span></span>|

<span data-ttu-id="70f41-241">Si no especifica una clasificación, la asignación de directivas se asigna a la clasificación más baja.</span><span class="sxs-lookup"><span data-stu-id="70f41-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="70f41-242">En el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="70f41-243">Actualmente, la asignación de directivas a grupos que usan el Centro de administración de Microsoft Teams solo está disponible para la directiva de llamadas de Teams, la directiva de parque de llamadas de Teams, la directiva de Teams, la directiva de eventos en directo de Teams, la directiva de reunión de Teams y la directiva de mensajería de Teams.</span><span class="sxs-lookup"><span data-stu-id="70f41-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="70f41-244">Para otros tipos de directiva, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70f41-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="70f41-245">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la página de tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="70f41-246">Por ejemplo, vaya a **Directivas de reunión de**  >  **reuniones.**</span><span class="sxs-lookup"><span data-stu-id="70f41-246">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="70f41-247">Seleccione la **pestaña Asignación de directivas de** grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-247">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="70f41-248">Seleccione **Agregar grupo** y, a continuación, en el panel Asignar **directiva** al grupo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70f41-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="70f41-249">Busque y agregue el grupo al que desea asignar la directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="70f41-250">Establezca la clasificación de la tarea de grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="70f41-251">Seleccione la directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="70f41-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="70f41-252">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="70f41-252">Select **Apply**.</span></span>

<span data-ttu-id="70f41-253">Para quitar una asignación de directiva de grupo, en la pestaña **Asignación** de directivas de grupo de la página directiva, seleccione la asignación de grupo y, a continuación, **seleccione Quitar**.</span><span class="sxs-lookup"><span data-stu-id="70f41-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="70f41-254">Para cambiar la clasificación de una asignación de grupo, primero debe quitar la asignación de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="70f41-255">Después, siga los pasos anteriores para asignar la directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="70f41-256">Usar la opción de PowerShell</span><span class="sxs-lookup"><span data-stu-id="70f41-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="70f41-257">Actualmente, la asignación de directivas a grupos que usan PowerShell no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="70f41-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="70f41-258">Vea [New-CsGroupPolicyAssignment para](/powershell/module/teams/new-csgrouppolicyassignment) obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="70f41-258">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="70f41-259">Instalar y conectarse al módulo De PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="70f41-260">Para obtener instrucciones paso a paso, vea [Instalar PowerShell de Teams.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="70f41-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="70f41-261">Asignar una directiva a un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="70f41-262">Use el cmdlet [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) para asignar una directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-262">Use the [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="70f41-263">Puede especificar un grupo con el id. de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="70f41-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="70f41-264">En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de administradores minoristas a un grupo con una clasificación de tareas de 1.</span><span class="sxs-lookup"><span data-stu-id="70f41-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="70f41-265">Obtener asignaciones de directivas para un grupo</span><span class="sxs-lookup"><span data-stu-id="70f41-265">Get policy assignments for a group</span></span>

<span data-ttu-id="70f41-266">Use el cmdlet [Get-CsGroupPolicyAssignment para](/powershell/module/teams/get-csgrouppolicyassignment) obtener todas las directivas asignadas a un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-266">Use the [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="70f41-267">Tenga en cuenta que los grupos siempre aparecen en la lista por su id. de grupo, incluso si se usó su dirección SIP o su dirección de correo electrónico para asignar la directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="70f41-268">En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="70f41-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="70f41-269">En este ejemplo, se devuelven todos los grupos asignados a una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="70f41-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="70f41-270">Quitar una directiva de un grupo</span><span class="sxs-lookup"><span data-stu-id="70f41-270">Remove a policy from a group</span></span>

<span data-ttu-id="70f41-271">Use el cmdlet [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) para quitar una directiva de un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-271">Use the [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="70f41-272">Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y que tienen una clasificación inferior.</span><span class="sxs-lookup"><span data-stu-id="70f41-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="70f41-273">Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tienen una clasificación de 3 y 4 se actualizan para reflejar su nueva clasificación.</span><span class="sxs-lookup"><span data-stu-id="70f41-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="70f41-274">En las dos tablas siguientes se muestra este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="70f41-274">The following two tables show this example.</span></span>

<span data-ttu-id="70f41-275">Esta es una lista de las tareas de directiva y las prioridades de una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="70f41-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="70f41-276">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="70f41-276">Group name</span></span>  |<span data-ttu-id="70f41-277">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="70f41-277">Policy name</span></span>  |<span data-ttu-id="70f41-278">Clasificación</span><span class="sxs-lookup"><span data-stu-id="70f41-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="70f41-279">Ventas</span><span class="sxs-lookup"><span data-stu-id="70f41-279">Sales</span></span>    |<span data-ttu-id="70f41-280">Directiva de ventas</span><span class="sxs-lookup"><span data-stu-id="70f41-280">Sales policy</span></span>       | <span data-ttu-id="70f41-281">1</span><span class="sxs-lookup"><span data-stu-id="70f41-281">1</span></span>        |
|<span data-ttu-id="70f41-282">Región Oeste</span><span class="sxs-lookup"><span data-stu-id="70f41-282">West Region</span></span>     |<span data-ttu-id="70f41-283">Directiva región oeste</span><span class="sxs-lookup"><span data-stu-id="70f41-283">West Region policy</span></span>         |<span data-ttu-id="70f41-284">2</span><span class="sxs-lookup"><span data-stu-id="70f41-284">2</span></span>         |
|<span data-ttu-id="70f41-285">División</span><span class="sxs-lookup"><span data-stu-id="70f41-285">Division</span></span>    |<span data-ttu-id="70f41-286">Directiva de división</span><span class="sxs-lookup"><span data-stu-id="70f41-286">Division policy</span></span>         |<span data-ttu-id="70f41-287">3</span><span class="sxs-lookup"><span data-stu-id="70f41-287">3</span></span>         |
|<span data-ttu-id="70f41-288">Subsidiaria</span><span class="sxs-lookup"><span data-stu-id="70f41-288">Subsidiary</span></span>   |<span data-ttu-id="70f41-289">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="70f41-289">Subsidiary policy</span></span>        |<span data-ttu-id="70f41-290">4</span><span class="sxs-lookup"><span data-stu-id="70f41-290">4</span></span>         |

<span data-ttu-id="70f41-291">Si quitamos la directiva región oeste del grupo Región oeste, las asignaciones de directivas y las prioridades se actualizan de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="70f41-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="70f41-292">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="70f41-292">Group name</span></span>  |<span data-ttu-id="70f41-293">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="70f41-293">Policy name</span></span>  |<span data-ttu-id="70f41-294">Clasificación</span><span class="sxs-lookup"><span data-stu-id="70f41-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="70f41-295">Ventas</span><span class="sxs-lookup"><span data-stu-id="70f41-295">Sales</span></span>    |<span data-ttu-id="70f41-296">Directiva de ventas</span><span class="sxs-lookup"><span data-stu-id="70f41-296">Sales policy</span></span>       | <span data-ttu-id="70f41-297">1</span><span class="sxs-lookup"><span data-stu-id="70f41-297">1</span></span>        |
|<span data-ttu-id="70f41-298">División</span><span class="sxs-lookup"><span data-stu-id="70f41-298">Division</span></span>    |<span data-ttu-id="70f41-299">Directiva de división</span><span class="sxs-lookup"><span data-stu-id="70f41-299">Division policy</span></span>         |<span data-ttu-id="70f41-300">2</span><span class="sxs-lookup"><span data-stu-id="70f41-300">2</span></span>         |
|<span data-ttu-id="70f41-301">Subsidiaria</span><span class="sxs-lookup"><span data-stu-id="70f41-301">Subsidiary</span></span>   |<span data-ttu-id="70f41-302">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="70f41-302">Subsidiary policy</span></span>        |<span data-ttu-id="70f41-303">3</span><span class="sxs-lookup"><span data-stu-id="70f41-303">3</span></span>        |

<span data-ttu-id="70f41-304">En este ejemplo, quitamos la directiva de reunión de Teams de un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="70f41-305">Cambiar una asignación de directiva para un grupo</span><span class="sxs-lookup"><span data-stu-id="70f41-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="70f41-306">El cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="70f41-306">The [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="70f41-307">Mientras tanto, para cambiar una asignación de directiva de grupo, puede quitar la asignación de directiva actual del grupo y, después, agregar una nueva asignación de directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="70f41-308">Después de asignar una directiva a un grupo, puede usar el cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) para cambiar la asignación de directivas de ese grupo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="70f41-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="70f41-309">Cambiar la clasificación</span><span class="sxs-lookup"><span data-stu-id="70f41-309">Change the ranking</span></span>
- <span data-ttu-id="70f41-310">Cambiar la directiva de un tipo de directiva determinado</span><span class="sxs-lookup"><span data-stu-id="70f41-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="70f41-311">Cambiar la directiva de un tipo de directiva determinado y la clasificación</span><span class="sxs-lookup"><span data-stu-id="70f41-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="70f41-312">En este ejemplo, cambiamos la directiva de parque de llamadas de Teams de un grupo a una directiva denominada SupportCallPark y la clasificación de tareas a 3.</span><span class="sxs-lookup"><span data-stu-id="70f41-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="70f41-313">Cambiar la directiva eficaz para un usuario</span><span class="sxs-lookup"><span data-stu-id="70f41-313">Change the effective policy for a user</span></span>

<span data-ttu-id="70f41-314">Este es un ejemplo de cómo cambiar la directiva eficaz para un usuario al que se le asigna directamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="70f41-315">En primer lugar, usamos el cmdlet [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) junto con el parámetro para obtener detalles de las directivas de difusión de reuniones de ```PolicySource``` Teams asociadas con el usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-315">First, we use the [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="70f41-316">El resultado muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada Eventos de empleado, que tiene prioridad sobre la directiva denominada Eventos en directo de proveedor asignada a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="70f41-317">Ahora, quitamos la directiva Eventos de empleado del usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="70f41-318">Esto significa que el usuario ya no tiene asignada una directiva de difusión de reunión de Teams directamente y heredará la directiva Eventos en directo del proveedor asignada al grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="70f41-319">Use el siguiente cmdlet en el módulo PowerShell de Skype Empresarial para ello.</span><span class="sxs-lookup"><span data-stu-id="70f41-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="70f41-320">Use el cmdlet siguiente en el módulo de PowerShell de Teams para hacerlo a escala a través de una asignación de directiva por lotes, donde $users es una lista de usuarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="70f41-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="70f41-321">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="70f41-322">Usar el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="70f41-322">Use the admin center</span></span>

<span data-ttu-id="70f41-323">Para asignar una directiva a los usuarios en masa:</span><span class="sxs-lookup"><span data-stu-id="70f41-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="70f41-324">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="70f41-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="70f41-325">Busque los usuarios a los que desea asignar la directiva o filtre la vista para mostrar los usuarios que desee.</span><span class="sxs-lookup"><span data-stu-id="70f41-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="70f41-326">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="70f41-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="70f41-327">Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="70f41-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="70f41-328">Seleccione **Editar configuración,** realice los cambios que desee y, a continuación, **seleccione Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="70f41-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="70f41-329">Para ver el estado de la asignación de directivas,  en el  banner que aparece en la parte superior de la página Usuarios después de seleccionar Aplicar para enviar la tarea de directiva, seleccione Registro **de actividades.**</span><span class="sxs-lookup"><span data-stu-id="70f41-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="70f41-330">O bien, en la navegación izquierda del Centro de administración de Microsoft Teams, vaya a Panel **y,** a continuación, en Registro de **actividades,** seleccione **Ver detalles.**</span><span class="sxs-lookup"><span data-stu-id="70f41-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="70f41-331">El registro de actividades muestra las asignaciones de directivas a lotes de más de 20 usuarios a través del Centro de administración de Microsoft Teams desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="70f41-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="70f41-332">Para obtener más información, vea [Ver las asignaciones de directivas en el registro de actividades.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="70f41-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="70f41-333">Usar método de PowerShell</span><span class="sxs-lookup"><span data-stu-id="70f41-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="70f41-334">Actualmente, la asignación de directivas por lotes con PowerShell no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="70f41-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="70f41-335">Vea [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="70f41-335">See [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="70f41-336">Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="70f41-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="70f41-337">Use el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y la directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="70f41-337">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="70f41-338">Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="70f41-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="70f41-339">A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones en un lote.</span><span class="sxs-lookup"><span data-stu-id="70f41-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="70f41-340">Especifique los usuarios por su id. de objeto o dirección del Protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="70f41-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="70f41-341">La dirección SIP de un usuario suele tener el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="70f41-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="70f41-342">Si se especifica un usuario con su UPN o correo electrónico, pero tiene un valor diferente de su dirección SIP, la asignación de directivas no se realizará correctamente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="70f41-343">Si un lote incluye usuarios duplicados, los duplicados se quitarán del lote antes de procesar y el estado solo se proporciona para los usuarios únicos que permanecen en el lote.</span><span class="sxs-lookup"><span data-stu-id="70f41-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="70f41-344">Un lote puede contener hasta 5000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="70f41-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="70f41-345">Para obtener los mejores resultados, no envíe más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="70f41-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="70f41-346">Permitir que los lotes completen el procesamiento antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="70f41-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="70f41-347">Instalar y conectarse al módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="70f41-348">Ejecute lo siguiente para instalar el módulo [PowerShell de Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="70f41-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="70f41-349">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="70f41-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="70f41-350">Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="70f41-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="70f41-351">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="70f41-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="70f41-352">Instalar y conectarse al módulo Azure AD PowerShell para Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="70f41-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="70f41-353">Es posible que también quiera descargar e instalar el módulo [Azure AD PowerShell para Graph](/powershell/azure/active-directory/install-adv2) (si aún no lo ha hecho) y conectarse a Azure AD para recuperar una lista de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="70f41-353">You might also want to [download and install the Azure AD PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="70f41-354">Ejecute lo siguiente para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="70f41-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="70f41-355">Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a Teams.</span><span class="sxs-lookup"><span data-stu-id="70f41-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="70f41-356">Asignar una directiva de configuración a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="70f41-357">En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar una directiva de configuración de aplicaciones denominada Directiva de configuración de aplicaciones de HR a un lote de usuarios que aparecen en el archivo Users_ids.text.</span><span class="sxs-lookup"><span data-stu-id="70f41-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="70f41-358">En este ejemplo, nos conectamos a Azure AD para recuperar una colección de usuarios y, a continuación, asignamos una directiva de mensajería denominada Nueva directiva de mensajería de contratación a un lote de usuarios especificado mediante su dirección SIP.</span><span class="sxs-lookup"><span data-stu-id="70f41-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="70f41-359">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="70f41-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="70f41-360">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el id. de operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="70f41-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="70f41-361">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que se encuentran en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="70f41-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="70f41-362">Para obtener más información, [vea Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="70f41-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="70f41-363">Asignar un paquete de directiva a los usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-363">Assign a policy package to users</span></span>

<span data-ttu-id="70f41-364">Un paquete de directivas en Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a los usuarios que tienen los mismos roles o similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="70f41-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="70f41-365">Cada paquete de directivas está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten actividades típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="70f41-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="70f41-366">Algunos ejemplos de paquetes de directivas son el paquete educación (profesor) y el paquete de atención sanitaria (trabajador clínico).</span><span class="sxs-lookup"><span data-stu-id="70f41-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="70f41-367">Para obtener más información, vea [Administrar paquetes de directivas en Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="70f41-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="70f41-368">Asignar un paquete de directiva a un usuario</span><span class="sxs-lookup"><span data-stu-id="70f41-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="70f41-369">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, a continuación, seleccione el usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="70f41-370">En la página del usuario, seleccione **Directivas** y, a continuación, junto **a Paquete de directivas,** seleccione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="70f41-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="70f41-371">En el **panel Asignar paquete de** directiva, seleccione el paquete que desea asignar y, a continuación, seleccione **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="70f41-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="70f41-372">Asignar un paquete de directiva a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="70f41-373">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Paquetes de directiva y, a continuación, seleccione el paquete de directiva que desea asignar haciendo clic a la izquierda del nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="70f41-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="70f41-374">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="70f41-374">Select **Manage users**.</span></span>
3. <span data-ttu-id="70f41-375">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="70f41-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="70f41-376">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="70f41-376">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="70f41-377">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="70f41-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="70f41-378">Asignar un paquete de directivas a un grupo</span><span class="sxs-lookup"><span data-stu-id="70f41-378">Assign a policy package to a group</span></span>

<span data-ttu-id="70f41-379">La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="70f41-379">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="70f41-380">La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="70f41-380">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="70f41-381">A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.</span><span class="sxs-lookup"><span data-stu-id="70f41-381">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="70f41-382">La asignación de paquetes de directiva a grupos se recomienda para grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="70f41-382">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="70f41-383">Al asignar el paquete de directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-383">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="70f41-384">Sin embargo, la propagación de la asignación de directivas a los miembros del grupo se realiza como una operación en segundo plano y puede tardar algún tiempo, dependiendo del tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-384">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="70f41-385">Lo mismo ocurre cuando una directiva no está desasignada de un grupo o cuando se agregan o quitan miembros de un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-385">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70f41-386">Antes de empezar, es importante comprender las reglas de [prioridad](#precedence-rules) y la clasificación [de las asignaciones de grupo.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="70f41-386">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="70f41-387">Asegúrese de leer y comprender los conceptos de [Lo que necesita saber acerca](#what-you-need-to-know-about-policy-assignment-to-groups) de la asignación de directivas a grupos anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="70f41-387">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="70f41-388">Asignar un paquete de directiva a un grupo de usuarios en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="70f41-388">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="70f41-389">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-389">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="70f41-390">En el panel de navegación izquierdo, vaya a la página del paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="70f41-390">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="70f41-391">Seleccione la pestaña Asignación de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-391">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="70f41-392">Seleccione **Agregar grupo** y, a continuación, en el panel Asignar un paquete de directiva al grupo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70f41-392">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="70f41-393">a.</span><span class="sxs-lookup"><span data-stu-id="70f41-393">a.</span></span> <span data-ttu-id="70f41-394">Busque y agregue el grupo al que desea asignar el paquete de directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-394">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="70f41-395">b.</span><span class="sxs-lookup"><span data-stu-id="70f41-395">b.</span></span> <span data-ttu-id="70f41-396">Seleccione un paquete de directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-396">Select a policy package.</span></span>

    <span data-ttu-id="70f41-397">c.</span><span class="sxs-lookup"><span data-stu-id="70f41-397">c.</span></span> <span data-ttu-id="70f41-398">Establezca la clasificación para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="70f41-398">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="70f41-399">d.</span><span class="sxs-lookup"><span data-stu-id="70f41-399">d.</span></span> <span data-ttu-id="70f41-400">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="70f41-400">Select **Apply**.</span></span>

    ![muestra la asignación de directiva de grupo](media/group-pkg-assignment.png)

5. <span data-ttu-id="70f41-402">Para administrar la clasificación de un tipo de directiva específico, vaya a la página de directiva específica.</span><span class="sxs-lookup"><span data-stu-id="70f41-402">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="70f41-403">Para reasignar un paquete de directiva a un grupo, primero quite la asignación de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-403">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="70f41-404">A continuación, siga los pasos anteriores para asignar el paquete de directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-404">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="70f41-405">Trabajar con PowerShell</span><span class="sxs-lookup"><span data-stu-id="70f41-405">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="70f41-406">Obtener el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-406">Get the Teams PowerShell module</span></span>

<span data-ttu-id="70f41-407">Para obtener instrucciones paso a paso, vea [Instalar PowerShell de Teams.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="70f41-407">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="70f41-408">Asignar un paquete de directiva a un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-408">Assign a policy package to a group of users</span></span>

<span data-ttu-id="70f41-409">Use el cmdlet [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) para asignar un paquete de directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="70f41-409">Use the [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="70f41-410">Puede especificar un grupo con el id. de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="70f41-410">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="70f41-411">Al asignar el paquete de directiva, especifique una clasificación de asignación de [grupo](#group-assignment-ranking) para cada tipo de directiva en el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="70f41-411">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="70f41-412">En este ejemplo, asignamos el paquete de directiva de Education_Teacher a un grupo con una clasificación de asignaciones de 1 para TeamsAppSetupPolicy y TeamsMeetingBroadcastPolicy y una clasificación de 2 para TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="70f41-412">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="70f41-413">Asignar un paquete de directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-413">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="70f41-414">Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="70f41-414">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="70f41-415">Use el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y el paquete de directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="70f41-415">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="70f41-416">Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="70f41-416">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="70f41-417">A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones en un lote.</span><span class="sxs-lookup"><span data-stu-id="70f41-417">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="70f41-418">Especifique los usuarios por su id. de objeto o dirección del Protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="70f41-418">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="70f41-419">La dirección SIP de un usuario suele tener el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="70f41-419">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="70f41-420">Si se especifica un usuario con su UPN o correo electrónico, pero tiene un valor diferente de su dirección SIP, la asignación de directivas no se realizará correctamente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="70f41-420">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="70f41-421">Si un lote incluye usuarios duplicados, los duplicados se quitarán del lote antes de procesar y el estado solo se proporciona para los usuarios únicos que permanecen en el lote.</span><span class="sxs-lookup"><span data-stu-id="70f41-421">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="70f41-422">Un lote contiene hasta 5 000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="70f41-422">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="70f41-423">Para obtener los mejores resultados, no envíe más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="70f41-423">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="70f41-424">Permitir que los lotes completen el procesamiento antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="70f41-424">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="70f41-425">Usar el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-425">Use the Teams PowerShell module</span></span>

<span data-ttu-id="70f41-426">Ejecute lo siguiente para instalar el módulo [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) de Microsoft Teams (si aún no lo ha hecho).</span><span class="sxs-lookup"><span data-stu-id="70f41-426">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="70f41-427">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="70f41-427">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="70f41-428">Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="70f41-428">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="70f41-429">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="70f41-429">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="70f41-430">Asignar paquetes de directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="70f41-430">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="70f41-431">En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar el paquete de directiva Education_PrimaryStudent un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="70f41-431">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="70f41-432">Ver el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="70f41-432">See the status of a batch assignment</span></span>

<span data-ttu-id="70f41-433">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el id. de operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="70f41-433">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="70f41-434">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que se encuentran en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="70f41-434">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="70f41-435">Para obtener más información, [vea Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="70f41-435">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="70f41-436">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="70f41-436">Related topics</span></span>

[<span data-ttu-id="70f41-437">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="70f41-437">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)