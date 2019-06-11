---
title: Requisitos de equilibrio de carga de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4848c78c755b95a15c28ab1f8e2555a180e22bfa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Requisitos de equilibrio de carga para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Si tiene grupos de servidores front-end, grupos de directores o grupos de servidores perimetrales, necesita implementar el equilibrio de carga para estos grupos. El equilibrio de carga distribuye el tráfico entre los servidores de los grupos.

Lync Server 2013 admite dos tipos de soluciones de equilibrio de carga para el tráfico de cliente a servidor: equilibrio de carga del sistema de nombres de dominio (DNS) y equilibrio de carga de hardware. El equilibrio de carga de DNS ofrece varias ventajas, como la administración más sencilla, la solución de problemas más eficaz y la capacidad de aislar gran parte del tráfico de Lync Server de cualquier problema potencial de equilibrado de carga de hardware.

Decida qué solución de equilibrio de carga es adecuada para cada grupo de su implementación, teniendo en cuenta las restricciones siguientes:

  - La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar el equilibrio de carga de DNS en una interfaz y el equilibrio de carga de hardware en la otra.

  - Algunos tipos de tráfico requieren un equilibrador de carga de hardware. Por ejemplo, el tráfico HTTP requiere un equilibrador de carga de hardware en lugar del equilibrio de carga de DNS. El equilibrio de carga de DNS no funciona con tráfico web del cliente al servidor.

Para obtener más información sobre cómo elegir una solución de equilibrador de carga de hardware, consulte [requisitos del equilibrador de carga de hardware para Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Si decide usar el equilibrio de carga de DNS para un grupo, pero aún tiene que implementar equilibradores de carga de hardware para el tráfico, como el tráfico HTTP, la administración de los equilibradores de carga de hardware será mucho más sencilla. Por ejemplo, configurar el equilibrador de carga de hardware será más sencillo, pues solamente administrará el tráfico HTTPS y HTTP, mientras que el equilibrio de carga de DNS administrará todos los demás protocolos. Para obtener más información, consulte [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md).

Para el tráfico de servidor a servidor, Lync Server 2013 usa el equilibrio de carga que reconoce la topología. Los servidores leen la topología Publicada en el almacén central de administración para obtener los FQDN de los servidores de la topología y distribuyen automáticamente el tráfico entre los servidores. Los administradores no necesitan configurar ni administrar este tipo de equilibrio de carga.

Si utiliza el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no es suficiente con solo quitar las entradas de direcciones IP del FQDN del grupo de servidores. También es preciso quitar la entrada de DNS para el equipo.

</div>

<span> </span>

</div>

</div>

</div>

