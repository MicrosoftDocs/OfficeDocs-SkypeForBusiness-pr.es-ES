---
title: Análisis de exclusiones para Skype para Business Server del antivirus
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
ms.openlocfilehash: 2e85816b10a808224a79b065153ecf466c4911c8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009267"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="de355-103">Análisis de exclusiones para Skype para Business Server del antivirus</span><span class="sxs-lookup"><span data-stu-id="de355-103">Antivirus scanning exclusions for Skype for Business Server</span></span>
 
<span data-ttu-id="de355-104">Información general de interoperación del detector de virus con Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="de355-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="de355-105">En este artículo se incluyen recomendaciones que pueden ayudar a un administrador a determinar la causa del potencial de inestabilidad en un equipo que está ejecutando una versión compatible de Microsoft Windows cuando se usa con el software antivirus en un dominio de Active Directory entorno o en un entorno empresarial administrada.</span><span class="sxs-lookup"><span data-stu-id="de355-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="de355-106">Se recomienda que aplicar temporalmente estos procedimientos para evaluar un sistema.</span><span class="sxs-lookup"><span data-stu-id="de355-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="de355-107">Si el rendimiento del sistema o la estabilidad se ha mejorado por las recomendaciones que se realizan en este artículo, póngase en contacto con su proveedor de software antivirus para obtener instrucciones o para una versión actualizada del software antivirus.</span><span class="sxs-lookup"><span data-stu-id="de355-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="de355-108">Este artículo contiene información que muestra cómo ayudar a reducir la configuración de seguridad o cómo desactivar temporalmente las características de seguridad en un equipo.</span><span class="sxs-lookup"><span data-stu-id="de355-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="de355-109">Puede realizar estos cambios para comprender la naturaleza de un problema específico.</span><span class="sxs-lookup"><span data-stu-id="de355-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="de355-110">Antes de realizar estos cambios, le recomendamos que evalúe los riesgos asociados con la implementación de esta solución en su entorno concreto.</span><span class="sxs-lookup"><span data-stu-id="de355-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="de355-111">Si decide implementar esta solución alternativa, tome las medidas adicionales oportunas para ayudar a proteger el equipo para los archivos que ya no se examina el software antivirus.</span><span class="sxs-lookup"><span data-stu-id="de355-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>
  
<span data-ttu-id="de355-112">Para asegurarse de que el detector antivirus no interfiere con el funcionamiento de Skype para Business Server, debe excluir directorios y procesos específicos para cada Skype para un servidor Business Server o rol de servidor en el que ejecute un detector de virus.</span><span class="sxs-lookup"><span data-stu-id="de355-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="de355-113">Es necesario excluir los siguientes procesos y directorios:</span><span class="sxs-lookup"><span data-stu-id="de355-113">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="de355-114">Las ubicaciones de archivos y carpetas enumeradas a continuación son las ubicaciones predeterminadas de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="de355-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="de355-115">Si no usó los valores predeterminados para algunas ubicaciones, excluya esas ubicaciones especificadas para su organización en lugar de las ubicaciones predeterminadas especificadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="de355-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="de355-116">Tenga en cuenta que es posible que algunos programas antivirus necesiten rutas de acceso absolutas (no relativas) para su lista de exclusión.</span><span class="sxs-lookup"><span data-stu-id="de355-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="de355-117">Skype para los procesos del servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="de355-117">Skype for Business Server processes:</span></span>
    
  - <span data-ttu-id="de355-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="de355-118">ABServer.exe</span></span>
    
  - <span data-ttu-id="de355-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="de355-119">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="de355-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="de355-120">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="de355-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="de355-121">ChannelService.exe</span></span>
    
  - <span data-ttu-id="de355-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="de355-122">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="de355-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="de355-123">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="de355-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="de355-124">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="de355-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="de355-125">DataProxy.exe</span></span>
    
  - <span data-ttu-id="de355-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="de355-126">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="de355-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="de355-127">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="de355-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="de355-128">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="de355-129">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="de355-129">LysSvc.exe</span></span>
    
  - <span data-ttu-id="de355-130">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="de355-130">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="de355-131">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="de355-131">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="de355-132">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="de355-132">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="de355-133">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="de355-133">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="de355-134">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="de355-134">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="de355-135">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="de355-135">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="de355-136">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="de355-136">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="de355-137">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="de355-137">RtcHost.exe</span></span>
    
  - <span data-ttu-id="de355-138">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="de355-138">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="de355-139">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="de355-139">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="de355-140">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="de355-140">XmppTGW.exe</span></span>
    
- <span data-ttu-id="de355-141">Procesos del servicio de host de Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="de355-141">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="de355-142">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="de355-142">Fabric.exe</span></span>
    
  - <span data-ttu-id="de355-143">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="de355-143">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="de355-144">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="de355-144">FabricHost.exe</span></span>
    
- <span data-ttu-id="de355-145">Procesos de IIS:</span><span class="sxs-lookup"><span data-stu-id="de355-145">IIS processes:</span></span>
    
  - <span data-ttu-id="de355-146">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="de355-146">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="de355-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="de355-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="de355-148">Procesos del back-end de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="de355-148">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="de355-149">Tenga en cuenta que estas rutas dependen de la versión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de355-149">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="de355-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="de355-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="de355-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="de355-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="de355-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="de355-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="de355-153">Procesos del front-end de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="de355-153">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="de355-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="de355-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="de355-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="de355-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="de355-156">Instancia RTC de instalación Standard Edition</span><span class="sxs-lookup"><span data-stu-id="de355-156">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="de355-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="de355-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="de355-158">Directorios y archivos:</span><span class="sxs-lookup"><span data-stu-id="de355-158">Directories and files:</span></span>
    
  - <span data-ttu-id="de355-159">%systemroot%\system32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="de355-159">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="de355-160">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="de355-160">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="de355-161">%SystemRoot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="de355-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="de355-162">Tenga en cuenta que estas rutas de acceso son específicos de Skype para la versión de Business Server.</span><span class="sxs-lookup"><span data-stu-id="de355-162">Note that these paths are specific to Skype for Business Server version.</span></span> 
    
  - <span data-ttu-id="de355-163">%programfiles%\Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="de355-163">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="de355-164">%programfiles%\Common Files\Skype Empresarial Server 2015\Nodo de monitor</span><span class="sxs-lookup"><span data-stu-id="de355-164">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="de355-165">%programfiles%\Common Files\Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="de355-165">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="de355-166">%programfiles%\Common Files\Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="de355-166">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="de355-167">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="de355-167">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="de355-p105">Almacén de recurso compartido de archivos (especificado en el Generador de topologías). Los almacenes de archivos se especifican en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="de355-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="de355-170">Datos y archivos de registro de SQL Server, incluidos los relacionados con la base de datos back-end, el almacén de usuarios, el almacén de archivado, el almacén de supervisión y el almacén de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="de355-170">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="de355-171">Las bases de datos y los archivos de registro se pueden especificar en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="de355-171">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="de355-172">Para obtener información detallada acerca de los archivos de registro y datos para cada base de datos, incluidos los nombres de forma predeterminada, vea [datos de SQL Server y la ubicación del archivo de registro](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="de355-172">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="de355-173">SQL Server datos y archivos de registro, los referentes a la base de datos front-end, Skype para almacén empresariales y almacén de RtcDatabase incluidos.</span><span class="sxs-lookup"><span data-stu-id="de355-173">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="de355-174">Normalmente, se encuentran en %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="de355-174">They are normally under %localdrive%\CSData.</span></span>
    

