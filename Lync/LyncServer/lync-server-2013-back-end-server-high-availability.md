---
title: 'Lync Server 2013: alta disponibilidad del servidor back-end'
description: 'Lync Server 2013: alta disponibilidad del servidor back-end.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805cbf96e107329aa5c374cfa1e2d01234d360a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543776"
---
# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="463e5-103">Alta disponibilidad del servidor back-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="463e5-103">Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="463e5-104">_**Última modificación del tema:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="463e5-104">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="463e5-105">Para garantizar la alta disponibilidad de los servidores back-end, puede usar la creación de reflejos de SQL sincrónicos o clústeres SQL.</span><span class="sxs-lookup"><span data-stu-id="463e5-105">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="463e5-106">El uso de una de estas soluciones es opcional, pero se recomienda para mantener la continuidad empresarial de la organización.</span><span class="sxs-lookup"><span data-stu-id="463e5-106">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="463e5-107">La creación de reflejo de SQL asincrónico no es compatible con alta disponibilidad del servidor back-end en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="463e5-107">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="463e5-108">En lo que resta de este documento, la creación de reflejos SQL significa la creación de reflejos SQL sincrónica, salvo que se aclare explícitamente lo contrario.</span><span class="sxs-lookup"><span data-stu-id="463e5-108">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="463e5-109">Puede configurar fácilmente la creación de reflejos de SQL con el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="463e5-109">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="463e5-110">Para los clústeres de conmutación por error de SQL, debe usar SQL Server para la instalación.</span><span class="sxs-lookup"><span data-stu-id="463e5-110">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="463e5-111">Si usa la creación de reflejo de SQL o un clúster de SQL en un grupo que está emparejado con otro grupo de servidores front-end para la recuperación ante desastres, debe usar la solución de alta disponibilidad back-end en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="463e5-111">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="463e5-112">No debe emparejar un grupo con la creación de reflejos de SQL con un grupo de servidores mediante clústeres de SQL.</span><span class="sxs-lookup"><span data-stu-id="463e5-112">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="463e5-113">Al implementar la creación de reflejos de SQL, todas las bases de datos de Lync Server del grupo están reflejadas, incluido el almacén de administración central, si se encuentra en este grupo, así como la base de datos de aplicación de grupo de respuesta y la base de datos de aplicación de estacionamiento de llamadas, si esas aplicaciones se ejecutan en el grupo.</span><span class="sxs-lookup"><span data-stu-id="463e5-113">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="463e5-p104">Con la creación de reflejos SQL, no necesita utilizar almacenamiento compartido para los servidores. Cada servidor guarda su copia de la base de datos en un almacenamiento local.</span><span class="sxs-lookup"><span data-stu-id="463e5-p104">With SQL mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="463e5-p105">Puede elegir implementar una creación de reflejos SQL con o sin un testigo. Recomendamos utilizar un testigo porque esto permite que la conmutación por error del servidor back-end sea automática. De lo contrario, un administrador debe invocar manualmente la conmutación por error. Tenga en cuenta que incluso si se implementa un testigo, un administrador puede invocar manualmente la conmutación por error del servidor back-end, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="463e5-p105">You may choose to deploy SQL mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="463e5-p106">Si utiliza un testigo, puede utilizar un único testigo para varios pares de servidores back-end. No existe una correspondencia estricta uno a uno entre testigos y pares de servidores back-end. Las implementaciones que utilizan un único testigo para varios pares de servidores back-end no son tan resistentes como las topologías con un testigo independiente para cada par de servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="463e5-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="463e5-123">Para obtener más información acerca de la compatibilidad con clústeres de SQL, consulte [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="463e5-123">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="463e5-124">Para obtener más información sobre la implementación de clústeres de SQL, vea [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="463e5-124">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="463e5-125">Tiempo de recuperación para la conmutación por error del servidor back-end automático con reflejo SQL</span><span class="sxs-lookup"><span data-stu-id="463e5-125">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="463e5-126">Para la conmutación por error de back-end automática con creación de reflejos de SQL, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="463e5-126">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="463e5-127">Debido a la creación de reflejos SQL sincrónica, no prevemos pérdida de datos durante los errores en el servidor back-end excepto en raras ocasiones, cuando tanto los servidores front-end y los servidores back-end dejan de funcionar simultáneamente mientras se mueven datos entre los servidores.</span><span class="sxs-lookup"><span data-stu-id="463e5-127">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="463e5-128">El destino de ingeniería para objetivo de punto de recuperación (RPO) es de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="463e5-128">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="463e5-129">Experiencia del usuario durante el error del servidor back-end con la creación de reflejo de SQL</span><span class="sxs-lookup"><span data-stu-id="463e5-129">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="463e5-130">La experiencia del usuario durante un error depende de la naturaleza del error y de la topología.</span><span class="sxs-lookup"><span data-stu-id="463e5-130">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="463e5-131">Si usa la creación de reflejos de SQL y ha configurado un testigo, y se produce un error en la entidad de seguridad, el failover del servidor back-end se produce de forma automática y rápida.</span><span class="sxs-lookup"><span data-stu-id="463e5-131">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="463e5-132">Los usuarios activos no deberían notar muchas interrupciones en sus sesiones en curso.</span><span class="sxs-lookup"><span data-stu-id="463e5-132">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="463e5-133">Si no hay ningún testigo configurado, llevará algún tiempo hasta que el administrador pueda invocar manualmente la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="463e5-133">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="463e5-134">Durante este tiempo, es posible que los usuarios activos se vean afectados.</span><span class="sxs-lookup"><span data-stu-id="463e5-134">During that time, active users may be affected.</span></span> <span data-ttu-id="463e5-135">Continuarán sus sesiones como normales durante unos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="463e5-135">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="463e5-136">Si el principal todavía no se ha restaurado o un administrador no ha conmutado por error a la copia de seguridad, entonces los usuarios cambian al modo de resistencia, lo que significa que no pueden realizar tareas que requieran un cambio persistente en Lync Server (como agregar un contacto).</span><span class="sxs-lookup"><span data-stu-id="463e5-136">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="463e5-p111">Si tanto el servidor back-end principal como el de reflejo fallan o si se produce un error en uno de esos servidores y el testigo, el servidor back-end dejará de estar disponible (incluso si se trata del principal que sigue funcionando). En este caso, los usuarios activos se cambian al modo de resistencia después de algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="463e5-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

