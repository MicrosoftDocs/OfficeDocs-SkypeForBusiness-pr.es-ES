---
title: 'Lync Server 2013: alta disponibilidad del servidor back-end'
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
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="af708-102">Servidor back end de alta disponibilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af708-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af708-103">_**Última modificación del tema:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="af708-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="af708-104">Para garantizar la alta disponibilidad de los servidores de servicios de fondo, puede usar la creación de reflejos de SQL sincrónico o la organización en clústeres SQL.</span><span class="sxs-lookup"><span data-stu-id="af708-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="af708-105">Uso de una de estas soluciones opcional, pero se recomienda para mantener la continuidad empresarial de su organización.</span><span class="sxs-lookup"><span data-stu-id="af708-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="af708-106">El reflejo de SQL asincrónico no es compatible con la alta disponibilidad del servidor back-end en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af708-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="af708-107">En el resto de este documento, el reflejo SQL significa reflejos de SQL sincrónico, a menos que se indique lo contrario de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="af708-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="af708-108">Puede configurar la creación de reflejos de SQL fácilmente con el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="af708-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="af708-109">Los clústeres de conmutación por error de SQL deben configurarse desde SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af708-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="af708-110">Si utiliza la creación de reflejos de SQL o la agrupación de SQL en un grupo que está emparejado con otro grupo de servidores front-end para la recuperación de desastres, debe usar la solución de alta disponibilidad de back-end en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="af708-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="af708-111">No debe emparejar un grupo con el reflejo de SQL con un grupo mediante el uso de clústeres de SQL.</span><span class="sxs-lookup"><span data-stu-id="af708-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="af708-112">Al implementar el reflejo de SQL, todas las bases de datos de Lync Server del grupo están reflejadas, incluido el almacén central de administración, si se encuentra en este grupo, así como la base de datos de aplicación de grupo de respuesta y la base de datos de aplicación de estacionamiento de llamadas, si dichas aplicaciones se están ejecutando en el grupo.</span><span class="sxs-lookup"><span data-stu-id="af708-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="af708-113">Con la creación de reflejos de SQL, no es necesario usar almacenamiento compartido para los servidores.</span><span class="sxs-lookup"><span data-stu-id="af708-113">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="af708-114">Cada servidor guarda su copia de la base de datos en un almacenamiento local.</span><span class="sxs-lookup"><span data-stu-id="af708-114">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="af708-115">Puede optar por implementar el reflejo de SQL con un testigo o sin él.</span><span class="sxs-lookup"><span data-stu-id="af708-115">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="af708-116">Recomendamos usar un testigo, porque esto permite que la conmutación por error del servidor back-end sea automática.</span><span class="sxs-lookup"><span data-stu-id="af708-116">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="af708-117">De lo contrario, un administrador tendrá que invocar manualmente la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="af708-117">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="af708-118">Tenga en cuenta que, incluso si se implementa un testigo, un administrador puede invocar manualmente la conmutación por error del servidor back-end, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="af708-118">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="af708-p106">Si usa un testigo, puede usar un único testigo para varios pares de servidores back-end. No existe una correspondencia estricta uno a uno entre testigos y pares de servidores back-end. Las implementaciones en las que se emplea un único testigo para varios pares de servidores back-end no son tan resistentes como las topologías con un testigo independiente para cada par de servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="af708-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="af708-122">Para obtener más información sobre la compatibilidad con clústeres de SQL, vea [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="af708-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="af708-123">Para obtener más información sobre la implementación de clústeres de SQL, consulte [Configure SQL Server clustering for Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="af708-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="af708-124">Tiempo de recuperación para la conmutación automática por error del servidor de back-end con reflejo SQL</span><span class="sxs-lookup"><span data-stu-id="af708-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="af708-125">Para el failover de back end automático con reflejo SQL, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="af708-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="af708-126">A causa de la creación de reflejos de SQL sincrónicos, no se espera la pérdida de datos durante la falla del servidor de servicios de fondo, excepto en raras ocasiones, cuando los servidores front-end y el servidor back-end se desactivan simultáneamente mientras se mueven los datos entre los servidores.</span><span class="sxs-lookup"><span data-stu-id="af708-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="af708-127">El objetivo de ingeniería para el objetivo de punto de recuperación (RPO) es de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="af708-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="af708-128">Experiencia del usuario durante el error del servidor back-end con reflejo SQL</span><span class="sxs-lookup"><span data-stu-id="af708-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="af708-129">La experiencia del usuario durante un error depende de la naturaleza del error y de la topología.</span><span class="sxs-lookup"><span data-stu-id="af708-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="af708-130">Si utiliza el reflejo de SQL y tiene un testigo configurado, y se produce un error en el principal, el failover del servidor de back-end se produce de forma automática y rápida.</span><span class="sxs-lookup"><span data-stu-id="af708-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="af708-131">Los usuarios activos no tendrían que notar muchas interrupciones en sus sesiones en curso.</span><span class="sxs-lookup"><span data-stu-id="af708-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="af708-132">Si no hay ningún testigo configurado, tomará algún tiempo que el administrador invoque manualmente la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="af708-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="af708-133">Durante ese tiempo, los usuarios activos probablemente lo notarán.</span><span class="sxs-lookup"><span data-stu-id="af708-133">During that time, active users may be affected.</span></span> <span data-ttu-id="af708-134">Continuarán con sus sesiones normalmente durante unos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="af708-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="af708-135">Si el principal aún no se restaura o un administrador no conmuta por error a la copia de seguridad, entonces los usuarios cambian al modo de resistencia, lo que significa que no pueden realizar tareas que requieran un cambio persistente en Lync Server (como agregar un contacto).</span><span class="sxs-lookup"><span data-stu-id="af708-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="af708-p111">Si tanto el servidor back-end principal como el de reflejo fallan o si se produce un error en uno de esos servidores y el testigo, el servidor back-end dejará de estar disponible (incluso si se trata del principal que sigue funcionando). En este caso, los usuarios activos se cambian al modo de resistencia después de algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="af708-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

