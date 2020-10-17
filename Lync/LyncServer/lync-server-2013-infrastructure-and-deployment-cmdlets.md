---
title: 'Lync Server 2013: cmdlets de infraestructura e implementación'
description: 'Lync Server 2013: cmdlets de infraestructura e implementación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Infrastructure and deployment cmdlets
ms:assetid: 0a6e872a-9f70-4f23-a4a5-8820dbf55370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398153(v=OCS.15)
ms:contentKeyID: 48183364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcd527d804422bbed28d63d320c267a85068e61d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552756"
---
# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c8cf4-103">Cmdlets de infraestructura e implementación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8cf4-103">Infrastructure and deployment cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8cf4-104">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="c8cf4-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="c8cf4-105">Los cmdlets de infraestructura e implementación incluidos en Microsoft Lync Server 2013 pueden ser útiles en la configuración e implementación inicial del producto; después de implementar Lync Server, estos cmdlets pueden usarse para hacer cosas como comprobar que los componentes funcionan según lo esperado; administrar la configuración de replicación; y hacer una copia de seguridad y restaurar la topología, las directivas y las opciones de configuración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8cf4-105">The infrastructure and deployment cmdlets included in Microsoft Lync Server 2013 can be useful in the initial setup and deployment of the product; after Lync Server has been deployed these cmdlets can then be used to do such things as verify that components are working as expected; manage replication settings; and backup and restore the Lync Server topology, policies, and configuration settings.</span></span>

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a><span data-ttu-id="c8cf4-106">Cmdlets de implementación e infraestructura</span><span class="sxs-lookup"><span data-stu-id="c8cf4-106">Infrastructure and Deployment Cmdlets</span></span>

<span data-ttu-id="c8cf4-107">Los administradores rara vez tendrán que llamar directamente a muchas de la infraestructura y la implementación.</span><span class="sxs-lookup"><span data-stu-id="c8cf4-107">Administrators will rarely need to directly call many of the infrastructure and deployment.</span></span> <span data-ttu-id="c8cf4-108">Esto se debe a que estos cmdlets se invocan automáticamente cuando se ejecuta el programa de instalación o el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="c8cf4-108">That is because these cmdlets are automatically invoked when you run Setup or the Topology Builder.</span></span> <span data-ttu-id="c8cf4-109">(Una excepción importante podría ser el cmdlet **Export-CsConfiguration** , que permite realizar una copia de seguridad de la topología, las directivas y las opciones de configuración de Lync Server). Sin embargo, y cuando sea necesario, los cmdlets de infraestructura e implementación también se pueden ejecutar desde el shell de administración de Lync Server o desde una secuencia de comandos; el uso de un script permite automatizar determinadas tareas.</span><span class="sxs-lookup"><span data-stu-id="c8cf4-109">(One major exception might be the **Export-CsConfiguration** cmdlet, which enables you to make a backup copy of your Lync Server topology, policies, and configuration settings.) However, and when needed, the infrastructure and deployment cmdlets can also be run from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="c8cf4-110">A continuación se muestra una lista de cmdlets directamente relacionados con la infraestructura y la implementación:</span><span class="sxs-lookup"><span data-stu-id="c8cf4-110">The following is a list of cmdlets that relate directly to infrastructure and deployment:</span></span>

<span data-ttu-id="c8cf4-111">**[Cmdlets de Active Directory en Lync Server 2013](lync-server-2013-active-directory-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="c8cf4-111">**[Active Directory cmdlets in Lync Server 2013](lync-server-2013-active-directory-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-112">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-112">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-113">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-113">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-114">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-114">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-115">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-115">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-116">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-116">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-117">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-117">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-118">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-118">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-119">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-119">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

<span data-ttu-id="c8cf4-120">**[Cmdlets de replicación en Lync Server 2013](lync-server-2013-replication-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="c8cf4-120">**[Replication cmdlets in Lync Server 2013](lync-server-2013-replication-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-121">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-121">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-122">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-122">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-123">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-123">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-124">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-124">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-125">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-125">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-126">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-126">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-127">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-127">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-128">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-128">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-129">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-129">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

<span data-ttu-id="c8cf4-130">**[Cmdlets de topología Jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="c8cf4-130">**[Topology cmdlets jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-131">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-131">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-132">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-132">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-133">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-133">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-134">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-134">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-135">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-135">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-136">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-136">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-137">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-137">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-138">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-138">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-139">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-139">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-140">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-140">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-141">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-141">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-142">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-142">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-143">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-143">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c8cf4-144">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-144">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c8cf4-145">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-145">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

<span data-ttu-id="c8cf4-146">**[Cmdlets de copia de seguridad y alta disponibilidad en Lync Server 2013](lync-server-2013-backup-and-high-availability-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="c8cf4-146">**[Backup and high availability cmdlets in Lync Server 2013](lync-server-2013-backup-and-high-availability-cmdlets.md)**</span></span>

  - <span data-ttu-id="c8cf4-147">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-147">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="c8cf4-148">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-148">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="c8cf4-149">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-149">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-150">[Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-150">[Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-151">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-151">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-152">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-152">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-153">[Copia de seguridad de CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-153">[Backup-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-154">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-154">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-155">[Get-CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-155">[Get-CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-156">[Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-156">[Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-157">[Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-157">[Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-158">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-158">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-159">[Invoke-CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-159">[Invoke-CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-160">[Sync-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-160">[Sync-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c8cf4-161">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8cf4-161">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8cf4-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8cf4-162">See Also</span></span>


[<span data-ttu-id="c8cf4-163">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8cf4-163">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

