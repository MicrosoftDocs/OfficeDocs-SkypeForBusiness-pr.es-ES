---
title: Enrutamiento entre troncales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Obtenga información sobre cómo Skype empresarial Server Enterprise Voice admite el enrutamiento entre troncales.
ms.openlocfilehash: f590463eced61cf2e8b19a27f7cfc2dd648c63c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276834"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="cafb4-103">Enrutamiento entre troncales en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cafb4-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="cafb4-104">Obtenga información sobre cómo Skype empresarial Server Enterprise Voice admite el enrutamiento entre troncales.</span><span class="sxs-lookup"><span data-stu-id="cafb4-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="cafb4-105">Skype empresarial Server proporciona administración de sesiones básica mediante la compatibilidad con el enrutamiento de intertroncalización.</span><span class="sxs-lookup"><span data-stu-id="cafb4-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="cafb4-106">Esto permite que Skype empresarial Server ofrezca funcionalidades de control de llamadas a sistemas de telefonía indirectos.</span><span class="sxs-lookup"><span data-stu-id="cafb4-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="cafb4-107">El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX.</span><span class="sxs-lookup"><span data-stu-id="cafb4-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="cafb4-108">De forma similar, Skype empresarial Server puede interconectar dos o más sistemas IP-PBX para que las llamadas se puedan realizar y recibir entre los teléfonos PBX de los diferentes sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="cafb4-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="cafb4-109">En la ilustración siguiente se muestra cómo Skype empresarial Server proporciona interconectividad entre una puerta de enlace PSTN y una IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="cafb4-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Diagrama de conexión puerta de enlace RTC/IP-PBX en Lync Server](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="cafb4-111">En la siguiente ilustración se muestra cómo Skype empresarial Server conecta dos sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="cafb4-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagrama de interconexión de los sistemas IP-PAX en Lync Server](../../media/inter_trunk02.jpg)
  

