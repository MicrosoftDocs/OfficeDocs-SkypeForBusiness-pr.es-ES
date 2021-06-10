---
title: Teams y Skype interoperabilidad
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Obtenga información sobre las capacidades de interoperabilidad entre Teams usuarios de su organización y Skype (consumidor).
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093960"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="a6391-103">Teams y Skype interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="a6391-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="a6391-104">En este artículo se ofrece información general sobre las capacidades de interoperabilidad entre Microsoft Teams y Skype (consumidor).</span><span class="sxs-lookup"><span data-stu-id="a6391-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="a6391-105">Obtenga información sobre Teams usuarios y Skype pueden comunicarse a través de chats y llamadas y los controles de administración que se aplican.</span><span class="sxs-lookup"><span data-stu-id="a6391-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="a6391-106">Teams usuarios de su organización pueden chatear y llamar a Skype mediante su dirección de correo electrónico y viceversa.</span><span class="sxs-lookup"><span data-stu-id="a6391-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="a6391-107">Teams usuarios pueden buscar e iniciar una conversación de solo texto uno a uno o una llamada de audio o vídeo con un Skype usuario.</span><span class="sxs-lookup"><span data-stu-id="a6391-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="a6391-108">Skype usuarios pueden buscar e iniciar una conversación de solo texto uno a uno o una llamada de audio o vídeo con un Teams usuario.</span><span class="sxs-lookup"><span data-stu-id="a6391-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="a6391-109">Estas funcionalidades están disponibles en los clientes de escritorio, web y móvil (Android e iOS) tanto para Teams como Skype.</span><span class="sxs-lookup"><span data-stu-id="a6391-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="a6391-110">Para una experiencia óptima, le recomendamos que Skype versión 8.58 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="a6391-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="a6391-111">Las Teams y Skype de interoperabilidad que se deba en este artículo no están disponibles en implementaciones de GCC, GCC High o DOD, ni en entornos de nube privados.</span><span class="sxs-lookup"><span data-stu-id="a6391-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="a6391-112">Experiencia de chat y llamadas</span><span class="sxs-lookup"><span data-stu-id="a6391-112">Chat and calling experience</span></span>

<span data-ttu-id="a6391-113">Esta es una descripción general de la experiencia de chat y llamadas.</span><span class="sxs-lookup"><span data-stu-id="a6391-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="a6391-114">Teams usuario inicia un chat o llamada con un Skype usuario</span><span class="sxs-lookup"><span data-stu-id="a6391-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="a6391-115">Teams usuarios pueden buscar un usuario Skype escribiendo su dirección de correo electrónico en un nuevo chat o en la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a6391-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="a6391-116">El Teams puede seleccionar el Skype en los resultados de búsqueda para iniciar un chat o una llamada con ellos.</span><span class="sxs-lookup"><span data-stu-id="a6391-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="a6391-117">Un Skype usuario puede elegir no aparecer en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a6391-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="a6391-118">En este caso, no se mostrarán en los resultados de búsqueda en Teams y Teams usuarios no podrán encontrarlos.</span><span class="sxs-lookup"><span data-stu-id="a6391-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="a6391-119">Skype usuario inicia un chat o una llamada con un Teams usuario</span><span class="sxs-lookup"><span data-stu-id="a6391-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="a6391-120">Skype usuarios pueden buscar e iniciar un chat con un usuario Teams usando su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a6391-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="a6391-121">Al Teams de correo electrónico se le notifica que tiene un mensaje nuevo de un usuario de Skype y primero tiene que aceptar el mensaje antes de poder responderlo.</span><span class="sxs-lookup"><span data-stu-id="a6391-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="a6391-122">Si el Teams selecciona **Aceptar,** se acepta la conversación y ambos usuarios pueden chatear y llamarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="a6391-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="a6391-123">Si el Teams selecciona **Bloquear,** la conversación está bloqueada y se bloquean los mensajes y las llamadas posteriores de Skype usuario.</span><span class="sxs-lookup"><span data-stu-id="a6391-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="a6391-124">Si el Teams selecciona Ver **mensajes,** el mensaje se muestra en Teams, lo que ayuda al usuario a decidir si desea aceptar o bloquear la conversación.</span><span class="sxs-lookup"><span data-stu-id="a6391-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="a6391-125">Si ha actualizado de Skype Empresarial Teams y los usuarios están en el modo solo Teams, los chats y las llamadas de los usuarios de Skype Teams a Teams.</span><span class="sxs-lookup"><span data-stu-id="a6391-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="a6391-126">Si los usuarios están en el modo Islas, los chats y las llamadas de Skype a Teams usuarios se entregan a Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="a6391-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="a6391-127">Teams usuario bloquea o desbloquea un Skype usuario</span><span class="sxs-lookup"><span data-stu-id="a6391-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="a6391-128">Después de que Teams usuario acepte o bloquee la solicitud de conversación inicial de un usuario de Skype, puede elegir bloquear o desbloquear a esa persona en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="a6391-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="a6391-129">Pueden hacerlo en la conversación o en su configuración de privacidad en Teams.</span><span class="sxs-lookup"><span data-stu-id="a6391-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="a6391-130">Skype usuarios no sabrán que se han bloqueado.</span><span class="sxs-lookup"><span data-stu-id="a6391-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="a6391-131">Los Skype, junto con otras personas y números de teléfono de red telefónica conmutada (RTC) bloqueados por un usuario de Teams, aparecen en la lista de contactos bloqueados del usuario en Teams.</span><span class="sxs-lookup"><span data-stu-id="a6391-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="a6391-132">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="a6391-132">Limitations</span></span>

- <span data-ttu-id="a6391-133">Las conversaciones son de solo texto.</span><span class="sxs-lookup"><span data-stu-id="a6391-133">Conversations are text-only.</span></span> <span data-ttu-id="a6391-134">Esto significa que no hay ningún formato enriquecido, @mentions, emojis u otras características de chat que estén disponibles en una experiencia de chat de Teams [nativa.](native-chat-for-external-users.md)</span><span class="sxs-lookup"><span data-stu-id="a6391-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="a6391-135">Las conversaciones son solo uno a uno.</span><span class="sxs-lookup"><span data-stu-id="a6391-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="a6391-136">Los chats grupales no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="a6391-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="a6391-137">Teams usuarios y Skype usuarios no pueden ver la presencia de los demás.</span><span class="sxs-lookup"><span data-stu-id="a6391-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="a6391-138">No se admite Skype usuarios con su Skype o número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="a6391-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="a6391-139">Skype usuarios no pueden llamar Teams usuarios que configuren el reenvío de llamadas al número de otro usuario, al número de un delegado o a un número de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="a6391-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="a6391-140">Solo se admite el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="a6391-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="a6391-141">La escalación de interoperabilidad, las llamadas grupales y las reuniones no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="a6391-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="a6391-142">No se admite la capacidad para que un delegado llame a Skype usuario en nombre de un usuario Teams usuario.</span><span class="sxs-lookup"><span data-stu-id="a6391-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="a6391-143">No se admite el uso compartido de pantalla con el chat.</span><span class="sxs-lookup"><span data-stu-id="a6391-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="a6391-144">Establecer si Teams usuarios pueden comunicarse con Skype usuarios</span><span class="sxs-lookup"><span data-stu-id="a6391-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="a6391-145">Como administrador, use el centro de administración de Microsoft Teams o PowerShell para establecer la configuración de acceso externo para controlar si Teams usuarios de su organización pueden comunicarse con Skype usuarios.</span><span class="sxs-lookup"><span data-stu-id="a6391-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="a6391-146">De forma predeterminada, esta funcionalidad está activada para los nuevos inquilinos.</span><span class="sxs-lookup"><span data-stu-id="a6391-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="a6391-147">Sin embargo, existe un requisito previo para que el administrador de TI configure el siguiente registro SRV dns si aún no está disponible para su dominio, por ejemplo _sipfederationtls.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a6391-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="a6391-148">**Servicio:** sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a6391-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="a6391-149">**Protocolo:** TCP</span><span class="sxs-lookup"><span data-stu-id="a6391-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="a6391-150">**Prioridad:** 100</span><span class="sxs-lookup"><span data-stu-id="a6391-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="a6391-151">**Peso:** 1</span><span class="sxs-lookup"><span data-stu-id="a6391-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="a6391-152">**Puerto:** 5061</span><span class="sxs-lookup"><span data-stu-id="a6391-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="a6391-153">**Destino:** sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a6391-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="a6391-154">Si actualizó de Skype Empresarial a Teams, la configuración de comunicaciones externas que configuró en el centro de administración de Skype Empresarial se migrará a Teams.</span><span class="sxs-lookup"><span data-stu-id="a6391-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a6391-155">En el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a6391-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="a6391-156">En el Microsoft Teams de administración, vaya a Configuración de toda la organización Acceso externo y, a continuación, active Los usuarios pueden comunicarse con  >   **Skype usuarios.**</span><span class="sxs-lookup"><span data-stu-id="a6391-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="a6391-157">Para obtener instrucciones paso a paso sobre cómo configurar esta y otras opciones de acceso externo, vea Administrar el acceso [externo en Teams](./manage-external-access.md#allow-or-block-domains).</span><span class="sxs-lookup"><span data-stu-id="a6391-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](./manage-external-access.md#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a6391-158">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6391-158">Using PowerShell</span></span>

<span data-ttu-id="a6391-159">Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6391-159">Do the following:</span></span> 
1. <span data-ttu-id="a6391-160">Use el cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) junto con el parámetro para controlar si Teams usuarios pueden comunicarse ```EnablePublicCloudAccess``` con Skype usuarios.</span><span class="sxs-lookup"><span data-stu-id="a6391-160">Use the [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="a6391-161">Al establecer el parámetro ```true``` para que Teams usuarios puedan comunicarse con Skype usuarios.</span><span class="sxs-lookup"><span data-stu-id="a6391-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="a6391-162">Puede usar el parámetro para habilitar o deshabilitar ```EnablePublicCloudAudioVideoAccess``` las llamadas de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="a6391-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="a6391-163">Use el cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) junto con el parámetro establecido en para que Teams usuarios puedan comunicarse con ```Provider``` ```"WindowsLive"``` Skype usuarios.</span><span class="sxs-lookup"><span data-stu-id="a6391-163">Use the [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a6391-164">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a6391-164">Related topics</span></span>

- [<span data-ttu-id="a6391-165">Administrar el acceso externo en Teams</span><span class="sxs-lookup"><span data-stu-id="a6391-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="a6391-166">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="a6391-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)