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
description: Puede usar la siguiente métrica para calcular el tráfico de usuario en cada sitio y el número de puertos necesarios para admitir ese tráfico.
ms.openlocfilehash: c631361a7ef6d4706632f59366adac3384a6d255
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827690"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="76dbc-103">Estimación del uso y el tráfico de voz para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="76dbc-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="76dbc-104">Puede usar la siguiente métrica para calcular el tráfico de usuario en cada sitio y el número de puertos necesarios para admitir ese tráfico.</span><span class="sxs-lookup"><span data-stu-id="76dbc-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="76dbc-105">Para **Tráfico reducido** (una llamada de RTC por usuario y hora) calcula 15 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="76dbc-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="76dbc-106">Para **Tráfico medio** (dos llamadas de RTC por usuario y hora) calcula 10 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="76dbc-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="76dbc-107">Para **Tráfico denso** (tres llamadas o más de RTC por usuario y hora) calcula 5 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="76dbc-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="76dbc-108">A su vez, el número de puertos determina el número de servidores de mediación y puertas de enlace que serán necesarios.</span><span class="sxs-lookup"><span data-stu-id="76dbc-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="76dbc-109">Las puertas de enlace de la red telefónica conmutada (RTC) que la mayoría de las organizaciones consideran implementar varían de 2 puertos a hasta 960 puertos.</span><span class="sxs-lookup"><span data-stu-id="76dbc-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="76dbc-110">(Hay puertas de enlace incluso más grandes, pero las usan principalmente los proveedores de servicios de telefonía).</span><span class="sxs-lookup"><span data-stu-id="76dbc-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="76dbc-p102">Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. El número de puertas de enlace requeridas equivaldría al número total de puertos requeridos determinado por la capacidad total de las puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="76dbc-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

