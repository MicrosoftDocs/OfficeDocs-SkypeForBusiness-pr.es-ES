---
title: Configuración de detección automática para movilidad con implementaciones híbridas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 027357579ff9ff90d82a78994696a5a2fb656188
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Configuración de la detección automática en Lync Server 2013 para movilidad con implementaciones híbridas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-18_

Las implementaciones híbridas son configuraciones que usan el servicio en la nube de Microsoft Lync Online y la implementación local. En este tipo de configuración, el servicio de detección automática puede determinar dónde está ubicado realmente el usuario. Es decir, detección automática ayuda a encontrar la cuenta de usuario y donde se encuentra el servidor que hospeda la cuenta del usuario, independientemente de si se encuentra en la implementación local o en la implementación de Lync Online.

Por ejemplo, si una cuenta de usuario está hospedada en un servidor de Lync Online, el intento de ubicar al usuario ocurrirá como sigue, en un proceso conocido como *detectabilidad*:

  - El usuario inicia un intento de conexión en la implementación local, **contoso.com**.

  - Se envía el intento a lyncdiscover.contoso.com, el nombre de DNS asociado al servicio de detección automática.

  - Detección automática hace referencia al grupo de registradores supuesto en la implementación local de contoso.com y recibe información sobre el servidor principal real del usuario hospedado en Lync Online. La detección automática envía al usuario una derivación al servicio de detección automática en línea de **lync.com**.

  - El usuario inicia un intento de conexión al servicio de detección automática en línea de lync.com y puede localizar la cuenta de usuario y el servidor principal del usuario.

Para que clientes móviles puedan descubrir la implementación en la que se encuentra el servidor principal del usuario, debe configurar el servicio de detección automática con un localizador de recursos uniforme (URL) nuevo. Para configurar el servicio de detección automática, haga lo siguiente:

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configuración de detección automática para implementaciones híbridas

1.  Use Get-CsHostingProvider para recuperar el valor del atributo ProxyFQDN.

2.  Desde el shell de administración de Lync Server, escriba
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Donde \[la\] identidad se reemplaza con el nombre de dominio del espacio de direcciones SIP compartido.

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

