---
title: 'Lync Server 2013: conmutación por error del servidor de chat persistente'
description: 'Lync Server 2013: conmutación por error del servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42a3a8f5df203cc23be39a4a691ad713330eab59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554966"
---
# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="4983c-103">Conmutación por error del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4983c-103">Failing over Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4983c-104">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="4983c-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="4983c-105">La conmutación por error para el servidor de chat persistente está diseñada para ser principalmente un proceso manual.</span><span class="sxs-lookup"><span data-stu-id="4983c-105">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="4983c-106">El procedimiento de conmutación por error se basa en el supuesto de que el centro de datos secundario está en funcionamiento, pero los servicios del servidor de chat persistente donde se encuentra la base de datos de chat persistente principal no están disponibles, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4983c-106">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="4983c-107">La base de datos principal del servidor de chat persistente y la reflejada del servidor de chat persistente están inactivas.</span><span class="sxs-lookup"><span data-stu-id="4983c-107">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="4983c-108">El servidor front-end de Lync Server está inactivo.</span><span class="sxs-lookup"><span data-stu-id="4983c-108">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="4983c-109">El procedimiento se basa en dos pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="4983c-109">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="4983c-110">Recuperar la base de datos de chat persistente principal (MGC).</span><span class="sxs-lookup"><span data-stu-id="4983c-110">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="4983c-111">La creación de reflejos para la nueva base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="4983c-111">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="4983c-112">La base de datos de cumplimiento de chat persistente (mgccomp) no se conmuta por error.</span><span class="sxs-lookup"><span data-stu-id="4983c-112">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="4983c-113">Los contenidos de esta base de datos son transitorios y se purgan cuando el adaptador de conformidad procesa los datos.</span><span class="sxs-lookup"><span data-stu-id="4983c-113">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="4983c-114">Es su responsabilidad, como administrador de chat persistente, administrar correctamente la salida del adaptador para evitar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="4983c-114">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="4983c-115">Para conmutar por error el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4983c-115">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="4983c-116">Quite el trasvase de registros de la base de datos de trasvase de registros del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4983c-116">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="4983c-117">Mediante SQL Server Management Studio, conéctese a la instancia de base de datos donde se encuentra la base de datos de copia de seguridad del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4983c-117">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="4983c-118">Abra una ventana de consulta en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="4983c-118">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="4983c-119">Utilice el siguiente comando para colocar el trasvase de registros:</span><span class="sxs-lookup"><span data-stu-id="4983c-119">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="4983c-120">Copie cualquier archivo de copia de seguridad no copiado desde el recurso compartido de copia de seguridad a la carpeta de destino de copias del servidor de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4983c-120">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="4983c-121">Aplique cualquier copia de seguridad de registro de transacciones no aplicadas en secuencia con la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="4983c-121">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="4983c-122">Para obtener más información, consulte "Cómo: aplicar una copia de seguridad del registro de transacciones (Transact-SQL)" en https://go.microsoft.com/fwlink/p/?linkid=247428 .</span><span class="sxs-lookup"><span data-stu-id="4983c-122">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at https://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="4983c-p103">Publique en línea la base de datos mgc de copia de seguridad. Utilizando la ventana de consultas que se abre en el paso 1b, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4983c-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="4983c-125">Finalice todas las conexiones a la base de datos mgc, si existe alguna:</span><span class="sxs-lookup"><span data-stu-id="4983c-125">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="4983c-126">**exec Sp \_ who2** para identificar conexiones a la base de datos MGC.</span><span class="sxs-lookup"><span data-stu-id="4983c-126">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="4983c-127">\*\*Kill \<spid\> \*\* para finalizar estas conexiones.</span><span class="sxs-lookup"><span data-stu-id="4983c-127">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="4983c-128">Publique en línea la base de datos:</span><span class="sxs-lookup"><span data-stu-id="4983c-128">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="4983c-129">**restaurar la base de datos MGC con recuperación**.</span><span class="sxs-lookup"><span data-stu-id="4983c-129">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="4983c-130">En el shell de administración de Lync Server, use el comando **set-CsPersistentChatState-Identity "Service: ATL-CS-001.litwareinc.com" – PoolState FailedOver** para conmutar por error a la base de datos de copia de seguridad MGC.</span><span class="sxs-lookup"><span data-stu-id="4983c-130">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="4983c-131">Asegúrese de sustituir el nombre de dominio completo del grupo de servidores de chat persistente por atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4983c-131">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="4983c-132">La base de datos de copia de seguridad mgc funciona actualmente como base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="4983c-132">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="4983c-133">En el shell de administración de Lync Server, use el cmdlet **install-CsMirrorDatabase** para establecer un reflejo de alta disponibilidad para la base de datos de copia de seguridad que ahora sirve como base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="4983c-133">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="4983c-134">Utilice la instancia de la base de datos de copia de seguridad como base de datos principal y la instancia de la base de datos reflejada de copia de seguridad como instancia reflejada.</span><span class="sxs-lookup"><span data-stu-id="4983c-134">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="4983c-135">Este no es el mismo reflejo de lo que se configuró inicialmente para la base de datos principal durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="4983c-135">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="4983c-136">Para obtener más información, consulte la sección "uso de los cmdlets del shell de administración de Lync Server" en [DEPLOYING SQL Mirror for back end Server High Availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="4983c-136">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="4983c-137">Establezca los servidores activos del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4983c-137">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="4983c-138">Desde el shell de comandos de Lync Server, use el cmdlet **set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.</span><span class="sxs-lookup"><span data-stu-id="4983c-138">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4983c-139">Todos los servidores activos deben estar ubicados dentro del mismo centro de datos como la nueva base de datos principal o en un centro de datos que tenga una latencia baja o un ancho de banda alto.</span><span class="sxs-lookup"><span data-stu-id="4983c-139">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="4983c-140">En este punto, la conmutación por error de la base de datos principal del servidor de chat persistente en la base de datos de copia de seguridad del servidor de chat persistente se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="4983c-140">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

