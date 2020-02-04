---
title: 'Lync Server 2013: M:N troncal'
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
ms.openlocfilehash: 4485380d6de5d247511b863761fcf7c75d38a29b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a>M:N troncal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Lync Server 2013 admite una mayor flexibilidad en la definición de un tronco para el enrutamiento de llamadas de versiones anteriores. Un tronco es una asociación lógica entre un servidor de mediación y un número de puerto de escucha con una puerta de enlace y un número de puerto de escucha. Esto implica varias cosas: un servidor de mediación puede tener varios troncos para la misma puerta de enlace. un servidor de mediación puede tener varios troncos en diferentes puertas de enlace. a la inversa, una puerta de enlace puede tener varios troncos en diferentes servidores de mediación.

Aún es necesario crear un tronco de raíz cuando se agrega una puerta de enlace a la topología de Lync con el generador de topologías. El número de puertas de enlace que un servidor de mediación dado puede controlar depende de la capacidad de procesamiento del servidor durante las horas de mayor actividad. Si implementa un servidor de mediación en hardware que supera los requisitos mínimos de hardware para Lync Server 2013, según se describe en [hardware compatible con Lync server 2013](lync-server-2013-supported-hardware.md) en la documentación de compatibilidad, la estimación de cuántas llamadas de no omisión activas puede controlar un servidor de mediación independiente es de aproximadamente 1000 llamadas. Cuando se implementa en el hardware que cumple estas especificaciones, se espera que el servidor de mediación realice la transcodificación, pero sigue enrutando las llamadas para varias puertas de enlace incluso si las puertas de enlace no admiten la omisión de medios.

Al definir una ruta de llamada, especifica los troncos asociados a esa ruta, pero no especifica qué servidores de mediación están asociados a esa ruta. En su lugar, use el generador de topología para asociar troncos con servidores de mediación. En otras palabras, el enrutamiento determina qué tronco se debe usar para una llamada y, posteriormente, el servidor de mediación asociado con ese tronco se envía a través de la señalización de esa llamada.

El servidor de mediación se puede implementar como un grupo; Este grupo se puede colocar con un grupo de servidores front-end o se puede implementar como un grupo independiente. Cuando un servidor de mediación se encuentra con un grupo de servidores front-end, el tamaño del grupo puede ser de hasta 12 (el límite del tamaño del conjunto de registradores). Tomadas en conjunto, estas nuevas capacidades aumentan la confiabilidad y la flexibilidad de implementación para servidores de mediación, pero requieren capacidades asociadas en las siguientes entidades de pares:

  - **Puerta de enlace RTC.** Una puerta de enlace completa de Lync Server 2013 debe implementar el equilibrio de carga de DNS, lo que permite que una puerta de enlace de red telefónica conmutada (RTC) válida actúe como equilibrado de carga para un grupo de servidores de mediación y, por lo tanto, equilibre la carga de las llamadas en el grupo.

  - **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del grupo de servidores de mediación al SBC, el SBC puede recibir conexiones de cualquier servidor de mediación del grupo. En la dirección de SBC a la agrupación, el tráfico puede enviarse a cualquier servidor de mediación del grupo. Esto puede conseguirse a través del equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una alternativa es conceder al proveedor de servicios las direcciones IP de todos los servidores de mediación en el grupo y el proveedor de servicios los aprovisionará en su SBC como un enlace SIP independiente para cada servidor de mediación. Después, el proveedor de servicios gestionará el equilibrio de carga para sus propios servidores. Es posible que no todos los proveedores de servicios o SBC admitan estas capacidades. Además, es posible que el proveedor de servicios exija cargos adicionales para esta capacidad. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.

  - **IP-PBX.** En la dirección del grupo de servidores de mediación a la terminación SIP IP-PBX, el IP-PBX puede recibir conexiones de cualquier servidor de mediación del grupo. En la dirección desde el IP-PBX a la agrupación, el tráfico puede enviarse a cualquier servidor de mediación del grupo. Dado que la mayoría de las PBX IP no admiten el equilibrio de carga de DNS, recomendamos que se definan conexiones SIP directas individuales desde la PBX IP a cada servidor de mediación del grupo. La IP-PBX gestionará su propio equilibrio de carga al distribuir el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en la IP-PBX. Si un IP-PBX en particular admite este concepto de grupo de troncal y cómo se intersecta con la arquitectura de clúster y redundancia de IP-PBX, debe determinarse antes de decidir si un clúster de servidor de mediación puede interactuar correctamente con un IP-PBX.

Un grupo de servidores de mediación debe tener una vista uniforme de la puerta de enlace del mismo nivel con la que interactúa. Esto significa que todos los miembros del grupo obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por lo tanto, no hay ninguna forma de segmentar el grupo para que algunos servidores de mediación se comuniquen con solo algunos pares de puertas de enlace para las llamadas salientes. Si tal segmentación es necesaria, se debe usar un grupo de servidores de mediación independiente. Por ejemplo, esto sucedería si las puertas de enlace RTC, los troncos SIP o las IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo, tal y como se ha explicado anteriormente en este mismo tema.

Una puerta de enlace RTC en particular, IP-PBX o un troncal del mismo nivel SIP puede enrutar a varios servidores o troncos de mediación. El número de puertas de enlace que puede controlar un determinado grupo de servidores de media depende del número de llamadas que usan la omisión de medios. Si una gran cantidad de llamadas usa omisión de medios, un servidor de mediación del grupo puede controlar muchas más llamadas, porque solo es necesario el procesamiento de la capa de señalización.

</div>

<span> </span>

</div>

</div>

</div>

