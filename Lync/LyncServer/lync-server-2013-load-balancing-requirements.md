---
title: Requisitos del equilibrio de carga de Lync Server 2013
TOCTitle: Requisitos del equilibrio de carga de Lync Server 2013
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48275885
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos del equilibrio de carga de Lync Server 2013

 

_**Última modificación del tema:** 2012-10-05_

Si tiene Grupos de servidores front-end, grupos de Director o grupos de Servidor perimetral, deberá implementar el equilibrio de carga en estos grupos. El equilibrio de carga distribuye el tráfico entre los servidores de los grupos de servidores.

Lync Server 2013 admite dos tipos de soluciones de equilibro de carga para el tráfico cliente a servidor: el equilibrio de carga del Sistema de nombres de dominio (DNS) y el equilibrio de carga de hardware. El equilibrio de carga DNS ofrece varias ventajas, como una administración más sencilla, una solución de problemas más eficaz y la capacidad de aislar gran parte del tráfico de Lync Server de posibles problemas en el equilibrador de carga de hardware.

Decida qué solución de equilibrio de carga es adecuada para cada grupo de su implementación, teniendo en cuenta las restricciones siguientes:

  - La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar el equilibrio de carga de DNS en una interfaz y el equilibrio de carga de hardware en la otra.

  - Algunos tipos de tráfico requieren un equilibrador de carga de hardware. Por ejemplo, el tráfico HTTP requiere un equilibrador de carga de hardware en lugar del equilibrio de carga de DNS. El equilibrio de carga de DNS no funciona con tráfico web de cliente a servidor.

Para obtener más información sobre la selección de una solución de equilibrador de carga de hardware, vea [Requisitos del equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Si decide usar el equilibrio de carga DNS para un grupo pero aún tiene que implementar equilibradores de carga de hardware para tráfico como el tráfico HTTP, la administración de los equilibradores de carga de hardware será mucho más sencilla. Por ejemplo, configurar el equilibrador de carga de hardware será más sencillo, pues solamente administrará el tráfico HTTPS y HTTP, mientras que el equilibrio de carga de DNS administrará todos los demás protocolos. Para obtener información detallada, consulte [Equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md).

Para un tráfico de servidor a servidor, el Lync Server 2013 usa un equilibrio de carga preparado para topología. los servidores leen la topología publicada en el Almacén de administración central para obtener los FQDN de los servidores en la topología y distribuir automáticamente el tráfico entre los servidores. los administradores no necesitan configurar o administrar este tipo de equilibrio de carga.

Si utiliza el equilibrio de carga de DNS y debe bloquear el tráfico a una computadora específica, no es suficiente con solo eliminar las entradas de direcciones IP del grupo FQDN. También debe eliminar la entrada DNS para la computadora.

