---
title: Uso de Topology Builder para configurar la alta disponibilidad y la recuperación ante desastres
description: Usar el generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04764a58ac3ae1bbe0df97aadeabb03158ce8100
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547326"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="33a98-103">Usar el generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33a98-103">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33a98-104">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="33a98-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="33a98-105">Lleve a cabo los siguientes pasos en el generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="33a98-105">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="33a98-106">Agregue las bases de datos reflejadas y los almacenes de SQL Server de la base de datos secundaria de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="33a98-106">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="33a98-107">Edite las propiedades del servicio del servidor de chat persistente en:</span><span class="sxs-lookup"><span data-stu-id="33a98-107">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="33a98-108">Habilite el reflejo para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="33a98-108">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="33a98-109">Agregue el almacén de SQL Server de reflejo principal.</span><span class="sxs-lookup"><span data-stu-id="33a98-109">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="33a98-110">Habilite la base de datos de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33a98-110">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="33a98-111">Agregue el almacén de SQL Server secundario de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33a98-111">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="33a98-112">Agregue el reflejo del almacén de SQL Server para la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="33a98-112">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="33a98-113">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="33a98-113">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

