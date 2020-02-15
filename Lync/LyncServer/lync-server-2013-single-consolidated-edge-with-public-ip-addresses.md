---
title: 'Lync Server 2013: servidor perimetral consolidado único con direcciones IP públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1867abe0cc16190650d2be303a55ecf0dd6a5efd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Si su organización necesita admitir menos de 15.000 conexiones de cliente del servicio perimetral de acceso, 1.000 conexiones de cliente de servicio de conferencia Web de Lync Server activas y 500 sesiones perimetrales A/V concurrentes, y la alta disponibilidad del servidor perimetral no es importante, esta topología ofrece las ventajas de un menor costo de hardware y una implementación más sencilla. Si necesita una mayor capacidad o necesita una alta disponibilidad, debe implementar una topología de servidor perimetral consolidado escalado.

  - <span></span>  
    [Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Servidor perimetral consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> Cuando se usa la dirección IP pública en el servidor perimetral, la puerta de enlace predeterminada en el servidor perimetral deja de ser el firewall o enrutador, pero el enrutador o firewall en el perímetro del perímetro público, que será una dirección pública. El proxy inverso continúa usando el enrutador o firewall asociado con la red perimetral más externa. La diferencia entre el proxy inverso y el servidor perimetral con direcciones IP públicas es que el proxy inverso sigue usando NAT y el servidor perimetral usa una relación de ruta.



</div>

La figura no muestra los directores, una función de servidor opcional implementada en la red interna entre los servidores perimetrales y los grupos de servidores front-end o el servidor. Para obtener más información sobre la topología para directores, consulte [componentes necesarios para el Director en Lync Server 2013](lync-server-2013-components-required-for-the-director.md). La figura representa un único proxy inverso.

<div>


> [!NOTE]  
> La figura se muestra a título orientativo y como ejemplo de direccionamiento de IP, pero no pretende representar los flujos de comunicación reales con el tráfico correcto de entrada y salida. La figura representa una vista posible de alto nivel de tráfico. Los detalles del flujo de tráfico según corresponden a la entrada (a los puertos de escucha) y a la salida (a los servidores o clientes de destino) se representan en el diagrama de resumen de puertos en cada escenario. Por ejemplo, TCP 443 se define en realidad como de entrada exclusivamente (al proxy de servidor perimetral o inverso) y solo es un flujo bidireccional desde la perspectiva del protocolo (TCP). Además, en la figura se muestra la naturaleza del tráfico a medida que cambia, cuando se produce la traducción de direcciones de red (NAT) (la dirección de destino se cambia en la entrada y la dirección de origen en la salida). Los ejemplos de los firewalls interno y externo, y las interfaces de servidor se presentan tan solo a título de referencia. Por último, cuando procede se presentan ejemplos de relaciones de la ruta y la puerta de enlace predeterminadas. Tenga en cuenta también que el diagrama usa la zona DNS <EM>. com</EM> para representar la zona DNS externa tanto para el proxy inverso como para los servidores perimetrales, y la zona DNS de <EM>.net</EM> hace referencia a la zona DNS interna.



</div>

La novedad de Microsoft Lync Server 2013 es la compatibilidad con el direccionamiento IPv6. Parecidas en gran medida a las direcciones IPv4, las direcciones IPv6 se deben asignar de tal manera que formen parte del espacio de direcciones IPv6 asignado. Las direcciones de este tema son solo ejemplos. Deberá obtener direcciones IPv6 que funcionen en la implementación, proporcionen el ámbito adecuado e interoperen con direcciones internas y externas. Windows Server proporciona una característica que es importante para la operación de IPv6 de transición y la comunicación de IPv4 a IPv6 llamada *Dual Stack*. La pila dual es una pila de red independiente y distinta para IPv4 e IPv6. Es lo que hace posible asignar direcciones IPv4 e IPv6 al mismo tiempo, y permite que el servidor se comunique con otros hosts y clientes en función de requisitos particulares.

Los tipos de direcciones típicos que usará para el direccionamiento IPv6 serán las direcciones IPv6 globales (similares a las direcciones IPv4 públicas), las direcciones IPv6 locales únicas (similares a los intervalos de direcciones IPv4 privados) y las direcciones IPv6 locales de vínculo (similares a las direcciones IP privadas automáticas). direcciones en Windows Server para IPv4)

Existen tecnologías de traducción de direcciones de red (NAT) para IPv6 que hacen posible la traducción de direcciones de red de IPv6 a IPv4 (suele conocerse como NAT64) y la traducción de direcciones de red de IPv6 a IPv6 (NAT66). La existencia de tecnologías NAT significa que los cinco escenarios presentados para los servidores perimetrales de Lync Server siguen siendo válidos.

<div>


> [!WARNING]  
> IPv6 es un tema complejo y requiere una planificación minuciosa con el equipo de red y el proveedor de Internet para asegurarse de que las direcciones que asigne en el nivel de servidor de Windows y en el nivel de 2013 de Lync Server funcionarán según lo previsto. Consulte los vínculos al final de este tema para ver más recursos sobre la planeación y el direccionamiento de IPv6.



</div>

**Topología de perímetro consolidado de un solo equipo con direcciones IP públicas**

![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")

<div>


> [!IMPORTANT]  
> Si usa el control de admisión de llamadas (CAC), sigue siendo necesario asignar direcciones IPv4 a la interfaz interna del servidor perimetral. El control de admisión de llamadas emplea direcciones IPv4, con lo cual deberán estar disponibles para que funcione.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen de certificado-perímetro consolidado de un solo consolidado con direcciones IP públicas en Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP públicas en Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Resumen de DNS-servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Arquitectura de direcciones de IP versión 6](http://tools.ietf.org/html/rfc4291)  
[Formato de dirección de unidifusión global IPv6](http://tools.ietf.org/html/rfc3587)  
[Direcciones de unidifusión IPv6 locales únicas](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

