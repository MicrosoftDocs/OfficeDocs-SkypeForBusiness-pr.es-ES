---
title: 'Lync Server 2013: recursos necesarios para el servidor de chat persistente'
description: 'Lync Server 2013: recursos necesarios para el servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c81f0017428e4305e46fbcf5580a83af38accf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542556"
---
# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="6110d-103">Recursos necesarios para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6110d-103">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6110d-104">_**Última modificación del tema:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="6110d-104">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="6110d-105">La alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente requieren recursos adicionales aparte de lo que normalmente se necesita para la operación completa.</span><span class="sxs-lookup"><span data-stu-id="6110d-105">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="6110d-106">Antes de configurar el servidor de chat persistente para la alta disponibilidad y la recuperación ante desastres, asegúrese de que dispone de los siguientes recursos además de los necesarios para el funcionamiento del servidor de chat persistente estándar.</span><span class="sxs-lookup"><span data-stu-id="6110d-106">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="6110d-107">Para obtener información adicional sobre la configuración, consulte [Configuring persistent chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="6110d-107">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="6110d-108">Una instancia de base de datos dedicada ubicada en el mismo centro de datos físico en el que se encuentra el front-end principal del servicio del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6110d-108">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="6110d-109">Esta base de datos servirá como reflejo de SQL Server para la base de datos de chat persistente principal.</span><span class="sxs-lookup"><span data-stu-id="6110d-109">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="6110d-110">Opcionalmente, designe un servidor SQL Server adicional para que sirva como testigo de creación de reflejos si desea una conmutación por error automatizada para la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="6110d-110">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="6110d-111">Una instancia de base de datos dedicada ubicada en el otro centro de datos físico.</span><span class="sxs-lookup"><span data-stu-id="6110d-111">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="6110d-112">Esta base de datos servirá como base de datos secundaria de trasvase de registros de SQL Server para la base de datos en el centro de datos principal.</span><span class="sxs-lookup"><span data-stu-id="6110d-112">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="6110d-113">Una instancia de base de datos dedicada que sirva como reflejo de SQL Server para la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="6110d-113">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="6110d-114">Si lo desea, puede designar un servidor SQL Server a servidor adicional como testigo de creación de reflejos.</span><span class="sxs-lookup"><span data-stu-id="6110d-114">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="6110d-115">Ambos deben estar ubicados en el mismo centro de datos físico que la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="6110d-115">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="6110d-116">Si el cumplimiento del servidor de chat persistente está habilitado, se necesitan tres instancias de base de datos dedicadas adicionales.</span><span class="sxs-lookup"><span data-stu-id="6110d-116">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="6110d-117">Su distribución es la misma que la que se ha descrito anteriormente para la base de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6110d-117">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="6110d-118">Aunque es posible que la base de datos de cumplimiento comparta la misma instancia de SQL Server que la base de datos de chat persistente, recomendamos instancias independientes para la alta disponibilidad y la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="6110d-118">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="6110d-119">Es necesario crear y designar un recurso compartido de archivos para los registros de transacciones de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6110d-119">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="6110d-120">Todos los servidores SQL de ambos centros de datos que ejecutan bases de datos de chat persistente deben tener acceso de lectura y escritura a este recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="6110d-120">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="6110d-121">Este recurso compartido no está designado como parte del rol FileStore.</span><span class="sxs-lookup"><span data-stu-id="6110d-121">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="6110d-122">Un recurso compartido de archivos en el servidor de base de datos secundario que sirva como carpeta de destino para los registros de transacciones de SQL Server que se copian del recurso compartido de archivos del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="6110d-122">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6110d-123">Los servidores de chat persistente activos en un grupo de servidores de chat persistente deben residir en la misma zona horaria que el grupo de Lync del próximo salto definido en la topología.</span><span class="sxs-lookup"><span data-stu-id="6110d-123">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="6110d-124">Las figuras siguientes proporcionan ejemplos sobre cómo se puede configurar todo el grupo de servidores de chat persistente en las dos topologías de grupo de servidores extendidos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6110d-124">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="6110d-125">Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda alto/latencia baja</span><span class="sxs-lookup"><span data-stu-id="6110d-125">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="6110d-126">Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta</span><span class="sxs-lookup"><span data-stu-id="6110d-126">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="6110d-127">La siguiente figura muestra una topología de grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda alto/baja latencia.</span><span class="sxs-lookup"><span data-stu-id="6110d-127">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="6110d-128">**Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda alto/latencia baja**</span><span class="sxs-lookup"><span data-stu-id="6110d-128">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="6110d-129">![Examen de configuración del grupo de servidores de chat persistente HBW](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Examen de configuración del grupo de servidores de chat persistente HBW")</span><span class="sxs-lookup"><span data-stu-id="6110d-129">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="6110d-130">La siguiente figura muestra una topología de grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta.</span><span class="sxs-lookup"><span data-stu-id="6110d-130">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="6110d-131">**Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta**</span><span class="sxs-lookup"><span data-stu-id="6110d-131">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="6110d-132">![Examen de configuración del grupo de servidores de chat persistente LBW](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Examen de configuración del grupo de servidores de chat persistente LBW")</span><span class="sxs-lookup"><span data-stu-id="6110d-132">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

