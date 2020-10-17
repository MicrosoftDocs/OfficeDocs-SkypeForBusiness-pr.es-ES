---
title: 'Lync Server 2013: cmdlets de conectividad de RTC'
description: 'Lync Server 2013: cmdlets de conectividad con RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity cmdlets
ms:assetid: b19ba43c-3987-410d-a704-aba0a4fb0498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415670(v=OCS.15)
ms:contentKeyID: 48185142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b36311ea2f983bb65864d13929b5052d0a408c2c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559216"
---
# <a name="pstn-connectivity-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e2f21-103">Cmdlets de conectividad RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2f21-103">PSTN connectivity cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2f21-104">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e2f21-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e2f21-105">La telefonía IP empresarial proporciona una configuración que permite realizar llamadas a y desde la red telefónica conmutada (RTC) sin que se opongan a la calidad de servicio (QoS).</span><span class="sxs-lookup"><span data-stu-id="e2f21-105">Enterprise Voice provides settings that allow for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="e2f21-106">Puede configurar estas opciones a través de los cmdlets disponibles en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2f21-106">You can configure these settings through cmdlets available from the Lync Server Management Shell.</span></span>

<div>

## <a name="pstn-connectivity-cmdlets"></a><span data-ttu-id="e2f21-107">Cmdlets de conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="e2f21-107">PSTN Connectivity Cmdlets</span></span>

<span data-ttu-id="e2f21-108">Use los cmdlets siguientes para configurar diversos aspectos de la conectividad con RTC.</span><span class="sxs-lookup"><span data-stu-id="e2f21-108">Use the following cmdlets to configure various aspects of PSTN connectivity.</span></span>

<span data-ttu-id="e2f21-109">**[Cmdlets de puertas de enlace RTC en Lync Server 2013](lync-server-2013-pstn-gateways-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e2f21-109">**[PSTN gateways cmdlets in Lync Server 2013](lync-server-2013-pstn-gateways-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-110">[Set-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-110">[Set-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-111">[Test-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-111">[Test-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-112">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-112">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-113">[Set-CsMediationServer](https://technet.microsoft.com/library/Gg398213(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-113">[Set-CsMediationServer](https://technet.microsoft.com/library/Gg398213(v=OCS.15))</span></span>

<span data-ttu-id="e2f21-114">**[Cmdlets de enrutamiento estático en Lync Server 2013](lync-server-2013-static-routing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e2f21-114">**[Static routing cmdlets in Lync Server 2013](lync-server-2013-static-routing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-115">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-115">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-116">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-116">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-117">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-117">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-118">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-118">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-119">[New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-119">[New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-120">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-120">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-121">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-121">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-122">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-122">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-123">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-123">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-124">[New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-124">[New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-125">[New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-125">[New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-126">[New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-126">[New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-127">[New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-127">[New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-128">[New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-128">[New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-129">[New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-129">[New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-130">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-130">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-131">[New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-131">[New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))</span></span>

<span data-ttu-id="e2f21-132">**[Cmdlets de configuración de tronco en Lync Server 2013](lync-server-2013-trunking-configuration-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e2f21-132">**[Trunking configuration cmdlets in Lync Server 2013](lync-server-2013-trunking-configuration-cmdlets.md)**</span></span>

  - <span data-ttu-id="e2f21-133">[Test-CsInterTrunkRouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-133">[Test-CsInterTrunkRouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e2f21-134">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-134">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))</span></span>

  - <span data-ttu-id="e2f21-135">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-135">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))</span></span>

  - <span data-ttu-id="e2f21-136">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-136">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))</span></span>

  - <span data-ttu-id="e2f21-137">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-137">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-138">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-138">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-139">[New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-139">[New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-140">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-140">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-141">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-141">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e2f21-142">[Get-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-142">[Get-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-143">[Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-143">[Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-144">[New-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-144">[New-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-145">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-145">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-146">[Set-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-146">[Set-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-147">[Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-147">[Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-148">[New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-148">[New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span></span>

<span data-ttu-id="e2f21-149">**[Cmdlets de enrutamiento de voz en Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e2f21-149">**[Voice routing cmdlets in Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-150">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-150">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-151">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-151">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-152">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-152">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-153">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-153">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e2f21-154">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-154">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-155">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-155">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-156">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-156">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-157">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-157">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e2f21-158">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2f21-158">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2f21-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2f21-159">See Also</span></span>


[<span data-ttu-id="e2f21-160">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2f21-160">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

