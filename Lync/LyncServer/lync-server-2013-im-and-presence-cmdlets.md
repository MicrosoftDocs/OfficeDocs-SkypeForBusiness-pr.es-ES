---
title: 'Lync Server 2013: cmdlets de mensajería instantánea y presencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1cdb8e7e9f0301219968a8eab35d23d550a8a17
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a>Cmdlets de presencia y mensajería instantánea en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-26_

Los cmdlets de mensajería instantánea (mi) y presencia permiten administrar las características de cliente a través de Windows PowerShell. Puede establecer directivas de presencia que se aplican a los usuarios en el ámbito global, de sitio o por usuario. También puede configurar varias características de privacidad y mensajería instantánea.

<div>

## <a name="im-and-presence-cmdlets"></a>Cmdlets de mensajería instantánea y presencia

Para configurar la mensajería instantánea y la presencia, use los siguientes cmdlets:

  - <span></span>  
    [Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - <span></span>  
    [Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - <span></span>  
    [New-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - <span></span>  
    [Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - <span></span>  
    [Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

<!-- end list -->

  - [Get-CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [New-CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [Remove-CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [Set-CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - <span></span>  
    [New-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - <span></span>  
    [Remove-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - <span></span>  
    [Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - <span></span>  
    [New-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - <span></span>  
    [Remove-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - <span></span>  
    [Set-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - <span></span>  
    [New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - <span></span>  
    [Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - <span></span>  
    [Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - <span></span>  
    [New-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - <span></span>  
    [Remove-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - <span></span>  
    [Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Vea también


[Cmdlets de administración de clientes en Lync Server 2013](lync-server-2013-client-management-cmdlets.md)  


[Blog de Lync Server PowerShell](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

