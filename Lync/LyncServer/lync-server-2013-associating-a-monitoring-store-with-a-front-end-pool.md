---
title: 'Lync Server 2013: asociar un almacén de supervisión con un grupo de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06cc3c85911b7581117a475d1e390aafdf760ca1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="78910-102">Asociar una tienda de supervisión con un grupo de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78910-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78910-103">_**Última modificación del tema:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="78910-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="78910-104">En Microsoft Lync Server 2013 los datos de supervisión solo se pueden recopilar en grupos front-end que se hayan asociado a un almacén de supervisión, una tarea que normalmente se lleva a cabo define un grupo de servidores front-end en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="78910-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="78910-105">Para asociar un almacén de supervisión con un nuevo grupo de servidores front-end, asegúrese de seleccionar la opción **supervisión (registrar detalles de llamadas y registro de métricas de la calidad de la experiencia)** en la página **seleccionar características** del Asistente para definir un nuevo grupo front-end.</span><span class="sxs-lookup"><span data-stu-id="78910-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="78910-106">Tenga en cuenta que, si selecciona esta opción, también debe especificar un almacén SQL para poder completar el asistente; sin embargo, este almacén no tiene que existir en el momento en que se ejecutó el asistente.</span><span class="sxs-lookup"><span data-stu-id="78910-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="78910-107">Eso significa que puede primero asociar un grupo con una tienda de supervisión y, después, configurar y configurar ese almacén.</span><span class="sxs-lookup"><span data-stu-id="78910-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="78910-108">O bien, asocie un grupo de servidores front-end ya existente a un almacén de supervisión nuevo o diferente ejecutando el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="78910-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="78910-109">Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="78910-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="78910-110">En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="78910-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="78910-p102">En el cuadro de diálogo **Guardar como**, escriba un nombre de archivo para la topología actual y después haga clic en **Guardar**. Más tarde, si tiene problemas con la nueva topología, podrá recuperar y volver a publicar la topología guardada.</span><span class="sxs-lookup"><span data-stu-id="78910-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="78910-113">En el generador de topologías, expanda **Lync Server 2013**, expanda el nombre del sitio que contiene el grupo de servidores front-end y, a continuación, haga clic en expandir **agrupaciones front-end de Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="78910-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="78910-114">Haga clic con el botón secundario en el nombre del grupo de servidores que se asociará al almacén de supervisión y después haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="78910-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="78910-p103">En el cuadro de diálogo **Editar propiedades**, en la pestaña **General**, seleccione la opción **Supervisión (métricas CDR y QoE)** y después seleccione una base de datos SQL Server ya existente en la lista desplegable **Supervisión de SQL Server Store** (o bien haga clic en **Nuevo** para asociar el grupo de servidores a un almacén de base de datos nuevo). Si decide usar un almacén de base de datos nuevo, en el cuadro de diálogo **Definir nuevo almacén SQL**, escriba el nombre de dominio completo del equipo de SQL Server en el cuadro **FQDN de SQL Server**. Si quiere usar la instancia de SQL Server habitual del almacén, seleccione **Instancia predeterminada**, si no, seleccione **Instancia con nombre** y escriba el nombre de la instancia en el cuadro **Instancia con nombre**.</span><span class="sxs-lookup"><span data-stu-id="78910-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="78910-p104">El cuadro de diálogo **Editar propiedades** también le da la opción de crear un reflejo de SQL para la base de datos de supervisión (un reflejo de SQL permite mantener dos copias de las bases de datos de supervisión, una copia almacenada en el PC del almacén de supervisión y otra en el PC del reflejo de SQL). Para habilitar el reflejo, seleccione **Esta instancia de SQL está en una relación de reflejo** y escriba el número de puerto del servidor de reflejo en el cuadro **Número de puerto de reflejo**.</span><span class="sxs-lookup"><span data-stu-id="78910-p104">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer). To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="78910-120">En el cuadro de diálogo **Editar propiedades**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="78910-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="78910-121">Después de asociar el almacén de supervisión al grupo de servidores front-end, publique la nueva topología antes de que los cambios entren en vigor.</span><span class="sxs-lookup"><span data-stu-id="78910-121">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect.</span></span> <span data-ttu-id="78910-122">Para publicar su nueva topología, siga los pasos que se indican en el generador de topología:</span><span class="sxs-lookup"><span data-stu-id="78910-122">To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="78910-123">Haga clic en **Acción**, seleccione **Topología** y haga clic en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="78910-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="78910-124">En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78910-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="78910-125">En la página **Asistente para publicación completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="78910-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="78910-126">Después de publicar la topología, instale la base de datos de supervisión en el equipo que hospedará el almacén de supervisión.</span><span class="sxs-lookup"><span data-stu-id="78910-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="78910-127">La base de datos de supervisión se puede instalar mediante el shell de administración de Lync Server y Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78910-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="78910-128">Para instalar la base de datos de forma local (es decir, para instalar la base de datos en el mismo equipo en el que se ejecuta el shell de administración de Lync Server), inicie el shell de administración en el equipo adecuado, escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="78910-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="78910-129">Al ejecutar el comando anterior, install-CsDatabase leerá la topología actual de Lync Server, determinará qué bases de datos deben instalarse en el equipo local y, a continuación, instalará y configurará automáticamente cada una de esas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="78910-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="78910-130">Para instalar la base de datos en un equipo remoto (es decir, en un equipo que no sea el equipo en el que se ejecute el shell de administración), incluya al menos dos parámetros: el parámetro ConfiguredDatabases y el parámetro SqlServerFqdn.</span><span class="sxs-lookup"><span data-stu-id="78910-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="78910-131">Estos parámetros indican al cmdlet install-CsDatabase para que recupere la topología de Lync Server y, a continuación, instale y configure las bases de datos necesarias en el equipo especificado por el parámetro SqlServerFqdn.</span><span class="sxs-lookup"><span data-stu-id="78910-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="78910-132">El parámetro SqlServerFqdn necesita usar un valor que represente el nombre de dominio completo del equipo donde se vayan a instalar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="78910-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="78910-133">Por ejemplo, este comando instala la base de datos de supervisión en el PC atl-sql-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="78910-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="78910-134">Como alternativa, puede instalar la base de datos de supervisión ejecutando el Asistente para la implementación de Lync Server en el equipo que hospedará el almacén de supervisión.</span><span class="sxs-lookup"><span data-stu-id="78910-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="78910-135">Para ello, inicie sesión en el equipo pertinente y ejecute el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="78910-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="78910-136">Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Asistente de implementación de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="78910-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="78910-137">En el Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="78910-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="78910-138">En la página **implementar** , en **paso 2: configurar o quitar componentes de Lync Server**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="78910-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="78910-139">En el Asistente para la configuración de componentes del servidor de Lync, en la página **Configurar componentes de Lync Server** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78910-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="78910-140">En la página **especificar la ruta de acceso a los MSI** , escriba la ruta de acceso al archivo Ocscore. msi (un archivo incluido con los medios de instalación de Lync Server) y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78910-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="78910-141">En la página **Ejecutar comandos**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="78910-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="78910-142">Para asegurarse de que todos los servicios de Lync Server requeridos se hayan iniciado, haga clic en **Ejecutar** en el título **4: iniciar servicios** de la página **implementar**</span><span class="sxs-lookup"><span data-stu-id="78910-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

