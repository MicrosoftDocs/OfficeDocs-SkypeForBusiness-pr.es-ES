---
title: 'Lync Server 2013: asociar subredes con sitios de red para CAC'
description: 'Lync Server 2013: asocie subredes con sitios de red para CAC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d68607c1674bb964c27c8408583be7f5e092f4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560506"
---
# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="b9f80-103">Asociar subredes a sitios de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9f80-103">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9f80-104">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b9f80-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b9f80-p101">Todas las subredes de la red deben estar asociadas con un sitio de red específico. Por este motivo la información de las subredes se usa para determinar el sitio de red en el que se encuentra un extremo. Cuando se conoce la ubicación de ambas partes en una sesión, el control de admisión de llamadas puede determinar si hay suficiente ancho de banda para establecer una llamada.</span><span class="sxs-lookup"><span data-stu-id="b9f80-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="b9f80-108">El control de admisión de llamadas no tiene requisitos especiales para la asociación de subredes con sitios de red.</span><span class="sxs-lookup"><span data-stu-id="b9f80-108">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="b9f80-109">Para crear una asociación entre las subredes y los sitios de red de la topología, siga los procedimientos que se indican en [asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="b9f80-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="b9f80-110">Para ver los sitios de red (y sus subredes respectivas) en la topología de red de ejemplo para el control de admisión de llamadas, consulte [ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="b9f80-110">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

