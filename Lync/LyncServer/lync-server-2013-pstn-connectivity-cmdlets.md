---
title: 'Lync Server 2013: cmdlets de conectividad RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN connectivity cmdlets
ms:assetid: b19ba43c-3987-410d-a704-aba0a4fb0498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415670(v=OCS.15)
ms:contentKeyID: 48185142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7271622dbfefee9c0c96063b242015ab7f7225b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-cmdlets-in-lync-server-2013"></a>Cmdlets de conectividad RTC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Telefonía IP empresarial proporciona una configuración que permite realizar llamadas a la red de telefonía pública conmutada (RTC) y a la misma sin que se produzca ninguna disminución de calidad de servicio (QoS). Puede configurar estas opciones mediante cmdlets disponibles en el shell de administración de Lync Server.

<div>

## <a name="pstn-connectivity-cmdlets"></a>Cmdlets de conectividad RTC

Use los siguientes cmdlets para configurar diversos aspectos de la conectividad RTC.

**[Cmdlets de puertas de enlace RTC en Lync Server 2013](lync-server-2013-pstn-gateways-cmdlets.md)**

  - <span></span>  
    [Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Prueba-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Prueba-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))

**[Cmdlets de enrutamiento estático en Lync Server 2013](lync-server-2013-static-routing-cmdlets.md)**

  - <span></span>  
    [Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))

  - <span></span>  
    [New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))

  - <span></span>  
    [Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))

  - <span></span>  
    [Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))

  - <span></span>  
    [Nuevo: CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))

  - <span></span>  
    [Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))

  - <span></span>  
    [Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Nuevo: CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Nuevo: CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Nuevo: CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Nuevo: CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Nuevo: CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Nuevo: CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Nuevo: CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Nuevo: CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))

**[Cmdlets de configuración de Troncalización en Lync Server 2013](lync-server-2013-trunking-configuration-cmdlets.md)**

  - [Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))

<!-- end list -->

  - [Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))

  - [New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))

  - [Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))

  - [Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))

  - <span></span>  
    [Nuevo: CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))

  - <span></span>  
    [Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))

  - <span></span>  
    [Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))

<!-- end list -->

  - [Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))

  - <span></span>  
    [Nuevo: CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))

  - <span></span>  
    [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))

  - <span></span>  
    [Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))

  - <span></span>  
    [Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Nuevo: CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))

**[Cmdlets de enrutamiento de voz en Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**

  - <span></span>  
    [Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))

  - <span></span>  
    [Nuevo: CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))

  - <span></span>  
    [Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))

  - <span></span>  
    [Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))

  - <span></span>  
    [Nuevo: CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))

  - <span></span>  
    [Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))

  - <span></span>  
    [Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))

  - <span></span>  
    [Prueba-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))

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

