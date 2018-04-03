---
title: Servidores proxy para Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: 0f4d0b82eeaedd4b81ea84a8d8d3a67993d7be96
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="243dd-103">Servidores proxy para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="243dd-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="243dd-104">[] En este artículo se ofrecen algunas indicaciones sobre cómo usar un servidor proxy con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="243dd-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="243dd-105">Se recomienda no usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="243dd-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="243dd-p101">En lo que se refiere al tráfico de Skype Empresarial a través de servidores proxy, Microsoft recomienda omitirlos siempre que sea posible. Los servidores proxy no aportan una mayor seguridad a Skype Empresarial, ya que su tráfico ya está cifrado.</span><span class="sxs-lookup"><span data-stu-id="243dd-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="243dd-p102">Y, sin embargo, tener un servidor proxy puede generar problemas; en concreto, se pueden crear problemas relacionados con el rendimiento en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos pueden crear una experiencia negativa en los escenarios de Skype Empresarial que impliquen audio y vídeo, en los que las secuencias en tiempo real son esenciales.</span><span class="sxs-lookup"><span data-stu-id="243dd-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="243dd-111">Si necesita usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="243dd-111">If you need to use a proxy server</span></span>

<span data-ttu-id="243dd-p103">Algunas organizaciones no pueden omitir un servidor proxy para el tráfico de Skype Empresarial. Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="243dd-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="243dd-114">Microsoft también recomienda:</span><span class="sxs-lookup"><span data-stu-id="243dd-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="243dd-115">Usar una resolución DNS externa</span><span class="sxs-lookup"><span data-stu-id="243dd-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="243dd-116">Usar UDP directo basado en el enrutamiento</span><span class="sxs-lookup"><span data-stu-id="243dd-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="243dd-117">Permitir el tráfico UDP</span><span class="sxs-lookup"><span data-stu-id="243dd-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="243dd-118">Seguir las otras recomendaciones que aparecen en nuestras directrices de redes:</span><span class="sxs-lookup"><span data-stu-id="243dd-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="243dd-119">Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="243dd-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="243dd-120">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="243dd-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="243dd-121">Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.</span><span class="sxs-lookup"><span data-stu-id="243dd-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a><span data-ttu-id="243dd-122">Proveedores de servidores proxy con opciones de configuración o soporte de Skype Empresarial integrados</span><span class="sxs-lookup"><span data-stu-id="243dd-122">Proxy vendors with built-in Skype for Business support or configuration options</span></span>

<span data-ttu-id="243dd-123">En esta sección encontrará información sobre proveedores de servidores proxy que proporcionan productos o servicios que han demostrado que funcionan correctamente con el tráfico de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="243dd-123">This section will contain information about proxy vendors who provide products or services that are proven to work successfully with Skype for Business traffic.</span></span>
  
<span data-ttu-id="243dd-124">Para organizaciones que usen **soluciones del servidor proxy Bluecoat**, se ha publicado un nuevo firmware que aborda varios problemas relacionados con:</span><span class="sxs-lookup"><span data-stu-id="243dd-124">For organizations using **Bluecoat Proxy solutions**, a new firmware has been released which addresses several issues with:</span></span>
    
  - <span data-ttu-id="243dd-125">Interceptación SSL</span><span class="sxs-lookup"><span data-stu-id="243dd-125">SSL interception</span></span>
    
  - <span data-ttu-id="243dd-126">Comprobaciones OCSP/SRL</span><span class="sxs-lookup"><span data-stu-id="243dd-126">OCSP/SRL checks</span></span>
    
  - <span data-ttu-id="243dd-127">SIP sobre TLS</span><span class="sxs-lookup"><span data-stu-id="243dd-127">SIP over TLS</span></span>
    
  - <span data-ttu-id="243dd-128">Soporte para TURN</span><span class="sxs-lookup"><span data-stu-id="243dd-128">support for TURN</span></span>
    
<span data-ttu-id="243dd-p104">El soporte nativo de Bluecoat para Skype Empresarial se puede activar fácilmente, lo que permitirá identificar el tráfico relevante y gestionarlo correctamente. De este modo se garantiza una autenticación, señalización y un flujo de tráfico de medios óptimos para proporcionar una fantástica experiencia de usuario sin comprometer la seguridad.</span><span class="sxs-lookup"><span data-stu-id="243dd-p104">Bluecoat's native support for Skype for Business can easily be enabled, allowing for the identification of relevant traffic, and managing it appropriately. This ensures optimal authentication, signaling, and media traffic flow, to provide a great user experience without security concerns.</span></span>
    
<span data-ttu-id="243dd-131">Consulte el siguiente vínculo si Proxy Bluecoat es una parte de la topología de red:https://support.symantec.com/en_US/article.DOC9757.html</span><span class="sxs-lookup"><span data-stu-id="243dd-131">Please refer to the following link if Bluecoat Proxy is a part of your network topology: https://support.symantec.com/en_US/article.DOC9757.html</span></span>

## <a name="related-topics"></a><span data-ttu-id="243dd-132">See also</span><span class="sxs-lookup"><span data-stu-id="243dd-132">Related topics</span></span>

[<span data-ttu-id="243dd-133">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="243dd-133">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 