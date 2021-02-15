---
title: Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumen: lea este tema para obtener información sobre cómo configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 0b58f820c1157da8ff36f8dcc68d9e08465bcddc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830630"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="a3742-103">Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a3742-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a3742-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a3742-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a3742-105">Skype Empresarial Server admite varios modos de alta disponibilidad para los servidores back-end, incluida la creación de reflejos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a3742-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="a3742-106">Para obtener más información, consulte [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a3742-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3742-107">Los grupos de disponibilidad AlwaysOn no son compatibles con los servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a3742-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="a3742-108">Antes de configurar la implementación de chat persistente para la alta disponibilidad y la recuperación ante desastres, asegúrese de estar familiarizado con los conceptos de Planeación de alta disponibilidad y recuperación ante desastres para el servidor de chat persistente en [Skype Empresarial Server 2015.](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="a3742-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="a3742-109">La solución de recuperación ante desastres para el servidor de chat persistente descrita en estos temas se basa en un grupo de servidores de chat persistente extendido.</span><span class="sxs-lookup"><span data-stu-id="a3742-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="a3742-110">El contenido de planeación describe los requisitos de recursos y la topología de grupo extendido que permite la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente, incluido el uso de la creación de reflejos de SQL Server para alta disponibilidad y el trasvase de registros de SQL Server para la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="a3742-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="a3742-111">Uso del Generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="a3742-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="a3742-112">En topology Builder, realice los siguientes pasos para configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a3742-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="a3742-113">Agregue las bases de datos reflejadas y la base de datos secundaria de trasvase de registros SQL Server almacenes.</span><span class="sxs-lookup"><span data-stu-id="a3742-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="a3742-114">Edite las propiedades del servicio de servidor de chat persistente para:</span><span class="sxs-lookup"><span data-stu-id="a3742-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="a3742-115">a.</span><span class="sxs-lookup"><span data-stu-id="a3742-115">a.</span></span> <span data-ttu-id="a3742-116">Habilite el reflejo para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a3742-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="a3742-117">b.</span><span class="sxs-lookup"><span data-stu-id="a3742-117">b.</span></span> <span data-ttu-id="a3742-118">Agregue el reflejo principal SQL Server almacén.</span><span class="sxs-lookup"><span data-stu-id="a3742-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="a3742-119">c.</span><span class="sxs-lookup"><span data-stu-id="a3742-119">c.</span></span> <span data-ttu-id="a3742-120">Habilite la base de SQL Server de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="a3742-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="a3742-121">d.</span><span class="sxs-lookup"><span data-stu-id="a3742-121">d.</span></span> <span data-ttu-id="a3742-122">Agregue el SQL Server secundario de trasvase SQL Server registros.</span><span class="sxs-lookup"><span data-stu-id="a3742-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="a3742-123">e.</span><span class="sxs-lookup"><span data-stu-id="a3742-123">e.</span></span> <span data-ttu-id="a3742-124">Agregue el reflejo SQL Server almacén de la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="a3742-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="a3742-125">f.</span><span class="sxs-lookup"><span data-stu-id="a3742-125">f.</span></span> <span data-ttu-id="a3742-126">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="a3742-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="a3742-127">Configurar el trasvase SQL Server registros de la base de datos principal del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a3742-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="a3742-128">Mediante SQL Server Management Studio, conéctese a la instancia de base de datos de trasvase de registros secundaria del servidor de chat persistente y asegúrese de que SQL Server agente está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a3742-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="a3742-129">A continuación, conéctese a la instancia de base de datos principal de chat persistente y realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="a3742-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="a3742-130">Haga clic con el botón secundario en la base de datos de CGM y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a3742-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="a3742-131">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="a3742-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="a3742-132">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="a3742-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="a3742-133">En **Copias de seguridad de registro de transacciones**, haga clic en **Configuración de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="a3742-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="a3742-134">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad de registro de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="a3742-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="a3742-p110">Si la carpeta de copia de seguridad está ubicada en el servidor primario, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor primario, escriba una ruta local a la carpeta (ejemplo: c:\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor primario, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="a3742-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3742-137">Si la cuenta SQL Server servicio del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="a3742-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="a3742-138">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="a3742-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="a3742-139">Observe la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="a3742-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="a3742-140">Para personalizar la programación de la instalación, haga clic en **Programar** y ajuste la programación SQL Server agente según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a3742-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="a3742-141">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3742-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="a3742-142">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a3742-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="a3742-143">Haga **clic** en Conectar y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="a3742-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="a3742-144">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **CGM** de la lista.</span><span class="sxs-lookup"><span data-stu-id="a3742-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="a3742-145">En  la pestaña Inicializar base de datos secundaria, elija la opción Sí, genere una copia de seguridad completa de la base de datos principal y restáurela en la base de datos secundaria (y cree la base de datos secundaria si no **existe).**</span><span class="sxs-lookup"><span data-stu-id="a3742-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="a3742-p112">En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que deben copiarse las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="a3742-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="a3742-148">Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**.</span><span class="sxs-lookup"><span data-stu-id="a3742-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="a3742-149">Para personalizar la programación de la instalación, haga clic en **Programar** y ajuste la programación SQL Server agente según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a3742-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="a3742-150">Esta programación debe ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a3742-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="a3742-151">En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.</span><span class="sxs-lookup"><span data-stu-id="a3742-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="a3742-152">En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.</span><span class="sxs-lookup"><span data-stu-id="a3742-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="a3742-153">Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.</span><span class="sxs-lookup"><span data-stu-id="a3742-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="a3742-154">Observe la programación de copia de seguridad incluido en el cuadro **Programación** en **Trabajo de restauración**.</span><span class="sxs-lookup"><span data-stu-id="a3742-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="a3742-155">Para personalizar la programación de la instalación, haga clic en Programación, ajuste la programación del agente de SQL Server según sea necesario y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3742-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="a3742-156">Esta programación debe ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a3742-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="a3742-157">En el cuadro de diálogo **Propiedades de base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="a3742-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="a3742-158">Configurar el trasvase SQL Server registros entre el reflejo principal y la base de datos secundaria</span><span class="sxs-lookup"><span data-stu-id="a3742-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="a3742-159">Realice los siguientes pasos para que el trasvase de registros continúe si la base de datos de chat persistente principal se ha conversado con la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="a3742-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="a3742-160">Conmutar por error manualmente la base de datos de chat persistente principal al reflejo.</span><span class="sxs-lookup"><span data-stu-id="a3742-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="a3742-161">Esto se realiza mediante el Shell de administración de Skype Empresarial Server y el cmdlet **Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="a3742-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="a3742-162">Con el SQL Server Management Studio, conéctese a la instancia reflejada del servidor de chat persistente principal.</span><span class="sxs-lookup"><span data-stu-id="a3742-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="a3742-163">Asegúrese de que el agente SQL Server está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a3742-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="a3742-164">Haga clic con el botón secundario en la base de datos de CGM y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a3742-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="a3742-165">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="a3742-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="a3742-166">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="a3742-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="a3742-167">En **Copias de seguridad de registro de transacciones**, haga clic en **Configuración de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="a3742-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="a3742-168">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="a3742-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="a3742-p116">Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro  **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta local a la carpeta (ejemplo: c:\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="a3742-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3742-171">Si la cuenta SQL Server servicio del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="a3742-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="a3742-172">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="a3742-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="a3742-173">Observe la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="a3742-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="a3742-174">Para personalizar la programación de la instalación, haga clic en **Programar** y ajuste la programación SQL Server agente, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a3742-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3742-175">Use la misma configuración que usa para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="a3742-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="a3742-176">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3742-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="a3742-177">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a3742-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="a3742-178">Haga clic en **Conectar**, y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="a3742-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="a3742-179">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **CGM** de la lista.</span><span class="sxs-lookup"><span data-stu-id="a3742-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="a3742-180">En la pestaña **Inicializar base de datos secundaria**, seleccione la opción **No, la base de datos secundaria está inicializada**.</span><span class="sxs-lookup"><span data-stu-id="a3742-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="a3742-p118">En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que deben copiarse las copias de seguridad de los registros de transacciones y haga clic en **Aceptar**. Esa carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="a3742-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="a3742-183">Abra la lista desplegable **Incluir configuración** y seleccione **Incluir configuración en una nueva ventana de consulta**.</span><span class="sxs-lookup"><span data-stu-id="a3742-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="a3742-184">En la nueva ventana de consulta, en **Propiedades de base de datos**, haga clic en **Aceptar** para comenzar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="a3742-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="a3742-185">Seleccione y ejecute la primera mitad de la consulta (vea el paso 18) hasta la línea: -- End: Script que se ejecutará \* \* \* \* \* \* en primary: \* \* \* \* \* \* .</span><span class="sxs-lookup"><span data-stu-id="a3742-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a3742-186">La ejecución manual de este script es necesaria porque SQL Server Management Studio no admite varias bases de datos principales en una SQL Server de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="a3742-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="a3742-187">Seleccione **Cancelar** para cerrar el panel de configuración de envío del archivo de registro y establecer una configuración de trabajo que implemente correctamente el envío del archivo de registro a la base de datos principal y reflejada (en caso de conmutación por error).</span><span class="sxs-lookup"><span data-stu-id="a3742-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="a3742-188">Conmutación por recuperación manual de la base de datos de chat persistente principal a la principal.</span><span class="sxs-lookup"><span data-stu-id="a3742-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="a3742-189">Esto se realiza mediante el Shell de administración de Skype Empresarial Server y el cmdlet **Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="a3742-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

