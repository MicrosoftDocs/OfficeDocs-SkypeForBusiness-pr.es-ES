---
title: 'Lync Server 2013: roles de usuario en el servidor de chat persistente'
description: 'Lync Server 2013: roles de usuario en el servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aed64aaa9129e6667cd138bc4365acfb2a64d52c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550856"
---
# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f1ff0-103">Roles de usuario en el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1ff0-103">User roles in Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1ff0-104">_**Última modificación del tema:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="f1ff0-104">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="f1ff0-105">El servidor de chat persistente proporciona el concepto de miembros permitidos/denegados, que se aplica a las categorías de chat persistentes y a los controles que pueden tener acceso a salones de una categoría determinada.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-105">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f1ff0-106">Los miembros permitidos o denegados de una categoría no son los mismos que los de un rol de <STRONG>miembro</STRONG> , que se aplican a un salón de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-106">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="f1ff0-p101">Las búsquedas muestran todos los salones de chat abiertos y cerrados para los que el usuario que realiza la búsqueda se encuentra en la lista de miembros permitidos/denegados. Los salones secretos no se muestran a menos que el usuario que realiza la búsqueda sea miembro del salón secreto. De este modo, el usuario solo puede buscar salones de los que sea miembro o aquellos a los que pueda solicitar ser miembro.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-p101">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list. Secret rooms are not displayed unless the user who performs the search is a member of the secret room. The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="f1ff0-p102">El principio básico del concepto de miembros permitidos/denegados son las zonas de protección. Por ejemplo, en las instituciones financieras y bancarias, es muy común disponer de límites de protección que impidan a los comerciantes y analistas compartir comunicaciones durante la implementación de directivas y convenciones. Para ello, el administrador puede crear categorías de manera que una categoría admita la creación y el uso de salones por parte de los comerciantes, mientras que la otra admita la creación y el uso de salones por parte de los analistas. Esta limitación está diseñada para impedir que se agreguen usuarios como miembros del salón si la categoría principal lo prohíbe.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-p102">The primary rationale for the concept of Allowed/Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="f1ff0-114">A continuación se muestran los cuatro roles de usuario servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="f1ff0-114">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="f1ff0-115">**Creador:** Usuarios con permisos para crear salones de chat.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-115">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="f1ff0-116">Estos usuarios figuran en la lista de autores de determinadas categorías: pueden crear salones de chat en sus categorías, asignar miembros en función de la categoría y asignar administradores del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-116">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="f1ff0-117">El usuario que cree un salón de chat se agregará automáticamente como administrador del salón.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-117">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1ff0-p104">Los autores solo están autorizados a crear salones de chat. La promoción automática al rol de Administrador es la que permite al Autor delimitar las pertenencias a grupos, etc., en los servicios de chat creados.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="f1ff0-120">Este rol ofrece la opción de controlar quién crea salones de chat en su organización, lo cual resulta de especial utilidad si desea administrar de forma centralizada creación de salones de chat para garantizar el cumplimiento de directivas y convenciones, con la consiguiente delegación de la administración de la sala de chat a los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-120">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="f1ff0-121">**Administrador:** Usuarios que administran las propiedades de un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-121">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="f1ff0-122">Los administradores de salones de chat pueden modificar la lista de miembros (agregar o quitar miembros), así como la lista de administradores de la sala de chat (agregar y quitar administradores).</span><span class="sxs-lookup"><span data-stu-id="f1ff0-122">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="f1ff0-123">Los administradores de los salones de chat pueden agregarse a sí mismos a la lista de miembros o de moderadores (en salones de auditorio) para participar en el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-123">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="f1ff0-124">También pueden deshabilitar salones de chat (los administradores pueden consultar los salones de chat deshabilitados para eliminarlos de forma permanente).</span><span class="sxs-lookup"><span data-stu-id="f1ff0-124">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="f1ff0-125">Los administradores pueden cambiar todas las propiedades de los salones de chat, excepto la categoría del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-125">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="f1ff0-126">Solo el administrador de chat persistente puede cambiar la categoría una vez que se haya creado el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-126">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f1ff0-127">En caso de que el administrador también sea autor en otra categoría, estará autorizado a cambiar la categoría a otra en la que esté autorizado a crear salones de chat.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-127">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="f1ff0-128">**Miembro:** Usuarios que son miembros de un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-128">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="f1ff0-129">Estos usuarios pueden ver los salones de chat en el directorio (incluso si el salón de chat es secreto), así como suscribirse al salón de chat (incluidas las opciones de metadatos, como los mensajes no leídos, los filtros de ego y los filtros de palabras clave), y participar en el salón de chat (puede publicar, a menos que el salón sea un salón de auditorio en el</span><span class="sxs-lookup"><span data-stu-id="f1ff0-129">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="f1ff0-130">Los usuarios que no son miembros del salón de chat pueden buscar el salón de chat si están en la lista de miembros permitidos de la categoría, pero necesitan solicitar acceso para unirse a estos salones de chat para tener acceso al contenido.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-130">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="f1ff0-131">(No hay acceso ni aprobaciones de solicitud integradas en el sistema; estas se realizan de forma externa por correo electrónico, teléfono u otros formularios de contacto).</span><span class="sxs-lookup"><span data-stu-id="f1ff0-131">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="f1ff0-132">**Moderador:** Usuarios que pueden publicar en un salón de Auditorio.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-132">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1ff0-133">El servidor de chat persistente permite a los usuarios crear y administrar salones de chat para un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-133">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="f1ff0-134">Sin embargo, los usuarios no pueden crear ni administrar salones de chat en otros sitios dentro de la misma topología.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-134">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="f1ff0-135">Asegúrese de especificar los creadores y creadores de salones de chat para todos los sitios de la organización.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-135">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="f1ff0-136">Los siguientes roles son roles de administrador para el servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="f1ff0-136">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="f1ff0-137">**Administrador de chat persistente (CsPersistentChatAdministrator):** Se trata de un nuevo rol de control de acceso de Role-Based (RBAC) para administrar y administrar el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-137">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="f1ff0-138">Los usuarios o grupos de seguridad designados como CsPersistentChatAdministrator pueden administrar el servidor de chat persistente con los cmdlets de Windows PowerShell de forma remota (es decir, desde un equipo que no sea el servidor de chat persistente).</span><span class="sxs-lookup"><span data-stu-id="f1ff0-138">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="f1ff0-139">El servidor de chat persistente comprueba que el administrador de chat persistente sea miembro del grupo local de administradores de RTC local en el servidor front-end del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-139">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="f1ff0-140">El rol CsPersistentChatAdministrator puede administrar los salones de chat (modificar todas las propiedades como, por ejemplo, la pertenencia a grupos, los administradores o las categorías, marcar los salones como deshabilitados, etc.) y crear y administrar categorías de salones de chat que definan quién puede crear y tener acceso a los salones.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-140">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="f1ff0-141">Los administradores también pueden marcar salones de chat como deshabilitados y eliminar los salones de chat que ya no estén activos.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-141">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="f1ff0-142">Los administradores no están sujetos a las restricciones que tienen los Autores o los Miembros permitidos.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-142">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="f1ff0-143">Los administradores pueden crear cualquier tipo de salón de chat y agregarse a sí mismos como miembros de cualquier salón de chat.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-143">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="f1ff0-144">Los administradores también pueden modificar y administrar la configuración de los chats persistentes (propiedades de grupo, la configuración global y la configuración de cumplimiento) y también pueden planear e implementar la migración desde una implementación de servidor de chat de grupo anterior al servidor de chat persistente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-144">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="f1ff0-145">**Administrador de Lync:** Administrador empresarial general de Lync Server 2013 responsable de la implementación.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-145">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="f1ff0-146">**Operations Manager:** Usuario responsable de la administración de las operaciones diarias.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-146">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="f1ff0-147">**Desarrolladores y partners de terceros:** Los desarrolladores de terceros amplían el sistema y, en particular, proporcionan una solución de pared ética para conversaciones en grupo, herramientas y soporte de cumplimiento, clientes web/móviles y un marco para el desarrollo de robots.</span><span class="sxs-lookup"><span data-stu-id="f1ff0-147">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

