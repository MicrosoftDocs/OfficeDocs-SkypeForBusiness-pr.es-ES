---
title: 'Lync Server 2013: Servidor perimetral consolidado ampliado con equilibradores de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa5a395c8509961937af23c12763a5bf55cc326
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-21_

En la topología del grupo perimetral, dos o más servidores perimetrales se implementan como un grupo de carga equilibrada en la red perimetral del centro de datos. El equilibrio de carga de hardware se usa para el tráfico de las interfaces de los servidores perimetrales externos e internos.

Si su organización requiere soporte técnico para más de 15.000 conexiones de cliente del servicio perimetral de acceso, 1.000 conexiones de cliente del servicio perimetral activas de conferencias web o 500 sesiones de servicio perimetral A/V activas, y la alta disponibilidad del servidor perimetral es importante, Esta topología ofrece las ventajas de la escalabilidad y la compatibilidad con la conmutación por error.

La figura no muestra los directores, un rol de servidor opcional implementado en la red interna entre los servidores perimetrales y los grupos de servidores front-end o el servidor. . Para obtener más información sobre la topología para directores, consulte [componentes necesarios para el director de Lync Server 2013](lync-server-2013-components-required-for-the-director.md).

<div>


> [!NOTE]  
> La cifra que se muestra es para la orientación y el direccionamiento IP de ejemplo, pero no tiene la intención de representar los flujos de comunicación reales con el tráfico entrante y saliente correcto. La figura representa una vista de alto nivel del tráfico posible. Los detalles del flujo de tráfico según pertenecen a los puertos entrante (en los que se escuchan) y salientes (a los servidores de destino o a los clientes) se representan en el diagrama de Resumen de puertos en cada escenario. Por ejemplo, TCP 443 es realmente entrante (solo para el servidor perimetral o proxy inverso) y es solo un flujo bidireccional desde una perspectiva de protocolo (TCP). Además, la figura muestra la naturaleza del tráfico cuando cambia cuando se produce NAT (traducción de direcciones de red) (la dirección de destino se cambia en entrante; la dirección de origen se cambia en saliente). Ejemplo de firewall externo e interno, y las interfaces de servidor se muestran solo con fines de referencia. Por último, se muestra ejemplo de puerta de enlace predeterminada y relaciones de ruta, cuando corresponda. Observe también que el diagrama usa la zona DNS <EM>. com</EM> para representar la zona DNS externa tanto para el proxy inverso como con los servidores perimetrales, y la zona DNS de <EM>.net</EM> hace referencia a la zona DNS interna.



</div>

Las novedades de Microsoft Lync Server 2013 son compatibilidad con el direccionamiento IPv6. Al igual que con el direccionamiento IPv4, las direcciones IPv6 deben asignarse de forma que las direcciones formen parte del espacio de direcciones IPv6 asignado. Las direcciones de este tema solo son por ejemplo. Debe adquirir direcciones IPv6 que funcionen en su implementación, proporcionar el ámbito correcto y interoperar con direcciones internas y externas. Windows Server proporciona una característica importante para la operación de IPv6 de transición y la comunicación de IPv4 a IPv6 denominada *pila dual*. La pila dual es una pila de red separada y distinta para IPv4 y para IPv6. La pila dual es lo que le permite asignar direcciones IPv4 e IPv6 al mismo tiempo y permite que el servidor se comunique con otros hosts y clientes en función de sus requisitos.

Los tipos de dirección típicos que usará para el direccionamiento IPv6 serán las direcciones globales de IPv6 (similares a las direcciones IPv4 públicas), las direcciones locales IPv6 únicas (similares a los intervalos de direcciones IPv4 privadas) y las direcciones locales del vínculo IPv6 (similares a IP privadas automáticas). direcciones en Windows Server para IPv4)

Existen tecnologías de traducción de direcciones de red (NAT) para IPv6 que permitirán NAT IPv6 a IPv4 (comúnmente denominado NAT64) y para NAT IPv6 a IPv6 (comúnmente conocido como NAT66). La existencia de tecnologías NAT significa que los cinco escenarios presentados para los servidores perimetrales de Lync Server siguen siendo válidos.

<div>


> [!WARNING]  
> IPv6 es un tema complejo y requiere un cuidadoso planeamiento con el equipo de redes y el proveedor de Internet para garantizar que las direcciones que asigne en el nivel de servidor de Windows y en el nivel de 2013 de Lync Server funcionen de la manera esperada. Vea los vínculos del final de este tema para conocer otros recursos sobre la planeación y el direccionamiento de IPv6.



</div>

**Configuración del equilibrador de carga de hardware**

Para obtener más información, consulte la sección "requisitos del equilibrador de carga de hardware para un borde A/V" en [componentes necesarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).

**Topología perimetral consolidada escalada (equilibrio de carga de hardware)**

![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2] (images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")

<div>


> [!IMPORTANT]  
> Si está usando control de admisión de llamadas (CAC), aún debe asignar direcciones IPv4 a la interfaz interna del servidor perimetral. CAC usa direcciones IPv4 y debe tener disponibles para funcionar.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen de certificado - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Resumen DNS - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Arquitectura de direccionamiento de IP versión 6](http://tools.ietf.org/html/rfc4291)  
[Formato de dirección global de unidifusión IPv6](http://tools.ietf.org/html/rfc3587)  
[Direcciones de unidifusión IPv6 locales únicas](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

