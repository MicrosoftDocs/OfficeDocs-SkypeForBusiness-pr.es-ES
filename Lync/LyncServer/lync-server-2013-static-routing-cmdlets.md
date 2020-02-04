---
title: 'Lync Server 2013: cmdlets de enrutamiento estáticos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a5c5dcefa5c4650c6bbfabf940840f22fc5df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="static-routing-cmdlets-in-lync-server-2013"></a>Cmdlets de enrutamiento estático en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-20_

Con las rutas estáticas, los administradores pueden predeterminar las rutas de red tomadas por los mensajes SIP. Cuando un servidor recibe un mensaje, el servidor comprueba la dirección del mensaje y, a continuación, reenvía el mensaje al servidor del próximo salto preconfigurado por un administrador. Si se configuran correctamente, las rutas estáticas ayudan a asegurar la entrega precisa y puntual de los mensajes sin apenas sobrecargar los servidores.

<div>

## <a name="static-routing-cmdlets"></a>Cmdlets de enrutamiento estático

A menos que el personal de soporte técnico de Microsoft lo indique de otra manera, las rutas estáticas configuradas para Microsoft Lync Server 2013 deberían crearse con el cmdlet [New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15)) . Después de crear una ruta, puede usar los cmdlets de CsStaticRoutingConfiguration para agregar esa ruta a una colección de enrutamiento estático.

**Enrutamiento estático**

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

