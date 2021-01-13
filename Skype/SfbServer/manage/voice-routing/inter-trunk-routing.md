---
title: Enrutamiento entre troncos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype Empresarial Server proporciona administración de sesiones básicas a través de la compatibilidad con el enrutamiento entretrunkes. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814130"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="4535e-103">Enrutamiento entre troncos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4535e-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="4535e-104">Skype Empresarial Server proporciona administración de sesiones básicas a través de la compatibilidad con el enrutamiento entretrunkes.</span><span class="sxs-lookup"><span data-stu-id="4535e-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="4535e-105">Esta funcionalidad permite a Skype Empresarial Server proporcionar funcionalidades de control de llamadas a sistemas de telefonía descendente.</span><span class="sxs-lookup"><span data-stu-id="4535e-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="4535e-106">El enrutamiento entre troncos puede interconectar sistemas IP-PBX con una puerta de enlace de red de telefonía conmutada (RTC) pública para que las llamadas realizadas desde un teléfono de central de conmutación PBX se puedan enrutan a la RTC y las llamadas RTC entrantes se puedan enrutar a un teléfono PBX.</span><span class="sxs-lookup"><span data-stu-id="4535e-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="4535e-107">Del mismo modo, Skype Empresarial Server puede interconectar dos o más sistemas IP-PBX para que las llamadas se puedan realizar y recibir entre teléfonos PBX desde los diferentes sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="4535e-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="4535e-108">En la figura siguiente se muestra que Skype Empresarial Server proporciona interconexión entre una puerta de enlace RTC y una IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="4535e-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interconectividad entre una puerta de enlace RTC y una IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="4535e-110">En la figura siguiente se muestra cómo Skype Empresarial Server conecta dos sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="4535e-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype Empresarial Server conectando dos sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

