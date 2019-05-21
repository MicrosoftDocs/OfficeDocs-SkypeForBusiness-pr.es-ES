---
title: Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial Server 2015.'
ms.openlocfilehash: 152797229dc02bfcd1991a9ac6f67370c9154593
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282297"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="cbb6a-103">Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="cbb6a-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cbb6a-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cbb6a-105">Skype empresarial Server admite varios modos de alta disponibilidad para los servidores back-end, incluyendo la creación de reflejos de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="cbb6a-106">Para más información, vea [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="cbb6a-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cbb6a-107">Los grupos de disponibilidad AlwaysOn no son compatibles con los servidores de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="cbb6a-108">Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cbb6a-109">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="cbb6a-110">Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="cbb6a-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="cbb6a-111">Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cbb6a-112">Antes de configurar la implementación de chat persistente para una alta disponibilidad y recuperación ante desastres, asegúrese de que está familiarizado con los conceptos de [plan de alta disponibilidad y recuperación ante desastres para el servidor de chat persistente en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="cbb6a-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="cbb6a-113">La solución de recuperación ante desastres para el servidor de chat persistente que se describe en estos temas se ha creado en un grupo de servidores de chat persistente ampliado.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="cbb6a-114">En el contenido de planeación se describen los requisitos de recursos y la topología de grupo expandida que permite una alta disponibilidad y recuperación ante desastres para el servidor de chat persistente, incluyendo el reflejo de SQL Server para una mayor disponibilidad y el trasvase de registros de SQL Server para recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="cbb6a-115">Usar el Generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="cbb6a-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="cbb6a-116">En el Generador de topologías, haga lo siguiente para configurar la alta disponibilidad y la recuperación ante desastres del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="cbb6a-117">Agregue las bases de datos reflejadas y de trasvase de registros que SQL Server almacena.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="cbb6a-118">Edite las propiedades del servicio del servidor de chat persistentes en:</span><span class="sxs-lookup"><span data-stu-id="cbb6a-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="cbb6a-119">a.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-119">a.</span></span> <span data-ttu-id="cbb6a-120">Habilite la creación de reflejo para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="cbb6a-121">b.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-121">b.</span></span> <span data-ttu-id="cbb6a-122">Agregue el almacén de SQL Server de reflejo principal.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="cbb6a-123">c.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-123">c.</span></span> <span data-ttu-id="cbb6a-124">Habilite la base de datos de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="cbb6a-125">d.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-125">d.</span></span> <span data-ttu-id="cbb6a-126">Agregue el almacén de SQL Server secundario de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="cbb6a-127">&.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-127">e.</span></span> <span data-ttu-id="cbb6a-128">Agregue el reflejo de la tienda SQL Server para la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="cbb6a-129">f.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-129">f.</span></span> <span data-ttu-id="cbb6a-130">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="cbb6a-131">Configurar el trasvase de registros de SQL Server para la base de datos principal del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="cbb6a-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="cbb6a-132">Con SQL Server Management Studio, conéctese a la instancia de base de datos de trasvase de registros secundaria del servidor de chat persistente y asegúrese de que el Agente SQL Server se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="cbb6a-133">A continuación, conéctese a la instancia principal de la base de datos de chat persistente y realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="cbb6a-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="cbb6a-134">Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="cbb6a-135">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="cbb6a-136">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="cbb6a-137">En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="cbb6a-138">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="cbb6a-p111">Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta (por ejemplo: c:\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="cbb6a-p111">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cbb6a-141">Si la cuenta de servicio de SQL Server del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="cbb6a-142">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="cbb6a-143">Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="cbb6a-144">Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="cbb6a-145">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="cbb6a-146">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="cbb6a-147">Haga clic en **conectar** y conéctese a la instancia de SQL Server que haya configurado como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="cbb6a-148">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="cbb6a-149">En la pestaña **Inicializar base de datos secundaria**, elija la opción **Sí, generar una copia de seguridad completa de la base de datos principal y restaurarla en la base de datos secundaria (y crear la base de datos secundaria si no existe)**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="cbb6a-p113">En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-p113">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="cbb6a-152">Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="cbb6a-153">Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="cbb6a-154">Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="cbb6a-155">En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="cbb6a-156">En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="cbb6a-157">Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="cbb6a-158">Observe la programación de restauración incluida en el cuadro **Programación** en **Trabajo de restauración**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="cbb6a-159">Para personalizar la programación de la instalación, haga clic en **programación**, ajuste la programación del Agente SQL Server según sea necesario y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="cbb6a-160">Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="cbb6a-161">En el cuadro de diálogo **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="cbb6a-162">Configurar el trasvase de registros de SQL Server entre el reflejo principal y la base de datos secundaria</span><span class="sxs-lookup"><span data-stu-id="cbb6a-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="cbb6a-163">Siga estos pasos para que el trasvase de registros continúe si la base de datos de chat principal persistente se conmuta por error a su base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="cbb6a-164">Failover manual de la base de datos principal de chat persistente en el reflejo.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="cbb6a-165">Esto se realiza mediante el shell de administración de Skype empresarial Server y el cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="cbb6a-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="cbb6a-166">Con SQL Server Management Studio, conéctese a la instancia principal de reflejo del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="cbb6a-167">Asegúrese de que el Agente SQL Server se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="cbb6a-168">Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="cbb6a-169">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="cbb6a-170">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="cbb6a-171">En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="cbb6a-172">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="cbb6a-p117">Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="cbb6a-p117">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cbb6a-175">Si la cuenta de servicio de SQL Server del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="cbb6a-176">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="cbb6a-177">Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="cbb6a-178">Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cbb6a-179">Use la misma configuración que usa para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="cbb6a-180">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="cbb6a-181">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="cbb6a-182">Haga clic en **Conectar**, y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="cbb6a-183">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="cbb6a-184">En la pestaña **Inicializar base de datos secundaria**, seleccione la opción **No, la base de datos secundaria está inicializada**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="cbb6a-p119">En la pestaña **Copiar archivos**, en **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones y haga clic en **Aceptar**. Esta carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-p119">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="cbb6a-187">Abra la lista desplegable **Incluir configuración** y seleccione **Incluir configuración en una nueva ventana de consulta**.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="cbb6a-188">En la nueva ventana de consulta, en **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="cbb6a-189">Seleccione y ejecute la primera mitad de la consulta (vea el paso 18) hasta la línea:-- \* \* \* \* \* \* end: script \* \* \* \* \* \*que se ejecutará en Primary:.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cbb6a-190">La ejecución manual de este script es necesaria porque SQL Server Management Studio no admite varias bases de datos principales en una configuración de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="cbb6a-191">Seleccione **Cancelar** para cerrar el panel de configuración del trasvase de archivos de registros y establecer una configuración de trabajo que implemente correctamente el trasvase de archivos de registros a la base de datos principal y reflejada (en caso de conmutación por error). </span><span class="sxs-lookup"><span data-stu-id="cbb6a-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="cbb6a-192">Failback manual de la base de datos principal de chat persistente al principal.</span><span class="sxs-lookup"><span data-stu-id="cbb6a-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="cbb6a-193">Esto se realiza mediante el shell de administración de Skype empresarial Server y el cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="cbb6a-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

