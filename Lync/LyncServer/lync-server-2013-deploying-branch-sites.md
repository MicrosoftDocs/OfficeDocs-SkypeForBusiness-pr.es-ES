---
title: 'Lync Server 2013: Implementación de sitios de sucursales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: facfda5d1d7ce67ea08f71cbfb943792eeced7a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="4ec48-102">Implementación de sitios de sucursales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ec48-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ec48-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4ec48-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4ec48-104">Los usuarios de un sitio de sucursal obtienen la mayor parte de su funcionalidad de 2013 de Lync Server en el servidor del sitio central al que está asociado el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="4ec48-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="4ec48-105">Cada sitio de sucursal está asociado con un solo sitio central.</span><span class="sxs-lookup"><span data-stu-id="4ec48-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="4ec48-106">Para proporcionar llamadas a y desde la red de telefonía pública conmutada (RTC), un sitio de sucursal puede contener cualquiera de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="4ec48-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="4ec48-107">Una puerta de enlace RTC y posiblemente un servidor Meditation</span><span class="sxs-lookup"><span data-stu-id="4ec48-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="4ec48-108">Un tronco de SIP</span><span class="sxs-lookup"><span data-stu-id="4ec48-108">A SIP trunk</span></span>

  - <span data-ttu-id="4ec48-109">Una infraestructura de voz existente con una central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="4ec48-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="4ec48-110">Un equipo de sucursales con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="4ec48-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="4ec48-111">Un servidor de sucursal con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="4ec48-111">A Survivable Branch Server</span></span>

<span data-ttu-id="4ec48-112">Los sitios de sucursales con un equipo de sucursal o un servidor de sucursal con la supervivencia son más resistentes en las horas de la red de área amplia o errores de sitio central que las sucursales sin una de estas soluciones.</span><span class="sxs-lookup"><span data-stu-id="4ec48-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="4ec48-113">Por ejemplo, en un sitio con una sucursal o un servidor de sucursal superviviente implementado, los usuarios pueden seguir realizando y recibiendo llamadas RTC si la red que conecta el sitio de la sucursal con el sitio central está desactivada.</span><span class="sxs-lookup"><span data-stu-id="4ec48-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="4ec48-114">Otra forma de lograr la resistencia al sitio de la sucursal es usar una puerta de enlace PSTN o un tronco del SIP con una implementación de Lync Server de escala completa en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="4ec48-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="4ec48-115">Para obtener detalles sobre qué implementación de sitio de sucursal es adecuada para su organización, incluidos los requisitos previos y otras consideraciones de planeación, consulte [planificación de la conectividad RTC en Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) y [planeamiento de resistencia de voz de sitio de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="4ec48-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4ec48-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4ec48-116">In This Section</span></span>

  - [<span data-ttu-id="4ec48-117">Proporcionar conectividad RTC en un sitio de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ec48-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="4ec48-118">Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ec48-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

