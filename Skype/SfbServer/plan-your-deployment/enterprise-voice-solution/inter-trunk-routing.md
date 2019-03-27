---
title: Enrutamiento entre tronco en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Obtenga información sobre cómo Skype para Business Server Enterprise Voice admite enrutamiento troncal entre granjas.
ms.openlocfilehash: 281e722898655e463c3db281014421ae224c2cec
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892663"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="e974a-103">Enrutamiento entre tronco en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e974a-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="e974a-104">Obtenga información sobre cómo Skype para Business Server Enterprise Voice admite enrutamiento troncal entre granjas.</span><span class="sxs-lookup"><span data-stu-id="e974a-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="e974a-105">Skype para Business Server proporciona administración de sesiones básica a través de la compatibilidad de enrutamiento entre troncos.</span><span class="sxs-lookup"><span data-stu-id="e974a-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="e974a-106">Esto permite Skype para Business Server proporcionar funcionalidades de control de llamada a sistemas de telefonía de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="e974a-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="e974a-107">El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX.</span><span class="sxs-lookup"><span data-stu-id="e974a-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="e974a-108">De forma similar, Skype para Business Server puede interconnect dos o más sistemas de IP-PBX para que las llamadas se pueden colocar y recibió entre teléfonos PBX de los distintos sistemas de IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e974a-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="e974a-109">La siguiente ilustración muestra Skype para Business Server proporcionando interconectividad entre una puerta de enlace RTC y un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e974a-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Diagrama de conexión puerta de enlace RTC/IP-PBX en Lync Server](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="e974a-111">En la siguiente figura ilustra Skype para Business Server conectando dos sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e974a-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagrama de interconexión de los sistemas IP-PAX en Lync Server](../../media/inter_trunk02.jpg)
  

