---
title: Planear la conectividad con RTC en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Planee la conectividad con RTC Telefonía IP empresarial en Skype Empresarial Server.
ms.openlocfilehash: 492f4e2cc71644cb1e9957f407a549cce5dbc31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813570"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="dc385-103">Planear la conectividad con RTC en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="dc385-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="dc385-104">Planee la conectividad con RTC Telefonía IP empresarial en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="dc385-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="dc385-105">Una solución de telefonía VoIP profesional debe proporcionar llamadas entrantes y realizadas a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="dc385-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="dc385-106">Los usuarios que llaman y reciben llamadas no deben tener en cuenta la tecnología subyacente: desde la perspectiva del usuario, una llamada entre la infraestructura de Telefonía IP empresarial y la RTC debería parecer como otra llamada telefónica.</span><span class="sxs-lookup"><span data-stu-id="dc385-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="dc385-107">Skype Empresarial Server proporciona una conectividad RTC confiable y escalable mediante las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dc385-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="dc385-108">**Troncos SIP** a un proveedor de servicios de telefonía por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="dc385-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="dc385-109">**Conexiones SIP directas** a una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="dc385-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="dc385-110">**Conexiones SIP directas** a una PBX</span><span class="sxs-lookup"><span data-stu-id="dc385-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="dc385-111">Según su tamaño, cobertura geográfica e infraestructura de voz existente, una empresa puede usar una, dos o incluso las tres opciones en varias ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="dc385-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="dc385-112">Para obtener más información sobre estas opciones, consulte las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="dc385-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="dc385-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dc385-113">In this section</span></span>

- [<span data-ttu-id="dc385-114">Enlace troncal SIP en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="dc385-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="dc385-115">Conexiones SIP directas en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="dc385-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="dc385-116">Tronco M:N en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="dc385-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="dc385-117">Reglas de conversión en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="dc385-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="dc385-118">Planear el enrutamiento de voz saliente en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="dc385-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

