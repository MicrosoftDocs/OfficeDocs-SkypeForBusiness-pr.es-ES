---
title: Exclusiones de análisis antivirus para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Resumen de interoperación de escáner antivirus con Skype para Business Server 2015.
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a><span data-ttu-id="171e0-103">Exclusiones de análisis antivirus para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="171e0-103">Antivirus scanning exclusions for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="171e0-104">Resumen de interoperación de escáner antivirus con Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="171e0-104">Overview of antivirus scanner interoperation with Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="171e0-105">Para asegurarse de que el programa antivirus no interfiere con el funcionamiento de Skype para Business Server 2015, debe excluir los directorios y procesos específicos para cada Skype para servidor Business Server 2015 o rol de servidor en el que se ejecuta un programa antivirus.</span><span class="sxs-lookup"><span data-stu-id="171e0-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server 2015, you must exclude specific processes and directories for each Skype for Business Server 2015 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="171e0-106">Es necesario excluir los siguientes procesos y directorios:</span><span class="sxs-lookup"><span data-stu-id="171e0-106">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="171e0-107">Ubicaciones de archivos y carpetas enumerados a continuación son las ubicaciones predeterminadas para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="171e0-107">Folder and file locations listed below are the default locations for Skype for Business Server 2015.</span></span> <span data-ttu-id="171e0-108">Si no usó los valores predeterminados para algunas ubicaciones, excluya esas ubicaciones especificadas para su organización en lugar de las ubicaciones predeterminadas especificadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="171e0-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="171e0-109">Tenga en cuenta que es posible que algunos programas antivirus necesiten rutas de acceso absolutas (no relativas) para su lista de exclusión.</span><span class="sxs-lookup"><span data-stu-id="171e0-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="171e0-110">Skype para los procesos de negocio servidor 2015:</span><span class="sxs-lookup"><span data-stu-id="171e0-110">Skype for Business Server 2015 processes:</span></span>
    
  - <span data-ttu-id="171e0-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-111">ABServer.exe</span></span>
    
  - <span data-ttu-id="171e0-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-112">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="171e0-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-113">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="171e0-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-114">ChannelService.exe</span></span>
    
  - <span data-ttu-id="171e0-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-115">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="171e0-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-116">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="171e0-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-117">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="171e0-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-118">DataProxy.exe</span></span>
    
  - <span data-ttu-id="171e0-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-119">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="171e0-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-120">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="171e0-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-121">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="171e0-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-122">LysSvc.exe</span></span>
    
  - <span data-ttu-id="171e0-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-123">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="171e0-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-124">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="171e0-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-125">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="171e0-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-126">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="171e0-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-127">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="171e0-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-128">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="171e0-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-129">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="171e0-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-130">RtcHost.exe</span></span>
    
  - <span data-ttu-id="171e0-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-131">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="171e0-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-132">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="171e0-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-133">XmppTGW.exe</span></span>
    
- <span data-ttu-id="171e0-134">Procesos del servicio de host de Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="171e0-134">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="171e0-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-135">Fabric.exe</span></span>
    
  - <span data-ttu-id="171e0-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-136">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="171e0-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-137">FabricHost.exe</span></span>
    
- <span data-ttu-id="171e0-138">Procesos de IIS:</span><span class="sxs-lookup"><span data-stu-id="171e0-138">IIS processes:</span></span>
    
  - <span data-ttu-id="171e0-139">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-139">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="171e0-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="171e0-141">Procesos del back-end de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="171e0-141">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="171e0-142">Tenga en cuenta que estas rutas dependen de la versión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="171e0-142">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="171e0-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="171e0-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="171e0-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="171e0-146">Procesos del front-end de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="171e0-146">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="171e0-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="171e0-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="171e0-149">Instancia RTC de instalación Standard Edition</span><span class="sxs-lookup"><span data-stu-id="171e0-149">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="171e0-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="171e0-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="171e0-151">Directorios y archivos:</span><span class="sxs-lookup"><span data-stu-id="171e0-151">Directories and files:</span></span>
    
  - <span data-ttu-id="171e0-152">%systemroot%\system32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="171e0-152">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="171e0-153">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="171e0-153">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="171e0-154">%SystemRoot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="171e0-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>
    
  - <span data-ttu-id="171e0-155">%programfiles%\Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="171e0-155">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="171e0-156">%programfiles%\Common Files\Skype Empresarial Server 2015\Nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="171e0-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="171e0-157">%programfiles%\Common Files\Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="171e0-157">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="171e0-158">%programfiles%\Common Files\Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="171e0-158">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="171e0-159">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="171e0-159">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="171e0-p103">Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="171e0-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="171e0-162">Datos y archivos de registro de SQL Server, incluidos los relacionados con la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="171e0-162">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="171e0-163">Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="171e0-163">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="171e0-164">Para obtener más información acerca de los archivos de datos y de registro para cada base de datos, incluidos los nombres predeterminados, consulte [la ubicación del archivo de registro y datos de SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="171e0-164">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="171e0-165">SQL Server datos y registro de archivos, los de la base de datos front-end de Skype para almacén de negocios y almacén de RtcDatabase incluidos.</span><span class="sxs-lookup"><span data-stu-id="171e0-165">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="171e0-166">Normalmente, se encuentran en %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="171e0-166">They are normally under %localdrive%\CSData.</span></span>
    

