---
title: Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumen: Conozca cómo administrar el servidor de charla persistente salones de chat de Skype para Business Server 2015.'
ms.openlocfilehash: fd927e3a54f1f3a8df429677f481ea224534b984
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="7a599-103">Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="7a599-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7a599-104">**Resumen:** Aprenda a administrar el servidor de charla persistente salones de chat de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7a599-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7a599-105">Con el uso correcto de las categorías, es mucho más fácil crear y administrar los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="7a599-106">Una categoría define quién puede crear o unirse a los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="7a599-107">Antes de intentar administrar salones de chat, asegúrese de leer las [categorías de chat persistentes, salones de charla y funciones de usuario de Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) y [Administrar categorías en el servidor de charla persistente en Skype para Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="7a599-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
<span data-ttu-id="7a599-108">Puede configurar y administrar salones de charla mediante la interfaz de línea de comandos de Windows PowerShell, o mediante el Skype para cliente de negocio si usted es un miembro de la sala de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-108">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="7a599-109">En este tema se describe cómo administrar salones de charla mediante la interfaz de línea de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a599-109">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="7a599-110">Si desea administrar salones de charla mediante el Skype para Business client, consulte la Ayuda del cliente.</span><span class="sxs-lookup"><span data-stu-id="7a599-110">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="7a599-111">Salas de chat puede ser de dos tipos: Normal y auditorio.</span><span class="sxs-lookup"><span data-stu-id="7a599-111">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="7a599-112">Una sala de chat Normal permite que todos los miembros a publicar y leer mensajes.</span><span class="sxs-lookup"><span data-stu-id="7a599-112">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="7a599-113">Un auditorio es un tipo de salón de chat donde pueden registrar sólo los moderadores, pero todos pueden leer.</span><span class="sxs-lookup"><span data-stu-id="7a599-113">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="7a599-114">El acceso a los salones de chat y su administración dependen de los roles de usuario, de esta manera:</span><span class="sxs-lookup"><span data-stu-id="7a599-114">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="7a599-115">Es preciso que los usuarios sean miembros de un salón de chat para poder publicar y leer mensajes.</span><span class="sxs-lookup"><span data-stu-id="7a599-115">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="7a599-116">Los moderadores pueden publicar en los salones que son auditorios.</span><span class="sxs-lookup"><span data-stu-id="7a599-116">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="7a599-117">Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado.</span><span class="sxs-lookup"><span data-stu-id="7a599-117">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="7a599-118">También pueden quitar o cambiar mensajes que se consideren inapropiados para un salón de chat específico.</span><span class="sxs-lookup"><span data-stu-id="7a599-118">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="7a599-119">Los usuarios finales, incluidos los autores de los mensajes, no pueden eliminar contenido de ningún salón de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-119">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="7a599-120">Administradores de salón de chat pueden realizar cambios en todas las propiedades de la sala de chat, incluida la deshabilitación de salas.</span><span class="sxs-lookup"><span data-stu-id="7a599-120">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="7a599-121">Los administradores no pueden, sin embargo, se eliminar una sala o cambiar la categoría de una sala.</span><span class="sxs-lookup"><span data-stu-id="7a599-121">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="7a599-122">Solo los administradores pueden eliminar un salón de chat una vez creado.</span><span class="sxs-lookup"><span data-stu-id="7a599-122">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="7a599-123">Puede configurar y administrar los salones de chat por medio de los siguientes cmdlets de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7a599-123">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="7a599-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="7a599-124">**Cmdlet**</span></span>|<span data-ttu-id="7a599-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7a599-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7a599-126">Nueva CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7a599-126">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7a599-127">Crea un salón de chat</span><span class="sxs-lookup"><span data-stu-id="7a599-127">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="7a599-128">Conjunto de CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7a599-128">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7a599-129">Configura las opciones de un salón existente; asigna usuarios y grupos de usuarios al salón</span><span class="sxs-lookup"><span data-stu-id="7a599-129">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="7a599-130">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7a599-130">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7a599-131">Recuperar información acerca de salas</span><span class="sxs-lookup"><span data-stu-id="7a599-131">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="7a599-132">Borrar CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7a599-132">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7a599-133">Borra un salón o los mensajes de un salón</span><span class="sxs-lookup"><span data-stu-id="7a599-133">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="7a599-134">Quitar CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7a599-134">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7a599-135">Quita un salón</span><span class="sxs-lookup"><span data-stu-id="7a599-135">Remove a room</span></span>  <br/> |
|<span data-ttu-id="7a599-136">Quitar CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="7a599-136">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="7a599-137">Quita mensajes de un salón</span><span class="sxs-lookup"><span data-stu-id="7a599-137">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="7a599-138">Con el cmdlet **New-CsPersistentChatRoom** puede crear salones de chat y con **Set-CsPersistentChatRoom** puede configurar un salón de chat existente, incluso agregar usuarios al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-138">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="7a599-139">Puede configurar los siguientes parámetros del salón de chat:</span><span class="sxs-lookup"><span data-stu-id="7a599-139">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="7a599-140">Disabled.</span><span class="sxs-lookup"><span data-stu-id="7a599-140">Disabled.</span></span> <span data-ttu-id="7a599-141">Le permite deshabilitar o habilitar un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-141">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="7a599-142">Invitaciones.</span><span class="sxs-lookup"><span data-stu-id="7a599-142">Invitations.</span></span> <span data-ttu-id="7a599-143">Permite habilitar o deshabilitar las invitaciones de los salones de chat, que se usan para informar a los usuarios cuando se los agregó como miembros de un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-143">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="7a599-144">La configuración predeterminada para las invitaciones es la heredada, por lo que el salón de chat adopta las opciones de configuración de la invitación configuradas en la categoría al que pertenece.</span><span class="sxs-lookup"><span data-stu-id="7a599-144">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="7a599-145">Al configurar las opciones de las invitaciones en False en el salón de chat, se cambia la configuración de la categoría.</span><span class="sxs-lookup"><span data-stu-id="7a599-145">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="7a599-146">Privacidad.</span><span class="sxs-lookup"><span data-stu-id="7a599-146">Privacy.</span></span> <span data-ttu-id="7a599-147">Permite especificar si una sala de chat es abierto, cerrado o secreto.</span><span class="sxs-lookup"><span data-stu-id="7a599-147">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="7a599-148">Salas abiertos pueden podrá buscar y tener acceso a cualquier usuario.</span><span class="sxs-lookup"><span data-stu-id="7a599-148">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="7a599-149">Salas cerradas pueden buscar por cualquier persona, pero que sean accesibles sólo para miembros.</span><span class="sxs-lookup"><span data-stu-id="7a599-149">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="7a599-150">Pueden buscar secretas salones y sólo tiene acceso a los miembros de la sala.</span><span class="sxs-lookup"><span data-stu-id="7a599-150">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="7a599-151">De forma predeterminada, cada nueva sala está configurado inicialmente como cerrado.</span><span class="sxs-lookup"><span data-stu-id="7a599-151">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="7a599-152">Type.</span><span class="sxs-lookup"><span data-stu-id="7a599-152">Type.</span></span> <span data-ttu-id="7a599-153">Permite especificar si una sala de chat es una sala Normal, que acepta los mensajes expuestos por cualquier miembro o en un salón de auditorio, que acepta mensajes expuestos sólo por un moderador.</span><span class="sxs-lookup"><span data-stu-id="7a599-153">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="7a599-154">Addin.</span><span class="sxs-lookup"><span data-stu-id="7a599-154">Addin.</span></span> <span data-ttu-id="7a599-155">Permite asociar complementos previamente configurados con un salón de chat, por lo que los miembros pueden ver el contenido URL mientras participan.</span><span class="sxs-lookup"><span data-stu-id="7a599-155">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="7a599-156">Además de los parámetros anteriores, el cmdlet **Set-CsPersistentChatRoom** le permite asignar a usuarios al salón de chat de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7a599-156">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="7a599-157">Members.</span><span class="sxs-lookup"><span data-stu-id="7a599-157">Members.</span></span> <span data-ttu-id="7a599-158">Configura la pertenencia del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-158">Configures membership for the chat room.</span></span> <span data-ttu-id="7a599-159">Puede agregar o quitar miembros individuales o varios miembros con un único cmdlet al especificar la dirección SIP de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7a599-159">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="7a599-160">Para permitir la adición en masa de usuarios, puede especificar también grupos de distribución o unidades organizativas de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7a599-160">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="7a599-161">Managers.</span><span class="sxs-lookup"><span data-stu-id="7a599-161">Managers.</span></span> <span data-ttu-id="7a599-162">Permite asignar directores al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-162">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="7a599-163">Los directores tienen los permisos para definir la pertenencia de un salón de chat junto con otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="7a599-163">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="7a599-p114">Presenters. Permite asignar moderadores a un salón de chat auditorio.</span><span class="sxs-lookup"><span data-stu-id="7a599-p114">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
 <span data-ttu-id="7a599-166">Para obtener más información acerca de la sintaxis, incluidos todos los parámetros, vea [Skype para el Shell de administración de negocio servidor 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="7a599-166">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="7a599-167">Crear un salón</span><span class="sxs-lookup"><span data-stu-id="7a599-167">Create a new room</span></span>

<span data-ttu-id="7a599-168">Puede crear un salón con el cmdlet **New-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="7a599-168">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="7a599-169">Por ejemplo, el comando siguiente crea un nuevo salón de charla denominado ITChatRoom en el grupo cs-atl-001.contoso.com. En este ejemplo, el salón de chat se agrega a la categoría de TI:</span><span class="sxs-lookup"><span data-stu-id="7a599-169">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com. In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="7a599-170">**Nota:** PersistentChatPoolFqdn no es necesario si se cumple alguna de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7a599-170">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="7a599-171">Hay sólo un grupo de servidor de charla persistente.</span><span class="sxs-lookup"><span data-stu-id="7a599-171">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="7a599-172">Proporciona un FQDN del grupo de servidores a la categoría.</span><span class="sxs-lookup"><span data-stu-id="7a599-172">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="7a599-173">Proporciona un FQDN del grupo de servidores para agregar el salón.</span><span class="sxs-lookup"><span data-stu-id="7a599-173">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="7a599-174">Configurar un salón existente</span><span class="sxs-lookup"><span data-stu-id="7a599-174">Configure an existing room</span></span>

<span data-ttu-id="7a599-175">Puede configurar un espacio existente mediante el cmdlet **Set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="7a599-175">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="7a599-176">Por ejemplo, el siguiente comando asigna user1 como miembro y moderador y Usuario2 como un administrador de la sala de auditorio testCat:</span><span class="sxs-lookup"><span data-stu-id="7a599-176">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="7a599-177">En el siguiente ejemplo, se agregan todos los usuarios de la UO de NorthAmericaUsers en Active Directory al salón de chat NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="7a599-177">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="7a599-178">En el siguiente ejemplo, se agregan todos los miembros del grupo de distribución Finanzas al mismo salón de chat:</span><span class="sxs-lookup"><span data-stu-id="7a599-178">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="7a599-179">Habilitar o deshabilitar un salón</span><span class="sxs-lookup"><span data-stu-id="7a599-179">Disable or enable a room</span></span>

<span data-ttu-id="7a599-180">Si el tema de un salón de Chat persistente ya no es relevante, hacer el salón de chat disponible a los usuarios si lo deshabilita.</span><span class="sxs-lookup"><span data-stu-id="7a599-180">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="7a599-181">Cuando se deshabilita un salón de chat, se desconectan inmediatamente todos los miembros de la sala.</span><span class="sxs-lookup"><span data-stu-id="7a599-181">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="7a599-182">Una vez deshabilitado un salón de chat, los usuarios no pueden unirlo o encontrarlo en las búsquedas de salón de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-182">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="7a599-183">Si persiste el historial del salón de charla, se conservará el contenido cuando está deshabilitado el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-183">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="7a599-184">Pero, dicho contenido no aparecerá en las búsquedas mientras el salón de chat permanezca deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="7a599-184">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="7a599-185">Si vuelve a habilitar el salón de chat, los usuarios podrán buscar mensajes publicados antes de que se deshabilitara el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="7a599-185">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="7a599-186">Para obtener información acerca de cómo configurar el historial del salón de chat, consulte [Administrar categorías en el servidor de charla persistente en Skype para Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="7a599-186">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="7a599-187">Si un salón de chat se encuentra deshabilitado, se conservan su lista de pertenencia y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="7a599-187">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="7a599-188">Como administrador, puede habilitar un salón que se ha deshabilitado y no es necesario que vuelva a establecer la configuración de forma manual.</span><span class="sxs-lookup"><span data-stu-id="7a599-188">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="7a599-189">Puede deshabilitar una sala con el cmdlet **Set-CsPersistentChatRoom** y estableciendo el parámetro deshabilitado en True:</span><span class="sxs-lookup"><span data-stu-id="7a599-189">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="7a599-190">Para habilitar un salón de chat, establezca el parámetro Disabled en False:</span><span class="sxs-lookup"><span data-stu-id="7a599-190">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False

```

## <a name="get-information-about-rooms"></a><span data-ttu-id="7a599-191">Obtener información sobre las salas</span><span class="sxs-lookup"><span data-stu-id="7a599-191">Get information about rooms</span></span>

<span data-ttu-id="7a599-192">Para obtener información sobre los salones configurados para su organización, puede usar el cmdlet **Get-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="7a599-192">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="7a599-193">El siguiente comando devuelve información sobre todos los salones de chat configurados para la organización:</span><span class="sxs-lookup"><span data-stu-id="7a599-193">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="7a599-194">Quitar todo el contenido de un salón</span><span class="sxs-lookup"><span data-stu-id="7a599-194">Remove all content from a room</span></span>

<span data-ttu-id="7a599-p120">Puede quitar el contenido de un salón al usar el cmdlet **Clear-CsPersistentChatRoom**. Por ejemplo, el siguiente comando quita todo el contenido del salón de chat persistente ITChatRoom que se agregó al él el 1 de marzo de 2015 o antes de esa fecha:</span><span class="sxs-lookup"><span data-stu-id="7a599-p120">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="7a599-197">Quitar un mensaje de un salón</span><span class="sxs-lookup"><span data-stu-id="7a599-197">Remove a message from a room</span></span>

<span data-ttu-id="7a599-p121">Puede quitar uno o más mensajes en la base de datos del chat persistente y, de forma opcional, cambiar el mensaje con un mensaje predeterminado o con un mensaje del administrador. Para ello, use el cmdlet **Remove-CsPersistentChatMessage**. Por ejemplo, el siguiente comando quita todos los mensajes del salón de chat ITChatRoom que kenmyer@contoso.com haya publicado:</span><span class="sxs-lookup"><span data-stu-id="7a599-p121">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="7a599-200">En el siguiente ejemplo se cambian todos los mensajes quitados por una advertencia de que el mensaje ya no se encuentra disponible:</span><span class="sxs-lookup"><span data-stu-id="7a599-200">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="7a599-201">Quitar un salón</span><span class="sxs-lookup"><span data-stu-id="7a599-201">Remove a room</span></span>

<span data-ttu-id="7a599-202">Puede quitar un salón con el cmdlet **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="7a599-202">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="7a599-203">Por ejemplo, el siguiente comando quita el salón de chat RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="7a599-203">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="7a599-204">Mover un salón de una categoría a otra</span><span class="sxs-lookup"><span data-stu-id="7a599-204">Move a room from one category to another</span></span>

<span data-ttu-id="7a599-p122">Si un director de un salón de chat tiene privilegios de **Creador** en otra categoría, puede mover el salón de una categoría a otra. El salón no se eliminará ni volverá a crearse, ya que es un cambio de asociación dentro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a599-p122">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="7a599-p123">El cambio de categoría de un salón de chat tiene que realizarse de forma ocasional y con precaución. Una categoría determina la pertenencia permitida para el salón de chat, por lo tanto, cuando un salón de chat se mueve a otra categoría, se purgan todas las listas de control de acceso del sistema (SACL) que ya no son compatibles con la nueva categoría. Por ejemplo, si un usuario era miembro del salón y ya no es un miembro permitido en la nueva categoría, la pertenencia del salón se modificará y se quitará al usuario del salón.</span><span class="sxs-lookup"><span data-stu-id="7a599-p123">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

