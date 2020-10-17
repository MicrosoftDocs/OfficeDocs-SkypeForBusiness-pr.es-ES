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
# <a name="phones-and-devices-cmdlets-in-lync-server-2013"></a>Cmdlets de teléfonos y dispositivos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-28_

Microsoft Lync Server 2013 proporciona una serie de cmdlets que permiten administrar teléfonos y otros dispositivos de hardware. Esto incluye cosas como teléfonos de voz sobre IP (VoIP); teléfonos de área común (por ejemplo, un teléfono en un vestíbulo de edificio, cafetería u otra ubicación pública); e incluso teléfonos analógicos, teléfonos que no pueden ejecutar Lync Phone Edition.

<div>

## <a name="phones-and-devices-cmdlets"></a>Cmdlets de teléfonos y dispositivos

Los cmdlets **CsDeviceUpdate** se usan para administrar el servicio Web de actualización de dispositivos, un componente de Lync Server que permite a los administradores distribuir actualizaciones de firmware a teléfonos y otros dispositivos que ejecutan Lync Phone Edition.

  - <span></span>  
    [Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))

  - <span></span>  
    [Move-CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - <span></span>  
    [New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))

  - <span></span>  
    [Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - <span></span>  
    [Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))

  - <span></span>  
    [Move-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - <span></span>  
    [New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))

  - <span></span>  
    [Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - <span></span>  
    [Set-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))

  - <span></span>  
    [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))

  - <span></span>  
    [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))

  - <span></span>  
    [Set-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))

  - <span></span>  
    [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))

  - <span></span>  
    [Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))

  - <span></span>  
    [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))

  - <span></span>  
    [Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [APPROVE-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))

  - <span></span>  
    [Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))

  - <span></span>  
    [Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))

  - <span></span>  
    [RESET-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))

  - <span></span>  
    [Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))

  - <span></span>  
    [New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))

  - <span></span>  
    [Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))

  - <span></span>  
    [Set-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Consulte también


[Blog de Lync Server PowerShell](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

