---
title: 'Lync Server 2013: control de admisión de llamadas y servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16158c8920279d95cfe3deed37f789eaedccc8b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Control de admisión de llamadas y servidor de mediación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

El servicio de control de admisión de llamadas (CAC), que apareció por primera vez en Lync Server 2010, administra el establecimiento de sesiones en tiempo real, en función del ancho de banda disponible, para evitar la mala calidad de la experiencia (QoE) para los usuarios de redes congestionadas. Para admitir esta capacidad, el servidor de mediación, que proporciona la señalización y la conversión de medios entre la infraestructura de telefonía IP empresarial y una puerta de enlace o un proveedor de enlace troncal SIP, es responsable de la administración de ancho de banda para sus dos interacciones en el Lync. Lado del servidor y en el lado del puerta de enlace. En el servicio de control de admisión de llamadas, la entidad que finaliza una llamada controla la reserva del ancho de banda. Los pares de puertas de enlace (puerta de enlace RTC, IP-PBX, SBC) con los que interactúa el servidor de mediación en el lado de la puerta de enlace no admiten Lync Server 2013 Call Admission Control. Por lo tanto, el servidor de mediación debe controlar las interacciones de ancho de banda en nombre de su puerta de enlace del mismo nivel. Siempre que sea posible, el servidor de mediación reservará el ancho de banda por adelantado. Si no es posible (por ejemplo, si se desconoce la localidad del extremo multimedia definitivo de una llamada realizada a la puerta de enlace del mismo nivel, en el lado de la puerta de enlace), se reserva el ancho de banda cuando se establece la llamada. Este funcionamiento puede provocar la sobresuscripción del ancho de banda, pero es la única forma de evitar las llamadas falsas.

El desvío de medios y la reserva del ancho de banda se excluyen mutuamente. Si se usa desvío de medios en una llamada, no se aplicará el control de admisión de llamadas en esa llamada. En este caso, se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda. Si se usa el control de admisión de llamadas para una llamada concreta que implica el servidor de mediación, esa llamada no puede emplear la omisión de medios.

Para obtener más información sobre la omisión de medios o el control de admisión de llamadas, consulte [Planning for Media bypass in Lync server 2013](lync-server-2013-planning-for-media-bypass.md) o [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) en la documentación referente a la planeación.

</div>

<span> </span>

</div>

</div>

</div>

