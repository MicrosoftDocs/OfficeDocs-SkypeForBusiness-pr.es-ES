---
title: 'Lync Server 2013: cmdlets de certificados y autenticación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate and authentication cmdlets
ms:assetid: ebb51778-3558-49d2-8343-d83e7a731559
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415680(v=OCS.15)
ms:contentKeyID: 48185711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 873ab07ecb532851e42116dd6691c8c5ad723d7c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-and-authentication-cmdlets-in-lync-server-2013"></a>Cmdlets de certificados y autenticación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Los cmdlets de certificado y autenticación abarcan una amplia gama de tareas, por ejemplo la administración de certificados de cliente y servidor, la administración de PIN de usuario, así como la administración de los dominios SIP y cuentas Kerberos que se usan con Internet Information Services.

<div>

## <a name="certificate-and-authentication-cmdlets"></a>Cmdlets de certificados y autenticación

A continuación se presenta una lista de cmdlets directamente relacionados con la administración de certificados y de autenticación:

**Certificados y autenticación**

  - <span></span>  
    [Get-CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - <span></span>  
    [Import-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - <span></span>  
    [Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - <span></span>  
    [Solicitud-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - <span></span>  
    [Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - <span></span>  
    [REVOKE-CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Lock-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - <span></span>  
    [Set-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - <span></span>  
    [Unlock-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - <span></span>  
    [New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - <span></span>  
    [Grant-CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - <span></span>  
    [New-CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - <span></span>  
    [Remove-CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - <span></span>  
    [Set-CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - <span></span>  
    [New-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - <span></span>  
    [Remove-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - <span></span>  
    [Set-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - <span></span>  
    [New-CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - <span></span>  
    [Remove-CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - <span></span>  
    [Set-CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

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

