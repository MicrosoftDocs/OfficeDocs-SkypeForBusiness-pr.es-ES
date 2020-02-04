---
title: 'Lync Server 2013: cmdlets de conferencias de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing cmdlets
ms:assetid: 0718f82a-91c4-466f-8443-a85002deaa48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415630(v=OCS.15)
ms:contentKeyID: 48183320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110bd0b96f16c986cffeaffc58085e597a44bd47
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="200ff-102">Cmdlets de conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="200ff-102">Dial-in conferencing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="200ff-103">_**Última modificación del tema:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="200ff-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="200ff-104">Las conferencias de acceso telefónico local proporcionan a los usuarios un modo de usar un teléfono "normal" (es decir, un dispositivo de la red de telefonía pública conmutada) para unirse a la parte de audio de una conferencia.</span><span class="sxs-lookup"><span data-stu-id="200ff-104">Dial-in conferencing provides a way for users to use a "regular" telephone (that is, a device on the public switched telephone network) to join the audio portion of a conference.</span></span>

<div>

## <a name="dial-in-conferencing-cmdlets"></a><span data-ttu-id="200ff-105">Cmdlets de conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="200ff-105">Dial-In Conferencing Cmdlets</span></span>

<span data-ttu-id="200ff-106">Si no desea permitir las conferencias de acceso telefónico local, puede deshabilitar esta función con el cmdlet Set-CsConferencingPolicy y establecer la propiedad EnableDialInConferencing en false.</span><span class="sxs-lookup"><span data-stu-id="200ff-106">If you do not want to allow dial-in conferencing you can disable this capability by using the Set-CsConferencingPolicy cmdlet and setting the EnableDialInConferencing property to False.</span></span> <span data-ttu-id="200ff-107">De forma predeterminada, todos los usuarios pueden hospedar reuniones que incluyan conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="200ff-107">By default, all users are allowed to host meetings that include dial-in conferencing.</span></span>

<span data-ttu-id="200ff-108">**Conferencias de acceso telefónico local**</span><span class="sxs-lookup"><span data-stu-id="200ff-108">**Dial-In Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-109">[Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-109">[Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-110">[Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-110">[Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-111">[New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-111">[New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-112">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-112">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="200ff-113">[Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-113">[Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="200ff-114">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-114">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-115">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-115">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-116">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-116">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-117">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-117">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="200ff-118">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-118">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-119">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-119">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-120">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-120">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-121">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-121">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="200ff-122">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-122">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-123">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-123">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-124">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-124">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="200ff-125">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-125">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="200ff-126">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="200ff-126">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="200ff-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="200ff-127">See Also</span></span>


[<span data-ttu-id="200ff-128">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="200ff-128">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

