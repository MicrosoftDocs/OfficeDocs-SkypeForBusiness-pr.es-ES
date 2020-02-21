---
title: 'Lync Server 2013: cambiar las opciones de base de datos de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a820ca891ceb8196f8b4e0d2e023799f36e9e9ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="ac03c-102">Cambiar las opciones de base de datos de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac03c-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac03c-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ac03c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ac03c-104">Si implementa el archivado con el almacenamiento de SQL Server para el almacenamiento de archivado para cualquiera de sus usuarios, puede realizar los siguientes cambios en el almacenamiento de la base de datos:</span><span class="sxs-lookup"><span data-stu-id="ac03c-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="ac03c-105">Use una base de datos de SQL Server diferente para el almacenamiento de archivado.</span><span class="sxs-lookup"><span data-stu-id="ac03c-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="ac03c-106">Esto incluye la base de datos de archivado principal y cualquier base de datos que use para la creación de reflejo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac03c-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="ac03c-107">Cambie a la integración de Microsoft Exchange para almacenar los datos y archivos de archivado en servidores de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ac03c-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="ac03c-108">Si todos los usuarios están hospedados en los servidores de Exchange 2013 y desea usar el almacenamiento de Microsoft Exchange para todos los usuarios de la implementación, debe quitar las bases de datos de almacén de SQL Server de la topología.</span><span class="sxs-lookup"><span data-stu-id="ac03c-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="ac03c-109">Para realizar cualquiera de estos cambios, debe ejecutar el generador de topologías, realizar los cambios y, a continuación, volver a publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="ac03c-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="ac03c-110">Puede usar el generador de topologías para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ac03c-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="ac03c-111">No especifique el **almacén de SQL Server de archivado** ni habilite la información de **reflejo del almacén de SQL Server** , a menos que tenga usuarios de Lync que no estén hospedados en servidores de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ac03c-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="ac03c-112">Cambiar la opción de la base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="ac03c-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="ac03c-113">En un equipo que ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).</span><span class="sxs-lookup"><span data-stu-id="ac03c-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac03c-114">Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, que es necesaria para agregar un componente a la topología. debe usar una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que usa para el almacén de archivos de Lync Server 2013 (es decir, el generador de topologías puede configurar las listas de control de acceso discrecional necesarias ( DACL) o una cuenta con derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="ac03c-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="ac03c-115">Inicie el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="ac03c-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="ac03c-116">En el árbol de consola, explore el grupo de servidores front-end en los que ha implementado el servidor de archivado y, a continuación, haga clic en el nombre del grupo de servidores front-end al que quiere modificar las opciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac03c-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="ac03c-117">En el menú **Acción**, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ac03c-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="ac03c-118">En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="ac03c-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="ac03c-119">Desplácese hacia abajo hasta **Servidor de archivado**.</span><span class="sxs-lookup"><span data-stu-id="ac03c-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="ac03c-120">En **Servidor de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac03c-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="ac03c-121">Para cambiar a un almacén de SQL Server existente diferente, en  **Almacén SQL Server de archivado**, en el cuadro de desplegable, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac03c-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="ac03c-122">Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.</span><span class="sxs-lookup"><span data-stu-id="ac03c-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="ac03c-123">Para especificar un nuevo almacén de SQL Server, haga clic en **Nuevo** y en el cuadro de diálogo **Definir un nuevo almacén de SQL Server** lleve a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac03c-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="ac03c-124">Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.</span><span class="sxs-lookup"><span data-stu-id="ac03c-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="ac03c-125">Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac03c-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="ac03c-126">En **FQDN de SQL Server**, especifique el nombre de dominio completo (FQDN) del servidor en el que desea crear el nuevo almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac03c-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="ac03c-127">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  \*\*Instancia con nombre \*\* y especifique la instancia que desee usar.</span><span class="sxs-lookup"><span data-stu-id="ac03c-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="ac03c-128">Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="ac03c-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="ac03c-129">Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac03c-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="ac03c-130">Para usar un almacén de SQL Server existente para la creación de reflejos, en el cuadro de lista desplegable **archivado de reflejo de almacén de SQL Server** , haga clic en el nombre del almacén de SQL Server que desee usar para la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="ac03c-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="ac03c-131">Para especificar un nuevo almacén de SQL Server para la creación de reflejos, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ac03c-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="ac03c-132">En **FQDN de SQL Server**, especifique el nombre de dominio completo (FQDN) del SQL Server en el que desea crear el nuevo almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac03c-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="ac03c-133">Haga clic en **Instancia predeterminada** para utilizar la instancia predeterminada o, para especificar una instancia diferente, haga clic en **Instancia denominada** y, a continuación, haga clic en la instancia que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="ac03c-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="ac03c-134">Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="ac03c-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="ac03c-135">Si habilita la creación de reflejos de SQL Server y desea agregar o cambiar un testigo de creación de reflejos de SQL Server (una tercera y distinta instancia de SQL Server que pueda detectar el estado del servidor SQL Server principal y de las instancias reflejadas), active la casilla **usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación automática por error**</span><span class="sxs-lookup"><span data-stu-id="ac03c-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="ac03c-136">En **FQDN de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo testigo de creación de reflejos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac03c-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="ac03c-137">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  \*\*Instancia con nombre \*\* y especifique la instancia que desee usar para el testigo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="ac03c-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="ac03c-138">Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="ac03c-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="ac03c-139">Para cambiar a la integración de Microsoft Exchange para almacenar los datos y los archivos de archivado en servidores de Exchange 2013 (si todos los usuarios de la implementación están alojados en los servidores de Exchange 2013), elimine toda la información de las bases de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="ac03c-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ac03c-140">Si tiene usuarios de Lync que no están hospedados en servidores de Exchange 2013, no elimine la información del almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac03c-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="ac03c-141">Para guardar la configuración, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ac03c-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ac03c-142">Los cambios que realice en el generador de topologías no surtirán efecto hasta que publique la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="ac03c-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="ac03c-143">Para obtener más información, consulte <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">publicación de la topología actualizada para agregar bases de datos de archivado en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="ac03c-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

