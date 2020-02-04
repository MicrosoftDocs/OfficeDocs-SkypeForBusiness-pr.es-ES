---
title: 'Lync Server 2013: mensajería instantánea y cmdlets de presencia'
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
ms.openlocfilehash: 0d96b8971bb25898e9e8b02403b0f8cd5447681c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a>Cmdlets de presencia y mensajería instantánea en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-26_

Los cmdlets de presencia y mensajería instantánea le permiten administrar dichas características de cliente a través de Windows PowerShell. Puede establecer directivas de presencia que se apliquen a los usuarios en el ámbito global, de sitio o por usuario. También puede configurar diversas características de privacidad y mensajería instantánea.

<div>

## <a name="im-and-presence-cmdlets"></a>Cmdlets de presencia y mensajería instantánea

Para configurar la mensajería instantánea y la presencia, use los siguientes cmdlets:

  - <span></span>  
    [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))

  - <span></span>  
    [Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))

  - <span></span>  
    [New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))

  - <span></span>  
    [Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))

  - <span></span>  
    [Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))

<!-- end list -->

  - [Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))

  - [New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))

  - [Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))

  - [Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))

  - <span></span>  
    [Nuevo: CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))

  - <span></span>  
    [Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))

  - <span></span>  
    [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))

  - <span></span>  
    [Nuevo: CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))

  - <span></span>  
    [Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))

  - <span></span>  
    [Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))

  - <span></span>  
    [Nuevo: CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))

  - <span></span>  
    [Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))

  - <span></span>  
    [Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))

  - <span></span>  
    [Nuevo: CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))

  - <span></span>  
    [Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))

  - <span></span>  
    [Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Prueba-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Prueba-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Prueba-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Prueba-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Prueba-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Vea también


[Cmdlets de administración de clientes en Lync Server 2013](lync-server-2013-client-management-cmdlets.md)  


[Blog de Lync Server PowerShell](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

