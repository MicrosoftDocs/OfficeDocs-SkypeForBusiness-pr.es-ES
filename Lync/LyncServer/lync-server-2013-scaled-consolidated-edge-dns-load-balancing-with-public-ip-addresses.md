---
title: Servidor perimetral consolidado escalado, equilibrio de carga DNS con direcciones IP públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: 2b854f6d-3d3f-4961-a5f8-a03f47740df0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204761(v=OCS.15)
ms:contentKeyID: 48183698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07d8e46ce5f4e8a6295b3b2ee09451646ed77847
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Servidor perimetral consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

En la topología del grupo de servidores perimetrales, se implementan dos o más servidores perimetrales como grupo de servidores de carga equilibrada en la red perimetral del centro de datos. El equilibrio de carga del Sistema de nombres de dominio (DNS) se usa con el tráfico hacia las interfaces perimetrales internas y externas.

Si su organización necesita admitir más de 15.000 conexiones de cliente del servicio perimetral de acceso, 1.000 conexiones de cliente del servicio de conferencia Web de Lync Server activas o 500 sesiones perimetrales A/V concurrentes, y/o la alta disponibilidad del servidor perimetral es importante, esta topología ofrece las ventajas de escalabilidad y compatibilidad con la conmutación por error.

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

![7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537](images/JJ204761.7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537(OCS.15).jpg "7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537")

<div>


> [!IMPORTANT]
> Si usa el control de admisión de llamadas (CAC), sigue siendo necesario asignar direcciones IPv4 a la interfaz interna del servidor perimetral. El control de admisión de llamadas emplea direcciones IPv4, con lo cual deberán estar disponibles para que funcione.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen de certificado-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Resumen de Puerto-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Resumen de DNS-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Arquitectura de direcciones de IP versión 6](https://tools.ietf.org/html/rfc4291)  
[Formato de dirección de unidifusión global IPv6](https://tools.ietf.org/html/rfc3587)  
[Direcciones de unidifusión IPv6 locales únicas](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

