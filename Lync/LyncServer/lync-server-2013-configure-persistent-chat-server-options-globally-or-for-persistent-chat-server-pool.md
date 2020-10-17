---
title: 'Lync Server 2013: configurar las opciones del servidor de chat persistente de forma global o para el grupo de servidores de chat persistente'
description: 'Lync Server 2013: Configure las opciones del servidor de chat persistente de forma global o para el grupo de servidores de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0e26fc8719f9aa5f153a7962df70ee7237b980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564996"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="5461b-103">Configure las opciones del servidor de chat persistente de forma global o para el grupo de servidores de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5461b-103">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5461b-104">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5461b-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5461b-105">En el panel de control de Lync Server 2013, puede usar la sección **configuración de chat persistente** de la página **chat persistente** para establecer la configuración de chat persistente globalmente, donde se aplica a todos los grupos de servidores de chat persistente o a un grupo de servidores de chat persistente específico.</span><span class="sxs-lookup"><span data-stu-id="5461b-105">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5461b-106">Para configurar y usar el servidor de chat persistente, primero debe usar el generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="5461b-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="5461b-107">Para obtener más información, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="5461b-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="5461b-108">Para configurar las opciones de chat persistente de forma global</span><span class="sxs-lookup"><span data-stu-id="5461b-108">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="5461b-109">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5461b-109">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5461b-110">En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="5461b-110">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="5461b-111">Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5461b-111">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5461b-112">También puede usar cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5461b-112">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5461b-113">Para obtener más información, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="5461b-113">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="5461b-114">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Configuración de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="5461b-114">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="5461b-115">En la página **configuración de chat persistente** , haga clic en **nuevo** y, a continuación, haga clic en **configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="5461b-115">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5461b-116">Elija esta opción si desea que la configuración se aplique a todos los grupos de servidores de chat persistente implementados en el sitio.</span><span class="sxs-lookup"><span data-stu-id="5461b-116">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="5461b-117">Haga clic en <STRONG>configuración del grupo</STRONG> de servidores si desea que la configuración se aplique a un grupo de servidores de chat persistente específico.</span><span class="sxs-lookup"><span data-stu-id="5461b-117">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="5461b-118">En **seleccionar un sitio**, seleccione el sitio que se va a configurar para la configuración del sitio del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5461b-118">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="5461b-119">En **Nueva configuración de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5461b-119">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="5461b-p105">En **Nombre**, especifique un nombre para la nueva configuración. De forma predeterminada, el nombre del sitio ya existe.</span><span class="sxs-lookup"><span data-stu-id="5461b-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="5461b-p106">En **Historial de chat predeterminado**, defina el número de mensajes de chat que se procesarán para cada salón tras la primera solicitud. De forma predeterminada, el número es 30. Esta es la configuración global, y los administradores pueden deshabilitar el historial de chat por categoría.</span><span class="sxs-lookup"><span data-stu-id="5461b-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="5461b-125">El servidor de chat persistente almacenará estos mensajes en la memoria caché, por lo que, si aumenta este número, se almacenarán en caché más mensajes.</span><span class="sxs-lookup"><span data-stu-id="5461b-125">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="5461b-126">SIempre puede obtener acceso al contenido histórico mediante búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5461b-126">You can always access historical content by search.</span></span> <span data-ttu-id="5461b-127">El número predeterminado simplemente determina el número máximo de mensajes que ve inicialmente al conectarse a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="5461b-127">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="5461b-p108">En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo para cada historial de chat. De forma predeterminada, el número es 20 MB (20 000 KB). Este es el tamaño máximo para un archivo que se puede cargar en cualquier salón de chat en el sistema (para el cual las cargas de archivos están habilitadas mediante la configuración de su correspondiente **Categoría**).</span><span class="sxs-lookup"><span data-stu-id="5461b-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="5461b-131">Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores que usan el servidor de chat en grupo de Office Communications Server 2007 R2 &nbsp; o Lync server 2010, el chat en grupo puede publicar archivos en un salón.</span><span class="sxs-lookup"><span data-stu-id="5461b-131">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="5461b-132">El cliente de Lync 2013 no tiene capacidad de carga y descarga de archivos, por lo que si tiene una implementación pura de Lync 2013 o un cliente de Lync 2013, no se pueden publicar archivos en un salón de chat del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5461b-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="5461b-133">En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes.</span><span class="sxs-lookup"><span data-stu-id="5461b-133">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="5461b-134">El servidor de chat persistente envía información de la lista (quién está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcanza este número.</span><span class="sxs-lookup"><span data-stu-id="5461b-134">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="5461b-135">De forma predeterminada, el número es 75.</span><span class="sxs-lookup"><span data-stu-id="5461b-135">By default, the number is 75.</span></span> <span data-ttu-id="5461b-136">Este límite indica el número máximo de participantes en un salón más allá del cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados sobre quién está presente en el salón.</span><span class="sxs-lookup"><span data-stu-id="5461b-136">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="5461b-p111">(Opcional). En **URL de administración de salón**, seleccione la dirección URL de administración del salón. Esta es la dirección URL para una administración de salones personalizada basada en web. Si no necesita personalizar la administración de salones, y simplemente usa la configuración predeterminada, deje esta opción en blanco. Después de definir la dirección URL, se aplica como la dirección URL de administración de salones tanto internos como externos.</span><span class="sxs-lookup"><span data-stu-id="5461b-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="5461b-141">Si desea personalizar la experiencia de creación de salas e incluir su flujo de trabajo específico, puede crear una solución de administración de salas personalizada con el kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarla en algún lugar y colocar la dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="5461b-141">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="5461b-142">Esta dirección URL se envía al cliente para que cuando un usuario intente ver o crear un salón, se le dirija a su solución de administración de salones personalizada.</span><span class="sxs-lookup"><span data-stu-id="5461b-142">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="5461b-143">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5461b-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="5461b-144">Para configurar las opciones de chat persistente para un grupo de servidores de chat persistente específico</span><span class="sxs-lookup"><span data-stu-id="5461b-144">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="5461b-145">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5461b-145">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5461b-146">En el menú **Inicio** , seleccione el panel de control de Lync Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="5461b-146">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="5461b-147">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5461b-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5461b-148">También puede usar cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5461b-148">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5461b-149">Para obtener más información, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent chat Server by Using Windows PowerShell cmdlets</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="5461b-149">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="5461b-150">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Configuración de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="5461b-150">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="5461b-151">En la página **Configuración de chat persistente**, haga clic en **Nueva** y, a continuación, haga clic en **Configuración del grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="5461b-151">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="5461b-152">En **seleccionar un servicio**, seleccione el servicio asociado con el grupo de servidores de chat persistente que se va a configurar.</span><span class="sxs-lookup"><span data-stu-id="5461b-152">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="5461b-153">En **Nueva configuración de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5461b-153">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="5461b-p115">En **Nombre**, especifique un nombre para la nueva configuración. De forma predeterminada, el nombre del grupo de sitios ya existe.</span><span class="sxs-lookup"><span data-stu-id="5461b-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="5461b-p116">En **Historial de chat predeterminado**, defina el número de mensajes de chat que se procesarán para cada salón tras la primera solicitud. De forma predeterminada, el número es 30. Esta es la configuración global, y los administradores pueden deshabilitar el historial de chat por categoría.</span><span class="sxs-lookup"><span data-stu-id="5461b-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="5461b-159">El servidor de chat persistente almacenará estos mensajes en la memoria caché, por lo que, si aumenta este número, se almacenarán en caché más mensajes.</span><span class="sxs-lookup"><span data-stu-id="5461b-159">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="5461b-160">SIempre puede obtener acceso al contenido histórico mediante búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5461b-160">You can always access historical content by search.</span></span> <span data-ttu-id="5461b-161">El número predeterminado simplemente determina el número máximo de mensajes que ve inicialmente al conectarse a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="5461b-161">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="5461b-p118">En **Tamaño máximo de archivo (KB)**, seleccione el tamaño máximo de archivo para cada historial de chat. De forma predeterminada, el número es 20 MB (20 000 KB). Este es el tamaño máximo para un archivo que se puede cargar en cualquier salón de chat en el sistema (para el cual las cargas de archivos están habilitadas mediante la configuración de su correspondiente **Categoría**).</span><span class="sxs-lookup"><span data-stu-id="5461b-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="5461b-165">Esta configuración se aplica en el servidor porque las aplicaciones personalizadas o los clientes de chat de grupo anteriores (el servidor de chat en grupo de Office Communications Server 2007 R2 &nbsp; o Lync server 2010, chat en grupo) pueden publicar archivos en un salón.</span><span class="sxs-lookup"><span data-stu-id="5461b-165">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="5461b-166">El cliente de Lync 2013 no tiene capacidad de carga y descarga de archivos, por lo que si tiene una implementación pura de Lync 2013 o un cliente de Lync 2013, no se pueden publicar archivos en un salón de chat del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5461b-166">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="5461b-167">En **Límite de actualización de participantes**, seleccione el límite de actualizaciones de participantes.</span><span class="sxs-lookup"><span data-stu-id="5461b-167">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="5461b-168">El servidor de chat persistente envía información de la lista (quién está conectado a un salón de chat) a todos los participantes hasta que el número de usuarios conectados alcanza este número.</span><span class="sxs-lookup"><span data-stu-id="5461b-168">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="5461b-169">De forma predeterminada, el número es 75.</span><span class="sxs-lookup"><span data-stu-id="5461b-169">By default, the number is 75.</span></span> <span data-ttu-id="5461b-170">Este límite indica el número máximo de participantes en un salón más allá del cual el servidor de chat persistente deja de enviar actualizaciones de lista a los clientes conectados sobre quién está presente en el salón.</span><span class="sxs-lookup"><span data-stu-id="5461b-170">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="5461b-p121">En **URL de administración de salón**, seleccione la dirección URL de administración de salón. Se trata de la dirección URL para una implementación de administración de salones basada en web. Si no necesita personalizar la administración de salones y simplemente utiliza la configuración predeterminada, deje esta opción en blanco.</span><span class="sxs-lookup"><span data-stu-id="5461b-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="5461b-174">Si desea personalizar la experiencia de creación de salas e incluir su flujo de trabajo específico, puede crear una solución de administración de salas personalizada con el kit de desarrollo de software (SDK) del servidor de chat persistente, hospedarla en algún lugar y colocar la dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="5461b-174">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="5461b-175">Esta dirección URL se envía al cliente de modo que, cuando un usuario intente ver o crear un salón, será dirigido a su solución personalizada de administración de salones.</span><span class="sxs-lookup"><span data-stu-id="5461b-175">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="5461b-176">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5461b-176">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

