---
title: Administrar directivas de reunión
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Descubra cómo administrar la configuración de una directiva de reunión en Teams con el fin de controlar las características disponibles para sus participantes en reuniones programadas por usuarios.
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598763"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="d7c1d-103">Administrar directivas de reunión en Teams</span><span class="sxs-lookup"><span data-stu-id="d7c1d-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="d7c1d-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="d7c1d-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="d7c1d-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="d7c1d-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="d7c1d-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="d7c1d-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="d7c1d-107">Las Directivas de reunión se usan para controlar las características disponibles para sus participantes en reuniones programadas por usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="d7c1d-108">Puede usar la directiva global (predeterminada para toda la organización) o crear directivas personalizadas y asignarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="d7c1d-109">Puede administrar las directivas de reuniones en el Centro de administración de Microsoft Teams o mediante [PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d7c1d-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d7c1d-110">Para obtener información sobre el uso de los roles para administrar los permisos de los moderadores y los asistentes de reuniones, consulte [Roles en una reunión de Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span><span class="sxs-lookup"><span data-stu-id="d7c1d-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="d7c1d-111">Puede implementar directivas en las formas que se indican a continuación. Esto afectará a la experiencia de los usuarios antes de que se inicie la reunión, durante una reunión o después de una reunión.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="d7c1d-112">Tipo de implementación</span><span class="sxs-lookup"><span data-stu-id="d7c1d-112">Implementation type</span></span>  |<span data-ttu-id="d7c1d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7c1d-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d7c1d-114">Por organizador</span><span class="sxs-lookup"><span data-stu-id="d7c1d-114">Per-organizer</span></span>    |<span data-ttu-id="d7c1d-115">Al implementar una directiva por organizador, todos los participantes de la reunión heredan la directiva del organizador.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="d7c1d-116">Ejemplo: **Admitir automáticamente personas** es una directiva por organizador y controla si los usuarios pueden unirse a la reunión directamente o esperar en la sala de espera para reuniones programadas por el usuario al que se ha asignado la directiva.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="d7c1d-117">Por usuario</span><span class="sxs-lookup"><span data-stu-id="d7c1d-117">Per-user</span></span>    |<span data-ttu-id="d7c1d-118">Cuando implementa una directiva por usuario, solo la directiva por usuario se aplica para restringir determinadas características para el organizador o los participantes de la reunión.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="d7c1d-119">Por ejemplo, **Permitir Reunirse ahora en los canales** es una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="d7c1d-120">Por organizador y por usuario</span><span class="sxs-lookup"><span data-stu-id="d7c1d-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="d7c1d-121">Cuando implementa una combinación de una directiva por organizador y por usuario, se restringen determinadas características a los participantes de la reunión en función de las directivas de los usuarios y del organizador.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="d7c1d-122">Por ejemplo, **Permitir la grabación en la nube** es una directiva por organizador y por usuario.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="d7c1d-123">Active esta opción para permitir que el organizador de la reunión y los participantes inicien y detengan una grabación.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="d7c1d-124">Puede editar la configuración en la directiva global o crear y asignar una o más directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="d7c1d-125">Los usuarios obtendrán la directiva global, a menos que usted cree y asigne una directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="d7c1d-126">El botón Detalles de la reunión estará disponible si un usuario tiene habilitadas las licencias de conferencia de audio o si el usuario admite las conferencias de audio. Si no, los detalles de la reunión no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="d7c1d-127">Crear una directiva de reuniones personalizada</span><span class="sxs-lookup"><span data-stu-id="d7c1d-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="d7c1d-128">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Reuniones** > **Directivas de reunión**.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="d7c1d-129">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-129">Click **Add**.</span></span>
3. <span data-ttu-id="d7c1d-130">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="d7c1d-131">El nombre no puede contener caracteres especiales ni tener más de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="d7c1d-132">Seleccione la configuración que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="d7c1d-133">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-133">Click **Save**.</span></span>

<span data-ttu-id="d7c1d-134">Por ejemplo, supongamos que tiene un grupo de usuarios y quiere limitar el ancho de banda que necesitaría la reunión.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="d7c1d-135">Cree una nueva directiva personalizada denominada "ancho de banda limitado" y deshabilite las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d7c1d-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="d7c1d-136">En **Audio y vídeo**:</span><span class="sxs-lookup"><span data-stu-id="d7c1d-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="d7c1d-137">Desactive Permitir la grabación en la nube.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="d7c1d-138">Desactive Permitir vídeo IP.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="d7c1d-139">En **Uso compartido de contenido**:</span><span class="sxs-lookup"><span data-stu-id="d7c1d-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="d7c1d-140">Desactive el modo de uso compartido de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="d7c1d-141">Desactive Permitir pizarra.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="d7c1d-142">Desactive Permitir notas compartidas.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="d7c1d-143">Luego asigne la directiva a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="d7c1d-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="d7c1d-144">Editar una directiva de reunión</span><span class="sxs-lookup"><span data-stu-id="d7c1d-144">Edit a meeting policy</span></span>

<span data-ttu-id="d7c1d-145">Puede editar la directiva global y las directivas personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="d7c1d-146">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Reuniones** > **Directivas de reunión**.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="d7c1d-147">Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="d7c1d-148">A partir de aquí, realice los cambios que desee.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="d7c1d-149">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d7c1d-150">Un usuario solo puede tener asignada una directiva de reuniones cada vez.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="d7c1d-151">Asignar una directiva de reunión a los usuarios</span><span class="sxs-lookup"><span data-stu-id="d7c1d-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="d7c1d-152">No puede eliminar una directiva si tiene usuarios asignados.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="d7c1d-153">Primero, debe asignar una directiva diferente a todos los usuarios afectados. Luego, podrá eliminar la directiva original.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="d7c1d-154">Configuración de la directiva de reunión</span><span class="sxs-lookup"><span data-stu-id="d7c1d-154">Meeting policy settings</span></span>

<span data-ttu-id="d7c1d-155">Al seleccionar una directiva existente en la página **Directivas de reunión** o seleccionar **Agregar** para agregar una nueva directiva, puede establecer la configuración para lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d7c1d-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="d7c1d-156">General</span><span class="sxs-lookup"><span data-stu-id="d7c1d-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="d7c1d-157">Audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="d7c1d-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="d7c1d-158">Uso compartido de contenido</span><span class="sxs-lookup"><span data-stu-id="d7c1d-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="d7c1d-159">Participantes e invitados</span><span class="sxs-lookup"><span data-stu-id="d7c1d-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="d7c1d-160">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d7c1d-160">Related topics</span></span>

- [<span data-ttu-id="d7c1d-161">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="d7c1d-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="d7c1d-162">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="d7c1d-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="d7c1d-163">Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess</span><span class="sxs-lookup"><span data-stu-id="d7c1d-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)