---
title: Troncalización SIP de sitio de sucursal en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Obtenga más información sobre la Troncalización SIP en sucursales en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 158c1cff28ba0c21f5c995a1fe5b7dfdf2f9f150
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803260"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="49323-103">Troncalización SIP de sitio de sucursal en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="49323-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="49323-104">Obtenga más información sobre la Troncalización SIP en sucursales en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="49323-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="49323-105">En algunos casos, es posible que necesites implementar el troncal de SIP distribuido en los sitios de sucursales seleccionados.</span><span class="sxs-lookup"><span data-stu-id="49323-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="49323-106">Para determinar si es necesario un tronco de SIP para un sitio de sucursal y para obtener información sobre las opciones de topología admitidas para la implementación de los troncos SIP en sitios de sucursales, consulte el [enlace troncal de SIP en Skype empresarial Server](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="49323-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="49323-107">Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="49323-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="49323-108">Si decide implementar un tronco SIP de sitio de sucursal, debe realizar un análisis de costos específico del sitio.</span><span class="sxs-lookup"><span data-stu-id="49323-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="49323-109">Por ejemplo, una empresa que tiene un sitio central en Redmond, Washington y un sitio de sucursal en Nueva York debe realizar un análisis para determinar si implementar un tronco SIP desde el sitio de Nueva York a un proveedor de servicios locales.</span><span class="sxs-lookup"><span data-stu-id="49323-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="49323-110">Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifica qué números de llamada directa a la extensión (DID) usarán el tronco SIP y analiza la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425).</span><span class="sxs-lookup"><span data-stu-id="49323-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="49323-111">Puede haber finalizado el sitio de la sucursal en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="49323-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="49323-112">Por ejemplo, el sitio central de Redmond puede hospedar números para el sitio de sucursal de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="49323-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="49323-113">Si el precio de la implementación de un tronco de SIP distribuido es menor que el precio de esas llamadas, considere la posibilidad de implementar un tronco del SIP en el sitio de la sucursal de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="49323-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="49323-114">Otros requisitos de un tronco SIP de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="49323-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="49323-115">La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas de la red telefónica conmutada (RTC) de larga distancia de cada opción.</span><span class="sxs-lookup"><span data-stu-id="49323-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="49323-116">Si implementa un tronco SIP de sitio de sucursal, también necesita determinar los requisitos de resistencia y ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="49323-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="49323-117">Si el vínculo entre el sitio de la sucursal y el sitio central es resistente y tiene suficiente ancho de banda, puede implementar un tronco SIP o una puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="49323-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="49323-118">No es necesario implementar una aplicación de rama que sea superviviente en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="49323-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="49323-119">Si el vínculo entre el sitio de la sucursal y el sitio central no es resistente, implemente un dispositivo de sucursal con la supervivencia o implemente un servidor de sucursal que sea reviviente con una puerta de enlace o un tronco SIP en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="49323-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

