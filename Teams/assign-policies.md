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
ms.openlocfilehash: 9d6253645e674d680f86d0b6f89a62968e6c21ba
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533947"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="69afe-103">Asignar directivas a los usuarios de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="69afe-104">Como administrador, use directivas para controlar las características de teams que están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="69afe-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="69afe-105">Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por citar algunas.</span><span class="sxs-lookup"><span data-stu-id="69afe-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="69afe-106">Las organizaciones tienen diferentes tipos de usuarios con necesidades exclusivas y directivas personalizadas que usted crea y asigna le permiten adaptar la configuración de directivas a distintos conjuntos de usuarios según esas necesidades.</span><span class="sxs-lookup"><span data-stu-id="69afe-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="69afe-107">Para facilitar la administración de directivas de su organización, Teams ofrece varias formas de asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="69afe-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="69afe-108">Puede asignar una directiva directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes, o a un grupo del que son miembros los usuarios.</span><span class="sxs-lookup"><span data-stu-id="69afe-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="69afe-109">También puede usar paquetes de directivas para asignar una colección preconfigurada de directivas a los usuarios de su organización que tengan roles similares.</span><span class="sxs-lookup"><span data-stu-id="69afe-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="69afe-110">La opción que elija dependerá del número de directivas que esté administrando y del número de usuarios a los que va a asignar.</span><span class="sxs-lookup"><span data-stu-id="69afe-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="69afe-111">Al configurar las directivas globales (predeterminada para toda la organización) de modo que se apliquen al mayor número de usuarios de su organización, solo tiene que asignar directivas a aquellos usuarios que requieran directivas especializadas.</span><span class="sxs-lookup"><span data-stu-id="69afe-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="69afe-112">En este artículo se describen las diferentes maneras en las que puede asignar directivas a los usuarios y las situaciones recomendadas para Cuándo usarlas.</span><span class="sxs-lookup"><span data-stu-id="69afe-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="69afe-113">¿Qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="69afe-113">Which policy takes precedence?</span></span>

<span data-ttu-id="69afe-114">Un usuario tiene una directiva vigente para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="69afe-115">Es posible o incluso probable que un usuario tenga asignada directamente una directiva y también es miembro de uno o más grupos a los que se ha asignado una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="69afe-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="69afe-116">En estos tipos de escenarios, ¿qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="69afe-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="69afe-117">La Directiva efectiva del usuario se determina según las reglas de prioridad, de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="69afe-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="69afe-118">Si un usuario tiene asignada directamente una directiva (ya sea de forma individual o mediante una asignación por lotes), tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="69afe-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="69afe-119">En el ejemplo siguiente, la Directiva efectiva del usuario es la Lincoln cuadrada de la reunión, que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva asignada directamente](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="69afe-121">Si un usuario no tiene asignada directamente una directiva de un tipo determinado, tendrá prioridad la directiva asignada a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="69afe-122">Si un usuario es miembro de varios grupos, tiene prioridad la Directiva que tiene la mayor [clasificación de asignación de grupo](#group-assignment-ranking) para el tipo de directiva determinado.</span><span class="sxs-lookup"><span data-stu-id="69afe-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="69afe-123">En este ejemplo, la Directiva efectiva del usuario es el equipo de ejecución y la Directiva de alta definición, que tiene la mayor clasificación de asignación relativa a otros grupos de los que el usuario es miembro y al que también se les ha asignado una directiva del mismo tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama que muestra cómo tiene prioridad una directiva heredada del grupo](media/assign-policies-example-group.png)

<span data-ttu-id="69afe-125">Si un usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario recibirá la directiva global (opción predeterminada para toda la organización) para ese tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="69afe-126">Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="69afe-126">Here's an example.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva global](media/assign-policies-example-global.png)

<span data-ttu-id="69afe-128">Para obtener más información, vea [reglas de prioridad](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="69afe-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="69afe-129">Formas de asignar directivas</span><span class="sxs-lookup"><span data-stu-id="69afe-129">Ways to assign policies</span></span>

<span data-ttu-id="69afe-130">A continuación se ofrece una descripción general de las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno.</span><span class="sxs-lookup"><span data-stu-id="69afe-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="69afe-131">Haga clic en los vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="69afe-131">Click the links to learn more.</span></span>

<span data-ttu-id="69afe-132">Antes de asignar directivas a usuarios individuales o grupos, primero [establezca las directivas globales (valor predeterminado de organización)](#set-the-global-policies) para que se apliquen al mayor número de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="69afe-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="69afe-133">Una vez configuradas las directivas globales, solo tendrá que asignar directivas a aquellos usuarios que requieran directivas especializadas.</span><span class="sxs-lookup"><span data-stu-id="69afe-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="69afe-134">Haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="69afe-134">Do this</span></span>  |<span data-ttu-id="69afe-135">Si...</span><span class="sxs-lookup"><span data-stu-id="69afe-135">If...</span></span>  | <span data-ttu-id="69afe-136">Usar...</span><span class="sxs-lookup"><span data-stu-id="69afe-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="69afe-137">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="69afe-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="69afe-138">Ya está familiarizado con Teams y solo necesita asignar una o dos directivas a un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="69afe-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="69afe-139">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="69afe-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="69afe-140">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="69afe-140">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="69afe-141">Debe asignar varias directivas a conjuntos específicos de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="69afe-141">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="69afe-142">Por ejemplo, asigne el paquete de directivas Educación (profesor) a los profesores de su escuela para proporcionarles acceso completo a chats, llamadas y reuniones, y al paquete de directivas Educación (estudiante secundario escolar) a los estudiantes secundarios para limitar ciertas funciones como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="69afe-142">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="69afe-143">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="69afe-144">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="69afe-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="69afe-145">Debe asignar directivas a grandes conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="69afe-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="69afe-146">Por ejemplo, desea asignar una directiva a cientos o miles de usuarios de su organización al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="69afe-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="69afe-147">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="69afe-148">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="69afe-148">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="69afe-149">Debe asignar directivas en función de la pertenencia a grupos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-149">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="69afe-150">Por ejemplo, desea asignar una directiva a todos los usuarios de un grupo de seguridad o de una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="69afe-150">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="69afe-151">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="69afe-152">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="69afe-152">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="69afe-153">Debe asignar varias directivas a un lote de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="69afe-153">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="69afe-154">Por ejemplo, asigne el paquete de directivas Educación (profesor) a todos los profesores de su escuela mediante la asignación por lotes para proporcionarles acceso total a chats, llamadas y reuniones, y asigne el paquete de directivas Educación (estudiante secundario) a un lote de estudiantes secundarios para limitar ciertas capacidades como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="69afe-154">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="69afe-155">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-155">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="69afe-156">Asignar un paquete de directivas a un grupo (próximamente)</span><span class="sxs-lookup"><span data-stu-id="69afe-156">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="69afe-157">Establecer las directivas globales</span><span class="sxs-lookup"><span data-stu-id="69afe-157">Set the global policies</span></span>

<span data-ttu-id="69afe-158">Siga estos pasos para establecer las directivas globales (valor predeterminado de la organización) para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-158">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="69afe-159">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-159">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="69afe-160">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de directivas del tipo de directiva que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="69afe-160">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="69afe-161">Por ejemplo, **Teams**  >  **Policies**, directivas de reuniones de **reuniones**  >  **Meetings policies**, **directivas de mensajería**o directivas de llamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="69afe-161">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="69afe-162">Seleccione la directiva **global (opción predeterminada para toda la organización)** para ver la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="69afe-162">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="69afe-163">Actualice la Directiva según sea necesario y, a continuación, seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="69afe-163">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="69afe-164">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="69afe-164">Using PowerShell</span></span>

<span data-ttu-id="69afe-165">Para establecer las directivas globales mediante PowerShell, use el identificador global.</span><span class="sxs-lookup"><span data-stu-id="69afe-165">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="69afe-166">Para empezar, revisamos la directiva global actual para determinar qué configuración desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="69afe-166">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="69afe-167">A continuación, actualice la directiva global según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="69afe-167">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="69afe-168">Solo tiene que especificar los valores de la configuración que quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="69afe-168">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="69afe-169">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="69afe-169">Assign a policy to individual users</span></span>

<span data-ttu-id="69afe-170">Siga estos pasos para asignar una directiva a un usuario individual o a un número reducido de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="69afe-170">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="69afe-171">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-171">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="69afe-172">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="69afe-172">To assign a policy to a user:</span></span>

1. <span data-ttu-id="69afe-173">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-173">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="69afe-174">Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.</span><span class="sxs-lookup"><span data-stu-id="69afe-174">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="69afe-175">Seleccione la Directiva que desea asignar y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="69afe-175">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="69afe-176">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69afe-176">Or, you can also do the following:</span></span>

1. <span data-ttu-id="69afe-177">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-177">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="69afe-178">Seleccione la Directiva que desea asignar haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-178">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="69afe-179">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="69afe-179">Select **Manage users**.</span></span>
4. <span data-ttu-id="69afe-180">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="69afe-180">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="69afe-181">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="69afe-181">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="69afe-182">Cuando haya terminado de agregar usuarios, seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="69afe-182">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="69afe-183">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="69afe-183">Using PowerShell</span></span>

<span data-ttu-id="69afe-184">Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo.</span><span class="sxs-lookup"><span data-stu-id="69afe-184">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="69afe-185">Use el ```Grant-``` cmdlet para un tipo de directiva determinado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-185">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="69afe-186">Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una política de reunión de Teams a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="69afe-186">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="69afe-187">Estos cmdlets están incluidos en el módulo de PowerShell de Skype empresarial online y están documentados en la [Referencia del cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="69afe-187">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="69afe-188">Descargue e instale el [módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si todavía no lo ha hecho) y, a continuación, ejecute lo siguiente para conectarse a Skype empresarial online e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="69afe-188">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="69afe-189">En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiantes a un usuario denominado Reda.</span><span class="sxs-lookup"><span data-stu-id="69afe-189">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="69afe-190">Para obtener más información, lea [Administración de directivas a través de PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="69afe-190">To learn more, read [Managing policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="69afe-191">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="69afe-191">Assign a policy package</span></span>

<span data-ttu-id="69afe-192">Un paquete de directivas de Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles iguales o similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="69afe-192">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="69afe-193">Cada paquete de directivas está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten actividades típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="69afe-193">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="69afe-194">Algunos ejemplos de paquetes de directivas son el paquete educativo (profesor) y el paquete de salud (trabajador clínico).</span><span class="sxs-lookup"><span data-stu-id="69afe-194">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="69afe-195">Cuando se asigna un paquete de directivas a los usuarios, se crean las directivas del paquete y, después, se puede personalizar la configuración de cada Directiva del paquete para satisfacer las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="69afe-195">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="69afe-196">Para obtener más información sobre los paquetes de directivas, incluidas las instrucciones paso a paso sobre cómo asignarlos y administrarlos, consulte [administrar paquetes de directivas en Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="69afe-196">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="69afe-197">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="69afe-197">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="69afe-198">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-198">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="69afe-199">Para asignar una directiva a usuarios en bloque:</span><span class="sxs-lookup"><span data-stu-id="69afe-199">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="69afe-200">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="69afe-200">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="69afe-201">Busque los usuarios a los que desea asignar la Directiva o filtre la vista para mostrar los usuarios que desea.</span><span class="sxs-lookup"><span data-stu-id="69afe-201">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="69afe-202">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="69afe-202">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="69afe-203">Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="69afe-203">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="69afe-204">Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="69afe-204">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="69afe-205">Para ver el estado de la asignación de Directiva, en la pancarta que aparece en la parte superior de la página **usuarios** después de hacer clic en **aplicar** para enviar la asignación de Directiva, haga clic en **registro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="69afe-205">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="69afe-206">O bien, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel**y, a continuación, en **registro de actividades**, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="69afe-206">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="69afe-207">En el registro de actividades se muestran asignaciones de directivas de los lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="69afe-207">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="69afe-208">Para obtener más información, vea [ver las asignaciones de directivas en el registro de actividades](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="69afe-208">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="69afe-209">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="69afe-209">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="69afe-210">Actualmente, la asignación de directivas por lotes con PowerShell no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="69afe-210">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="69afe-211">Vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="69afe-211">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="69afe-212">Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="69afe-212">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="69afe-213">Use el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para enviar un lote de usuarios y la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="69afe-213">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="69afe-214">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="69afe-214">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="69afe-215">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="69afe-215">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="69afe-216">Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="69afe-216">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="69afe-217">Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="69afe-217">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="69afe-218">Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-218">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="69afe-219">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="69afe-219">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="69afe-220">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="69afe-220">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="69afe-221">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="69afe-221">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="69afe-222">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="69afe-222">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="69afe-223">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-223">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="69afe-224">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="69afe-224">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="69afe-225">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="69afe-225">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="69afe-226">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="69afe-226">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="69afe-227">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="69afe-227">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="69afe-228">Instalar y conectarse al módulo de Azure AD PowerShell for Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="69afe-228">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="69afe-229">Es posible que también desee [Descargar e instalar el módulo Azure ad PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (si todavía no lo ha hecho) y conectarse a Azure ad para poder recuperar una lista de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="69afe-229">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="69afe-230">Ejecute lo siguiente para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="69afe-230">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="69afe-231">Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a teams.</span><span class="sxs-lookup"><span data-stu-id="69afe-231">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="69afe-232">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="69afe-232">Assign a policy to a batch of users</span></span>

<span data-ttu-id="69afe-233">En este ejemplo, usamos el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para asignar una directiva de configuración de aplicación denominada Directiva de configuración de la aplicación de RRHH a un lote de usuarios que aparece en el archivo Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="69afe-233">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="69afe-234">En este ejemplo, se conectará a Azure AD para recuperar una colección de usuarios y, a continuación, asignar una directiva de mensajería llamada nueva Directiva de mensajería de contratación a un lote de usuarios especificado mediante su dirección SIP.</span><span class="sxs-lookup"><span data-stu-id="69afe-234">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="69afe-235">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="69afe-235">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="69afe-236">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="69afe-236">Get the status of a batch assignment</span></span>

<span data-ttu-id="69afe-237">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="69afe-237">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="69afe-238">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="69afe-238">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="69afe-239">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="69afe-239">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="69afe-240">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="69afe-240">Assign a policy to a group</span></span>

<span data-ttu-id="69afe-241">La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="69afe-241">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="69afe-242">La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="69afe-242">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="69afe-243">A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda.</span><span class="sxs-lookup"><span data-stu-id="69afe-243">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="69afe-244">La asignación de directivas a grupos se recomienda para grupos de hasta 50.000 usuarios, pero también funciona con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="69afe-244">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="69afe-245">Al asignar la Directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-245">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="69afe-246">Sin embargo, ten en cuenta que la propagación de la asignación de directiva a miembros del grupo se realiza como una operación en segundo plano y puede llevar algún tiempo, según el tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-246">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="69afe-247">Lo mismo sucede cuando se elimina la asignación de una directiva de un grupo, o cuando se agregan miembros a un grupo o se quitan de él.</span><span class="sxs-lookup"><span data-stu-id="69afe-247">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="69afe-248">Lo que debe saber sobre la asignación de directivas a grupos</span><span class="sxs-lookup"><span data-stu-id="69afe-248">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="69afe-249">Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-249">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="69afe-250">Reglas de prioridad</span><span class="sxs-lookup"><span data-stu-id="69afe-250">Precedence rules</span></span>

<span data-ttu-id="69afe-251">Para un tipo de directiva determinado, la Directiva efectiva del usuario se determina de acuerdo con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69afe-251">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="69afe-252">Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo que esté asignada a un grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-252">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="69afe-253">En otras palabras, si un usuario tiene asignada directamente una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-253">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="69afe-254">Esto también significa que si un usuario tiene una directiva de un determinado tipo que se le asignó directamente, tendrá que quitar esa Directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-254">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="69afe-255">Si un usuario no tiene una directiva asignada directamente y es miembro de dos o más grupos y cada grupo tiene una directiva del mismo tipo que tiene asignada, el usuario hereda la Directiva de la asignación de grupo que tiene la clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="69afe-255">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="69afe-256">Si un usuario no es miembro de ningún grupo al que se le ha asignado una directiva, la directiva global (opción predeterminada para toda la organización) para ese tipo de Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-256">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="69afe-257">La Directiva efectiva de un usuario se actualiza de acuerdo con estas reglas cuando se agrega o se quita un usuario de un grupo al que se asigna una directiva, se elimina la asignación de una directiva de un grupo o se quita una directiva que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-257">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="69afe-258">Clasificación de asignación de grupo</span><span class="sxs-lookup"><span data-stu-id="69afe-258">Group assignment ranking</span></span>
 
<span data-ttu-id="69afe-259">Cuando se asigna una directiva a un grupo, se especifica una clasificación para la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-259">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="69afe-260">Se usa para determinar qué directiva debe heredar un usuario como su Directiva efectiva si el usuario es miembro de dos o más grupos y se le asigna una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="69afe-260">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="69afe-261">La clasificación de la asignación de grupo es relativa a otras asignaciones de grupo del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="69afe-261">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="69afe-262">Por ejemplo, si va a asignar una directiva de llamadas a dos grupos, establezca la jerarquía de una asignación en 1 y la otra en 2, siendo 1 el ranking más alto.</span><span class="sxs-lookup"><span data-stu-id="69afe-262">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="69afe-263">La clasificación de la asignación de grupo indica qué pertenencia de grupo es más importante o más relevante que otras pertenencias a grupos en relación con la herencia.</span><span class="sxs-lookup"><span data-stu-id="69afe-263">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="69afe-264">Por ejemplo, supongamos que tiene dos grupos, guarda empleados y administradores de la tienda.</span><span class="sxs-lookup"><span data-stu-id="69afe-264">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="69afe-265">Ambos grupos tienen asignada una directiva de llamadas de equipo, almacenan empleados que llaman a la Directiva de llamadas y a los jefes de tienda, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="69afe-265">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="69afe-266">En el caso de un administrador de tienda que esté en ambos grupos, su rol como director es más relevante que su rol como empleado, por lo que la política de llamadas que se asigna al grupo de administradores de la tienda debería tener una clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="69afe-266">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="69afe-267">Mesa</span><span class="sxs-lookup"><span data-stu-id="69afe-267">Group</span></span> |<span data-ttu-id="69afe-268">Nombre de directiva de llamadas de equipo</span><span class="sxs-lookup"><span data-stu-id="69afe-268">Teams calling policy name</span></span>  |<span data-ttu-id="69afe-269">Clasificación</span><span class="sxs-lookup"><span data-stu-id="69afe-269">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="69afe-270">Administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="69afe-270">Store Managers</span></span>   |<span data-ttu-id="69afe-271">Directiva de llamadas a administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="69afe-271">Store Managers Calling Policy</span></span>         |<span data-ttu-id="69afe-272">1</span><span class="sxs-lookup"><span data-stu-id="69afe-272">1</span></span>|
|<span data-ttu-id="69afe-273">Almacenar empleados</span><span class="sxs-lookup"><span data-stu-id="69afe-273">Store Employees</span></span>    |<span data-ttu-id="69afe-274">Almacenar la política de llamadas</span><span class="sxs-lookup"><span data-stu-id="69afe-274">Store Employees Calling Policy</span></span>      |<span data-ttu-id="69afe-275">2</span><span class="sxs-lookup"><span data-stu-id="69afe-275">2</span></span>|

<span data-ttu-id="69afe-276">Si no especifica una clasificación, la asignación de directiva recibe la clasificación más baja.</span><span class="sxs-lookup"><span data-stu-id="69afe-276">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="69afe-277">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-277">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="69afe-278">Por el momento, la asignación de directivas a grupos que usan el centro de administración de Microsoft Teams solo está disponible para la Directiva de llamadas de Teams, la Directiva de Parque de llamadas de Teams, la Directiva de Teams, la Directiva de eventos en vivo de Teams, la Directiva de reuniones</span><span class="sxs-lookup"><span data-stu-id="69afe-278">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="69afe-279">Para otros tipos de directivas, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69afe-279">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="69afe-280">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-280">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="69afe-281">Por ejemplo, vaya a **Meetings**  >  **las directivas de reunión**de reuniones.</span><span class="sxs-lookup"><span data-stu-id="69afe-281">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="69afe-282">Seleccione la pestaña **asignación de directiva de grupo** .</span><span class="sxs-lookup"><span data-stu-id="69afe-282">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="69afe-283">Seleccione **Agregar grupo**y, a continuación, en el panel **asignar Directiva a grupo** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69afe-283">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="69afe-284">Busque y agregue el grupo al que desea asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-284">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="69afe-285">Establezca la clasificación de la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-285">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="69afe-286">Seleccione la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="69afe-286">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="69afe-287">Seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="69afe-287">Select **Apply**.</span></span>

<span data-ttu-id="69afe-288">Para quitar una asignación de directiva de grupo, en la pestaña **asignación de directiva de grupo** de la página de Directiva, seleccione la asignación de grupo y, a continuación, seleccione **quitar**.</span><span class="sxs-lookup"><span data-stu-id="69afe-288">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="69afe-289">Para cambiar la jerarquía de una asignación de grupo, primero debe quitar la asignación de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-289">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="69afe-290">Después, siga los pasos anteriores para asignar la Directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-290">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="69afe-291">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="69afe-291">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="69afe-292">Por el momento, la asignación de directivas a grupos con PowerShell no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="69afe-292">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="69afe-293">Vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="69afe-293">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="69afe-294">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-294">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="69afe-295">Para obtener instrucciones paso a paso, consulte [instalar Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="69afe-295">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="69afe-296">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="69afe-296">Assign a policy to a group</span></span>

<span data-ttu-id="69afe-297">Use el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-297">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="69afe-298">Puede especificar un grupo mediante el identificador de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="69afe-298">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="69afe-299">En este ejemplo, usamos el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva de reunión de Teams denominada Directiva de reunión de directores minoristas a un grupo con una clasificación de asignación de 1.</span><span class="sxs-lookup"><span data-stu-id="69afe-299">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="69afe-300">Para obtener más información, vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="69afe-300">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="69afe-301">Obtener asignaciones de directivas para un grupo</span><span class="sxs-lookup"><span data-stu-id="69afe-301">Get policy assignments for a group</span></span>

<span data-ttu-id="69afe-302">Use el ```Get-CsGroupPolicyAssignment``` cmdlet para obtener todas las directivas asignadas a un grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-302">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="69afe-303">Ten en cuenta que los grupos siempre aparecen en la lista por su identificador de grupo aunque su dirección SIP o dirección de correo electrónico se hayan usado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-303">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="69afe-304">En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="69afe-304">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="69afe-305">En este ejemplo, se devuelven todos los grupos que tienen asignada una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="69afe-305">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="69afe-306">Para obtener más información, vea [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="69afe-306">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="69afe-307">Quitar una directiva de un grupo</span><span class="sxs-lookup"><span data-stu-id="69afe-307">Remove a policy from a group</span></span>

<span data-ttu-id="69afe-308">Use el ```Remove-CsGroupPolicyAssignment``` cmdlet para quitar una directiva de un grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-308">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="69afe-309">Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y con una clasificación menor.</span><span class="sxs-lookup"><span data-stu-id="69afe-309">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="69afe-310">Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tengan una jerarquía de 3 y 4 se actualizarán para reflejar su nueva clasificación.</span><span class="sxs-lookup"><span data-stu-id="69afe-310">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="69afe-311">En las dos tablas siguientes se muestra este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="69afe-311">The following two tables show this example.</span></span>

<span data-ttu-id="69afe-312">A continuación se ofrece una lista de las asignaciones de directivas y las prioridades de una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="69afe-312">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="69afe-313">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="69afe-313">Group name</span></span>  |<span data-ttu-id="69afe-314">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="69afe-314">Policy name</span></span>  |<span data-ttu-id="69afe-315">Clasificación</span><span class="sxs-lookup"><span data-stu-id="69afe-315">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="69afe-316">Ventas</span><span class="sxs-lookup"><span data-stu-id="69afe-316">Sales</span></span>    |<span data-ttu-id="69afe-317">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="69afe-317">Sales policy</span></span>       | <span data-ttu-id="69afe-318">1</span><span class="sxs-lookup"><span data-stu-id="69afe-318">1</span></span>        |
|<span data-ttu-id="69afe-319">Región occidental</span><span class="sxs-lookup"><span data-stu-id="69afe-319">West Region</span></span>     |<span data-ttu-id="69afe-320">Política de la región occidental</span><span class="sxs-lookup"><span data-stu-id="69afe-320">West Region policy</span></span>         |<span data-ttu-id="69afe-321">2</span><span class="sxs-lookup"><span data-stu-id="69afe-321">2</span></span>         |
|<span data-ttu-id="69afe-322">Departamentos</span><span class="sxs-lookup"><span data-stu-id="69afe-322">Division</span></span>    |<span data-ttu-id="69afe-323">Política de división</span><span class="sxs-lookup"><span data-stu-id="69afe-323">Division policy</span></span>         |<span data-ttu-id="69afe-324">3</span><span class="sxs-lookup"><span data-stu-id="69afe-324">3</span></span>         |
|<span data-ttu-id="69afe-325">Secundaria</span><span class="sxs-lookup"><span data-stu-id="69afe-325">Subsidiary</span></span>   |<span data-ttu-id="69afe-326">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="69afe-326">Subsidiary policy</span></span>        |<span data-ttu-id="69afe-327">4</span><span class="sxs-lookup"><span data-stu-id="69afe-327">4</span></span>         |

<span data-ttu-id="69afe-328">Si quitamos la política de región occidental del grupo región oeste, las asignaciones y prioridades de directivas se actualizan de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="69afe-328">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="69afe-329">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="69afe-329">Group name</span></span>  |<span data-ttu-id="69afe-330">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="69afe-330">Policy name</span></span>  |<span data-ttu-id="69afe-331">Clasificación</span><span class="sxs-lookup"><span data-stu-id="69afe-331">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="69afe-332">Ventas</span><span class="sxs-lookup"><span data-stu-id="69afe-332">Sales</span></span>    |<span data-ttu-id="69afe-333">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="69afe-333">Sales policy</span></span>       | <span data-ttu-id="69afe-334">1</span><span class="sxs-lookup"><span data-stu-id="69afe-334">1</span></span>        |
|<span data-ttu-id="69afe-335">Departamentos</span><span class="sxs-lookup"><span data-stu-id="69afe-335">Division</span></span>    |<span data-ttu-id="69afe-336">Política de división</span><span class="sxs-lookup"><span data-stu-id="69afe-336">Division policy</span></span>         |<span data-ttu-id="69afe-337">2</span><span class="sxs-lookup"><span data-stu-id="69afe-337">2</span></span>         |
|<span data-ttu-id="69afe-338">Secundaria</span><span class="sxs-lookup"><span data-stu-id="69afe-338">Subsidiary</span></span>   |<span data-ttu-id="69afe-339">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="69afe-339">Subsidiary policy</span></span>        |<span data-ttu-id="69afe-340">3</span><span class="sxs-lookup"><span data-stu-id="69afe-340">3</span></span>        |

<span data-ttu-id="69afe-341">En este ejemplo, quitamos la política de reuniones de Teams de un grupo.</span><span class="sxs-lookup"><span data-stu-id="69afe-341">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="69afe-342">Para obtener más información, consulte [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="69afe-342">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="69afe-343">Cambiar una asignación de directiva para un grupo</span><span class="sxs-lookup"><span data-stu-id="69afe-343">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="69afe-344">El ```Set-CsGroupPolicyAssignment``` cmdlet estará disponible pronto.</span><span class="sxs-lookup"><span data-stu-id="69afe-344">The ```Set-CsGroupPolicyAssignment``` cmdlet will be available soon.</span></span> <span data-ttu-id="69afe-345">Mientras tanto, para cambiar una asignación de directiva de grupo, puede quitar la asignación de directiva actual del grupo y, a continuación, agregar una nueva asignación de directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-345">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="69afe-346">Después de asignar una directiva a un grupo, puede usar el ```Set-CsGroupPolicyAssignment``` cmdlet para cambiar la asignación de directivas del grupo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="69afe-346">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignment``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="69afe-347">Cambiar la clasificación</span><span class="sxs-lookup"><span data-stu-id="69afe-347">Change the ranking</span></span>
- <span data-ttu-id="69afe-348">Cambiar la Directiva de un tipo de directiva determinado</span><span class="sxs-lookup"><span data-stu-id="69afe-348">Change the policy of a given policy type</span></span>
- <span data-ttu-id="69afe-349">Cambiar la Directiva de un determinado tipo de directiva y la clasificación</span><span class="sxs-lookup"><span data-stu-id="69afe-349">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="69afe-350">En este ejemplo, cambiamos la Directiva de los equipos de un grupo a una directiva llamada SupportCallPark y la clasificación de asignación a 3.</span><span class="sxs-lookup"><span data-stu-id="69afe-350">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="69afe-351">Para obtener más información, consulte [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="69afe-351">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>



#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="69afe-352">Cambiar la Directiva efectiva de un usuario</span><span class="sxs-lookup"><span data-stu-id="69afe-352">Change the effective policy for a user</span></span>

<span data-ttu-id="69afe-353">Este es un ejemplo de cómo cambiar la Directiva efectiva para un usuario que tiene asignada directamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="69afe-353">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="69afe-354">En primer lugar, usamos el ```Get-CsUserPolicyAssignment``` cmdlet junto con el ```PolicySource``` parámetro para obtener detalles de los equipos de reunión de las directivas de difusión asociados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-354">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="69afe-355">Para obtener más información, vea [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="69afe-355">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="69afe-356">En la salida se muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada eventos de empleados, que tiene prioridad sobre la Directiva denominada eventos de proveedor que se asignan a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-356">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="69afe-357">Ahora, quitamos la Directiva de eventos de empleados del usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-357">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="69afe-358">Esto significa que el usuario ya no tiene una directiva de difusión de reunión de equipos que se les asignó directamente y heredará la Directiva de eventos en vivo de proveedores que se asigna al grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-358">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="69afe-359">Use el siguiente cmdlet en el módulo de PowerShell de Skype empresarial para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="69afe-359">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="69afe-360">Puede usar el siguiente cmdlet en el módulo de PowerShell de Teams para hacerlo a escala mediante una asignación de Directiva por lotes, donde $users es una lista de los usuarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="69afe-360">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="69afe-361">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="69afe-361">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="69afe-362">Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directivas a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="69afe-362">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="69afe-363">Use el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para enviar un lote de usuarios y el paquete de directivas que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="69afe-363">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="69afe-364">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="69afe-364">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="69afe-365">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="69afe-365">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="69afe-366">Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="69afe-366">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="69afe-367">Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="69afe-367">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="69afe-368">Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario.</span><span class="sxs-lookup"><span data-stu-id="69afe-368">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="69afe-369">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="69afe-369">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="69afe-370">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="69afe-370">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="69afe-371">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="69afe-371">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="69afe-372">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="69afe-372">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="69afe-373">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-373">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="69afe-374">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si todavía no lo ha hecho).</span><span class="sxs-lookup"><span data-stu-id="69afe-374">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="69afe-375">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="69afe-375">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="69afe-376">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="69afe-376">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="69afe-377">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="69afe-377">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="69afe-378">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="69afe-378">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="69afe-379">En este ejemplo, usamos el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para asignar el paquete de directivas Education_PrimaryStudent a un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="69afe-379">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="69afe-380">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="69afe-380">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="69afe-381">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="69afe-381">Get the status of a batch assignment</span></span>

<span data-ttu-id="69afe-382">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="69afe-382">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="69afe-383">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="69afe-383">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="69afe-384">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="69afe-384">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="69afe-385">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="69afe-385">Related topics</span></span>

[<span data-ttu-id="69afe-386">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="69afe-386">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
