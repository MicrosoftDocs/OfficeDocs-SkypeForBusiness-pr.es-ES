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
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="ea4cc-103">Estimar el uso y el tráfico de voz de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ea4cc-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="ea4cc-104">Puede usar la siguiente métrica para calcular el tráfico de usuario en cada sitio y el número de puertos necesarios para admitir ese tráfico.</span><span class="sxs-lookup"><span data-stu-id="ea4cc-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="ea4cc-105">Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="ea4cc-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="ea4cc-106">Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="ea4cc-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="ea4cc-107">Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="ea4cc-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="ea4cc-108">El número de puertos, a su vez, determina la cantidad de servidores de mediación y puertas de enlace que se requerirán.</span><span class="sxs-lookup"><span data-stu-id="ea4cc-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="ea4cc-109">Las puertas de enlace de red de telefonía pública conmutada (RTC) que la mayoría de las organizaciones consideran implementar intervalos de tamaño desde dos puertos hasta un máximo de 960 puertos.</span><span class="sxs-lookup"><span data-stu-id="ea4cc-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="ea4cc-110">(Hay incluso puertas de enlace más grandes, pero las usan principalmente los proveedores de servicios de telefonía).</span><span class="sxs-lookup"><span data-stu-id="ea4cc-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="ea4cc-p102">Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="ea4cc-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

