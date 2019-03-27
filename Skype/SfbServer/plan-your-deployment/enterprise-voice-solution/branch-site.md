---
title: Enlace troncal SIP sitio de sucursal en Skype para Business Server
ms.reviewer: ''
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
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Obtenga información sobre el enlace troncal SIP en sitios de sucursal en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 333cb5f150efb431d4c7c43a0d78b601cb8ff268
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896612"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="604e8-103">Enlace troncal SIP sitio de sucursal en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="604e8-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="604e8-104">Obtenga información sobre el enlace troncal SIP en sitios de sucursal en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="604e8-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="604e8-105">En algunos casos, es posible que necesite implementar el enlace troncal SIP distribuido en sitios de sucursal seleccionado.</span><span class="sxs-lookup"><span data-stu-id="604e8-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="604e8-106">Para determinar si un SIP tronco es necesaria para un sitio de sucursal y para obtener información detallada acerca de las opciones de topologías admitidas para la implementación de enlaces troncales SIP en sitios de sucursal, consulte el [enlace troncal SIP en Skype para Business Server](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="604e8-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="604e8-107">Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="604e8-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="604e8-108">Cuando decide implementar un tronco SIP de sitio de sucursal, debe realizar un análisis de costo específicos del sitio.</span><span class="sxs-lookup"><span data-stu-id="604e8-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="604e8-109">Por ejemplo, una empresa que tenga un sitio central en Redmond, Washington y un sitio de sucursal de Nueva York, debe hacer un análisis para determinar si se debe implementar un tronco SIP desde el sitio de Nueva York a un proveedor de servicio local.</span><span class="sxs-lookup"><span data-stu-id="604e8-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="604e8-110">Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifica qué números de llamada directa a la extensión (DID) usarán el tronco SIP y analiza la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425).</span><span class="sxs-lookup"><span data-stu-id="604e8-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="604e8-111">Puede tener terminación DID para el sitio de sucursal en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="604e8-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="604e8-112">Por ejemplo, el sitio central de Redmond puede hospedar números DID para el sitio de sucursal de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="604e8-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="604e8-113">Si el costo de implementar un tronco SIP distribuido es menor que el costo de esas llamadas, considere la posibilidad de implementar un tronco SIP en el sitio de sucursal de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="604e8-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="604e8-114">Otros requisitos de un tronco SIP de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="604e8-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="604e8-115">La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas de la red telefónica conmutada (RTC) de larga distancia de cada opción.</span><span class="sxs-lookup"><span data-stu-id="604e8-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="604e8-116">Si implementa un tronco SIP de sitio de sucursal, debe determinar los requisitos de ancho de banda y la resistencia.</span><span class="sxs-lookup"><span data-stu-id="604e8-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="604e8-117">Si el vínculo entre el sitio central y el sitio de sucursal es resistente y tiene suficiente ancho de banda, puede implementar un tronco SIP o puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="604e8-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="604e8-118">No es necesario implementar una aplicación de sucursal con funciones de supervivencia en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="604e8-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="604e8-119">Si el vínculo entre el sitio central y el sitio de sucursal no es resistente, implementar una aplicación de sucursal con funciones de supervivencia o implementar un servidor de sucursal con funciones de supervivencia con una puerta de enlace o un tronco SIP en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="604e8-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

