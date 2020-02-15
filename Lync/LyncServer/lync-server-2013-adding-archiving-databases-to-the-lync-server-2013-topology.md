---
title: 'Lync Server 2013: adición de bases de datos de archivado a la topología de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e73fe49aaf3a5b90a23bcfd6b99c9a5bb4476513
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="0eec0-102">Adición de bases de datos de archivado a la topología de 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="0eec0-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0eec0-103">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="0eec0-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="0eec0-104">Debe incorporar el archivado a la topología para poder configurar la implementación a fin de admitir el archivado.</span><span class="sxs-lookup"><span data-stu-id="0eec0-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="0eec0-105">La información de este tema explica cómo usar el generador de topologías para agregar archivado a la topología existente.</span><span class="sxs-lookup"><span data-stu-id="0eec0-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0eec0-106">Si desea usar la integración de Microsoft Exchange para almacenar los datos y los archivos de archivado en servidores de Exchange 2013 para todos los usuarios de la implementación, no especifique el <STRONG>almacén de SQL Server de archivado</STRONG> ni use la información de <STRONG>reflejo de almacén de SQL Server</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="0eec0-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="0eec0-107">Para agregar la compatibilidad de base de datos de archivado a la topología</span><span class="sxs-lookup"><span data-stu-id="0eec0-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="0eec0-108">En un equipo que ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).</span><span class="sxs-lookup"><span data-stu-id="0eec0-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0eec0-109">Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, que es necesaria para agregar un servidor a la topología. debe usar una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Lync Server 2013 (es decir, el generador de topología puede configurar la lista de control de acceso discrecional (DACL) requerida. o una cuenta con derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="0eec0-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="0eec0-110">Inicie el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="0eec0-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="0eec0-111">En el árbol de consola, vaya al grupo de servidores front-end en el que desee implementar el archivado y haga clic en el nombre de dicho grupo.</span><span class="sxs-lookup"><span data-stu-id="0eec0-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="0eec0-112">En el menú **Acción**, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0eec0-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="0eec0-113">En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="0eec0-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="0eec0-114">Desplácese a  **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="0eec0-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="0eec0-115">Seleccione la casilla **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="0eec0-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="0eec0-116">En **almacén de SQL Server de archivado,** realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0eec0-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="0eec0-117">Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.</span><span class="sxs-lookup"><span data-stu-id="0eec0-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="0eec0-118">Si todos los usuarios están hospedados en Microsoft Exchange Server 2013 o posterior, puede archivar las comunicaciones de Lync para todos los usuarios de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0eec0-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="0eec0-119">En este caso, no es necesario configurar el almacén de archivado de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0eec0-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="0eec0-120">Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0eec0-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="0eec0-121">En **FQDN de SQL Server**, especifique el nombre de dominio completo (FQDN) del servidor en el que desea crear el nuevo almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0eec0-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="0eec0-122">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  \*\*Instancia con nombre \*\* y especifique la instancia que desee usar.</span><span class="sxs-lookup"><span data-stu-id="0eec0-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="0eec0-123">Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="0eec0-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="0eec0-124">Si desea usar la creación de reflejos del almacén de SQL Server, seleccione **Habilitar creación de reflejos del almacén de SQL Server**y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0eec0-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="0eec0-125">Para usar un almacén de SQL Server existente para la creación de reflejos, en el cuadro de lista desplegable **archivado de reflejo de almacén de SQL Server** , haga clic en el nombre del almacén de SQL Server que desee usar para la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="0eec0-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="0eec0-126">Para especificar un nuevo almacén de SQL Server para la creación de reflejos, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0eec0-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="0eec0-127">En **FQDN de SQL Server**, especifique el nombre de dominio completo (FQDN) del SQL Server en el que desea crear el nuevo almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0eec0-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="0eec0-128">Haga clic en **Instancia predeterminada** para utilizar la instancia predeterminada o, para especificar una instancia diferente, haga clic en **Instancia denominada** y, a continuación, haga clic en la instancia que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="0eec0-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="0eec0-129">Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="0eec0-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="0eec0-130">Si habilita la creación de reflejos de SQL Server y desea incluir un testigo de creación de reflejos de SQL Server (una tercera y distinta instancia de SQL Server que pueda detectar el estado del servidor SQL Server principal y las instancias reflejadas), active la casilla **usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación por error automática** y, a continuación, siga uno de estos procedimientos</span><span class="sxs-lookup"><span data-stu-id="0eec0-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="0eec0-131">En **FQDN de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo testigo de creación de reflejos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0eec0-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="0eec0-132">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  \*\*Instancia con nombre \*\* y especifique la instancia que desee usar para el testigo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="0eec0-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="0eec0-133">Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="0eec0-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="0eec0-134">Para guardar la configuración, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0eec0-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

