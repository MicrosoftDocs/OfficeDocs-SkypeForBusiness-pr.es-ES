---
title: Estimar el uso y el tráfico de voz de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Puede usar la siguiente métrica para calcular el tráfico de usuario en cada sitio y el número de puertos necesarios para admitir ese tráfico.
ms.openlocfilehash: f324a3030a8265288a30062fdfc1040a1aea8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816069"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Estimar el uso y el tráfico de voz de Skype empresarial Server
 
Puede usar la siguiente métrica para calcular el tráfico de usuario en cada sitio y el número de puertos necesarios para admitir ese tráfico.
  
> Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.
> 
> Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.
> 
> Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.
    
El número de puertos, a su vez, determina la cantidad de servidores de mediación y puertas de enlace que se requerirán. Las puertas de enlace de red de telefonía pública conmutada (RTC) que la mayoría de las organizaciones consideran implementar intervalos de tamaño desde dos puertos hasta un máximo de 960 puertos. (Hay incluso puertas de enlace más grandes, pero las usan principalmente los proveedores de servicios de telefonía).
  
Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.
  

