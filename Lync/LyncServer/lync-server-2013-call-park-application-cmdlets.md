---
title: 'Lync Server 2013: cmdlets de aplicación de estacionamiento de llamadas'
description: 'Lync Server 2013: cmdlets de aplicación de estacionamiento de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park application cmdlets
ms:assetid: 30cc001f-b29e-4d44-bad7-65e1133e67b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415639(v=OCS.15)
ms:contentKeyID: 48183764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25d37e8cfad022e9e8478e68f158e1838bdcca5b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570096"
---
# <a name="call-park-application-cmdlets-in-lync-server-2013"></a><span data-ttu-id="8b13d-103">Cmdlets de aplicación de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b13d-103">Call Park application cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b13d-104">_**Última modificación del tema:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="8b13d-104">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="8b13d-105">La aplicación estacionamiento de llamadas permite al usuario poner una llamada en espera y, a continuación, recuperar esa llamada desde un teléfono diferente.</span><span class="sxs-lookup"><span data-stu-id="8b13d-105">Call Park application allows a user to place a call on hold, then retrieve that call from a different phone.</span></span> <span data-ttu-id="8b13d-106">Use estos cmdlets para establecer la configuración de las órbitas de estacionamiento de llamadas y la aplicación estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8b13d-106">Use these cmdlets to configure settings for call park orbits and the Call Park application.</span></span>

<div>

## <a name="call-park-application-cmdlets"></a><span data-ttu-id="8b13d-107">Cmdlets de la aplicación Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="8b13d-107">Call Park Application Cmdlets</span></span>

<span data-ttu-id="8b13d-108">Los cmdlets siguientes pueden usarse para administrar la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8b13d-108">The following cmdlets can be used to manage Call Park application.</span></span>

<span data-ttu-id="8b13d-109">**Aplicación Estacionamiento de llamadas**</span><span class="sxs-lookup"><span data-stu-id="8b13d-109">**Call Park Application**</span></span>

  - <span></span>  
    <span data-ttu-id="8b13d-110">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8b13d-110">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8b13d-111">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8b13d-111">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8b13d-112">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8b13d-112">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8b13d-113">[Set-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8b13d-113">[Set-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8b13d-114">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8b13d-114">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8b13d-115">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8b13d-115">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8b13d-116">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8b13d-116">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8b13d-117">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8b13d-117">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8b13d-118">[Set-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8b13d-118">[Set-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b13d-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b13d-119">See Also</span></span>


[<span data-ttu-id="8b13d-120">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b13d-120">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

