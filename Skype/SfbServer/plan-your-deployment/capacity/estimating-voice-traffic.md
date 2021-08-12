---
title: Estimación del uso y el tráfico de voz para Skype Empresarial Server
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
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Puede usar la siguiente métrica para estimar el tráfico de usuarios en cada sitio y el número de puertos necesarios para admitir ese tráfico.
ms.openlocfilehash: 470590baf8ce5735b77576292fc6558d916dd3a7173b95c113b74d42f35c5224
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318843"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Estimación del uso y el tráfico de voz para Skype Empresarial Server
 
Puede usar la siguiente métrica para estimar el tráfico de usuarios en cada sitio y el número de puertos necesarios para admitir ese tráfico.
  
> Para **Tráfico reducido** (una llamada de RTC por usuario y hora) calcula 15 usuarios por puerto.
> 
> Para **Tráfico medio** (dos llamadas de RTC por usuario y hora) calcula 10 usuarios por puerto.
> 
> Para **Tráfico denso** (tres llamadas o más de RTC por usuario y hora) calcula 5 usuarios por puerto.
    
El número de puertos a su vez determina el número de servidores de mediación y puertas de enlace que se necesitan. Las puertas de enlace de red telefónica conmutada (RTC) que la mayoría de las organizaciones consideran la posibilidad de implementar un intervalo de tamaño de 2 puertos a hasta 960 puertos. (Hay puertas de enlace incluso más grandes, pero las usan principalmente los proveedores de servicios de telefonía).
  
Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. El número de puertas de enlace requeridas equivaldría al número total de puertos requeridos determinado por la capacidad total de las puertas de enlace.
  

