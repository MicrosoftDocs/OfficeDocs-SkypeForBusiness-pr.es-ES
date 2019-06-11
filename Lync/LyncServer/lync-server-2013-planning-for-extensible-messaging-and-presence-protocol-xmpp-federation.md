---
title: Planear la Federación de protocolo de presencia y mensajería extensible (XMPP)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4e1d8f9b7f164dd9e83f556dcc57809619278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Planeamiento de la Federación de protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP) que se podría implementar como una función de servidor independiente para permitir la Federación con implementaciones de XMPP. En Microsoft Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica. La funcionalidad XMPP se instala en dos partes: un proxy XMPP que se ejecuta en el servidor perimetral y la puerta de enlace XMPP que se ejecuta en los servidores front-end.

La implementación y configuración de XMPP se trata en [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) se planea la compatibilidad de XMPP en la organización mediante la definición de reglas de puerto y protocolo en el firewall, la configuración de certificados y la adición de DNS PTR. En los temas siguientes de esta sección se resume la información necesaria para planear correctamente la Federación XMPP para su implementación.

<div>


> [!IMPORTANT]
> La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen de certificados: Federación de protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Resumen de puertos: Federación protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Resumen de DNS: Federación protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar la federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))  
[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))  
[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

