---
title: 'Lync Server 2013: cmdlets de Federación y de acceso externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b206d8de27f2cdeebab5db0c125012c2a29c65b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>Cmdlets de Federación y de acceso externo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-26_

La Federación y el acceso externo ofrecen dos capacidades importantes: la Federación permite que los usuarios se comuniquen con personas de fuera de la organización, mientras que el acceso externo permite a los usuarios conectarse a Microsoft Lync Server 2013 desde fuera de la red interna. Los cmdlets disponibles para administrar la Federación y el acceso externo en Lync Server 2013 le permiten determinar quién puede comunicarse con sus usuarios (y cuáles no) y determinar si esos usuarios se pueden conectar a Lync Server sin tener que iniciar sesión en el red.

<div>

## <a name="federation-and-external-access-cmdlets"></a>Cmdlets de Federación y de acceso externo

La mayoría de las tareas de administración que se aplican a la Federación y el acceso externo se pueden realizar desde el panel de control de Lync Server. Estas mismas tareas se pueden realizar con cmdlets desde el shell de administración de Lync Server o desde una secuencia de comandos; el uso de una secuencia de comandos le permite automatizar determinadas tareas. A continuación se muestra una lista de cmdlets que se relacionan directamente con la administración de la Federación y el acceso externo:

  - <span></span>  
    [Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))

  - <span></span>  
    [Nuevo: CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))

  - <span></span>  
    [Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))

  - <span></span>  
    [Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))

  - <span></span>  
    [Nuevo: CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))

  - <span></span>  
    [Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))

  - <span></span>  
    [Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))

  - <span></span>  
    [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))

  - <span></span>  
    [Nuevo: CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))

  - <span></span>  
    [Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))

  - [New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))

  - [Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))

  - [Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))

  - <span></span>  
    [Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))

  - <span></span>  
    [Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))

  - <span></span>  
    [Nuevo: CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))

  - <span></span>  
    [Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))

  - <span></span>  
    [Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))

  - <span></span>  
    [Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))

  - <span></span>  
    [Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))

  - <span></span>  
    [Nuevo: CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))

  - <span></span>  
    [Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))

  - <span></span>  
    [Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Prueba-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))

  - [New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))

  - [Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))

  - [Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Vea también


[Blog de Lync Server PowerShell](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

