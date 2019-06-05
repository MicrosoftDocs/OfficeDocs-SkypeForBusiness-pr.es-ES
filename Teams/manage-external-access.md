---
title: Administrar el acceso externo (federación) en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: Su administrador de ti puede configurar el acceso externo para otros dominios (Federación) para permitir que los usuarios de esos dominios participen en Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702723"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="b063a-103">Administrar el acceso externo (federación) en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b063a-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="b063a-104">Con el acceso externo de Microsoft Teams, los usuarios de otros dominios pueden participar en tus chats y llamadas.</span><span class="sxs-lookup"><span data-stu-id="b063a-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="b063a-105">También puede permitir que los usuarios externos que siguen usando Skype empresarial online o Skype empresarial local participen en él.</span><span class="sxs-lookup"><span data-stu-id="b063a-105">You can also allow external users who are still using Skype for Business Online or Skype for Business on-prem to participate.</span></span> 

<span data-ttu-id="b063a-106">El acceso externo (Federación) y el acceso de invitados son diferentes:</span><span class="sxs-lookup"><span data-stu-id="b063a-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="b063a-107">Acceso de invitado concede permiso de acceso a una persona.</span><span class="sxs-lookup"><span data-stu-id="b063a-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="b063a-108">Acceso externo concede permiso de acceso a un dominio completo.</span><span class="sxs-lookup"><span data-stu-id="b063a-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="b063a-109">El acceso de invitados, una vez otorgado por el propietario de un equipo, permite que un invitado [tenga acceso a recursos](guest-experience.md), como archivos y debates de canales, para un equipo específico y conversa con otros usuarios del equipo al que han sido invitados.</span><span class="sxs-lookup"><span data-stu-id="b063a-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="b063a-110">Con el acceso externo (chat federado), los participantes del chat externo no tienen acceso a los equipos de la organización o a los recursos del equipo.</span><span class="sxs-lookup"><span data-stu-id="b063a-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="b063a-111">Solo pueden participar en un chat federado.</span><span class="sxs-lookup"><span data-stu-id="b063a-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="b063a-112">Los administradores de inquilinos pueden elegir entre las dos opciones de comunicación dependiendo del nivel de colaboración que sea deseable con la parte externa.</span><span class="sxs-lookup"><span data-stu-id="b063a-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="b063a-113">Los administradores pueden elegir entre dos enfoques o ambos, según las necesidades de la organización, pero recomendamos habilitar el acceso de invitados para disfrutar de una experiencia de Teams más completa.</span><span class="sxs-lookup"><span data-stu-id="b063a-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="b063a-114">Consulte la tabla siguiente para obtener una comparación de las características de acceso externo e invitado.</span><span class="sxs-lookup"><span data-stu-id="b063a-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="b063a-115">Característica</span><span class="sxs-lookup"><span data-stu-id="b063a-115">Feature</span></span> | <span data-ttu-id="b063a-116">Usuarios de acceso externo</span><span class="sxs-lookup"><span data-stu-id="b063a-116">External access users</span></span> | <span data-ttu-id="b063a-117">Usuarios de acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="b063a-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="b063a-118">El usuario puede chatear con alguien de otra empresa</span><span class="sxs-lookup"><span data-stu-id="b063a-118">User can chat with someone in another company</span></span> | <span data-ttu-id="b063a-119">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-119">Yes</span></span> |<span data-ttu-id="b063a-120">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-120">Yes</span></span> |
| <span data-ttu-id="b063a-121">El usuario puede llamar a alguien de otra empresa</span><span class="sxs-lookup"><span data-stu-id="b063a-121">User can call someone in another company</span></span> | <span data-ttu-id="b063a-122">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-122">Yes</span></span> | <span data-ttu-id="b063a-123">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-123">Yes</span></span> |
| <span data-ttu-id="b063a-124">El usuario puede ver si alguien de otra empresa está disponible para realizar llamadas o chats</span><span class="sxs-lookup"><span data-stu-id="b063a-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="b063a-125">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-125">Yes</span></span> | <span data-ttu-id="b063a-126">Sí<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b063a-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="b063a-127">El usuario puede buscar usuarios en espacios empresariales externos</span><span class="sxs-lookup"><span data-stu-id="b063a-127">User can search for users across external tenants</span></span> | <span data-ttu-id="b063a-128">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b063a-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="b063a-129">No</span><span class="sxs-lookup"><span data-stu-id="b063a-129">No</span></span> |
| <span data-ttu-id="b063a-130">El usuario puede compartir archivos</span><span class="sxs-lookup"><span data-stu-id="b063a-130">User can share files</span></span> | <span data-ttu-id="b063a-131">No</span><span class="sxs-lookup"><span data-stu-id="b063a-131">No</span></span> | <span data-ttu-id="b063a-132">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-132">Yes</span></span> |
| <span data-ttu-id="b063a-133">El usuario puede acceder a los recursos de Teams</span><span class="sxs-lookup"><span data-stu-id="b063a-133">User can access Teams resources</span></span> | <span data-ttu-id="b063a-134">No</span><span class="sxs-lookup"><span data-stu-id="b063a-134">No</span></span> | <span data-ttu-id="b063a-135">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-135">Yes</span></span> |
| <span data-ttu-id="b063a-136">Se puede Agregar un usuario a un chat grupal</span><span class="sxs-lookup"><span data-stu-id="b063a-136">User can be added to a group chat</span></span> | <span data-ttu-id="b063a-137">No</span><span class="sxs-lookup"><span data-stu-id="b063a-137">No</span></span> | <span data-ttu-id="b063a-138">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-138">Yes</span></span> |
| <span data-ttu-id="b063a-139">Se puede Agregar un usuario a una reunión</span><span class="sxs-lookup"><span data-stu-id="b063a-139">User can be added to a meeting</span></span> | <span data-ttu-id="b063a-140">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-140">Yes</span></span> | <span data-ttu-id="b063a-141">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-141">Yes</span></span> |
| <span data-ttu-id="b063a-142">Se pueden agregar usuarios adicionales a un chat con un usuario externo</span><span class="sxs-lookup"><span data-stu-id="b063a-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="b063a-143">No<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b063a-143">No<sup>3</sup></span></span> | <span data-ttu-id="b063a-144">N/D</span><span class="sxs-lookup"><span data-stu-id="b063a-144">N/A</span></span> |
| <span data-ttu-id="b063a-145">El usuario se identifica como una fiesta externa</span><span class="sxs-lookup"><span data-stu-id="b063a-145">User is identified as an external party</span></span> | <span data-ttu-id="b063a-146">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-146">Yes</span></span> | <span data-ttu-id="b063a-147">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-147">Yes</span></span> |
| <span data-ttu-id="b063a-148">Se muestra la presencia</span><span class="sxs-lookup"><span data-stu-id="b063a-148">Presence is displayed</span></span> | <span data-ttu-id="b063a-149">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-149">Yes</span></span> | <span data-ttu-id="b063a-150">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-150">Yes</span></span> |
| <span data-ttu-id="b063a-151">Se muestra un mensaje de fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="b063a-151">Out of office message is shown</span></span> | <span data-ttu-id="b063a-152">No</span><span class="sxs-lookup"><span data-stu-id="b063a-152">No</span></span> | <span data-ttu-id="b063a-153">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-153">Yes</span></span> |
| <span data-ttu-id="b063a-154">Usuario individual puede bloquearse</span><span class="sxs-lookup"><span data-stu-id="b063a-154">Individual user can be blocked</span></span> | <span data-ttu-id="b063a-155">No</span><span class="sxs-lookup"><span data-stu-id="b063a-155">No</span></span> | <span data-ttu-id="b063a-156">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-156">Yes</span></span> |
| <span data-ttu-id="b063a-157">@mentions son compatibles</span><span class="sxs-lookup"><span data-stu-id="b063a-157">@mentions are supported</span></span> | <span data-ttu-id="b063a-158">No</span><span class="sxs-lookup"><span data-stu-id="b063a-158">No</span></span> | <span data-ttu-id="b063a-159">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-159">Yes</span></span> |
| <span data-ttu-id="b063a-160">Hacer llamadas privadas</span><span class="sxs-lookup"><span data-stu-id="b063a-160">Make Private Calls</span></span> | <span data-ttu-id="b063a-161">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-161">Yes</span></span> | <span data-ttu-id="b063a-162">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-162">Yes</span></span> |
| <span data-ttu-id="b063a-163">Permitir video IP</span><span class="sxs-lookup"><span data-stu-id="b063a-163">Allow IP Video</span></span> | <span data-ttu-id="b063a-164">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-164">Yes</span></span> | <span data-ttu-id="b063a-165">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-165">Yes</span></span> |
| <span data-ttu-id="b063a-166">Modo de uso compartido de pantalla</span><span class="sxs-lookup"><span data-stu-id="b063a-166">Screen Sharing Mode</span></span> | <span data-ttu-id="b063a-167">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-167">Yes</span></span> | <span data-ttu-id="b063a-168">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-168">Yes</span></span> |
| <span data-ttu-id="b063a-169">Permitir reunirse ahora</span><span class="sxs-lookup"><span data-stu-id="b063a-169">Allow Meet Now</span></span> | <span data-ttu-id="b063a-170">No</span><span class="sxs-lookup"><span data-stu-id="b063a-170">No</span></span> | <span data-ttu-id="b063a-171">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-171">Yes</span></span> |
| <span data-ttu-id="b063a-172">Editar mensajes enviados</span><span class="sxs-lookup"><span data-stu-id="b063a-172">Edit Sent Messages</span></span> | <span data-ttu-id="b063a-173">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-173">Yes</span></span> | <span data-ttu-id="b063a-174">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-174">Yes</span></span> |
| <span data-ttu-id="b063a-175">Puede eliminar mensajes enviados</span><span class="sxs-lookup"><span data-stu-id="b063a-175">Can Delete Sent Messages</span></span> | <span data-ttu-id="b063a-176">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-176">Yes</span></span> | <span data-ttu-id="b063a-177">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-177">Yes</span></span> |
| <span data-ttu-id="b063a-178">Usar Giphy en la conversación</span><span class="sxs-lookup"><span data-stu-id="b063a-178">Use Giphy In Conversation</span></span> | <span data-ttu-id="b063a-179">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-179">Yes</span></span> | <span data-ttu-id="b063a-180">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-180">Yes</span></span> |
| <span data-ttu-id="b063a-181">Usar memes en una conversación</span><span class="sxs-lookup"><span data-stu-id="b063a-181">Use Memes In Conversation</span></span> | <span data-ttu-id="b063a-182">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-182">Yes</span></span> | <span data-ttu-id="b063a-183">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-183">Yes</span></span> |
| <span data-ttu-id="b063a-184">Usar adhesivos en la conversación</span><span class="sxs-lookup"><span data-stu-id="b063a-184">Use Stickers In Conversation</span></span> | <span data-ttu-id="b063a-185">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-185">Yes</span></span> | <span data-ttu-id="b063a-186">Sí</span><span class="sxs-lookup"><span data-stu-id="b063a-186">Yes</span></span> |
||||

<span data-ttu-id="b063a-187"><sup>1</sup> siempre que el usuario se haya agregado como invitado y haya iniciado sesión como invitado para el inquilino invitado.</span><span class="sxs-lookup"><span data-stu-id="b063a-187"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="b063a-188"><sup>2</sup> solo por correo electrónico o dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="b063a-188"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="b063a-189"><sup>3</sup> el chat externo (federado) solo es 1:1.</span><span class="sxs-lookup"><span data-stu-id="b063a-189"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

> [!NOTE]
> <span data-ttu-id="b063a-190">Para obtener más información sobre las características de invitado y la experiencia de invitado, vea [activar o desactivar el acceso de invitado a Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) y [Cómo es la experiencia de invitado](https://docs.microsoft.com/microsoftteams/guest-experience).</span><span class="sxs-lookup"><span data-stu-id="b063a-190">For more information on guest features and the guest experience, see [Turn on or off guest access to Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) and [What the guest experience is like](https://docs.microsoft.com/microsoftteams/guest-experience).</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="b063a-191">Activar o desactivar el acceso externo (los usuarios pueden comunicarse con usuarios de Skype empresarial y Teams)</span><span class="sxs-lookup"><span data-stu-id="b063a-191">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="b063a-192">Puede usar Microsoft Teams & el centro de administración de Skype empresarial para administrar el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="b063a-192">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="b063a-193">En el centro de administración de Microsoft Teams & de Skype empresarial, seleccione **configuración** > **externa**de la organización.</span><span class="sxs-lookup"><span data-stu-id="b063a-193">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Captura de pantalla de la configuración de acceso externo a toda la organización](media/manage-external-access-1.png)<span data-ttu-id="b063a-195">.</span><span class="sxs-lookup"><span data-stu-id="b063a-195"></span></span>

2. <span data-ttu-id="b063a-196">Activar o desactivar los **usuarios pueden comunicarse con los usuarios de Skype empresarial y Teams** cambien a **activado** o desactivado. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b063a-196">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![Captura de pantalla del interruptor de acceso externo activado](media/manage-external-access-2.png)<span data-ttu-id="b063a-198">.</span><span class="sxs-lookup"><span data-stu-id="b063a-198"></span></span>

3. <span data-ttu-id="b063a-199">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b063a-199">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="b063a-200">Agregar o bloquear un dominio</span><span class="sxs-lookup"><span data-stu-id="b063a-200">Add or block a domain</span></span>

<span data-ttu-id="b063a-201">Siga estos pasos para agregar un dominio o deshabilitar el acceso externo para un dominio.</span><span class="sxs-lookup"><span data-stu-id="b063a-201">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="b063a-202">En el centro de administración de Microsoft Teams & de Skype empresarial, seleccione **configuración** > **externa**de la organización.</span><span class="sxs-lookup"><span data-stu-id="b063a-202">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="b063a-203">Seleccione **Agregar un dominio**.</span><span class="sxs-lookup"><span data-stu-id="b063a-203">Select **Add a domain**.</span></span> 
 
    ![Captura de pantalla de la página acceso externo con el vínculo Agregar un dominio](media/manage-external-access-3.png)<span data-ttu-id="b063a-205">.</span><span class="sxs-lookup"><span data-stu-id="b063a-205"></span></span>

   <span data-ttu-id="b063a-206">Aparece el panel **Agregar un dominio** .</span><span class="sxs-lookup"><span data-stu-id="b063a-206">The **Add a domain** pane appears.</span></span>

    ![Captura de pantalla del panel agregar un dominio](media/manage-external-access-4.png)<span data-ttu-id="b063a-208">.</span><span class="sxs-lookup"><span data-stu-id="b063a-208"></span></span>


3. <span data-ttu-id="b063a-209">En **Agregar un dominio**, escriba el nombre del dominio. por ejemplo, escriba Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b063a-209">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="b063a-210">Seleccione **Permitido** o **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="b063a-210">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="b063a-211">Puedes cambiar esta configuración en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="b063a-211">You can change this setting at any time.</span></span>

2. <span data-ttu-id="b063a-212">Seleccione **listo**.</span><span class="sxs-lookup"><span data-stu-id="b063a-212">Select **Done**.</span></span>

<span data-ttu-id="b063a-213">Después de agregar un dominio, verá el nombre de dominio y el estado añadidos a la lista de dominios en la página acceso externo.</span><span class="sxs-lookup"><span data-stu-id="b063a-213">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="b063a-214">Más información</span><span class="sxs-lookup"><span data-stu-id="b063a-214">More information</span></span>

<span data-ttu-id="b063a-215">Para obtener información sobre el acceso de invitados en Microsoft Teams, consulte [administrar el acceso de invitado en Microsoft Teams](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="b063a-215">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>
