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
description: 'Resumen: Obtenga información sobre cómo administrar Persistent Chat Server salones de chat de Skype para Business Server 2015.'
ms.openlocfilehash: 25d13b8b44e16d476191fdae337eb72d73e77dbc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973778"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="6ed2b-103">Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="6ed2b-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6ed2b-104">**Resumen:** Obtenga información sobre cómo administrar Persistent Chat Server salones de chat de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6ed2b-105">Con el uso correcto de las categorías, es mucho más fácil crear y administrar los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="6ed2b-106">Una categoría define quién puede crear o unirse a los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="6ed2b-107">Antes de intentar administrar salones de chat, asegúrese de leer [las categorías de chat persistente, salones de chat y funciones de usuario de Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) y [Administrar categorías en el servidor de Chat persistente en Skype para Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="6ed2b-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ed2b-108">Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6ed2b-109">La misma funcionalidad está disponible en los equipos.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="6ed2b-110">Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="6ed2b-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="6ed2b-111">Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="6ed2b-112">Puede configurar y administrar salones de chat mediante el uso de la interfaz de línea de comandos de Windows PowerShell, o mediante el Skype para clientes empresariales si usted es un miembro del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="6ed2b-113">En este tema se describe cómo administrar salones de chat mediante el uso de la interfaz de línea de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="6ed2b-114">Si desea administrar los salones de chat mediante el Skype para clientes empresariales, vea la Ayuda del cliente.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="6ed2b-115">Salones de chat puede ser uno de los dos tipos: Normal y tipo auditorio.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="6ed2b-116">Un salón de chat Normal permite que todos los miembros publicar y leer los mensajes.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="6ed2b-117">Un tipo de auditorio es un tipo de salón de chat donde sólo los moderadores pueden publicar, pero todos los usuarios pueden leer.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="6ed2b-118">El acceso a los salones de chat y su administración dependen de los roles de usuario, de esta manera:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="6ed2b-119">Es preciso que los usuarios sean miembros de un salón de chat para poder publicar y leer mensajes.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="6ed2b-120">Los moderadores pueden publicar en los salones que son auditorios.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="6ed2b-121">Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="6ed2b-122">También pueden quitar o cambiar mensajes que se consideren inapropiados para un salón de chat específico.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="6ed2b-123">Los usuarios finales, incluidos los autores de los mensajes, no pueden eliminar contenido de ningún salón de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="6ed2b-124">Administradores de salones de chat pueden realizar cambios a todas las propiedades de salón de chat, incluida la deshabilitación de salas.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="6ed2b-125">Los administradores no se pueden, sin embargo, se eliminar una sala o cambiar la categoría de un salón de.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="6ed2b-126">Solo los administradores pueden eliminar un salón de chat una vez creado.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="6ed2b-127">Puede configurar y administrar los salones de chat por medio de los siguientes cmdlets de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="6ed2b-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="6ed2b-128">**Cmdlet**</span></span>|<span data-ttu-id="6ed2b-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6ed2b-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6ed2b-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6ed2b-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6ed2b-131">Crea un salón de chat</span><span class="sxs-lookup"><span data-stu-id="6ed2b-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="6ed2b-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6ed2b-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6ed2b-133">Configura las opciones de un salón existente; asigna usuarios y grupos de usuarios al salón</span><span class="sxs-lookup"><span data-stu-id="6ed2b-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="6ed2b-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6ed2b-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6ed2b-135">Recuperar información acerca de los salones</span><span class="sxs-lookup"><span data-stu-id="6ed2b-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="6ed2b-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6ed2b-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6ed2b-137">Borra un salón o los mensajes de un salón</span><span class="sxs-lookup"><span data-stu-id="6ed2b-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="6ed2b-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6ed2b-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6ed2b-139">Quita un salón</span><span class="sxs-lookup"><span data-stu-id="6ed2b-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="6ed2b-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="6ed2b-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="6ed2b-141">Quita mensajes de un salón</span><span class="sxs-lookup"><span data-stu-id="6ed2b-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="6ed2b-142">Con el cmdlet **New-CsPersistentChatRoom** puede crear salones de chat y con **Set-CsPersistentChatRoom** puede configurar un salón de chat existente, incluso agregar usuarios al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="6ed2b-143">Puede configurar los siguientes parámetros del salón de chat:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="6ed2b-144">Disabled.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-144">Disabled.</span></span> <span data-ttu-id="6ed2b-145">Le permite deshabilitar o habilitar un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="6ed2b-146">Invitaciones.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-146">Invitations.</span></span> <span data-ttu-id="6ed2b-147">Permite habilitar o deshabilitar las invitaciones de los salones de chat, que se usan para informar a los usuarios cuando se los agregó como miembros de un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="6ed2b-148">La configuración predeterminada para las invitaciones es la heredada, por lo que el salón de chat adopta las opciones de configuración de la invitación configuradas en la categoría al que pertenece.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="6ed2b-149">Al configurar las opciones de las invitaciones en False en el salón de chat, se cambia la configuración de la categoría.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="6ed2b-150">Privacidad.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-150">Privacy.</span></span> <span data-ttu-id="6ed2b-151">Permite especificar si un salón de chat está abierto, cerrado o secreto.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="6ed2b-152">Salones abiertos puedan buscar y tener acceso a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="6ed2b-153">Salones de cerrado se pueden buscar por cualquier usuario, pero se pueden tener acceso sólo por los miembros.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="6ed2b-154">Secretas salones puedan buscar y tener acceso a sólo los miembros de la sala.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="6ed2b-155">De forma predeterminada, cada nueva sala se configura inicialmente como cerrado.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="6ed2b-156">Type.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-156">Type.</span></span> <span data-ttu-id="6ed2b-157">Permite especificar si un salón de chat es un salón Normal, que acepta mensajes enviados por cualquier miembro o un salón de tipo auditorio, que acepta mensajes expuestos sólo por un moderador.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="6ed2b-158">Addin.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-158">Addin.</span></span> <span data-ttu-id="6ed2b-159">Permite asociar complementos previamente configurados con un salón de chat, por lo que los miembros pueden ver el contenido URL mientras participan.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="6ed2b-160">Además de los parámetros anteriores, el cmdlet **Set-CsPersistentChatRoom** permite asignar a usuarios al salón de chat de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="6ed2b-161">Members.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-161">Members.</span></span> <span data-ttu-id="6ed2b-162">Configura la pertenencia del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-162">Configures membership for the chat room.</span></span> <span data-ttu-id="6ed2b-163">Puede agregar o quitar miembros individuales o varios miembros con un único cmdlet al especificar la dirección SIP de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="6ed2b-164">Para permitir la adición en masa de usuarios, puede especificar también grupos de distribución o unidades organizativas de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="6ed2b-165">Managers.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-165">Managers.</span></span> <span data-ttu-id="6ed2b-166">Permite asignar directores al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="6ed2b-167">Los directores tienen los permisos para definir la pertenencia de un salón de chat junto con otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="6ed2b-p115">Presenters. Permite asignar moderadores a un salón de chat auditorio.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-p115">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
 <span data-ttu-id="6ed2b-170">Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros, vea [Skype para Shell de administración de Business Server 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="6ed2b-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="6ed2b-171">Crear un salón</span><span class="sxs-lookup"><span data-stu-id="6ed2b-171">Create a new room</span></span>

<span data-ttu-id="6ed2b-172">Puede crear un salón con el cmdlet **New-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="6ed2b-173">Por ejemplo, el siguiente comando crea un salón de chat denominado ITChatRoom on the pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="6ed2b-174">En este ejemplo, el salón de chat se agrega a la categoría de TI:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-174">In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="6ed2b-175">**Nota:** PersistentChatPoolFqdn no es necesario si se cumple una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="6ed2b-176">Hay un solo grupo de servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="6ed2b-177">Proporciona un FQDN del grupo de servidores a la categoría.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="6ed2b-178">Proporciona un FQDN del grupo de servidores para agregar el salón.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="6ed2b-179">Configurar un salón existente</span><span class="sxs-lookup"><span data-stu-id="6ed2b-179">Configure an existing room</span></span>

<span data-ttu-id="6ed2b-180">Puede configurar un salón existente mediante el cmdlet **Set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="6ed2b-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="6ed2b-181">Por ejemplo, el comando siguiente asigna user1 como un miembro y moderador y user2 como un administrador de la sala de auditorio testCat:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="6ed2b-182">En el siguiente ejemplo, se agregan todos los usuarios de la UO de NorthAmericaUsers en Active Directory al salón de chat NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="6ed2b-183">En el siguiente ejemplo, se agregan todos los miembros del grupo de distribución Finanzas al mismo salón de chat:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="6ed2b-184">Habilitar o deshabilitar un salón</span><span class="sxs-lookup"><span data-stu-id="6ed2b-184">Disable or enable a room</span></span>

<span data-ttu-id="6ed2b-185">Si el tema de un salón de Chat en grupo ya no es relevante, puede que el salón de chat a no esté disponible para los usuarios deshabilitando el programa.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="6ed2b-186">Cuando un salón de chat está deshabilitado, todos los miembros inmediatamente están desconectados de la sala.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="6ed2b-187">Después de un salón de chat está deshabilitado, los usuarios no se pueden volver a unirse a él o buscar en las búsquedas de salón de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="6ed2b-188">Si continúa el historial del salón de chat, el contenido se conserva cuando se deshabilita el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="6ed2b-189">Pero, dicho contenido no aparecerá en las búsquedas mientras el salón de chat permanezca deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="6ed2b-190">Si vuelve a habilitar el salón de chat, los usuarios podrán buscar mensajes publicados antes de que se deshabilitara el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="6ed2b-191">Para obtener información acerca de cómo configurar el historial de salones de chat, vea [Administrar categorías en el servidor de Chat persistente en Skype para Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="6ed2b-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="6ed2b-192">Si un salón de chat se encuentra deshabilitado, se conservan su lista de pertenencia y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="6ed2b-193">Como administrador, puede habilitar un salón que se ha deshabilitado y no es necesario que vuelva a establecer la configuración de forma manual.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="6ed2b-194">Puede deshabilitar un salón mediante el cmdlet **Set-CsPersistentChatRoom** y establecer el parámetro deshabilitado en True:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="6ed2b-195">Para habilitar un salón de chat, establezca el parámetro Disabled en False:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="6ed2b-196">Obtener información acerca de los salones</span><span class="sxs-lookup"><span data-stu-id="6ed2b-196">Get information about rooms</span></span>

<span data-ttu-id="6ed2b-197">Para obtener información sobre los salones configurados para su organización, puede usar el cmdlet **Get-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="6ed2b-198">El siguiente comando devuelve información sobre todos los salones de chat configurados para la organización:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="6ed2b-199">Quitar todo el contenido de un salón</span><span class="sxs-lookup"><span data-stu-id="6ed2b-199">Remove all content from a room</span></span>

<span data-ttu-id="6ed2b-p121">Puede quitar el contenido de un salón al usar el cmdlet **Clear-CsPersistentChatRoom**. Por ejemplo, el siguiente comando quita todo el contenido del salón de chat persistente ITChatRoom que se agregó al él el 1 de marzo de 2015 o antes de esa fecha:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-p121">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="6ed2b-202">Quitar un mensaje de un salón</span><span class="sxs-lookup"><span data-stu-id="6ed2b-202">Remove a message from a room</span></span>

<span data-ttu-id="6ed2b-p122">Puede quitar uno o más mensajes en la base de datos del chat persistente y, de forma opcional, cambiar el mensaje con un mensaje predeterminado o con un mensaje del administrador. Para ello, use el cmdlet **Remove-CsPersistentChatMessage**. Por ejemplo, el siguiente comando quita todos los mensajes del salón de chat ITChatRoom que kenmyer@contoso.com haya publicado:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-p122">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="6ed2b-205">En el siguiente ejemplo se cambian todos los mensajes quitados por una advertencia de que el mensaje ya no se encuentra disponible:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="6ed2b-206">Quitar un salón</span><span class="sxs-lookup"><span data-stu-id="6ed2b-206">Remove a room</span></span>

<span data-ttu-id="6ed2b-207">Puede quitar un salón con el cmdlet **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="6ed2b-208">Por ejemplo, el siguiente comando quita el salón de chat RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="6ed2b-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="6ed2b-209">Mover un salón de una categoría a otra</span><span class="sxs-lookup"><span data-stu-id="6ed2b-209">Move a room from one category to another</span></span>

<span data-ttu-id="6ed2b-p123">Si un director de un salón de chat tiene privilegios de **Creador** en otra categoría, puede mover el salón de una categoría a otra. El salón no se eliminará ni volverá a crearse, ya que es un cambio de asociación dentro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-p123">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="6ed2b-p124">El cambio de categoría de un salón de chat tiene que realizarse de forma ocasional y con precaución. Una categoría determina la pertenencia permitida para el salón de chat, por lo tanto, cuando un salón de chat se mueve a otra categoría, se purgan todas las listas de control de acceso del sistema (SACL) que ya no son compatibles con la nueva categoría. Por ejemplo, si un usuario era miembro del salón y ya no es un miembro permitido en la nueva categoría, la pertenencia del salón se modificará y se quitará al usuario del salón.</span><span class="sxs-lookup"><span data-stu-id="6ed2b-p124">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

