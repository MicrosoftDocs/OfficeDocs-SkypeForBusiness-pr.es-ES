---
title: 'Lync Server 2013: cmdlets de directiva de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policy cmdlets
ms:assetid: 92744ec6-754d-498b-b430-dcd5c985ce10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415663(v=OCS.15)
ms:contentKeyID: 48184800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63846183479c8b81091f5d0bc81a68874d8201f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voice-policy-cmdlets-in-lync-server-2013"></a><span data-ttu-id="67c28-102">Cmdlets de directiva de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67c28-102">Voice policy cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67c28-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="67c28-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="67c28-p101">Managing Enterprise Voice posibilita la configuración de elementos como las directivas de voz y los planes de marcado, además de la asociación de directivas de voz con rutas de voz. Los cmdlets relativos a la administración de directivas de voz pueden usarse para definir características como las llamadas simultáneas (la posibilidad de recibir una segunda llamada cada vez que alguien llama al número de una oficina), el desvío de llamadas y el requisito de marcado.</span><span class="sxs-lookup"><span data-stu-id="67c28-p101">Managing Enterprise Voice includes configuring such things as voice policies and dial plans, and associating voice policies with voice routes. Cmdlets related to managing voice policies can be used to set features such as simultaneous ringing (the ability to have a second phone ring each time someone calls your office phone), call forwarding, and dialing requirement.</span></span>

<div>

## <a name="voice-policy-cmdlets"></a><span data-ttu-id="67c28-106">Cmdlets de directivas de voz</span><span class="sxs-lookup"><span data-stu-id="67c28-106">Voice Policy Cmdlets</span></span>

<span data-ttu-id="67c28-107">Los cmdlets siguientes pueden usarse para administrar directivas de voz y planes de marcado para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="67c28-107">The following cmdlets can be used to manage voice policies and dial plans for Enterprise Voice.</span></span>

<span data-ttu-id="67c28-108">**Directiva de voz**</span><span class="sxs-lookup"><span data-stu-id="67c28-108">**Voice Policy**</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-109">[Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-109">[Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-110">[Grant-CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-110">[Grant-CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-111">[New-CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-111">[New-CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-112">[Remove-CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-112">[Remove-CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-113">[Set-CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-113">[Set-CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-114">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-114">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="67c28-115">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-115">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-116">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-116">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="67c28-117">[Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-117">[Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-118">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-118">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-119">[New-CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-119">[New-CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-121">[Set-CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-121">[Set-CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="67c28-122">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67c28-122">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67c28-123">Consulta también</span><span class="sxs-lookup"><span data-stu-id="67c28-123">See Also</span></span>


[<span data-ttu-id="67c28-124">Cmdlets de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67c28-124">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="67c28-125">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="67c28-125">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

