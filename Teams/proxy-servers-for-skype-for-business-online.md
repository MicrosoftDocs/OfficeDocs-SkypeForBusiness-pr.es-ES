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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Este artículo proporciona información sobre el uso de un servidor proxy con Microsoft Teams o Skype empresarial.
ms.openlocfilehash: 5a0d35ee2b8c95c4dea30886497e184f57077264
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905682"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Servidores proxy para Skype Empresarial Online o Teams

Este artículo proporciona instrucciones sobre cómo usar un servidor proxy con Teams o Skype empresarial.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Se recomienda no usar un servidor proxy

Cuando se trata de equipos o de Skype empresarial por proxy, Microsoft recomienda omitir los servidores proxy. Los servidores proxy no hacen que los equipos ni Skype empresarial sean más seguros porque el tráfico ya está cifrado.
  
Y tener un proxy puede causar problemas. Los problemas relacionados con el rendimiento pueden introducirse en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos provocarán una experiencia negativa en esos equipos o escenarios de Skype empresarial como audio y vídeo, donde las transmisiones en tiempo real son esenciales.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Si necesita usar un servidor proxy

Algunas organizaciones no tienen la opción de omitir un proxy para el tráfico de equipos o de Skype empresarial. Si ese es el caso, deberás tener en mente los problemas mencionados anteriormente.
  
Microsoft también recomienda:
  
- Usar una resolución DNS externa
    
- Usar UDP directo basado en el enrutamiento
    
- Permitir el tráfico UDP
    
- Siguiendo el resto de recomendaciones de nuestras directrices de redes: [preparar la red de su organización para equipos](prepare-network.md)
  
    
Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.
  
## <a name="related-topics"></a>Temas relacionados

[Principios de conectividad de red de Office 365](https://aka.ms/pnc)

[Preparar la red de la organización para Microsoft Teams](prepare-network.md)
