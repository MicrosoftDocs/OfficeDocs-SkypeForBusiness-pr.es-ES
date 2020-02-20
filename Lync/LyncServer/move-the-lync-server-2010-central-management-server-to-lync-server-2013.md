---
title: Mover el servidor de administración central de Lync Server 2010 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b344ff2fb9fb4ed123d864e219f64d9c1f04202
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="d86f6-102">Mover el servidor de administración central de Lync Server 2010 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d86f6-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d86f6-103">_**Última modificación del tema:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="d86f6-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="d86f6-104">Después de realizar la migración de Lync Server 2010 a Lync Server 2013, debe mover el servidor de administración central de Lync Server 2010 al servidor o grupo de servidores front-end de Lync Server 2013, antes de poder quitar el servidor de Lync Server 2010 heredado.</span><span class="sxs-lookup"><span data-stu-id="d86f6-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="d86f6-105">El servidor de administración central es un único sistema de réplica principal/múltiple, donde la copia de lectura y escritura de la base de datos está retenida por el servidor front-end que contiene el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="d86f6-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="d86f6-106">Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y implementación.</span><span class="sxs-lookup"><span data-stu-id="d86f6-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="d86f6-107">La base de datos local recibe actualizaciones de réplica por medio del agente replicador de réplicas de Lync Server que se ejecuta como un servicio en todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="d86f6-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="d86f6-108">El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está formado por los archivos XDS. MDF y XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="d86f6-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="d86f6-109">Un punto de control de servicio (SCP) hace referencia a la ubicación de la base de datos maestra en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d86f6-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="d86f6-110">Todas las herramientas que usan el servidor de administración central para administrar y configurar Lync Server usan el SCP para localizar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="d86f6-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="d86f6-111">Después de mover correctamente el servidor de administración central, debe quitar las bases de datos del servidor de administración central del servidor front-end original.</span><span class="sxs-lookup"><span data-stu-id="d86f6-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="d86f6-112">Para obtener información sobre cómo quitar las bases de datos del servidor de administración central, vea [quitar la base de datos de SQL Server para un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d86f6-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="d86f6-113">Use el cmdlet **Move-CsManagementServer** de Windows PowerShell en el shell de administración de Lync Server para mover la base de datos de la base de datos de lync Server 2010 SQL Server a la base de datos de sql server 2013 de Lync Server y, a continuación, actualice el SCP para que apunte a la ubicación del servidor de administración central de lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d86f6-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="d86f6-114">Preparar los servidores front-end de Lync Server 2013 antes de mover el servidor de administración central</span><span class="sxs-lookup"><span data-stu-id="d86f6-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="d86f6-115">Use los procedimientos de esta sección para preparar los servidores front-end de Lync Server 2013 antes de mover el servidor de administración central de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d86f6-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="d86f6-116">Para preparar un grupo de servidores front-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="d86f6-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="d86f6-117">En el grupo de servidores front-end de Lync Server 2013 Enterprise Edition donde desea reubicar el servidor de administración central: inicie sesión en el equipo en el que está instalado el shell de administración de Lync Server como miembro del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="d86f6-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="d86f6-118">También debe tener derechos y permisos de usuario sysadmin de base de datos de SQL Server en la base de datos en la que desea instalar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="d86f6-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="d86f6-119">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d86f6-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="d86f6-120">Para crear el nuevo almacén de administración central en la base de datos de Lync Server 2013 SQL Server, en el shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="d86f6-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="d86f6-121">Confirme que el estado del servicio **Lync Server Front-End** esté en **Iniciado**</span><span class="sxs-lookup"><span data-stu-id="d86f6-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="d86f6-122">Para preparar un servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d86f6-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="d86f6-123">En el servidor front-end de Lync Server 2013 Standard Edition donde desea reubicar el servidor de administración central: inicie sesión en el equipo en el que está instalado el shell de administración de Lync Server como miembro del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="d86f6-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="d86f6-124">Abra el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d86f6-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="d86f6-125">En el Asistente para la implementación de Lync Server, haga clic en **preparar el primer servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="d86f6-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="d86f6-126">En la página **ejecución de comandos** , SQL Server Express está instalado como servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="d86f6-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="d86f6-127">Se crean las reglas de firewall necesarias.</span><span class="sxs-lookup"><span data-stu-id="d86f6-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="d86f6-128">Cuando finalice la instalación de la base de datos y el software necesario como requisito previo, haga clic en  \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="d86f6-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d86f6-129">Es posible que la instalación inicial necesite bastante tiempo antes de mostrar actualizaciones en la pantalla de resumen de resultados de comandos.</span><span class="sxs-lookup"><span data-stu-id="d86f6-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="d86f6-130">Esto se debe a la instalación de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="d86f6-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="d86f6-131">Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="d86f6-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="d86f6-132">Para crear el nuevo almacén de administración central en el servidor front-end de Lync Server 2013 Standard Edition, en el shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="d86f6-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="d86f6-133">Confirme que el estado del servicio **Lync Server Front-End** esté en **Iniciado**</span><span class="sxs-lookup"><span data-stu-id="d86f6-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="d86f6-134">Para mover el servidor de administración central de Lync Server 2010 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d86f6-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="d86f6-135">En el servidor de Lync Server 2013 que será el servidor de administración central: inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="d86f6-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="d86f6-136">También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d86f6-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="d86f6-137">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d86f6-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="d86f6-138">En el shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="d86f6-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d86f6-139">Si <CODE>Enable-CsTopology</CODE> no se realiza correctamente, solucione el problema para evitar que el comando se complete antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d86f6-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="d86f6-140">Si <STRONG>enable-CsTopology</STRONG> no se realiza correctamente, se producirá un error en el movimiento y puede dejar la topología en un estado en el que no haya almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="d86f6-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="d86f6-141">En el servidor front-end de Lync Server 2013 o el grupo de servidores front-end, en el shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="d86f6-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="d86f6-142">El shell de administración de Lync Server muestra los servidores, los almacenes de archivos, los almacenes de bases de datos y los puntos de conexión de servicio del estado actual y el estado propuesto.</span><span class="sxs-lookup"><span data-stu-id="d86f6-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="d86f6-143">Lea la información cuidadosamente y confirme que se trata del origen y el destino deseados.</span><span class="sxs-lookup"><span data-stu-id="d86f6-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="d86f6-144">Escriba **S** para continuar o **N** para detener la migración.</span><span class="sxs-lookup"><span data-stu-id="d86f6-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="d86f6-145">Revise las advertencias o los errores generados por el comando **Move-CsManagementServer** y resuélvalos.</span><span class="sxs-lookup"><span data-stu-id="d86f6-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="d86f6-146">En el servidor de Lync Server 2013, abra el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d86f6-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="d86f6-147">En el Asistente para la implementación de Lync Server, haga clic en **instalar o actualizar el sistema Lync Server**, haga clic en **paso 2: configurar o quitar componentes de Lync Server**, haga clic en **siguiente**, revise el Resumen y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d86f6-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="d86f6-148">En el servidor de Lync Server 2010, abra el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d86f6-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="d86f6-149">En el Asistente para la implementación de Lync Server, haga clic en **instalar o actualizar el sistema Lync Server**, haga clic en **paso 2: configurar o quitar componentes de Lync Server**, haga clic en **siguiente**, revise el Resumen y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d86f6-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="d86f6-150">Reinicie el servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d86f6-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="d86f6-151">Esto es necesario debido a un cambio de pertenencia a grupo para obtener acceso a la base de datos del servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="d86f6-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="d86f6-152">Para confirmar que se está produciendo la replicación con el nuevo almacén de administración central, en el shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="d86f6-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d86f6-153">Es posible que la replicación necesite bastante tiempo para actualizar todas las réplicas.</span><span class="sxs-lookup"><span data-stu-id="d86f6-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="d86f6-154">Para quitar los archivos del almacén de administración central de Lync Server 2010 después de un movimiento</span><span class="sxs-lookup"><span data-stu-id="d86f6-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="d86f6-155">En el servidor de Lync Server 2010: inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="d86f6-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="d86f6-156">También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d86f6-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="d86f6-157">Abrir Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86f6-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d86f6-158">No continúe con la eliminación de los archivos de base de datos anteriores hasta que la replicación haya finalizado y esté estable.</span><span class="sxs-lookup"><span data-stu-id="d86f6-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="d86f6-159">Si quita los archivos antes de completar la replicación, se interrumpirá el proceso de replicación y dejará el servidor de administración central recién movido en un estado desconocido.</span><span class="sxs-lookup"><span data-stu-id="d86f6-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="d86f6-160">Utilice el cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> para confirmar el estado de la replicación.</span><span class="sxs-lookup"><span data-stu-id="d86f6-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="d86f6-161">Para quitar los archivos de la base de datos de almacén de administración central del servidor de administración central de Lync Server 2010, escriba:</span><span class="sxs-lookup"><span data-stu-id="d86f6-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="d86f6-162">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d86f6-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="d86f6-163">Donde el \<FQDN de SQL Server\> es el servidor Back-End de Lync Server 2010 en una implementación de Enterprise Edition o el FQDN del servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d86f6-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

