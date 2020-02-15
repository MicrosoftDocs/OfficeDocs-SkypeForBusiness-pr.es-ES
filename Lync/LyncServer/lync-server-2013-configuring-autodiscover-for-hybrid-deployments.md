---
title: 'Lync Server 2013: configuración de detección automática para implementaciones híbridas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f97ed9c5346252782b8105bf1de9f76bf3522155
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Configuración de detección automática en Lync Server 2013 para implementaciones híbridas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-12_

Las implementaciones híbridas son configuraciones que usan el servicio en la nube de Microsoft Lync Online y la implementación local. En este tipo de configuración, el servicio de detección automática puede determinar dónde está ubicado realmente el usuario. Es decir, detección automática ayuda a encontrar la cuenta de usuario y donde se encuentra el servidor que hospeda la cuenta del usuario, independientemente de si se encuentra en la implementación local o en la implementación de Lync Online.

Por ejemplo, si una cuenta de usuario está hospedada en un servidor de Lync Online, el intento de ubicar al usuario ocurrirá como sigue, en un proceso conocido como *detectabilidad*:

  - El usuario inicia un intento de conexión en la implementación local, **contoso.com**.

  - Se envía el intento a lyncdiscover.contoso.com, el nombre de DNS asociado al servicio de detección automática.

  - Detección automática hace referencia al grupo de registradores supuesto en la implementación local de contoso.com y recibe información sobre el servidor principal real del usuario hospedado en Lync Online. La detección automática envía al usuario una derivación al servicio de detección automática en línea de **lync.com**.

  - El usuario inicia un intento de conexión al servicio de detección automática en línea de lync.com y puede localizar la cuenta de usuario y el servidor principal del usuario.

Para permitir que los clientes detecten la implementación en la que se encuentra el servidor principal del usuario, debe configurar el servicio de detección automática con un nuevo localizador de recursos uniforme (URL). Para configurar el servicio de detección automática, haga lo siguiente:

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configuración de detección automática para implementaciones híbridas

1.  En el tema, [requisitos del servicio Detección automática para Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), use Get-CsHostingProvider para recuperar el valor del atributo ProxyFQDN.

2.  Desde el shell de administración de Lync Server, escriba
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Donde \[la\] identidad se reemplaza con el nombre de dominio del espacio de direcciones SIP compartido.

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

