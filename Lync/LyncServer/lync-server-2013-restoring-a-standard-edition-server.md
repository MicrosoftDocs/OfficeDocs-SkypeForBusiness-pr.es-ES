---
title: 'Lync Server 2013: restaurar un servidor Standard Edition'
description: 'Lync Server 2013: restaurar un servidor Standard Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2cd6976324492e0539c47999f78434e1a82706
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542396"
---
# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="d3903-103">Restaurar un servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3903-103">Restoring a Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3903-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d3903-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d3903-105">Si se produce un error en un servidor Standard Edition que no hospeda el almacén de administración central, siga los procedimientos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="d3903-105">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="d3903-106">Si se produce un error en el almacén de administración central, consulte [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="d3903-106">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d3903-107">Le recomendamos que tome una copia de imagen del sistema antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="d3903-107">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="d3903-108">Puede usar esta imagen como un punto de reversión, en caso de que algo salga mal durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="d3903-108">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="d3903-109">Es posible que desee realizar la copia de la imagen después de instalar el sistema operativo y SQL Server y restaurar o volver a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="d3903-109">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="d3903-110">Para restaurar un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d3903-110">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="d3903-111">Empiece con un servidor nuevo o limpio que tenga el mismo nombre de dominio completo (FQDN) que el equipo con error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="d3903-111">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3903-112">Siga los procedimientos de implementación de servidores de la organización para realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="d3903-112">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="d3903-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins y del grupo local Administradores, inicie sesión en el servidor que va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="d3903-113">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="d3903-114">Restaure el almacén de archivos copiando el almacén de archivos adecuado de $Backup a la ubicación del almacén de archivos en el servidor y comparta la carpeta.</span><span class="sxs-lookup"><span data-stu-id="d3903-114">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d3903-115">La ruta de acceso y el nombre de archivo del almacén de archivos restaurados deben ser exactamente los mismos que los del almacén de archivos de copia de seguridad para que los componentes que usan los archivos puedan acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="d3903-115">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="d3903-116">Ejecute el generador de topologías:</span><span class="sxs-lookup"><span data-stu-id="d3903-116">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="d3903-117">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d3903-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="d3903-118">Haga clic en **Descargar topología de la implementación existente** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d3903-118">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="d3903-p103">Seleccione la topología y, a continuación, haga clic en **Guardar**. Haga clic en **Sí** para confirmar la selección.</span><span class="sxs-lookup"><span data-stu-id="d3903-p103">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="d3903-121">Vaya a la carpeta o los medios de instalación de Lync Server y, a continuación, inicie el Asistente para la implementación de Lync Server que se encuentra en la \\ configuración de \\ AMD64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="d3903-121">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="d3903-122">Use el Asistente para la implementación de Lync Server para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3903-122">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="d3903-123">Ejecute el **Paso 1: Instalar el almacén de configuración local** para instalar los archivos de configuración local.</span><span class="sxs-lookup"><span data-stu-id="d3903-123">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="d3903-124">Ejecute el **paso 2: configurar o quitar los componentes de Lync Server** para instalar los roles de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3903-124">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="d3903-125">Ejecute el **Paso 3: Solicitar, instalar o asignar certificados** para asignar los certificados.</span><span class="sxs-lookup"><span data-stu-id="d3903-125">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="d3903-126">Ejecute el **Paso 4: Iniciar servicios** para iniciar los servicios en el servidor.</span><span class="sxs-lookup"><span data-stu-id="d3903-126">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="d3903-127">Para obtener información detallada sobre cómo ejecutar el Asistente para la implementación, consulte la documentación de implementación correspondiente al rol de servidor que esté restaurando.</span><span class="sxs-lookup"><span data-stu-id="d3903-127">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="d3903-128">Para restaurar los datos del usuario, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3903-128">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="d3903-129">Copie ExportedUserData.zip de $Backup \\ a un directorio local.</span><span class="sxs-lookup"><span data-stu-id="d3903-129">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="d3903-130">Antes de restaurar los datos de usuario, debe detener los servicios de Lync.</span><span class="sxs-lookup"><span data-stu-id="d3903-130">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="d3903-131">Para ello, escriba:</span><span class="sxs-lookup"><span data-stu-id="d3903-131">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="d3903-132">Para restaurar los datos del usuario, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="d3903-132">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="d3903-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d3903-133">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="d3903-134">Reinicie Lync Services escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3903-134">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="d3903-135">Si implementó el grupo de respuesta en este servidor Standard Edition, restaure los datos de configuración del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d3903-135">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="d3903-136">Para obtener más información, consulte [restore Response Group Settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d3903-136">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="d3903-137">Si ha implementado chat persistente en este servidor Standard Edition, restaure la base de datos de chat persistente (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="d3903-137">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="d3903-138">Si usó la copia de seguridad de SQL Server para hacer una copia de seguridad de la base de datos de chat persistente, use los procedimientos de restauración de SQL Server para restaurarla.</span><span class="sxs-lookup"><span data-stu-id="d3903-138">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="d3903-139">Si usó el cmdlet Export-CsPersistentChatData para hacer una copia de seguridad, use el Import-CsPersistentChatData para restaurarlo.</span><span class="sxs-lookup"><span data-stu-id="d3903-139">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

