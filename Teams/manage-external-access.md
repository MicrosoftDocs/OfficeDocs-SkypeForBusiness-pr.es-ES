---
title: Administrar el acceso externo (federación) en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: karvell
search.appverid: MET150
description: El Administrador de TI puede configurar el acceso externo para otros dominios (federación) permitir que los usuarios de esos dominios a participar en los equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56e4171421cc52ec1ca79895aba3c0f259d20201
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2019
ms.locfileid: "29708800"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="5d59d-103">Administrar el acceso externo (federación) en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d59d-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="5d59d-104">Con acceso externo de Microsoft Teams, los usuarios de otros dominios pueden participar en las charlas y las llamadas.</span><span class="sxs-lookup"><span data-stu-id="5d59d-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="5d59d-105">También puede permitir que a los usuarios externos que todavía se están usando Skype para la empresa para participar.</span><span class="sxs-lookup"><span data-stu-id="5d59d-105">You can also allow external users who are still using Skype for Business to participate.</span></span> 

<span data-ttu-id="5d59d-106">Acceso externo (federación) y el acceso de invitado son diferentes:</span><span class="sxs-lookup"><span data-stu-id="5d59d-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="5d59d-107">Acceso de invitado concede permiso de acceso a un individuo.</span><span class="sxs-lookup"><span data-stu-id="5d59d-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="5d59d-108">Acceso externo concede permiso de acceso a todo el dominio.</span><span class="sxs-lookup"><span data-stu-id="5d59d-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="5d59d-109">Acceso como invitado, una vez concedido por el propietario de un equipo, permite que a un invitado para [tener acceso a recursos](guest-experience.md), como discusiones de canal y archivos, para un equipo específico y chat con otros usuarios en el equipo que hayan sido invitados a.</span><span class="sxs-lookup"><span data-stu-id="5d59d-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="5d59d-110">Con acceso externo (chat federado), los participantes externos chat no tienen acceso a la organización invitar a los equipos o recursos de equipo.</span><span class="sxs-lookup"><span data-stu-id="5d59d-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="5d59d-111">Solo pueden participar en conversaciones federadas proporcionó en.</span><span class="sxs-lookup"><span data-stu-id="5d59d-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="5d59d-112">Los administradores de inquilinos pueden elegir entre las opciones de dos comunicación dependiendo de qué nivel de colaboración es deseable con la parte externa.</span><span class="sxs-lookup"><span data-stu-id="5d59d-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="5d59d-113">Pueden elegir los administradores enfoques o ambos, dependiendo de sus necesidades de la organización, pero se recomienda habilitar el acceso de invitado para una experiencia de los equipos más completo y en colaboración.</span><span class="sxs-lookup"><span data-stu-id="5d59d-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="5d59d-114">Vea la siguiente tabla para obtener una comparación de externo y acceso a las características de invitado.</span><span class="sxs-lookup"><span data-stu-id="5d59d-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="5d59d-115">Característica</span><span class="sxs-lookup"><span data-stu-id="5d59d-115">Feature</span></span> | <span data-ttu-id="5d59d-116">Usuarios de acceso externo</span><span class="sxs-lookup"><span data-stu-id="5d59d-116">External access users</span></span> | <span data-ttu-id="5d59d-117">Usuarios de acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="5d59d-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="5d59d-118">Usuario puede hablar con una persona de otra empresa</span><span class="sxs-lookup"><span data-stu-id="5d59d-118">User can chat with someone in another company</span></span> | <span data-ttu-id="5d59d-119">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-119">Yes</span></span> |<span data-ttu-id="5d59d-120">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-120">Yes</span></span> |
| <span data-ttu-id="5d59d-121">Usuario puede llamar a alguien de otra compañía</span><span class="sxs-lookup"><span data-stu-id="5d59d-121">User can call someone in another company</span></span> | <span data-ttu-id="5d59d-122">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-122">Yes</span></span> | <span data-ttu-id="5d59d-123">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-123">Yes</span></span> |
| <span data-ttu-id="5d59d-124">Usuario puede ver si una persona de otra empresa está disponible para la llamada o chat</span><span class="sxs-lookup"><span data-stu-id="5d59d-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="5d59d-125">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-125">Yes</span></span> | <span data-ttu-id="5d59d-126">Sí<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d59d-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="5d59d-127">Puede buscar usuario para los usuarios en los inquilinos externos</span><span class="sxs-lookup"><span data-stu-id="5d59d-127">User can search for users across external tenants</span></span> | <span data-ttu-id="5d59d-128">Sí<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5d59d-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="5d59d-129">No</span><span class="sxs-lookup"><span data-stu-id="5d59d-129">No</span></span> |
| <span data-ttu-id="5d59d-130">Usuario puede compartir archivos</span><span class="sxs-lookup"><span data-stu-id="5d59d-130">User can share files</span></span> | <span data-ttu-id="5d59d-131">No</span><span class="sxs-lookup"><span data-stu-id="5d59d-131">No</span></span> | <span data-ttu-id="5d59d-132">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-132">Yes</span></span> |
| <span data-ttu-id="5d59d-133">Usuario puede tener acceso a los recursos de los equipos</span><span class="sxs-lookup"><span data-stu-id="5d59d-133">User can access Teams resources</span></span> | <span data-ttu-id="5d59d-134">No</span><span class="sxs-lookup"><span data-stu-id="5d59d-134">No</span></span> | <span data-ttu-id="5d59d-135">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-135">Yes</span></span> |
| <span data-ttu-id="5d59d-136">Usuario puede agregarse a una conversación en grupo</span><span class="sxs-lookup"><span data-stu-id="5d59d-136">User can be added to a group chat</span></span> | <span data-ttu-id="5d59d-137">No</span><span class="sxs-lookup"><span data-stu-id="5d59d-137">No</span></span> | <span data-ttu-id="5d59d-138">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-138">Yes</span></span> |
| <span data-ttu-id="5d59d-139">Se puede agregar el usuario a una reunión</span><span class="sxs-lookup"><span data-stu-id="5d59d-139">User can be added to a meeting</span></span> | <span data-ttu-id="5d59d-140">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-140">Yes</span></span> | <span data-ttu-id="5d59d-141">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-141">Yes</span></span> |
| <span data-ttu-id="5d59d-142">Se pueden agregar usuarios adicionales a una conversación con un usuario externo</span><span class="sxs-lookup"><span data-stu-id="5d59d-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="5d59d-143">No hay<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5d59d-143">No<sup>3</sup></span></span> | <span data-ttu-id="5d59d-144">N/D</span><span class="sxs-lookup"><span data-stu-id="5d59d-144">N/A</span></span> |
| <span data-ttu-id="5d59d-145">Usuario se identifica como una parte externa</span><span class="sxs-lookup"><span data-stu-id="5d59d-145">User is identified as an external party</span></span> | <span data-ttu-id="5d59d-146">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-146">Yes</span></span> | <span data-ttu-id="5d59d-147">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-147">Yes</span></span> |
| <span data-ttu-id="5d59d-148">Se muestra la presencia</span><span class="sxs-lookup"><span data-stu-id="5d59d-148">Presence is displayed</span></span> | <span data-ttu-id="5d59d-149">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-149">Yes</span></span> | <span data-ttu-id="5d59d-150">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-150">Yes</span></span> |
| <span data-ttu-id="5d59d-151">Fuera de la oficina se muestra el mensaje</span><span class="sxs-lookup"><span data-stu-id="5d59d-151">Out of office message is shown</span></span> | <span data-ttu-id="5d59d-152">No</span><span class="sxs-lookup"><span data-stu-id="5d59d-152">No</span></span> | <span data-ttu-id="5d59d-153">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-153">Yes</span></span> |
| <span data-ttu-id="5d59d-154">Se puede bloquear un usuario individual</span><span class="sxs-lookup"><span data-stu-id="5d59d-154">Individual user can be blocked</span></span> | <span data-ttu-id="5d59d-155">No</span><span class="sxs-lookup"><span data-stu-id="5d59d-155">No</span></span> | <span data-ttu-id="5d59d-156">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-156">Yes</span></span> |
| <span data-ttu-id="5d59d-157">se admiten @mentions</span><span class="sxs-lookup"><span data-stu-id="5d59d-157">@mentions are supported</span></span> | <span data-ttu-id="5d59d-158">No</span><span class="sxs-lookup"><span data-stu-id="5d59d-158">No</span></span> | <span data-ttu-id="5d59d-159">Sí</span><span class="sxs-lookup"><span data-stu-id="5d59d-159">Yes</span></span> |
||||

<span data-ttu-id="5d59d-160"><sup>1</sup> siempre que el usuario se ha agregado como invitado y ha iniciado sesión como invitado en el inquilino de invitado.</span><span class="sxs-lookup"><span data-stu-id="5d59d-160"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="5d59d-161"><sup>2</sup> sólo por correo electrónico o la dirección de protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="5d59d-161"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="5d59d-162"><sup>3</sup> externo chat (federada) es sólo 1:1.</span><span class="sxs-lookup"><span data-stu-id="5d59d-162"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

## <a name="turn-on-or-turn-off-external-access"></a><span data-ttu-id="5d59d-163">Activar o desactivar el acceso externo</span><span class="sxs-lookup"><span data-stu-id="5d59d-163">Turn on or turn off external access</span></span>

<span data-ttu-id="5d59d-164">Puede usar el & Teams Microsoft Skype para el centro de administración de negocio para administrar el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="5d59d-164">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="5d59d-165">En la & Teams Microsoft Skype para el centro de administración de negocio, seleccione **configuración de toda la organización** > **acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="5d59d-165">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Captura de pantalla de acceso externo de la configuración de toda la organización](media/manage-external-access-1.png)<span data-ttu-id="5d59d-167">.</span><span class="sxs-lookup"><span data-stu-id="5d59d-167"></span></span>

2. <span data-ttu-id="5d59d-168">Permite activar o desactivar el modificador de **acceso externo** a **activado** o **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="5d59d-168">Toggle the **External access** switch to **On** or **Off**.</span></span>

     ![Captura de pantalla del modificador de acceso externo activado](media/manage-external-access-2.png)<span data-ttu-id="5d59d-170">.</span><span class="sxs-lookup"><span data-stu-id="5d59d-170"></span></span>

3. <span data-ttu-id="5d59d-171">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5d59d-171">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="5d59d-172">Agregar o bloquear un dominio</span><span class="sxs-lookup"><span data-stu-id="5d59d-172">Add or block a domain</span></span>

<span data-ttu-id="5d59d-173">Siga estos pasos para agregar un dominio o desactivar el acceso externo para un dominio.</span><span class="sxs-lookup"><span data-stu-id="5d59d-173">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="5d59d-174">En la & Teams Microsoft Skype para el centro de administración de negocio, seleccione **configuración de toda la organización** > **acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="5d59d-174">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="5d59d-175">Seleccione **Agregar un dominio**.</span><span class="sxs-lookup"><span data-stu-id="5d59d-175">Select **Add a domain**.</span></span> 
 
    ![Captura de pantalla de externos página de acceso con agregar un vínculo de dominio](media/manage-external-access-3.png)<span data-ttu-id="5d59d-177">.</span><span class="sxs-lookup"><span data-stu-id="5d59d-177"></span></span>

   <span data-ttu-id="5d59d-178">Aparece el panel **Agregar un dominio** .</span><span class="sxs-lookup"><span data-stu-id="5d59d-178">The **Add a domain** pane appears.</span></span>

    ![Captura de pantalla de agregar un panel de dominio](media/manage-external-access-4.png)<span data-ttu-id="5d59d-180">.</span><span class="sxs-lookup"><span data-stu-id="5d59d-180"></span></span>


3. <span data-ttu-id="5d59d-181">En **Agregar un dominio**, escriba el nombre del dominio; Por ejemplo, escriba Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5d59d-181">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="5d59d-182">Seleccione **Permitir** o **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="5d59d-182">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="5d59d-183">Puede cambiar esta configuración en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="5d59d-183">You can change this setting at any time.</span></span>

2. <span data-ttu-id="5d59d-184">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="5d59d-184">Select **Done**.</span></span>

<span data-ttu-id="5d59d-185">Después de agregar un dominio, podrá ver el nombre de dominio y el estado que se agrega a la lista de dominios en la página de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="5d59d-185">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="5d59d-186">Más información</span><span class="sxs-lookup"><span data-stu-id="5d59d-186">More information</span></span>

<span data-ttu-id="5d59d-187">Para obtener información sobre el acceso de invitado en Microsoft Teams, vea [administrar el acceso de invitado en los equipos de Microsoft](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="5d59d-187">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>