---
title: 'Lync Server 2013: configuración del trasvase de registros de SQL Server para la base de datos principal del servidor de chat persistente'
description: 'Lync Server 2013: configurar el trasvase de registros de SQL Server para la base de datos principal del servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72b7e68bd0cb7b9f544b86a15204d3e832692ec1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554266"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="2d707-103">Configurar el trasvase de registros de SQL Server en Lync Server 2013 para la base de datos principal del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2d707-103">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d707-104">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="2d707-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="2d707-105">Mediante SQL Server Management Studio, conéctese a la instancia de base de datos de trasvase de registros secundaria del servidor de chat persistente y asegúrese de que el Agente SQL Server se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="2d707-105">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="2d707-106">Mediante SQL Server Management Studio conectado a la instancia de base de datos principal de chat persistente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2d707-106">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="2d707-107">Asegúrese de que el Agente SQL Server se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="2d707-107">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="2d707-108">Haga clic con el botón secundario en la base de datos de CGM y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2d707-108">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="2d707-109">En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="2d707-109">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="2d707-110">Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.</span><span class="sxs-lookup"><span data-stu-id="2d707-110">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="2d707-111">En **Copias de seguridad de registro de transacciones**, haga clic en **Configuración de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="2d707-111">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="2d707-112">En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad de registro de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="2d707-112">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="2d707-113">Si la carpeta de copia de seguridad se encuentra en el servidor principal, escriba la ruta de acceso local a la carpeta de copia de seguridad en el cuadro **si la carpeta de copia de seguridad se encuentra en el servidor principal, escriba una ruta de acceso local a la carpeta (ejemplo: c: \\ copia de seguridad)** .</span><span class="sxs-lookup"><span data-stu-id="2d707-113">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="2d707-114">(Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).</span><span class="sxs-lookup"><span data-stu-id="2d707-114">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2d707-115">Si la cuenta de servicio de SQL Server en el servidor principal se ejecuta con la cuenta de sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="2d707-115">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="2d707-116">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.</span><span class="sxs-lookup"><span data-stu-id="2d707-116">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="2d707-117">Observe la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="2d707-117">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="2d707-118">Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2d707-118">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="2d707-119">En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d707-119">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="2d707-120">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2d707-120">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="2d707-121">Haga clic en **conectar** y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="2d707-121">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="2d707-122">En el cuadro **Base de datos secundaria**, seleccione la base de datos de **CGM** de la lista.</span><span class="sxs-lookup"><span data-stu-id="2d707-122">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="2d707-123">En la pestaña **inicializar base de datos secundaria** , elija la opción **sí, genere una copia de seguridad completa de la base de datos principal y restáurela en la base de datos secundaria (y cree la base de datos secundaria si no existe)**.</span><span class="sxs-lookup"><span data-stu-id="2d707-123">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="2d707-p103">En la pestaña **Copiar archivos**, en el cuadro \*\*Carpeta de destino de los archivos copiados \*\*, escriba la ruta de acceso de la carpeta en la que deben copiarse las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="2d707-p103">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="2d707-126">Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**.</span><span class="sxs-lookup"><span data-stu-id="2d707-126">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="2d707-127">Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2d707-127">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="2d707-128">Esta programación debe ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2d707-128">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="2d707-129">En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.</span><span class="sxs-lookup"><span data-stu-id="2d707-129">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="2d707-130">En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.</span><span class="sxs-lookup"><span data-stu-id="2d707-130">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="2d707-131">Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.</span><span class="sxs-lookup"><span data-stu-id="2d707-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="2d707-132">Observe la programación de copia de seguridad incluido en el cuadro **Programación** en **Trabajo de restauración**.</span><span class="sxs-lookup"><span data-stu-id="2d707-132">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="2d707-133">Para personalizar la programación de la instalación, haga clic en **programación**, ajuste la programación del Agente SQL Server según sea necesario y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d707-133">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="2d707-134">Esta programación debe ser aproximadamente la misma que la programación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2d707-134">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="2d707-135">En el cuadro de diálogo **Propiedades de base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="2d707-135">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

