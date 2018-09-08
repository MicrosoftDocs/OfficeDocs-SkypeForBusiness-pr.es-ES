---
title: Plan para la conectividad de RTC en Skype para Business Server
ms.author: crowe
author: CarolynRowe
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
ms.openlocfilehash: 0c84cc1c683f55ab003164f845071c071c620adc
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881828"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="f9ea6-103">Plan para la conectividad de RTC en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f9ea6-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="f9ea6-104">Plan para la conectividad de RTC en Enterprise Voice en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="f9ea6-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="f9ea6-105">Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio (QoS) se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="f9ea6-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="f9ea6-106">Los usuarios que realizar y reciban llamadas no deben tener en cuenta la tecnología subyacente: desde la perspectiva del usuario, una llamada entre la infraestructura de Enterprise Voice y la RTC debe parecer exactamente igual que otra llamada de teléfono.</span><span class="sxs-lookup"><span data-stu-id="f9ea6-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="f9ea6-107">Skype para Business Server ofrece una conectividad de RTC confiable y escalable mediante el uso de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f9ea6-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="f9ea6-108">**Troncos SIP** a un proveedor de servicios de telefonía por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="f9ea6-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="f9ea6-109">**Conexiones SIP directas** a una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="f9ea6-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="f9ea6-110">**Conexiones SIP directas** a una PBX</span><span class="sxs-lookup"><span data-stu-id="f9ea6-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="f9ea6-p102">Según cuál sea el tamaño, la cobertura geográfica y la infraestructura de voz existente de una organización, es posible usar una, dos o todas estas opciones en diversas ubicaciones. Para obtener más información sobre estas opciones, mira las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="f9ea6-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f9ea6-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f9ea6-113">In this section</span></span>

- [<span data-ttu-id="f9ea6-114">Enlace troncal SIP en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f9ea6-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="f9ea6-115">Conexiones SIP directas en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f9ea6-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="f9ea6-116">Tronco m: n en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f9ea6-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="f9ea6-117">Reglas de conversión de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f9ea6-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="f9ea6-118">Plan para el enrutamiento de voz salientes en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f9ea6-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

