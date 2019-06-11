---
title: 'Lync Server 2013: asociar subredes con sitios de red para omitir elementos multimedia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c0f2d6461264ff8b54609e280c59986e1a923c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="663fa-102">Asociar subredes con sitios de red para evitar contenido multimedia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="663fa-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="663fa-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="663fa-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="663fa-104">En este tema se supone que ha configurado la configuración global de omisión de medios y que ha configurado la región de red y los sitios de red para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="663fa-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="663fa-105">Cada subred de su red debe estar asociada a un sitio de red específico.</span><span class="sxs-lookup"><span data-stu-id="663fa-105">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="663fa-106">Esto se debe a que la información de subred se usa para determinar el sitio de red en el que se encuentra un extremo.</span><span class="sxs-lookup"><span data-stu-id="663fa-106">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="663fa-107">Cuando se conocen las ubicaciones de ambas partes en una sesión, la omisión de medios puede determinar dónde enviar los medios para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="663fa-107">When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="663fa-108">La omisión de elementos multimedia no tiene ningún requisito especial para asociar subredes a sitios de red.</span><span class="sxs-lookup"><span data-stu-id="663fa-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="663fa-109">Para crear una asociación entre las subredes y los sitios de red de su topología, siga los procedimientos que se describen en [asociar una subred con un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="663fa-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="663fa-110">Pasos siguientes: crear perfiles de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="663fa-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="663fa-111">Después de asociar subredes a sitios de red para omitir elementos multimedia, debe crear uno o varios perfiles de directiva de ancho de banda que crearán particiones de subredes para los usuarios con una buena conectividad y aquellos sin, a fin de omitir los medios.</span><span class="sxs-lookup"><span data-stu-id="663fa-111">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass.</span></span> <span data-ttu-id="663fa-112">Todas las subredes de una región de red con sitios de red que no tienen restricciones de ancho de banda tienen una buena conectividad y, por lo tanto, estas subredes pueden usar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="663fa-112">All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="663fa-113">Para obtener información sobre los procedimientos para configurar perfiles de directiva de ancho de banda, consulte [crear perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="663fa-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

