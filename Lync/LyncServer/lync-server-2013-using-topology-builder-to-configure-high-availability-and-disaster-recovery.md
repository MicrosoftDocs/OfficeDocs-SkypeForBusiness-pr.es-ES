---
title: Uso de Topology Builder para configurar la alta disponibilidad y la recuperación ante desastres
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
ms.openlocfilehash: 75117cd8a88b5ff5f333457033b5af49c5464f53
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="78cc6-102">Usar el generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78cc6-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78cc6-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="78cc6-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="78cc6-104">Lleve a cabo los siguientes pasos en el generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="78cc6-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="78cc6-105">Agregue las bases de datos reflejadas y los almacenes de SQL Server de la base de datos secundaria de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="78cc6-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="78cc6-106">Edite las propiedades del servicio del servidor de chat persistente en:</span><span class="sxs-lookup"><span data-stu-id="78cc6-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="78cc6-107">Habilite el reflejo para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="78cc6-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="78cc6-108">Agregue el almacén de SQL Server de reflejo principal.</span><span class="sxs-lookup"><span data-stu-id="78cc6-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="78cc6-109">Habilite la base de datos de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="78cc6-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="78cc6-110">Agregue el almacén de SQL Server secundario de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="78cc6-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="78cc6-111">Agregue el reflejo del almacén de SQL Server para la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="78cc6-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="78cc6-112">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="78cc6-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

