---
title: 'Lync Server 2013: asociar subredes con sitios de red para el desvío de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74f007accc53158a1f541dbe4ac6aa821cd8be4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="06725-102">Asociar subredes con sitios de red para el desvío de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06725-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06725-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="06725-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06725-104">En este tema se da por supuesto que ha realizado la configuración global de desvío de medios, así como una región de red y los sitios de red para el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="06725-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="06725-p101">Todas las subredes de la red debe estar asociadas con un sitio de red específico. Por este motivo la información de las subredes se usa para determinar el sitio de red en el que se encuentra un extremo. Cuando se conocen las ubicaciones de ambas partes de una sesión, el desvío de medios puede determinar si envía medios para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="06725-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="06725-108">El desvío de medios no tiene requisitos especiales para asociar subredes con sitios de red.</span><span class="sxs-lookup"><span data-stu-id="06725-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="06725-109">Para crear una asociación entre las subredes y los sitios de red de la topología, siga los procedimientos que se indican en [asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="06725-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="06725-110">Pasos siguientes: Crear perfiles de directivas de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="06725-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="06725-p103">Una vez asociadas las subredes con sitios de red para el desvío de medios, deberá crear uno o varios perfiles de directiva de ancho de banda que particionen las subredes entre las que tienen buena conectividad y aquellas cuyo propósito no es el desvío de medios. Todas las subredes de una región de red que poseen sitios de red sin restricciones de ancho de banda tienen buena conectividad y, por lo tanto, pueden usar el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="06725-p103">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass. All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="06725-113">Para conocer los procedimientos para configurar los perfiles de directiva de ancho de banda, consulte [Create Bandwidth Policy Profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="06725-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

