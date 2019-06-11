---
title: Grupo de director escalado - Equilibrio de carga DNS y equilibradores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cd92304ca3a1147737958ad9d9fc94a49b2e5e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="2dd6a-102">Grupo de director escalado - Equilibrio de carga DNS y equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dd6a-102">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2dd6a-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2dd6a-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2dd6a-104">Un grupo de directores con escala, en el que hay más de un director implementado para manejar capacidad adicional y proporcionar una alta disponibilidad, requiere el equilibrio de carga para distribuir la comunicación entre el cliente y el servidor a todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="2dd6a-104">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="2dd6a-105">Un director hospeda servicios web muy parecidos a un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2dd6a-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="2dd6a-106">Para proporcionar el equilibrio de carga, puede usar el equilibrio de carga de hardware o el equilibrio de carga del sistema de nombres de dominio (DNS) y el equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="2dd6a-106">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="2dd6a-107">El equilibrio de carga de hardware se requiere para los servicios web y el equilibrio de carga de DNS solo no proporciona las capacidades necesarias para los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="2dd6a-107">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="2dd6a-108">En los siguientes temas se describen las consideraciones de planeación para implementar un grupo de directores mediante el equilibrio de carga de DNS junto con el equilibrio de carga del hardware.</span><span class="sxs-lookup"><span data-stu-id="2dd6a-108">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="2dd6a-109">Si tiene previsto usar el equilibrio de carga de hardware, pero no el equilibrio de carga de DNS para el grupo de directores, consulte el tema [grupo de directores escalados-equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) que describe los requisitos de planeación de esa topología.</span><span class="sxs-lookup"><span data-stu-id="2dd6a-109">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="2dd6a-110">![Grupo de directores a escala] (images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Grupo de directores a escala")</span><span class="sxs-lookup"><span data-stu-id="2dd6a-110">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2dd6a-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2dd6a-111">In This Section</span></span>

  - [<span data-ttu-id="2dd6a-112">Resumen de certificado - Carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dd6a-112">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="2dd6a-113">Resumen de puerto - Carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dd6a-113">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="2dd6a-114">Resumen de DNS - Carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dd6a-114">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

