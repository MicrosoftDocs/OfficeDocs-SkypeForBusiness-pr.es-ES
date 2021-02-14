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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Este artículo proporciona información sobre cómo usar un servidor proxy con Skype Empresarial.
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863760"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="4550a-103">Servidores proxy para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4550a-103">Proxy servers for Skype for Business Online</span></span>

<span data-ttu-id="4550a-104">Este artículo proporciona instrucciones sobre cómo usar un servidor proxy con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="4550a-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="4550a-105">Se recomienda no usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="4550a-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="4550a-p101">En cuanto al tráfico de Skype Empresarial a través de servidores proxy, Microsoft recomienda omitir servidores proxy. Los servidores proxy no hacen que Skype Empresarial sea más seguro porque el tráfico ya está cifrado.</span><span class="sxs-lookup"><span data-stu-id="4550a-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="4550a-p102">Y tener un proxy puede causar problemas. Los problemas relacionados con el rendimiento pueden introducirse en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos provocarán una experiencia negativa en los escenarios de Teams o Skype Empresarial, como el audio y el vídeo, donde las transmisiones en tiempo real son esenciales.</span><span class="sxs-lookup"><span data-stu-id="4550a-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="4550a-111">Si necesita usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="4550a-111">If you need to use a proxy server</span></span>

<span data-ttu-id="4550a-p103">Algunas organizaciones no pueden omitir un servidor proxy para el tráfico de Skype Empresarial. Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4550a-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="4550a-114">Microsoft también recomienda:</span><span class="sxs-lookup"><span data-stu-id="4550a-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="4550a-115">Usar una resolución DNS externa</span><span class="sxs-lookup"><span data-stu-id="4550a-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="4550a-116">Usar UDP directo basado en el enrutamiento</span><span class="sxs-lookup"><span data-stu-id="4550a-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="4550a-117">Permitir el tráfico UDP</span><span class="sxs-lookup"><span data-stu-id="4550a-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="4550a-118">Siguiendo las demás recomendaciones de nuestras directrices de red:</span><span class="sxs-lookup"><span data-stu-id="4550a-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="4550a-119">Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4550a-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="4550a-120">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4550a-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="4550a-121">Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.</span><span class="sxs-lookup"><span data-stu-id="4550a-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4550a-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4550a-122">Related topics</span></span>

[<span data-ttu-id="4550a-123">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4550a-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 