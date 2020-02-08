---
title: Servidores proxy para equipos o Skype empresarial online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Este artículo proporciona información sobre el uso de un servidor proxy con Skype empresarial.
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863760"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Servidores proxy para Skype empresarial online

En este artículo se proporcionan instrucciones sobre el uso de un servidor proxy con Skype empresarial.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Se recomienda no usar un servidor proxy

Cuando se trata de tráfico de Skype empresarial por proxy, Microsoft recomienda omitir los servidores proxy. Los servidores proxy no hacen que Skype empresarial sea más seguro porque el tráfico ya está cifrado.
  
Y tener un proxy puede causar problemas. Los problemas relacionados con el rendimiento pueden introducirse en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos provocarán una experiencia negativa en esos equipos o escenarios de Skype empresarial como audio y vídeo, donde las transmisiones en tiempo real son esenciales.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Si necesita usar un servidor proxy

Algunas organizaciones no pueden omitir un servidor proxy para el tráfico de Skype Empresarial. Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.
  
Microsoft también recomienda:
  
- Usar una resolución DNS externa
    
- Usar UDP directo basado en el enrutamiento
    
- Permitir el tráfico UDP
    
- Siguiendo el resto de recomendaciones de nuestras directrices de redes:
    
  - [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance.md)
    
  - [Optimizar la red para Skype Empresarial Online](optimizing-your-network.md)
    
Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.
  
## <a name="related-topics"></a>Temas relacionados

[Optimizar la red para Skype Empresarial Online](optimizing-your-network.md)
 