---
title: 'Lync Server 2013: cmdlets de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing cmdlets
ms:assetid: 7ff94637-6319-4c45-9230-be34e8d81ede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398641(v=OCS.15)
ms:contentKeyID: 48184640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a95cf0c07726670b15891b2a067346e3452f333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-cmdlets-in-lync-server-2013"></a>Cmdlets de conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Microsoft Lync Server 2013 permite que los usuarios se unan a conferencias de dos maneras diferentes: mediante el uso de una aplicación de conferencias, como Lync 2013, o al marcar con un teléfono. Los usuarios de acceso telefónico no pueden realizar tareas como ver diapositivas o intercambiar mensajes instantáneos, pero pueden participar plenamente en la parte de audio de una conferencia.

<div>

## <a name="conferencing-cmdlets"></a>Cmdlets de conferencia

Los cmdlets de **CsDialInConferencing** se usan para configurar las propiedades de conferencia de acceso telefónico local, lo que incluye todo lo que le permite especificar los números de teléfono a los que los usuarios pueden llamar para unirse a una conferencia con los comandos del teclado disponibles después de unirse a una conferencia (por ejemplo, si pulsas 6 para desactivar o reactivar el audio de su teléfono). La mayoría de las demás características de una conferencia (por ejemplo, los usuarios pueden grabar la Conferencia, los usuarios pueden compartir aplicaciones durante la Conferencia, etc.) se administran mediante los cmdlets de **CsConferencingPolicy** .

**[Cmdlets de conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))

  - <span></span>  
    [Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))

  - <span></span>  
    [New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))

  - <span></span>  
    [Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))

**[Cmdlets de conferencias web en Lync Server 2013](lync-server-2013-web-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))

  - <span></span>  
    [Remove-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))

  - <span></span>  
    [Set-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))

  - <span></span>  
    [New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))

  - <span></span>  
    [Remove-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))

  - <span></span>  
    [Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))

  - <span></span>  
    [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))

  - <span></span>  
    [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))

  - <span></span>  
    [Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))

  - <span></span>  
    [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))

  - <span></span>  
    [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))

  - <span></span>  
    [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))

  - <span></span>  
    [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))

<!-- end list -->

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))

  - [Move-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))

  - <span></span>  
    [Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))

  - <span></span>  
    [Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))

  - <span></span>  
    [Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))

  - <span></span>  
    [Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))

  - <span></span>  
    [Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))

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

