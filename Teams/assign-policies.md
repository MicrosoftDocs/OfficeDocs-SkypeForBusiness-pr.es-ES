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
ms.openlocfilehash: 403131fa3e7bd2b3fb2a128640ac49497394d669
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938549"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="55b45-103">Asignar directivas a los usuarios de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="55b45-104">**Tenga en cuenta lo siguiente sobre una de las características descritas en este artículo, asignación de directiva a grupos**:</span><span class="sxs-lookup"><span data-stu-id="55b45-104">**Note the following about one of the features discussed in this article, policy assignment to groups**:</span></span> 
> - <span data-ttu-id="55b45-105">[Asignación de directiva a grupos mediante el centro de administración de Microsoft Teams](#using-the-microsoft-teams-admin-center-3)todavía no se ha publicado.</span><span class="sxs-lookup"><span data-stu-id="55b45-105">[Policy assignment to groups using the Microsoft Teams admin center](#using-the-microsoft-teams-admin-center-3), hasn't yet been released.</span></span> <span data-ttu-id="55b45-106">Se ha anunciado y pronto estará disponible.</span><span class="sxs-lookup"><span data-stu-id="55b45-106">It's been announced, and it's coming soon.</span></span> 
> - <span data-ttu-id="55b45-107">La [asignación de directivas a grupos con PowerShell](#using-powershell-3)solo está disponible actualmente en Private Preview.</span><span class="sxs-lookup"><span data-stu-id="55b45-107">[Policy assignment to groups using PowerShell](#using-powershell-3), is currently only available in private preview.</span></span> <span data-ttu-id="55b45-108">Los cmdlets de PowerShell para esta característica se encuentran en el módulo PowerShell de la versión preliminar de Teams.</span><span class="sxs-lookup"><span data-stu-id="55b45-108">The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.</span></span>
>
> <span data-ttu-id="55b45-109">Para estar al día del estado de versión de esta característica, consulte la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="55b45-109">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="55b45-110">Como administrador, use directivas para controlar las características de teams que están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="55b45-110">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="55b45-111">Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por citar algunas.</span><span class="sxs-lookup"><span data-stu-id="55b45-111">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="55b45-112">Las organizaciones tienen diferentes tipos de usuarios con necesidades exclusivas y directivas personalizadas que usted crea y asigna le permiten adaptar la configuración de directivas a distintos conjuntos de usuarios según esas necesidades.</span><span class="sxs-lookup"><span data-stu-id="55b45-112">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="55b45-113">Para facilitar la administración de directivas de su organización, Teams ofrece varias formas de asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="55b45-113">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="55b45-114">Puede asignar una directiva directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes, o a un grupo del que son miembros los usuarios.</span><span class="sxs-lookup"><span data-stu-id="55b45-114">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="55b45-115">También puede usar paquetes de directivas para asignar una colección preconfigurada de directivas a los usuarios de su organización que tengan roles similares.</span><span class="sxs-lookup"><span data-stu-id="55b45-115">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="55b45-116">La opción que elija dependerá del número de directivas que esté administrando y del número de usuarios a los que va a asignar.</span><span class="sxs-lookup"><span data-stu-id="55b45-116">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="55b45-117">Al configurar las directivas globales (predeterminada para toda la organización) de modo que se apliquen al mayor número de usuarios de su organización, solo tiene que asignar directivas a aquellos usuarios que requieran directivas especializadas.</span><span class="sxs-lookup"><span data-stu-id="55b45-117">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="55b45-118">En este artículo se describen las diferentes maneras en las que puede asignar directivas a los usuarios y las situaciones recomendadas para Cuándo usarlas.</span><span class="sxs-lookup"><span data-stu-id="55b45-118">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="55b45-119">¿Qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="55b45-119">Which policy takes precedence?</span></span>

<span data-ttu-id="55b45-120">Un usuario tiene una directiva vigente para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-120">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="55b45-121">Es posible o incluso probable que un usuario tenga asignada directamente una directiva y también es miembro de uno o más grupos a los que se ha asignado una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="55b45-121">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="55b45-122">En estos tipos de escenarios, ¿qué directiva tiene prioridad?</span><span class="sxs-lookup"><span data-stu-id="55b45-122">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="55b45-123">La Directiva efectiva del usuario se determina según las reglas de prioridad, de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="55b45-123">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="55b45-124">Si un usuario tiene asignada directamente una directiva (ya sea de forma individual o mediante una asignación por lotes), tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="55b45-124">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="55b45-125">En el ejemplo siguiente, la Directiva efectiva del usuario es la Lincoln cuadrada de la reunión, que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-125">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva asignada directamente](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="55b45-127">Si un usuario no tiene asignada directamente una directiva de un tipo determinado, tendrá prioridad la directiva asignada a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-127">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="55b45-128">Si un usuario es miembro de varios grupos, tiene prioridad la Directiva que tiene la mayor [clasificación de asignación de grupo](#group-assignment-ranking) para el tipo de directiva determinado.</span><span class="sxs-lookup"><span data-stu-id="55b45-128">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="55b45-129">En este ejemplo, la Directiva efectiva del usuario es el equipo de ejecución y la Directiva de alta definición, que tiene la mayor clasificación de asignación relativa a otros grupos de los que el usuario es miembro y al que también se les ha asignado una directiva del mismo tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-129">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama que muestra cómo tiene prioridad una directiva heredada del grupo](media/assign-policies-example-group.png)

<span data-ttu-id="55b45-131">Si un usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario recibirá la directiva global (opción predeterminada para toda la organización) para ese tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-131">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="55b45-132">Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="55b45-132">Here's an example.</span></span>

![Diagrama que muestra cómo tiene prioridad una directiva global](media/assign-policies-example-global.png)

<span data-ttu-id="55b45-134">Para obtener más información, vea [reglas de prioridad](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="55b45-134">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="55b45-135">Formas de asignar directivas</span><span class="sxs-lookup"><span data-stu-id="55b45-135">Ways to assign policies</span></span>

<span data-ttu-id="55b45-136">A continuación se ofrece una descripción general de las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno.</span><span class="sxs-lookup"><span data-stu-id="55b45-136">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="55b45-137">Haga clic en los vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="55b45-137">Click the links to learn more.</span></span>

<span data-ttu-id="55b45-138">Antes de asignar directivas a usuarios individuales o grupos, primero [establezca las directivas globales (valor predeterminado de organización)](#set-the-global-policies) para que se apliquen al mayor número de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="55b45-138">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="55b45-139">Una vez configuradas las directivas globales, solo tendrá que asignar directivas a aquellos usuarios que requieran directivas especializadas.</span><span class="sxs-lookup"><span data-stu-id="55b45-139">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="55b45-140">Haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="55b45-140">Do this</span></span>  |<span data-ttu-id="55b45-141">Si...</span><span class="sxs-lookup"><span data-stu-id="55b45-141">If...</span></span>  | <span data-ttu-id="55b45-142">Usar...</span><span class="sxs-lookup"><span data-stu-id="55b45-142">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="55b45-143">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="55b45-143">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="55b45-144">Ya está familiarizado con Teams y solo necesita asignar una o dos directivas a un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="55b45-144">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="55b45-145">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="55b45-145">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="55b45-146">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="55b45-146">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="55b45-147">Debe asignar varias directivas a conjuntos específicos de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="55b45-147">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="55b45-148">Por ejemplo, asigne el paquete de directivas Educación (profesor) a los profesores de su escuela para proporcionarles acceso completo a chats, llamadas y reuniones, y al paquete de directivas Educación (estudiante secundario escolar) a los estudiantes secundarios para limitar ciertas funciones como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="55b45-148">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="55b45-149">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="55b45-150">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="55b45-150">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="55b45-151">Debe asignar directivas a grandes conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="55b45-151">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="55b45-152">Por ejemplo, desea asignar una directiva a cientos o miles de usuarios de su organización al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="55b45-152">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="55b45-153">El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-153">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="55b45-154">[Asignar una directiva a un grupo](#assign-a-policy-to-a-group) (en vista previa o próximamente)</span><span class="sxs-lookup"><span data-stu-id="55b45-154">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview/coming soon)</span></span>|<span data-ttu-id="55b45-155">Debe asignar directivas en función de la pertenencia a grupos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-155">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="55b45-156">Por ejemplo, desea asignar una directiva a todos los usuarios de un grupo de seguridad o de una unidad de organización.</span><span class="sxs-lookup"><span data-stu-id="55b45-156">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="55b45-157">El centro de administración de Microsoft Teams (próximamente) o cmdlets de PowerShell en el módulo de PowerShell de Teams (en versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="55b45-157">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module (in preview)</span></span>|
| [<span data-ttu-id="55b45-158">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="55b45-158">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="55b45-159">Debe asignar varias directivas a un lote de usuarios de su organización que tengan roles iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="55b45-159">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="55b45-160">Por ejemplo, asigne el paquete de directivas Educación (profesor) a todos los profesores de su escuela mediante la asignación por lotes para proporcionarles acceso total a chats, llamadas y reuniones, y asigne el paquete de directivas Educación (estudiante secundario) a un lote de estudiantes secundarios para limitar ciertas capacidades como las llamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="55b45-160">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="55b45-161">Cmdlets de PowerShell en el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-161">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="55b45-162">Asignar un paquete de directivas a un grupo (próximamente)</span><span class="sxs-lookup"><span data-stu-id="55b45-162">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="55b45-163">Establecer las directivas globales</span><span class="sxs-lookup"><span data-stu-id="55b45-163">Set the global policies</span></span>

<span data-ttu-id="55b45-164">Siga estos pasos para establecer las directivas globales (valor predeterminado de la organización) para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-164">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="55b45-165">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-165">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="55b45-166">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de directivas del tipo de directiva que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="55b45-166">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="55b45-167">Por ejemplo, **Teams**  >  **Policies**, directivas de reuniones de **reuniones**  >  **Meetings policies**, **directivas de mensajería**o directivas de llamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="55b45-167">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="55b45-168">Seleccione la directiva **global (opción predeterminada para toda la organización)** para ver la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="55b45-168">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="55b45-169">Actualice la Directiva según sea necesario y, a continuación, seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="55b45-169">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="55b45-170">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="55b45-170">Using PowerShell</span></span>

<span data-ttu-id="55b45-171">Para establecer las directivas globales mediante PowerShell, use el identificador global.</span><span class="sxs-lookup"><span data-stu-id="55b45-171">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="55b45-172">Para empezar, revisamos la directiva global actual para determinar qué configuración desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="55b45-172">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="55b45-173">A continuación, actualice la directiva global según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="55b45-173">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="55b45-174">Solo tiene que especificar los valores de la configuración que quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="55b45-174">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="55b45-175">Asignar una directiva a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="55b45-175">Assign a policy to individual users</span></span>

<span data-ttu-id="55b45-176">Siga estos pasos para asignar una directiva a un usuario individual o a un número reducido de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="55b45-176">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="55b45-177">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-177">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="55b45-178">Para asignar una directiva a un usuario:</span><span class="sxs-lookup"><span data-stu-id="55b45-178">To assign a policy to a user:</span></span>

1. <span data-ttu-id="55b45-179">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-179">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="55b45-180">Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.</span><span class="sxs-lookup"><span data-stu-id="55b45-180">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="55b45-181">Seleccione la Directiva que desea asignar y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="55b45-181">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="55b45-182">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55b45-182">Or, you can also do the following:</span></span>

1. <span data-ttu-id="55b45-183">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-183">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="55b45-184">Seleccione la Directiva que desea asignar haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-184">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="55b45-185">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="55b45-185">Select **Manage users**.</span></span>
4. <span data-ttu-id="55b45-186">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="55b45-186">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="55b45-187">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="55b45-187">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="55b45-188">Cuando haya terminado de agregar usuarios, seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="55b45-188">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="55b45-189">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="55b45-189">Using PowerShell</span></span>

<span data-ttu-id="55b45-190">Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo.</span><span class="sxs-lookup"><span data-stu-id="55b45-190">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="55b45-191">Use el ```Grant-``` cmdlet para un tipo de directiva determinado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-191">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="55b45-192">Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una política de reunión de Teams a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="55b45-192">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="55b45-193">Estos cmdlets están incluidos en el módulo de PowerShell de Skype empresarial online y están documentados en la [Referencia del cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="55b45-193">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="55b45-194">Descargue e instale el [módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si todavía no lo ha hecho) y, a continuación, ejecute lo siguiente para conectarse a Skype empresarial online e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="55b45-194">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="55b45-195">En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiantes a un usuario denominado Reda.</span><span class="sxs-lookup"><span data-stu-id="55b45-195">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="55b45-196">Para obtener más información, vea [Administrar directivas mediante PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="55b45-196">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="55b45-197">Asignar un paquete de directivas</span><span class="sxs-lookup"><span data-stu-id="55b45-197">Assign a policy package</span></span>

<span data-ttu-id="55b45-198">Un paquete de directivas de Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles iguales o similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="55b45-198">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="55b45-199">Cada paquete de directivas está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten actividades típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="55b45-199">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="55b45-200">Algunos ejemplos de paquetes de directivas son el paquete educativo (profesor) y el paquete de salud (trabajador clínico).</span><span class="sxs-lookup"><span data-stu-id="55b45-200">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="55b45-201">Cuando se asigna un paquete de directivas a los usuarios, se crean las directivas del paquete y, después, se puede personalizar la configuración de cada Directiva del paquete para satisfacer las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="55b45-201">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="55b45-202">Para obtener más información sobre los paquetes de directivas, incluidas las instrucciones paso a paso sobre cómo asignarlos y administrarlos, consulte [administrar paquetes de directivas en Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="55b45-202">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="55b45-203">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="55b45-203">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="55b45-204">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-204">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="55b45-205">Para asignar una directiva a usuarios en bloque:</span><span class="sxs-lookup"><span data-stu-id="55b45-205">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="55b45-206">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="55b45-206">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="55b45-207">Busque los usuarios a los que desea asignar la Directiva o filtre la vista para mostrar los usuarios que desea.</span><span class="sxs-lookup"><span data-stu-id="55b45-207">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="55b45-208">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="55b45-208">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="55b45-209">Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="55b45-209">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="55b45-210">Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="55b45-210">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="55b45-211">Para ver el estado de la asignación de Directiva, en la pancarta que aparece en la parte superior de la página **usuarios** después de hacer clic en **aplicar** para enviar la asignación de Directiva, haga clic en **registro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="55b45-211">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="55b45-212">O bien, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel**y, a continuación, en **registro de actividades**, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="55b45-212">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="55b45-213">En el registro de actividades se muestran asignaciones de directivas de los lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="55b45-213">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="55b45-214">Para obtener más información, vea [ver las asignaciones de directivas en el registro de actividades](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="55b45-214">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="55b45-215">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="55b45-215">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="55b45-216">Actualmente, la asignación de directivas por lotes con PowerShell no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="55b45-216">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="55b45-217">Vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="55b45-217">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="55b45-218">Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="55b45-218">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="55b45-219">Use el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para enviar un lote de usuarios y la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="55b45-219">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="55b45-220">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="55b45-220">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="55b45-221">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="55b45-221">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="55b45-222">Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="55b45-222">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="55b45-223">Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="55b45-223">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="55b45-224">Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-224">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="55b45-225">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="55b45-225">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="55b45-226">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="55b45-226">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="55b45-227">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="55b45-227">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="55b45-228">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="55b45-228">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="55b45-229">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-229">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="55b45-230">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="55b45-230">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="55b45-231">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="55b45-231">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="55b45-232">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="55b45-232">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="55b45-233">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="55b45-233">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="55b45-234">Instalar y conectarse al módulo de Azure AD PowerShell for Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="55b45-234">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="55b45-235">Es posible que también desee [Descargar e instalar el módulo Azure ad PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (si todavía no lo ha hecho) y conectarse a Azure ad para poder recuperar una lista de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="55b45-235">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="55b45-236">Ejecute lo siguiente para conectarse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="55b45-236">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="55b45-237">Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a teams.</span><span class="sxs-lookup"><span data-stu-id="55b45-237">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="55b45-238">Asignar una directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="55b45-238">Assign a policy to a batch of users</span></span>

<span data-ttu-id="55b45-239">En este ejemplo, usamos el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para asignar una directiva de configuración de aplicación denominada Directiva de configuración de la aplicación de RRHH a un lote de usuarios que aparece en el archivo Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="55b45-239">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="55b45-240">En este ejemplo, se conectará a Azure AD para recuperar una colección de usuarios y, a continuación, asignar una directiva de mensajería llamada nueva Directiva de mensajería de contratación a un lote de usuarios especificado mediante su dirección SIP.</span><span class="sxs-lookup"><span data-stu-id="55b45-240">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="55b45-241">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="55b45-241">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="55b45-242">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="55b45-242">Get the status of a batch assignment</span></span>

<span data-ttu-id="55b45-243">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="55b45-243">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="55b45-244">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="55b45-244">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="55b45-245">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="55b45-245">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="55b45-246">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="55b45-246">Assign a policy to a group</span></span>

<span data-ttu-id="55b45-247">La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="55b45-247">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="55b45-248">La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="55b45-248">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="55b45-249">A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda.</span><span class="sxs-lookup"><span data-stu-id="55b45-249">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="55b45-250">La asignación de directivas a grupos se recomienda para grupos de hasta 50.000 usuarios, pero también funciona con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="55b45-250">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="55b45-251">Al asignar la Directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-251">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="55b45-252">Sin embargo, ten en cuenta que la propagación de la asignación de directiva a miembros del grupo se realiza como una operación en segundo plano y puede llevar algún tiempo, según el tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-252">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="55b45-253">Lo mismo sucede cuando se elimina la asignación de una directiva de un grupo, o cuando se agregan miembros a un grupo o se quitan de él.</span><span class="sxs-lookup"><span data-stu-id="55b45-253">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="55b45-254">Lo que debe saber sobre la asignación de directivas a grupos</span><span class="sxs-lookup"><span data-stu-id="55b45-254">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="55b45-255">Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-255">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="55b45-256">Reglas de prioridad</span><span class="sxs-lookup"><span data-stu-id="55b45-256">Precedence rules</span></span>

<span data-ttu-id="55b45-257">Para un tipo de directiva determinado, la Directiva efectiva del usuario se determina de acuerdo con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55b45-257">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="55b45-258">Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo que esté asignada a un grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-258">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="55b45-259">En otras palabras, si un usuario tiene asignada directamente una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-259">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="55b45-260">Esto también significa que si un usuario tiene una directiva de un determinado tipo que se le asignó directamente, tendrá que quitar esa Directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-260">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="55b45-261">Si un usuario no tiene una directiva asignada directamente y es miembro de dos o más grupos y cada grupo tiene una directiva del mismo tipo que tiene asignada, el usuario hereda la Directiva de la asignación de grupo que tiene la clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="55b45-261">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="55b45-262">Si un usuario no es miembro de ningún grupo al que se le ha asignado una directiva, la directiva global (opción predeterminada para toda la organización) para ese tipo de Directiva se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-262">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="55b45-263">La Directiva efectiva de un usuario se actualiza de acuerdo con estas reglas cuando se agrega o se quita un usuario de un grupo al que se asigna una directiva, se elimina la asignación de una directiva de un grupo o se quita una directiva que se asigna directamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-263">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="55b45-264">Clasificación de asignación de grupo</span><span class="sxs-lookup"><span data-stu-id="55b45-264">Group assignment ranking</span></span>
 
<span data-ttu-id="55b45-265">Cuando se asigna una directiva a un grupo, se especifica una clasificación para la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-265">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="55b45-266">Se usa para determinar qué directiva debe heredar un usuario como su Directiva efectiva si el usuario es miembro de dos o más grupos y se le asigna una directiva del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="55b45-266">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="55b45-267">La clasificación de la asignación de grupo es relativa a otras asignaciones de grupo del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="55b45-267">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="55b45-268">Por ejemplo, si va a asignar una directiva de llamadas a dos grupos, establezca la jerarquía de una asignación en 1 y la otra en 2, siendo 1 el ranking más alto.</span><span class="sxs-lookup"><span data-stu-id="55b45-268">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="55b45-269">La clasificación de la asignación de grupo indica qué pertenencia de grupo es más importante o más relevante que otras pertenencias a grupos en relación con la herencia.</span><span class="sxs-lookup"><span data-stu-id="55b45-269">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="55b45-270">Por ejemplo, supongamos que tiene dos grupos, guarda empleados y administradores de la tienda.</span><span class="sxs-lookup"><span data-stu-id="55b45-270">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="55b45-271">Ambos grupos tienen asignada una directiva de llamadas de equipo, almacenan empleados que llaman a la Directiva de llamadas y a los jefes de tienda, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="55b45-271">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="55b45-272">En el caso de un administrador de tienda que esté en ambos grupos, su rol como director es más relevante que su rol como empleado, por lo que la política de llamadas que se asigna al grupo de administradores de la tienda debería tener una clasificación más alta.</span><span class="sxs-lookup"><span data-stu-id="55b45-272">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="55b45-273">Mesa</span><span class="sxs-lookup"><span data-stu-id="55b45-273">Group</span></span> |<span data-ttu-id="55b45-274">Nombre de directiva de llamadas de equipo</span><span class="sxs-lookup"><span data-stu-id="55b45-274">Teams calling policy name</span></span>  |<span data-ttu-id="55b45-275">Clasificación</span><span class="sxs-lookup"><span data-stu-id="55b45-275">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="55b45-276">Administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="55b45-276">Store Managers</span></span>   |<span data-ttu-id="55b45-277">Directiva de llamadas a administradores de tienda</span><span class="sxs-lookup"><span data-stu-id="55b45-277">Store Managers Calling Policy</span></span>         |<span data-ttu-id="55b45-278">1</span><span class="sxs-lookup"><span data-stu-id="55b45-278">1</span></span>|
|<span data-ttu-id="55b45-279">Almacenar empleados</span><span class="sxs-lookup"><span data-stu-id="55b45-279">Store Employees</span></span>    |<span data-ttu-id="55b45-280">Almacenar la política de llamadas</span><span class="sxs-lookup"><span data-stu-id="55b45-280">Store Employees Calling Policy</span></span>      |<span data-ttu-id="55b45-281">2</span><span class="sxs-lookup"><span data-stu-id="55b45-281">2</span></span>|

<span data-ttu-id="55b45-282">Si no especifica una clasificación, la asignación de directiva recibe la clasificación más baja.</span><span class="sxs-lookup"><span data-stu-id="55b45-282">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="55b45-283">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-283">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="55b45-284">**Aún no se ha publicado esta característica. Se ha anunciado y pronto estará disponible.**</span><span class="sxs-lookup"><span data-stu-id="55b45-284">**This feature hasn't yet been released. It's been announced, and it's coming soon.**</span></span>

> [!NOTE]
> <span data-ttu-id="55b45-285">Por el momento, la asignación de directivas a grupos con el centro de administración de Microsoft Teams solo está disponible para la Directiva de llamadas de equipos, la Directiva de reunión de Teams y la Directiva de mensajería de Teams.</span><span class="sxs-lookup"><span data-stu-id="55b45-285">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="55b45-286">Para otros tipos de directivas, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55b45-286">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="55b45-287">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-287">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="55b45-288">Por ejemplo, vaya a **Meetings**  >  **las directivas de reunión**de reuniones.</span><span class="sxs-lookup"><span data-stu-id="55b45-288">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="55b45-289">Seleccione la pestaña **asignación de directiva de grupo** .</span><span class="sxs-lookup"><span data-stu-id="55b45-289">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="55b45-290">Seleccione **Agregar grupo**y, a continuación, en el panel **asignar Directiva a grupo** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55b45-290">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="55b45-291">Busque y agregue el grupo al que desea asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-291">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="55b45-292">Establezca la clasificación de la asignación de grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-292">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="55b45-293">Seleccione la Directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="55b45-293">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="55b45-294">Seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="55b45-294">Select **Apply**.</span></span>

<span data-ttu-id="55b45-295">Para quitar una asignación de directiva de grupo, en la pestaña **asignación de directiva de grupo** de la página de Directiva, seleccione la asignación de grupo y, a continuación, seleccione **quitar**.</span><span class="sxs-lookup"><span data-stu-id="55b45-295">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="55b45-296">Para cambiar la jerarquía de una asignación de grupo, primero debe quitar la asignación de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-296">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="55b45-297">Después, siga los pasos anteriores para asignar la Directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-297">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="55b45-298">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="55b45-298">Using PowerShell</span></span>

<span data-ttu-id="55b45-299">**Esta característica solo está disponible actualmente en Private Preview. Los cmdlets para esta característica se encuentran en el módulo PowerShell de la versión preliminar de Teams.**</span><span class="sxs-lookup"><span data-stu-id="55b45-299">**This feature is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

> [!NOTE]
> <span data-ttu-id="55b45-300">Por el momento, la asignación de directivas a grupos con PowerShell no está disponible para todos los tipos de directivas de Teams.</span><span class="sxs-lookup"><span data-stu-id="55b45-300">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="55b45-301">Vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obtener la lista de tipos de directiva admitidos.</span><span class="sxs-lookup"><span data-stu-id="55b45-301">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="55b45-302">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-302">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="55b45-303">Los cmdlets se encuentran en la versión preliminar del módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="55b45-303">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="55b45-304">Siga estos pasos para desinstalar primero la versión disponible general del módulo de PowerShell de Teams (si está instalada) y, a continuación, instale la última versión preliminar del módulo de la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55b45-304">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="55b45-305">Si todavía no lo ha hecho, ejecute lo siguiente para registrar la galería de pruebas de PowerShell como fuente de confianza.</span><span class="sxs-lookup"><span data-stu-id="55b45-305">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="55b45-306">Si tiene instalada la versión general del módulo de PowerShell de Teams, ejecute lo siguiente para desinstalarla.</span><span class="sxs-lookup"><span data-stu-id="55b45-306">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="55b45-307">Ejecute lo siguiente para instalar el módulo de PowerShell más reciente de Microsoft Teams desde la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55b45-307">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="55b45-308">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="55b45-308">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="55b45-309">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="55b45-309">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="55b45-310">Asignar una directiva a un grupo</span><span class="sxs-lookup"><span data-stu-id="55b45-310">Assign a policy to a group</span></span>

<span data-ttu-id="55b45-311">Use el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-311">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="55b45-312">Puede especificar un grupo mediante el identificador de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="55b45-312">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="55b45-313">En este ejemplo, usamos el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva de reunión de Teams denominada Directiva de reunión de directores minoristas a un grupo con una clasificación de asignación de 1.</span><span class="sxs-lookup"><span data-stu-id="55b45-313">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="55b45-314">Para obtener más información, vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="55b45-314">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="55b45-315">Obtener asignaciones de directivas para un grupo</span><span class="sxs-lookup"><span data-stu-id="55b45-315">Get policy assignments for a group</span></span>

<span data-ttu-id="55b45-316">Use el ```Get-CsGroupPolicyAssignment``` cmdlet para obtener todas las directivas asignadas a un grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-316">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="55b45-317">Ten en cuenta que los grupos siempre aparecen en la lista por su identificador de grupo aunque su dirección SIP o dirección de correo electrónico se hayan usado para asignar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-317">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="55b45-318">En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="55b45-318">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="55b45-319">En este ejemplo, se devuelven todos los grupos que tienen asignada una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="55b45-319">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="55b45-320">Para obtener más información, vea [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="55b45-320">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="55b45-321">Quitar una directiva de un grupo</span><span class="sxs-lookup"><span data-stu-id="55b45-321">Remove a policy from a group</span></span>

<span data-ttu-id="55b45-322">Use el ```Remove-CsGroupPolicyAssignment``` cmdlet para quitar una directiva de un grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-322">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="55b45-323">Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y con una clasificación menor.</span><span class="sxs-lookup"><span data-stu-id="55b45-323">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="55b45-324">Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tengan una jerarquía de 3 y 4 se actualizarán para reflejar su nueva clasificación.</span><span class="sxs-lookup"><span data-stu-id="55b45-324">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="55b45-325">En las dos tablas siguientes se muestra este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="55b45-325">The following two tables show this example.</span></span>

<span data-ttu-id="55b45-326">A continuación se ofrece una lista de las asignaciones de directivas y las prioridades de una directiva de reunión de Teams.</span><span class="sxs-lookup"><span data-stu-id="55b45-326">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="55b45-327">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="55b45-327">Group name</span></span>  |<span data-ttu-id="55b45-328">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="55b45-328">Policy name</span></span>  |<span data-ttu-id="55b45-329">Clasificación</span><span class="sxs-lookup"><span data-stu-id="55b45-329">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="55b45-330">Ventas</span><span class="sxs-lookup"><span data-stu-id="55b45-330">Sales</span></span>    |<span data-ttu-id="55b45-331">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="55b45-331">Sales policy</span></span>       | <span data-ttu-id="55b45-332">1</span><span class="sxs-lookup"><span data-stu-id="55b45-332">1</span></span>        |
|<span data-ttu-id="55b45-333">Región occidental</span><span class="sxs-lookup"><span data-stu-id="55b45-333">West Region</span></span>     |<span data-ttu-id="55b45-334">Política de la región occidental</span><span class="sxs-lookup"><span data-stu-id="55b45-334">West Region policy</span></span>         |<span data-ttu-id="55b45-335">2</span><span class="sxs-lookup"><span data-stu-id="55b45-335">2</span></span>         |
|<span data-ttu-id="55b45-336">Departamentos</span><span class="sxs-lookup"><span data-stu-id="55b45-336">Division</span></span>    |<span data-ttu-id="55b45-337">Política de división</span><span class="sxs-lookup"><span data-stu-id="55b45-337">Division policy</span></span>         |<span data-ttu-id="55b45-338">3</span><span class="sxs-lookup"><span data-stu-id="55b45-338">3</span></span>         |
|<span data-ttu-id="55b45-339">Secundaria</span><span class="sxs-lookup"><span data-stu-id="55b45-339">Subsidiary</span></span>   |<span data-ttu-id="55b45-340">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="55b45-340">Subsidiary policy</span></span>        |<span data-ttu-id="55b45-341">4</span><span class="sxs-lookup"><span data-stu-id="55b45-341">4</span></span>         |

<span data-ttu-id="55b45-342">Si quitamos la política de región occidental del grupo región oeste, las asignaciones y prioridades de directivas se actualizan de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="55b45-342">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="55b45-343">Nombre del grupo</span><span class="sxs-lookup"><span data-stu-id="55b45-343">Group name</span></span>  |<span data-ttu-id="55b45-344">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="55b45-344">Policy name</span></span>  |<span data-ttu-id="55b45-345">Clasificación</span><span class="sxs-lookup"><span data-stu-id="55b45-345">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="55b45-346">Ventas</span><span class="sxs-lookup"><span data-stu-id="55b45-346">Sales</span></span>    |<span data-ttu-id="55b45-347">Política de ventas</span><span class="sxs-lookup"><span data-stu-id="55b45-347">Sales policy</span></span>       | <span data-ttu-id="55b45-348">1</span><span class="sxs-lookup"><span data-stu-id="55b45-348">1</span></span>        |
|<span data-ttu-id="55b45-349">Departamentos</span><span class="sxs-lookup"><span data-stu-id="55b45-349">Division</span></span>    |<span data-ttu-id="55b45-350">Política de división</span><span class="sxs-lookup"><span data-stu-id="55b45-350">Division policy</span></span>         |<span data-ttu-id="55b45-351">2</span><span class="sxs-lookup"><span data-stu-id="55b45-351">2</span></span>         |
|<span data-ttu-id="55b45-352">Secundaria</span><span class="sxs-lookup"><span data-stu-id="55b45-352">Subsidiary</span></span>   |<span data-ttu-id="55b45-353">Directiva subsidiaria</span><span class="sxs-lookup"><span data-stu-id="55b45-353">Subsidiary policy</span></span>        |<span data-ttu-id="55b45-354">3</span><span class="sxs-lookup"><span data-stu-id="55b45-354">3</span></span>        |

<span data-ttu-id="55b45-355">En este ejemplo, quitamos la política de reuniones de Teams de un grupo.</span><span class="sxs-lookup"><span data-stu-id="55b45-355">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="55b45-356">Para obtener más información, consulte [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="55b45-356">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="55b45-357">Cambiar una asignación de directiva para un grupo</span><span class="sxs-lookup"><span data-stu-id="55b45-357">Change a policy assignment for a group</span></span>

<span data-ttu-id="55b45-358">Después de asignar una directiva a un grupo, puede usar el ```Set-CsGroupPolicyAssignment``` cmdlet para cambiar la asignación de directivas del grupo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="55b45-358">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignment``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="55b45-359">Cambiar la clasificación</span><span class="sxs-lookup"><span data-stu-id="55b45-359">Change the ranking</span></span>
- <span data-ttu-id="55b45-360">Cambiar la Directiva de un tipo de directiva determinado</span><span class="sxs-lookup"><span data-stu-id="55b45-360">Change the policy of a given policy type</span></span>
- <span data-ttu-id="55b45-361">Cambiar la Directiva de un determinado tipo de directiva y la clasificación</span><span class="sxs-lookup"><span data-stu-id="55b45-361">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="55b45-362">En este ejemplo, cambiamos la Directiva de los equipos de un grupo a una directiva llamada SupportCallPark y la clasificación de asignación a 3.</span><span class="sxs-lookup"><span data-stu-id="55b45-362">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="55b45-363">Para obtener más información, consulte [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="55b45-363">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="55b45-364">Cambiar la Directiva efectiva de un usuario</span><span class="sxs-lookup"><span data-stu-id="55b45-364">Change the effective policy for a user</span></span>

<span data-ttu-id="55b45-365">Este es un ejemplo de cómo cambiar la Directiva efectiva para un usuario que tiene asignada directamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="55b45-365">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="55b45-366">En primer lugar, usamos el ```Get-CsUserPolicyAssignment``` cmdlet junto con el ```PolicySource``` parámetro para obtener detalles de los equipos de reunión de las directivas de difusión asociados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-366">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="55b45-367">Para obtener más información, vea [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="55b45-367">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="55b45-368">En la salida se muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada eventos de empleados, que tiene prioridad sobre la Directiva denominada eventos de proveedor que se asignan a un grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-368">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="55b45-369">Ahora, quitamos la Directiva de eventos de empleados del usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-369">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="55b45-370">Esto significa que el usuario ya no tiene una directiva de difusión de reunión de equipos que se les asignó directamente y heredará la Directiva de eventos en vivo de proveedores que se asigna al grupo al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-370">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="55b45-371">Use el siguiente cmdlet en el módulo de PowerShell de Skype empresarial para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="55b45-371">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="55b45-372">Puede usar el siguiente cmdlet en el módulo de PowerShell de Teams para hacerlo a escala mediante una asignación de Directiva por lotes, donde $users es una lista de los usuarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="55b45-372">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="55b45-373">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="55b45-373">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="55b45-374">Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directivas a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="55b45-374">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="55b45-375">Use el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para enviar un lote de usuarios y el paquete de directivas que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="55b45-375">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="55b45-376">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="55b45-376">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="55b45-377">Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.</span><span class="sxs-lookup"><span data-stu-id="55b45-377">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="55b45-378">Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="55b45-378">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="55b45-379">Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="55b45-379">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="55b45-380">Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario.</span><span class="sxs-lookup"><span data-stu-id="55b45-380">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="55b45-381">Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote.</span><span class="sxs-lookup"><span data-stu-id="55b45-381">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="55b45-382">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="55b45-382">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="55b45-383">Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="55b45-383">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="55b45-384">Permita que los lotes terminen de procesarse antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="55b45-384">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="55b45-385">Instalar y conectarse al módulo de PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-385">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="55b45-386">Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si todavía no lo ha hecho).</span><span class="sxs-lookup"><span data-stu-id="55b45-386">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="55b45-387">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="55b45-387">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="55b45-388">Ejecute lo siguiente para conectarse a teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="55b45-388">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="55b45-389">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="55b45-389">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="55b45-390">Asignar un paquete de directivas a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="55b45-390">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="55b45-391">En este ejemplo, usamos el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para asignar el paquete de directivas Education_PrimaryStudent a un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="55b45-391">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="55b45-392">Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="55b45-392">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="55b45-393">Obtener el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="55b45-393">Get the status of a batch assignment</span></span>

<span data-ttu-id="55b45-394">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="55b45-394">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="55b45-395">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="55b45-395">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="55b45-396">Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="55b45-396">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="55b45-397">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="55b45-397">Related topics</span></span>

[<span data-ttu-id="55b45-398">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="55b45-398">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
