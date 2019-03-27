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
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="9f63c-103">Estimar el tráfico y el uso de voz de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="9f63c-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="9f63c-104">Puede usar la siguiente métrica para calcular el tráfico de usuario en cada sitio y el número de puertos que se requieren para admitir dicho tráfico.</span><span class="sxs-lookup"><span data-stu-id="9f63c-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="9f63c-105">Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="9f63c-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="9f63c-106">Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="9f63c-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="9f63c-107">Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="9f63c-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="9f63c-108">El número de puertos a su vez determina el número de servidores de mediación y puertas de enlace que serán necesarios.</span><span class="sxs-lookup"><span data-stu-id="9f63c-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="9f63c-109">Las puertas de enlace de (RTC) de la red telefónica conmutada pública que la mayoría de las organizaciones consideran la implementación de intervalo de tamaño de 2 puertos para los puertos de 960 como máximo.</span><span class="sxs-lookup"><span data-stu-id="9f63c-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="9f63c-110">(Hay puertas de enlace incluso más grandes, pero las usan principalmente por proveedores de servicios de telefonía.)</span><span class="sxs-lookup"><span data-stu-id="9f63c-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="9f63c-p102">Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="9f63c-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

