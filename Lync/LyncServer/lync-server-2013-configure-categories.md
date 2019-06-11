---
title: 'Lync Server 2013: Configurar categorías'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310d0b2e32c8a21f00e20593a408df260eb80e32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="c7886-102">Configurar categorías en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7886-102">Configure categories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7886-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="c7886-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="c7886-104">En el panel de control de Lync Server 2013, puede usar la sección **categoría** de la página **chat persistente** para configurar categorías.</span><span class="sxs-lookup"><span data-stu-id="c7886-104">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="c7886-105">Una categoría de salón de chat persistente es una estructura lógica para organizar salones de chat.</span><span class="sxs-lookup"><span data-stu-id="c7886-105">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="c7886-106">Una categoría define un conjunto predeterminado de listas de control de acceso (ACL) para controlar los usuarios y grupos de usuarios que se pueden crear o unir a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="c7886-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="c7886-107">Puede usar zonas de protección de datos confidenciales de imposición de categorías entre distintas subdivisiones en sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="c7886-107">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="c7886-108">Las categorías de salones de chat pueden contener salones de chat, pero no otras categorías.</span><span class="sxs-lookup"><span data-stu-id="c7886-108">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="c7886-109">Cada categoría describe su contenido con metadatos como Name y Description.</span><span class="sxs-lookup"><span data-stu-id="c7886-109">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="c7886-110">Además, la categoría tiene propiedades que se pueden definir para controlar el comportamiento de los salones de chat que pertenecen a esta categoría; así, si el salón de chat permite Invitations, File Uploads o contiene el Chat History.</span><span class="sxs-lookup"><span data-stu-id="c7886-110">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="c7886-111">Para configurar categorías para salones de chat</span><span class="sxs-lookup"><span data-stu-id="c7886-111">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="c7886-112">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c7886-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c7886-113">En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="c7886-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="c7886-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c7886-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c7886-115">También puede usar los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7886-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="c7886-116">Para obtener más información, vea <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="c7886-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="c7886-117">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Categoría**.</span><span class="sxs-lookup"><span data-stu-id="c7886-117">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="c7886-118">Para varias implementaciones del grupo de servidores de chat persistentes, seleccione el grupo adecuado de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c7886-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="c7886-119">En la página **Categoría**, haga clic en **Nuevo** o en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c7886-119">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="c7886-120">En **seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de chat persistente en el que se debe crear la categoría.</span><span class="sxs-lookup"><span data-stu-id="c7886-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="c7886-121">El servicio es el grupo de servidores de chat persistente que usa el chat persistente (cliente) para identificar a qué grupo pertenece la categoría.</span><span class="sxs-lookup"><span data-stu-id="c7886-121">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="c7886-122">Una categoría puede pertenecer a un único grupo de servidores de chat persistentes, no se puede mover a otro grupo o compartir con otro grupo.</span><span class="sxs-lookup"><span data-stu-id="c7886-122">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="c7886-123">En **Nueva categoría**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7886-123">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="c7886-124">En **Nombre**, especifique un nombre para la nueva categoría de salón.</span><span class="sxs-lookup"><span data-stu-id="c7886-124">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="c7886-125">En **Descripción**, proporcione una descripción detallada sobre la categoría del salón (por ejemplo, una categoría de salón para Contoso).</span><span class="sxs-lookup"><span data-stu-id="c7886-125">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="c7886-126">Para controlar si las invitaciones se pueden habilitar para salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar invitaciones**.</span><span class="sxs-lookup"><span data-stu-id="c7886-126">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="c7886-127">Si está activada, los salones de esta categoría puedan tener invitaciones activas o inactivas y, si está desactivada, el salón de esta categoría no puede tener invitaciones.</span><span class="sxs-lookup"><span data-stu-id="c7886-127">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="c7886-128">Si un salón tiene invitaciones, cuando se agrega un nuevo miembro a un salón, recibe una notificación de la nueva sala en su cliente de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c7886-128">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="c7886-p107">Para controlar las cargas de archivos en salones de chat que pertenecen a esta categoría, active o desactive la casilla **Habilitar carga de archivo**. Si está activada, los salones de esta categoría pueden habilitar o deshabilitar las cargas de archivos y, si no está activada, los salones de esta categoría no pueden tener cargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="c7886-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="c7886-131">Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores que usan el servidor de&nbsp;chat grupal de Office Communications Server 2007 R2 o Lync Server 2010, la conversación grupal puede publicar archivos en un salón.</span><span class="sxs-lookup"><span data-stu-id="c7886-131">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="c7886-132">El cliente de Lync 2013 no tiene la funcionalidad de carga y descarga de archivos, por lo que si tiene una implementación de Lync 2013 pura o un cliente de Lync 2013, no es posible publicar archivos en un salón de chat del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c7886-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="c7886-133">Para controlar el historial de conversaciones, Active o desactive la casilla de verificación **Habilitar el historial de chat** .</span><span class="sxs-lookup"><span data-stu-id="c7886-133">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="c7886-134">Si está activada, los salones de chat serán persistentes; en caso contrario, los mensajes de chats no persisten.</span><span class="sxs-lookup"><span data-stu-id="c7886-134">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="c7886-135">Si el cumplimiento está habilitado, los chats del salón se guardarán en consecuencia, pero los usuarios no podrán tener acceso a los mensajes antiguos.</span><span class="sxs-lookup"><span data-stu-id="c7886-135">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="c7886-136">Esta opción puede usarse en salones designados para la colaboración en tiempo real y ad-hoc que no necesiten que el historial de chat persista.</span><span class="sxs-lookup"><span data-stu-id="c7886-136">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="c7886-137">En **Editar categoría**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7886-137">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="c7886-138">En **pertenencia**, en la sección **miembros permitidos** , agregar o quitar usuarios y otros principios de los servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, etc.) que se pueden agregar como miembros de salones de chat pertenece a la categoría.</span><span class="sxs-lookup"><span data-stu-id="c7886-138">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="c7886-139">Las entidades de seguridad permitidas por una categoría pueden buscar los salones de la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón podrán encontrarlo en el directorio).</span><span class="sxs-lookup"><span data-stu-id="c7886-139">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="c7886-140">En **pertenencia**, en la sección **miembros** denegados, agregue o quite usuarios y otros principales de Active Directory asociados a miembros que se deniegan del salón.</span><span class="sxs-lookup"><span data-stu-id="c7886-140">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="c7886-141">En **pertenencia**, en la sección **creadores** , agregue o quite usuarios y otras entidades de Active Directory asociadas con los creadores de la categoría.</span><span class="sxs-lookup"><span data-stu-id="c7886-141">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="c7886-142">Un creador es un usuario que tiene permisos para crear salones de chat y asignar administradores y miembros de los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="c7886-142">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="c7886-143">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c7886-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

