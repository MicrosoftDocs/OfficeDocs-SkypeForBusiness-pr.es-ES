---
title: 'Lync Server 2013: definición de los requisitos para la telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bd6b93941404f60fe8b7ff936dc9a982fe59220
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="eb179-102">Definición de los requisitos para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb179-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb179-103">_**Última modificación del tema:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="eb179-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="eb179-104">En este tema se proporciona una introducción a las consideraciones que se deben tener en cuenta sobre las regiones, los sitios y los vínculos entre los sitios de la topología y cómo son importantes cuando se implementa la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="eb179-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="eb179-105">Para obtener detalles que le ayuden a tomar estas decisiones, consulte [configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="eb179-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="eb179-106">Sitios y regiones</span><span class="sxs-lookup"><span data-stu-id="eb179-106">Sites and Regions</span></span>

<span data-ttu-id="eb179-107">En primer lugar, identifique los sitios de la topología en los que va a implementar la telefonía IP empresarial y las regiones de red a las que pertenecen dichos sitios.</span><span class="sxs-lookup"><span data-stu-id="eb179-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="eb179-108">En concreto, tenga en cuenta la forma en que proporcionará conectividad de red telefónica conmutada (RTC) a cada sitio.</span><span class="sxs-lookup"><span data-stu-id="eb179-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="eb179-109">Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo.</span><span class="sxs-lookup"><span data-stu-id="eb179-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="eb179-110">Decida dónde se implementarán las puertas de enlace localmente, donde se implementarán las aplicaciones de sucursal con funciones de supervivencia (las) y dónde puede configurar los troncos SIP (ya sea localmente o en el sitio central) a un proveedor de servicios de telefonía por Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="eb179-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="eb179-111">Vínculos de red entre sitios</span><span class="sxs-lookup"><span data-stu-id="eb179-111">Network Links Between Sites</span></span>

<span data-ttu-id="eb179-112">También debe tener en cuenta el uso de ancho de banda que espera en los vínculos de red entre el sitio central y sus sitios de sucursal.</span><span class="sxs-lookup"><span data-stu-id="eb179-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="eb179-113">Si tiene, o planea implementar, vínculos WAN resistentes entre sitios, le recomendamos que implemente una puerta de enlace en cada sitio de sucursal para proporcionar una terminación de marcado entrante directo local (DID) para los usuarios de dichos sitios.</span><span class="sxs-lookup"><span data-stu-id="eb179-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="eb179-114">Si tiene vínculos WAN resistentes, pero es probable que el ancho de banda de un vínculo WAN esté restringido, configure el control de admisión de llamadas para ese vínculo.</span><span class="sxs-lookup"><span data-stu-id="eb179-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="eb179-115">Si no tiene vínculos WAN resistentes, aloje menos de 1000 usuarios en el sitio de sucursal y no tiene administradores de Lync Server entrenados locales, le recomendamos que implemente una aplicación de sucursal con funciones de supervivencia en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="eb179-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="eb179-116">Si hospeda entre 1000 y 5000 usuarios en el sitio de sucursal, carecen de una conexión WAN resistente y tienen disponibles administradores de Lync Server entrenados, le recomendamos que implemente un servidor de sucursal con funciones de supervivencia con una puerta de enlace pequeña en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="eb179-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="eb179-117">También debe considerar la posibilidad de habilitar la omisión de medios en vínculos restringidos si tiene una puerta de enlace del mismo nivel que admite la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="eb179-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb179-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="eb179-118">See Also</span></span>


[<span data-ttu-id="eb179-119">Configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb179-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

