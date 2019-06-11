---
title: 'Lync Server 2013: Control de admisión de llamadas y servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 787e312bcdee289050f2147912e87ef542433db4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Control de admisión de llamadas y servidor de mediación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Control de admisión de llamadas (CAC), introducido por primera vez en Lync Server 2010, administra el establecimiento de sesión en tiempo real, basado en el ancho de banda disponible, para evitar la mala calidad de la experiencia (QoE) para los usuarios de redes congestionadas. Para admitir esta capacidad, el servidor de mediación, que proporciona la señalización y la traducción de medios entre la infraestructura de telefonía IP empresarial y una puerta de enlace o proveedor de Troncalización SIP, es responsable de la administración del ancho de banda de sus dos interacciones en Lync. Servidor y en la puerta de enlace. En el servicio de control de admisión de llamadas, la entidad de terminación para una llamada gestiona la reserva del ancho de banda. Los pares de puertas de enlace (puerta de enlace PSTN, IP-PBX, SBC) con los que interactúa el servidor de mediación en el lado de la puerta de enlace no admiten Lync Server 2013 control de admisión de llamadas. Por lo tanto, el servidor de mediación tiene que controlar las interacciones de ancho de banda en nombre de su punto de conexión. Siempre que sea posible, el servidor de mediación reservará el ancho de banda por adelantado. Si no es posible (por ejemplo, si se desconoce la localidad del extremo multimedia definitivo de una llamada saliente a la puerta de enlace del mismo nivel, en el lado de la puerta de enlace), se reserva el ancho de banda cuando se establece la llamada. Este comportamiento puede provocar la saturación del ancho de banda, pero es la única forma de evitar las llamadas falsas.

La omisión de medios y la reserva del ancho de banda se excluyen mutuamente. Si se emplea una omisión de medios para una llamada, el control de admisión no se realiza para esa llamada. En este caso, se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda. Si se usa el control de admisión de llamadas para una llamada en particular que implica el servidor de mediación, esa llamada no puede emplear la omisión de medios.

Para obtener detalles acerca de la omisión de medios o el control de admisión de llamadas, consulte [planificación de la omisión de medios en Lync server 2013](lync-server-2013-planning-for-media-bypass.md) o [planificación de control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) en la documentación de planificación.

</div>

<span> </span>

</div>

</div>

</div>

