---
title: 'Lync Server 2013: enlace troncal SIP de sitio de sucursal'
description: 'Lync Server 2013: enlace troncal SIP de sitio de sucursal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33e408a462c21ffa6df6e6a2aee50d7b87dca1f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569326"
---
# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="c3b48-103">Enlace troncal SIP de sitios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3b48-103">Branch site SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3b48-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c3b48-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c3b48-105">En algunos casos, es posible que necesite implementar un enlace troncal SIP distribuido en los sitios de sucursal seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c3b48-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="c3b48-106">Para determinar si se necesita un tronco SIP para un sitio de sucursal, revise la información de [cómo se implementa el enlace troncal SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="c3b48-106">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="c3b48-107">Para obtener más información sobre las opciones de topología compatibles para implementar troncos SIP en sitios de sucursal, consulte [soluciones de resistencia de sitios de sucursal en Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="c3b48-107">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="c3b48-108">Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="c3b48-108">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="c3b48-109">Cuando decida implementar un tronco SIP de sitio de sucursal, debe realizar un análisis de costos específicos del sitio.</span><span class="sxs-lookup"><span data-stu-id="c3b48-109">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="c3b48-110">Por ejemplo, una empresa que tenga un sitio central en Redmond, Washington y un sitio de sucursal en Nueva York debe realizar un análisis para determinar si debe implementar un tronco SIP desde el sitio de Nueva York a un proveedor de servicios local.</span><span class="sxs-lookup"><span data-stu-id="c3b48-110">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="c3b48-111">Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifique qué números DID usarán el tronco SIP y analice la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425).</span><span class="sxs-lookup"><span data-stu-id="c3b48-111">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="c3b48-112">Puede haber finalizado la terminación del sitio de sucursal en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="c3b48-112">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="c3b48-113">Por ejemplo, el sitio central de Redmond puede hospedar números DID para el sitio de sucursal de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="c3b48-113">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="c3b48-114">Si el costo de implementar un tronco SIP distribuido es menor que el costo de las llamadas, considere la posibilidad de implementar un tronco SIP en el sitio de sucursal de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="c3b48-114">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="c3b48-115">Otros requisitos de un tronco SIP de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="c3b48-115">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="c3b48-116">La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas RTC de larga distancia de cada opción.</span><span class="sxs-lookup"><span data-stu-id="c3b48-116">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="c3b48-117">Si implementa un tronco SIP de sitio de sucursal, también necesita determinar los requisitos de resistencia y ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="c3b48-117">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="c3b48-118">Si el vínculo entre el sitio de sucursal y el sitio central es resistente y tiene suficiente ancho de banda, puede implementar un tronco SIP o una puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="c3b48-118">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="c3b48-119">No es necesario implementar una aplicación de sucursal con funciones de supervivencia en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="c3b48-119">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="c3b48-120">Si el vínculo entre el sitio de sucursal y el sitio central no es resistente, implemente una aplicación de sucursal con funciones de supervivencia o implemente un servidor de sucursal con funciones de supervivencia con una puerta de enlace o un tronco SIP en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="c3b48-120">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

