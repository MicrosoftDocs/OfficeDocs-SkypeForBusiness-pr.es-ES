---
title: Soporte de software de base de datos de Lync Server 2013
description: 'Lync Server 2013: compatibilidad con software de base de datos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c5d7b44e5febc4123dbcdf7072b98fcfd004609
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558156"
---
# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="34f7e-103">Compatibilidad con software de base de datos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34f7e-103">Database software support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34f7e-104">_**Última modificación del tema:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="34f7e-104">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="34f7e-105">Lync Server 2013 admite los siguientes sistemas de administración de bases de datos:</span><span class="sxs-lookup"><span data-stu-id="34f7e-105">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="34f7e-106">**Base de datos back-end de un grupo de servidores front-end, una base de datos de archivado, una base de datos de supervisión, una base de datos de chat persistente y una base de datos para el cumplimiento de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="34f7e-106">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="34f7e-p101">Software de base de datos Microsoft SQL Server 2008 R2 Enterprise (edición de 64 bits) o el último service pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="34f7e-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="34f7e-p102">Microsoft SQL Server 2008 R2 Standard (edición de 64 bits) o el último service pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="34f7e-p102">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="34f7e-p103">Microsoft SQL Server 2012 Enterprise (edición de 64 bits) o el último service pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="34f7e-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="34f7e-p104">Microsoft SQL Server 2012 Standard (edición de 64 bits) o el último service pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="34f7e-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="34f7e-115">**Bases de datos del servidor Standard Edition y de los servidores front-end**</span><span class="sxs-lookup"><span data-stu-id="34f7e-115">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="34f7e-116">Microsoft SQL Server 2012 Express (edición de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="34f7e-116">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="34f7e-117">Además, se recomienda ejecutar el último Service Pack.</span><span class="sxs-lookup"><span data-stu-id="34f7e-117">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="34f7e-118">Admitimos la revisión y actualización de Microsoft SQL Server en servidores front-end y servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="34f7e-118">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="34f7e-119">Sin embargo, cuando realiza cualquier tipo de actualización o revisión en los servidores front-end, debe tener en cuenta los requisitos de quórum.</span><span class="sxs-lookup"><span data-stu-id="34f7e-119">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="34f7e-120">Para obtener más información, vea [actualizar o actualizar los servidores front-end en Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) y las [topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="34f7e-120">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34f7e-121">Lync Server 2013 instala automáticamente Microsoft SQL Server 2012 Express (edición de 64 bits) en cada servidor Standard Edition y en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="34f7e-121">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="34f7e-122">Lync Server 2013 no admite la edición de 32 bits de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34f7e-122">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="34f7e-123">Emplee la edición de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="34f7e-123">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="34f7e-124">SQL Server Web Edition y SQL Server Workgroup Edition no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="34f7e-124">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="34f7e-125">No puede usarlos con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34f7e-125">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="34f7e-126">Lync Server 2013 admite la creación de reflejos de bases de datos nativas.</span><span class="sxs-lookup"><span data-stu-id="34f7e-126">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="34f7e-127">Para usar la función de servidor de supervisión, debe instalar SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="34f7e-127">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="34f7e-128">En un grupo de servidores front-end, la base de datos back-end puede ser un único equipo con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34f7e-128">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="34f7e-129">Si combinar las bases de datos de Lync Server con otras bases de datos, es muy recomendable evaluar todos los factores que pueden afectar a la disponibilidad y el rendimiento, así como garantizar que, si se produce un error en un nodo, el nodo restante pueda controlar la carga.</span><span class="sxs-lookup"><span data-stu-id="34f7e-129">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="34f7e-130">Para comprobar las capacidades de conmutación por error, se recomienda probar todos los escenarios de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="34f7e-130">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="34f7e-131">Uso de la creación de reflejos de SQL y los clústeres de SQL</span><span class="sxs-lookup"><span data-stu-id="34f7e-131">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="34f7e-132">Lync Server 2013 admite el uso de la creación de reflejo de SQL o de la organización en clústeres de SQL para cada base de datos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34f7e-132">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="34f7e-133">Puede configurar la creación de reflejos de SQL fácilmente con la herramienta Topology Builder en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34f7e-133">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="34f7e-134">Para los clústeres de conmutación por error de SQL, debe usar SQL Server para la instalación.</span><span class="sxs-lookup"><span data-stu-id="34f7e-134">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="34f7e-135">Lync Server 2013 admite topologías de creación de reflejos de SQL y de agrupación en clústeres de SQL para todas las implementaciones, incluidas las implementaciones de Greenfield y las organizaciones que han actualizado desde versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34f7e-135">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="34f7e-136">La compatibilidad con clústeres de SQL es para una configuración activa/pasiva.</span><span class="sxs-lookup"><span data-stu-id="34f7e-136">SQL Clustering support is for an active/passive configuration.</span></span> <span data-ttu-id="34f7e-137">Por motivos de rendimiento, el nodo pasivo no debe compartirse con ninguna otra instancia de SQL.</span><span class="sxs-lookup"><span data-stu-id="34f7e-137">For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="34f7e-138">Se incluye la siguiente compatibilidad:</span><span class="sxs-lookup"><span data-stu-id="34f7e-138">The following support is included:</span></span>

  - <span data-ttu-id="34f7e-139">Clústeres de conmutación por error de dos nodos para los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="34f7e-139">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="34f7e-140">Microsoft SQL Server 2012 Standard (edición de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="34f7e-140">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="34f7e-141">Además, se recomienda ejecutar el último Service Pack.</span><span class="sxs-lookup"><span data-stu-id="34f7e-141">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="34f7e-142">Microsoft SQL Server 2008 R2 Standard (edición de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="34f7e-142">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="34f7e-143">Además, se recomienda ejecutar el último Service Pack.</span><span class="sxs-lookup"><span data-stu-id="34f7e-143">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="34f7e-144">Clústeres de conmutación por error de hasta dieciséis nodos para los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="34f7e-144">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="34f7e-145">Microsoft SQL Server 2012 Enterprise (edición de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="34f7e-145">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="34f7e-146">Además, se recomienda ejecutar el último Service Pack.</span><span class="sxs-lookup"><span data-stu-id="34f7e-146">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="34f7e-147">Microsoft SQL Server 2008 R2 Enterprise Database software (edición de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="34f7e-147">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="34f7e-148">Además, se recomienda ejecutar el último Service Pack.</span><span class="sxs-lookup"><span data-stu-id="34f7e-148">Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="34f7e-149">Para obtener más información acerca de la creación de reflejos de SQL, vea [back end Server High Availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="34f7e-149">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="34f7e-150">Para obtener más información sobre cómo implementar clústeres de SQL, vea [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="34f7e-150">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="34f7e-151">Para obtener más información y procedimientos recomendados para clústeres de conmutación por error en SQL Server 2012, consulte <https://technet.microsoft.com/library/hh231721.aspx> .</span><span class="sxs-lookup"><span data-stu-id="34f7e-151">For more information and best practices for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="34f7e-152">Para clústeres de conmutación por error en SQL Server 2008, consulte <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .</span><span class="sxs-lookup"><span data-stu-id="34f7e-152">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

