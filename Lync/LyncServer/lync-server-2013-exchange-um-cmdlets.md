---
title: 'Lync Server 2013: cmdlets de mensajería unificada de Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange UM cmdlets
ms:assetid: 32922b9f-590d-41cc-ba57-9ed5f1caa814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415642(v=OCS.15)
ms:contentKeyID: 48183786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e4c530095b69e8aadd07ad37e3fbe4a46b361a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-um-cmdlets-in-lync-server-2013"></a><span data-ttu-id="68676-102">Cmdlets de mensajería unificada de Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68676-102">Exchange UM cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68676-103">_**Última modificación del tema:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="68676-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="68676-104">Microsoft Lync Server 2013 funciona junto con la mensajería unificada de Exchange (UM) para implementar el acceso de operador automático y suscriptor para el correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="68676-104">Microsoft Lync Server 2013 works together with Exchange Unified Messaging (UM) to implement Auto Attendant and Subscriber Access for hosted voice mail.</span></span> <span data-ttu-id="68676-105">Estas características se pueden administrar mediante cmdlets en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68676-105">These features can be managed through cmdlets in the Lync Server Management Shell.</span></span>

<div>

## <a name="exchange-um-cmdlets"></a><span data-ttu-id="68676-106">Cmdlets de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="68676-106">Exchange UM Cmdlets</span></span>

<span data-ttu-id="68676-107">Los siguientes cmdlets se pueden usar para administrar la mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="68676-107">The following cmdlets can be used to manage Exchange UM</span></span>

<span data-ttu-id="68676-108">**Mensajería unificada de Exchange**</span><span class="sxs-lookup"><span data-stu-id="68676-108">**Exchange UM**</span></span>

  - <span></span>  
    <span data-ttu-id="68676-109">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-109">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-110">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-110">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-111">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-111">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-112">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-112">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-113">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-113">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="68676-114">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-114">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="68676-115">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-115">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="68676-116">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-116">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="68676-117">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-117">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="68676-118">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-118">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-119">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-119">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-120">[Nuevo: CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-120">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-121">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-121">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-122">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-122">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="68676-123">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-123">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-124">[Nuevo: CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-124">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-125">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-125">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="68676-126">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="68676-126">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68676-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="68676-127">See Also</span></span>


[<span data-ttu-id="68676-128">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="68676-128">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

