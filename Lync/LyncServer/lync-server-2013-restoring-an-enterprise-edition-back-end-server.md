---
title: 'Lync Server 2013: restauración de un servidor back-end de Enterprise Edition'
description: 'Lync Server 2013: restauración de un servidor back-end de Enterprise Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2147aec00714704195399449e5d5e4d6ce609fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555216"
---
# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="2c1f0-103">Restauración de un servidor back-end de Enterprise Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c1f0-103">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c1f0-104">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="2c1f0-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="2c1f0-105">Use el procedimiento descrito en este tema en los dos casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2c1f0-105">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="2c1f0-106">Se produce un error en las bases de datos principal y reflejada de un servidor back-end de Enterprise Edition reflejado.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-106">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="2c1f0-107">Se produce un error en un servidor back-end de Enterprise Edition que no es reflejado.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-107">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="2c1f0-108">Si tiene un back-end de Enterprise Edition reflejado y solo se produce un error en el reflejo o la base de datos principal, consulte [restaurar un servidor back-end de Enterprise Edition en Lync server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) para restaurar la base de datos principal y [restaurar un servidor back-end de Enterprise Edition en Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) para restaurar el reflejo.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-108">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="2c1f0-109">Si se produce un error en el almacén de administración central, consulte [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="2c1f0-109">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="2c1f0-110">Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, vea [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="2c1f0-110">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2c1f0-111">Le recomendamos que tome una copia de imagen del sistema antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="2c1f0-112">Puede usar esta imagen como un punto de reversión, en caso de que algo salga mal durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="2c1f0-113">Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="2c1f0-114">Para restaurar un servidor back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="2c1f0-114">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="2c1f0-115">Empiece con un servidor nuevo o limpio que tenga el mismo nombre de dominio completo (FQDN) que el equipo con error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c1f0-116">Siga los procedimientos de implementación de servidores de la organización para realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="2c1f0-117">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el servidor que va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="2c1f0-118">Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los nombres de instancia iguales que antes del error.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-118">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c1f0-p103">Según la implementación, el servidor back-end puede incluir varias bases de datos combinadas o independientes. Para instalar el servidor SQL Server, siga el mismo procedimiento que usó originalmente para implementar el servidor, incluidos los permisos e inicios de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-p103">Depending on your deployment, the Back End Server might include multiple collocated or separate databases. Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="2c1f0-121">Tras instalar SQL Server, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c1f0-121">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="2c1f0-122">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-122">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="2c1f0-123">Haga clic en **Descargar topología de la implementación existente** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-123">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="2c1f0-p104">Seleccione la topología y, a continuación, haga clic en **Guardar**. Haga clic en **Sí** para confirmar la selección.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-p104">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="2c1f0-126">Haga clic con el botón secundario en el nodo **Lync Server 2013** y, a continuación, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-126">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="2c1f0-127">Siga el asistente **Publicar la topología**.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-127">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="2c1f0-128">En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-128">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2c1f0-129">En la página <STRONG>Crear bases de datos</STRONG> solo se muestran bases de datos independientes.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-129">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="2c1f0-130">Si está restaurando un back-end que fue reflejado, continúe para seguir el resto del asistente hasta que aparezca la **base de datos de creación de reflejos** del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-130">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="2c1f0-131">Seleccione la base de datos que desea instalar y complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-131">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="2c1f0-132">Siga los pasos restantes del asistente y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-132">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2c1f0-133">En lugar de ejecutar el generador de topologías, puede usar el cmdlet <STRONG>install-CsDatabase</STRONG> para crear cada base de datos y el cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar la creación de reflejos.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-133">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="2c1f0-134">Para obtener más información, vea la documentación referente a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-134">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="2c1f0-135">Para restaurar los datos del usuario, lleve a cabo el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="2c1f0-135">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="2c1f0-136">Copie ExportedUserData.zip de $Backup \\ a un directorio local.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-136">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="2c1f0-137">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="2c1f0-138">Antes de restaurar los datos de usuario, debe detener los servicios de Lync.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-138">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="2c1f0-139">Para ello, escriba:</span><span class="sxs-lookup"><span data-stu-id="2c1f0-139">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="2c1f0-140">Para restaurar los datos del usuario, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="2c1f0-140">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="2c1f0-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2c1f0-141">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="2c1f0-142">Reinicie Lync Services escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c1f0-142">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="2c1f0-143">Si implementó el grupo de respuesta en este grupo, restaure los datos de configuración del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-143">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="2c1f0-144">Para obtener más información, consulte [restore Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2c1f0-144">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="2c1f0-145">Si desea restaurar un servidor back-end que incluye bases de datos de archivado o supervisión, restaure los datos de archivado o supervisión con una herramienta de SQL Server, como SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-145">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="2c1f0-146">Para obtener más información, consulte [restauración de la supervisión o archivado de datos en Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="2c1f0-146">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

