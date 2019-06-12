---
title: 'Lync Server 2013: Configuración del envío de registro de SQL Server entre el reflejo principal y la base de datos secundaria de envío de registro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a><span data-ttu-id="e3845-102">Configuración del envío de registro de SQL Server entre el reflejo principal y la base de datos secundaria de envío de registro en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3845-102">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3845-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e3845-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e3845-104">Siga estos pasos para que el trasvase de registros continúe si la base de datos de chat principal persistente se conmuta por error a su base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="e3845-104">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>

1.  <span data-ttu-id="e3845-105">Failover manual de la base de datos principal de chat persistente en el reflejo.</span><span class="sxs-lookup"><span data-stu-id="e3845-105">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="e3845-106">Esto se realiza mediante el shell de administración de Lync Server y el cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="e3845-106">This is done by using the Lync Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="e3845-107">Para obtener más información, consulte "uso de los cmdlets del shell de administración de Lync Server" en [implementar el reflejo SQL para back-end servidor de alta disponibilidad en Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="e3845-107">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

2.  <span data-ttu-id="e3845-108">Con SQL Server Management Studio, conéctese a la instancia principal de reflejo del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e3845-108">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>

3.  <span data-ttu-id="e3845-109">Asegúrese de que el Agente SQL Server se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="e3845-109">Be sure that the SQL Server Agent is running.</span></span>

4.  <span data-ttu-id="e3845-110">Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e3845-110">Right-click the mgc database, and then click **Properties**.</span></span>

5.  <span data-ttu-id="e3845-111">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="e3845-111">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

6.  <span data-ttu-id="e3845-112">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="e3845-112">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

7.  <span data-ttu-id="e3845-113">En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e3845-113">Under **Transaction log backups**, click **Backup Settings**.</span></span>

8.  <span data-ttu-id="e3845-114">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="e3845-114">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>

9.  <span data-ttu-id="e3845-p102">Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="e3845-p102">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e3845-117">Si la cuenta de servicio de SQL Server del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="e3845-117">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

10. <span data-ttu-id="e3845-118">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="e3845-118">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

11. <span data-ttu-id="e3845-119">Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e3845-119">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="e3845-120">Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e3845-120">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e3845-121">Use la misma configuración que usa para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="e3845-121">Use the same settings that you used for the primary database.</span></span>

    
    </div>

12. <span data-ttu-id="e3845-122">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e3845-122">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>

13. <span data-ttu-id="e3845-123">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e3845-123">Under **Secondary server instances and databases**, click **Add**.</span></span>

14. <span data-ttu-id="e3845-124">Haga clic en **Conectar**, y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="e3845-124">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

15. <span data-ttu-id="e3845-125">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.</span><span class="sxs-lookup"><span data-stu-id="e3845-125">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

16. <span data-ttu-id="e3845-126">En la pestaña **Inicializar base de datos secundaria**, seleccione la opción **No, la base de datos secundaria está inicializada**.</span><span class="sxs-lookup"><span data-stu-id="e3845-126">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>

17. <span data-ttu-id="e3845-p104">En la pestaña **Copiar archivos**, en **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones y haga clic en **Aceptar**. Esta carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="e3845-p104">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>

18. <span data-ttu-id="e3845-129">Abra la lista desplegable **Incluir configuración** y seleccione **Incluir configuración en una nueva ventana de consulta**.</span><span class="sxs-lookup"><span data-stu-id="e3845-129">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>

19. <span data-ttu-id="e3845-130">En la nueva ventana de consulta, en **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="e3845-130">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>

20. <span data-ttu-id="e3845-131">Seleccione y ejecute la primera mitad de la consulta (vea el paso 18) hasta la línea:-- \* \* \* \* \* \* end: script \* \* \* \* \* \*que se ejecutará en Primary:.</span><span class="sxs-lookup"><span data-stu-id="e3845-131">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e3845-132">La ejecución manual de este script es necesaria porque SQL Server Management Studio no admite varias bases de datos principales en una configuración de trasvase de registros de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e3845-132">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span>

    
    </div>

21. <span data-ttu-id="e3845-133">Seleccione **Cancelar** para cerrar el panel de configuración del trasvase de archivos de registros y establecer una configuración de trabajo que implemente correctamente el trasvase de archivos de registros a la base de datos principal y reflejada (en caso de conmutación por error). </span><span class="sxs-lookup"><span data-stu-id="e3845-133">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>

22. <span data-ttu-id="e3845-134">Failback manual de la base de datos principal de chat persistente al principal.</span><span class="sxs-lookup"><span data-stu-id="e3845-134">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="e3845-135">Esto se realiza mediante el shell de administración de Lync Server y el cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="e3845-135">This is done by using the Lync Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="e3845-136">Para obtener más información, consulte "uso de los cmdlets del shell de administración de Lync Server" en [implementar el reflejo SQL para back-end servidor de alta disponibilidad en Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="e3845-136">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e3845-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3845-137">See Also</span></span>


[<span data-ttu-id="e3845-138">Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3845-138">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[<span data-ttu-id="e3845-139">Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3845-139">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

