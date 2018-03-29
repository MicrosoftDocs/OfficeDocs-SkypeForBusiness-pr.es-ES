---
title: Enrutamiento entre troncos en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Aprenda cómo Skype para Telefonía IP empresarial de Business Server admite el enrutamiento Inter-tronco.
ms.openlocfilehash: 58872fccca335792ccbdf03c2c8475c328197426
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="inter-trunk-routing-in-skype-for-business-server-2015"></a><span data-ttu-id="60012-103">Enrutamiento entre troncos en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="60012-103">Inter-trunk routing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="60012-104">Aprenda cómo Skype para Telefonía IP empresarial de Business Server admite el enrutamiento Inter-tronco.</span><span class="sxs-lookup"><span data-stu-id="60012-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="60012-105">Skype para Business Server proporciona administración de sesión básica mediante el soporte de enrutamiento intertrunk.</span><span class="sxs-lookup"><span data-stu-id="60012-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="60012-106">Esto permite Skype para Business Server proporcionar funcionalidades de control de llamada a sistemas de telefonía de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="60012-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="60012-107">El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX.</span><span class="sxs-lookup"><span data-stu-id="60012-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="60012-108">De igual forma, Skype para Business Server puede interconectar dos o más sistemas de IP-PBX para que pueden colocarse llamadas y recibidas entre los teléfonos PBX de los diferentes sistemas de IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="60012-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="60012-109">La figura siguiente ilustra Skype para Business Server proporcionar interconectividad entre una puerta de enlace PSTN y un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="60012-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Diagrama de conexión puerta de enlace RTC/IP-PBX en Lync Server](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="60012-111">En la siguiente figura ilustra Skype para Business Server conectar dos sistemas de IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="60012-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagrama de interconexión de los sistemas IP-PAX en Lync Server](../../media/inter_trunk02.jpg)
  

