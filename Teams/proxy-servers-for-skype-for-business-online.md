---
title: Servidores proxy para los equipos o Skype para profesionales en línea
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
description: En este artículo se proporciona información acerca del uso de un servidor proxy con los equipos o Skype para la empresa.
ms.openlocfilehash: 1b25d0554ec8c5dca113be0842149dae11850b7e
ms.sourcegitcommit: 327fe807b461aff18b06449f06b9e51ce393c4bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "29972216"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="7083b-103">Servidores proxy para los equipos o Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="7083b-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="7083b-104">En este artículo se proporcionan instrucciones sobre el uso de un servidor proxy con los equipos o Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="7083b-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="7083b-105">Se recomienda no usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="7083b-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="7083b-106">Cuando se trata de los equipos o Skype para el tráfico de negocios a través de los servidores proxy, Microsoft recomienda no usar servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="7083b-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="7083b-107">Los servidores proxy no realiza los equipos o Skype para la empresa más seguro debido a que el tráfico ya está cifrado.</span><span class="sxs-lookup"><span data-stu-id="7083b-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="7083b-108">Y tener un proxy puede provocar problemas.</span><span class="sxs-lookup"><span data-stu-id="7083b-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="7083b-109">Se pueden introducir problemas relacionados con el rendimiento en el entorno a través de latencia y pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="7083b-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="7083b-110">Cuestiones como éstas dará como resultado una experiencia negativa en dichas equipos o Skype para escenarios empresariales como audio y vídeo, donde las secuencias en tiempo real son esenciales.</span><span class="sxs-lookup"><span data-stu-id="7083b-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="7083b-111">Si necesita usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="7083b-111">If you need to use a proxy server</span></span>

<span data-ttu-id="7083b-112">Algunas organizaciones no tienen ninguna opción para omitir a un servidor proxy para los equipos o Skype para el tráfico de negocio.</span><span class="sxs-lookup"><span data-stu-id="7083b-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="7083b-113">Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7083b-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="7083b-114">Microsoft también recomienda:</span><span class="sxs-lookup"><span data-stu-id="7083b-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="7083b-115">Usar una resolución DNS externa</span><span class="sxs-lookup"><span data-stu-id="7083b-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="7083b-116">Usar UDP directo basado en el enrutamiento</span><span class="sxs-lookup"><span data-stu-id="7083b-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="7083b-117">Permitir el tráfico UDP</span><span class="sxs-lookup"><span data-stu-id="7083b-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="7083b-118">Sigue las otras recomendaciones de nuestras pautas de redes:</span><span class="sxs-lookup"><span data-stu-id="7083b-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="7083b-119">Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7083b-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="7083b-120">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7083b-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="7083b-121">Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.</span><span class="sxs-lookup"><span data-stu-id="7083b-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7083b-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7083b-122">Related topics</span></span>

[<span data-ttu-id="7083b-123">Optimizar la red para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7083b-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 