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
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server-2015"></a><span data-ttu-id="e76ef-103">Estimar el tráfico y el uso de la voz de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e76ef-103">Estimating voice usage and traffic for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e76ef-104">Puede utilizar la métrica siguiente para estimar el tráfico de usuarios en cada sitio y el número de puertos que son necesarios para admitir ese tráfico.</span><span class="sxs-lookup"><span data-stu-id="e76ef-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="e76ef-105">Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="e76ef-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
    
> <span data-ttu-id="e76ef-106">Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="e76ef-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
    
> <span data-ttu-id="e76ef-107">Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="e76ef-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="e76ef-108">El número de puertos a su vez determina el número de servidores de mediación y puertas de enlace que serán necesarios.</span><span class="sxs-lookup"><span data-stu-id="e76ef-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="e76ef-109">Las puertas de enlace de (RTC) de la red telefónica pública conmutada que la mayoría de las organizaciones consideran la implementación de intervalo de tamaño de 2 puertos a puertos como máximo 960.</span><span class="sxs-lookup"><span data-stu-id="e76ef-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="e76ef-110">(Hay puertas de enlace aún mayores, pero se utilizan principalmente por proveedores de servicios de telefonía).</span><span class="sxs-lookup"><span data-stu-id="e76ef-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="e76ef-p102">Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="e76ef-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

