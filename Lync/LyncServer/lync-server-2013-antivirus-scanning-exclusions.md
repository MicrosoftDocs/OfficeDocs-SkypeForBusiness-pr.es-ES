---
title: 'Lync Server 2013: Exclusiones de la detección de virus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34843038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="4c987-102">Exclusiones de la detección de virus para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c987-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c987-103">_**Última modificación del tema:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="4c987-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="4c987-104">Para asegurarse de que el detector de virus no interfiere con el funcionamiento de Lync Server 2013, debe excluir los procesos y directorios específicos de cada rol de servidor o servidor de Lync Server 2013 en el que se ejecute un detector de virus.</span><span class="sxs-lookup"><span data-stu-id="4c987-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="4c987-105">Es necesario excluir los siguientes procesos y directorios:</span><span class="sxs-lookup"><span data-stu-id="4c987-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4c987-106">Las ubicaciones de carpetas y archivos que se enumeran a continuación son las ubicaciones predeterminadas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c987-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="4c987-107">Si no usó los valores predeterminados para algunas ubicaciones, excluya esas ubicaciones especificadas para su organización en lugar de las ubicaciones predeterminadas especificadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="4c987-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4c987-108">Tenga en cuenta que es posible que algunos programas antivirus necesiten rutas de acceso absolutas (no relativas) para su lista de exclusión.</span><span class="sxs-lookup"><span data-stu-id="4c987-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="4c987-109">Procesos de 2013 de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4c987-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="4c987-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="4c987-111">AcpMcuSvc. exe</span><span class="sxs-lookup"><span data-stu-id="4c987-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="4c987-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4c987-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4c987-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="4c987-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="4c987-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="4c987-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4c987-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="4c987-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="4c987-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4c987-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="4c987-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="4c987-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="4c987-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="4c987-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="4c987-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="4c987-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="4c987-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="4c987-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="4c987-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="4c987-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="4c987-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="4c987-133">Procesos del servicio de host de Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="4c987-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="4c987-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="4c987-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="4c987-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="4c987-136">FabricHost.exe</span></span>

  - <span data-ttu-id="4c987-137">Procesos de IIS:</span><span class="sxs-lookup"><span data-stu-id="4c987-137">IIS processes:</span></span>
    
      - <span data-ttu-id="4c987-138">% SystemRoot%\\system32\\Inetsrv\\, w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="4c987-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="4c987-139">% SystemRoot%\\SysWOW64\\Inetsrv\\. exe</span><span class="sxs-lookup"><span data-stu-id="4c987-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="4c987-140">Procesos del back-end de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="4c987-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="4c987-141">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\SQLServr. exe</span><span class="sxs-lookup"><span data-stu-id="4c987-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="4c987-142">% ProgramFiles%\\Microsoft SQL Server\\MSRS11. \\Reporting\\Services\\ReportServer\\bin ReportingServicesService. exe</span><span class="sxs-lookup"><span data-stu-id="4c987-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="4c987-143">% ProgramFiles%\\Microsoft SQL Server\\MSAS11. Papelera\\\\OLAP\\de MSSQLServer MSMDSrv. exe</span><span class="sxs-lookup"><span data-stu-id="4c987-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="4c987-144">Procesos del front-end de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="4c987-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="4c987-145">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\SQLServr. exe</span><span class="sxs-lookup"><span data-stu-id="4c987-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="4c987-146">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\SQLServr. exe</span><span class="sxs-lookup"><span data-stu-id="4c987-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="4c987-147">Directorios y archivos:</span><span class="sxs-lookup"><span data-stu-id="4c987-147">Directories and files:</span></span>
    
      - <span data-ttu-id="4c987-148">archivos de registro\\de\\% SystemRoot% system32</span><span class="sxs-lookup"><span data-stu-id="4c987-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="4c987-149">archivos de registro\\de\\% SystemRoot% SysWow64</span><span class="sxs-lookup"><span data-stu-id="4c987-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="4c987-150">% SystemRoot%\\Microsoft.net\\del\\ensamblado GAC\_MSIL</span><span class="sxs-lookup"><span data-stu-id="4c987-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="4c987-151">% programfiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c987-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="4c987-152">Archivos\\\\comunes de% ProgramFiles% Microsoft Lync Server\\2013 nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="4c987-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="4c987-153">Archivos\\comunes de\\% ProgramFiles% Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c987-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="4c987-154">% SystemDrive%\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="4c987-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="4c987-155">Almacén de recurso compartido de archivos (especificado en el Generador de topologías).</span><span class="sxs-lookup"><span data-stu-id="4c987-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="4c987-156">Los almacenes de archivos se especifican en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="4c987-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="4c987-157">Datos y archivos de registro de SQL Server, incluidos los relacionados con la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4c987-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="4c987-158">Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="4c987-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="4c987-159">Para obtener detalles sobre los archivos de datos y de registro de cada base de datos, incluidos los nombres predeterminados, consulte ubicación de los [archivos de registro y datos de SQL Server para Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="4c987-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4c987-160">Los datos y archivos de registro de SQL Server, incluidos los de la base de datos front-end, la tienda Lync y la tienda RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="4c987-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="4c987-161">Normalmente se encuentran debajo de% UnidadLocal\\% CSData.</span><span class="sxs-lookup"><span data-stu-id="4c987-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

