---
title: 'Lync Server 2013: asociar subredes con sitios de red para CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c00205e8aa070eacb7b5d99ec724ad8b67fa2ae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="6125b-102">Asociar subredes con sitios de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6125b-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6125b-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6125b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6125b-104">Cada subred de su red debe estar asociada a un sitio de red específico.</span><span class="sxs-lookup"><span data-stu-id="6125b-104">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="6125b-105">Esto se debe a que la información de subred se usa para determinar el sitio de red en el que se encuentra un extremo.</span><span class="sxs-lookup"><span data-stu-id="6125b-105">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="6125b-106">Cuando se conocen las ubicaciones de ambas partes en una sesión, control de admisión de llamadas (CAC) puede determinar si hay suficiente ancho de banda para establecer una llamada.</span><span class="sxs-lookup"><span data-stu-id="6125b-106">When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="6125b-107">El control de admisión de llamadas no tiene ningún requisito especial para la Asociación de subredes con sitios de red.</span><span class="sxs-lookup"><span data-stu-id="6125b-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="6125b-108">Para crear una asociación entre las subredes y los sitios de red de su topología, siga los procedimientos que se describen en [asociar una subred con un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="6125b-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="6125b-109">Para ver los sitios de red (y sus respectivas subredes) en la topología de red de ejemplo para el control de admisión de llamadas, vea [ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="6125b-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

