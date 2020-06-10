---
title: Servidores proxy para Skype Empresarial Online o Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Este artículo proporciona información sobre el uso de un servidor proxy con Microsoft Teams o Skype empresarial.
ms.openlocfilehash: 3d8e2e067cce4214f51ee54ec08bafa1f4100770
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665962"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="6529d-103">Servidores proxy para Skype Empresarial Online o Teams</span><span class="sxs-lookup"><span data-stu-id="6529d-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="6529d-104">Este artículo proporciona instrucciones sobre cómo usar un servidor proxy con Teams o Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="6529d-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="6529d-105">Se recomienda no usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="6529d-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="6529d-p101">Cuando se trata de equipos o de Skype empresarial por proxy, Microsoft recomienda omitir los servidores proxy. Los servidores proxy no hacen que los equipos ni Skype empresarial sean más seguros porque el tráfico ya está cifrado.</span><span class="sxs-lookup"><span data-stu-id="6529d-p101">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="6529d-p102">Y tener un proxy puede causar problemas. Los problemas relacionados con el rendimiento pueden introducirse en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos provocarán una experiencia negativa en esos equipos o escenarios de Skype empresarial como audio y vídeo, donde las transmisiones en tiempo real son esenciales.</span><span class="sxs-lookup"><span data-stu-id="6529d-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="6529d-111">Si necesita usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="6529d-111">If you need to use a proxy server</span></span>

<span data-ttu-id="6529d-p103">Algunas organizaciones no tienen la opción de omitir un proxy para el tráfico de equipos o de Skype empresarial. Si ese es el caso, deberás tener en mente los problemas mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6529d-p103">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="6529d-114">Microsoft también recomienda:</span><span class="sxs-lookup"><span data-stu-id="6529d-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="6529d-115">Usar una resolución DNS externa</span><span class="sxs-lookup"><span data-stu-id="6529d-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="6529d-116">Usar UDP directo basado en el enrutamiento</span><span class="sxs-lookup"><span data-stu-id="6529d-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="6529d-117">Permitir el tráfico UDP</span><span class="sxs-lookup"><span data-stu-id="6529d-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="6529d-118">Siguiendo el resto de recomendaciones de nuestras directrices de redes: [preparar la red de su organización para equipos](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="6529d-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="6529d-119">Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.</span><span class="sxs-lookup"><span data-stu-id="6529d-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6529d-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6529d-120">Related topics</span></span>

[<span data-ttu-id="6529d-121">Principios de conectividad de red de Microsoft 365 y Office 365</span><span class="sxs-lookup"><span data-stu-id="6529d-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="6529d-122">Preparar la red de la organización para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6529d-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)
