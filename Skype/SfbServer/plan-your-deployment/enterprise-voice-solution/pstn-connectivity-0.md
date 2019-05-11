---
title: Plan para la conectividad de RTC en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Plan para la conectividad de RTC en Enterprise Voice en Skype para Business Server.
ms.openlocfilehash: aa3449746c539e7b7bf8fe5332fa4313f80fa555
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913573"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="563fc-103">Plan para la conectividad de RTC en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="563fc-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="563fc-104">Plan para la conectividad de RTC en Enterprise Voice en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="563fc-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="563fc-105">Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio (QoS) se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="563fc-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="563fc-106">Los usuarios que realizar y reciban llamadas no deben tener en cuenta la tecnología subyacente: desde la perspectiva del usuario, una llamada entre la infraestructura de Enterprise Voice y la RTC debe parecer exactamente igual que otra llamada de teléfono.</span><span class="sxs-lookup"><span data-stu-id="563fc-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="563fc-107">Skype para Business Server ofrece una conectividad de RTC confiable y escalable mediante el uso de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="563fc-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="563fc-108">**Troncos SIP** a un proveedor de servicios de telefonía por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="563fc-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="563fc-109">**Conexiones SIP directas** a una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="563fc-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="563fc-110">**Conexiones SIP directas** a una PBX</span><span class="sxs-lookup"><span data-stu-id="563fc-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="563fc-p102">Según cuál sea el tamaño, la cobertura geográfica y la infraestructura de voz existente de una organización, es posible usar una, dos o todas estas opciones en diversas ubicaciones. Para obtener más información sobre estas opciones, mira las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="563fc-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="563fc-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="563fc-113">In this section</span></span>

- [<span data-ttu-id="563fc-114">Enlace troncal SIP en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="563fc-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="563fc-115">Conexiones SIP directas en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="563fc-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="563fc-116">Tronco m: n en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="563fc-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="563fc-117">Reglas de conversión de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="563fc-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="563fc-118">Plan para el enrutamiento de voz salientes en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="563fc-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

