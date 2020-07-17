---
title: Mover el servidor de administración central
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de migrar a Skype empresarial Server 2019, debe mover el servidor de administración central al servidor o grupo de servidores front-end de Skype empresarial Server 2019, antes de que pueda quitar el servidor heredado.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752472"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="850af-103">Mover el servidor de administración central heredado a Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="850af-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="850af-104">Después de migrar a Skype empresarial Server 2019, y antes de poder quitar el servidor heredado, debe mover el servidor de administración central al servidor o grupo de servidores front-end de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="850af-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="850af-105">El servidor de administración central es un único sistema de réplica principal/múltiple, donde la copia de lectura y escritura de la base de datos está retenida por el servidor front-end que contiene el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="850af-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="850af-106">Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la configuración y la implementación.</span><span class="sxs-lookup"><span data-stu-id="850af-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="850af-107">La base de datos local recibe actualizaciones de réplica por medio del agente replicador de réplicas de Skype empresarial Server que se ejecuta como un servicio en todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="850af-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="850af-108">El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está formado por los archivos XDS. MDF y XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="850af-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="850af-109">Un punto de control de servicio (SCP) hace referencia a la ubicación de la base de datos maestra en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="850af-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="850af-110">Todas las herramientas que usan el servidor de administración central para administrar y configurar Skype empresarial Server usan el SCP para localizar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="850af-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="850af-111">Después de mover correctamente el servidor de administración central, debe quitar las bases de datos del servidor de administración central del servidor front-end original.</span><span class="sxs-lookup"><span data-stu-id="850af-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="850af-112">Para obtener información sobre cómo quitar las bases de datos del servidor de administración central, vea [quitar la base de datos de SQL Server para un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="850af-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="850af-113">Use el cmdlet **Move-CsManagementServer** de Windows PowerShell en el shell de administración de Skype empresarial Server para mover la base de datos de la instalación heredada de SQL Server a la base de datos de sql server 2019 de Skype empresarial Server y, a continuación, actualice el SCP para que apunte a la ubicación del servidor de administración central de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="850af-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="850af-114">Use los procedimientos de esta sección para preparar los servidores front-end de Skype empresarial Server 2019 antes de mover el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="850af-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="850af-115">Para preparar un grupo de servidores front-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="850af-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="850af-116">En el grupo de servidores front-end de Skype empresarial Server 2019 Enterprise Edition donde desea reubicar el servidor de administración central, inicie sesión en el equipo en el que está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="850af-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="850af-117">También debe tener derechos y permisos de usuario sysadmin de base de datos de SQL Server en la base de datos en la que desea instalar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="850af-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="850af-118">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="850af-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="850af-119">Para crear el nuevo almacén de administración central en la base de datos de SQL Server de Skype empresarial Server 2019, en el shell de administración de Skype empresarial Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="850af-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="850af-120">Confirme que el estado del servicio **front-end de Skype empresarial Server** se **ha iniciado**.</span><span class="sxs-lookup"><span data-stu-id="850af-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="850af-121">Para preparar un servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="850af-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="850af-122">En el servidor front-end de Skype empresarial Server 2019 Standard Edition donde desea reubicar el servidor de administración central, inicie sesión en el equipo en el que está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="850af-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="850af-123">Abra el Asistente para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="850af-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="850af-124">En el Asistente para la implementación de Skype empresarial Server, haga clic en **preparar el primer servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="850af-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="850af-125">En la página **ejecución de comandos** , SQL Server Express está instalado como servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="850af-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="850af-126">Se crean las reglas de firewall necesarias.</span><span class="sxs-lookup"><span data-stu-id="850af-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="850af-127">Cuando finalice la instalación de la base de datos y el software necesario como requisito previo, haga clic en  \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="850af-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="850af-128">Es posible que la instalación inicial necesite bastante tiempo antes de mostrar actualizaciones en la pantalla de resumen de resultados de comandos.</span><span class="sxs-lookup"><span data-stu-id="850af-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="850af-129">Esto se debe a la instalación de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="850af-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="850af-130">Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="850af-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="850af-131">Para crear el nuevo almacén de administración central en el servidor front-end de Skype empresarial Server 2019 Standard Edition, en el shell de administración de Skype empresarial Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="850af-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="850af-132">Confirme que el estado del servicio **front-end de Skype empresarial Server** se **ha iniciado**.</span><span class="sxs-lookup"><span data-stu-id="850af-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="850af-133">Para mover el servidor de administración central de instalaciones heredadas a Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="850af-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="850af-134">En el servidor de Skype empresarial Server 2019 que será el servidor de administración central, inicie sesión en el equipo en el que está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="850af-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="850af-135">También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="850af-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="850af-136">Abra el shell de administración de Skype empresarial Server (ejecutar como administrador).</span><span class="sxs-lookup"><span data-stu-id="850af-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="850af-137">En el shell de administración de Skype empresarial Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="850af-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="850af-138">Si `Enable-CsTopology` no se realiza correctamente, solucione el problema para evitar que el comando se complete antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="850af-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="850af-139">Si **enable-CsTopology** no se realiza correctamente, se producirá un error en el movimiento y puede dejar la topología en un estado en el que no haya almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="850af-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="850af-140">En el servidor front-end de Skype empresarial Server 2019 o en el grupo de servidores front-end, en el shell de administración de Skype empresarial Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="850af-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="850af-141">El shell de administración de Skype empresarial Server muestra los servidores, los almacenes de archivos, los almacenes de bases de datos y los puntos de conexión de servicio del estado actual y el estado propuesto.</span><span class="sxs-lookup"><span data-stu-id="850af-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="850af-142">Lea la información cuidadosamente y confirme que se trata del origen y el destino deseados.</span><span class="sxs-lookup"><span data-stu-id="850af-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="850af-143">Escriba **S** para continuar o **N** para detener la migración.</span><span class="sxs-lookup"><span data-stu-id="850af-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="850af-144">Revise las advertencias o los errores generados por el comando **Move-CsManagementServer** y resuélvalos.</span><span class="sxs-lookup"><span data-stu-id="850af-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="850af-145">En el servidor de Skype empresarial Server 2019, abra el Asistente para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="850af-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="850af-146">En el Asistente para la implementación de Skype empresarial Server, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**, haga clic en **paso 2: configurar o quitar componentes de Skype empresarial Server**, haga clic en **siguiente**, revise el Resumen y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="850af-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="850af-147">En el servidor de instalación heredado, abra el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="850af-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="850af-148">En el Asistente para la implementación de Skype empresarial Server, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**, haga clic en **paso 2: configurar o quitar componentes de Skype empresarial Server**, haga clic en **siguiente**, revise el Resumen y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="850af-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="850af-149">Reinicie el servidor de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="850af-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="850af-150">Esto es necesario debido a un cambio de pertenencia a grupo para obtener acceso a la base de datos del servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="850af-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="850af-151">Para confirmar que se está produciendo la replicación con el nuevo almacén de administración central, en el shell de administración de Skype empresarial Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="850af-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="850af-152">Es posible que la replicación necesite bastante tiempo para actualizar todas las réplicas.</span><span class="sxs-lookup"><span data-stu-id="850af-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="850af-153">Para quitar los archivos de almacén de administración central de instalación heredados después de un movimiento</span><span class="sxs-lookup"><span data-stu-id="850af-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="850af-154">En el servidor de instalación heredado, inicie sesión en el equipo en el que está instalado el shell de administración de Skype empresarial Server como miembro del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="850af-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="850af-155">También debe tener los permisos y derechos de usuario del administrador de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="850af-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="850af-156">Abrir Shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="850af-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="850af-157">No continúe con la eliminación de los archivos de base de datos anteriores hasta que la replicación haya finalizado y esté estable.</span><span class="sxs-lookup"><span data-stu-id="850af-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="850af-158">Si quita los archivos antes de completar la replicación, se interrumpirá el proceso de replicación y dejará el servidor de administración central recién movido en un estado desconocido.</span><span class="sxs-lookup"><span data-stu-id="850af-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="850af-159">Utilice el cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar el estado de la replicación.</span><span class="sxs-lookup"><span data-stu-id="850af-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="850af-160">Para quitar los archivos de la base de datos de almacén de administración central del servidor de administración central de instalación heredada, escriba:</span><span class="sxs-lookup"><span data-stu-id="850af-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="850af-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="850af-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="850af-162">Donde _\<FQDN of SQL Server\>_ es el servidor back-end de instalación heredado de una implementación de Enterprise Edition o el FQDN del servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="850af-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

