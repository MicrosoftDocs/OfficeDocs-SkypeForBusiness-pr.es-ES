---
title: 'Lync Server 2013: restauración de un servidor de servicios de fondo de la edición Enterprise'
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
ms.openlocfilehash: 2bd57054505b3200f63bed8a60c47b400f7e7642
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="1f709-102">Restauración de un servidor de servicios de fondo de la edición empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f709-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f709-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="1f709-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="1f709-104">Use el procedimiento que se describe en este tema en los dos siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="1f709-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="1f709-105">Se producen errores en las bases de datos principal y reflejada de un servidor de servicios de fondo con duplicación de Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1f709-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="1f709-106">Se produce un error en el servidor de servicios de fondo de la edición empresarial que no está reflejado.</span><span class="sxs-lookup"><span data-stu-id="1f709-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="1f709-107">Si tiene un back-end de la edición empresarial reflejada y solo se produce un error en el reflejo o la base de datos principal, consulte [restaurar un servidor de back-end de empresa duplicada en Lync server 2013-principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) para restaurar la base de datos principal, y [restaurar un servidor back-end empresarial reflejado en Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) para restaurar el reflejo.</span><span class="sxs-lookup"><span data-stu-id="1f709-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="1f709-108">Si se produce un error en el almacén de administración central, vea [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="1f709-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="1f709-109">Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, consulte [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="1f709-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1f709-110">Le recomendamos que tome una copia de la imagen del sistema antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="1f709-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="1f709-111">Puede usar esta imagen como punto de reversión, en caso de que algo falle durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="1f709-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="1f709-112">Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="1f709-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="1f709-113">Para restaurar un servidor de servicios de fondo de la edición Enterprise</span><span class="sxs-lookup"><span data-stu-id="1f709-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="1f709-114">Empiece con un servidor limpio o nuevo que tenga el mismo nombre de dominio completo (FQDN) que el equipo que ha fallado, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="1f709-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f709-115">Siga los procedimientos de implementación de servidores de su organización para realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="1f709-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="1f709-116">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el servidor que va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="1f709-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="1f709-117">Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los mismos nombres de instancia que antes del error.</span><span class="sxs-lookup"><span data-stu-id="1f709-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f709-118">Dependiendo de su implementación, el servidor back-end puede incluir varias bases de datos colocadas o independientes.</span><span class="sxs-lookup"><span data-stu-id="1f709-118">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="1f709-119">Siga el mismo procedimiento para instalar SQL Server que usó originalmente para implementar el servidor, incluidos los permisos y los inicios de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f709-119">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="1f709-120">Después de instalar SQL Server, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f709-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="1f709-121">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1f709-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="1f709-122">Haga clic en **Descargar topología de la implementación existente**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f709-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="1f709-123">Seleccione la topología y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1f709-123">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="1f709-124">Haga clic en **sí** para confirmar la selección.</span><span class="sxs-lookup"><span data-stu-id="1f709-124">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="1f709-125">Haga clic con el botón derecho en el nodo de **2013 de Lync Server** y, después, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="1f709-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="1f709-126">Siga los instrucciones para **publicar el Asistente de topología** .</span><span class="sxs-lookup"><span data-stu-id="1f709-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="1f709-127">En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.</span><span class="sxs-lookup"><span data-stu-id="1f709-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1f709-128">Solo se muestran las bases de datos independientes en la página <STRONG>crear bases de datos</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1f709-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="1f709-129">Si está restaurando un back-end que fue reflejado, continúe siguiendo con el resto del asistente hasta que aparezca el mensaje **crear base de datos de reflejo** .</span><span class="sxs-lookup"><span data-stu-id="1f709-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="1f709-130">Seleccione la base de datos que desea instalar y complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="1f709-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="1f709-131">Siga el resto del asistente y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1f709-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1f709-132">En lugar de ejecutar el generador de topología, puede usar el cmdlet <STRONG>install-CsDatabase</STRONG> para crear cada base de datos y el cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar el reflejo.</span><span class="sxs-lookup"><span data-stu-id="1f709-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="1f709-133">Para obtener más información, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f709-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="1f709-134">Restaure los datos de usuario al realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f709-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="1f709-135">Copie ExportedUserData. zip desde $Backup\\ a un directorio local.</span><span class="sxs-lookup"><span data-stu-id="1f709-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="1f709-136">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1f709-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="1f709-137">Antes de restaurar los datos de usuario, debe detener los servicios de Lync.</span><span class="sxs-lookup"><span data-stu-id="1f709-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="1f709-138">Para ello, escriba:</span><span class="sxs-lookup"><span data-stu-id="1f709-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="1f709-139">Para restaurar los datos de usuario, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="1f709-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="1f709-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1f709-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="1f709-141">Reinicie los servicios de Lync escribiendo:</span><span class="sxs-lookup"><span data-stu-id="1f709-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="1f709-142">Si ha implementado el grupo de respuesta en este grupo, restaure los datos de configuración del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1f709-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="1f709-143">Para obtener más información, consulte [restauración de la configuración de grupo de respuesta en Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1f709-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="1f709-144">Si está restaurando un servidor back-end que incluye archivar o supervisar bases de datos, restaure los datos de archivado o supervisión mediante una herramienta de SQL Server, como SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="1f709-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="1f709-145">Para obtener más información, vea [restaurar o archivar datos en Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="1f709-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

