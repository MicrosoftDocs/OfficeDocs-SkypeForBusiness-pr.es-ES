---
title: 'Lync Server 2013: copia de seguridad y restauración de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d65d06ac9c72e776eee51b9b3dff6c6db3a59031
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="31e00-102">Copia de seguridad y restauración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31e00-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31e00-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="31e00-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="31e00-104">En esta sección, encontrará los procedimientos recomendados para realizar copias de seguridad de los datos de Lync Server 2013 y para restaurarlos si tiene un error.</span><span class="sxs-lookup"><span data-stu-id="31e00-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="31e00-105">Estos procedimientos recomendados se aplican a las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="31e00-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="31e00-106">Un grupo de servidores de Lync completo de cualquier tipo (servidor front-end, servidor perimetral, servidor de mediación, servidor de chat persistente o director) o un servidor individual de uno de estos grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="31e00-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="31e00-107">El servidor de administración central</span><span class="sxs-lookup"><span data-stu-id="31e00-107">The Central Management Server</span></span>

  - <span data-ttu-id="31e00-108">Un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="31e00-108">A Standard Edition server</span></span>

  - <span data-ttu-id="31e00-109">Un servidor back-end de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="31e00-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="31e00-110">Un almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="31e00-110">A File Store</span></span>

  - <span data-ttu-id="31e00-111">Una base de datos de archivado, una base de datos de supervisión o una base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="31e00-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="31e00-112">En esta sección no se incluye información sobre cómo restaurar un sitio completo o desarrollar un sitio en espera.</span><span class="sxs-lookup"><span data-stu-id="31e00-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="31e00-113">Para obtener más información sobre cómo desarrollar una solución de recuperación ante desastres con grupos de servidores front-end emparejados, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="31e00-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="31e00-114">Este es el método recomendado para la planeación de la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="31e00-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="31e00-115">Si ha implementado grupos de servidores front-end emparejados, si uno de estos grupos da error y se convierte en irrecuperable, puede restaurar este grupo con un nuevo nombre de dominio completo (FQDN) de su grupo emparejado.</span><span class="sxs-lookup"><span data-stu-id="31e00-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="31e00-116">Para obtener más información sobre los pasos para realizar esta recuperación, consulte [conmutación por error de un grupo de servidores en Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="31e00-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="31e00-117">Además, si más adelante desea volver a crear un grupo de servidores con errores e irrecuperables que formaba parte de un par de servidores front-end, puede seguir los pasos que se indican en [realizar una conmutación por error de grupo de servidores front-end ABC en Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span><span class="sxs-lookup"><span data-stu-id="31e00-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="31e00-118">La metodología descrita en este documento incluye consideraciones especiales durante la fase de planeación.</span><span class="sxs-lookup"><span data-stu-id="31e00-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="31e00-119">Para obtener más información, consulte [establecer un plan de copia de seguridad y restauración para Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="31e00-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="31e00-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="31e00-120">In This Section</span></span>

  - [<span data-ttu-id="31e00-121">Preparación para la copia de seguridad y restauración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31e00-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="31e00-122">Copia de seguridad de datos y configuración en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31e00-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="31e00-123">Restauración de datos y configuración en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31e00-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="31e00-124">Hojas de cálculo de copia de seguridad y restauración para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31e00-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

