---
title: 'Lync Server 2013: implementación de sitios de sucursal'
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
ms.openlocfilehash: c167dc4f81053d5b9dde547f2f1e6e3d9d1a0fe7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="56b96-102">Implementación de sitios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56b96-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56b96-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="56b96-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="56b96-104">Los usuarios de sitios de sucursal obtienen la mayor parte de su funcionalidad de 2013 de Lync Server del servidor en el sitio central al que está asociado el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="56b96-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="56b96-105">Todas y cada una de las sucursales están asociadas a exactamente un sitio central.</span><span class="sxs-lookup"><span data-stu-id="56b96-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="56b96-106">Para poder realizar llamadas a y desde la red telefónica conmutada pública (RTC), una sucursal puede contener cualquiera de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="56b96-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="56b96-107">Una puerta de enlace RTC y, probablemente, un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="56b96-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="56b96-108">Un tronco SIP</span><span class="sxs-lookup"><span data-stu-id="56b96-108">A SIP trunk</span></span>

  - <span data-ttu-id="56b96-109">Una infraestructura de voz existente con una central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="56b96-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="56b96-110">Una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="56b96-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="56b96-111">Un servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="56b96-111">A Survivable Branch Server</span></span>

<span data-ttu-id="56b96-112">Los sitios de sucursal con una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia son más resistentes en las horas de la red de área extensa o errores de sitio central que los sitios de sucursal sin una de estas soluciones.</span><span class="sxs-lookup"><span data-stu-id="56b96-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="56b96-113">Por ejemplo, en un sitio con una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia implementado, los usuarios aún pueden realizar y recibir llamadas RTC si la red que conecta el sitio de sucursal al sitio central no está disponible.</span><span class="sxs-lookup"><span data-stu-id="56b96-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="56b96-114">Otra forma de lograr la resistencia del sitio de sucursal es usar una puerta de enlace RTC o un tronco SIP con una implementación de Lync Server a gran escala en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="56b96-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="56b96-115">Para obtener información detallada sobre qué implementación de sitios de sucursal es la adecuada para su organización, incluidos los requisitos previos y otras consideraciones de planeación, consulte [Planning for RTC Connectivity in Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) y [Planning for Branch-site Voice Resiliency en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="56b96-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="56b96-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="56b96-116">In This Section</span></span>

  - [<span data-ttu-id="56b96-117">Suministro de conectividad RTC en un sitio de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56b96-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="56b96-118">Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56b96-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

