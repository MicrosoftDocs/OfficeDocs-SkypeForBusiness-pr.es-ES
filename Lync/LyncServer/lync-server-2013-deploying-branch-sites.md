---
title: 'Lync Server 2013: Implementación de sitios de sucursales'
TOCTitle: Implementación de sitios de sucursales
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48274520
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de sitios de sucursales en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Los usuarios de las sucursales sacan el máximo partido de la funcionalidad de Lync Server 2013 del servidor ubicado en el sitio central al que la sucursal está asociada. Todas y cada una de las sucursales están asociadas a exactamente un sitio central. Para poder realizar llamadas a y desde la red telefónica conmutada pública (RTC), una sucursal puede contener cualquiera de los siguientes elementos:

  - Una puerta de enlace RTC y, probablemente, un servidor de mediación

  - Un tronco SIP

  - Una infraestructura de voz existente con una central de conmutación (PBX)

  - Una Aplicación de sucursal con funciones de supervivencia

  - Una Servidor de sucursal con funciones de supervivencia

Las sucursales con una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia son más resistentes en caso de errores de sitio central o de red de área extensa que las que carecen de estas soluciones. Por ejemplo, en un sitio con una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia implementado, los usuarios pueden seguir realizando y recibiendo llamadas RTC si la red que conecta la sucursal con el sitio central está fuera de servicio. Otra forma de lograr una sucursal resistente consiste en usar una puerta de enlace RTC o un tronco SIP con una implementación de Lync Server a escala completa en la sucursal.

Para obtener más detalles a la hora de decidir cuál es la implementación de sucursal adecuada para su organización, incluidos los requisitos previos y otras consideraciones de planeación, consulte " [Planeación de la conectividad con RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)” y “[Planificar la resistencia de voz en sitios de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)” en la documentación de planeación.

## En esta sección

  - [Proporcionar conectividad RTC en un sitio de sucursal en Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

