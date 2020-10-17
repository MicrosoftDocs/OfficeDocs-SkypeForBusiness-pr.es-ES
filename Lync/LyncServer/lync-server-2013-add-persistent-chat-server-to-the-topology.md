---
title: 'Lync Server 2013: agregar un servidor de chat persistente a la topología'
description: 'Lync Server 2013: agregar un servidor de chat persistente a la topología.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0321978ce4a0c7381cf2915030267645931f572b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572436"
---
# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="5dc01-103">Agregar un servidor de chat persistente a la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5dc01-103">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dc01-104">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5dc01-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5dc01-105">Debe incorporar Lync Server 2013, la compatibilidad con el servidor de chat persistente en su topología antes de configurar la implementación para que admita el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5dc01-105">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="5dc01-106">La información de este tema describe cómo usar el generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología existente.</span><span class="sxs-lookup"><span data-stu-id="5dc01-106">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="5dc01-107">Para agregar un servidor de chat persistente a una topología</span><span class="sxs-lookup"><span data-stu-id="5dc01-107">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="5dc01-108">Realice los siguientes pasos para instalar un único grupo de servidores de chat persistente sin una configuración de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="5dc01-108">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="5dc01-109">Para configurar un grupo de servidores de chat persistente estirado para alta disponibilidad y recuperación ante desastres, consulte [Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="5dc01-109">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="5dc01-110">Para implementar varios grupos de servidores de chat persistente, repita el mismo proceso para cada grupo.</span><span class="sxs-lookup"><span data-stu-id="5dc01-110">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="5dc01-111">En un equipo que ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).</span><span class="sxs-lookup"><span data-stu-id="5dc01-111">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5dc01-112">Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, necesaria para instalar un servidor de Lync Server 2013. debe usar una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, lectura, escritura y modificación) en el almacén de archivos que va a usar para el almacén de archivos del servidor de chat persistente (es decir, el generador de topologías puede configurar las DACL necesarias) o una cuenta con derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="5dc01-112">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="5dc01-113">Inicie el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="5dc01-113">Start Topology Builder.</span></span>

3.  <span data-ttu-id="5dc01-114">En el árbol de la consola, vaya al nodo **grupos de chat persistentes** y expándalo para seleccionar un grupo de servidores de chat persistente, o haga clic con el botón secundario en el nodo y seleccione **nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="5dc01-114">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="5dc01-115">Deberá definir el nombre de dominio completo (FQDN) del grupo, e indicar si el grupo será la implementación de un grupo de un único servidor o de un grupo de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="5dc01-115">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="5dc01-116">Puede elegir un **Grupo de varios PC** o **Grupo de un PC**.</span><span class="sxs-lookup"><span data-stu-id="5dc01-116">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="5dc01-117">Elija el primero si tiene previsto tener más de un servidor de servidor de chat persistente en su grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5dc01-117">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="5dc01-118">Realice esta elección ahora, o luego, debido a que después de crear un solo grupo de PC no podrá agregar servidores adicionales más adelante.</span><span class="sxs-lookup"><span data-stu-id="5dc01-118">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="5dc01-119">Si elige un grupo de varios equipos, escriba los nombres de los servidores front-end de servidor de chat persistente individuales que componen el grupo.</span><span class="sxs-lookup"><span data-stu-id="5dc01-119">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5dc01-120">Si se está instalando el rol de servidor de chat persistente en un servidor de Lync Server 2013 &nbsp; Standard Edition, el FQDN debe coincidir con el FQDN del servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5dc01-120">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="5dc01-121">Definir un **nombre para mostrar** sencillo para el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5dc01-121">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="5dc01-122">Los clientes personalizados pueden usar el nombre para mostrar, especialmente cuando hay varios grupos de servidores de chat persistente, para diferenciar las salas.</span><span class="sxs-lookup"><span data-stu-id="5dc01-122">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="5dc01-123">Definir el puerto usado por el servidor de chat persistente para comunicarse con los servidores front-end de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5dc01-123">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="5dc01-124">El puerto predeterminado es 5041.</span><span class="sxs-lookup"><span data-stu-id="5dc01-124">The default port is 5041.</span></span>

6.  <span data-ttu-id="5dc01-125">Si su organización requiere compatibilidad con el cumplimiento, seleccione la casilla **Habilitar cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="5dc01-125">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="5dc01-126">Si se elige, el servicio de cumplimiento del servidor de chat persistente se instala en el mismo equipo que el servidor front-end del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5dc01-126">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="5dc01-127">Más adelante, se le pedirá que seleccione un servidor back-end de SQL Server para el cumplimiento del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5dc01-127">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="5dc01-128">Asigne la afinidad de sitios para el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5dc01-128">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="5dc01-129">Active la casilla de verificación **usar este grupo de \<SiteName\> servidores como predeterminado para el sitio** o **use este grupo de servidores como predeterminado para todos los sitios** para designar este grupo de servidores de chat persistente como grupo predeterminado para el sitio actual o todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="5dc01-129">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="5dc01-130">Cuando se usa el cliente de Lync 2013 para crear y administrar salones, la experiencia de creación y administración de la sala usa el grupo de servidores predeterminado asociado al sitio del usuario, de modo que pueda redirigir las operaciones de creación y administración de salas a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="5dc01-130">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="5dc01-131">Esto solo se aplica cuando se implementan varios grupos de servidores de chat persistente y se desea usar las características de creación y administración de salas del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5dc01-131">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5dc01-132">Puede personalizar las características de creación y administración de salas con el kit de desarrollo de software (SDK) del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5dc01-132">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="5dc01-133">Para obtener más información sobre cómo configurar las bases de datos de copia de seguridad de SQL Server para la recuperación ante desastres, consulte <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="5dc01-133">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="5dc01-134">Defina el **almacén de SQL para el back-end del servidor de chat persistente (donde se almacena el contenido del salón de chat)** mediante uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="5dc01-134">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="5dc01-135">Para usar una base de datos de SQL Server existente, en la lista desplegable, haga clic en el nombre de la base de datos de SQL Server que desee usar.</span><span class="sxs-lookup"><span data-stu-id="5dc01-135">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="5dc01-136">Para especificar una nueva base de datos de SQL Server, haga clic en **nuevo**y, en **definir nuevo almacén de SQL**, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5dc01-136">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="5dc01-137">En **FQDN de SQL Server**, especifique el FQDN del servidor SQL Server en el que desea crear la nueva base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5dc01-137">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="5dc01-138">Puede seleccionar **Instancia predeterminada** para utilizar la instancia predeterminada, o bien, para especificar una instancia diferente, seleccione **Instancia con nombre** y, a continuación, especifique la instancia que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="5dc01-138">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="5dc01-139">Defina la base de datos de cumplimiento de SQL Server si ha habilitado el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5dc01-139">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5dc01-140">Para obtener más información sobre cómo configurar reflejos de SQL Server para alta disponibilidad de la base de datos del servidor de chat persistente y la base de datos de cumplimiento del servidor de chat persistente, vea <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="5dc01-140">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="5dc01-141">Defina el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="5dc01-141">Define the file store.</span></span> <span data-ttu-id="5dc01-142">Un almacén de archivos es una carpeta en la que se almacena una copia de cualquier archivo cargado al repositorio de archivos, por ejemplo, el almacenamiento de datos adjuntos de archivos publicados en una de chat.</span><span class="sxs-lookup"><span data-stu-id="5dc01-142">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="5dc01-143">En el caso de una topología de servidor de chat persistente de varios servidores, debe ser una ruta de acceso de Convención de nomenclatura universal (UNC); para una topología de servidor de chat persistente de un solo servidor, puede ser una ruta de acceso de archivo local.</span><span class="sxs-lookup"><span data-stu-id="5dc01-143">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="5dc01-144">Para utilizar un almacén de archivos existente, realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="5dc01-144">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="5dc01-145">En el **FQDN del servidor de archivos**, especifique el FQDN del almacén de archivos en el que desee crear el nuevo almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="5dc01-145">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="5dc01-146">En **Recurso compartido de archivos**, especifique el almacén de archivos que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="5dc01-146">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5dc01-147">Puede definir el almacén de archivos en Topology Builder antes de crear el almacén de archivos, pero debe crear el almacén de archivos en la ubicación definida que defina antes de publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="5dc01-147">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="5dc01-148">Seleccione el grupo de servidores front-end que se usará como próximo salto para este grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5dc01-148">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="5dc01-149">Se trata del grupo de servidores front-end que podrá enrutar las solicitudes del servidor de chat persistente a este grupo.</span><span class="sxs-lookup"><span data-stu-id="5dc01-149">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="5dc01-150">Para guardar la configuración, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5dc01-150">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="5dc01-151">El grupo de servidores de chat persistente aparece en Topology Builder junto con la configuración específica del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="5dc01-151">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="5dc01-152">Para publicar ahora la topología actualizada a la que tiene el servidor de chat persistente, vea [Publish The Updated Topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="5dc01-152">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5dc01-153">Con el generador de topología ya abierto, puede continuar con el paso 3 en <A href="lync-server-2013-publish-the-updated-topology.md">publicar la topología actualizada en Lync Server 2013</A> para empezar a publicar su topología actualizada.</span><span class="sxs-lookup"><span data-stu-id="5dc01-153">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

