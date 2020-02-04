---
title: 'Lync Server 2013: cmdlets de servicios y roles de servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles and services cmdlets
ms:assetid: ff3561de-043e-4071-88f7-8de3cded52f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415683(v=OCS.15)
ms:contentKeyID: 48185971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f59ff1b76b2381c611f07f09bbdaabcdc5e4a69b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="fb6f0-102">Cmdlets de servicios y roles de servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb6f0-102">Server roles and services cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb6f0-103">_**Última modificación del tema:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="fb6f0-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="fb6f0-104">Muchos componentes de Microsoft Lync Server 2013 se ejecutan como roles de servidor o como servicios.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-104">Many Microsoft Lync Server 2013 components run as server roles or as services.</span></span> <span data-ttu-id="fb6f0-105">Lync Server 2013 incluye varios cmdlets que le permiten administrar estos roles y servicios de servidor.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-105">Lync Server 2013 ships with a number of cmdlets that enable you to manage these server roles and services.</span></span>

<div>

## <a name="server-roles-and-services-cmdlets"></a><span data-ttu-id="fb6f0-106">Cmdlets de servicios y roles de servidor</span><span class="sxs-lookup"><span data-stu-id="fb6f0-106">Server Roles and Services Cmdlets</span></span>

<span data-ttu-id="fb6f0-107">Muchas (pero no todas) las tareas de administración que se aplican a los servidores y roles de servicio se pueden realizar desde el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-107">Many (but not all) of the management tasks that apply to servers and service roles can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="fb6f0-108">Por ejemplo, puede administrar la configuración del servidor de archivado, pero no la de la libreta de direcciones, mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-108">For example, you can manage Archiving Server settings but not Address Book Server settings by using Lync Server Control Panel.</span></span> <span data-ttu-id="fb6f0-109">Sin embargo, todas estas tareas se pueden realizar con cmdlets desde el shell de administración de Lync Server o desde una secuencia de comandos; el uso de una secuencia de comandos le permite automatizar determinadas tareas.</span><span class="sxs-lookup"><span data-stu-id="fb6f0-109">However, all these tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="fb6f0-110">A continuación se muestra una lista de cmdlets que se relacionan directamente con la administración de roles y servicios de servidor:</span><span class="sxs-lookup"><span data-stu-id="fb6f0-110">The following is a list of cmdlets that relate directly to managing server roles and services:</span></span>

<span data-ttu-id="fb6f0-111">**[Cmdlets del servidor de la libreta de direcciones en Lync Server 2013](lync-server-2013-address-book-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="fb6f0-111">**[Address Book Server cmdlets in Lync Server 2013](lync-server-2013-address-book-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-112">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-112">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-113">[Nuevo: CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-113">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-114">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-114">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-115">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-115">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-116">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-116">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-117">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-117">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-118">[Prueba-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-118">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-119">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-119">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span></span>

<span data-ttu-id="fb6f0-120">**[Cmdlets de archivado y supervisión en Lync Server 2013](lync-server-2013-archiving-and-monitoring-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="fb6f0-120">**[Archiving and Monitoring cmdlets in Lync Server 2013](lync-server-2013-archiving-and-monitoring-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-121">[Get-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-121">[Get-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-122">[Nuevo: CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-122">[New-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-123">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-123">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-124">[Set-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-124">[Set-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-125">[Exportar-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-125">[Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-126">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-126">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-127">[Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-127">[Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-128">[Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-128">[Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-129">[Nuevo: CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-129">[New-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-130">[Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-130">[Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-131">[Set-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-131">[Set-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-132">[Set-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-132">[Set-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-133">[Get-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-133">[Get-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-134">[Nuevo: CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-134">[New-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-135">[Remove-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-135">[Remove-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-136">[Set-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-136">[Set-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-137">[Set-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-137">[Set-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-138">[Get-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-138">[Get-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-139">[Nuevo: CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-139">[New-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-140">[Remove-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-140">[Remove-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-141">[Set-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-141">[Set-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))</span></span>

<span data-ttu-id="fb6f0-142">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-142">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-143">[Exportar-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-143">[Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-144">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-144">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-145">[Get-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-145">[Get-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-146">[New-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-146">[New-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-147">[Remove-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-147">[Remove-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-148">[Set-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-148">[Set-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-149">[Get-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-149">[Get-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-150">[Remove-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-150">[Remove-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-151">[Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-151">[Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-152">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-152">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-153">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-153">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-154">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-154">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-155">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-155">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-156">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-156">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-157">[New-CsExtendedTest](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-157">[New-CsExtendedTest](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))</span></span>

<span data-ttu-id="fb6f0-158">**[Cmdlets de servidores de administración y bases de datos en Lync Server 2013](lync-server-2013-database-and-management-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="fb6f0-158">**[Database and Management Server cmdlets in Lync Server 2013](lync-server-2013-database-and-management-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-159">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-159">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-160">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-160">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-161">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-161">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-162">[Install-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-162">[Install-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-163">[Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-163">[Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-164">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-164">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="fb6f0-165">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-165">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="fb6f0-166">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-166">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="fb6f0-167">[Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-167">[Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="fb6f0-168">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-168">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-169">[Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-169">[Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-170">[Set-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-170">[Set-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-171">[Update-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-171">[Update-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-172">[Move-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-172">[Move-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-173">[Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-173">[Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="fb6f0-174">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-174">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))</span></span>

<span data-ttu-id="fb6f0-175">**[Cmdlets de servidor perimetral en Lync Server 2013](lync-server-2013-edge-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="fb6f0-175">**[Edge Server cmdlets in Lync Server 2013](lync-server-2013-edge-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-176">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-176">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-177">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-177">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-178">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-178">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-179">[Nuevo: CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-179">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-180">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-180">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-181">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-181">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-182">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-182">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-183">[Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-183">[Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span></span>

<span data-ttu-id="fb6f0-184">**[Otros cmdlets de roles de servidor en Lync Server 2013](lync-server-2013-other-server-role-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="fb6f0-184">**[Other server role cmdlets in Lync Server 2013](lync-server-2013-other-server-role-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-185">[Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-185">[Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-186">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-186">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span></span>

<span data-ttu-id="fb6f0-187">**[Cmdlets de registrador y Director en Lync Server 2013](lync-server-2013-registrar-and-director-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="fb6f0-187">**[Registrar and Director cmdlets in Lync Server 2013](lync-server-2013-registrar-and-director-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-188">[Set-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-188">[Set-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-189">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/en-us/library/JJ619172(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-189">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/en-us/library/JJ619172(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-190">[Set-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-190">[Set-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-191">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-191">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-192">[Nuevo: CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-192">[New-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-193">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-193">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-194">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-194">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-195">[Prueba-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-195">[Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))</span></span>

<span data-ttu-id="fb6f0-196">**[Cmdlets de servicios en Lync Server 2013](lync-server-2013-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="fb6f0-196">**[Services cmdlets in Lync Server 2013](lync-server-2013-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-197">[Get-CsService](https://technet.microsoft.com/en-us/library/Gg413038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-197">[Get-CsService](https://technet.microsoft.com/en-us/library/Gg413038(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-198">[Get-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-198">[Get-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398803(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-199">[Start-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398561(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-199">[Start-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398561(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-200">[Stop-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398426(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-200">[Stop-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398426(v=OCS.15))</span></span>

<span data-ttu-id="fb6f0-201">**[Solución de problemas de roles de servidor y cmdlets de servicios en Lync Server 2013](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="fb6f0-201">**[Troubleshooting server roles and services cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-202">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-202">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-203">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-203">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-204">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-204">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-205">[Nuevo: CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-205">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-206">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-206">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-207">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-207">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-208">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-208">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-209">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-209">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-210">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-210">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-211">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-211">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-212">[Nuevo: CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-212">[New-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-213">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-213">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-214">[Nuevo: CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-214">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-215">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-215">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-216">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-216">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span></span>

<span data-ttu-id="fb6f0-217">**[Cmdlets de servicios y servidores Web en Lync Server 2013](lync-server-2013-web-server-and-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="fb6f0-217">**[Web server and services cmdlets in Lync Server 2013](lync-server-2013-web-server-and-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-218">[Nuevo: CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-218">[New-CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-219">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-219">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-220">[Nuevo: CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-220">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-221">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-221">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-222">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-222">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-223">[Nuevo: CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-223">[New-CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-224">[Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-224">[Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-225">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-225">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-226">[Nuevo: CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-226">[New-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-227">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-227">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-228">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-228">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-229">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-229">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-230">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-230">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-231">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-231">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-232">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-232">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-233">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-233">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-234">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-234">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fb6f0-235">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-235">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fb6f0-236">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-236">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="fb6f0-237">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-237">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="fb6f0-238">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fb6f0-238">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb6f0-239">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb6f0-239">See Also</span></span>


[<span data-ttu-id="fb6f0-240">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb6f0-240">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

