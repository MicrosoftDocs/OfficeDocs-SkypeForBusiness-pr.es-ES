---
title: 'Lync Server 2013: cmdlets de Federación y de acceso externo'
description: 'Lync Server 2013: cmdlets de Federación y de acceso externo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 930de66a54d3f8db07394baf2d8470affe5090e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543396"
---
# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a><span data-ttu-id="96afd-103">Cmdlets de Federación y acceso externo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96afd-103">Federation and external access cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96afd-104">_**Última modificación del tema:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="96afd-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="96afd-105">La Federación y el acceso externo proporcionan dos capacidades importantes: la Federación permite a los usuarios comunicarse con personas de fuera de la organización, mientras que el acceso externo permite que los usuarios se conecten a Microsoft Lync Server 2013 desde fuera de la red interna.</span><span class="sxs-lookup"><span data-stu-id="96afd-105">Federation and external access provide two important capabilities: federation enables users to communicate with people outside your organization, while external access enables users to connect to Microsoft Lync Server 2013 from outside the internal network.</span></span> <span data-ttu-id="96afd-106">Los cmdlets disponibles para administrar la Federación y el acceso externo en Lync Server 2013 le permiten determinar quiénes son los usuarios que pueden comunicarse (y cuáles no) y determinan si los usuarios pueden conectarse a Lync Server sin tener que iniciar sesión en la red interna.</span><span class="sxs-lookup"><span data-stu-id="96afd-106">The cmdlets available for managing federation and external access in Lync Server 2013 let you determine who your users can (and cannot) communicate with, and determine whether or not those users can connect to Lync Server without having to log on to the internal network.</span></span>

<div>

## <a name="federation-and-external-access-cmdlets"></a><span data-ttu-id="96afd-107">Cmdlets de federación y acceso externo</span><span class="sxs-lookup"><span data-stu-id="96afd-107">Federation and External Access Cmdlets</span></span>

<span data-ttu-id="96afd-108">La mayoría de las tareas de administración que se aplican a la Federación y el acceso externo se pueden realizar desde el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96afd-108">Most management tasks that apply to federation and external access can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="96afd-109">Estas mismas tareas se pueden realizar con cmdlets desde el shell de administración de Lync Server o desde una secuencia de comandos; el uso de un script permite automatizar determinadas tareas.</span><span class="sxs-lookup"><span data-stu-id="96afd-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="96afd-110">A continuación se presenta una lista de cmdlets directamente relacionados con la administración del acceso externo y la federación:</span><span class="sxs-lookup"><span data-stu-id="96afd-110">The following is a list of cmdlets that relate directly to managing federation and external access:</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-111">[Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-111">[Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-112">[New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-112">[New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-113">[Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-113">[Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-114">[Set-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-114">[Set-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="96afd-115">[Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-115">[Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-116">[New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-116">[New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-117">[Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-117">[Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-118">[Set-CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-118">[Set-CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="96afd-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-120">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-120">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-121">[New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-121">[New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-122">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-122">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-123">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-123">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="96afd-124">[Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-124">[Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))</span></span>

  - <span data-ttu-id="96afd-125">[New-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-125">[New-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))</span></span>

  - <span data-ttu-id="96afd-126">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-126">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))</span></span>

  - <span data-ttu-id="96afd-127">[Set-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-127">[Set-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="96afd-128">[Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-128">[Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-129">[Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-129">[Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-130">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-130">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-131">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-131">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-132">[Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-132">[Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-133">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-133">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="96afd-134">[Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-134">[Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-135">[Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-135">[Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-136">[Get-CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-136">[Get-CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-137">[New-CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-137">[New-CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-138">[Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-138">[Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="96afd-139">[Set-CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-139">[Set-CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="96afd-140">[Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-140">[Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="96afd-141">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-141">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>

  - <span data-ttu-id="96afd-142">[New-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-142">[New-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))</span></span>

  - <span data-ttu-id="96afd-143">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-143">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))</span></span>

  - <span data-ttu-id="96afd-144">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-144">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="96afd-145">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-145">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>

  - <span data-ttu-id="96afd-146">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-146">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="96afd-147">[Test-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96afd-147">[Test-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="96afd-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96afd-148">See Also</span></span>


[<span data-ttu-id="96afd-149">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="96afd-149">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

