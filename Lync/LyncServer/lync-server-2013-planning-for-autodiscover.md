---
title: 'Lync Server 2013: planeamiento de la detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1d0ce7a775bc73c5f3afa10d1f9c148395b0eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Planificación de la detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-16_

La detección automática se presentó en Lync Server en la actualización acumulativa para Lync Server 2010: noviembre de 2011. El principal objetivo de esta implementación inicial de la detección automática es proporcionar un medio para que Lync Mobile encuentre el servicio de movilidad (MCX). El servicio de detección automática de Lync Server 2013 es un servicio usado por todos los clientes para ubicar servicios de servidor y de usuario. El servicio de detección automática de Microsoft Lync Server 2013 se ejecuta en directores y servidores front-end.

<div>


> [!TIP]  
> Para obtener más información técnica sobre la detección automática y sobre lo que se comunica a los clientes, consulte Descripción de la <A href="lync-server-2013-understanding-autodiscover.md">detección automática en Lync Server 2013</A>.<BR>La movilidad sigue siendo un escenario diferenciado y los servicios de movilidad aún requieren una planificación especial. Para obtener más información, consulte <A href="lync-server-2013-planning-for-mobility.md">planificación de movilidad en Lync Server 2013</A>.



</div>

Cuando se introdujo la detección automática en Lync Server 2010, había comprometeciones que era necesario realizar para implementar un servicio que requiriera posibles cambios de certificados en las implementaciones existentes de servidor. La detección automática podría usarse en el puerto TCP 443 para HTTPS o en el puerto TCP 80 para HTTP. Si se tomó la decisión de usar HTTPS, es necesario volver a emitir certificados en los servidores proxy inversos, directores y servidores de aplicaciones para el usuario para poder `lyncdiscover.<domain>` dar `lyncdiscoverinternal.<domain>` cabida a los registros necesarios y DNS. Si la decisión fue utilizar HTTP, la reemisión de certificados podría evitarse mediante el uso de registros CNAME (o alias) DNS para usar los nombres existentes en los certificados. El uso de HTTP significa que las comunicaciones iniciales no estaban cifradas.

Puesto que Lync Server 2013 usa la detección automática para todos los clientes, el escenario principal es usar HTTPS de forma exclusiva y para crear certificados con lyncdiscover. \<dominio\> como parte de la configuración de servidores proxy inversos, directores y servidores de aplicaciones para el usuario. Si implementa la detección automática en una implementación actualizada de Lync Server 2010, es posible que desee usar HTTP para evitar la emisión de certificados. En las siguientes secciones se proporciona una guía para ambos escenarios.

<div>


> [!IMPORTANT]  
> La lista de nombres alternativos de asunto en certificados usados por la regla de publicación de servicios web externos debe contener un <EM>lyncdiscover.&lt; sipdomain&gt; </EM> entrada para cada dominio SIP de su organización. Para obtener información sobre las entradas de nombre alternativo de asunto necesarias para los directores, servidores de aplicaciones para el usuario y proxy inversos, consulte <A href="lync-server-2013-certificate-summary-autodiscover.md">Resumen del certificado: detección automática en Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen del certificado: detección automática en Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Resumen de puertos-detección automática en Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Resumen de DNS-detección automática en Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Híbrida y dividida en dominios: detección automática en Lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

