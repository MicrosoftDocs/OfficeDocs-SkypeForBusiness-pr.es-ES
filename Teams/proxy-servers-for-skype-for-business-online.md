---
title: Servidores proxy para Skype Empresarial Online o Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: En este artículo se proporciona información sobre el uso de un servidor proxy con Microsoft Teams o Skype Empresarial.
ms.openlocfilehash: 61a1878b3c7057de7dddbcd63c480f80c2f16e0f
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045439"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Servidores proxy para Skype Empresarial Online o Teams

Este artículo proporciona instrucciones sobre el uso de un servidor proxy con Teams o Skype Empresarial.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Se recomienda no usar un servidor proxy

En lo que respecta a Teams o Skype Empresarial tráfico a través de servidores proxy, Microsoft recomienda omitirlos. Los servidores proxy no Teams ni Skype Empresarial más seguros porque el tráfico ya está cifrado.
  
Además, tener un proxy puede causar problemas. Los problemas relacionados con el rendimiento se pueden introducir en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos producirán una experiencia negativa en escenarios Teams o Skype Empresarial como audio y vídeo, donde las transmisiones en tiempo real son esenciales.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Si necesita usar un servidor proxy

Algunas organizaciones no tienen ninguna opción para omitir un proxy para Teams o Skype Empresarial tráfico. Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.
  
Microsoft también recomienda:
  
- Usar una resolución DNS externa
    
- Usar UDP directo basado en el enrutamiento
    
- Permitir el tráfico UDP
    
- Siguiendo las otras recomendaciones de nuestras directrices de redes: [Preparar la red de su organización para Teams](prepare-network.md)
  
    
Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.
  
## <a name="related-topics"></a>Temas relacionados

[Principios de conectividad de red de Microsoft 365 y Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Preparar la red de la organización para Microsoft Teams](prepare-network.md)