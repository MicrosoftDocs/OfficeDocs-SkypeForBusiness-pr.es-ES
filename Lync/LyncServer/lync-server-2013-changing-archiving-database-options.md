---
title: 'Lync Server 2013: cambiar las opciones de la base de datos de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a98c2efc0dc956a6b8c33f2fcf065f629e5e57d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="ec8b9-102">Cambiar las opciones de base de datos de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec8b9-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec8b9-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ec8b9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ec8b9-104">Si implementa el archivado con almacenamiento de SQL Server para archivar el almacenamiento de cualquiera de los usuarios, puede realizar los siguientes cambios de almacenamiento en la base de datos:</span><span class="sxs-lookup"><span data-stu-id="ec8b9-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="ec8b9-105">Use una base de datos de SQL Server diferente para archivar almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="ec8b9-106">Esto incluye la base de datos de archivado principal y cualquier base de datos que use para el reflejo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="ec8b9-107">Cambie a la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="ec8b9-108">Si todos los usuarios están alojados en los servidores de Exchange 2013 y desea usar el almacenamiento de Microsoft Exchange para todos los usuarios de su implementación, debe quitar las bases de datos del almacén de SQL Server de su topología.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="ec8b9-109">Para realizar alguno de estos cambios, debe ejecutar el generador de topología, realizar los cambios y, a continuación, volver a publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="ec8b9-110">Puede usar el generador de topología para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="ec8b9-111">No especifique el **archivado de SQL Server Store** ni habilitar la información de reflejo de la **tienda de SQL Server** , a menos que tenga usuarios de Lync que no estén alojados en servidores de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="ec8b9-112">Cambiar la opción de base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="ec8b9-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="ec8b9-113">En un equipo que ejecute Lync Server 2013 o en el que estén instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).</span><span class="sxs-lookup"><span data-stu-id="ec8b9-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ec8b9-114">Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para agregar un componente a la topología, debe usar una cuenta que sea miembro del grupo de <STRONG>administradores de dominio</STRONG> y la de <STRONG>RTCUniversalSer Grupo verAdmins</STRONG> y que tiene permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Lync Server 2013 (es decir, el generador de topología puede configurar las listas de control de acceso discrecional obligatorias ( DACL) o una cuenta con derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="ec8b9-115">Iniciar el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="ec8b9-116">En el árbol de consola, explore el grupo de servidores front-end en los que ha implementado el servidor de archivado y, luego, haga clic en el nombre del grupo de servidores front-end al que quiere modificar las opciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="ec8b9-117">En el menú **Acción**, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="ec8b9-118">En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="ec8b9-119">Desplácese hacia abajo hasta **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="ec8b9-120">En **Archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec8b9-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="ec8b9-121">Para cambiar a otro almacén de SQL Server existente, en **Almacén SQL Server de archivado**, en el cuadro de desplegable, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec8b9-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="ec8b9-122">Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="ec8b9-123">Para especificar un nuevo almacén de SQL Server, haga clic en **Nuevo** y, en el cuadro de diálogo **Definir un nuevo almacén de SQL Server**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec8b9-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="ec8b9-124">Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="ec8b9-125">Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec8b9-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="ec8b9-126">En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="ec8b9-127">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="ec8b9-128">Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="ec8b9-129">Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, luego, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec8b9-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="ec8b9-130">Para usar un almacén de SQL Server existente para la creación de reflejo, en el cuadro de lista desplegable archivado reflejado de **SQL Server** , haga clic en el nombre del almacén de SQL Server que desea usar para el reflejo.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="ec8b9-131">Para especificar un nuevo almacén de SQL Server para la creación de reflejo, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ec8b9-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="ec8b9-132">En **FQDN de SQL Server**, especifique el nombre completo del servidor SQL Server en el que desea crear el nuevo almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="ec8b9-133">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="ec8b9-134">Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="ec8b9-135">Si habilita el reflejo de SQL Server y quiere agregar o cambiar un testigo de reflejo de SQL Server (una tercera, instancia independiente de SQL Server que puede detectar el estado del servidor SQL Server principal y de las instancias reflejadas), seleccione **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** y, después, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ec8b9-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="ec8b9-136">En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo testigo de reflejo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="ec8b9-137">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="ec8b9-138">Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="ec8b9-139">Para cambiar a la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange 2013 (si todos los usuarios de su implementación están alojados en los servidores de Exchange 2013), elimine toda la información para archivar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ec8b9-140">Si tiene usuarios de Lync que no estén alojados en servidores de Exchange 2013, no elimine la información de la tienda SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="ec8b9-141">Para guardar la configuración, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ec8b9-142">Los cambios que haga en el generador de topología no se aplicarán hasta que publique la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="ec8b9-143">Para obtener más información, vea <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">publicación de la topología actualizada para agregar bases de datos de archivado en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="ec8b9-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

