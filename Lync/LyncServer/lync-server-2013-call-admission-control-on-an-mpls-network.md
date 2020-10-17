---
title: 'Lync Server 2013: control de admisión de llamadas en una red MPLS'
description: 'Lync Server 2013: control de admisión de llamadas en una red MPLS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e26ba95a9191b567520978ee9512cbbc12e934ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572376"
---
# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a><span data-ttu-id="41e0a-103">Control de admisión de llamadas en una red MPLS con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41e0a-103">Call admission control on an MPLS network with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41e0a-104">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="41e0a-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="41e0a-p101">En una red de conmutación de etiquetas multiprotocolo (MPLS), todos los sitios se conectan mediante una malla completa. Es decir, todos los sitios se conectan directamente a la red troncal del proveedor del servicio de internet MPLS, y se proporciona ancho de banda a todos los sitios para que lo usen a través de un vínculo WAN a la nube MPLS. No existe ningún concentrador de red ni ningún sitio central que controle el enrutamiento IP. En la siguiente figura se muestra una red sencilla basada en la tecnología MPLS.</span><span class="sxs-lookup"><span data-stu-id="41e0a-p101">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="41e0a-109">**Red MPLS de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="41e0a-109">**Example MPLS network**</span></span>

<span data-ttu-id="41e0a-110">![CAC con MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC con MPLS")</span><span class="sxs-lookup"><span data-stu-id="41e0a-110">![CAC with MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC with MPLS")</span></span>

<span data-ttu-id="41e0a-p102">Para implementar el control admisión de llamadas (CAC) en una red MPLS, debe crear una región de red que represente la nube MPLS y un sitio de red que represente cada uno de los sitios satélite MPLS. En la siguiente figura se muestra cómo deberán configurarse la región de red y los sitios de red para representar la red MPLS de ejemplo de la figura anterior. Los límites de ancho de banda generales y los límites de sesión de ancho de banda se basan en la capacidad del vínculo WAN desde el sitio de red hasta la región de red que representa la nube MPLS.</span><span class="sxs-lookup"><span data-stu-id="41e0a-p102">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="41e0a-114">**Región de red y sitios de red para una red MPLS**</span><span class="sxs-lookup"><span data-stu-id="41e0a-114">**Network region and network sites for an MPLS network**</span></span>

<span data-ttu-id="41e0a-115">![Diagrama de control de admisión de llamadas (CAC) con MPLS](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Diagrama de control de admisión de llamadas (CAC) con MPLS")</span><span class="sxs-lookup"><span data-stu-id="41e0a-115">![Call Admission Control (CAC) with MPLS diagram](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Call Admission Control (CAC) with MPLS diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

