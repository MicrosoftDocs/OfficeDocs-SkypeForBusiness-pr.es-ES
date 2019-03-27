---
title: Estimar el tráfico y el uso de voz de Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Puede usar la siguiente métrica para calcular el tráfico de usuario en cada sitio y el número de puertos que se requieren para admitir dicho tráfico.
ms.openlocfilehash: 4475be7d233bbfa34c1d2aa8b62d578ebb985423
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893128"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Estimar el tráfico y el uso de voz de Skype para Business Server
 
Puede usar la siguiente métrica para calcular el tráfico de usuario en cada sitio y el número de puertos que se requieren para admitir dicho tráfico.
  
> Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.
> 
> Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.
> 
> Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.
    
El número de puertos a su vez determina el número de servidores de mediación y puertas de enlace que serán necesarios. Las puertas de enlace de (RTC) de la red telefónica conmutada pública que la mayoría de las organizaciones consideran la implementación de intervalo de tamaño de 2 puertos para los puertos de 960 como máximo. (Hay puertas de enlace incluso más grandes, pero las usan principalmente por proveedores de servicios de telefonía.)
  
Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.
  

