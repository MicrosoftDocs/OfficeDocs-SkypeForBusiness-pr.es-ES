---
title: Enlace troncal SIP de sitios de sucursal en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Conozca la Troncalización SIP en los sitios de sucursal en Skype para Business Server Telefonía IP empresarial.
ms.openlocfilehash: 92616062c12fce51e3adb816d5ebc299a5dbf3fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server-2015"></a><span data-ttu-id="87e60-103">Enlace troncal SIP de sitios de sucursal en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="87e60-103">Branch site SIP trunking in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="87e60-104">Conozca la Troncalización SIP en los sitios de sucursal en Skype para Business Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="87e60-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="87e60-105">En algunos casos, puede que necesite implementar distribuida Troncalización SIP en sitios de la rama seleccionada.</span><span class="sxs-lookup"><span data-stu-id="87e60-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="87e60-106">Para determinar si un SIP trunk es necesaria para un sitio de sucursal y para obtener información detallada acerca de las opciones de topología admitida para la implementación de los troncos de SIP en sucursales, consulte [SIP trunking en Skype para Business Server 2015](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="87e60-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server 2015](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="87e60-107">Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="87e60-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="87e60-108">Cuando se decide implementar un tronco SIP de sitio de sucursal, debe realizar un análisis de costo específicos del sitio.</span><span class="sxs-lookup"><span data-stu-id="87e60-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="87e60-109">Por ejemplo, una empresa que tiene un sitio central en Redmond, Washington y un sitio de la sucursal de Nueva York, debe hacer un análisis para determinar si debe implementar un troncal SIP desde el sitio de Nueva York a un proveedor de servicio local.</span><span class="sxs-lookup"><span data-stu-id="87e60-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="87e60-110">Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifica qué números de llamada directa a la extensión (DID) usarán el tronco SIP y analiza la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425).</span><span class="sxs-lookup"><span data-stu-id="87e60-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="87e60-111">Puede tener terminación DID para el sitio de la sucursal en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="87e60-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="87e60-112">Por ejemplo, el sitio central de Redmond puede alojar números DID para el sitio de la sucursal de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="87e60-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="87e60-113">Si el costo de implementar un troncal SIP distribuido es menor que el costo de esas llamadas, considere la posibilidad de implementar un troncal SIP en el sitio de la sucursal de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="87e60-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="87e60-114">Otros requisitos de un tronco SIP de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="87e60-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="87e60-115">La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas de la red telefónica conmutada (RTC) de larga distancia de cada opción.</span><span class="sxs-lookup"><span data-stu-id="87e60-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="87e60-116">Si implementa un tronco SIP de sitio de sucursal, debe determinar los requisitos de ancho de banda y la resiliencia.</span><span class="sxs-lookup"><span data-stu-id="87e60-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="87e60-117">Si el vínculo entre su sitio de sucursal y el sitio central es resistente y tiene suficiente ancho de banda, puede desplegar un troncal SIP o puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="87e60-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="87e60-118">No es necesario implementar un dispositivo de sucursal que sobreviven en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="87e60-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="87e60-119">Si el vínculo entre el sitio de sucursal y central no es resistente, implementar un dispositivo de la rama que sobreviven o implementar un servidor de sucursal que sobreviven con una puerta de enlace o la troncal SIP en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="87e60-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

