---
title: Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumen: Leer este tema para aprender a configurar alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: f0bf1a98bb8967a7310844d9aa85d17d4ef4d167
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="59b8d-103">Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="59b8d-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="59b8d-104">**Resumen:** Lea este tema para aprender a configurar alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="59b8d-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="59b8d-105">Skype para Business Server admite varios modos de alta disponibilidad para su nuevo servidores de fondo, incluidos el espejado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="59b8d-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="59b8d-106">Para obtener más información, vea [Planear la alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="59b8d-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="59b8d-107">No se admiten grupos de disponibilidad AlwaysOn con servidores de charla persistente.</span><span class="sxs-lookup"><span data-stu-id="59b8d-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="59b8d-108">Antes de configurar su implementación de Chat persistentes para alta disponibilidad y recuperación ante desastres, asegúrese de que está familiarizado con los conceptos de [Plan para alta disponibilidad y recuperación ante desastres para el servidor de charla persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="59b8d-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="59b8d-109">La solución de recuperación ante desastres para servidor de Chat persistentes se describen en estos temas se basa en un grupo de servidores de charla persistente extendido.</span><span class="sxs-lookup"><span data-stu-id="59b8d-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="59b8d-110">El contenido de planificación describe requisitos de recursos y la topología de grupo extendida que permite persistente Chat Server, incluyendo el uso de reflejos de SQL Server para alta disponibilidad y SQL Server trasvase de registros para alta disponibilidad y recuperación ante desastres recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="59b8d-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="59b8d-111">Usar el Generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="59b8d-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="59b8d-112">En el Generador de topologías, haga lo siguiente para configurar la alta disponibilidad y la recuperación ante desastres del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="59b8d-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="59b8d-113">Agregar el registro envío secundario la base de datos de SQL Server almacena y de las bases de datos de reflejo.</span><span class="sxs-lookup"><span data-stu-id="59b8d-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="59b8d-114">Editar las propiedades del servicio servidor de Chat persistente para:</span><span class="sxs-lookup"><span data-stu-id="59b8d-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="59b8d-115">a.</span><span class="sxs-lookup"><span data-stu-id="59b8d-115">a.</span></span> <span data-ttu-id="59b8d-116">Habilite la creación de reflejo para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="59b8d-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="59b8d-117">b.</span><span class="sxs-lookup"><span data-stu-id="59b8d-117">b.</span></span> <span data-ttu-id="59b8d-118">Agregar el almacén de SQL Server de espejo primario.</span><span class="sxs-lookup"><span data-stu-id="59b8d-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="59b8d-119">c.</span><span class="sxs-lookup"><span data-stu-id="59b8d-119">c.</span></span> <span data-ttu-id="59b8d-120">Habilitar la base de datos de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59b8d-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="59b8d-121">d.</span><span class="sxs-lookup"><span data-stu-id="59b8d-121">d.</span></span> <span data-ttu-id="59b8d-122">Agregar el almacén de SQL Server de secundario de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59b8d-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="59b8d-123">e.</span><span class="sxs-lookup"><span data-stu-id="59b8d-123">e.</span></span> <span data-ttu-id="59b8d-124">Agregar el reflejo de almacén de SQL Server para la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="59b8d-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="59b8d-125">f.</span><span class="sxs-lookup"><span data-stu-id="59b8d-125">f.</span></span> <span data-ttu-id="59b8d-126">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="59b8d-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="59b8d-127">Configurar el trasvase de registros de SQL Server para la base de datos principal del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="59b8d-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="59b8d-128">Con SQL Server Management Studio, conectarse a la instancia de trasvase de registros secundaria de base de datos de servidor de charla persistente y asegúrese de que está ejecutando el agente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59b8d-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="59b8d-129">A continuación, conectarse a la instancia de base de datos principal de Chat persistentes y realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="59b8d-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="59b8d-130">Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="59b8d-131">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="59b8d-132">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="59b8d-133">En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="59b8d-134">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="59b8d-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="59b8d-p110">Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta (por ejemplo: c:\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="59b8d-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="59b8d-137">Si la cuenta de servicio de SQL Server en el servidor principal se ejecuta bajo la cuenta sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="59b8d-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="59b8d-138">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="59b8d-139">Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="59b8d-140">Para personalizar la programación de la instalación, haga clic en **programar**y ajustar la programación del agente de SQL Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="59b8d-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="59b8d-141">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="59b8d-142">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="59b8d-143">Haga clic en **Conectar** y conectarse a la instancia de SQL Server que se ha configurado como el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="59b8d-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="59b8d-144">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.</span><span class="sxs-lookup"><span data-stu-id="59b8d-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="59b8d-145">En la pestaña **Inicializar base de datos secundaria**, elija la opción **Sí, generar una copia de seguridad completa de la base de datos principal y restaurarla en la base de datos secundaria (y crear la base de datos secundaria si no existe)**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="59b8d-p112">En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="59b8d-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="59b8d-148">Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="59b8d-149">Para personalizar la programación de la instalación, haga clic en **programar**y ajustar la programación del agente de SQL Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="59b8d-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="59b8d-150">Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="59b8d-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="59b8d-151">En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="59b8d-152">En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="59b8d-153">Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="59b8d-154">Observe la programación de restauración incluida en el cuadro **Programación** en **Trabajo de restauración**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="59b8d-155">Para personalizar la programación de la instalación, haga clic en **programar**, ajustar la programación del agente de SQL Server según sea necesario y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="59b8d-156">Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="59b8d-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="59b8d-157">En el cuadro de diálogo **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="59b8d-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="59b8d-158">Configurar el trasvase de registros de SQL Server entre el reflejo principal y la base de datos secundaria</span><span class="sxs-lookup"><span data-stu-id="59b8d-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="59b8d-159">Realice los pasos siguientes para el trasvase de registros para continuar si la base de datos principal de Chat persistentes se conmuta a su base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="59b8d-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="59b8d-160">Conmutar manualmente la base de datos de Chat persistentes principal al reflejo.</span><span class="sxs-lookup"><span data-stu-id="59b8d-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="59b8d-161">Esto se hace mediante el Skype para el Shell de administración de servidor empresarial y el cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="59b8d-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="59b8d-162">Con la de SQL Server Management Studio, conectarse a la instancia de reflejo de persistente Chat Server principal.</span><span class="sxs-lookup"><span data-stu-id="59b8d-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="59b8d-163">Asegúrese de que está ejecutando el agente de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59b8d-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="59b8d-164">Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="59b8d-165">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="59b8d-166">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="59b8d-167">En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="59b8d-168">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="59b8d-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="59b8d-p116">Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="59b8d-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="59b8d-171">Si la cuenta de servicio de SQL Server en el servidor principal se ejecuta bajo la cuenta sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="59b8d-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="59b8d-172">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="59b8d-173">Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="59b8d-174">Para personalizar la programación de la instalación, haga clic en **programar**y ajustar la programación del agente de SQL Server, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="59b8d-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="59b8d-175">Use la misma configuración que usa para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="59b8d-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="59b8d-176">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="59b8d-177">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="59b8d-178">Haga clic en **Conectar**, y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="59b8d-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="59b8d-179">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.</span><span class="sxs-lookup"><span data-stu-id="59b8d-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="59b8d-180">En la pestaña **Inicializar base de datos secundaria**, seleccione la opción **No, la base de datos secundaria está inicializada**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="59b8d-p118">En la pestaña **Copiar archivos**, en **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones y haga clic en **Aceptar**. Esta carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="59b8d-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="59b8d-183">Abra la lista desplegable **Incluir configuración** y seleccione **Incluir configuración en una nueva ventana de consulta**.</span><span class="sxs-lookup"><span data-stu-id="59b8d-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="59b8d-184">En la nueva ventana de consulta, en **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="59b8d-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="59b8d-185">Seleccionar y ejecutar la primera mitad de la consulta (consulte el paso 18) a la línea:-- \* \* \* \* \* \* fin: secuencia de comandos que se ejecutará en el principal: \* \* \* \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="59b8d-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="59b8d-186">Es necesario ejecutar manualmente el script porque SQL Server Management Studio no admite varias bases de datos principales en una configuración de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59b8d-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="59b8d-187">Seleccione **Cancelar** para cerrar el panel de configuración del trasvase de archivos de registros y establecer una configuración de trabajo que implemente correctamente el trasvase de archivos de registros a la base de datos principal y reflejada (en caso de conmutación por error). </span><span class="sxs-lookup"><span data-stu-id="59b8d-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="59b8d-188">Manualmente conmutar la base de datos de Chat persistentes principal para el principal.</span><span class="sxs-lookup"><span data-stu-id="59b8d-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="59b8d-189">Esto se hace utilizando el Skype para el Shell de administración de servidor empresarial y el cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="59b8d-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

