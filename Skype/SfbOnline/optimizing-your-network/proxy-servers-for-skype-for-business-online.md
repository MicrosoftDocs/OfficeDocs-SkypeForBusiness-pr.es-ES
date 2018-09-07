---
title: Servidores proxy para Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: En este artículo se ofrecen algunas indicaciones sobre cómo usar un servidor proxy con Skype Empresarial.
ms.openlocfilehash: 3d83e2f6d4eb2b88a52eb949217ac2f00c72acff
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850017"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Servidores proxy para Skype Empresarial Online

[] En este artículo se ofrecen algunas indicaciones sobre cómo usar un servidor proxy con Skype Empresarial.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Se recomienda no usar un servidor proxy

En lo que se refiere al tráfico de Skype Empresarial a través de servidores proxy, Microsoft recomienda omitirlos siempre que sea posible. Los servidores proxy no aportan una mayor seguridad a Skype Empresarial, ya que su tráfico ya está cifrado.
  
Y, sin embargo, tener un servidor proxy puede generar problemas; en concreto, se pueden crear problemas relacionados con el rendimiento en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos pueden crear una experiencia negativa en los escenarios de Skype Empresarial que impliquen audio y vídeo, en los que las secuencias en tiempo real son esenciales.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Si necesita usar un servidor proxy

Algunas organizaciones no pueden omitir un servidor proxy para el tráfico de Skype Empresarial. Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.
  
Microsoft también recomienda:
  
- Usar una resolución DNS externa
    
- Usar UDP directo basado en el enrutamiento
    
- Permitir el tráfico UDP
    
- Seguir las otras recomendaciones que aparecen en nuestras directrices de redes:
    
  - [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Optimizar la red para Skype Empresarial Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.
  
## <a name="related-topics"></a>Temas relacionados

[Optimizar la red para Skype Empresarial Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 