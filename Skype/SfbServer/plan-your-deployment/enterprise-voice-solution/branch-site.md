---
title: Troncalización SIP de sitio de sucursal en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Obtenga más información sobre la Troncalización SIP en sucursales en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 14af9a096b368f310b0d4fbce425bf6d1c08696a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277114"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Troncalización SIP de sitio de sucursal en Skype empresarial Server
 
Obtenga más información sobre la Troncalización SIP en sucursales en Skype empresarial Server Enterprise Voice.
  
En algunos casos, es posible que necesites implementar el troncal de SIP distribuido en los sitios de sucursales seleccionados. Para determinar si es necesario un tronco de SIP para un sitio de sucursal y para obtener información sobre las opciones de topología admitidas para la implementación de los troncos SIP en sitios de sucursales, consulte el [enlace troncal de SIP en Skype empresarial Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal

Si decide implementar un tronco SIP de sitio de sucursal, debe realizar un análisis de costos específico del sitio. Por ejemplo, una empresa que tiene un sitio central en Redmond, Washington y un sitio de sucursal en Nueva York debe realizar un análisis para determinar si implementar un tronco SIP desde el sitio de Nueva York a un proveedor de servicios locales.
  
Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifica qué números de llamada directa a la extensión (DID) usarán el tronco SIP y analiza la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425). Puede haber finalizado el sitio de la sucursal en el sitio central. Por ejemplo, el sitio central de Redmond puede hospedar números para el sitio de sucursal de Nueva York. Si el precio de la implementación de un tronco de SIP distribuido es menor que el precio de esas llamadas, considere la posibilidad de implementar un tronco del SIP en el sitio de la sucursal de Nueva York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Otros requisitos de un tronco SIP de sitio de sucursal

La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas de la red telefónica conmutada (RTC) de larga distancia de cada opción. Si implementa un tronco SIP de sitio de sucursal, también necesita determinar los requisitos de resistencia y ancho de banda. Si el vínculo entre el sitio de la sucursal y el sitio central es resistente y tiene suficiente ancho de banda, puede implementar un tronco SIP o una puerta de enlace. No es necesario implementar una aplicación de rama que sea superviviente en el sitio de la sucursal. Si el vínculo entre el sitio de la sucursal y el sitio central no es resistente, implemente un dispositivo de sucursal con la supervivencia o implemente un servidor de sucursal que sea reviviente con una puerta de enlace o un tronco SIP en el sitio de la sucursal. 
  

