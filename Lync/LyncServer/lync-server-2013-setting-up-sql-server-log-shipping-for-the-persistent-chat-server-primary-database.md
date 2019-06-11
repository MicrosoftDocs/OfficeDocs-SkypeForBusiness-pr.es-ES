---
title: 'Lync Server 2013: Configurar registro de transacciones de SQL Server para base de datos principal del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0de2285d77ba2228b90d244c841efc0b986bf454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="97fa9-102">Configurar registro de transacciones de SQL Server para base de datos principal del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97fa9-102">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97fa9-103">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="97fa9-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="97fa9-104">Con SQL Server Management Studio, conéctese a la instancia de base de datos de trasvase de registros secundaria del servidor de chat persistente y asegúrese de que el Agente SQL Server se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="97fa9-104">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="97fa9-105">Con SQL Server Management Studio conectado a la instancia de base de datos principal de chat persistente, realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="97fa9-105">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="97fa9-106">Asegúrese de que el Agente SQL Server se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="97fa9-106">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="97fa9-107">Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-107">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="97fa9-108">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-108">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="97fa9-109">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-109">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="97fa9-110">En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-110">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="97fa9-111">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="97fa9-111">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="97fa9-112">Si la carpeta de copia de seguridad se encuentra en el servidor principal, escriba la ruta de acceso local a la carpeta de copia de seguridad en el cuadro **si la carpeta de copia de seguridad se encuentra en el servidor principal,\\escriba una ruta de acceso local a la carpeta (ejemplo: c: copia de seguridad)** .</span><span class="sxs-lookup"><span data-stu-id="97fa9-112">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="97fa9-113">(Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="97fa9-113">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="97fa9-114">Si la cuenta de servicio de SQL Server del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="97fa9-114">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="97fa9-115">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-115">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="97fa9-116">Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-116">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="97fa9-117">Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="97fa9-117">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="97fa9-118">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-118">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="97fa9-119">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-119">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="97fa9-120">Haga clic en **conectar** y conéctese a la instancia de SQL Server que haya configurado como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="97fa9-120">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="97fa9-121">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.</span><span class="sxs-lookup"><span data-stu-id="97fa9-121">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="97fa9-122">En la pestaña **Inicializar base de datos secundaria**, elija la opción **Sí, generar una copia de seguridad completa de la base de datos principal y restaurarla en la base de datos secundaria (y crear la base de datos secundaria si no existe)**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-122">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="97fa9-p103">En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="97fa9-p103">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="97fa9-125">Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="97fa9-126">Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="97fa9-126">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="97fa9-127">Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="97fa9-127">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="97fa9-128">En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="97fa9-129">En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-129">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="97fa9-130">Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-130">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="97fa9-131">Observe la programación de restauración incluida en el cuadro **Programación** en **Trabajo de restauración**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-131">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="97fa9-132">Para personalizar la programación de la instalación, haga clic en **programación**, ajuste la programación del Agente SQL Server según sea necesario y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97fa9-132">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="97fa9-133">Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="97fa9-133">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="97fa9-134">En el cuadro de diálogo **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="97fa9-134">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

