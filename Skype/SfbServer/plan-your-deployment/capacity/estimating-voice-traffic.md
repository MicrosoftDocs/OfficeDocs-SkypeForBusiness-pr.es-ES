---
title: Estimar el tráfico y el uso de la voz de Skype para Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 10/22/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Puede utilizar la métrica siguiente para estimar el tráfico de usuarios en cada sitio y el número de puertos que son necesarios para admitir ese tráfico.
ms.openlocfilehash: dffcfdf7dcf70162b2a9c9ce65ab56b9025a4db0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server-2015"></a>Estimar el tráfico y el uso de la voz de Skype para Business Server 2015
 
Puede utilizar la métrica siguiente para estimar el tráfico de usuarios en cada sitio y el número de puertos que son necesarios para admitir ese tráfico.
  
> Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.
    
> Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.
    
> Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.
    
El número de puertos a su vez determina el número de servidores de mediación y puertas de enlace que serán necesarios. Las puertas de enlace de (RTC) de la red telefónica pública conmutada que la mayoría de las organizaciones consideran la implementación de intervalo de tamaño de 2 puertos a puertos como máximo 960. (Hay puertas de enlace aún mayores, pero se utilizan principalmente por proveedores de servicios de telefonía).
  
Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.
  

