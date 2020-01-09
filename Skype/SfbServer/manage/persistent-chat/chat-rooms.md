---
title: Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumen: Aprenda a administrar salones de chat del servidor de chat persistente en Skype empresarial Server 2015.'
ms.openlocfilehash: cbced7f62a4684e5541e35b5985b7e93cc7d3e66
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992125"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="1d2a5-103">Administrar salones de chat en el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="1d2a5-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1d2a5-104">**Resumen:** Aprenda a administrar salones de chat del servidor de chat persistente en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1d2a5-105">Con el uso correcto de las categorías, es mucho más fácil crear y administrar los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="1d2a5-106">Una categoría define quién puede crear o unirse A los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="1d2a5-107">Antes de intentar administrar los salones de chat, asegúrese de leer las [categorías de chat persistentes, los salones de chat y los roles de usuario en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) y [administrar las categorías en el servidor de chat persistente en skype empresarial Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="1d2a5-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d2a5-108">Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="1d2a5-109">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="1d2a5-110">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="1d2a5-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="1d2a5-111">Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="1d2a5-112">Puede configurar y administrar salones de chat con la interfaz de línea de comandos de Windows PowerShell o con el cliente de Skype empresarial si es miembro del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="1d2a5-113">En este tema se describe cómo administrar los salones de chat con la interfaz de línea de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="1d2a5-114">Si desea administrar salones de chat con el cliente de Skype empresarial, consulte la ayuda del cliente.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="1d2a5-115">Los salones de chat pueden ser de dos tipos: normal y Auditorio.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="1d2a5-116">Un salón de chat normal permite a todos los miembros publicar y leer mensajes.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="1d2a5-117">Un auditorio es un tipo de salón de chat en el que solo pueden publicar los moderadores, pero todo el mundo puede leer.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="1d2a5-118">El acceso a los salones de chat y su administración dependen de los roles de usuario, de esta manera:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="1d2a5-119">Es preciso que los usuarios sean miembros de un salón de chat para poder publicar y leer mensajes.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="1d2a5-120">Los moderadores pueden publicar en los salones que son auditorios.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="1d2a5-121">Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="1d2a5-122">También pueden quitar o cambiar mensajes que se consideren inapropiados para un salón de chat específico.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="1d2a5-123">Los usuarios finales, incluidos los autores de los mensajes, no pueden eliminar contenido de ningún salón de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="1d2a5-124">Los administradores de salones de chat pueden realizar cambios en todas las propiedades de los salones de chat, incluyendo la deshabilitación de salas.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="1d2a5-125">Sin embargo, los administradores no pueden eliminar una sala o cambiar la categoría de una sala.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="1d2a5-126">Solo los administradores pueden eliminar un salón de chat una vez creado.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="1d2a5-127">Puede configurar y administrar los salones de chat por medio de los siguientes cmdlets de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="1d2a5-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="1d2a5-128">**Cmdlet**</span></span>|<span data-ttu-id="1d2a5-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1d2a5-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d2a5-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="1d2a5-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="1d2a5-131">Crea un salón de chat</span><span class="sxs-lookup"><span data-stu-id="1d2a5-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="1d2a5-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="1d2a5-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="1d2a5-133">Configura las opciones de un salón existente; asigna usuarios y grupos de usuarios al salón</span><span class="sxs-lookup"><span data-stu-id="1d2a5-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="1d2a5-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="1d2a5-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="1d2a5-135">Recuperar información sobre salas</span><span class="sxs-lookup"><span data-stu-id="1d2a5-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="1d2a5-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="1d2a5-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="1d2a5-137">Borra un salón o los mensajes de un salón</span><span class="sxs-lookup"><span data-stu-id="1d2a5-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="1d2a5-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="1d2a5-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="1d2a5-139">Quita un salón</span><span class="sxs-lookup"><span data-stu-id="1d2a5-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="1d2a5-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="1d2a5-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="1d2a5-141">Quita mensajes de un salón</span><span class="sxs-lookup"><span data-stu-id="1d2a5-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="1d2a5-142">Con el cmdlet **New-CsPersistentChatRoom** puede crear salones de chat y con **Set-CsPersistentChatRoom** puede configurar un salón de chat existente, incluso agregar usuarios al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="1d2a5-143">Puede configurar los siguientes parámetros del salón de chat:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="1d2a5-144">Disabled.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-144">Disabled.</span></span> <span data-ttu-id="1d2a5-145">Te permite deshabilitar o habilitar un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="1d2a5-146">Invitaciones.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-146">Invitations.</span></span> <span data-ttu-id="1d2a5-147">Permite habilitar o deshabilitar las invitaciones de los salones de chat, que se usan para informar a los usuarios cuando se los agregó como miembros de un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="1d2a5-148">La configuración predeterminada para las invitaciones es la heredada, por lo que el salón de chat adopta las opciones de configuración de la invitación configuradas en la categoría al que pertenece.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="1d2a5-149">Al configurar las opciones de las invitaciones en False en el salón de chat, se cambia la configuración de la categoría.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="1d2a5-150">Declaración.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-150">Privacy.</span></span> <span data-ttu-id="1d2a5-151">Le permite especificar si un salón de chat está abierto, cerrado o secreto.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="1d2a5-152">Cualquier persona puede buscar y acceder a las salas abiertas.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="1d2a5-153">Las salas cerradas pueden ser buscadas por cualquier persona, pero solo las pueden acceder los miembros.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="1d2a5-154">Solo los miembros del salón pueden buscar en ellas las salas de secretos.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="1d2a5-155">De forma predeterminada, cada nueva sala está configurada inicialmente como cerrada.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="1d2a5-156">Type.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-156">Type.</span></span> <span data-ttu-id="1d2a5-157">Permite especificar si un salón de chat es un salón normal, que acepta los mensajes publicados por cualquier miembro, o una sala de auditorio, que acepta los mensajes publicados solo por un moderador.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="1d2a5-158">Addin.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-158">Addin.</span></span> <span data-ttu-id="1d2a5-159">Permite asociar complementos previamente configurados con un salón de chat, por lo que los miembros pueden ver el contenido URL mientras participan.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="1d2a5-160">Además de los parámetros anteriores, el cmdlet **set-CsPersistentChatRoom** le permite asignar usuarios al salón de chat de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="1d2a5-161">Members.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-161">Members.</span></span> <span data-ttu-id="1d2a5-162">Configura la pertenencia del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-162">Configures membership for the chat room.</span></span> <span data-ttu-id="1d2a5-163">Puede agregar o quitar miembros individuales o varios miembros con un único cmdlet al especificar la dirección SIP de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="1d2a5-164">Para permitir la adición en masa de usuarios, puede especificar también grupos de distribución o unidades organizativas de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="1d2a5-165">Managers.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-165">Managers.</span></span> <span data-ttu-id="1d2a5-166">Permite asignar directores al salón de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="1d2a5-167">Los directores tienen los permisos para definir la pertenencia de un salón de chat junto con otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="1d2a5-p115">Presenters. Permite asignar moderadores a un salón de chat auditorio.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-p115">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="1d2a5-170">Para más detalles sobre la sintaxis, incluso todos los parámetros, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="1d2a5-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="1d2a5-171">Crear un salón</span><span class="sxs-lookup"><span data-stu-id="1d2a5-171">Create a new room</span></span>

<span data-ttu-id="1d2a5-172">Puede crear un salón con el cmdlet **New-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="1d2a5-173">Por ejemplo, el siguiente comando crea un salón de chat denominado ITChatRoom on the pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="1d2a5-174">En este ejemplo, el salón de chat se agrega a la categoría de TI:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="1d2a5-175">**Nota:** PersistentChatPoolFqdn no es necesario si una de las siguientes condiciones es cierta:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="1d2a5-176">Solo hay un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="1d2a5-177">Proporciona un FQDN del grupo de servidores a la categoría.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="1d2a5-178">Proporciona un FQDN del grupo de servidores para agregar el salón.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="1d2a5-179">Configurar un salón existente</span><span class="sxs-lookup"><span data-stu-id="1d2a5-179">Configure an existing room</span></span>

<span data-ttu-id="1d2a5-180">Puede configurar una sala existente con el cmdlet **set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="1d2a5-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="1d2a5-181">Por ejemplo, el siguiente comando asigna user1 como miembro y moderador, y usuario2 como director, de la sala testCat de auditorio:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="1d2a5-182">En el siguiente ejemplo, se agregan todos los usuarios de la UO de NorthAmericaUsers en Active Directory al salón de chat NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="1d2a5-183">En el siguiente ejemplo, se agregan todos los miembros del grupo de distribución Finanzas al mismo salón de chat:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="1d2a5-184">Habilitar o deshabilitar un salón</span><span class="sxs-lookup"><span data-stu-id="1d2a5-184">Disable or enable a room</span></span>

<span data-ttu-id="1d2a5-185">Si el tema de un salón de chat persistente ya no es relevante, puede deshabilitarlo para hacer que el salón de chat no esté disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="1d2a5-186">Cuando un salón de chat está deshabilitado, todos los miembros se desconectan inmediatamente del salón.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="1d2a5-187">Después de deshabilitar un salón de chat, los usuarios no pueden volver a unirse o encontrarlo en las búsquedas del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="1d2a5-188">Si el historial del salón de chat continúa, el contenido se conserva cuando el salón de chat está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="1d2a5-189">Pero, dicho contenido no aparecerá en las búsquedas mientras el salón de chat permanezca deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="1d2a5-190">Si vuelve a habilitar el salón de chat, los usuarios podrán buscar mensajes publicados antes de que se deshabilitara el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="1d2a5-191">Para obtener información sobre cómo configurar el historial del salón de chat, consulte [administrar categorías en el servidor de chat persistente en Skype empresarial server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="1d2a5-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="1d2a5-192">Si un salón de chat se encuentra deshabilitado, se conservan su lista de pertenencia y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="1d2a5-193">Como administrador, puede habilitar un salón que se ha deshabilitado y no es necesario que vuelva a establecer la configuración de forma manual.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="1d2a5-194">Para deshabilitar un salón, use el cmdlet **set-CsPersistentChatRoom** y establezca el parámetro disabled en true:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="1d2a5-195">Para habilitar un salón de chat, establezca el parámetro Disabled en False:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="1d2a5-196">Obtener información sobre salas</span><span class="sxs-lookup"><span data-stu-id="1d2a5-196">Get information about rooms</span></span>

<span data-ttu-id="1d2a5-197">Para obtener información sobre los salones configurados para su organización, puede usar el cmdlet **Get-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="1d2a5-198">El siguiente comando devuelve información sobre todos los salones de chat configurados para la organización:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="1d2a5-199">Quitar todo el contenido de un salón</span><span class="sxs-lookup"><span data-stu-id="1d2a5-199">Remove all content from a room</span></span>

<span data-ttu-id="1d2a5-p121">Puede quitar el contenido de un salón al usar el cmdlet **Clear-CsPersistentChatRoom**. Por ejemplo, el siguiente comando quita todo el contenido del salón de chat persistente ITChatRoom que se agregó al él el 1 de marzo de 2015 o antes de esa fecha:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-p121">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="1d2a5-202">Quitar un mensaje de un salón</span><span class="sxs-lookup"><span data-stu-id="1d2a5-202">Remove a message from a room</span></span>

<span data-ttu-id="1d2a5-p122">Puede quitar uno o más mensajes en la base de datos del chat persistente y, de forma opcional, cambiar el mensaje con un mensaje predeterminado o con un mensaje del administrador. Para ello, use el cmdlet **Remove-CsPersistentChatMessage**. Por ejemplo, el siguiente comando quita todos los mensajes del salón de chat ITChatRoom que kenmyer@contoso.com haya publicado:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-p122">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="1d2a5-205">En el siguiente ejemplo se cambian todos los mensajes quitados por una advertencia de que el mensaje ya no se encuentra disponible:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="1d2a5-206">Quitar un salón</span><span class="sxs-lookup"><span data-stu-id="1d2a5-206">Remove a room</span></span>

<span data-ttu-id="1d2a5-207">Puede quitar un salón con el cmdlet **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="1d2a5-208">Por ejemplo, el siguiente comando quita el salón de chat RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="1d2a5-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="1d2a5-209">Mover un salón de una categoría a otra</span><span class="sxs-lookup"><span data-stu-id="1d2a5-209">Move a room from one category to another</span></span>

<span data-ttu-id="1d2a5-p123">Si un director de un salón de chat tiene privilegios de **Creador** en otra categoría, puede mover el salón de una categoría a otra. El salón no se eliminará ni volverá a crearse, ya que es un cambio de asociación dentro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-p123">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="1d2a5-p124">El cambio de categoría de un salón de chat tiene que realizarse de forma ocasional y con precaución. Una categoría determina la pertenencia permitida para el salón de chat, por lo tanto, cuando un salón de chat se mueve a otra categoría, se purgan todas las listas de control de acceso del sistema (SACL) que ya no son compatibles con la nueva categoría. Por ejemplo, si un usuario era miembro del salón y ya no es un miembro permitido en la nueva categoría, la pertenencia del salón se modificará y se quitará al usuario del salón.</span><span class="sxs-lookup"><span data-stu-id="1d2a5-p124">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

