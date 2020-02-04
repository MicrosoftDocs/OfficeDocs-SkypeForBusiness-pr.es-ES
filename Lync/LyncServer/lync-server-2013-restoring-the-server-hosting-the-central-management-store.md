---
title: 'Lync Server 2013: restaurar el servidor que hospeda el almacén de administración central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 976f486d096f7be59e2eef74eab7b03d6cc4bab0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="94896-102">Restaurar el servidor que hospeda el almacén de administración central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94896-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94896-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="94896-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="94896-104">Una implementación de Lync Server tiene un único almacén de administración central, una copia de la cual se replica en cada servidor que ejecuta un rol de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94896-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="94896-105">En este tema se describe cómo restaurar un servidor de back-end o un servidor Standard Edition que hospeda el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="94896-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="94896-106">Para encontrar el grupo en el que se encuentra el servidor de administración central, abra el generador de topologías, haga clic en **Lync Server**y mire en el panel derecho, en **servidor de administración central**.</span><span class="sxs-lookup"><span data-stu-id="94896-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="94896-107">Si el servidor back-end que hospeda el almacén de administración central está en una configuración duplicada y la base de datos reflejada sigue funcionando, le recomendamos que haga una copia de seguridad de este reflejo en funcionamiento y, a continuación, realice una restauración completa tanto en la base de datos principal como en la base de datos reflejada con esta copia de seguridad siguiendo el procedimiento de restauración que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="94896-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="94896-108">Esto es necesario porque la restauración de back-end requiere modificar y publicar la topología, lo cual puede hacerse solo si la base de datos principal que hospeda CMS está operativa.</span><span class="sxs-lookup"><span data-stu-id="94896-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="94896-109">Además, tenga en cuenta que las funciones de base de datos principales y reflejadas no se pueden intercambiar si la topología no se puede publicar.</span><span class="sxs-lookup"><span data-stu-id="94896-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94896-110">Si se produjo un error en un servidor de back-end o un servidor Standard Edition que no aloja el almacén de administración central, consulte <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restaurar un servidor de servicios de fondo de la edición empresarial en Lync server 2013</A> o <A href="lync-server-2013-restoring-a-standard-edition-server.md">restaurar un servidor Standard Edition en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="94896-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="94896-111">Si un servidor back-end que hospeda el almacén de administración central está en una configuración reflejada y solo se produjo un error en el reflejo, consulte <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restaurar un servidor de back-end de empresa duplicada en Lync Server 2013-Mirror</A>.</span><span class="sxs-lookup"><span data-stu-id="94896-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="94896-112">Si se produce un error en cualquier otro servidor, vea <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restaurar un servidor miembro de Enterprise Edition en Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="94896-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="94896-113">Le recomendamos que tome una copia de la imagen del sistema antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="94896-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="94896-114">Puede usar esta imagen como punto de reversión, en caso de que algo falle durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="94896-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="94896-115">Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="94896-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="94896-116">Para restaurar el almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="94896-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="94896-117">Empiece con un servidor limpio o nuevo que tenga el mismo nombre de dominio completo (FQDN) que el equipo que ha fallado, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="94896-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94896-118">Siga los procedimientos de implementación de servidores de su organización para realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="94896-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="94896-119">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins y del grupo de administradores locales, inicie sesión en el servidor que va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="94896-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="94896-120">Si está restaurando un servidor Standard Edition, restaure el almacén de archivos copiando el almacén de archivos adecuado de $Backup a la ubicación del almacén de archivos en el servidor y, a continuación, comparta la carpeta.</span><span class="sxs-lookup"><span data-stu-id="94896-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="94896-121">La ruta de acceso y el nombre de archivo del almacén de archivos restaurado deben ser exactamente iguales a los de la copia de seguridad del almacén de archivos para que los componentes que los usan puedan acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="94896-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="94896-122">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="94896-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="94896-123">Si va a instalar un servidor Standard Edition, vaya a la carpeta o los elementos multimedia de instalación de Lync Server y, a continuación, inicie el \\asistente\\para\\la implementación de Lync Server, que se encuentra en Setup AMD64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="94896-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="94896-124">En el Asistente para la implementación, haga clic en **preparar el primer servidor Standard Edition** y siga el Asistente para instalar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="94896-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="94896-125">Si va a instalar un servidor de servicios de fondo para empresas, instale SQL Server 2012 o SQL Server 2008 R2, de modo que los nombres de instancia se mantengan igual que antes del error.</span><span class="sxs-lookup"><span data-stu-id="94896-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="94896-126">Según el servidor que esté restaurando y en la implementación, el servidor puede incluir varias bases de datos colocadas o independientes.</span><span class="sxs-lookup"><span data-stu-id="94896-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="94896-127">Siga el mismo procedimiento para instalar SQL Server que usó originalmente para implementar el servidor, incluidos los permisos y los inicios de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="94896-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="94896-128">Desde un servidor front-end, inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="94896-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="94896-129">Vuelva a crear el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="94896-129">Re-create the Central Management store.</span></span> <span data-ttu-id="94896-130">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94896-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="94896-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="94896-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="94896-132">Establezca el punto de control de los servicios de dominio de Active Directory para el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="94896-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="94896-133">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94896-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="94896-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="94896-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94896-135">Si pierde el punto de conexión, puede volver a ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="94896-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="94896-136">Importar los datos de la tienda de administración central desde $Backup.</span><span class="sxs-lookup"><span data-stu-id="94896-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="94896-137">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94896-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="94896-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="94896-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="94896-139">Habilitar los cambios que acaba de hacer.</span><span class="sxs-lookup"><span data-stu-id="94896-139">Enable the changes you have just made.</span></span> <span data-ttu-id="94896-140">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="94896-140">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94896-141">Después de habilitar la topología, puede encontrar el documento de topología en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="94896-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="94896-142">Si está restaurando un servidor de servicios de fondo Enterprise Edition que también ha hospedado el CMS, o si necesita volver a crear un reflejo del CMS, siga este paso.</span><span class="sxs-lookup"><span data-stu-id="94896-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="94896-143">En caso contrario, vaya al paso 11.</span><span class="sxs-lookup"><span data-stu-id="94896-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="94896-144">Instale las bases de datos independientes de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="94896-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="94896-145">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="94896-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="94896-146">Haga clic en **Descargar topología de la implementación existente**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94896-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="94896-147">Seleccione la topología y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="94896-147">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="94896-148">Haga clic en **sí** para confirmar la selección.</span><span class="sxs-lookup"><span data-stu-id="94896-148">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="94896-149">Haga clic con el botón derecho en el nodo de **2013 de Lync Server** y, después, haga clic en **instalar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="94896-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="94896-150">Siga el Asistente para la **instalación de bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="94896-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="94896-151">Si está restaurando una base de datos que no es el almacén de administración central en este servidor, en la página **crear bases** de datos, seleccione las bases de datos que desea volver a crear.</span><span class="sxs-lookup"><span data-stu-id="94896-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="94896-152">Solo se muestran las bases de datos independientes en la página <STRONG>crear bases de datos</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="94896-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="94896-153">Las bases de datos colocadas se crean al ejecutar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94896-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="94896-154">Si está restaurando un servidor de servicios de fondo reflejado, siga con el resto del asistente hasta que llegue a la pregunta de crear una base de datos de reflejo.</span><span class="sxs-lookup"><span data-stu-id="94896-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="94896-155">Seleccione la base de datos que desea instalar y complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="94896-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="94896-156">Siga el resto del asistente y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="94896-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="94896-157">En lugar de ejecutar el generador de topología, puede usar el cmdlet <STRONG>install-CsDatabase</STRONG> para crear cada base de datos y el cmdlet <STRONG>install-CsMirrorDatabase</STRONG> para configurar el reflejo.</span><span class="sxs-lookup"><span data-stu-id="94896-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="94896-158">Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> y <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.</span><span class="sxs-lookup"><span data-stu-id="94896-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="94896-159">Si está restaurando un servidor Standard Edition, vaya a la carpeta o los elementos multimedia de instalación de Lync Server e inicie el Asistente para la implementación \\de\\Lync\\Server que se encuentra en Setup AMD64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="94896-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="94896-160">Use el Asistente para la implementación de Lync Server para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94896-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="94896-161">Ejecute el **paso 1: instalar el almacén de configuración local** para instalar los archivos de configuración local.</span><span class="sxs-lookup"><span data-stu-id="94896-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="94896-162">Ejecute el **paso 2: configurar o quitar los componentes de Lync Server** para instalar los roles de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94896-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="94896-163">Ejecute el **paso 3: solicitar, instalar o asignar certificados** para asignar los certificados.</span><span class="sxs-lookup"><span data-stu-id="94896-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="94896-164">Ejecute el **paso 4: iniciar servicios** para iniciar servicios en el servidor.</span><span class="sxs-lookup"><span data-stu-id="94896-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="94896-165">Para obtener más información sobre cómo ejecutar el Asistente para la implementación, consulte la documentación de implementación del rol de servidor que va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="94896-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="94896-166">Restaure los datos de usuario al realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94896-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="94896-167">Copie ExportedUserData. zip desde $Backup\\ a un directorio local.</span><span class="sxs-lookup"><span data-stu-id="94896-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="94896-168">Antes de restaurar los datos de usuario, debe detener los servicios de Lync.</span><span class="sxs-lookup"><span data-stu-id="94896-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="94896-169">Para ello, escriba:</span><span class="sxs-lookup"><span data-stu-id="94896-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="94896-170">Para restaurar los datos de usuario, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="94896-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="94896-171">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="94896-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="94896-172">Reinicie los servicios de Lync escribiendo:</span><span class="sxs-lookup"><span data-stu-id="94896-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="94896-173">Restaure los datos de información de ubicación en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="94896-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="94896-174">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94896-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="94896-175">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="94896-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="94896-176">Si ha implementado el grupo de respuesta en este grupo o servidor Standard Edition, restaure los datos de configuración del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="94896-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="94896-177">Para obtener más información, consulte [restauración de la configuración de grupo de respuesta en Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="94896-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="94896-178">Si está restaurando un servidor back-end que incluye bases de datos de archivado o supervisión, restaure los datos de archivado o supervisión mediante una herramienta de administración de SQL Server, como SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="94896-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="94896-179">Para obtener más información, vea [restaurar o archivar datos en Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="94896-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

