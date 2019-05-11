---
title: Enlace troncal SIP sitio de sucursal en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Obtenga información sobre el enlace troncal SIP en sitios de sucursal en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: ac92b2c02279568d7658315808e5419d2263d6a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895573"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Enlace troncal SIP sitio de sucursal en Skype para Business Server
 
Obtenga información sobre el enlace troncal SIP en sitios de sucursal en Skype para Business Server Enterprise Voice.
  
En algunos casos, es posible que necesite implementar el enlace troncal SIP distribuido en sitios de sucursal seleccionado. Para determinar si un SIP tronco es necesaria para un sitio de sucursal y para obtener información detallada acerca de las opciones de topologías admitidas para la implementación de enlaces troncales SIP en sitios de sucursal, consulte el [enlace troncal SIP en Skype para Business Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal

Cuando decide implementar un tronco SIP de sitio de sucursal, debe realizar un análisis de costo específicos del sitio. Por ejemplo, una empresa que tenga un sitio central en Redmond, Washington y un sitio de sucursal de Nueva York, debe hacer un análisis para determinar si se debe implementar un tronco SIP desde el sitio de Nueva York a un proveedor de servicio local.
  
Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifica qué números de llamada directa a la extensión (DID) usarán el tronco SIP y analiza la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425). Puede tener terminación DID para el sitio de sucursal en el sitio central. Por ejemplo, el sitio central de Redmond puede hospedar números DID para el sitio de sucursal de Nueva York. Si el costo de implementar un tronco SIP distribuido es menor que el costo de esas llamadas, considere la posibilidad de implementar un tronco SIP en el sitio de sucursal de Nueva York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Otros requisitos de un tronco SIP de sitio de sucursal

La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas de la red telefónica conmutada (RTC) de larga distancia de cada opción. Si implementa un tronco SIP de sitio de sucursal, debe determinar los requisitos de ancho de banda y la resistencia. Si el vínculo entre el sitio central y el sitio de sucursal es resistente y tiene suficiente ancho de banda, puede implementar un tronco SIP o puerta de enlace. No es necesario implementar una aplicación de sucursal con funciones de supervivencia en el sitio de sucursal. Si el vínculo entre el sitio central y el sitio de sucursal no es resistente, implementar una aplicación de sucursal con funciones de supervivencia o implementar un servidor de sucursal con funciones de supervivencia con una puerta de enlace o un tronco SIP en el sitio de sucursal. 
  

