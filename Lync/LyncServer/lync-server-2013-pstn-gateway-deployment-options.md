---
title: 'Lync Server 2013: Opciones de implementación de la puerta de enlace RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137c9996429e953db22bea0c0dbd382f5a7af9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Opciones de implementación de la puerta de enlace RTC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>Puertas de enlace RTC

Las puertas de enlace de red de telefonía pública conmutada (RTC) son componentes de hardware de terceros que traducen las señales y los medios entre la infraestructura de telefonía IP empresarial y la RTC, ya sea directamente o a través de una conexión a los troncos SIP. En cualquiera de las dos topologías, la puerta de enlace finaliza la RTC. La puerta de enlace está aislada en su propia subred y está conectada a la red de la empresa a través del servidor de mediación.

Una empresa con varios sitios normalmente implementaría una o más puertas de enlace en cada sitio. Los sitios de sucursales se pueden conectar a la RTC a través de una puerta de enlace o a través de un equipo de sucursales con la supervivencia, que combina puerta de enlace y servidores en un único cuadro. Si los sitios de sucursal usan una puerta de enlace, se necesita un registrador y un servidor de mediación en el sitio, a menos que el vínculo WAN sea resistente. Uno o varios servidores de mediación, que se colocan en servidores front-end, pueden enrutar las llamadas de una o más puertas de enlace en cada sitio. Recomendamos que el registrador, el servidor de mediación y la puerta de enlace necesaria en el sitio se implementen como un equipo de sucursal con la supervivencia.

Determinar el número, el tamaño y la ubicación de las puertas de enlace RTC es quizás la decisión más importante y costosa que debe tomarse al planear la infraestructura de voz empresarial.

Estas son las principales preguntas que debe tener en cuenta. Tenga en cuenta que las respuestas a estas preguntas son totalmente interdependientes

  - ¿Cuántas puertas de enlace RTC se necesitan? La respuesta depende del número de usuarios, el número anticipado de llamadas simultáneas (carga de tráfico) y el número de sitios (cada sitio necesita uno).

  - ¿Qué tamaño deberían tener las puertas de enlace? La respuesta depende del número de usuarios del sitio y de la carga de tráfico.

  - ¿Dónde se deben ubicar los gateways? La respuesta depende en parte de la topología y en parte de la distribución geográfica de su organización.

También debe tener en cuenta las opciones de topología de la puerta de enlace (para obtener información detallada, vea topologías de puertas de enlace más adelante en este tema).

<div>

## <a name="mn-trunk-support"></a>Compatibilidad con troncos M:N

Los servidores de mediación pueden enrutar las llamadas a través de varias puertas de enlace, controladores de borde de sesión (SBCs) proporcionados por proveedores de servicios de telefonía por Internet o una combinación de ambos. Además, varios servidores de mediación en el grupo pueden interactuar con varias puertas de enlace. La ruta lógica definida entre un servidor de mediación y la puerta de enlace se denomina *troncal*. Cuando un usuario interno realiza una llamada RTC, la lógica de enrutamiento de salida en el grupo de servidores front-end elige el tronco que se va a enrutar sobre todas las combinaciones posibles que pueden estar disponibles para enrutar esa llamada en particular. Con el equilibrio de carga de DNS, si una llamada no logra alcanzar una puerta de enlace debido a un problema con un servidor de mediación en particular en el grupo, la llamada se volverá a intentar con un servidor de mediación alternativo en el grupo.

Para obtener más información sobre la planeación de varias puertas de enlace, consulte [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).

Para obtener más información sobre otras mejoras de enrutamiento saliente, vea [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="gateway-topologies"></a>Topologías de puerta de enlace

Cuando considere las preguntas fundamentales de la implementación de puertas de enlace, siga estos pasos:

1.  Contar los sitios en los que desea proporcionar conectividad RTC mediante telefonía IP empresarial.

2.  Estimar el tráfico de cada sitio (número de usuarios y número promedio de llamadas por hora por usuario).

3.  Implemente una o más puertas de enlace en cada sitio para controlar el tráfico anticipado.

La topología de la puerta de enlace distribuida resultante se muestra en la siguiente ilustración.

**Topología de puerta de enlace distribuida**

![Diagrama de topología de puerta de enlace distribuida] (images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagrama de topología de puerta de enlace distribuida")

Con esta topología, las llamadas entre los trabajadores de cada sitio y entre sitios se enrutan a través de la intranet. Las llamadas a la RTC se enrutan a través de la red IP de la empresa a las puertas de enlace que están más cerca de la ubicación de los números de destino. Pero, ¿qué sucede si su organización admite decenas, cientos o incluso miles de sitios distribuidos en uno o más continentes, ya que muchas instituciones financieras y otras grandes empresas sí lo hacen? En estos casos, no es práctico implementar una puerta de enlace independiente en cada sitio.

Para solucionar este problema, muchas de las grandes empresas prefieren implementar uno o varios sitios centrales de telefonía grandes, tal y como se muestra en la siguiente ilustración.

**Topología de sitio central de telefonía**

![Topología de puerta de enlace de centro de datos] (images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topología de puerta de enlace de centro de datos")

En esta topología, se implementan varias puertas de enlace grandes suficientes para dar cabida a la carga de usuarios prevista en cada sitio central. El proveedor de servicios telefónicos de la empresa reenvía todas las llamadas a los usuarios de la empresa a un sitio central. La lógica de enrutamiento en el sitio central determina si la llamada se debe enrutar a través de la intranet o de la RTC.

</div>

<div>

## <a name="gateway-location"></a>Ubicación de la puerta de enlace

La ubicación de la puerta de enlace también puede determinar los tipos de puertas de enlace que elija y cómo se configuran. Hay docenas de protocolos de RTC, ninguno de los cuales es un estándar de todo el mundo. Si todas las puertas de enlace están ubicadas en un solo país o región, esto no es un problema, pero si encuentra puertas de enlace en varios países o regiones, cada una de ellas debe estar configurada de acuerdo con los estándares de la RTC de ese país o región. Además, las puertas de enlace que están certificadas para funcionar, por ejemplo, Canadá, pueden no estar certificadas en India, Brasil ni la Unión Europea.

</div>

<div>

## <a name="gateway-size-and-number"></a>Número y tamaño de la puerta de enlace

Las puertas de enlace RTC que la mayoría de las organizaciones considerará para implementar intervalos de 2 a tan sólo puertos de 960. (Hay incluso puertas de enlace más grandes, pero las usan principalmente los proveedores de servicios de telefonía). Al estimar el número de puertos que necesita su organización, siga estas pautas:

  - Las organizaciones con uso de telefonía leve (una llamada de RTC por usuario por hora) deben asignar un puerto por cada 15 usuarios. Por ejemplo, si tiene 20 usuarios, necesitará una puerta de enlace con dos puertos.

  - Las organizaciones con uso moderado de telefonía (dos llamadas RTC por usuario por hora) deben asignar un puerto por cada 10 usuarios. Por ejemplo, si tiene 100 usuarios, necesitará un total de 10 puertos asignados entre una o más puertas de enlace.

  - Las organizaciones con uso intensivo de telefonía (tres o más llamadas RTC por usuario por hora) deben asignar un puerto por cada cinco usuarios. Por ejemplo, si tiene 47.000 usuarios, necesitará un total de 9.400 puertos asignados entre al menos 10 puertas de enlace grandes.

  - Se pueden adquirir puertos adicionales a medida que aumenta el número de usuarios o la cantidad de tráfico de la organización.

Para cualquier número de usuarios que deba admitir, tiene la opción de implementar menos puertas de enlace, más grandes o más pequeñas. Como regla, se recomienda usar un mínimo de dos puertas de enlace para una organización para mantener la disponibilidad si una de ellas falla.

Cada puerta de enlace RTC que implemente debe tener al menos un servidor de mediación correspondiente.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

