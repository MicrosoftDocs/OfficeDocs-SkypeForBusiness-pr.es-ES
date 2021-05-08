---
title: Servidores proxy para Skype Empresarial Online o Teams
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
description: En este artículo se proporciona información sobre cómo usar un servidor proxy con Skype Empresarial.
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240419"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Servidores proxy para Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En este artículo se proporcionan instrucciones sobre cómo usar un servidor proxy con Skype Empresarial.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Se recomienda no usar un servidor proxy

En lo que se refiere al tráfico de Skype Empresarial a través de servidores proxy, Microsoft recomienda omitirlos siempre que sea posible. Los servidores proxy no hacen que el Skype Empresarial sea más seguro porque el tráfico ya está cifrado.
  
Y tener un proxy puede causar problemas. Los problemas relacionados con el rendimiento se pueden introducir en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos darán como resultado una experiencia negativa en escenarios Teams o Skype Empresarial como audio y vídeo, donde las transmisiones en tiempo real son esenciales.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Si necesita usar un servidor proxy

Algunas organizaciones no pueden omitir un servidor proxy para el tráfico de Skype Empresarial. Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.
  
Microsoft también recomienda:
  
- Usar una resolución DNS externa
    
- Usar UDP directo basado en el enrutamiento
    
- Permitir el tráfico UDP
    
- Siguiendo las otras recomendaciones de nuestras directrices de redes:
    
  - [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance.md)
    
  - [Optimizar la red para Skype Empresarial Online](optimizing-your-network.md)
    
Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.
  
## <a name="related-topics"></a>Temas relacionados

[Optimizar la red para Skype Empresarial Online](optimizing-your-network.md)
 
