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
- NOCSH
ms.custom:
- Optimization
description: Este artículo proporciona información sobre el uso de un servidor proxy con Teams o Skype empresarial.
ms.openlocfilehash: e71dd21d8d359093b5dada84a8d0788e8dff6af3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708836"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="c8d9a-103">Servidores proxy para Skype Empresarial Online o Teams</span><span class="sxs-lookup"><span data-stu-id="c8d9a-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="c8d9a-104">Este artículo proporciona instrucciones sobre cómo usar un servidor proxy con Teams o Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="c8d9a-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="c8d9a-105">Se recomienda no usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="c8d9a-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="c8d9a-p101">Cuando se trata de equipos o de Skype empresarial por proxy, Microsoft recomienda omitir los servidores proxy. Los servidores proxy no hacen que los equipos ni Skype empresarial sean más seguros porque el tráfico ya está cifrado.</span><span class="sxs-lookup"><span data-stu-id="c8d9a-p101">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="c8d9a-p102">Y tener un proxy puede causar problemas. Los problemas relacionados con el rendimiento pueden introducirse en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos provocarán una experiencia negativa en esos equipos o escenarios de Skype empresarial como audio y vídeo, donde las transmisiones en tiempo real son esenciales.</span><span class="sxs-lookup"><span data-stu-id="c8d9a-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="c8d9a-111">Si necesita usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="c8d9a-111">If you need to use a proxy server</span></span>

<span data-ttu-id="c8d9a-p103">Algunas organizaciones no tienen la opción de omitir un proxy para el tráfico de equipos o de Skype empresarial. Si ese es el caso, deberás tener en mente los problemas mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c8d9a-p103">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="c8d9a-114">Microsoft también recomienda:</span><span class="sxs-lookup"><span data-stu-id="c8d9a-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="c8d9a-115">Usar una resolución DNS externa</span><span class="sxs-lookup"><span data-stu-id="c8d9a-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="c8d9a-116">Usar UDP directo basado en el enrutamiento</span><span class="sxs-lookup"><span data-stu-id="c8d9a-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="c8d9a-117">Permitir el tráfico UDP</span><span class="sxs-lookup"><span data-stu-id="c8d9a-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="c8d9a-118">Siguiendo el resto de recomendaciones de nuestras directrices de redes:</span><span class="sxs-lookup"><span data-stu-id="c8d9a-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="c8d9a-119">Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c8d9a-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="c8d9a-120">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c8d9a-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="c8d9a-121">Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.</span><span class="sxs-lookup"><span data-stu-id="c8d9a-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c8d9a-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c8d9a-122">Related topics</span></span>

[<span data-ttu-id="c8d9a-123">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c8d9a-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 