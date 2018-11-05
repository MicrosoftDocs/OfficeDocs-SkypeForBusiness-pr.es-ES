---
title: 'Lync Server 2013: Enlace troncal SIP de sitios de sucursal'
TOCTitle: Enlace troncal SIP de sitios de sucursal
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48276607
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enlace troncal SIP de sitios de sucursal en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

En algunos casos, puede que tenga que implementar el enlace troncal SIP distribuido en los sitios de sucursal seleccionados. Para determinar si se requiere un enlace troncal SIP para un Sitio de sucursal, lea la información proporcionada en [¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)

Para obtener información detallada sobre las opciones de topologías admitidas para la implementación de enlaces troncales SIP en los sitios de sucursal, vea [Soluciones de resistencia de sitios de sucursales en Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

## Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal

La decisión referente a la implementación de un tronco SIP de un Sitio de sucursal requiere un análisis de costos del sitio. Por ejemplo, una empresa que tiene un sitio central en Redmond, Washington, y un Sitio de sucursal en Nueva York debería realizar un análisis para determinar si debe implementar un tronco SIP del sitio de Nueva York a un proveedor de servicios local.

Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifique qué números DID usarán el tronco SIP y analice la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425). Puede tener una terminación DID para el Sitio de sucursal en el sitio central. Por ejemplo, el sitio central de Redmond puede hospedar números DID para el Sitio de sucursal de Nueva York. Si el costo de implementar un tronco SIP distribuido es menor que el costo de esas llamadas, considere la posibilidad de implementar un tronco SIP en el Sitio de sucursal de Nueva York.

## Otros requisitos de un tronco SIP de sitio de sucursal

La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas RTC de larga distancia de cada opción. Si implementa un tronco SIP de Sitio de sucursal, también debe determinar los requisitos de resistencia y de ancho de banda. Si el vínculo entre el Sitio de sucursal y el sitio central es resistente y tiene suficiente ancho de banda, puede implementar un tronco SIP o una puerta de enlace. No es necesario que implemente una Aplicación de sucursal con funciones de supervivencia en el Sitio de sucursal. Si el vínculo entre el Sitio de sucursal y el sitio central no es resistente, implemente una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia y, a continuación, implemente una puerta de enlace o un tronco SIP en el Sitio de sucursal.

