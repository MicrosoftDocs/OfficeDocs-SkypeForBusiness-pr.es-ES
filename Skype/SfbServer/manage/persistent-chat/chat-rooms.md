---
title: Administrar los salón de chat en el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumen: obtenga información sobre cómo administrar los salas de chat del servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815110"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="55935-103">Administrar los salón de chat en el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="55935-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="55935-104">**Resumen:** Obtenga información sobre cómo administrar los salón de chat del servidor de chat persistente en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="55935-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="55935-105">Crear y administrar salas de chat es mucho más fácil con el uso correcto de categorías.</span><span class="sxs-lookup"><span data-stu-id="55935-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="55935-106">Una categoría define quién puede crear o unirse a los salón de chat.</span><span class="sxs-lookup"><span data-stu-id="55935-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="55935-107">Antes de intentar administrar los salón de chat, asegúrese de leer las categorías de chat persistente, los salón de chat y los roles de usuario en [Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) y administrar las categorías en el servidor de chat persistente en [Skype Empresarial Server 2015.](categories.md)</span><span class="sxs-lookup"><span data-stu-id="55935-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="55935-108">El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="55935-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="55935-109">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="55935-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="55935-110">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="55935-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="55935-111">Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="55935-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="55935-112">Puede configurar y administrar los salón de chat mediante la interfaz de línea de comandos de Windows PowerShell o mediante el cliente de Skype Empresarial si es miembro del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="55935-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="55935-113">En este tema se describe cómo administrar los salón de chat mediante la interfaz Windows PowerShell línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="55935-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="55935-114">Si desea administrar los salón de chat con el cliente de Skype Empresarial, consulte la ayuda del cliente.</span><span class="sxs-lookup"><span data-stu-id="55935-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="55935-115">Los salón de chat pueden ser de dos tipos: Normal y Auditorio.</span><span class="sxs-lookup"><span data-stu-id="55935-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="55935-116">Un salón de chat Normal permite a todos los miembros publicar y leer mensajes.</span><span class="sxs-lookup"><span data-stu-id="55935-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="55935-117">Un auditorio es un tipo de salón de chat donde solo los presentadores pueden publicar, pero todos pueden leer.</span><span class="sxs-lookup"><span data-stu-id="55935-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="55935-118">Quién puede acceder a los salas de chat y administrarlos depende de los roles de usuario de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="55935-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="55935-119">Los usuarios deben ser miembros de un salón de chat para poder publicar y leer mensajes.</span><span class="sxs-lookup"><span data-stu-id="55935-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="55935-120">Los presentadores pueden publicar en salas de auditorio.</span><span class="sxs-lookup"><span data-stu-id="55935-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="55935-121">Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado.</span><span class="sxs-lookup"><span data-stu-id="55935-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="55935-122">Los administradores también pueden quitar o reemplazar mensajes que se consideren inapropiados para un salón de chat en particular.</span><span class="sxs-lookup"><span data-stu-id="55935-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="55935-123">Los usuarios finales, incluidos los autores de mensajes, no pueden eliminar contenido de ningún salón de chat.</span><span class="sxs-lookup"><span data-stu-id="55935-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="55935-124">Los administradores de los salón de chat pueden realizar cambios en todas las propiedades del salón de chat, incluida la deshabilitación de salas.</span><span class="sxs-lookup"><span data-stu-id="55935-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="55935-125">Sin embargo, los administradores no pueden eliminar un salón ni cambiar la categoría de un salón.</span><span class="sxs-lookup"><span data-stu-id="55935-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="55935-126">Solo los administradores pueden eliminar un salón de chat después de crearlo.</span><span class="sxs-lookup"><span data-stu-id="55935-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="55935-127">Puede configurar y administrar los salas de chat mediante los siguientes cmdlets Windows PowerShell web:</span><span class="sxs-lookup"><span data-stu-id="55935-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="55935-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="55935-128">**Cmdlet**</span></span>|<span data-ttu-id="55935-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="55935-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55935-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="55935-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="55935-131">Crear un nuevo salón de chat</span><span class="sxs-lookup"><span data-stu-id="55935-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="55935-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="55935-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="55935-133">Configurar las opciones de una sala existente; asignar usuarios y grupos de usuarios a la sala</span><span class="sxs-lookup"><span data-stu-id="55935-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="55935-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="55935-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="55935-135">Recuperar información sobre salas</span><span class="sxs-lookup"><span data-stu-id="55935-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="55935-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="55935-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="55935-137">Borrar una sala o mensajes de una sala</span><span class="sxs-lookup"><span data-stu-id="55935-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="55935-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="55935-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="55935-139">Quitar un salón</span><span class="sxs-lookup"><span data-stu-id="55935-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="55935-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="55935-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="55935-141">Quitar mensajes de una sala</span><span class="sxs-lookup"><span data-stu-id="55935-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="55935-142">Use el cmdlet **New-CsPersistentChatRoom** para crear salas de chat y el cmdlet **Set-CsPersistentChatRoom** para configurar un salón de chat existente, incluida la adición de usuarios al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="55935-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="55935-143">Puede configurar los siguientes parámetros para los salas de chat:</span><span class="sxs-lookup"><span data-stu-id="55935-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="55935-144">Deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="55935-144">Disabled.</span></span> <span data-ttu-id="55935-145">Permite deshabilitar o habilitar un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="55935-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="55935-146">Invitaciones.</span><span class="sxs-lookup"><span data-stu-id="55935-146">Invitations.</span></span> <span data-ttu-id="55935-147">Permite habilitar o deshabilitar las invitaciones a salas de chat, que se usan para notificar a los usuarios cuando se han agregado como miembros del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="55935-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="55935-148">La configuración predeterminada para las invitaciones heredadas, que hizo que el salón de chat adoptara la configuración de invitación configurada en la categoría a la que pertenece.</span><span class="sxs-lookup"><span data-stu-id="55935-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="55935-149">La configuración de las invitaciones en false en el nivel de salón de chat permite invalidar la configuración de categoría.</span><span class="sxs-lookup"><span data-stu-id="55935-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="55935-150">Privacidad.</span><span class="sxs-lookup"><span data-stu-id="55935-150">Privacy.</span></span> <span data-ttu-id="55935-151">Permite especificar si un salón de chat es Abierto, Cerrado o Secreto.</span><span class="sxs-lookup"><span data-stu-id="55935-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="55935-152">Cualquiera puede buscar en las salas abiertas y acceder a ellas.</span><span class="sxs-lookup"><span data-stu-id="55935-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="55935-153">Cualquiera puede buscar salas cerradas, pero solo los miembros pueden acceder a ellas.</span><span class="sxs-lookup"><span data-stu-id="55935-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="55935-154">Solo los miembros de la sala pueden buscar y tener acceso a los salas secretas.</span><span class="sxs-lookup"><span data-stu-id="55935-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="55935-155">De forma predeterminada, cada nueva sala se configura inicialmente como Cerrada.</span><span class="sxs-lookup"><span data-stu-id="55935-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="55935-156">Tipo.</span><span class="sxs-lookup"><span data-stu-id="55935-156">Type.</span></span> <span data-ttu-id="55935-157">Permite especificar si un salón de chat es un salón Normal, que acepta mensajes publicados por cualquier miembro, o un salón de auditorio, que acepta mensajes publicados solo por un moderador.</span><span class="sxs-lookup"><span data-stu-id="55935-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="55935-158">Addin.</span><span class="sxs-lookup"><span data-stu-id="55935-158">Addin.</span></span> <span data-ttu-id="55935-159">Permite asociar un complemento configurado previamente con un salón de chat, lo que permite que los miembros puedan ver el contenido de la dirección URL mientras participan.</span><span class="sxs-lookup"><span data-stu-id="55935-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="55935-160">Además de los parámetros anteriores, el cmdlet **Set-CsPersistentChatRoom** permite asignar usuarios al salón de chat de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="55935-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="55935-161">Miembros.</span><span class="sxs-lookup"><span data-stu-id="55935-161">Members.</span></span> <span data-ttu-id="55935-162">Configura la pertenencia al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="55935-162">Configures membership for the chat room.</span></span> <span data-ttu-id="55935-163">Puede agregar o quitar miembros individuales o múltiples mediante un solo cmdlet especificando la dirección SIP de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="55935-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="55935-164">Para permitir que los usuarios se puedan agregar de forma masiva, también se pueden especificar unidades organizativas o grupos de distribución de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55935-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="55935-165">Administradores.</span><span class="sxs-lookup"><span data-stu-id="55935-165">Managers.</span></span> <span data-ttu-id="55935-166">Permite asignar administradores al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="55935-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="55935-167">Los administradores tienen los permisos para definir la pertenencia a un salón de chat junto con otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="55935-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="55935-168">Presentadores.</span><span class="sxs-lookup"><span data-stu-id="55935-168">Presenters.</span></span> <span data-ttu-id="55935-169">Permite asignar presentadores a un salón de chat Auditorio.</span><span class="sxs-lookup"><span data-stu-id="55935-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="55935-170">Para obtener más información sobre la sintaxis, incluidos todos los parámetros, consulte Shell de administración de [Skype Empresarial Server 2015.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="55935-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="55935-171">Crear un nuevo salón</span><span class="sxs-lookup"><span data-stu-id="55935-171">Create a new room</span></span>

<span data-ttu-id="55935-172">Puede crear un nuevo salón con el cmdlet **New-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="55935-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="55935-173">Por ejemplo, el siguiente comando crea un nuevo salón de chat denominado ITChatRoom en el grupo atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="55935-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="55935-174">En este ejemplo, el salón de chat se agrega a la categoría de IT:</span><span class="sxs-lookup"><span data-stu-id="55935-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="55935-175">**Nota:** PersistentChatPoolFqdn no es necesario si se cumple una de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="55935-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="55935-176">Solo hay un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="55935-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="55935-177">Proporciona un poolFqdn a la categoría.</span><span class="sxs-lookup"><span data-stu-id="55935-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="55935-178">Proporciona un poolFqdn para agregar un salón.</span><span class="sxs-lookup"><span data-stu-id="55935-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="55935-179">Configurar una sala existente</span><span class="sxs-lookup"><span data-stu-id="55935-179">Configure an existing room</span></span>

<span data-ttu-id="55935-180">Puede configurar un salón existente mediante el cmdlet **Set-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="55935-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="55935-181">Por ejemplo, el siguiente comando asigna usuario1 como miembro y moderador, y usuario2 como administrador, de la sala de auditorio testCat:</span><span class="sxs-lookup"><span data-stu-id="55935-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="55935-182">En el siguiente ejemplo se agregan todos los usuarios de la unidad organizativa NorthAmericaUsers de Active Directory al salón de chat NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="55935-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="55935-183">En el siguiente ejemplo se agregan todos los miembros del grupo de distribución Finance al mismo salón de chat:</span><span class="sxs-lookup"><span data-stu-id="55935-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="55935-184">Deshabilitar o habilitar un salón</span><span class="sxs-lookup"><span data-stu-id="55935-184">Disable or enable a room</span></span>

<span data-ttu-id="55935-185">Si el tema de un salón de chat persistente ya no es relevante, puede hacer que el salón de chat no esté disponible para los usuarios si lo deshabilita.</span><span class="sxs-lookup"><span data-stu-id="55935-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="55935-186">Cuando se deshabilita una salón de chat, todos los miembros se desconectan inmediatamente del salón.</span><span class="sxs-lookup"><span data-stu-id="55935-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="55935-187">Después de deshabilitar un salón de chat, los usuarios no pueden unirse a él o encontrarlo en las búsquedas de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="55935-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="55935-188">Si el historial del salón de chat persiste, el contenido se conserva cuando el salón de chat está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="55935-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="55935-189">No obstante, ese contenido no aparecerá en las búsquedas durante el tiempo que el salón de chat permanezca deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="55935-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="55935-190">Si más tarde habilita el salón de chat, los usuarios pueden buscar mensajes que se publicaron antes de que lo deshabilitara.</span><span class="sxs-lookup"><span data-stu-id="55935-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="55935-191">Para obtener información sobre cómo configurar el historial de salas de chat, consulte Administrar categorías en el servidor de [chat persistente en Skype Empresarial Server 2015.](categories.md)</span><span class="sxs-lookup"><span data-stu-id="55935-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="55935-192">Al deshabilitar un salón de chat, su lista de miembros y otros ajustes se conservan.</span><span class="sxs-lookup"><span data-stu-id="55935-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="55935-193">Como administrador, puede habilitar una sala que se ha deshabilitado y no es necesario volver a crear manualmente la configuración.</span><span class="sxs-lookup"><span data-stu-id="55935-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="55935-194">Puede deshabilitar una sala mediante el cmdlet **Set-CsPersistentChatRoom** y estableciendo el parámetro Disabled en True:</span><span class="sxs-lookup"><span data-stu-id="55935-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="55935-195">Para habilitar un salón de chat, establezca el parámetro Disabled en False:</span><span class="sxs-lookup"><span data-stu-id="55935-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="55935-196">Obtener información sobre salas</span><span class="sxs-lookup"><span data-stu-id="55935-196">Get information about rooms</span></span>

<span data-ttu-id="55935-197">Para obtener información sobre las salas configuradas para su uso en la organización, puede usar el cmdlet **Get-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="55935-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="55935-198">El siguiente comando devuelve información sobre todos los salón de chat configurados para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="55935-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="55935-199">Quitar todo el contenido de un salón</span><span class="sxs-lookup"><span data-stu-id="55935-199">Remove all content from a room</span></span>

<span data-ttu-id="55935-200">Puede quitar contenido de un salón mediante el cmdlet **Clear-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="55935-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="55935-201">Por ejemplo, el siguiente comando quita todo el contenido del salón de chat persistente ITChatRoom que se agregó a la sala el 1 de marzo de 2015 o antes:</span><span class="sxs-lookup"><span data-stu-id="55935-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="55935-202">Quitar un mensaje de un salón</span><span class="sxs-lookup"><span data-stu-id="55935-202">Remove a message from a room</span></span>

<span data-ttu-id="55935-203">Puede quitar uno o más mensajes de la base de datos de chat persistente y, opcionalmente, reemplazar el mensaje por un mensaje predeterminado o por un mensaje proporcionado por el administrador, mediante el cmdlet **Remove-CsPersistentChatMessage.**</span><span class="sxs-lookup"><span data-stu-id="55935-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="55935-204">Por ejemplo, el siguiente comando quita todos los mensajes del salón de chat ITChatRoom que publicó el usuario kenmyer@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="55935-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="55935-205">En el siguiente ejemplo se reemplazan los mensajes eliminados con la nota de que el mensaje ya no está disponible:</span><span class="sxs-lookup"><span data-stu-id="55935-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="55935-206">Quitar un salón</span><span class="sxs-lookup"><span data-stu-id="55935-206">Remove a room</span></span>

<span data-ttu-id="55935-207">Puede quitar un salón mediante el cmdlet **Remove-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="55935-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="55935-208">Por ejemplo, el siguiente comando quita el salón de chat RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="55935-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="55935-209">Mover un salón de una categoría a otra</span><span class="sxs-lookup"><span data-stu-id="55935-209">Move a room from one category to another</span></span>

<span data-ttu-id="55935-210">Si un administrador  del salón de chat tiene privilegios de creador en otra categoría, puede mover el salón de una categoría a otra.</span><span class="sxs-lookup"><span data-stu-id="55935-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="55935-211">El salón no se eliminará y volverá a crearse.</span><span class="sxs-lookup"><span data-stu-id="55935-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="55935-212">Es un cambio de asociación dentro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="55935-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="55935-213">El cambio de una categoría de salón de chat debe realizarse rara vez y con precaución.</span><span class="sxs-lookup"><span data-stu-id="55935-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="55935-214">Una categoría determina la pertenencia permitida para el salón de chat, por lo tanto, cuando un salón de chat se mueve a otra categoría, se eliminan todas las listas de control de acceso del sistema (SACL) que ya no son compatibles con la nueva categoría.</span><span class="sxs-lookup"><span data-stu-id="55935-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="55935-215">Por ejemplo, si un usuario era miembro de la sala y ya no es miembro permitido en la nueva categoría, se modificará la pertenencia a la sala y el usuario se quitará de la sala.</span><span class="sxs-lookup"><span data-stu-id="55935-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

