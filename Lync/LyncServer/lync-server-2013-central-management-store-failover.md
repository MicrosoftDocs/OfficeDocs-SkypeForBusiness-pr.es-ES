---
title: 'Lync Server 2013: Conmutación por error del almacén de administración central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b320b3313f37a1912b909d018bbe37de5a997be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="f146f-102">Conmutación por error del almacén de administración central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f146f-102">Central Management store failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f146f-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f146f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f146f-104">El almacén central de administración contiene datos de configuración sobre servidores y servicios de la implementación de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f146f-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="f146f-105">Proporciona un almacenamiento schematized sólido de los datos necesarios para definir, configurar, mantener, administrar, describir y usar una implementación de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f146f-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="f146f-106">También comprueba los datos para asegurarse de que la configuración es coherente.</span><span class="sxs-lookup"><span data-stu-id="f146f-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="f146f-107">Cada implementación de Lync incluye un almacén de administración central, que se hospeda en el servidor back-end de un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f146f-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="f146f-108">Al establecer un emparejamiento de grupo que incluye el grupo que hospeda el almacén central de administración, se configura una base de datos de almacenamiento central de administración de copia de seguridad en el grupo de copias de seguridad y los servicios del almacén central de administración se instalan en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="f146f-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="f146f-109">En cualquier momento, una de las dos bases de datos del almacén de administración central es la principal activa y la otra es una en espera.</span><span class="sxs-lookup"><span data-stu-id="f146f-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="f146f-110">El servicio de copia de seguridad Replica el contenido desde el maestro activo al modo de espera.</span><span class="sxs-lookup"><span data-stu-id="f146f-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="f146f-111">Durante la conmutación por error de un grupo de servidores que implica a los grupos que hospedan el almacén de administración central, el administrador debe realizar la conmutación por error del almacén central de administración antes de realizar la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="f146f-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="f146f-112">Después de que se repara el desastre, no es necesario llevar a cabo la conmutación por recuperación del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="f146f-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="f146f-113">Después de la reparación, el almacén de administración central del grupo de copia de seguridad original puede permanecer como maestro activo.</span><span class="sxs-lookup"><span data-stu-id="f146f-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="f146f-114">Los objetivos de ingeniería para la conmutación por error del almacén de administración central son 5 minutos para el de tiempo de recuperación (RTO) y 5 minutos para el de punto de recuperación (RPO).</span><span class="sxs-lookup"><span data-stu-id="f146f-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

