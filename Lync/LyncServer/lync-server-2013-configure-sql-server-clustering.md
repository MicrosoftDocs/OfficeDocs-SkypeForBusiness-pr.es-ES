---
title: 'Lync Server 2013: configurar la organización en clústeres de SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279c6581d0a56193c094c3dd7b9638fd74e2e60c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="d7e37-102">Configurar clústeres de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7e37-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7e37-103">_**Última modificación del tema:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="d7e37-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="d7e37-104">Microsoft Lync Server 2013 admite clústeres para SQL Server 2012 y SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="d7e37-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="d7e37-105">Para obtener más información sobre lo que se admite, vea [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="d7e37-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="d7e37-106">Debe configurar y configurar el clúster de SQL Server antes de instalar e implementar el servidor front-end Enterprise Edition y la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="d7e37-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="d7e37-107">Para ver los procedimientos recomendados y las instrucciones de configuración para el clúster de conmutación por <http://technet.microsoft.com/en-us/library/hh231721.aspx>error en SQL Server 2012, consulte.</span><span class="sxs-lookup"><span data-stu-id="d7e37-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="d7e37-108">Para el clúster de conmutación por error en SQL Server <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>2008, consulte.</span><span class="sxs-lookup"><span data-stu-id="d7e37-108">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="d7e37-p103">Al instalar SQL Server, es preciso instalar también SQL Server Management Studio para administrar las ubicaciones de la base de datos y de los archivos de registro. SQL Server Management Studio se instala como un componente opcional al instalar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7e37-p103">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d7e37-111">Para instalar e implementar las bases de datos en el servidor basado en SQL Server, debe ser miembro del grupo sysadmin de SQL Server para el servidor basado en SQL Server en el que va a instalar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d7e37-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="d7e37-112">Si no es miembro del grupo sysadmin de SQL Server, tendrá que solicitar que lo agregue al grupo hasta que se implementen los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d7e37-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="d7e37-113">Si no puede hacerse miembro del grupo sysadmin, debe proporcionar el administrador de la base de datos de SQL Server con el script para configurar e implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="d7e37-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="d7e37-114">Para obtener más información sobre los permisos y los derechos de usuario adecuados que necesita para realizar los procedimientos, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d7e37-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="d7e37-115">Para configurar la organización en clústeres de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7e37-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="d7e37-116">Una vez completada la instalación y la configuración de la organización por clústeres de SQL Server, defina el almacén de SQL Server en el generador de topología con el nombre del clúster virtual de instancias de SQL Server (configurado en la configuración de clústeres de SQL Server) y la instancia. nombre de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7e37-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="d7e37-117">Es diferente de un único servidor basado en SQL Server, se usa el nombre de dominio completo (FQDN) del nodo virtual para un servidor basado en SQL Server agrupado.</span><span class="sxs-lookup"><span data-stu-id="d7e37-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d7e37-118">Los nodos individuales del clúster de servidor de Windows no tienen que estar configurados para el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="d7e37-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="d7e37-119">Solo usará el nombre de clúster de SQL Server virtual.</span><span class="sxs-lookup"><span data-stu-id="d7e37-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="d7e37-120">Si usa la topología Builder para implementar sus bases de datos, debe ser miembro del grupo sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7e37-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="d7e37-121">Si es miembro del grupo sysadmin de SQL Server, pero no tiene privilegios en el dominio (por ejemplo, una función de administrador de base de datos de SQL Server), tendrá los derechos para crear las bases de datos pero no para leer la información necesaria en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7e37-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="d7e37-122">Para más información sobre los derechos de usuario y los permisos necesarios para implementar Lync Server, consulte [permisos de implementación para SQL Server en Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d7e37-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="d7e37-123">Asegúrese de que los valores predeterminados de la carpeta base de datos y archivos de registro están asignados correctamente a los discos compartidos en el clúster de SQL Server mediante SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d7e37-123">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio.</span></span> <span data-ttu-id="d7e37-124">Este es un procedimiento obligatorio si va a crear bases de datos con el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="d7e37-124">This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d7e37-125">Si no instaló SQL Server Management Studio, puede instalarlo si vuelve a ejecutar la instalación de SQL Server y, a continuación, selecciona la herramienta de administración como una característica agregada para la implementación existente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7e37-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="d7e37-126">Instale las bases de datos para el servidor basado en SQL Server con los cmdlets del generador de topología o de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7e37-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="d7e37-127">Para usar el generador de topología, use el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="d7e37-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="d7e37-128">Para usar los cmdlets de Windows PowerShell, vea [instalación de bases de datos con el shell de administración de Lync Server en Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="d7e37-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="d7e37-129">Para crear bases de datos con el generador de topología</span><span class="sxs-lookup"><span data-stu-id="d7e37-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="d7e37-130">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d7e37-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d7e37-131">En el procedimiento siguiente se supone que ha definido y configurado su topología en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="d7e37-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="d7e37-132">Para obtener más información sobre cómo definir su topología, consulte<A href="lync-server-2013-defining-and-configuring-the-topology.md">definir y configurar la topología en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d7e37-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="d7e37-133">Para usar el generador de topología para publicar la topología y configurar la base de datos, debe iniciar sesión como usuario con los derechos de usuario y pertenencias a grupos correctos.</span><span class="sxs-lookup"><span data-stu-id="d7e37-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="d7e37-134">Para obtener más información sobre los derechos obligatorios y la pertenencia a grupos, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d7e37-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="d7e37-135">En el generador de topologías, a medida que publique la topología, en la página **crear bases de datos** , haga clic en **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="d7e37-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="d7e37-136">La página **Seleccionar ubicación de archivo de base de datos** tiene dos opciones que determinan cómo se implementarán los archivos de base de datos en el clúster de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7e37-136">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster.</span></span> <span data-ttu-id="d7e37-137">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d7e37-137">Select one of the following:</span></span>
    
      - <span data-ttu-id="d7e37-138">**Determinar automáticamente la ubicación del archivo de base de datos.**</span><span class="sxs-lookup"><span data-stu-id="d7e37-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="d7e37-139">Esta selección usa un algoritmo para determinar el registro de la base de datos y las ubicaciones del archivo de datos en función de la configuración del servidor basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7e37-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="d7e37-140">Los archivos se distribuirán de manera tal que intenten proporcionar un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="d7e37-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="d7e37-141">Use los valores predeterminados de instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7e37-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="d7e37-142">Al seleccionar esta opción se instalarán los archivos de registro y de datos de acuerdo con la configuración de la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7e37-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="d7e37-143">Después de implementar los archivos de base de datos en SQL Server, es posible que el administrador de la base de datos de SQL Server desee reubicar los archivos para optimizar el rendimiento de los requisitos de configuración de SQL Server concretos.</span><span class="sxs-lookup"><span data-stu-id="d7e37-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="d7e37-144">Complete la publicación de la topología y confirme que no hubo errores durante la operación.</span><span class="sxs-lookup"><span data-stu-id="d7e37-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

