---
title: 'Lync Server 2013: Definición de los requisitos para la telefonía IP empresarial'
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
ms.openlocfilehash: 8987905d2b117eb889486882b7d74ce4e52659a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="50a72-102">Definición de los requisitos para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50a72-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50a72-103">_**Última modificación del tema:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="50a72-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="50a72-104">En este tema se proporciona una descripción general de las consideraciones que debe tener en las regiones, los sitios y los vínculos entre los sitios de su topología y cómo son importantes cuando implementa la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="50a72-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="50a72-105">Para obtener detalles que le ayuden a tomar estas decisiones, consulte [configuración de red para las características de telefonía avanzada empresarial de Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="50a72-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="50a72-106">Sitios y regiones</span><span class="sxs-lookup"><span data-stu-id="50a72-106">Sites and Regions</span></span>

<span data-ttu-id="50a72-107">En primer lugar, identifique los sitios de su topología en los que va a implementar Enterprise Voice y las regiones de red a las que pertenecen dichos sitios.</span><span class="sxs-lookup"><span data-stu-id="50a72-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="50a72-108">En concreto, tenga en cuenta la forma en que se va a proporcionar conectividad de red telefónica conmutada (RTC) a cada sitio.</span><span class="sxs-lookup"><span data-stu-id="50a72-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="50a72-109">Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo.</span><span class="sxs-lookup"><span data-stu-id="50a72-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="50a72-110">Decidir dónde se implementarán las puertas de enlace de forma local, donde se implementarán los dispositivos de sucursal (SBAs) supervivientes, y donde puede configurar los troncos SIP (ya sea de forma local o en el sitio central) a un proveedor de servicios de telefonía por Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="50a72-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="50a72-111">Vínculos de red entre sitios</span><span class="sxs-lookup"><span data-stu-id="50a72-111">Network Links Between Sites</span></span>

<span data-ttu-id="50a72-112">También debe considerar el uso de ancho de banda que espera en los vínculos de red entre su sitio central y sus sitios de sucursales.</span><span class="sxs-lookup"><span data-stu-id="50a72-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="50a72-113">Si tiene, o planea implementar, vínculos WAN resistentes entre sitios, le recomendamos que implemente una puerta de enlace en cada sitio de sucursal para proporcionar una terminación de marcado directo local (sí) para los usuarios de esos sitios.</span><span class="sxs-lookup"><span data-stu-id="50a72-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="50a72-114">Si tiene vínculos WAN resistentes, pero es probable que el ancho de banda de un vínculo WAN esté restringido, configure el control de admisión de llamadas para ese vínculo.</span><span class="sxs-lookup"><span data-stu-id="50a72-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="50a72-115">Si no tiene vínculos WAN resistentes, aloje menos de 1000 usuarios en el sitio de la sucursal y no dispone de administradores de Lync Server capacitados locales, le recomendamos que implemente una aplicación de mayor supervivencia en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="50a72-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="50a72-116">Si se aloja entre usuarios de 1000 y 5000 en su sitio de sucursal, carece de una conexión WAN resistente y tiene disponibles administradores de Lync Server capacitados, le recomendamos que implemente un servidor de sucursal con una pequeña puerta de enlace en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="50a72-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="50a72-117">También debe considerar habilitar la omisión de medios en vínculos restringidos si tiene una puerta de enlace del mismo nivel que admite la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="50a72-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50a72-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="50a72-118">See Also</span></span>


[<span data-ttu-id="50a72-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50a72-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

