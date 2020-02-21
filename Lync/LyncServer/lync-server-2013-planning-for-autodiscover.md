---
title: 'Lync Server 2013: Planeación de la detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 990e58dc01171001e896b03e5a32fc8175c93b2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Planeación de la detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-16_

La detección automática se introdujo para Lync Server en la actualización acumulativa de Lync Server 2010: noviembre de 2011. El objetivo principal de esta implementación inicial de la detección automática era proporcionar un medio para que Lync Mobile encuentre el servicio de movilidad (MCX). El servicio Detección automática de Lync Server 2013 ahora es un servicio que usan todos los clientes para localizar servicios de servidor y de usuario. El servicio Detección automática de Microsoft Lync Server 2013 se ejecuta en los directores y servidores front-end.

<div>


> [!TIP]  
> Para obtener información más técnica sobre la detección automática y lo que se comunica a los clientes, consulte <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.<BR>La movilidad sigue siendo un escenario distinto y los servicios de movilidad aún requieren una planificación especial. Para obtener más información, consulte <A href="lync-server-2013-planning-for-mobility.md">Planning for Mobility in Lync Server 2013</A>.



</div>

Cuando se introdujo la detección automática en Lync Server 2010, había comprometerse con la necesidad de implementar un servicio que requiriera cambios potenciales en los certificados en las implementaciones de servidor existentes. La detección automática podría usarse a través del puerto TCP 443 para HTTPS o a través del puerto TCP 80 para HTTP. Si se decidió usar HTTPS, es necesario volver a emitir certificados en servidores proxy inversos, directores y servidores front-end para poder dar cabida a los registros `lyncdiscover.<domain>` DNS `lyncdiscoverinternal.<domain>` y necesarios. Si la decisión fue usar HTTP, la reemisión de certificados podría evitarse mediante el uso de registros CNAME (o alias) de DNS para usar los nombres existentes en los certificados. El uso de HTTP significa que las comunicaciones iniciales no están cifradas.

Como Lync Server 2013 usa detección automática para todos los clientes, el escenario principal es usar HTTPS de manera exclusiva y crear certificados con lyncdiscover. \<dominio\> como parte de la configuración de los servidores proxy inversos, los directores y los servidores front-end. Si va a implementar la detección automática en una implementación actualizada desde Lync Server 2010, es posible que desee usar HTTP para evitar volver a emitir certificados. En las secciones siguientes se proporciona una guía para ambos escenarios.

<div>


> [!IMPORTANT]  
> La lista de nombres alternativos de sujeto en los certificados usados por la regla de publicación de servicios web externos debe contener un <EM>lyncdiscover.&lt; entrada&gt; sipdomain</EM> para cada dominio SIP dentro de la organización. Para obtener información detallada sobre las entradas de nombre alternativo de sujeto que son necesarias para los directores, los servidores front-end y los proxies inversos, consulte <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate Summary-Autodiscover in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen de certificado-detección automática en Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Resumen de Puerto-detección automática en Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Resumen de DNS-detección automática en Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Híbrido y dividido-dominio-detección automática en Lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

