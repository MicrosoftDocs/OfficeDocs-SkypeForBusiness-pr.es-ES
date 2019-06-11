---
title: 'Lync Server 2013: Servidor perimetral consolidado simple con direcciones IP privadas y NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f37395f840e8811d343f11f6ee2a84bd4fcfbf82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a>Servidor perimetral consolidado simple con direcciones IP privadas y NAT en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Si su organización requiere soporte técnico para menos de 15.000 conexiones de cliente del servicio perimetral de acceso, 1.000 conexiones de cliente del servicio de conferencias por Internet de Lync Server activas y 500 sesiones concurrentes de borde A/V, y la alta disponibilidad del servidor perimetral no es importante, esta topología ofrece las ventajas de un menor costo de hardware y una implementación más simple. Si necesita una mayor capacidad o necesita una alta disponibilidad, debe implementar una topología de servidor perimetral consolidado a escala. Para obtener más información, vea una de las siguientes opciones:

  - <span></span>  
    [Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Perímetro consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

La figura no muestra los directores, un rol de servidor opcional implementado en la red interna entre los servidores perimetrales y los grupos de servidores front-end o el servidor. Para obtener más información sobre la topología para directores, consulte [componentes necesarios para el director de Lync Server 2013](lync-server-2013-components-required-for-the-director.md). La figura representa un único proxy inverso.

<div>


> [!NOTE]  
> La cifra que se muestra es para la orientación y el direccionamiento IP de ejemplo, pero no tiene la intención de representar los flujos de comunicación reales con el tráfico entrante y saliente correcto. La figura representa una vista de alto nivel del tráfico posible. Los detalles del flujo de tráfico según pertenecen a los puertos entrante (en los que se escuchan) y salientes (a los servidores de destino o a los clientes) se representan en el diagrama de Resumen de puertos en cada escenario. Por ejemplo, TCP 443 es realmente entrante (solo para el extremo o proxy inverso) y es solo un flujo bidireccional desde una perspectiva de protocolo (TCP). Además, la figura muestra la naturaleza del tráfico cuando cambia cuando se produce NAT (traducción de direcciones de red) (la dirección de destino se cambia en entrante; la dirección de origen se cambia en saliente). Ejemplo de firewall externo e interno, y las interfaces de servidor se muestran solo con fines de referencia. Por último, se muestra ejemplo de puerta de enlace predeterminada y relaciones de ruta, cuando corresponda. Observe también que el diagrama usa la zona DNS <EM>. com</EM> para representar la zona DNS externa tanto para el proxy inverso como con los servidores perimetrales, y la zona DNS de <EM>.net</EM> hace referencia a la zona DNS interna.



</div>

Las novedades de Microsoft Lync Server 2013 son compatibilidad con el direccionamiento IPv6. Al igual que con el direccionamiento IPv4, las direcciones IPv6 deben asignarse de forma que las direcciones formen parte del espacio de direcciones IPv6 asignado. Las direcciones de este tema solo son por ejemplo. Debe adquirir direcciones IPv6 que funcionen en su implementación, proporcionar el ámbito correcto y interoperar con direcciones internas y externas. Windows Server proporciona una característica importante para la operación de IPv6 de transición y la comunicación de IPv4 a IPv6 denominada *pila dual*. La pila dual es una pila de red separada y distinta para IPv4 y para IPv6. La pila dual es lo que le permite asignar direcciones IPv4 e IPv6 al mismo tiempo y permite que el servidor se comunique con otros hosts y clientes en función de sus requisitos.

Los tipos de dirección típicos que usará para el direccionamiento IPv6 serán las direcciones globales de IPv6 (similares a las direcciones IPv4 públicas), las direcciones locales IPv6 únicas (similares a los intervalos de direcciones IPv4 privadas) y las direcciones locales del vínculo IPv6 (similares a IP privadas automáticas). direcciones en Windows Server para IPv4)

Existen tecnologías de traducción de direcciones de red (NAT) para IPv6 que permitirán NAT IPv6 a IPv4 (comúnmente denominado NAT64) y para NAT IPv6 a IPv6 (comúnmente conocido como NAT66). La existencia de tecnologías NAT significa que los cinco escenarios presentados para los servidores perimetrales de Lync Server siguen siendo válidos.

<div>


> [!WARNING]  
> IPv6 es un tema complejo y requiere un cuidadoso planeamiento con el equipo de redes y el proveedor de Internet para garantizar que las direcciones que asigne en el nivel de servidor de Windows y en el nivel de 2013 de Lync Server funcionen de la manera esperada. Vea los vínculos del final de este tema para conocer otros recursos sobre la planeación y el direccionamiento de IPv6.



</div>

**Única topología de borde consolidado**

![d9b889c1-587c-4732-9b68-841186ccff78] (images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")

<div>


> [!IMPORTANT]  
> Si está usando control de admisión de llamadas (CAC), aún debe asignar direcciones IPv4 a la interfaz interna del servidor perimetral. CAC usa direcciones IPv4 y debe tener disponibles para funcionar.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen de certificado - Servidor perimetral consolidado simple con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Resumen de puerto - Perímetro consolidado de un solo equipo con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Resumen DNS - Servidor perimetral consolidado simple con dirección IP privada mediante NAT en Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

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

