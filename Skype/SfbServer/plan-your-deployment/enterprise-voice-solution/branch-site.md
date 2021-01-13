---
title: Enlace troncal SIP de sitio de sucursal en Skype Empresarial Server
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
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Obtenga información sobre el enlace troncal SIP en sitios de sucursal en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813720"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="d98e9-103">Enlace troncal SIP de sitio de sucursal en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d98e9-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="d98e9-104">Obtenga información sobre el enlace troncal SIP en sitios de sucursal en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d98e9-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d98e9-105">En algunos casos, es posible que deba implementar el enlace troncal SIP distribuido en los sitios de sucursal seleccionados.</span><span class="sxs-lookup"><span data-stu-id="d98e9-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="d98e9-106">Para determinar si se necesita un tronco SIP para un sitio de sucursal y para obtener más información sobre las opciones de topología admitidas para implementar troncos SIP en sitios de sucursal, consulte Enlace troncal SIP en [Skype Empresarial Server.](sip-trunking.md)</span><span class="sxs-lookup"><span data-stu-id="d98e9-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="d98e9-107">Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="d98e9-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="d98e9-108">Cuando decide implementar un tronco SIP de sitio de sucursal, debe realizar un análisis de costos específico del sitio.</span><span class="sxs-lookup"><span data-stu-id="d98e9-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="d98e9-109">Por ejemplo, una empresa que tiene un sitio central en Redmond, Washington y una sucursal en Nueva York, debe realizar un análisis para determinar si se va a implementar un tronco SIP desde el sitio de Nueva York a un proveedor de servicios local.</span><span class="sxs-lookup"><span data-stu-id="d98e9-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="d98e9-110">Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifique qué números DID usarán el tronco SIP y analice la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425).</span><span class="sxs-lookup"><span data-stu-id="d98e9-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="d98e9-111">Puede tener la terminación DID para el sitio de sucursal en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="d98e9-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="d98e9-112">Por ejemplo, el sitio central de Redmond puede hospedar números DID para la sucursal de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="d98e9-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="d98e9-113">Si el costo de implementar un tronco SIP distribuido es menor que el costo de esas llamadas, considere la posibilidad de implementar un tronco SIP en la sucursal de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="d98e9-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="d98e9-114">Otros requisitos de un tronco SIP de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="d98e9-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="d98e9-115">La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas RTC de larga distancia de cada opción.</span><span class="sxs-lookup"><span data-stu-id="d98e9-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="d98e9-116">Si implementa un tronco SIP de sitio de sucursal, también debe determinar los requisitos de resistencia y ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="d98e9-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="d98e9-117">Si el vínculo entre el sitio de sucursal y el sitio central es resistente y tiene suficiente ancho de banda, puede implementar un tronco SIP o una puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="d98e9-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="d98e9-118">No es necesario implementar una aplicación de sucursal con funciones de supervivencia en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="d98e9-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="d98e9-119">Si el vínculo entre el sitio de sucursal y el sitio central no es resistente, implemente una aplicación de sucursal con funciones de supervivencia o implemente un servidor de sucursal con funciones de supervivencia con una puerta de enlace o un tronco SIP en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="d98e9-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

