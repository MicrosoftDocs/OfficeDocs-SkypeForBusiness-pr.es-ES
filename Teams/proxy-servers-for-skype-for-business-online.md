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
description: En este artículo se proporciona información sobre cómo usar un servidor proxy con Microsoft Teams o Skype Empresarial.
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117728"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="fb913-103">Servidores proxy para Skype Empresarial Online o Teams</span><span class="sxs-lookup"><span data-stu-id="fb913-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="fb913-104">En este artículo se proporcionan instrucciones sobre cómo usar un servidor proxy con Teams o Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="fb913-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="fb913-105">Se recomienda no usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="fb913-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="fb913-106">Cuando se trata de tráfico de Teams o Skype Empresarial a través de servidores proxy, Microsoft recomienda omitir servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="fb913-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="fb913-107">Los servidores proxy no hacen que Teams o Skype Empresarial sean más seguros porque el tráfico ya está cifrado.</span><span class="sxs-lookup"><span data-stu-id="fb913-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="fb913-108">Y tener un proxy puede causar problemas.</span><span class="sxs-lookup"><span data-stu-id="fb913-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="fb913-109">Los problemas relacionados con el rendimiento se pueden introducir en el entorno a través de la latencia y la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="fb913-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="fb913-110">Problemas como estos darán como resultado una experiencia negativa en escenarios de Teams o Skype Empresarial como audio y vídeo, donde las transmisiones en tiempo real son esenciales.</span><span class="sxs-lookup"><span data-stu-id="fb913-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="fb913-111">Si necesita usar un servidor proxy</span><span class="sxs-lookup"><span data-stu-id="fb913-111">If you need to use a proxy server</span></span>

<span data-ttu-id="fb913-112">Algunas organizaciones no tienen ninguna opción para omitir un proxy para teams o tráfico de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="fb913-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="fb913-113">Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fb913-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="fb913-114">Microsoft también recomienda:</span><span class="sxs-lookup"><span data-stu-id="fb913-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="fb913-115">Usar una resolución DNS externa</span><span class="sxs-lookup"><span data-stu-id="fb913-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="fb913-116">Usar UDP directo basado en el enrutamiento</span><span class="sxs-lookup"><span data-stu-id="fb913-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="fb913-117">Permitir el tráfico UDP</span><span class="sxs-lookup"><span data-stu-id="fb913-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="fb913-118">Siguiendo las otras recomendaciones de nuestras directrices de red: [Preparar la red de su organización para Teams](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="fb913-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="fb913-119">Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.</span><span class="sxs-lookup"><span data-stu-id="fb913-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fb913-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fb913-120">Related topics</span></span>

[<span data-ttu-id="fb913-121">Principios de conectividad de red de Microsoft 365 y Office 365</span><span class="sxs-lookup"><span data-stu-id="fb913-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="fb913-122">Preparar la red de la organización para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb913-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)