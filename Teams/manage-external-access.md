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
description: El Administrador de TI puede configurar el acceso externo para otros dominios (federación) permitir que los usuarios de esos dominios a participar en los equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97b322969d3975b6f9ca2b2079d46fe95ef45e52
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459927"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="b598b-103">Administrar el acceso externo (federación) en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b598b-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="b598b-104">Con acceso externo de Microsoft Teams, los usuarios de otros dominios pueden participar en las charlas y las llamadas.</span><span class="sxs-lookup"><span data-stu-id="b598b-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="b598b-105">También puede permitir que a los usuarios externos que todavía se están usando Skype para la empresa para participar.</span><span class="sxs-lookup"><span data-stu-id="b598b-105">You can also allow external users who are still using Skype for Business to participate.</span></span> 

<span data-ttu-id="b598b-106">Acceso externo (federación) y el acceso de invitado son diferentes:</span><span class="sxs-lookup"><span data-stu-id="b598b-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="b598b-107">Acceso de invitado concede permiso de acceso a un individuo.</span><span class="sxs-lookup"><span data-stu-id="b598b-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="b598b-108">Acceso externo concede permiso de acceso a todo el dominio.</span><span class="sxs-lookup"><span data-stu-id="b598b-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="b598b-109">Acceso como invitado, una vez concedido por el propietario de un equipo, permite que a un invitado para [tener acceso a recursos](guest-experience.md), como discusiones de canal y archivos, para un equipo específico y chat con otros usuarios en el equipo que hayan sido invitados a.</span><span class="sxs-lookup"><span data-stu-id="b598b-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="b598b-110">Con acceso externo (chat federado), los participantes externos chat no tienen acceso a la organización invitar a los equipos o recursos de equipo.</span><span class="sxs-lookup"><span data-stu-id="b598b-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="b598b-111">Solo pueden participar en conversaciones federadas proporcionó en.</span><span class="sxs-lookup"><span data-stu-id="b598b-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="b598b-112">Los administradores de inquilinos pueden elegir entre las opciones de dos comunicación dependiendo de qué nivel de colaboración es deseable con la parte externa.</span><span class="sxs-lookup"><span data-stu-id="b598b-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="b598b-113">Pueden elegir los administradores enfoques o ambos, dependiendo de sus necesidades de la organización, pero se recomienda habilitar el acceso de invitado para una experiencia de los equipos más completo y en colaboración.</span><span class="sxs-lookup"><span data-stu-id="b598b-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="b598b-114">Vea la siguiente tabla para obtener una comparación de externo y acceso a las características de invitado.</span><span class="sxs-lookup"><span data-stu-id="b598b-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="b598b-115">Característica</span><span class="sxs-lookup"><span data-stu-id="b598b-115">Feature</span></span> | <span data-ttu-id="b598b-116">Usuarios de acceso externo</span><span class="sxs-lookup"><span data-stu-id="b598b-116">External access users</span></span> | <span data-ttu-id="b598b-117">Usuarios de acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="b598b-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="b598b-118">Usuario puede hablar con una persona de otra empresa</span><span class="sxs-lookup"><span data-stu-id="b598b-118">User can chat with someone in another company</span></span> | <span data-ttu-id="b598b-119">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-119">Yes</span></span> |<span data-ttu-id="b598b-120">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-120">Yes</span></span> |
| <span data-ttu-id="b598b-121">Usuario puede llamar a alguien de otra compañía</span><span class="sxs-lookup"><span data-stu-id="b598b-121">User can call someone in another company</span></span> | <span data-ttu-id="b598b-122">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-122">Yes</span></span> | <span data-ttu-id="b598b-123">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-123">Yes</span></span> |
| <span data-ttu-id="b598b-124">Usuario puede ver si una persona de otra empresa está disponible para la llamada o chat</span><span class="sxs-lookup"><span data-stu-id="b598b-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="b598b-125">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-125">Yes</span></span> | <span data-ttu-id="b598b-126">Sí<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b598b-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="b598b-127">Puede buscar usuario para los usuarios en los inquilinos externos</span><span class="sxs-lookup"><span data-stu-id="b598b-127">User can search for users across external tenants</span></span> | <span data-ttu-id="b598b-128">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b598b-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="b598b-129">No</span><span class="sxs-lookup"><span data-stu-id="b598b-129">No</span></span> |
| <span data-ttu-id="b598b-130">Usuario puede compartir archivos</span><span class="sxs-lookup"><span data-stu-id="b598b-130">User can share files</span></span> | <span data-ttu-id="b598b-131">No</span><span class="sxs-lookup"><span data-stu-id="b598b-131">No</span></span> | <span data-ttu-id="b598b-132">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-132">Yes</span></span> |
| <span data-ttu-id="b598b-133">Usuario puede tener acceso a los recursos de los equipos</span><span class="sxs-lookup"><span data-stu-id="b598b-133">User can access Teams resources</span></span> | <span data-ttu-id="b598b-134">No</span><span class="sxs-lookup"><span data-stu-id="b598b-134">No</span></span> | <span data-ttu-id="b598b-135">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-135">Yes</span></span> |
| <span data-ttu-id="b598b-136">Usuario puede agregarse a una conversación en grupo</span><span class="sxs-lookup"><span data-stu-id="b598b-136">User can be added to a group chat</span></span> | <span data-ttu-id="b598b-137">No</span><span class="sxs-lookup"><span data-stu-id="b598b-137">No</span></span> | <span data-ttu-id="b598b-138">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-138">Yes</span></span> |
| <span data-ttu-id="b598b-139">Se puede agregar el usuario a una reunión</span><span class="sxs-lookup"><span data-stu-id="b598b-139">User can be added to a meeting</span></span> | <span data-ttu-id="b598b-140">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-140">Yes</span></span> | <span data-ttu-id="b598b-141">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-141">Yes</span></span> |
| <span data-ttu-id="b598b-142">Se pueden agregar usuarios adicionales a una conversación con un usuario externo</span><span class="sxs-lookup"><span data-stu-id="b598b-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="b598b-143">No hay<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b598b-143">No<sup>3</sup></span></span> | <span data-ttu-id="b598b-144">N/D</span><span class="sxs-lookup"><span data-stu-id="b598b-144">N/A</span></span> |
| <span data-ttu-id="b598b-145">Usuario se identifica como una parte externa</span><span class="sxs-lookup"><span data-stu-id="b598b-145">User is identified as an external party</span></span> | <span data-ttu-id="b598b-146">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-146">Yes</span></span> | <span data-ttu-id="b598b-147">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-147">Yes</span></span> |
| <span data-ttu-id="b598b-148">Se muestra la presencia</span><span class="sxs-lookup"><span data-stu-id="b598b-148">Presence is displayed</span></span> | <span data-ttu-id="b598b-149">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-149">Yes</span></span> | <span data-ttu-id="b598b-150">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-150">Yes</span></span> |
| <span data-ttu-id="b598b-151">Fuera de la oficina se muestra el mensaje</span><span class="sxs-lookup"><span data-stu-id="b598b-151">Out of office message is shown</span></span> | <span data-ttu-id="b598b-152">No</span><span class="sxs-lookup"><span data-stu-id="b598b-152">No</span></span> | <span data-ttu-id="b598b-153">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-153">Yes</span></span> |
| <span data-ttu-id="b598b-154">Se puede bloquear un usuario individual</span><span class="sxs-lookup"><span data-stu-id="b598b-154">Individual user can be blocked</span></span> | <span data-ttu-id="b598b-155">No</span><span class="sxs-lookup"><span data-stu-id="b598b-155">No</span></span> | <span data-ttu-id="b598b-156">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-156">Yes</span></span> |
| <span data-ttu-id="b598b-157">se admiten @mentions</span><span class="sxs-lookup"><span data-stu-id="b598b-157">@mentions are supported</span></span> | <span data-ttu-id="b598b-158">No</span><span class="sxs-lookup"><span data-stu-id="b598b-158">No</span></span> | <span data-ttu-id="b598b-159">Sí</span><span class="sxs-lookup"><span data-stu-id="b598b-159">Yes</span></span> |
||||

<span data-ttu-id="b598b-160"><sup>1</sup> siempre que el usuario se ha agregado como invitado y ha iniciado sesión como invitado en el inquilino de invitado.</span><span class="sxs-lookup"><span data-stu-id="b598b-160"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="b598b-161"><sup>2</sup> sólo por correo electrónico o la dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="b598b-161"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="b598b-162"><sup>3</sup> externo chat (federada) es sólo 1:1.</span><span class="sxs-lookup"><span data-stu-id="b598b-162"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

## <a name="turn-on-or-turn-off-external-access"></a><span data-ttu-id="b598b-163">Activar o desactivar el acceso externo</span><span class="sxs-lookup"><span data-stu-id="b598b-163">Turn on or turn off external access</span></span>

<span data-ttu-id="b598b-164">Puede usar el & Teams Microsoft Skype para el centro de administración de negocio para administrar el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="b598b-164">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="b598b-165">En la & Teams Microsoft Skype para el centro de administración de negocio, seleccione **configuración de toda la organización** > **acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="b598b-165">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Captura de pantalla de acceso externo de la configuración de toda la organización](media/manage-external-access-1.png)<span data-ttu-id="b598b-167">.</span><span class="sxs-lookup"><span data-stu-id="b598b-167"></span></span>

2. <span data-ttu-id="b598b-168">Permite activar o desactivar el modificador de **acceso externo** a **activado** o **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="b598b-168">Toggle the **External access** switch to **On** or **Off**.</span></span>

     ![Captura de pantalla del modificador de acceso externo activado](media/manage-external-access-2.png)<span data-ttu-id="b598b-170">.</span><span class="sxs-lookup"><span data-stu-id="b598b-170"></span></span>

3. <span data-ttu-id="b598b-171">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b598b-171">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="b598b-172">Agregar o bloquear un dominio</span><span class="sxs-lookup"><span data-stu-id="b598b-172">Add or block a domain</span></span>

<span data-ttu-id="b598b-173">Siga estos pasos para agregar un dominio o desactivar el acceso externo para un dominio.</span><span class="sxs-lookup"><span data-stu-id="b598b-173">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="b598b-174">En la & Teams Microsoft Skype para el centro de administración de negocio, seleccione **configuración de toda la organización** > **acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="b598b-174">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="b598b-175">Seleccione **Agregar un dominio**.</span><span class="sxs-lookup"><span data-stu-id="b598b-175">Select **Add a domain**.</span></span> 
 
    ![Captura de pantalla de externos página de acceso con agregar un vínculo de dominio](media/manage-external-access-3.png)<span data-ttu-id="b598b-177">.</span><span class="sxs-lookup"><span data-stu-id="b598b-177"></span></span>

   <span data-ttu-id="b598b-178">Aparece el panel **Agregar un dominio** .</span><span class="sxs-lookup"><span data-stu-id="b598b-178">The **Add a domain** pane appears.</span></span>

    ![Captura de pantalla de agregar un panel de dominio](media/manage-external-access-4.png)<span data-ttu-id="b598b-180">.</span><span class="sxs-lookup"><span data-stu-id="b598b-180"></span></span>


3. <span data-ttu-id="b598b-181">En **Agregar un dominio**, escriba el nombre del dominio; Por ejemplo, escriba Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b598b-181">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="b598b-182">Seleccione **Permitir** o **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="b598b-182">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="b598b-183">Puede cambiar esta configuración en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="b598b-183">You can change this setting at any time.</span></span>

2. <span data-ttu-id="b598b-184">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b598b-184">Select **Done**.</span></span>

<span data-ttu-id="b598b-185">Después de agregar un dominio, podrá ver el nombre de dominio y el estado que se agrega a la lista de dominios en la página de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="b598b-185">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="b598b-186">Más información</span><span class="sxs-lookup"><span data-stu-id="b598b-186">More information</span></span>

<span data-ttu-id="b598b-187">Para obtener información sobre el acceso de invitado en Microsoft Teams, vea [administrar el acceso de invitado en los equipos de Microsoft](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="b598b-187">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>