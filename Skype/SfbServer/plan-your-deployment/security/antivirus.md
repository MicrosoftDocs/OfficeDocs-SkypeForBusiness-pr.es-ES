---
title: Exclusiones de detección antivirus para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Información general sobre la interacción del escáner antivirus con Skype empresarial Server.
ms.openlocfilehash: 10d296e36324fdbc8bca8f7da48370d619774501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815698"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="09fea-103">Exclusiones de detección antivirus para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="09fea-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="09fea-104">Información general sobre la interacción del escáner antivirus con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="09fea-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="09fea-105">Para asegurarse de que el detector antivirus no interfiera con el funcionamiento de Skype empresarial Server, debe excluir los procesos y directorios específicos de cada rol de servidor o servidor de Skype empresarial Server en el que ejecute un detector de virus.</span><span class="sxs-lookup"><span data-stu-id="09fea-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="09fea-106">Es necesario excluir los siguientes procesos y directorios:</span><span class="sxs-lookup"><span data-stu-id="09fea-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="09fea-107">Las ubicaciones de carpetas y archivos que se enumeran a continuación son las ubicaciones predeterminadas de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="09fea-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="09fea-108">Si no usó los valores predeterminados para algunas ubicaciones, excluya esas ubicaciones especificadas para su organización en lugar de las ubicaciones predeterminadas especificadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="09fea-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09fea-109">Tenga en cuenta que es posible que algunos programas antivirus necesiten rutas de acceso absolutas (no relativas) para su lista de exclusión.</span><span class="sxs-lookup"><span data-stu-id="09fea-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="09fea-110">Procesos de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="09fea-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="09fea-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-111">ABServer.exe</span></span>

  - <span data-ttu-id="09fea-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="09fea-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="09fea-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-114">ChannelService.exe</span></span>

  - <span data-ttu-id="09fea-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="09fea-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="09fea-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="09fea-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-118">DataProxy.exe</span></span>

  - <span data-ttu-id="09fea-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="09fea-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="09fea-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="09fea-122">LyncBackupService. exe</span><span class="sxs-lookup"><span data-stu-id="09fea-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="09fea-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-123">LysSvc.exe</span></span>

  - <span data-ttu-id="09fea-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="09fea-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="09fea-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="09fea-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="09fea-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="09fea-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="09fea-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="09fea-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-131">RtcHost.exe</span></span>

  - <span data-ttu-id="09fea-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="09fea-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="09fea-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-134">XmppTGW.exe</span></span>

- <span data-ttu-id="09fea-135">Procesos del servicio de host de Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="09fea-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="09fea-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-136">Fabric.exe</span></span>

  - <span data-ttu-id="09fea-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="09fea-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-138">FabricHost.exe</span></span>

- <span data-ttu-id="09fea-139">Procesos de IIS:</span><span class="sxs-lookup"><span data-stu-id="09fea-139">IIS processes:</span></span>

  - <span data-ttu-id="09fea-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="09fea-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="09fea-142">Procesos del back-end de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="09fea-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="09fea-143">Tenga en cuenta que estas rutas dependen de la versión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09fea-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="09fea-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="09fea-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="09fea-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="09fea-147">Procesos del front-end de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="09fea-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="09fea-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="09fea-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="09fea-150">Instancia RTC de instalación Standard Edition</span><span class="sxs-lookup"><span data-stu-id="09fea-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="09fea-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="09fea-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="09fea-152">Directorios y archivos:</span><span class="sxs-lookup"><span data-stu-id="09fea-152">Directories and files:</span></span>

  - <span data-ttu-id="09fea-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="09fea-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="09fea-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="09fea-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="09fea-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="09fea-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="09fea-156">Tenga en cuenta que estas rutas son específicas de la versión de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="09fea-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="09fea-157">%programfiles%\Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="09fea-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="09fea-158">%programfiles%\Common Files\Skype Empresarial Server 2015\Nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="09fea-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="09fea-159">%programfiles%\Common Files\Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="09fea-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="09fea-160">%programfiles%\Common Files\Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="09fea-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="09fea-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="09fea-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="09fea-p103">Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="09fea-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="09fea-p104">Datos y archivos de registro de SQL Server, incluidos los relacionados con la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones. Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías. Para más información sobre los datos y los archivos de registro de cada base de datos (incluidos los nombres predeterminados), vea [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="09fea-p104">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="09fea-167">Archivos de datos y de registro de SQL Server, incluidos los de la base de datos front-end, la tienda de Skype empresarial y la tienda RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="09fea-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="09fea-168">Normalmente, se encuentran en %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="09fea-168">They are normally under %localdrive%\CSData.</span></span>


