---
title: Enlace troncal SIP de sitios de sucursal en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Conozca la Troncalización SIP en los sitios de sucursal en Skype para Business Server Telefonía IP empresarial.
ms.openlocfilehash: 92616062c12fce51e3adb816d5ebc299a5dbf3fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server-2015"></a>Enlace troncal SIP de sitios de sucursal en Skype Empresarial Server 2015
 
Conozca la Troncalización SIP en los sitios de sucursal en Skype para Business Server Telefonía IP empresarial.
  
En algunos casos, puede que necesite implementar distribuida Troncalización SIP en sitios de la rama seleccionada. Para determinar si un SIP trunk es necesaria para un sitio de sucursal y para obtener información detallada acerca de las opciones de topología admitida para la implementación de los troncos de SIP en sucursales, consulte [SIP trunking en Skype para Business Server 2015](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal

Cuando se decide implementar un tronco SIP de sitio de sucursal, debe realizar un análisis de costo específicos del sitio. Por ejemplo, una empresa que tiene un sitio central en Redmond, Washington y un sitio de la sucursal de Nueva York, debe hacer un análisis para determinar si debe implementar un troncal SIP desde el sitio de Nueva York a un proveedor de servicio local.
  
Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifica qué números de llamada directa a la extensión (DID) usarán el tronco SIP y analiza la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425). Puede tener terminación DID para el sitio de la sucursal en el sitio central. Por ejemplo, el sitio central de Redmond puede alojar números DID para el sitio de la sucursal de Nueva York. Si el costo de implementar un troncal SIP distribuido es menor que el costo de esas llamadas, considere la posibilidad de implementar un troncal SIP en el sitio de la sucursal de Nueva York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Otros requisitos de un tronco SIP de sitio de sucursal

La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas de la red telefónica conmutada (RTC) de larga distancia de cada opción. Si implementa un tronco SIP de sitio de sucursal, debe determinar los requisitos de ancho de banda y la resiliencia. Si el vínculo entre su sitio de sucursal y el sitio central es resistente y tiene suficiente ancho de banda, puede desplegar un troncal SIP o puerta de enlace. No es necesario implementar un dispositivo de sucursal que sobreviven en el sitio de sucursal. Si el vínculo entre el sitio de sucursal y central no es resistente, implementar un dispositivo de la rama que sobreviven o implementar un servidor de sucursal que sobreviven con una puerta de enlace o la troncal SIP en el sitio de la sucursal. 
  

