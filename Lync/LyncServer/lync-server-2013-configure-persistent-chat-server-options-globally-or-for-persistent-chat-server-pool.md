---
title: 'Lync Server 2013: Configurar opciones de servidor de chat persistentes a escala global o para grupos de servidores de chat persistentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed79d1144c1ccb7abeac8dcf7d1f4d44c63e93e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="0a51c-102">Configurar opciones de servidor de chat persistentes a escala global o para grupos de servidores de chat persistentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a51c-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a51c-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0a51c-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0a51c-104">En el panel de control de Lync Server 2013, puede usar la sección **configuración de chat** persistente de la página **chat persistente** para configurar de forma global la configuración de la conversación persistente donde se aplica a todos los grupos de servidores de chat persistentes o a un determinado Grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0a51c-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a51c-105">Para configurar y usar el servidor de chat persistente, primero debe usar topología Builder para agregar la compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="0a51c-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="0a51c-106">Para obtener más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a su implementación en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="0a51c-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="0a51c-107">Para configurar las opciones de chat persistentes de forma global</span><span class="sxs-lookup"><span data-stu-id="0a51c-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="0a51c-108">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0a51c-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a51c-109">En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="0a51c-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="0a51c-110">Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a51c-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0a51c-111">También puede usar los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a51c-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="0a51c-112">Para obtener más información, vea <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="0a51c-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="0a51c-113">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Configuración de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="0a51c-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="0a51c-114">En la página **configuración de chat persistente** , haga clic en **nuevo** y, a continuación, en **configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="0a51c-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0a51c-115">Elija esta opción si quiere que la configuración se aplique a todos los grupos de servidores de chat persistentes implementados en el sitio.</span><span class="sxs-lookup"><span data-stu-id="0a51c-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="0a51c-116">Haga clic en <STRONG>configuración del grupo</STRONG> si quiere que la configuración se aplique a un grupo de servidores de chat persistente específico.</span><span class="sxs-lookup"><span data-stu-id="0a51c-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="0a51c-117">En **seleccionar un sitio**, seleccione el sitio que se va a configurar para la configuración del sitio del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0a51c-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="0a51c-118">En **Nueva configuración de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a51c-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="0a51c-p105">En **Nombre**, especifique un nombre para los nuevos parámetros de configuración. El nombre de sitio ya existe de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a51c-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="0a51c-p106">En **Historial de chat predeterminado**, defina la cantidad de mensajes de chat que se va a procesar para cada salón tras la primera solicitud. La cantidad predeterminada es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.</span><span class="sxs-lookup"><span data-stu-id="0a51c-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="0a51c-124">El servidor de chat persistente guardará estos mensajes en la memoria caché, por lo que, si aumenta este número, se almacenarán en caché más mensajes.</span><span class="sxs-lookup"><span data-stu-id="0a51c-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="0a51c-125">El acceso al contenido del historial siempre se encuentra disponible a través de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0a51c-125">You can always access historical content by search.</span></span> <span data-ttu-id="0a51c-126">La cantidad predeterminada solo indica la cantidad máxima de mensajes que ve inicialmente cuando se conecta a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="0a51c-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="0a51c-p108">En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo del archivo de cada historial de chat. La cantidad predeterminada es 20 MB (20 000 KB). Este es el tamaño máximo de archivo que puede cargarse a cualquier salón de chat del sistema (en el que las cargas de archivos estén habilitadas por su correspondiente parámetro de **Categoría**).</span><span class="sxs-lookup"><span data-stu-id="0a51c-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="0a51c-130">Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores que usan el servidor&nbsp;de chat grupal de Office Communications Server 2007 R2 o Lync Server 2010, la conversación grupal puede publicar archivos en un salón.</span><span class="sxs-lookup"><span data-stu-id="0a51c-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="0a51c-131">El cliente de Lync 2013 no tiene la funcionalidad de carga y descarga de archivos, por lo que si tiene una implementación de Lync 2013 pura o un cliente de Lync 2013, no es posible publicar archivos en un salón de chat del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0a51c-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="0a51c-132">En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes.</span><span class="sxs-lookup"><span data-stu-id="0a51c-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="0a51c-133">El servidor de chat persistente envía información de la lista (que está conectada a un salón de chat) a todos los participantes hasta que la cantidad de usuarios conectados alcance este número.</span><span class="sxs-lookup"><span data-stu-id="0a51c-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="0a51c-134">La cantidad predeterminada es 75.</span><span class="sxs-lookup"><span data-stu-id="0a51c-134">By default, the number is 75.</span></span> <span data-ttu-id="0a51c-135">Este límite indica la cantidad máxima de participantes en una habitación determinada, más allá de la cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados sobre quién está presente en el salón.</span><span class="sxs-lookup"><span data-stu-id="0a51c-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="0a51c-p111">(Opcional). En **URL de administración de sala**, seleccione la dirección URL de administración de salón. Esta es la dirección URL de una administración de salones personalizada basada en la web. Si no necesita personalizar la administración de salones y, simplemente, usa la configuración predeterminada, deje esta opción en blanco. Una vez que se haya definido la dirección URL, se aplicará como la dirección URL de administración del salón tanto interna como externa.</span><span class="sxs-lookup"><span data-stu-id="0a51c-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="0a51c-140">Si desea personalizar la experiencia de creación de la sala e incluir su flujo de trabajo específico, puede crear una solución de administración de salas personalizada mediante el kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarlo en algún lugar y colocar la dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="0a51c-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="0a51c-141">Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.</span><span class="sxs-lookup"><span data-stu-id="0a51c-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="0a51c-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0a51c-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="0a51c-143">Para configurar las opciones de chat persistente para un grupo de servidores de chat persistente específico</span><span class="sxs-lookup"><span data-stu-id="0a51c-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="0a51c-144">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0a51c-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a51c-145">En el menú **Inicio** , seleccione el panel de control de Lync Server, o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="0a51c-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="0a51c-146">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a51c-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0a51c-147">También puede usar los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a51c-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="0a51c-148">Para obtener más información, vea <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="0a51c-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="0a51c-149">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Configuración de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="0a51c-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="0a51c-150">En la página **Configuración de chat persistente**, haga clic en **Nuevo** y, luego, en **Configuración del grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="0a51c-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="0a51c-151">En **seleccionar un servicio**, seleccione el servicio asociado al grupo de servidores de chat persistente que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="0a51c-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="0a51c-152">En **Nueva configuración de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a51c-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="0a51c-p115">En **Nombre**, especifique un nombre para la nueva configuración. El nombre del grupo de servidores del sitio ya existe de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a51c-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="0a51c-p116">En **Historial de chat predeterminado**, defina la cantidad de mensajes de chat que se va a procesar para cada salón tras la primera solicitud. La cantidad predeterminada es 30. Esta es la configuración global y los administradores pueden deshabilitar el historial de chat por categoría.</span><span class="sxs-lookup"><span data-stu-id="0a51c-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="0a51c-158">El servidor de chat persistente guardará estos mensajes en la memoria caché, por lo que, si aumenta este número, se almacenarán en caché más mensajes.</span><span class="sxs-lookup"><span data-stu-id="0a51c-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="0a51c-159">El acceso al contenido del historial siempre se encuentra disponible a través de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0a51c-159">You can always access historical content by search.</span></span> <span data-ttu-id="0a51c-160">La cantidad predeterminada solo indica la cantidad máxima de mensajes que ve inicialmente cuando se conecta a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="0a51c-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="0a51c-p118">En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo del archivo de cada historial de chat. La cantidad predeterminada es 20 MB (20 000 KB). Este es el tamaño máximo de archivo que puede cargarse a cualquier salón de chat del sistema (en el que las cargas de archivos estén habilitadas por su correspondiente parámetro de **Categoría**).</span><span class="sxs-lookup"><span data-stu-id="0a51c-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="0a51c-164">Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores (servidor de chat&nbsp;en grupo de Office Communications Server 2007 R2 o Lync Server 2010, chat grupal) pueden publicar archivos en una sala.</span><span class="sxs-lookup"><span data-stu-id="0a51c-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="0a51c-165">El cliente de Lync 2013 no tiene la funcionalidad de carga y descarga de archivos, por lo que si tiene una implementación de Lync 2013 pura o un cliente de Lync 2013, no es posible publicar archivos en un salón de chat del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0a51c-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="0a51c-166">En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes.</span><span class="sxs-lookup"><span data-stu-id="0a51c-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="0a51c-167">El servidor de chat persistente envía información de la lista (que está conectada a un salón de chat) a todos los participantes hasta que la cantidad de usuarios conectados alcance este número.</span><span class="sxs-lookup"><span data-stu-id="0a51c-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="0a51c-168">La cantidad predeterminada es 75.</span><span class="sxs-lookup"><span data-stu-id="0a51c-168">By default, the number is 75.</span></span> <span data-ttu-id="0a51c-169">Este límite indica la cantidad máxima de participantes en una habitación determinada, más allá de la cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados sobre quién está presente en el salón.</span><span class="sxs-lookup"><span data-stu-id="0a51c-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="0a51c-p121">En **URL de administración de sala**, seleccione la dirección URL de administración de salón. Se trata de la dirección URL de una implementación de administración de salones basada en web. Si no necesita personalizar la administración de salones y, simplemente, usa la configuración predeterminada, deje esta opción en blanco.</span><span class="sxs-lookup"><span data-stu-id="0a51c-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="0a51c-173">Si desea personalizar la experiencia de creación de la sala e incluir su flujo de trabajo específico, puede crear una solución de administración de salas personalizada mediante el kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarlo en algún lugar y colocar la dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="0a51c-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="0a51c-174">Esta dirección URL se envía al cliente, de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.</span><span class="sxs-lookup"><span data-stu-id="0a51c-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="0a51c-175">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0a51c-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

