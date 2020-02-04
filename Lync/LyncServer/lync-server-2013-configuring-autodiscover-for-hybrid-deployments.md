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
ms.openlocfilehash: 8924194d89eafb75c06ff78ed3b765699e36b196
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Configuración de la detección automática en Lync Server 2013 para implementaciones híbridas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-12_

Las implementaciones híbridas son configuraciones que usan el servicio en la nube de Microsoft Lync Online y la implementación local. En este tipo de configuración, el servicio Detección automática debe poder ubicar dónde se encuentra realmente el usuario. Es decir, la detección automática ayuda a buscar la cuenta de usuario y dónde se encuentra el servidor que hospeda la cuenta del usuario, independientemente de si se encuentra en la implementación local o en la implementación de Lync Online.

Por ejemplo, si la cuenta de un usuario se hospeda en un servidor de Lync Online, el intento de ubicar al usuario tendrá el siguiente aspecto, en un proceso conocido como *descubrimiento*:

  - El usuario inicia un intento de conexión a la implementación local, **contoso.com**.

  - El intento se envía a lyncdiscover.contoso.com, el nombre DNS asociado al servicio Detección automática.

  - Detección automática hace referencia al grupo de registradores supuesto en la implementación local de contoso.com y se le proporciona información sobre el servidor principal real del usuario hospedado en Lync Online. La detección automática después envía al usuario una referencia al servicio de detección automática de **Lync.com** online.

  - El usuario inicia un intento de conexión al servicio de detección automática de lync.com online y puede ubicar la cuenta del usuario y el servidor principal del usuario.

Para permitir que los clientes descubran la implementación en la que se encuentra el servidor principal del usuario, debe configurar el servicio Detección automática con un localizador de recursos uniforme (URL) nuevo. Siga este procedimiento para configurar el servicio Detección automática.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configuración de detección automática para implementaciones híbridas

1.  En el tema [requisitos del servicio Autodiscover para Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), use Get-CsHostingProvider para recuperar el valor del atributo ProxyFQDN.

2.  Desde el shell de administración de Lync Server, escriba
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Donde \[identidad\] se reemplaza con el nombre de dominio del espacio de direcciones SIP compartido.

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

