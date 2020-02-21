---
title: 'Lync Server 2013: instalación de bases de datos mediante el shell de administración de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 443f353a43c2fdfd2f9fc8c7ce1a1b20c11a4a84
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="abe90-102">Instalación de bases de datos mediante el shell de administración de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe90-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abe90-103">_**Última modificación del tema:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="abe90-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="abe90-104">La separación de roles y responsabilidades entre los administradores de servidor y los administradores SQL Server puede ocasionar retrasos en la implementación.</span><span class="sxs-lookup"><span data-stu-id="abe90-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="abe90-105">Lync Server 2013 usa el control de acceso basado en roles (RBAC) para mitigar estas dificultades.</span><span class="sxs-lookup"><span data-stu-id="abe90-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="abe90-106">En algunos casos, el administrador de SQL Server tiene que administrar la instalación de bases de datos en el servidor de SQL Server fuera de RBAC.</span><span class="sxs-lookup"><span data-stu-id="abe90-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="abe90-107">El shell de administración de Lync Server 2013 proporciona un método para que el administrador de SQL Server ejecute cmdlets de Windows PowerShell diseñados para configurar las bases de datos con los archivos de registro y datos correctos.</span><span class="sxs-lookup"><span data-stu-id="abe90-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="abe90-108">Para obtener información detallada, consulte [permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="abe90-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="abe90-109">El siguiente procedimiento presupone que, al menos, Lync Server 2013 OCSCore. msi, SQL Server Native Client (SQLNCLI. msi) objetos de administración de Microsoft SQL Server 2012, tipos CLR para Microsoft SQL Server 2012 y Microsoft SQL Server 2012 ADOMD.NET están instalados.</span><span class="sxs-lookup"><span data-stu-id="abe90-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="abe90-110">El archivo OCSCore.msi está ubicado en el medio de instalación en el directorio \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="abe90-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="abe90-111">Los componentes restantes se encuentran en \Setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="abe90-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="abe90-112">Además, la preparación de Active Directory para Lync Server 2013 se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="abe90-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="abe90-113">**Install-CsDatabase** es el cmdlet de Windows PowerShell que se usa para instalar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="abe90-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="abe90-114">El cmdlet **Install-CsDatabase** tiene una gran cantidad de parámetros, aquí solo se tratan algunos.</span><span class="sxs-lookup"><span data-stu-id="abe90-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="abe90-115">Para obtener más información sobre los parámetros posibles, consulte la documentación del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abe90-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="abe90-116">Para evitar problemas de rendimiento y de posibles tiempos de espera, debe usar siempre nombres de dominio completos (FQDN) cuando hace referencia a servidores de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abe90-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="abe90-117">Evite usar referencias de solo nombre de host.</span><span class="sxs-lookup"><span data-stu-id="abe90-117">Avoid using host name-only references.</span></span> <span data-ttu-id="abe90-118">Por ejemplo, use sqlbe01.contoso.net, pero evite usar SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="abe90-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="abe90-119">Para instalar bases de datos, **install-CsDatabase** usa tres métodos principales para colocar las bases de datos en el servidor preparado de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="abe90-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="abe90-120">Ejecute **Install-CsDatabase** sin DatabasePaths o UseDefaultSqlPath.</span><span class="sxs-lookup"><span data-stu-id="abe90-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="abe90-121">El cmdlet usa un algoritmo integrado para determinar la mejor posición para los archivos de datos y registros.</span><span class="sxs-lookup"><span data-stu-id="abe90-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="abe90-122">El algoritmo solo funciona para implementaciones de SQL Server independientes.</span><span class="sxs-lookup"><span data-stu-id="abe90-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="abe90-123">Ejecute **Install-CsDatabase** con los parámetros DatabasePaths.</span><span class="sxs-lookup"><span data-stu-id="abe90-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="abe90-124">El algoritmo integrado para optimizar las ubicaciones de archivos de datos y registros no se usa si el parámetro DatabasePaths está definido.</span><span class="sxs-lookup"><span data-stu-id="abe90-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="abe90-125">El uso de este parámetro permite definir las ubicaciones donde se implementarán archivos de datos y registros.</span><span class="sxs-lookup"><span data-stu-id="abe90-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="abe90-126">Ejecute **Install-CsDatabase** con UseDefaultSqlPaths.</span><span class="sxs-lookup"><span data-stu-id="abe90-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="abe90-127">Esta opción no usa el algoritmo integrado para optimizar las ubicaciones de archivos de datos y registros.</span><span class="sxs-lookup"><span data-stu-id="abe90-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="abe90-128">Los archivos de datos y registros se implementan según los valores predeterminados establecidos por el administrador de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abe90-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="abe90-129">Estas rutas de acceso se suelen establecer para la administración automática de archivos de registro y de datos en SQL Server por anticipado y no están asociadas con la configuración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abe90-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="abe90-130">El parámetro DatabasePathMap también se puede usar para especificar explícitamente una ubicación para cada base de datos y su archivo de registro respectivo.</span><span class="sxs-lookup"><span data-stu-id="abe90-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="abe90-131">Para usar los cmdlets de Windows PowerShell para configurar el almacén de administración central de SQL Server</span><span class="sxs-lookup"><span data-stu-id="abe90-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="abe90-132">Inicie sesión en cualquier equipo con credenciales administrativas para la creación de bases de datos en el servidor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abe90-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="abe90-133">Para obtener información detallada, consulte [permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="abe90-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="abe90-134">Abra el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abe90-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="abe90-135">Si no ha ajustado la Directiva de ejecución de Windows PowerShell, debe ajustar la Directiva para permitir que se ejecuten los scripts de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="abe90-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="abe90-136">Para obtener más información, consulte "examen de la Directiva de [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093)ejecución" en.</span><span class="sxs-lookup"><span data-stu-id="abe90-136">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="abe90-137">Use el cmdlet **install-CsDatabase** para instalar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="abe90-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="abe90-138">El parámetro Report es opcional pero útil si está documentando el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="abe90-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="abe90-139">**Install-CsDatabase – DatabasePaths** puede usar hasta seis parámetros PATH, cada uno de los cuales define las rutas de acceso de las unidades como se define en datos de SQL Server y ubicación del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="abe90-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="abe90-140">Mediante las reglas lógicas de la configuración de la base de datos en Lync Server 2013, las unidades se redistribuyen en cubos de dos, cuatro o seis.</span><span class="sxs-lookup"><span data-stu-id="abe90-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="abe90-141">En función de la configuración de SQL Server y del número de cubos, deberá proporcionar dos rutas, cuatro rutas o seis rutas.</span><span class="sxs-lookup"><span data-stu-id="abe90-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="abe90-142">Si tiene tres unidades, se da prioridad al registro y los archivos de datos se distribuyen después.</span><span class="sxs-lookup"><span data-stu-id="abe90-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="abe90-143">Un ejemplo de un servidor basado en SQL Server configurado con seis unidades:</span><span class="sxs-lookup"><span data-stu-id="abe90-143">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="abe90-144">Una vez finalizada la instalación de la base de datos, puede cerrar el shell de administración de Lync Server 2013 o continuar con la instalación de las bases de datos configuradas de Lync Server 2013 en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="abe90-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="abe90-145">Para usar los cmdlets de Windows PowerShell con el fin de configurar las bases de datos configuradas de la topología de SQL Server</span><span class="sxs-lookup"><span data-stu-id="abe90-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="abe90-146">Para instalar las bases de datos configuradas del generador de topologías para Lync Server 2013, el administrador de Lync Server 2013 debe publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="abe90-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="abe90-147">Para obtener más información, consulte [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="abe90-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="abe90-148">Inicie sesión en cualquier equipo con credenciales administrativas para la creación de bases de datos en el servidor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abe90-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="abe90-149">Vea el tema [sobre los permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="abe90-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="abe90-150">Para poder configurar las bases de datos basadas en SQL Server, asegúrese de que la cuenta de administrador de SQL Server que se usa para ejecutar los pasos descritos aquí también es miembro del grupo sysadmins (o equivalente) en el servidor que ejecuta SQL Server y que mantiene la administración central. Rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="abe90-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="abe90-151">Esto es especialmente importante para comprobar si hay otros grupos de servidores de Lync Server 2013 que requieran la instalación o configuración de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abe90-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="abe90-152">Por ejemplo, si va a implementar un segundo grupo de servidores (pool02), pero el rol de servidor de administración central se mantiene mediante grupo01.</span><span class="sxs-lookup"><span data-stu-id="abe90-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="abe90-153">El grupo sysadmin de SQL Server (o equivalente) debe tener permisos en ambas bases de datos basadas en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abe90-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="abe90-154">Abra el shell de administración de Lync Server 2013, si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="abe90-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="abe90-155">Use el cmdlet **install-CsDatabase** para instalar las bases de datos configuradas del generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="abe90-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="abe90-156">El parámetro Report es opcional pero útil si está documentando el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="abe90-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="abe90-157">Cuando finalice la instalación de la base de datos, cierre Shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abe90-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="abe90-158">Para usar los cmdlets de Windows PowerShell para configurar la topología de SQL Server con el parámetro DatabasePathMap</span><span class="sxs-lookup"><span data-stu-id="abe90-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="abe90-159">Para instalar bases de datos para Lync Server 2013, el administrador de Lync Server debe crear las rutas de acceso e implementar los archivos de base de datos y de registro de acuerdo con un conjunto de reglas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="abe90-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="abe90-160">Inicie sesión en cualquier equipo con credenciales administrativas para la creación de bases de datos en el servidor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abe90-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="abe90-161">Vea el tema [sobre los permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="abe90-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="abe90-162">Para poder configurar las bases de datos basadas en SQL Server, asegúrese de que la cuenta de administrador de SQL Server que se usa para ejecutar los pasos descritos aquí también es miembro del grupo sysadmins (o equivalente) en el servidor que ejecuta SQL Server y que mantiene la administración central. Rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="abe90-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="abe90-163">Esto es especialmente importante para comprobar si hay otros grupos de servidores de Lync Server que requieran la instalación o configuración de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abe90-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="abe90-164">Por ejemplo, si va a implementar un segundo grupo de servidores (pool02), pero el rol de servidor de administración central se mantiene mediante grupo01.</span><span class="sxs-lookup"><span data-stu-id="abe90-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="abe90-165">El grupo sysadmin de SQL Server (o equivalente) debe tener permisos en ambas bases de datos basadas en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abe90-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="abe90-166">Abra el shell de administración de Lync Server, si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="abe90-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="abe90-167">Use el cmdlet **install-CsDatabase** con el parámetro DatabasePathMap y una tabla hash de PowerShell para instalar las bases de datos configuradas del generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="abe90-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="abe90-168">En el código de ejemplo, las rutas de acceso definidas para las bases de datos pueden determinarse de una manera granular mediante el parámetro – DatabasePathMap y una tabla hash definida de la siguiente manera (en el\\ejemplo, se usa "c: CSData" para todos los archivos de base\\de datos (. MDF) y "c: CSLogFiles" para todos los archivos de registro (. ldf).</span><span class="sxs-lookup"><span data-stu-id="abe90-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="abe90-169">La carpeta se creará según sea necesario mediante install-CsDatabase):</span><span class="sxs-lookup"><span data-stu-id="abe90-169">Folder will be created as needed by Install-CsDatabase):</span></span>
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  <span data-ttu-id="abe90-170">Dado que la base de datos y los archivos de registro se denominan explícitamente con su ubicación en el servidor de la base de datos de destino, puede definir ubicaciones específicas para la ubicación de registro y base de datos real de cada tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="abe90-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="abe90-171">En el siguiente ejemplo se colocan bases de datos para cada tipo de servicio específico en discos independientes y archivos de registro asociados en otro.</span><span class="sxs-lookup"><span data-stu-id="abe90-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="abe90-172">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abe90-172">For example:</span></span>
    
      - <span data-ttu-id="abe90-173">Todas las bases de datos RTC a "D\\: RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="abe90-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="abe90-174">Todos los archivos de registro RTC a "\\E: RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="abe90-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="abe90-175">Todas las bases de datos del almacén de aplicaciones en\\"F: CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="abe90-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="abe90-176">Todos los registros del almacén de aplicaciones en\\"G: CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="abe90-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="abe90-177">Todas las bases de datos del almacén de grupos de respuesta\\a "H: RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="abe90-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="abe90-178">Todos los registros del almacén de grupos de respuesta\\en "I: RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="abe90-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="abe90-179">Todas las bases de datos del almacén de la libreta de\\direcciones en "J: ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="abe90-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="abe90-180">Todos los archivos de registro del almacén de la libreta\\de direcciones en "K: ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="abe90-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="abe90-181">Todas las bases de datos de almacenamiento de archivado en\\"L: ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="abe90-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="abe90-182">Todos los registros del almacén de archivado en\\"M: ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="abe90-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="abe90-183">Todas las bases de datos del almacén de supervisión a\\"N: MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="abe90-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="abe90-184">Todos los archivos de registro del almacén de supervisión\\a "O: MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="abe90-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    <span data-ttu-id="abe90-185">Mediante el parámetro – DatabasePathMap, puede definir cualquier combinación de asignación de letra de unidad lógica que ofrezca la mejor solución para los requisitos de rendimiento y ubicación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abe90-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="abe90-186">Si configura los archivos de datos y los archivos de registro de la base de datos mediante el método **DatabasePathMap** , tendrá que realizar un leve cambio en el proceso normal cuando use el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="abe90-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="abe90-187">Normalmente, puede definir las opciones de topología, publicar la topología y elegir implementar las selecciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="abe90-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="abe90-188">Si ha usado **DatabasePathMap** , ya ha realizado la tercera parte del proceso del generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="abe90-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="abe90-189">En el caso de tener un servidor de base de datos completamente configurado antes de ejecutar el generador de topologías, seguirá definiendo todos los roles de servidor y las opciones, pero anule la selección de la opción para crear las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="abe90-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

