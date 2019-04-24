---
title: Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: 5c53652cf5084b5a6c021c38f71f1cccc0322efa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225493"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="edbbb-103">Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="edbbb-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="edbbb-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar la alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="edbbb-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="edbbb-105">Skype para Business Server admite varios modos de alta disponibilidad para los servidores Back-End, incluidas la creación de reflejo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="edbbb-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="edbbb-106">Para más información, vea [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="edbbb-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="edbbb-107">Grupos de disponibilidad AlwaysOn no son compatibles con servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="edbbb-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="edbbb-108">Antes de configurar la implementación de Chat persistente de alta disponibilidad y recuperación ante desastres, asegúrese de que está familiarizado con los conceptos de [planeación de alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="edbbb-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="edbbb-109">La solución de recuperación ante desastres para servidor de Chat persistente que se describen en estos temas se basa en un grupo de servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="edbbb-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="edbbb-110">El contenido de planeación describe los requisitos de recursos y la topología de grupo de servidores expandida que permite una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente, incluido el uso de la creación de reflejos de SQL Server de alta disponibilidad y para de trasvase de registros de SQL Server recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="edbbb-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="edbbb-111">Usar el Generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="edbbb-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="edbbb-112">En el Generador de topologías, haga lo siguiente para configurar la alta disponibilidad y la recuperación ante desastres del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="edbbb-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="edbbb-113">Agregue las bases de datos de reflejo y el registro trasvase de registros base de datos secundaria que almacenes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="edbbb-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="edbbb-114">Editar las propiedades del servicio servidor de Chat persistente para:</span><span class="sxs-lookup"><span data-stu-id="edbbb-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="edbbb-115">a.</span><span class="sxs-lookup"><span data-stu-id="edbbb-115">a.</span></span> <span data-ttu-id="edbbb-116">Habilite la creación de reflejo para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="edbbb-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="edbbb-117">b.</span><span class="sxs-lookup"><span data-stu-id="edbbb-117">b.</span></span> <span data-ttu-id="edbbb-118">Agregue el almacén de SQL Server de reflejo principal.</span><span class="sxs-lookup"><span data-stu-id="edbbb-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="edbbb-119">c.</span><span class="sxs-lookup"><span data-stu-id="edbbb-119">c.</span></span> <span data-ttu-id="edbbb-120">Habilitar la base de datos de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="edbbb-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="edbbb-121">d.</span><span class="sxs-lookup"><span data-stu-id="edbbb-121">d.</span></span> <span data-ttu-id="edbbb-122">Agregue el almacén de SQL Server secundario trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="edbbb-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="edbbb-123">e.</span><span class="sxs-lookup"><span data-stu-id="edbbb-123">e.</span></span> <span data-ttu-id="edbbb-124">Agregar el reflejo del almacén de SQL Server para la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="edbbb-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="edbbb-125">f.</span><span class="sxs-lookup"><span data-stu-id="edbbb-125">f.</span></span> <span data-ttu-id="edbbb-126">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="edbbb-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="edbbb-127">Configurar el trasvase de registros de SQL Server para la base de datos principal del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="edbbb-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="edbbb-128">Con SQL Server Management Studio, conéctese a la instancia de trasvase de registros secundaria de base de datos de servidor de Chat persistente y asegúrese de que el Agente SQL Server se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="edbbb-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="edbbb-129">A continuación, conéctese a la instancia de base de datos principal de Chat persistente y realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="edbbb-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="edbbb-130">Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="edbbb-131">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="edbbb-132">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="edbbb-133">En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="edbbb-134">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="edbbb-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="edbbb-p110">Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta (por ejemplo: c:\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="edbbb-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="edbbb-137">Si la cuenta de servicio de SQL Server en el servidor principal se ejecuta bajo la cuenta sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="edbbb-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="edbbb-138">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="edbbb-139">Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="edbbb-140">Para personalizar la programación de la instalación, haga clic en **programar**y ajustar la programación del Agente SQL Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="edbbb-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="edbbb-141">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="edbbb-142">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="edbbb-143">Haga clic en **Conectar** y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="edbbb-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="edbbb-144">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.</span><span class="sxs-lookup"><span data-stu-id="edbbb-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="edbbb-145">En la pestaña **Inicializar base de datos secundaria**, elija la opción **Sí, generar una copia de seguridad completa de la base de datos principal y restaurarla en la base de datos secundaria (y crear la base de datos secundaria si no existe)**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="edbbb-p112">En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="edbbb-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="edbbb-148">Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="edbbb-149">Para personalizar la programación de la instalación, haga clic en **programar**y ajustar la programación del Agente SQL Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="edbbb-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="edbbb-150">Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="edbbb-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="edbbb-151">En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="edbbb-152">En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="edbbb-153">Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="edbbb-154">Observe la programación de restauración incluida en el cuadro **Programación** en **Trabajo de restauración**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="edbbb-155">Para personalizar la programación de la instalación, haga clic en **programar**, ajuste la programación del Agente SQL Server según sea necesario y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="edbbb-156">Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="edbbb-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="edbbb-157">En el cuadro de diálogo **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="edbbb-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="edbbb-158">Configurar el trasvase de registros de SQL Server entre el reflejo principal y la base de datos secundaria</span><span class="sxs-lookup"><span data-stu-id="edbbb-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="edbbb-159">Realice los pasos siguientes para el trasvase de registros para continuar si la base de datos principal de Chat persistente se conmuta por error a su base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="edbbb-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="edbbb-160">Conmutación por error manual la base de datos de Chat persistente principal del reflejo.</span><span class="sxs-lookup"><span data-stu-id="edbbb-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="edbbb-161">Esto se realiza mediante la Skype para el cmdlet **Invoke-CsDatabaseFailover** y el Shell de administración de servidor de negocio.</span><span class="sxs-lookup"><span data-stu-id="edbbb-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="edbbb-162">Uso de SQL Server Management Studio, conéctese a la instancia de reflejo principal de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="edbbb-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="edbbb-163">Asegúrese de que el Agente SQL Server se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="edbbb-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="edbbb-164">Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="edbbb-165">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="edbbb-166">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="edbbb-167">En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="edbbb-168">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="edbbb-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="edbbb-p116">Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="edbbb-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="edbbb-171">Si la cuenta de servicio de SQL Server en el servidor principal se ejecuta bajo la cuenta sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="edbbb-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="edbbb-172">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="edbbb-173">Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="edbbb-174">Para personalizar la programación de la instalación, haga clic en **programar**y ajustar la programación del Agente SQL Server, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="edbbb-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="edbbb-175">Use la misma configuración que usa para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="edbbb-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="edbbb-176">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="edbbb-177">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="edbbb-178">Haga clic en **Conectar**, y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="edbbb-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="edbbb-179">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.</span><span class="sxs-lookup"><span data-stu-id="edbbb-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="edbbb-180">En la pestaña **Inicializar base de datos secundaria**, seleccione la opción **No, la base de datos secundaria está inicializada**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="edbbb-p118">En la pestaña **Copiar archivos**, en **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones y haga clic en **Aceptar**. Esta carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="edbbb-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="edbbb-183">Abra la lista desplegable **Incluir configuración** y seleccione **Incluir configuración en una nueva ventana de consulta**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="edbbb-184">En la nueva ventana de consulta, en **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="edbbb-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="edbbb-185">Seleccione y ejecute la primera mitad de la consulta (consulte el paso 18) copia de seguridad a la línea:-- \* \* \* \* \* \* End: secuencia de comandos que se ejecutará en el principal: \* \* \* \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="edbbb-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="edbbb-186">Es necesario ejecutar manualmente este script, debido a que SQL Server Management Studio no admite varias bases de datos principales en una configuración de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="edbbb-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="edbbb-187">Seleccione **Cancelar** para cerrar el panel de configuración del trasvase de archivos de registros y establecer una configuración de trabajo que implemente correctamente el trasvase de archivos de registros a la base de datos principal y reflejada (en caso de conmutación por error). </span><span class="sxs-lookup"><span data-stu-id="edbbb-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="edbbb-188">Manualmente conmutar por recuperación la base de datos de Chat persistente principal a la principal.</span><span class="sxs-lookup"><span data-stu-id="edbbb-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="edbbb-189">Esto se realiza mediante la Skype para Shell de administración de servidor empresarial y el cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="edbbb-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

