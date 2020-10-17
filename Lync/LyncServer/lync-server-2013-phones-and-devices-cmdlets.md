---
title: 'Lync Server 2013: cmdlets de teléfonos y dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones and devices cmdlets
ms:assetid: 6ebeba4b-43ce-4a31-9060-50d249b7564c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415657(v=OCS.15)
ms:contentKeyID: 48184467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d997b8a6c6dfc82943134d797ab2d98eb93d888
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524207"
---
# <a name="phones-and-devices-cmdlets-in-lync-server-2013"></a><span data-ttu-id="1e40b-102">Cmdlets de teléfonos y dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e40b-102">Phones and devices cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e40b-103">_**Última modificación del tema:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="1e40b-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="1e40b-104">Microsoft Lync Server 2013 proporciona una serie de cmdlets que permiten administrar teléfonos y otros dispositivos de hardware.</span><span class="sxs-lookup"><span data-stu-id="1e40b-104">Microsoft Lync Server 2013 provides a number of cmdlets that enable you to manage telephones and other hardware devices.</span></span> <span data-ttu-id="1e40b-105">Esto incluye cosas como teléfonos de voz sobre IP (VoIP); teléfonos de área común (por ejemplo, un teléfono en un vestíbulo de edificio, cafetería u otra ubicación pública); e incluso teléfonos analógicos, teléfonos que no pueden ejecutar Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1e40b-105">This includes such things as Voice over IP (VoIP) phones; common area phones (for example, a phone in a building lobby, cafeteria, or other public location); and even analog phones, phones that are not capable of running Lync Phone Edition.</span></span>

<div>

## <a name="phones-and-devices-cmdlets"></a><span data-ttu-id="1e40b-106">Cmdlets de teléfonos y dispositivos</span><span class="sxs-lookup"><span data-stu-id="1e40b-106">Phones and Devices Cmdlets</span></span>

<span data-ttu-id="1e40b-107">Los cmdlets **CsDeviceUpdate** se usan para administrar el servicio Web de actualización de dispositivos, un componente de Lync Server que permite a los administradores distribuir actualizaciones de firmware a teléfonos y otros dispositivos que ejecutan Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1e40b-107">The **CsDeviceUpdate** cmdlets are used to manage the Device Update Web service, a Lync Server component that enables administrators to distribute firmware updates to telephones and other devices running Lync Phone Edition.</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-108">[Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-108">[Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-109">[Move-CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-109">[Move-CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-110">[New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-110">[New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-111">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-111">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-112">[Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-112">[Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1e40b-113">[Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-113">[Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-114">[Move-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-114">[Move-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-115">[New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-115">[New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-116">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-116">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-117">[Set-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-117">[Set-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1e40b-118">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-118">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-119">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-119">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-120">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-120">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-121">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-121">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1e40b-122">[Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-122">[Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1e40b-123">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-123">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-124">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-124">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-125">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-125">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-126">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-126">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1e40b-127">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-127">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-128">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-128">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1e40b-129">[APPROVE-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-129">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-130">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-130">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-131">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-131">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-132">[RESET-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-132">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-133">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-133">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1e40b-134">[Test-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-134">[Test-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1e40b-135">[Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-135">[Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-136">[New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-136">[New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-137">[Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-137">[Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1e40b-138">[Set-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1e40b-138">[Set-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e40b-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e40b-139">See Also</span></span>


[<span data-ttu-id="1e40b-140">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e40b-140">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

