---
title: Planificar la conectividad con RTC en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Plan para la conectividad de RTC en Enterprise Voice en Skype para Business Server.
ms.openlocfilehash: 228391049988c2eb886c0cb4e7caccce6f55ff3b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server-2015"></a><span data-ttu-id="9fc81-103">Planificar la conectividad con RTC en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fc81-103">Plan for PSTN connectivity in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9fc81-104">Plan para la conectividad de RTC en Enterprise Voice en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="9fc81-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="9fc81-105">Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio (QoS) se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="9fc81-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="9fc81-106">Los usuarios que realizar y reciban llamadas no deben tener en cuenta la tecnología subyacente: desde la perspectiva del usuario, una llamada entre la infraestructura de Enterprise Voice y la RTC debe parecer exactamente igual que otra llamada de teléfono.</span><span class="sxs-lookup"><span data-stu-id="9fc81-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="9fc81-107">Skype para Business Server ofrece una conectividad de RTC confiable y escalable mediante el uso de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9fc81-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="9fc81-108">**Troncos SIP** a un proveedor de servicios de telefonía por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="9fc81-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="9fc81-109">**Conexiones SIP directas** a una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="9fc81-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="9fc81-110">**Conexiones SIP directas** a una PBX</span><span class="sxs-lookup"><span data-stu-id="9fc81-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="9fc81-p102">Según cuál sea el tamaño, la cobertura geográfica y la infraestructura de voz existente de una organización, es posible usar una, dos o todas estas opciones en diversas ubicaciones. Para obtener más información sobre estas opciones, mira las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="9fc81-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="9fc81-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9fc81-113">In this section</span></span>

- [<span data-ttu-id="9fc81-114">Enlace troncal SIP en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fc81-114">SIP trunking in Skype for Business Server 2015</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="9fc81-115">Conexiones SIP directas en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fc81-115">Direct SIP connections in Skype for Business Server 2015</span></span>](direct-sip.md)
    
- [<span data-ttu-id="9fc81-116">Tronco m: n en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fc81-116">M:N trunk in Skype for Business Server 2015</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="9fc81-117">Reglas de conversión de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fc81-117">Translation rules in Skype for Business Server 2015</span></span>](translation-rules.md)
    
- [<span data-ttu-id="9fc81-118">Plan para el enrutamiento de voz salientes en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fc81-118">Plan for outbound voice routing in Skype for Business Server 2015</span></span>](outbound-voice-routing.md)
    

