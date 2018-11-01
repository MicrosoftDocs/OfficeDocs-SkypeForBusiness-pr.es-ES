---
title: 'Lync Server 2013: Control de admisión de llamadas y servidor de mediación'
TOCTitle: Control de admisión de llamadas y servidor de mediación
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48275711
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Control de admisión de llamadas y servidor de mediación en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

El servicio de control de admisión de llamadas (CAC), introducido por primera vez en Lync Server 2010, administra el establecimiento de sesiones en tiempo real según el ancho de banda disponible para evitar que la calidad de la experiencia (QoE) de los usuarios sea deficiente en las redes congestionadas. Para permitir esta funcionalidad, el servidor de mediación, que proporciona la señalización y la conversión multimedia entre la infraestructura de Telefonía IP empresarial y un proveedor de troncos SIP o puerta de enlace, se encarga de administrar el ancho de banda para sus dos interacciones, en el lado de Lync Server y en el de la puerta de enlace. En el servicio de control de admisión de llamadas, la entidad que finaliza una llamada controla la reserva del ancho de banda. Las puertas de enlace del mismo nivel (la puerta de enlace RTC, IP-PBX y SBC) con las que interactúa el Servidor de mediación en el lado de la puerta de enlace no son compatibles con el servicio de control de admisión de llamadas de Lync Server 2013. Por ello, el Servidor de mediación se debe encargar de las interacciones del ancho de banda en lugar de la puerta de enlace del mismo nivel. Siempre que sea posible, el Servidor de mediación reservará por adelantado el ancho de banda. Si no es posible (por ejemplo, si se desconoce la localidad del extremo multimedia definitivo de una llamada realizada a la puerta de enlace del mismo nivel, en el lado de la puerta de enlace), se reserva el ancho de banda cuando se establece la llamada. Este funcionamiento puede provocar la sobresuscripción del ancho de banda, pero es la única forma de evitar las llamadas falsas.

El desvío de medios y la reserva del ancho de banda se excluyen mutuamente. Si se usa desvío de medios en una llamada, no se aplicará el control de admisión de llamadas en esa llamada. En este caso, se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda. Si se usa el control de admisión de llamadas para una determinada llamada que emplee el Servidor de mediación, esa llamada no podrá usar el desvío de medios.

Para ver más detalles acerca del desvío de medios o el control de admisión de llamadas, consulte [Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) o [Planear el control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) en la documentación sobre planeación.

