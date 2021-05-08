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
description: En este artículo se proporciona información sobre cómo usar un servidor proxy con Skype Empresarial.
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240419"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="241d3-103">Servidores proxy para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="241d3-103">Proxy servers for Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="241d3-104">En este artículo se proporcionan instrucciones sobre cómo usar un servidor proxy con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="241d3-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="241d3-105">Se recomienda no usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="241d3-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="241d3-106">En lo que se refiere al tráfico de Skype Empresarial a través de servidores proxy, Microsoft recomienda omitirlos siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="241d3-106">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="241d3-107">Los servidores proxy no hacen que el Skype Empresarial sea más seguro porque el tráfico ya está cifrado.</span><span class="sxs-lookup"><span data-stu-id="241d3-107">Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="241d3-108">Y tener un proxy puede causar problemas.</span><span class="sxs-lookup"><span data-stu-id="241d3-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="241d3-109">Los problemas relacionados con el rendimiento se pueden introducir en el entorno a través de la latencia y la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="241d3-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="241d3-110">Problemas como estos darán como resultado una experiencia negativa en escenarios Teams o Skype Empresarial como audio y vídeo, donde las transmisiones en tiempo real son esenciales.</span><span class="sxs-lookup"><span data-stu-id="241d3-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="241d3-111">Si necesita usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="241d3-111">If you need to use a proxy server</span></span>

<span data-ttu-id="241d3-p103">Algunas organizaciones no pueden omitir un servidor proxy para el tráfico de Skype Empresarial. Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="241d3-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="241d3-114">Microsoft también recomienda:</span><span class="sxs-lookup"><span data-stu-id="241d3-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="241d3-115">Usar una resolución DNS externa</span><span class="sxs-lookup"><span data-stu-id="241d3-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="241d3-116">Usar UDP directo basado en el enrutamiento</span><span class="sxs-lookup"><span data-stu-id="241d3-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="241d3-117">Permitir el tráfico UDP</span><span class="sxs-lookup"><span data-stu-id="241d3-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="241d3-118">Siguiendo las otras recomendaciones de nuestras directrices de redes:</span><span class="sxs-lookup"><span data-stu-id="241d3-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="241d3-119">Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="241d3-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="241d3-120">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="241d3-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="241d3-121">Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.</span><span class="sxs-lookup"><span data-stu-id="241d3-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="241d3-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="241d3-122">Related topics</span></span>

[<span data-ttu-id="241d3-123">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="241d3-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 
