---
title: 'Lync Server 2013: configurar categorías'
description: 'Lync Server 2013: configurar categorías.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1342ea0f5ee32284a32ac0dcc8ab3d370bb1dd91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578146"
---
# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="7ac2d-103">Configurar categorías en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ac2d-103">Configure categories in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ac2d-104">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="7ac2d-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="7ac2d-105">En el panel de control de Lync Server 2013, puede usar la sección **categoría** de la página **chat persistente** para configurar las categorías.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-105">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="7ac2d-106">Una categoría de salón de chat persistente es una estructura lógica para organizar salones de chat.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-106">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="7ac2d-107">Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que pueden crear o unirse a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-107">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="7ac2d-108">Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-108">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="7ac2d-109">Las categorías de salones de chat pueden contener salones de chat, pero no otras categorías.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-109">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="7ac2d-110">Cada categoría describe su contenido con metadatos, como Nombre y Descripción.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-110">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="7ac2d-111">Además, la categoría tiene propiedades que se pueden definir para controlar el comportamiento de los salones de chat que pertenecen a esta categoría, por ejemplo si el salón de chat permite invitaciones, cargas de archivos o contiene el historial de chat.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-111">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="7ac2d-112">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="7ac2d-112">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="7ac2d-113">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-113">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ac2d-114">En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-114">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="7ac2d-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7ac2d-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7ac2d-116">También puede usar cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-116">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7ac2d-117">Para obtener más información, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-117">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="7ac2d-118">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Categoría**.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-118">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="7ac2d-119">Para varias implementaciones del grupo de servidores de chat persistente, seleccione el grupo adecuado de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="7ac2d-120">En la página **Categoría**, haga clic en **Nueva** o **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-120">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="7ac2d-121">En **seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que se debe crear la categoría.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="7ac2d-122">El servicio es el grupo de servidores de chat persistente que usa el chat persistente (cliente) para identificar a qué grupo pertenece la categoría.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-122">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="7ac2d-123">Una categoría puede pertenecer solo a un grupo de servidores de chat persistente y no se puede mover a otro o compartido con otro grupo.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-123">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="7ac2d-124">En **Nueva categoría**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ac2d-124">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="7ac2d-125">En \*\*Nombre \*\*, especifique un nombre para el nuevo salón.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-125">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="7ac2d-126">En  \*\*Descripción \*\*, proporcione una descripción detallada de la categoría del salón (por ejemplo, una categoría de salón para Contoso).</span><span class="sxs-lookup"><span data-stu-id="7ac2d-126">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="7ac2d-127">Para controlar si se pueden habilitar invitaciones para salones de chat, active o desactive la casilla **Habilitar invitaciones**.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-127">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="7ac2d-128">Si la activa, los salones de esta categoría pueden tener invitaciones activadas o desactivadas; si se desactiva, los salones de esta categoría no pueden tener invitaciones.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-128">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="7ac2d-129">Si un salón tiene invitaciones, cuando se agrega un nuevo miembro a un salón, recibe una notificación del nuevo salón en su cliente de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-129">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="7ac2d-p107">Para controlar las cargas de archivos en salones de chat que pertenezcan a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si se activa, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos; si se desactiva, los salones de esta categoría no pueden tener cargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7ac2d-132">Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores que usan el servidor de chat en grupo de Office Communications Server 2007 R2 &nbsp; o Lync server 2010, el chat en grupo puede publicar archivos en un salón.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-132">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="7ac2d-133">El cliente de Lync 2013 no tiene capacidad de carga y descarga de archivos, por lo que si tiene una implementación pura de Lync 2013 o un cliente de Lync 2013, no se pueden publicar archivos en un salón de chat del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-133">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="7ac2d-134">Para controlar el historial de chat, Active o desactive la casilla **Habilitar el historial de chat** .</span><span class="sxs-lookup"><span data-stu-id="7ac2d-134">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="7ac2d-135">Si se activa, los salones de chat se vuelven persistentes; en caso contrario, los mensajes de chat no permanecen.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-135">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="7ac2d-136">Si se habilita el cumplimiento, los chats de los salones se guardarán en conformidad, pero los usuarios no podrán obtener acceso a los mensajes más antiguos.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-136">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="7ac2d-137">Esta opción se puede usar para salones designados para colaboraciones ad hoc en tiempo real y que no necesitan que se conserve el historial de chat.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-137">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="7ac2d-138">En **Editar categoría**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ac2d-138">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="7ac2d-139">En **pertenencia**, en la sección **miembros permitidos** , agregue o quite usuarios y otras entidades de seguridad de servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, etc.) que pueden agregarse como miembros de los salones de chat que pertenecen a la categoría.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-139">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="7ac2d-140">Los elementos principales permitidos por una categoría pueden buscar salones en la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón pueden buscarlo en el directorio).</span><span class="sxs-lookup"><span data-stu-id="7ac2d-140">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="7ac2d-141">En **pertenencia**, en la sección **miembros denegados** , agregue o quite usuarios y otras entidades de Active Directory asociadas con miembros denegados del salón.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-141">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="7ac2d-142">En **pertenencia**, en la sección **creadores** , agregue o quite usuarios y otras entidades de Active Directory asociadas con los creadores de la categoría.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-142">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="7ac2d-143">Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-143">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="7ac2d-144">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7ac2d-144">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

