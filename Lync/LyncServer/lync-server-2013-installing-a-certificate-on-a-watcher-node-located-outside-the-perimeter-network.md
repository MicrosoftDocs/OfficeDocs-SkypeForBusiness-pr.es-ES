---
title: 'Lync Server 2013: instalar un certificado en un nodo de monitor ubicado fuera de la red perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bf4519995abf75db7807f8cd80f07ea477c8d4b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498557"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Instalar un certificado en un nodo de monitor ubicado fuera de la red perimetral de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Los agentes de System Center Operations Manager que se ejecutan en una red perimetral (como un servidor perimetral de Lync Server), fuera de la empresa (como un nodo de monitor de transacciones sintéticas externo) o a través de un límite de confianza de los servicios de dominio de Active Directory, podrían requerir la configuración de un servidor de puerta de enlace de System Center Operations Manager. Este rol de servidor permite que los agentes que no tienen una relación de confianza con el servidor de administración raíz inicien alertas. Para obtener más información, vea "administrar servidores de puerta de enlace en Operations Manager 2007" en la biblioteca de TechNet de System Center Operations Manager en [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) .

Si implementa un agente en una de estas ubicaciones, también tendrá que solicitar y configurar un certificado que permita al nodo de monitor enviar alertas a System Center Operations Manager. Para simplificar este proceso, el equipo de Operations Manager creó una serie de utilidades para que pueda solicitar e instalar el tipo correcto de certificado en la PC nodo de supervisión. Para obtener más información y para descargar estas utilidades, consulte el artículo del blog "obtención de certificados para agentes no Unidos a un dominio fácilmente con el Asistente para generación de certificados" en [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) .

</div>

<span> </span>

</div>

</div>

</div>

