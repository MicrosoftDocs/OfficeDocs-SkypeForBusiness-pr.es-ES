---
title: Configurar la detección automática para movilidad con implementaciones híbridas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1865cab188bace472996db6207de62ce8498976
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Configurar la detección automática para movilidad con implementaciones híbridas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-18_

Las implementaciones híbridas son configuraciones que usan el servicio en la nube de Microsoft Lync Online y la implementación local. En este tipo de configuración, el servicio Detección automática debe poder ubicar dónde se encuentra realmente el usuario. Es decir, la detección automática ayuda a buscar la cuenta de usuario y dónde se encuentra el servidor que hospeda la cuenta del usuario, independientemente de si se encuentra en la implementación local o en la implementación de Lync Online.

Por ejemplo, si la cuenta de un usuario se hospeda en un servidor de Lync Online, el intento de ubicar al usuario tendrá el siguiente aspecto, en un proceso conocido como *descubrimiento*:

  - El usuario inicia un intento de conexión a la implementación local, **contoso.com**.

  - El intento se envía a lyncdiscover.contoso.com, el nombre DNS asociado al servicio Detección automática.

  - Detección automática hace referencia al grupo de registradores supuesto en la implementación local de contoso.com y se le proporciona información sobre el servidor principal real del usuario hospedado en Lync Online. La detección automática después envía al usuario una referencia al servicio de detección automática de **Lync.com** online.

  - El usuario inicia un intento de conexión al servicio de detección automática de lync.com online y puede ubicar la cuenta del usuario y el servidor principal del usuario.

Para que los clientes móviles puedan descubrir la implementación donde se encuentra el servidor principal del usuario, debe configurar el servicio Detección automática con un nuevo localizador de recursos uniforme (URL). Siga este procedimiento para configurar el servicio Detección automática.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configuración de detección automática para implementaciones híbridas

1.  Use Get-CsHostingProvider para recuperar el valor del atributo ProxyFQDN.

2.  Desde el shell de administración de Lync Server, escriba
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Donde \[identidad\] se reemplaza con el nombre de dominio del espacio de direcciones SIP compartido.

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

