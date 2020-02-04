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
ms.openlocfilehash: 00f45a7da053dd6dc150ae99e93b780117ba01e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policy-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e6a70-102">Cmdlets de directiva de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6a70-102">Voice policy cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6a70-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="e6a70-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="e6a70-104">La administración de la telefonía IP empresarial incluye configurar aspectos como directivas de voz y planes de marcado, y asociar directivas de voz con rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="e6a70-104">Managing Enterprise Voice includes configuring such things as voice policies and dial plans, and associating voice policies with voice routes.</span></span> <span data-ttu-id="e6a70-105">Los cmdlets relacionados con la administración de directivas de voz se pueden usar para establecer características como el timbre simultáneo (la posibilidad de tener un segundo timbre telefónico cada vez que alguien llame a su teléfono de la oficina), el desvío de llamadas y el requisito de marcado.</span><span class="sxs-lookup"><span data-stu-id="e6a70-105">Cmdlets related to managing voice policies can be used to set features such as simultaneous ringing (the ability to have a second phone ring each time someone calls your office phone), call forwarding, and dialing requirement.</span></span>

<div>

## <a name="voice-policy-cmdlets"></a><span data-ttu-id="e6a70-106">Cmdlets de directiva de voz</span><span class="sxs-lookup"><span data-stu-id="e6a70-106">Voice Policy Cmdlets</span></span>

<span data-ttu-id="e6a70-107">Los siguientes cmdlets se pueden usar para administrar directivas de voz y planes de marcado para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="e6a70-107">The following cmdlets can be used to manage voice policies and dial plans for Enterprise Voice.</span></span>

<span data-ttu-id="e6a70-108">**Directiva de voz 1**</span><span class="sxs-lookup"><span data-stu-id="e6a70-108">**Voice Policy**</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-109">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-109">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-110">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-110">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-111">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-111">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-112">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-112">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-113">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-113">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-114">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-114">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e6a70-115">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-115">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-116">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-116">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e6a70-117">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-117">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-118">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-118">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-119">[Nuevo: CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-119">[New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-121">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-121">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e6a70-122">[Prueba-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e6a70-122">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6a70-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6a70-123">See Also</span></span>


[<span data-ttu-id="e6a70-124">Cmdlets de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6a70-124">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="e6a70-125">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6a70-125">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

