---
title: 'Lync Server 2013: enrutamiento entre enlaces'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37a9feb818f48317f9a3dddd78a70700e3f6ccfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="3f6ea-102">Enrutamiento entre troncales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f6ea-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f6ea-103">_**Última modificación del tema:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="3f6ea-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="3f6ea-104">Lync Server 2013 proporciona administración de sesiones básica mediante la compatibilidad de enrutamiento de intertroncalización.</span><span class="sxs-lookup"><span data-stu-id="3f6ea-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="3f6ea-105">Esta nueva capacidad permite que Lync Server ofrezca funcionalidades de control de llamadas para los sistemas de telefonía indirectos.</span><span class="sxs-lookup"><span data-stu-id="3f6ea-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="3f6ea-106">El enrutamiento entre troncos puede interconectar una IP-PBX con una puerta de enlace de la red telefónica conmutada (RTC) para que las llamadas realizadas desde un teléfono de una central de conmutación (PBX) se puedan redirigir a la RTC y las llamadas RTC entrantes se puedan redirigir a un teléfono PBX.</span><span class="sxs-lookup"><span data-stu-id="3f6ea-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="3f6ea-107">De forma similar, Lync Server puede interconectar dos o más sistemas IP-PBX para que las llamadas se puedan realizar y recibir entre los teléfonos PBX de los diferentes sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="3f6ea-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="3f6ea-108">La siguiente ilustración muestra Lync Server 2013, que proporciona interconectividad entre una puerta de enlace PSTN y una IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="3f6ea-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="3f6ea-109">![Diagrama de conexión puerta de enlace RTC/IP-PBX en Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagrama de conexión puerta de enlace RTC/IP-PBX en Lync Server")</span><span class="sxs-lookup"><span data-stu-id="3f6ea-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="3f6ea-110">La figura siguiente muestra cómo Lync Server 2013 conecta dos sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="3f6ea-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="3f6ea-111">![Diagrama de interconexión de los sistemas IP-PAX en Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagrama de interconexión de los sistemas IP-PAX en Lync Server")</span><span class="sxs-lookup"><span data-stu-id="3f6ea-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

