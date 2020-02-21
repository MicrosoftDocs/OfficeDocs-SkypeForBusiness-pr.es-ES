---
title: 'Lync Server 2013: tronco de M:N'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accb2efafddc9253deda7fa20006dd9093e32496
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a>M:N troncal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Lync Server 2013 admite mayor flexibilidad para la definición de un tronco con fines de enrutamiento de llamadas de versiones anteriores. Un tronco es una asociación lógica entre un servidor de mediación y un número de puerto de escucha con una puerta de enlace y un número de puerto de escucha. Esto implica varias cosas: un servidor de mediación puede tener varios troncos en la misma puerta de enlace; un servidor de mediación puede tener varios troncos en puertas de enlace distintas; por el contrario, una puerta de enlace puede tener varios troncos en diferentes servidores de mediación.

Todavía es necesario crear un tronco raíz cuando se agrega una puerta de enlace a la topología de Lync mediante el generador de topologías. El número de puertas de enlace que un servidor de mediación determinado puede gestionar depende de la capacidad de procesamiento del servidor durante las horas pico. Si implementa un servidor de mediación en hardware que supera los requisitos mínimos de hardware para Lync Server 2013, tal y como se describe en [hardware compatible para Lync server 2013](lync-server-2013-supported-hardware.md) en la documentación de compatibilidad, la estimación del número de llamadas activas sin desviar que un servidor de mediación independiente puede controlar es aproximadamente 1000 llamadas. Cuando se implementa en hardware que cumple con estas especificaciones, se espera que el servidor de mediación realice la transcodificación, pero sigue enrutando las llamadas para varias puertas de enlace, incluso si las puertas de enlace no admiten la omisión de medios.

Al definir una ruta de llamada, se especifican los troncos asociados con dicha ruta, pero no se especifica qué servidores de mediación están asociados a esa ruta. En su lugar, puede usar el generador de topologías para asociar troncos con servidores de mediación. En otras palabras, el enrutamiento determina qué tronco usar para una llamada y, posteriormente, el servidor de mediación asociado con ese tronco recibe la señalización de esa llamada.

El servidor de mediación se puede implementar como un grupo de servidores; Este grupo se puede combinar con un grupo de servidores front-end o se puede implementar como un grupo independiente. Cuando un servidor de mediación se combina con un grupo de servidores front-end, el tamaño del grupo puede ser como máximo 12 (el límite del tamaño del grupo de registrador). En conjunto, estas nuevas capacidades aumentan la confiabilidad y la flexibilidad de implementación para los servidores de mediación, pero requieren capacidades asociadas en las entidades pares siguientes:

  - **Puerta de enlace RTC.** Una puerta de enlace completa de Lync Server 2013 debe implementar el equilibrio de carga de DNS, lo que permite que una puerta de enlace de red telefónica conmutada (RTC) válida actúe como un equilibrador de carga para un grupo de servidores de mediación y, por lo tanto, para equilibrar la carga de llamadas en el grupo.

  - **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del grupo de servidores de mediación al SBC, el SBC puede recibir conexiones de cualquier servidor de mediación del grupo. En la dirección desde el SBC hasta el grupo, el tráfico puede enviarse a cualquier servidor de mediación del grupo. Esto puede conseguirse mediante el equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una alternativa es proporcionar al proveedor de servicios las direcciones IP de todos los servidores de mediación en el grupo, y el proveedor de servicios aprovisionará estos en su SBC como un tronco SIP independiente para cada servidor de mediación. Después, el proveedor de servicios administrará el equilibrio de carga para sus propios servidores. No todos los proveedores de servicios y SBC admiten estas capacidades. Además, es posible que el proveedor de servicios exija costos adicionales. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.

  - **IP-PBX.** En la dirección del grupo de servidores de mediación a la terminación SIP de IP-PBX, el IP-PBX puede recibir conexiones de cualquier servidor de mediación del grupo. En la dirección desde el IP-PBX hacia el grupo, el tráfico puede enviarse a cualquier servidor de mediación del grupo. Como la mayoría de IP-PBX no admiten el equilibrio de carga de DNS, se recomienda que las conexiones SIP directas individuales se puedan definir desde el IP-PBX a cada servidor de mediación del grupo. El sistema IP-PBX administrará su propio equilibrio de carga distribuyendo el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en el sistema IP-PBX. Si un IP-PBX en particular admite este concepto de grupo de tronco y cómo se interseca con la arquitectura de clústeres y la redundancia de IP-PBX que se debe determinar antes de decidir si un clúster de servidores de mediación puede interactuar correctamente con una IP-PBX.

Un grupo de servidores de mediación debe tener una vista uniforme de la puerta de enlace del mismo nivel con la que interactúe. Esto significa que todos los miembros del grupo de servidores obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por lo tanto, no hay forma de segmentar el grupo para que algunos servidores de mediación se comuniquen solo con determinados homólogos de puerta de enlace para las llamadas salientes. Si esta segmentación es necesaria, se debe usar un grupo independiente de servidores de mediación. Por ejemplo, esto sucedería si las puertas de enlace RTC, troncos SIP o sistemas IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo de servidores, tal y como se ha explicado anteriormente en este mismo tema.

Una puerta de enlace RTC, un IP-PBX o un tronco del mismo nivel SIP específicos pueden enrutar a varios troncos o servidores de mediación. El número de puertas de enlace que un determinado grupo de servidores de mediación puede controlar depende del número de llamadas que usan la omisión de medios. Si un gran número de llamadas usa la omisión de medios, un servidor de mediación del grupo puede controlar muchas más llamadas, ya que solo es necesario procesar la capa de señalización.

</div>

<span> </span>

</div>

</div>

</div>

