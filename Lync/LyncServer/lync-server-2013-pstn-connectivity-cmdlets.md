---
title: 'Lync Server 2013: cmdlets de conectividad RTC'
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
ms.openlocfilehash: cf6adeec7b2a1cd3e73d60b918a68b2d31c48f3c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-cmdlets-in-lync-server-2013"></a><span data-ttu-id="0cc8b-102">Cmdlets de conectividad RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cc8b-102">PSTN connectivity cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cc8b-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="0cc8b-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0cc8b-104">Telefonía IP empresarial proporciona una configuración que permite realizar llamadas a la red de telefonía pública conmutada (RTC) y a la misma sin que se produzca ninguna disminución de calidad de servicio (QoS).</span><span class="sxs-lookup"><span data-stu-id="0cc8b-104">Enterprise Voice provides settings that allow for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="0cc8b-105">Puede configurar estas opciones mediante cmdlets disponibles en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0cc8b-105">You can configure these settings through cmdlets available from the Lync Server Management Shell.</span></span>

<div>

## <a name="pstn-connectivity-cmdlets"></a><span data-ttu-id="0cc8b-106">Cmdlets de conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="0cc8b-106">PSTN Connectivity Cmdlets</span></span>

<span data-ttu-id="0cc8b-107">Use los siguientes cmdlets para configurar diversos aspectos de la conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="0cc8b-107">Use the following cmdlets to configure various aspects of PSTN connectivity.</span></span>

<span data-ttu-id="0cc8b-108">**[Cmdlets de puertas de enlace RTC en Lync Server 2013](lync-server-2013-pstn-gateways-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0cc8b-108">**[PSTN gateways cmdlets in Lync Server 2013](lync-server-2013-pstn-gateways-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-109">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-109">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-110">[Prueba-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-110">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-111">[Prueba-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-111">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-112">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-112">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span></span>

<span data-ttu-id="0cc8b-113">**[Cmdlets de enrutamiento estático en Lync Server 2013](lync-server-2013-static-routing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0cc8b-113">**[Static routing cmdlets in Lync Server 2013](lync-server-2013-static-routing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-114">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-114">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-115">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-115">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-116">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-116">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-117">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-117">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-118">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-118">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-119">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-119">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-120">[Nuevo: CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-120">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-121">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-121">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-122">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-122">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-123">[Nuevo: CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-123">[New-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-124">[Nuevo: CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-124">[New-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-125">[Nuevo: CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-125">[New-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-126">[Nuevo: CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-126">[New-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-127">[Nuevo: CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-127">[New-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-128">[Nuevo: CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-128">[New-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-129">[Nuevo: CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-129">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-130">[Nuevo: CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-130">[New-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span></span>

<span data-ttu-id="0cc8b-131">**[Cmdlets de configuración de Troncalización en Lync Server 2013](lync-server-2013-trunking-configuration-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0cc8b-131">**[Trunking configuration cmdlets in Lync Server 2013](lync-server-2013-trunking-configuration-cmdlets.md)**</span></span>

  - <span data-ttu-id="0cc8b-132">[Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-132">[Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0cc8b-133">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-133">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))</span></span>

  - <span data-ttu-id="0cc8b-134">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-134">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))</span></span>

  - <span data-ttu-id="0cc8b-135">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-135">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))</span></span>

  - <span data-ttu-id="0cc8b-136">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-136">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-137">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-137">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-138">[Nuevo: CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-138">[New-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-139">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-139">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-140">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-140">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0cc8b-141">[Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-141">[Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-142">[Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-142">[Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-143">[Nuevo: CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-143">[New-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-144">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-144">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-145">[Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-145">[Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-146">[Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-146">[Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-147">[Nuevo: CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-147">[New-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span></span>

<span data-ttu-id="0cc8b-148">**[Cmdlets de enrutamiento de voz en Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0cc8b-148">**[Voice routing cmdlets in Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-149">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-149">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-150">[Nuevo: CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-150">[New-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-151">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-151">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-152">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-152">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0cc8b-153">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-153">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-154">[Nuevo: CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-154">[New-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-155">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-155">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-156">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-156">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0cc8b-157">[Prueba-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0cc8b-157">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0cc8b-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cc8b-158">See Also</span></span>


[<span data-ttu-id="0cc8b-159">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="0cc8b-159">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

