---
title: 'Lync Server 2013: Instalación de la base de datos con el Shell de administración de Lync Server'
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
ms.openlocfilehash: 8c617d323eb00476b53677b670c8cc6db0b8d05c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="b1c6a-102">Instalación de la base de datos con el Shell de administración de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1c6a-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1c6a-103">_**Última modificación del tema:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="b1c6a-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="b1c6a-104">La separación de roles y responsabilidades entre los administradores del servidor y los administradores de SQL Server puede dar lugar a retrasos en la implementación.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="b1c6a-105">Lync Server 2013 usa control de acceso basado en roles (RBAC) para mitigar estas dificultades.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="b1c6a-106">En algunos casos, el administrador de SQL Server debe administrar la instalación de bases de datos en el servidor basado en SQL Server fuera de RBAC.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="b1c6a-107">El shell de administración de Lync Server 2013 proporciona una forma para que el administrador de SQL Server ejecute cmdlets de Windows PowerShell diseñados para configurar las bases de datos con los archivos de datos y de registro correctos.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="b1c6a-108">Para obtener más información, consulte [permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b1c6a-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="b1c6a-109">En el procedimiento siguiente se supone que al menos Lync Server 2013 OCSCore. msi, SQL Server Native Client (SQLNCLI. msi) objetos de administración de Microsoft SQL Server 2012, tipos de CLR para Microsoft SQL Server 2012 y Microsoft SQL Server 2012 ADOMD.NET están instalados.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="b1c6a-110">El OCSCore. msi se encuentra en el medio de instalación en el directorio \Setup\AMD64\Setup</span><span class="sxs-lookup"><span data-stu-id="b1c6a-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="b1c6a-111">Los componentes restantes se encuentran en \Setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="b1c6a-112">Además, la preparación de Active Directory para Lync Server 2013 se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="b1c6a-113">**Install-CsDatabase** es el cmdlet de Windows PowerShell que usas para instalar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="b1c6a-114">El cmdlet **install-CsDatabase** tiene un gran número de parámetros, solo algunos de los cuales se tratan aquí.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="b1c6a-115">Para obtener más información sobre los parámetros posibles, consulte la documentación del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="b1c6a-116">Para evitar problemas de rendimiento y posibles problemas de tiempo de espera, use siempre nombres de dominio completos (FQDN) al hacer referencia a servidores basados en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="b1c6a-117">Evite usar referencias de solo nombres de host.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-117">Avoid using host name-only references.</span></span> <span data-ttu-id="b1c6a-118">Por ejemplo, use sqlbe01.contoso.net, pero evite usar SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="b1c6a-119">Para instalar bases de datos, **install-CsDatabase** usa tres métodos principales para ubicar las bases de datos en el servidor basado en SQL preparado:</span><span class="sxs-lookup"><span data-stu-id="b1c6a-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="b1c6a-120">Ejecute **install-CsDatabase** sin DatabasePaths o UseDefaultSqlPath.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="b1c6a-121">El cmdlet usa un algoritmo integrado para determinar la mejor ubicación de los archivos de registro y de datos.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="b1c6a-122">El algoritmo solo funciona para implementaciones independientes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="b1c6a-123">Ejecute **install-CsDatabase** con el parámetro DatabasePaths.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="b1c6a-124">El algoritmo integrado para optimizar las ubicaciones de los archivos de registro y datos no se usa si el parámetro DatabasePaths está definido.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="b1c6a-125">El uso de este parámetro le permite definir las ubicaciones en las que se implementarán los archivos de registro y de datos.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="b1c6a-126">Ejecute **install-CsDatabase** con UseDefaultSqlPaths.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="b1c6a-127">Esta opción no usa el algoritmo integrado para optimizar el registro y las ubicaciones de los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="b1c6a-128">El registro y el archivo de datos se implementan de acuerdo con los valores predeterminados establecidos por el administrador de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="b1c6a-129">Normalmente, estas rutas se establecen para la administración automática de archivos de registro y datos en SQL Server por adelantado y no están asociadas a la configuración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="b1c6a-130">El parámetro DatabasePathMap también se puede usar para especificar de forma explícita una ubicación para cada base de datos y el archivo de registro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="b1c6a-131">Para usar los cmdlets de Windows PowerShell para configurar el almacén de administración central de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b1c6a-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="b1c6a-132">En cualquier equipo, inicie sesión con credenciales administrativas para crear las bases de datos en el servidor basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="b1c6a-133">Para obtener más información, consulte [permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b1c6a-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="b1c6a-134">Abra el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="b1c6a-135">Si no ha ajustado la Directiva de ejecución de Windows PowerShell, debe ajustar la Directiva para permitir la ejecución de los scripts de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="b1c6a-136">Para obtener más información, consulte "examen de la Directiva de [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)ejecución" en.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-136">For details, see “Examining the Execution Policy” at [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="b1c6a-137">Use el cmdlet **install-CsDatabase** para instalar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
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
    > <span data-ttu-id="b1c6a-138">El parámetro de informe es opcional pero es útil si está documentando el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="b1c6a-139">**Install-CsDatabase – DatabasePaths** puede usar hasta seis parámetros PATH, cada uno de los cuales define las rutas de las unidades según se definen en los datos y la ubicación del archivo de registro de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="b1c6a-140">Según las reglas lógicas de la configuración de la base de datos en Lync Server 2013, las unidades se redistribuyen en cubos de dos, cuatro o seis.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="b1c6a-141">Según la configuración de SQL Server y el número de cubos, deberá proporcionar dos rutas, cuatro rutas o seis rutas.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="b1c6a-142">Si tiene tres unidades, el registro obtiene prioridad y los archivos de datos se distribuyen después de.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="b1c6a-143">Un ejemplo de un servidor basado en SQL Server configurado con seis unidades:</span><span class="sxs-lookup"><span data-stu-id="b1c6a-143">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="b1c6a-144">Una vez completada la instalación de la base de datos, puede cerrar el shell de administración de Lync Server 2013 o ir a la instalación de las bases de datos de Lync Server 2013 configuradas en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="b1c6a-145">Para usar los cmdlets de Windows PowerShell para configurar la topología de SQL Server configurada bases de datos</span><span class="sxs-lookup"><span data-stu-id="b1c6a-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="b1c6a-146">Para instalar las bases de datos configuradas en el generador de topologías para Lync Server 2013, el administrador de Lync Server 2013 debe publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="b1c6a-147">Para obtener más información, vea [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="b1c6a-148">En cualquier equipo, inicie sesión con credenciales administrativas para crear las bases de datos en el servidor basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="b1c6a-149">Vea el tema [sobre los permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b1c6a-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b1c6a-150">Para poder configurar las bases de datos basadas en SQL Server, asegúrese de que la cuenta de administrador de SQL Server que se usa para ejecutar los pasos descritos aquí también es miembro del grupo sysadmins (o equivalente) en el servidor que ejecuta SQL Server y que mantiene la administración central. Rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="b1c6a-151">Esto es especialmente importante para comprobar si hay otros grupos de 2013 de Lync Server que requieran la instalación o configuración de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="b1c6a-152">Por ejemplo, si está implementando un segundo grupo (pool02) pero el rol de servidor de administración central es de pool01.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="b1c6a-153">El grupo sysadmin de SQL Server (o equivalente) debe tener permisos en ambas bases de datos basadas en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="b1c6a-154">Abra el shell de administración de Lync Server 2013, si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="b1c6a-155">Use el cmdlet **install-CsDatabase** para instalar las bases de datos configuradas en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
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
    > <span data-ttu-id="b1c6a-156">El parámetro de informe es opcional pero es útil si está documentando el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="b1c6a-157">Cuando se complete la instalación de la base de datos, cierre el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="b1c6a-158">Para usar los cmdlets de Windows PowerShell para configurar la topología de SQL Server con el parámetro DatabasePathMap</span><span class="sxs-lookup"><span data-stu-id="b1c6a-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="b1c6a-159">Para instalar las bases de datos de Lync Server 2013, el administrador de Lync Server debe crear las rutas e implementar los archivos de base de datos y los archivos de registro según un conjunto predefinido de reglas.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="b1c6a-160">En cualquier equipo, inicie sesión con credenciales administrativas para crear las bases de datos en el servidor basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="b1c6a-161">Vea el tema [sobre los permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b1c6a-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b1c6a-162">Para poder configurar las bases de datos basadas en SQL Server, asegúrese de que la cuenta de administrador de SQL Server que se usa para ejecutar los pasos descritos aquí también es miembro del grupo sysadmins (o equivalente) en el servidor que ejecuta SQL Server y que mantiene la administración central. Rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="b1c6a-163">Esto es especialmente importante para comprobar si hay otros grupos de servidores de Lync que requieran la instalación o configuración de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="b1c6a-164">Por ejemplo, si está implementando un segundo grupo (pool02) pero el rol de servidor de administración central es de pool01.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="b1c6a-165">El grupo sysadmin de SQL Server (o equivalente) debe tener permisos en ambas bases de datos basadas en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="b1c6a-166">Abra el shell de administración de Lync Server, si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="b1c6a-167">Use el cmdlet **install-CsDatabase** con el parámetro DatabasePathMap y una tabla hash de PowerShell para instalar las bases de datos configuradas en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="b1c6a-168">En el código de ejemplo, las rutas de las bases de datos se pueden determinar de forma granular con el parámetro – DatabasePathMap y una tabla hash definida de la siguiente manera (el ejemplo usa "C:\\CSData" para todos los archivos de base de datos (. MDF) y\\"c: CSLogFiles" para todos los archivos de registro (. ldf).</span><span class="sxs-lookup"><span data-stu-id="b1c6a-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="b1c6a-169">Se creará una carpeta según sea necesario por install-CsDatabase):</span><span class="sxs-lookup"><span data-stu-id="b1c6a-169">Folder will be created as needed by Install-CsDatabase):</span></span>
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
6.  <span data-ttu-id="b1c6a-170">Puesto que la base de datos y los archivos de registro se denominan explícitamente con su ubicación en el servidor de la base de datos de destino, puede definir ubicaciones específicas para cada tipo de servicio y la ubicación de registro y de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="b1c6a-171">En el siguiente ejemplo se colocan bases de datos para cada tipo de servicio específico en discos independientes y archivos de registro relacionados en otro.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="b1c6a-172">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b1c6a-172">For example:</span></span>
    
      - <span data-ttu-id="b1c6a-173">Todas las bases de datos de RTC a "\\D: RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="b1c6a-174">Todos los archivos de registro de RTC a\\"E: RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="b1c6a-175">Todas las bases de datos del almacén de aplicaciones a\\"F: CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="b1c6a-176">Todos los registros del almacén de aplicaciones a\\"G: CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="b1c6a-177">Todas las bases de datos de la tienda de grupos de\\respuesta a "H: RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="b1c6a-178">Todos los registros del almacén de grupos de respuesta\\en "I: RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="b1c6a-179">Todas las bases de datos del almacén de la libreta de\\direcciones en "J: ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="b1c6a-180">Todos los archivos de registro del almacén de la libreta\\de direcciones a "K: ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="b1c6a-181">Todas las bases de datos del almacén de archivado a\\"L: ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="b1c6a-182">Todos los registros del almacén de archivado a\\"M: ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="b1c6a-183">Todas las bases de datos del almacén de supervisión a\\"N: MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="b1c6a-184">Todos los archivos de registro del almacén de supervisión\\a "O: MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="b1c6a-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
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
    
    <span data-ttu-id="b1c6a-185">Con el parámetro – DatabasePathMap, puede definir cualquier combinación de asignación de letra de unidad lógica que proporcione la mejor solución para sus requisitos de rendimiento y ubicación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="b1c6a-186">Si configura los archivos de datos y los archivos de registro de la base de datos con el método **DatabasePathMap** , tendrá que hacer un leve cambio en el proceso normal cuando use el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="b1c6a-187">Normalmente, debe definir las opciones de topología, publicar la topología y elegir implementar las selecciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="b1c6a-188">Si ha usado **DatabasePathMap** ya ha realizado la tercera parte del proceso de creación de topología.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="b1c6a-189">En el caso de que haya un servidor de base de datos completamente configurado antes de ejecutar el generador de topología, aún definirá todos los roles y las opciones del servidor, pero desactivando la opción para crear las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="b1c6a-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

