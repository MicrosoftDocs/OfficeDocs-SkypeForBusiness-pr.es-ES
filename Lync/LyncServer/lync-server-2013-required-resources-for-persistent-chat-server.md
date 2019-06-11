---
title: 'Lync Server 2013: Recursos requeridos para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac51432de0a6ca261e42f77d64ef1aa1a615cb6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ffda9-102">Recursos requeridos para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffda9-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffda9-103">_**Última modificación del tema:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="ffda9-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="ffda9-104">La alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente requieren recursos adicionales más allá de lo que normalmente se necesita para una completa operación.</span><span class="sxs-lookup"><span data-stu-id="ffda9-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="ffda9-105">Antes de configurar el servidor de chat persistente para una alta disponibilidad y recuperación ante desastres, asegúrese de disponer de los recursos siguientes, además de lo que se requiere para el funcionamiento del servidor de chat persistente estándar.</span><span class="sxs-lookup"><span data-stu-id="ffda9-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="ffda9-106">Para obtener información de configuración adicional, consulte [configuración de un servidor de chat persistente en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="ffda9-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="ffda9-107">Una instancia de base de datos dedicada ubicada en el mismo centro de datos físico en el que se encuentra el front-end del servicio del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ffda9-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="ffda9-108">Esta base de datos servirá de SQL Server Mirror para la base de datos de chat persistente principal.</span><span class="sxs-lookup"><span data-stu-id="ffda9-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="ffda9-109">De manera opcional, designe un servidor SQL Server adicional para que sirva como testigo de creación de reflejos si desea una conmutación automática para la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="ffda9-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="ffda9-110">Una instancia de base de datos dedicada ubicada en el otro centro de datos físico.</span><span class="sxs-lookup"><span data-stu-id="ffda9-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="ffda9-111">Esta base de datos servirá como la base de datos secundaria de trasvase de registros de SQL Server para la base de datos en el centro de datos principal.</span><span class="sxs-lookup"><span data-stu-id="ffda9-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="ffda9-112">Una instancia de base de datos dedicada que servirá como reflejo de SQL Server para la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="ffda9-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="ffda9-113">De manera opcional, designe un servidor SQL Server adicional como testigo de creación de reflejos.</span><span class="sxs-lookup"><span data-stu-id="ffda9-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="ffda9-114">Es preciso que ambos estén ubicados en el mismo centro de datos físico que la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="ffda9-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="ffda9-115">Si el cumplimiento del servidor de chat persistente está habilitado, se necesitan tres instancias de base de datos dedicadas adicionales.</span><span class="sxs-lookup"><span data-stu-id="ffda9-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="ffda9-116">Su distribución es la misma que la de la base de datos de chat persistente anterior.</span><span class="sxs-lookup"><span data-stu-id="ffda9-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="ffda9-117">Aunque es posible que la base de datos de cumplimiento comparta la misma instancia de SQL Server que la base de datos de chat persistente, recomendamos instancias independientes para la alta disponibilidad y la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="ffda9-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="ffda9-118">Es necesario crear y designar un recurso compartido de archivos para los registros de transacciones de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ffda9-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="ffda9-119">Todos los servidores SQL de ambos centros de datos que ejecutan bases de datos de chat persistentes deben tener acceso de lectura y escritura a este recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="ffda9-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="ffda9-120">Este recurso compartido no está designado como parte del rol FileStore.</span><span class="sxs-lookup"><span data-stu-id="ffda9-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="ffda9-121">Un recurso compartido de archivos en el servidor de la base de datos secundaria para que sirva como carpeta de destino para los registros de transacciones de SQL Server que se copian desde el recurso compartido de archivos del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="ffda9-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ffda9-122">Los servidores de chat persistente activos en un grupo de servidores de chat persistente deben residir en la misma zona horaria que el grupo de Lync del próximo salto definido en la topología.</span><span class="sxs-lookup"><span data-stu-id="ffda9-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="ffda9-123">Las figuras siguientes proporcionan ejemplos acerca de cómo se puede configurar todo el grupo de servidores de chat persistente en las dos topologías de grupo extendidas diferentes:</span><span class="sxs-lookup"><span data-stu-id="ffda9-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="ffda9-124">Grupo de servidores de chat persistente estirado cuando los centros de datos se encuentran en un gran ancho de banda y baja latencia.</span><span class="sxs-lookup"><span data-stu-id="ffda9-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="ffda9-125">Grupo de servidores de chat persistente estirado cuando los centros de datos se encuentran en una ubicación geográfica con un ancho de banda bajo y una latencia alta.</span><span class="sxs-lookup"><span data-stu-id="ffda9-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="ffda9-126">La siguiente ilustración muestra una topología de grupo de servidores de chat persistente superpuesto en la que los centros de datos se encuentran en una ubicación geográfica con un alto ancho de banda y baja latencia.</span><span class="sxs-lookup"><span data-stu-id="ffda9-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="ffda9-127">**Grupo de servidores de chat persistente estirado cuando los centros de datos se encuentran en un gran ancho de banda y baja latencia.**</span><span class="sxs-lookup"><span data-stu-id="ffda9-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="ffda9-128">![Examen de configuración HBW del grupo de servidores de chat persistente] (images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Examen de configuración HBW del grupo de servidores de chat persistente")</span><span class="sxs-lookup"><span data-stu-id="ffda9-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="ffda9-129">La siguiente ilustración muestra una topología de grupo de servidores de chat persistente superpuesto en la que los centros de datos se encuentran en una ubicación geográfica con un ancho de banda bajo y una latencia elevada.</span><span class="sxs-lookup"><span data-stu-id="ffda9-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="ffda9-130">**Grupo de servidores de chat persistente estirado cuando los centros de datos se encuentran en una ubicación geográfica con un ancho de banda bajo y una latencia alta.**</span><span class="sxs-lookup"><span data-stu-id="ffda9-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="ffda9-131">![Examen de configuración LBW del grupo de servidores de chat persistente] (images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Examen de configuración LBW del grupo de servidores de chat persistente")</span><span class="sxs-lookup"><span data-stu-id="ffda9-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

