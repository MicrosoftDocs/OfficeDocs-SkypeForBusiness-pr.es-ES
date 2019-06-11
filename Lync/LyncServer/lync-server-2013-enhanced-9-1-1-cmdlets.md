---
title: 'Lync Server 2013: cmdlets de 9-1-1 mejorados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enhanced 9-1-1 cmdlets
ms:assetid: e560c688-7b34-4bd7-8104-24f390644105
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415678(v=OCS.15)
ms:contentKeyID: 48185650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 674f74d9027789c63d76b8d8f280099b596b62b4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-cmdlets-in-lync-server-2013"></a><span data-ttu-id="47a23-102">Cmdlets de 9-1-1 mejorados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47a23-102">Enhanced 9-1-1 cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47a23-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="47a23-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="47a23-104">Microsoft Lync Server 2013 incluye cmdlets que le permiten implementar y administrar la implementación mejorada de 9-1-1 (E9-1-1) de una solución de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="47a23-104">Microsoft Lync Server 2013 ships with cmdlets that allow you to implement and manage the Enhanced 9-1-1 (E9-1-1) implementation of an Enterprise Voice solution.</span></span> <span data-ttu-id="47a23-105">Use estos cmdlets para asignar puntos de conexión a direcciones físicas y para configurar la configuración necesaria para que los usuarios de telefonía IP completen correctamente las llamadas de emergencia y envíen automáticamente una ubicación al proveedor de servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="47a23-105">Use these cmdlets to map connection points to physical addresses and to configure settings required for Enterprise Voice users to successfully complete emergency calls and automatically send a location to the emergency services provider.</span></span> <span data-ttu-id="47a23-106">No puede configurar E9-1-1 desde el panel de control de Lync Server, debe usar cmdlets.</span><span class="sxs-lookup"><span data-stu-id="47a23-106">You cannot configure E9-1-1 from the Lync Server Control Panel, you must use cmdlets.</span></span>

<div>

## <a name="enhanced-9-1-1-cmdlets"></a><span data-ttu-id="47a23-107">Cmdlets de 9-1-1 mejorados</span><span class="sxs-lookup"><span data-stu-id="47a23-107">Enhanced 9-1-1 Cmdlets</span></span>

<span data-ttu-id="47a23-108">Use los siguientes cmdlets para configurar E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="47a23-108">Use the following cmdlets to configure E9-1-1.</span></span>

<span data-ttu-id="47a23-109">**9-1-1 mejorado**</span><span class="sxs-lookup"><span data-stu-id="47a23-109">**Enhanced 9-1-1**</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-110">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-110">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-111">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-111">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-112">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-112">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47a23-113">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-113">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-114">[Prueba-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-114">[Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47a23-115">[Exportar-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-115">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-116">[Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-116">[Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-117">[Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-117">[Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-118">[Prueba-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-118">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-119">[Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-119">[Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-120">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-120">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47a23-121">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-121">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-122">[Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-122">[Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-123">[Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-123">[Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47a23-124">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-124">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-125">[Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-125">[Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-126">[Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-126">[Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47a23-127">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-127">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-128">[Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-128">[Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-129">[Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-129">[Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47a23-130">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-130">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-131">[Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-131">[Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-132">[Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-132">[Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47a23-133">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-133">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-134">[Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-134">[Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-135">[Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-135">[Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47a23-136">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-136">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-137">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-137">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-138">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-138">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47a23-139">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-139">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-140">[Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-140">[Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-141">[Nuevo: CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-141">[New-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-142">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-142">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-143">[Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-143">[Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-144">[Prueba-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-144">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="47a23-145">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-145">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-146">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-146">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-147">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-147">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="47a23-148">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="47a23-148">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47a23-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="47a23-149">See Also</span></span>


[<span data-ttu-id="47a23-150">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="47a23-150">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

