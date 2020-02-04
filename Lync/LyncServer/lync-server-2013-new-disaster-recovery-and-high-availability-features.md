---
title: 'Lync Server 2013: Nuevas funciones de alta disponibilidad y recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aabac29c5e866c4bfeff8ad79d392578d52ba650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="8e2d0-102">Nuevas funciones de alta disponibilidad y recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e2d0-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e2d0-103">_**Última modificación del tema:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="8e2d0-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="8e2d0-104">Como en Lync Server 2010, el esquema de alta disponibilidad (HA) principal para Lync Server 2013 se basa en la redundancia del servidor a través de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="8e2d0-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="8e2d0-105">Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor.</span><span class="sxs-lookup"><span data-stu-id="8e2d0-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="8e2d0-106">Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.</span><span class="sxs-lookup"><span data-stu-id="8e2d0-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="8e2d0-107">Lync Server 2013 agrega nuevas medidas de recuperación ante desastres permitiéndole emparejar grupos de servidores front-end ubicados en dos centros de recursos.</span><span class="sxs-lookup"><span data-stu-id="8e2d0-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="8e2d0-108">Si una de las agrupaciones emparejadas deja de funcionar, un administrador puede migrar por error los usuarios de ese grupo al otro grupo en el par, para proporcionar la continuación del servicio.</span><span class="sxs-lookup"><span data-stu-id="8e2d0-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="8e2d0-109">Esta funcionalidad no requiere soluciones costosas de red o de hardware, como redes de almacenamiento o discos compartidos.</span><span class="sxs-lookup"><span data-stu-id="8e2d0-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="8e2d0-110">Lync Server 2013 también agrega la alta disponibilidad del servidor back end.</span><span class="sxs-lookup"><span data-stu-id="8e2d0-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="8e2d0-111">Esta es una topología opcional en la que se implementan dos servidores de servicios de fondo para un grupo de servidores front-end y se configuran los reflejos de SQL sincrónico para todas las bases de datos de Lync que se ejecutan en los servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="8e2d0-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="8e2d0-112">Puede elegir si desea implementar un testigo para el reflejo.</span><span class="sxs-lookup"><span data-stu-id="8e2d0-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8e2d0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e2d0-113">See Also</span></span>


[<span data-ttu-id="8e2d0-114">Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e2d0-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

