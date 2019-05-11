---
title: Enrutamiento entre tronco en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype para Business Server proporciona administración de sesiones básica a través de la compatibilidad de enrutamiento entre troncos. '
ms.openlocfilehash: a1486d24c0681df44085db754fda380d653c636b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920516"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="73121-103">Enrutamiento entre tronco en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="73121-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="73121-104">Skype para Business Server proporciona administración de sesiones básica a través de la compatibilidad de enrutamiento entre troncos.</span><span class="sxs-lookup"><span data-stu-id="73121-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="73121-105">Esta capacidad permite Skype para Business Server proporcionar funcionalidades de control de llamada a sistemas de telefonía de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="73121-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="73121-106">El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX.</span><span class="sxs-lookup"><span data-stu-id="73121-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="73121-107">De forma similar, Skype para Business Server puede interconnect dos o más sistemas de IP-PBX para que las llamadas se pueden colocar y recibió entre teléfonos PBX de los distintos sistemas de IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="73121-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="73121-108">La siguiente ilustración muestra Skype para Business Server proporcionando interconectividad entre una puerta de enlace RTC y un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="73121-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interconectividad entre una puerta de enlace RTC y un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="73121-110">En la siguiente figura ilustra Skype para Business Server conectando dos sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="73121-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype para Business Server conectando dos sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

