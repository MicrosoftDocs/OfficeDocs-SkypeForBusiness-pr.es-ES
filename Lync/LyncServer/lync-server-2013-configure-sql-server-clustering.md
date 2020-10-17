---
title: 'Lync Server 2013: configurar la organización en clústeres de SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21fac13a22e2b2acf400ca154551a0705544644f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535217"
---
# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="00fcc-102">Configurar la organización en clústeres de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00fcc-102">Configure SQL Server clustering for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00fcc-103">_**Última modificación del tema:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="00fcc-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="00fcc-104">Microsoft Lync Server 2013 admite clústeres para SQL Server 2012 y SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="00fcc-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="00fcc-105">Para obtener más información sobre lo que se admite, consulte [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="00fcc-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="00fcc-106">Debe configurar y configurar el clúster de SQL Server antes de instalar e implementar la base de datos back-end y el servidor front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="00fcc-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="00fcc-107">Para conocer los procedimientos recomendados y las instrucciones de configuración de los clústeres de conmutación por error en SQL Server 2012, consulte <https://technet.microsoft.com/library/hh231721.aspx> .</span><span class="sxs-lookup"><span data-stu-id="00fcc-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="00fcc-108">Para clústeres de conmutación por error en SQL Server 2008, consulte <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .</span><span class="sxs-lookup"><span data-stu-id="00fcc-108">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="00fcc-109">Cuando instale SQL Server, instale también SQL Server Management Studio para administrar las ubicaciones de la base de datos y las ubicaciones de archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="00fcc-109">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="00fcc-110">SQL Server Management Studio se instala como componente adicional al instalar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00fcc-110">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="00fcc-111">Para instalar e implementar las bases de datos en el servidor basado en SQL Server, el usuario debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server en el que se vayan a instalar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="00fcc-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="00fcc-112">Si no es miembro del grupo sysadmins de SQL Server, deberá solicitar su incorporación en dicho grupo hasta que los archivos de base de datos se implementen.</span><span class="sxs-lookup"><span data-stu-id="00fcc-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="00fcc-113">Si no puede convertirse en miembro del grupo sysadmins, proporcione al administrador de bases de datos SQL Server la secuencia de comandos para configurar e implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="00fcc-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="00fcc-114">Para obtener información detallada sobre los permisos y derechos de usuario adecuados para realizar los procedimientos, vea <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="00fcc-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="00fcc-115">Para configurar clústeres SQL Server</span><span class="sxs-lookup"><span data-stu-id="00fcc-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="00fcc-116">Una vez completada la instalación y la configuración de la agrupación en clústeres de SQL Server, defina el almacén de SQL Server en Topology Builder mediante el nombre del clúster virtual de instancia de SQL Server (como se ha configurado en la configuración de clústeres de SQL Server) y el nombre de instancia de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00fcc-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="00fcc-117">A diferencia de lo que sucede con un solo servidor basado en SQL Server, usará el nombre de dominio completo (FQDN) del nodo virtual para un servidor en clúster basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00fcc-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00fcc-118">No es necesario configurar los nodos individuales del clúster de servidores de Windows para el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="00fcc-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="00fcc-119">Únicamente usará el nombre de clúster virtual de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00fcc-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="00fcc-120">Si usa el generador de topologías para implementar las bases de datos, debe ser miembro del grupo sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00fcc-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="00fcc-121">Si es miembro del grupo sysadmin de SQL Server, pero no tiene privilegios en el dominio (por ejemplo, un rol de administrador de bases de datos de SQL Server), tiene derechos para crear las bases de datos pero no para leer la información necesaria en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00fcc-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="00fcc-122">Para obtener más información sobre los derechos de usuario y los permisos necesarios para implementar Lync Server, vea [permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00fcc-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="00fcc-p108">Asegúrese de que los valores predeterminados de la carpeta de base de datos y la carpeta de archivos de registro se asignan correctamente a los discos compartidos en el clúster de SQL Server mediante SQL Server Management Studio. Se trata de un procedimiento necesario si se van a crear bases de datos con Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="00fcc-p108">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio. This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00fcc-125">Si no instaló SQL Server Management Studio, puede hacerlo ejecutando de nuevo la instalación de SQL Server y seleccionando a continuación la herramienta de administración como una característica agregada para la implementación existente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00fcc-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="00fcc-126">Instale las bases de datos para el servidor basado en SQL Server mediante el generador de topologías o los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00fcc-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="00fcc-127">Para usar el generador de topologías, use el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="00fcc-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="00fcc-128">Para usar los cmdlets de Windows PowerShell, consulte [instalación de bases de datos mediante el shell de administración de Lync Server en Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="00fcc-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="00fcc-129">Para crear bases de datos con el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="00fcc-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="00fcc-130">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="00fcc-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="00fcc-131">El siguiente procedimiento presupone que ha definido y configurado la topología en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="00fcc-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="00fcc-132">Para obtener más información sobre cómo definir la topología, consulte<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and Configuring the Topology in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="00fcc-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="00fcc-133">Para usar Topology Builder para publicar la topología y configurar la base de datos, debe iniciar sesión como usuario con los derechos de usuario y las pertenencias a grupo correctos.</span><span class="sxs-lookup"><span data-stu-id="00fcc-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="00fcc-134">Para obtener más información sobre los derechos obligatorios y las pertenencias a grupos, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="00fcc-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="00fcc-135">En el generador de topologías, cuando publique la topología, en la página **crear bases de datos** , haga clic en **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="00fcc-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="00fcc-p111">La página **Seleccionar la ubicación del archivo de base de datos** incluye dos opciones que determinan la forma en que se implementarán los archivos de base de datos en el clúster de SQL Server. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="00fcc-p111">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster. Select one of the following:</span></span>
    
      - <span data-ttu-id="00fcc-138">**Determinar automáticamente la ubicación del archivo de base de datos.**</span><span class="sxs-lookup"><span data-stu-id="00fcc-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="00fcc-139">Esta selección usa un algoritmo para determinar las ubicaciones del registro de la base de datos y el archivo de datos en función de la configuración de unidades en el servidor basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00fcc-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="00fcc-140">Los archivos se distribuirán de manera que se intente proporcionar un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="00fcc-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="00fcc-141">Usar valores predeterminados de instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00fcc-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="00fcc-142">Si selecciona esta opción, los archivos de datos y de registro se instalarán según la configuración de la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00fcc-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="00fcc-143">Después de la implementación de los archivos de base de datos en SQL Server, es posible que el administrador de bases de datos de SQL Server desee reubicar los archivos para optimizar el rendimiento de los requisitos de configuración de SQL Server en concreto.</span><span class="sxs-lookup"><span data-stu-id="00fcc-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="00fcc-144">Complete la publicación de la topología y confirme que no se produjeron errores durante la operación.</span><span class="sxs-lookup"><span data-stu-id="00fcc-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

