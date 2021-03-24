---
title: Exclusiones de análisis antivirus para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Información general sobre la interoperación del escáner antivirus con Skype Empresarial Server.
ms.openlocfilehash: 64646304b98de075fd9af0a82096da8c0bff2f12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104246"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="23036-103">Exclusiones de análisis antivirus para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="23036-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="23036-104">Información general sobre la interoperación del escáner antivirus con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="23036-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="23036-105">Para asegurarse de que el escáner antivirus no interfiera con el funcionamiento de Skype Empresarial Server, debe excluir procesos y directorios específicos para cada servidor o rol de servidor de Skype Empresarial Server en el que ejecute un escáner antivirus.</span><span class="sxs-lookup"><span data-stu-id="23036-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="23036-106">Estos son los procesos y directorios en cuestión:</span><span class="sxs-lookup"><span data-stu-id="23036-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="23036-107">Las ubicaciones de carpetas y archivos que se enumeran a continuación son las ubicaciones predeterminadas de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="23036-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="23036-108">En el caso de haya ubicaciones especificadas para la organización que no sean las predeterminadas, exclúyalas en lugar de las ubicaciones predeterminadas mencionadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="23036-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23036-109">Tenga en cuenta que algunos programas antivirus pueden necesitar rutas absolutas, no relativas, para su lista de exclusión.</span><span class="sxs-lookup"><span data-stu-id="23036-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="23036-110">Procesos de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="23036-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="23036-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="23036-111">ABServer.exe</span></span>

  - <span data-ttu-id="23036-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="23036-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="23036-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="23036-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="23036-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="23036-114">ChannelService.exe</span></span>

  - <span data-ttu-id="23036-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="23036-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="23036-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="23036-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="23036-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="23036-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="23036-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="23036-118">DataProxy.exe</span></span>

  - <span data-ttu-id="23036-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="23036-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="23036-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="23036-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="23036-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="23036-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="23036-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="23036-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="23036-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="23036-123">LysSvc.exe</span></span>

  - <span data-ttu-id="23036-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="23036-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="23036-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="23036-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="23036-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="23036-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="23036-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="23036-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="23036-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="23036-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="23036-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="23036-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="23036-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="23036-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="23036-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="23036-131">RtcHost.exe</span></span>

  - <span data-ttu-id="23036-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="23036-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="23036-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="23036-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="23036-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="23036-134">XmppTGW.exe</span></span>

- <span data-ttu-id="23036-135">Procesos del servicio host de Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="23036-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="23036-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="23036-136">Fabric.exe</span></span>

  - <span data-ttu-id="23036-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="23036-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="23036-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="23036-138">FabricHost.exe</span></span>

- <span data-ttu-id="23036-139">Procesos de IIS:</span><span class="sxs-lookup"><span data-stu-id="23036-139">IIS processes:</span></span>

  - <span data-ttu-id="23036-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="23036-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="23036-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="23036-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="23036-142">SQL Server Back-End procesos:</span><span class="sxs-lookup"><span data-stu-id="23036-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="23036-143">Tenga en cuenta que estas rutas de acceso son específicas SQL Server versión.</span><span class="sxs-lookup"><span data-stu-id="23036-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="23036-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="23036-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="23036-145">%ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="23036-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="23036-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="23036-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="23036-147">SQL Server Front-End procesos:</span><span class="sxs-lookup"><span data-stu-id="23036-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="23036-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="23036-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="23036-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="23036-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="23036-150">Instancia RTC de instalación de Standard Edition</span><span class="sxs-lookup"><span data-stu-id="23036-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="23036-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="23036-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="23036-152">Directorios y archivos:</span><span class="sxs-lookup"><span data-stu-id="23036-152">Directories and files:</span></span>

  - <span data-ttu-id="23036-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="23036-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="23036-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="23036-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="23036-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="23036-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="23036-156">Tenga en cuenta que estas rutas de acceso son específicas de la versión de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="23036-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="23036-157">%programfiles%\Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="23036-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="23036-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="23036-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="23036-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="23036-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="23036-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="23036-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="23036-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="23036-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="23036-p103">Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="23036-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="23036-164">Datos y archivos de registro de SQL Server, incluidos los relativos a la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="23036-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="23036-165">Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="23036-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="23036-166">Para obtener información detallada sobre los datos y los archivos de registro de cada base de datos (incluidos los nombres predeterminados), consulte [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="23036-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span>

  - <span data-ttu-id="23036-167">SQL Server datos y archivos de registro, incluidos los de la base de datos front-end, el almacén de Skype Empresarial y el almacén RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="23036-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="23036-168">Normalmente están en %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="23036-168">They are normally under %localdrive%\CSData.</span></span>