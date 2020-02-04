---
title: 'Lync Server 2013: mensajería instantánea y cmdlets de presencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d96b8971bb25898e9e8b02403b0f8cd5447681c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2cd34-102">Cmdlets de presencia y mensajería instantánea en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd34-102">IM and presence cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cd34-103">_**Última modificación del tema:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="2cd34-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="2cd34-104">Los cmdlets de presencia y mensajería instantánea le permiten administrar dichas características de cliente a través de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cd34-104">Instant Messaging (IM) and presence cmdlets allow you to manage those client features through Windows PowerShell.</span></span> <span data-ttu-id="2cd34-105">Puede establecer directivas de presencia que se apliquen a los usuarios en el ámbito global, de sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="2cd34-105">You can set presence policies that apply to users at the global, site, or per-user scope.</span></span> <span data-ttu-id="2cd34-106">También puede configurar diversas características de privacidad y mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="2cd34-106">You can also configure various privacy and IM features.</span></span>

<div>

## <a name="im-and-presence-cmdlets"></a><span data-ttu-id="2cd34-107">Cmdlets de presencia y mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="2cd34-107">IM and Presence Cmdlets</span></span>

<span data-ttu-id="2cd34-108">Para configurar la mensajería instantánea y la presencia, use los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="2cd34-108">The configure IM and presence, use the following cmdlets:</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-109">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-109">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-110">[Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-110">[Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-111">[New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-111">[New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-112">[Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-112">[Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-113">[Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-113">[Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2cd34-114">[Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-114">[Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))</span></span>

  - <span data-ttu-id="2cd34-115">[New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-115">[New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))</span></span>

  - <span data-ttu-id="2cd34-116">[Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-116">[Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))</span></span>

  - <span data-ttu-id="2cd34-117">[Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-117">[Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cd34-118">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-118">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-119">[Nuevo: CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-119">[New-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-120">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-120">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-121">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-121">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cd34-122">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-122">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cd34-123">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-123">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-124">[Nuevo: CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-124">[New-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-125">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-125">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-126">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-126">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cd34-127">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-127">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-128">[Nuevo: CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-128">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-129">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-129">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-130">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-130">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cd34-131">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-131">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-132">[Nuevo: CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-132">[New-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-133">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-133">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cd34-134">[Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-134">[Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cd34-135">[Prueba-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-135">[Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cd34-136">[Prueba-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-136">[Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cd34-137">[Prueba-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-137">[Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cd34-138">[Prueba-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-138">[Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cd34-139">[Prueba-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cd34-139">[Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2cd34-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cd34-140">See Also</span></span>


[<span data-ttu-id="2cd34-141">Cmdlets de administración de clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd34-141">Client management cmdlets in Lync Server 2013</span></span>](lync-server-2013-client-management-cmdlets.md)  


[<span data-ttu-id="2cd34-142">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cd34-142">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

