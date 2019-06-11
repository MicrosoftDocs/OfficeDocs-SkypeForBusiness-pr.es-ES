---
title: 'Lync Server 2013: Información general sobre los enlaces troncales SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e2c79261923456575e208aa472daae4aaab5f55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Información general sobre los enlaces troncales SIP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

La implementación de un enlace troncal SIP puede suponer un enorme avance a la hora de simplificar las telecomunicaciones de la organización y adaptarse a las mejoras más recientes de las comunicaciones en tiempo real. Una de las principales ventajas del enlace troncal SIP consiste en que es posible consolidar las conexiones de la organización a la red telefónica conmutada (RTC) en un único sitio central, cosa que con la versión anterior no era posible, ya que se usaban troncos de multiplexación por división de tiempo (TDM), lo que normalmente necesitaba un tronco por cada sitio de sucursal.

<div>

## <a name="sip-trunking-in-lync-server"></a>Troncalización SIP en Lync Server

Las capacidades de Troncalización SIP de Lync Server 2013 permiten lo siguiente:

  - Un usuario de la empresa, ya sea dentro o fuera del firewall de la empresa, puede hacer una llamada local o una llamada de larga distancia especificada por un número compatible con E. 164 que haya finalizado en la RTC como servicio del proveedor de servicios correspondiente.

  - Cualquier abonado de RTC puede ponerse en contacto con un usuario empresarial dentro o fuera del Firewall corporativo marcando un número de marcado interno directo que está asociado con ese usuario de la empresa.

</div>

<div>

## <a name="cost-savings"></a>Ahorro económico

El ahorro económico inherente al enlace troncal SIP puede ser considerable:

  - El coste de las llamadas de larga distancia suele ser mucho menor con un tronco SIP.

  - Es posible reducir tanto los costes de manejabilidad como la complejidad de la implementación.

  - Las tasas de interfaz de acceso básica (BRI) y de interfaz de acceso principal (PRI) se pueden evitar si se conecta un tronco SIP directamente al ITSP, a un coste visiblemente menor. En los enlaces troncales TDM, los proveedores de servicios establecen el cargo de las llamadas por minuto. El coste del enlace troncal SIP se puede basar en el uso de ancho de banda, que puede comprarse en incrementos más pequeños y, por tanto, más económicos (el coste real depende del modelo de servicio del ITSP que elijas).

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Enlace troncal SIP en comparación con el hospedaje de una puerta de enlace RTC o PBX IP

Como los troncos SIP se conectan directamente al proveedor de servicios, se puede prescindir de las puertas de enlace RTC y, en consecuencia, del coste de administración y complejidad que estas conllevan. El uso de un tronco SIP se traduce en un ahorro económico muy significativo, ya que requiere menos mantenimiento y administración.

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>Servicios de VoIP ampliados

Con frecuencia, las características de voz constituyen la principal motivación para implementar un enlace troncal SIP, si bien la compatibilidad de voz es solo el primer paso. Con los troncales SIP, puede ampliar las capacidades de VoIP y habilitar Lync Server 2013 para ofrecer un conjunto de servicios más completo. Por ejemplo:

  - La detección de presencia mejorada para dispositivos que no ejecutan Lync Server 2013 puede proporcionar mejor integración con teléfonos móviles, lo que le permite ver cuándo un usuario se encuentra en una llamada de teléfono móvil.

  - El servicio de llamadas de emergencia E9-1-1 permite que los responsables que atienden las llamadas al 911 sepan dónde se encuentra la persona que realiza la llamada a través de su número de teléfono.

<div>


> [!NOTE]  
> Ponte en contacto con tu ITSP para obtener una lista de los servicios que este admite y que puedes habilitar en tu organización.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

