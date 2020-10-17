---
title: 'Lync Server 2013: exclusiones de detección de virus'
description: 'Lync Server 2013: exclusiones de detección de virus.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561916"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="0adb0-103">Exclusiones de detección de virus para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0adb0-103">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0adb0-104">_**Última modificación del tema:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="0adb0-104">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="0adb0-105">Para asegurarse de que el detector de virus no interfiera con el funcionamiento de Lync Server 2013, debe excluir procesos y directorios específicos para cada rol de servidor o servidor de Lync Server 2013 en el que ejecute un detector de virus.</span><span class="sxs-lookup"><span data-stu-id="0adb0-105">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="0adb0-106">Estos son los procesos y directorios en cuestión:</span><span class="sxs-lookup"><span data-stu-id="0adb0-106">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0adb0-107">Las ubicaciones de archivos y carpetas que se enumeran a continuación son las ubicaciones predeterminadas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0adb0-107">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="0adb0-108">En el caso de haya ubicaciones especificadas para la organización que no sean las predeterminadas, exclúyalas en lugar de las ubicaciones predeterminadas mencionadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="0adb0-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0adb0-109">Tenga en cuenta que algunos programas antivirus pueden necesitar rutas de ruta absolutas, no relativas para la lista de exclusión.</span><span class="sxs-lookup"><span data-stu-id="0adb0-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="0adb0-110">Lync Server 2013 procesos de:</span><span class="sxs-lookup"><span data-stu-id="0adb0-110">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="0adb0-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-111">ABServer.exe</span></span>
    
      - <span data-ttu-id="0adb0-112">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-112">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="0adb0-113">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-113">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="0adb0-114">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-114">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="0adb0-115">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-115">ChannelService.exe</span></span>
    
      - <span data-ttu-id="0adb0-116">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-116">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="0adb0-117">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-117">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="0adb0-118">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-118">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="0adb0-119">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-119">DataProxy.exe</span></span>
    
      - <span data-ttu-id="0adb0-120">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-120">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="0adb0-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-121">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="0adb0-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-122">LysSvc.exe</span></span>
    
      - <span data-ttu-id="0adb0-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-123">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="0adb0-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-124">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="0adb0-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-125">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="0adb0-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-126">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="0adb0-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-127">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="0adb0-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-128">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="0adb0-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-129">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="0adb0-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-130">RtcHost.exe</span></span>
    
      - <span data-ttu-id="0adb0-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-131">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="0adb0-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-132">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="0adb0-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-133">XmppTGW.exe</span></span>

  - <span data-ttu-id="0adb0-134">Procesos del servicio host de Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="0adb0-134">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="0adb0-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-135">Fabric.exe</span></span>
    
      - <span data-ttu-id="0adb0-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-136">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="0adb0-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-137">FabricHost.exe</span></span>

  - <span data-ttu-id="0adb0-138">Procesos de IIS:</span><span class="sxs-lookup"><span data-stu-id="0adb0-138">IIS processes:</span></span>
    
      - <span data-ttu-id="0adb0-139">% SystemRoot% \\ system32 \\ Inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-139">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="0adb0-140">% SystemRoot% \\ SysWOW64 \\ Inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-140">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="0adb0-141">Procesos de Back-End de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="0adb0-141">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="0adb0-142">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. \\Binn MSSQL de MSSQLSERVER \\ \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-142">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="0adb0-143">% ProgramFiles% \\ Microsoft SQL Server \\ MSRS11. \\Papelera ReportServer de Reporting Services de MSSQLSERVER \\ \\ \\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="0adb0-143">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="0adb0-144">% ProgramFiles% \\ Microsoft SQL Server \\ MSAS11. \\MSMDSrv.exe de \\ bin \\ OLAP de MSSQLServer</span><span class="sxs-lookup"><span data-stu-id="0adb0-144">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="0adb0-145">Procesos de Front-End de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="0adb0-145">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="0adb0-146">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. \\ \\SQLServr.exe Binn de LYNCLOCAL MSSQL \\</span><span class="sxs-lookup"><span data-stu-id="0adb0-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="0adb0-147">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. \\ \\SQLServr.exe Binn de RTCLOCAL MSSQL \\</span><span class="sxs-lookup"><span data-stu-id="0adb0-147">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="0adb0-148">Directorios y archivos:</span><span class="sxs-lookup"><span data-stu-id="0adb0-148">Directories and files:</span></span>
    
      - <span data-ttu-id="0adb0-149">archivos de registro de% SystemRoot% \\ system32 \\</span><span class="sxs-lookup"><span data-stu-id="0adb0-149">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="0adb0-150">% SystemRoot% \\ \\ archivos de registro SysWow64</span><span class="sxs-lookup"><span data-stu-id="0adb0-150">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="0adb0-151">% SystemRoot% \\ Microsoft.net \\ ensamblado \\ GAC \_ MSIL</span><span class="sxs-lookup"><span data-stu-id="0adb0-151">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="0adb0-152">% programfiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0adb0-152">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="0adb0-153">Archivos comunes de% ProgramFiles% \\ \\ nodo de monitor de Microsoft Lync Server 2013 \\</span><span class="sxs-lookup"><span data-stu-id="0adb0-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="0adb0-154">Archivos comunes de% ProgramFiles% \\ \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0adb0-154">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="0adb0-155">% SystemDrive% \\ RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="0adb0-155">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="0adb0-156">Almacén de recurso compartido de archivos (especificado en el Generador de topologías).</span><span class="sxs-lookup"><span data-stu-id="0adb0-156">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="0adb0-157">Los almacenes de archivos se especifican en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="0adb0-157">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="0adb0-158">Datos y archivos de registro de SQL Server, incluidos los relativos a la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0adb0-158">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="0adb0-159">Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="0adb0-159">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="0adb0-160">Para obtener información detallada sobre los archivos de datos y de registro de cada base de datos, incluidos los nombres predeterminados, consulte [SQL Server Data and log file Placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) en la documentación referente a la implementación.</span><span class="sxs-lookup"><span data-stu-id="0adb0-160">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0adb0-161">Archivos de registro y datos de SQL Server, incluidos los de la base de datos front-end, la tienda Lync y el almacén RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="0adb0-161">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="0adb0-162">Normalmente se encuentran en% UnidadLocal% \\ CSData.</span><span class="sxs-lookup"><span data-stu-id="0adb0-162">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

