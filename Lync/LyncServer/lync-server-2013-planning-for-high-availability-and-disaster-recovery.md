---
title: 'Lync Server 2013: Planeación de alta disponibilidad y recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092e59813f76690233a950cd8ce914df47146d37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="0a7c5-102">Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a7c5-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a7c5-103">_**Última modificación del tema:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="0a7c5-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="0a7c5-104">Al igual que en Lync Server 2010, el esquema de alta disponibilidad principal para la mayoría de los roles de servidor de Lync Server 2013 se basa en la redundancia de los servidores a través de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="0a7c5-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="0a7c5-105">Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor.</span><span class="sxs-lookup"><span data-stu-id="0a7c5-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="0a7c5-106">Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.</span><span class="sxs-lookup"><span data-stu-id="0a7c5-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="0a7c5-107">Lync Server 2013 agrega nuevas medidas de recuperación ante desastres para grupos de servidores front-end mediante la introducción de dispersement geográficas de los servidores en dos centros de datos para ofrecer la continuación del servicio en caso de que se desconecte todo un grupo o sitio.</span><span class="sxs-lookup"><span data-stu-id="0a7c5-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="0a7c5-108">Lync Server 2013 también mejora la alta disponibilidad del servidor back-end, pues admite el reflejo de SQL sincrónico para las bases de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="0a7c5-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="0a7c5-109">En esta sección se explican estas características principales de alta disponibilidad y recuperación ante desastres, y también se describen los pasos que puede realizar para la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="0a7c5-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0a7c5-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0a7c5-110">In This Section</span></span>

  - [<span data-ttu-id="0a7c5-111">Grupo front-end para la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a7c5-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="0a7c5-112">Recuperación ante desastres del servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a7c5-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="0a7c5-113">Planear la resistencia de la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a7c5-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="0a7c5-114">Características de la administración de llamadas para la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a7c5-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="0a7c5-115">Configurar servidores de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a7c5-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="0a7c5-116">Resistencia de sitios de metropolitana de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0a7c5-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

