---
title: Mover el servidor de Administración Central
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de migrar a Skype para Business Server 2019, debe mover el servidor de Administración Central para la Skype para profesionales de 2019 Front-End Server o grupo de servidores, para poder quitar el servidor heredado.
ms.openlocfilehash: dc85548a3c81e55267bc0ed3a32e53860e4bce09
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894750"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="89373-103">Mover el servidor de Administración Central heredado a Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="89373-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="89373-104">Después de migrar a Skype para Business Server 2019 y poder quitar el servidor heredado, debe mover el servidor de Administración Central para la Skype para profesionales de 2019 Front-End Server o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="89373-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="89373-105">El servidor de Administración Central es un sistema de única réplica maestro o varios, donde se mantiene la copia de lectura y escritura de la base de datos por el servidor Front-End que contiene el servidor de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="89373-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="89373-106">Cada equipo en la topología, incluido el servidor Front-End que contiene el servidor de Administración Central, tiene una copia de solo lectura de los datos del almacén de Administración Central en la base de datos de SQL (denominado RTCLOCAL de forma predeterminada) instalado en el equipo durante el programa de instalación y despliegue.</span><span class="sxs-lookup"><span data-stu-id="89373-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="89373-107">La base de datos local recibe actualizaciones de réplica mediante el Skype para profesionales agente de Replicador de réplica de servidor que se ejecuta como un servicio en todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="89373-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="89373-108">El nombre de la base de datos real en el servidor de Administración Central y la réplica local es XDS, que se compone de los archivos xds.mdf y xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="89373-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="89373-109">Un punto de control de servicio (SCP) en servicios de dominio de Active Directory al que hace referencia la ubicación de la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="89373-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="89373-110">Todas las herramientas que use el servidor de Administración Central para administrar y configurar Skype para Business Server usa el SCP para encontrar el almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="89373-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="89373-111">Una vez que haya movido correctamente el servidor de Administración Central, debe quitar las bases de datos del servidor de Administración Central desde el servidor original de Front-End.</span><span class="sxs-lookup"><span data-stu-id="89373-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="89373-112">Para obtener información acerca de cómo quitar las bases de datos del servidor de Administración Central, vea [quitar la base de datos de SQL Server para un grupo de servidores Front-End](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="89373-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="89373-113">Use el cmdlet de Windows PowerShell **Move-CsManagementServer** en el Skype para Shell de administración de servidor empresarial para mover la base de datos de la base de datos de SQL Server install heredado para la Skype para la base de datos de Business Server 2019 SQL Server y, a continuación, actualice el SCP para que apunte a la Skype para la ubicación del servidor de Administración Central de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="89373-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="89373-114">Use los procedimientos de esta sección para preparar el Skype para servidores Front-End de Business Server 2019 antes de mover el servidor de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="89373-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="89373-115">Para preparar un grupo de servidores Front-End de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="89373-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="89373-116">En Skype para el grupo de servidores Front-End de Business Server 2019 Enterprise Edition donde desea reubicar el servidor de Administración Central, inicie sesión en el equipo donde está instalado el Skype para Shell de administración de servidor empresarial como un miembro de la \*\*RTCUniversalServerAdmins \*\*grupo.</span><span class="sxs-lookup"><span data-stu-id="89373-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="89373-117">También debe tener permisos y derechos de usuario de sysadmin de base de datos de SQL Server en la base de datos donde desea instalar el almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="89373-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="89373-118">Abra el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="89373-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="89373-119">Para crear el nuevo almacén de Administración Central en el Skype para base de datos de Business Server 2019 SQL Server, en el Skype para Shell de administración de servidor empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="89373-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="89373-120">Confirme que el estado del servicio de **Skype para Business Server front-end** es **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="89373-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="89373-121">Para preparar una edición Standard servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="89373-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="89373-122">En Skype para profesionales de 2019 Standard Edition Front-End Server donde desea reubicar el servidor de Administración Central, inicie sesión en el equipo donde está instalado el Skype para Shell de administración de servidor empresarial como un miembro de la \*\*RTCUniversalServerAdmins \*\*grupo.</span><span class="sxs-lookup"><span data-stu-id="89373-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="89373-123">Abra el Skype para el Asistente para la implementación de servidor de negocio.</span><span class="sxs-lookup"><span data-stu-id="89373-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="89373-124">Skype para el Asistente para la implementación de Business Server, haga clic en **Preparar el primer servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="89373-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="89373-125">En la página **Ejecución de comandos** , SQL Server Express está instalado como el servidor de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="89373-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="89373-126">Se crean las reglas de firewall necesarias.</span><span class="sxs-lookup"><span data-stu-id="89373-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="89373-127">Una vez completada la instalación de la base de datos y el software necesario como requisito previo, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="89373-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89373-128">La instalación inicial puede tardar algún tiempo sin actualizaciones visible a la pantalla de resumen de resultados de comando.</span><span class="sxs-lookup"><span data-stu-id="89373-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="89373-129">Esto es debido a la instalación de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="89373-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="89373-130">Si necesita supervisar la instalación de la base de datos, use el Administrador de tareas para supervisar el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="89373-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="89373-131">Para crear el nuevo almacén de Administración Central en el Skype para profesionales 2019 servidor Standard Edition Server Front-End, en la Skype para Shell de administración de servidor empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="89373-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="89373-132">Confirme que el estado del servicio de **Skype para Business Server front-end** es **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="89373-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="89373-133">Para mover que el heredado instala el servidor de Administración Central en Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="89373-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="89373-134">En Skype para servidor Business Server 2019 que será el servidor de Administración Central, inicie sesión en el equipo donde está instalado el Skype para Shell de administración de servidor empresarial como un miembro del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="89373-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="89373-135">También debe tener los derechos de usuario de administrador de base de datos de SQL Server y los permisos.</span><span class="sxs-lookup"><span data-stu-id="89373-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="89373-136">Abra Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="89373-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="89373-137">En Skype para Shell de administración de servidor empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="89373-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="89373-138">Si `Enable-CsTopology` no es correcta, resolver el problema que impide que el comando completar antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="89373-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="89373-139">Si **Enable-CsTopology** no se realiza correctamente, el movimiento se producirá un error y puede dejar la topología en un estado donde no hay ningún almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="89373-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="89373-140">En el Skype para grupo de negocio 2019 Front-End Server o Front-End, de la Skype para Shell de administración de servidor empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="89373-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Move-CsManagementServer
   ```

5. <span data-ttu-id="89373-141">Skype para Shell de administración de servidor empresarial muestra los servidores, almacenes de archivos, los almacenes de base de datos y los puntos de conexión de servicio de estado actual y el estado propuesto.</span><span class="sxs-lookup"><span data-stu-id="89373-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="89373-142">Lea detenidamente la información y confirmar que esta es la prevista origen y destino.</span><span class="sxs-lookup"><span data-stu-id="89373-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="89373-143">Escriba **Y** para continuar, o **N** para detener el movimiento.</span><span class="sxs-lookup"><span data-stu-id="89373-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="89373-144">Revise las advertencias o errores generados por el comando **Move-CsManagementServer** y resolverlos.</span><span class="sxs-lookup"><span data-stu-id="89373-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="89373-145">En Skype para Business Server 2019 server, abra el Skype para el Asistente para la implementación de servidor de negocio.</span><span class="sxs-lookup"><span data-stu-id="89373-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="89373-146">En Skype para el Asistente para la implementación de Business Server, haga clic en **instalar o actualización de Skype para el sistema de servidor empresarial**, haga clic en **paso 2: el programa de instalación o quitar Skype para los componentes de servidor empresariales**, haga clic en **siguiente**, revise el resumen y, a continuación, haga clic en Finalizar \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="89373-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="89373-147">En el heredado instalar el servidor, abra el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="89373-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="89373-148">En Skype para el Asistente para la implementación de Business Server, haga clic en **instalar o actualización de Skype para el sistema de servidor empresarial**, haga clic en **paso 2: el programa de instalación o quitar Skype para los componentes de servidor empresariales**, haga clic en **siguiente**, revise el resumen y, a continuación, haga clic en Finalizar \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="89373-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="89373-149">Reinicie el Skype para server Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="89373-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="89373-150">Esto es necesario debido a un cambio de pertenencia a grupo para tener acceso a la base de datos del servidor de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="89373-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="89373-151">Para confirmar que la replicación con la nueva Administración Central se está produciendo almacén, en la Skype para Shell de administración de servidor empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="89373-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="89373-152">La replicación puede tardar algún tiempo en actualizar todas las réplicas.</span><span class="sxs-lookup"><span data-stu-id="89373-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="89373-153">Para quitar archivos de almacén de Administración Central de instalación heredados después de un movimiento</span><span class="sxs-lookup"><span data-stu-id="89373-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="89373-154">En el heredado instalar el servidor, inicie sesión en el equipo donde está instalado el Skype para Shell de administración de servidor empresarial como un miembro del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="89373-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="89373-155">También debe tener los derechos de usuario de administrador de base de datos de SQL Server y los permisos.</span><span class="sxs-lookup"><span data-stu-id="89373-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="89373-156">Abra Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="89373-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="89373-157">No continúe con la eliminación de los archivos de base de datos anterior hasta que la replicación está completa y es estable.</span><span class="sxs-lookup"><span data-stu-id="89373-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="89373-158">Si quita los archivos antes de completar la replicación, se interrumpen el proceso de replicación y dejar el servidor de Administración Central que se movió recientemente en un estado desconocido.</span><span class="sxs-lookup"><span data-stu-id="89373-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="89373-159">Use el cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="89373-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="89373-160">Para quitar los archivos de base de datos del almacén de Administración Central de la instalación heredada servidor de Administración Central, escriba:</span><span class="sxs-lookup"><span data-stu-id="89373-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="89373-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="89373-161">For example:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="89373-162">Donde la _ \<FQDN de SQL Server\> _ es puede ser el heredado instalar servidor Back-End en una implementación de Enterprise Edition o el FQDN del servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="89373-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

