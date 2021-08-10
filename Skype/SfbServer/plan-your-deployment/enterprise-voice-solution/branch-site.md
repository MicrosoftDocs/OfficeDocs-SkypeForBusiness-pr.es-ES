---
title: Enlace troncal SIP del sitio de sucursal en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Obtenga información sobre el enlace troncal SIP en los sitios de sucursal en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 3a009e7e2a94cd9c172adb4cfb0496efc9a44a03749f6c40c6ee63fb321b7f62
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306961"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Enlace troncal SIP del sitio de sucursal en Skype Empresarial Server
 
Obtenga información sobre el enlace troncal SIP en los sitios de sucursal en Skype Empresarial Server Telefonía IP empresarial.
  
En algunos casos, es posible que deba implementar el enlace troncal SIP distribuido en sitios de sucursal seleccionados. Para determinar si se necesita un tronco SIP para un sitio de sucursal y para obtener más información sobre las opciones de topología admitidas para implementar troncos SIP en sitios de sucursal, vea Enlace troncal SIP en [Skype Empresarial Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal

Cuando decide implementar un tronco SIP del sitio de sucursal, debe realizar un análisis de costos específico del sitio. Por ejemplo, una empresa que tiene un sitio central en Redmond, Washington y un sitio de sucursal en Nueva York, debe realizar un análisis para determinar si se va a implementar un tronco SIP del sitio de Nueva York a un proveedor de servicios local.
  
Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifique qué números DID usarán el tronco SIP y analice la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425). Puede tener la terminación DID para el sitio de sucursal en el sitio central. Por ejemplo, el sitio central de Redmond puede hospedar números DID para el sitio de sucursal de Nueva York. Si el costo de implementar un tronco SIP distribuido es menor que el costo de esas llamadas, considere la posibilidad de implementar un tronco SIP en el sitio de sucursal de Nueva York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Otros requisitos de un tronco SIP de sitio de sucursal

La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas RTC de larga distancia de cada opción. Si implementa un tronco SIP del sitio de sucursal, también debe determinar los requisitos de resistencia y ancho de banda. Si el vínculo entre el sitio de sucursal y el sitio central es resistente y tiene ancho de banda suficiente, puede implementar un tronco SIP o una puerta de enlace. No es necesario implementar una aplicación de sucursal con funciones de supervivencia en el sitio de sucursal. Si el vínculo entre el sitio de sucursal y el sitio central no es resistente, implemente una aplicación de sucursal con funciones de supervivencia o implemente un servidor de sucursal con funciones de supervivencia con una puerta de enlace o un tronco SIP en el sitio de sucursal. 
  

