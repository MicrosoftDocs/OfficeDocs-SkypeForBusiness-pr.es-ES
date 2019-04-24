---
title: Análisis de exclusiones para Skype para Business Server del antivirus
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Información general de interoperación del detector de virus con Skype para Business Server.
ms.openlocfilehash: 377c9e8fb9de71187978fe541a23f43cc2282749
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213672"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="6bbc0-103">Análisis de exclusiones para Skype para Business Server del antivirus</span><span class="sxs-lookup"><span data-stu-id="6bbc0-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="6bbc0-104">Información general de interoperación del detector de virus con Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="6bbc0-105">En este artículo se incluyen recomendaciones que pueden ayudar a un administrador a determinar la causa del potencial de inestabilidad en un equipo que está ejecutando una versión compatible de Microsoft Windows cuando se usa con el software antivirus en un dominio de Active Directory entorno o en un entorno empresarial administrada.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="6bbc0-106">Se recomienda que aplicar temporalmente estos procedimientos para evaluar un sistema.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="6bbc0-107">Si el rendimiento del sistema o la estabilidad se ha mejorado por las recomendaciones que se realizan en este artículo, póngase en contacto con su proveedor de software antivirus para obtener instrucciones o para una versión actualizada del software antivirus.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="6bbc0-108">Este artículo contiene información que muestra cómo ayudar a reducir la configuración de seguridad o cómo desactivar temporalmente las características de seguridad en un equipo.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="6bbc0-109">Puede realizar estos cambios para comprender la naturaleza de un problema específico.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="6bbc0-110">Antes de realizar estos cambios, le recomendamos que evalúe los riesgos asociados con la implementación de esta solución en su entorno concreto.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="6bbc0-111">Si decide implementar esta solución alternativa, tome las medidas adicionales oportunas para ayudar a proteger el equipo para los archivos que ya no se examina el software antivirus.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="6bbc0-112">Para asegurarse de que el detector antivirus no interfiere con el funcionamiento de Skype para Business Server, debe excluir directorios y procesos específicos para cada Skype para un servidor Business Server o rol de servidor en el que ejecute un detector de virus.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="6bbc0-113">Es necesario excluir los siguientes procesos y directorios:</span><span class="sxs-lookup"><span data-stu-id="6bbc0-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="6bbc0-114">Las ubicaciones de archivos y carpetas enumeradas a continuación son las ubicaciones predeterminadas de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="6bbc0-115">Si no usó los valores predeterminados para algunas ubicaciones, excluya esas ubicaciones especificadas para su organización en lugar de las ubicaciones predeterminadas especificadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6bbc0-116">Tenga en cuenta que es posible que algunos programas antivirus necesiten rutas de acceso absolutas (no relativas) para su lista de exclusión.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="6bbc0-117">Skype para los procesos del servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="6bbc0-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="6bbc0-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-118">ABServer.exe</span></span>

  - <span data-ttu-id="6bbc0-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="6bbc0-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="6bbc0-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-121">ChannelService.exe</span></span>

  - <span data-ttu-id="6bbc0-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="6bbc0-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="6bbc0-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="6bbc0-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-125">DataProxy.exe</span></span>

  - <span data-ttu-id="6bbc0-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="6bbc0-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="6bbc0-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="6bbc0-129">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="6bbc0-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-130">LysSvc.exe</span></span>

  - <span data-ttu-id="6bbc0-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="6bbc0-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="6bbc0-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="6bbc0-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="6bbc0-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="6bbc0-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="6bbc0-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="6bbc0-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-138">RtcHost.exe</span></span>

  - <span data-ttu-id="6bbc0-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="6bbc0-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="6bbc0-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-141">XmppTGW.exe</span></span>

- <span data-ttu-id="6bbc0-142">Procesos del servicio de host de Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="6bbc0-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="6bbc0-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-143">Fabric.exe</span></span>

  - <span data-ttu-id="6bbc0-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="6bbc0-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-145">FabricHost.exe</span></span>

- <span data-ttu-id="6bbc0-146">Procesos de IIS:</span><span class="sxs-lookup"><span data-stu-id="6bbc0-146">IIS processes:</span></span>

  - <span data-ttu-id="6bbc0-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="6bbc0-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="6bbc0-149">Procesos del back-end de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="6bbc0-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="6bbc0-150">Tenga en cuenta que estas rutas dependen de la versión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="6bbc0-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6bbc0-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="6bbc0-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="6bbc0-154">Procesos del front-end de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="6bbc0-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="6bbc0-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6bbc0-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6bbc0-157">Instancia RTC de instalación Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6bbc0-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="6bbc0-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6bbc0-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="6bbc0-159">Directorios y archivos:</span><span class="sxs-lookup"><span data-stu-id="6bbc0-159">Directories and files:</span></span>

  - <span data-ttu-id="6bbc0-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="6bbc0-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="6bbc0-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="6bbc0-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="6bbc0-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="6bbc0-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="6bbc0-163">Tenga en cuenta que estas rutas de acceso son específicos de Skype para la versión de Business Server.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="6bbc0-164">%programfiles%\Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="6bbc0-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="6bbc0-165">%programfiles%\Common Files\Skype Empresarial Server 2015\Nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="6bbc0-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="6bbc0-166">%programfiles%\Common Files\Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="6bbc0-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="6bbc0-167">%programfiles%\Common Files\Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6bbc0-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="6bbc0-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="6bbc0-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="6bbc0-p105">Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="6bbc0-p106">Datos y archivos de registro de SQL Server, incluidos los relacionados con la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones. Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías. Para más información sobre los datos y los archivos de registro de cada base de datos (incluidos los nombres predeterminados), vea [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-p106">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="6bbc0-174">SQL Server datos y archivos de registro, los referentes a la base de datos front-end, Skype para almacén empresariales y almacén de RtcDatabase incluidos.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="6bbc0-175">Normalmente, se encuentran en %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-175">They are normally under %localdrive%\CSData.</span></span>


