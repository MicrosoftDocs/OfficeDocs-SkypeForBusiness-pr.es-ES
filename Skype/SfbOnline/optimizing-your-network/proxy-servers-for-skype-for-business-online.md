---
title: Servidores proxy para Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: En este artículo se ofrecen algunas indicaciones sobre cómo usar un servidor proxy con Skype Empresarial.
ms.openlocfilehash: 3d83e2f6d4eb2b88a52eb949217ac2f00c72acff
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850017"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="a3069-103">Servidores proxy para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a3069-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="a3069-104">[] En este artículo se ofrecen algunas indicaciones sobre cómo usar un servidor proxy con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="a3069-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="a3069-105">Se recomienda no usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="a3069-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="a3069-p101">En lo que se refiere al tráfico de Skype Empresarial a través de servidores proxy, Microsoft recomienda omitirlos siempre que sea posible. Los servidores proxy no aportan una mayor seguridad a Skype Empresarial, ya que su tráfico ya está cifrado.</span><span class="sxs-lookup"><span data-stu-id="a3069-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="a3069-p102">Y, sin embargo, tener un servidor proxy puede generar problemas; en concreto, se pueden crear problemas relacionados con el rendimiento en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos pueden crear una experiencia negativa en los escenarios de Skype Empresarial que impliquen audio y vídeo, en los que las secuencias en tiempo real son esenciales.</span><span class="sxs-lookup"><span data-stu-id="a3069-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="a3069-111">Si necesita usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="a3069-111">If you need to use a proxy server</span></span>

<span data-ttu-id="a3069-p103">Algunas organizaciones no pueden omitir un servidor proxy para el tráfico de Skype Empresarial. Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a3069-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="a3069-114">Microsoft también recomienda:</span><span class="sxs-lookup"><span data-stu-id="a3069-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="a3069-115">Usar una resolución DNS externa</span><span class="sxs-lookup"><span data-stu-id="a3069-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="a3069-116">Usar UDP directo basado en el enrutamiento</span><span class="sxs-lookup"><span data-stu-id="a3069-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="a3069-117">Permitir el tráfico UDP</span><span class="sxs-lookup"><span data-stu-id="a3069-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="a3069-118">Seguir las otras recomendaciones que aparecen en nuestras directrices de redes:</span><span class="sxs-lookup"><span data-stu-id="a3069-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="a3069-119">Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a3069-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="a3069-120">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a3069-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="a3069-121">Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.</span><span class="sxs-lookup"><span data-stu-id="a3069-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a3069-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a3069-122">Related topics</span></span>

[<span data-ttu-id="a3069-123">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a3069-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 