---
title: Planear la conectividad RTC en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Planear la conectividad RTC en telefonía empresarial en Skype empresarial Server.
ms.openlocfilehash: f0b6aa6b43562fea91885b0d55d75fd234ab97de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276500"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="f5e7c-103">Planear la conectividad RTC en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f5e7c-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="f5e7c-104">Planear la conectividad RTC en telefonía empresarial en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f5e7c-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="f5e7c-105">Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio (QoS) se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="f5e7c-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="f5e7c-106">Los usuarios que realicen y reciban llamadas no deben ser conscientes de la tecnología subyacente: desde el punto de vista del usuario, una llamada entre la infraestructura de telefonía IP empresarial y la RTC debe parecer simplemente otra llamada telefónica.</span><span class="sxs-lookup"><span data-stu-id="f5e7c-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="f5e7c-107">Skype empresarial Server proporciona conectividad RTC confiable y escalable con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f5e7c-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="f5e7c-108">**Troncos SIP** a un proveedor de servicios de telefonía por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="f5e7c-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="f5e7c-109">**Conexiones SIP directas** a una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="f5e7c-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="f5e7c-110">**Conexiones SIP directas** a una PBX</span><span class="sxs-lookup"><span data-stu-id="f5e7c-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="f5e7c-p102">Según cuál sea el tamaño, la cobertura geográfica y la infraestructura de voz existente de una organización, es posible usar una, dos o todas estas opciones en diversas ubicaciones. Para obtener más información sobre estas opciones, mira las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="f5e7c-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f5e7c-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f5e7c-113">In this section</span></span>

- [<span data-ttu-id="f5e7c-114">Troncalización SIP en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f5e7c-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="f5e7c-115">Conexiones SIP directas en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f5e7c-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="f5e7c-116">M:N troncal en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f5e7c-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="f5e7c-117">Reglas de traducción en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f5e7c-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="f5e7c-118">Planear el enrutamiento de voz saliente en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f5e7c-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

