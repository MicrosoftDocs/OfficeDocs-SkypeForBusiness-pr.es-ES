---
title: Almacén de archivos de movimiento de datos a un nuevo almacén de archivos en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si necesitará quitar el servidor de archivos que actualmente está actuando como el almacén de archivos para su Skype para la implementación de Business Server, o si necesita realizar otros cambios que harían que el archivo actual almacén no está disponible, primero debe crear un nuevo recurso compartido. Después deberá realizar los siguientes pasos:'
ms.openlocfilehash: fd8869a7cd0ca5f29d839de373e3e7d2f3d76faa
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988274"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="dbf88-104">Almacén de archivos de movimiento de datos a un nuevo almacén de archivos en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="dbf88-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>
 
<span data-ttu-id="dbf88-105">Si necesitará quitar el servidor de archivos que actualmente está actuando como el almacén de archivos para su Skype para la implementación de Business Server, o si necesita realizar otros cambios que harían que el archivo actual almacén no está disponible, primero debe crear un nuevo recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="dbf88-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="dbf88-106">Después deberá realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="dbf88-106">Then you need to perform the following steps:</span></span>
  
1. <span data-ttu-id="dbf88-107">Apague el Skype para servicios de Business Server que utilizan el almacén de archivos que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="dbf88-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>
    
2. <span data-ttu-id="dbf88-108">Definir el almacén de archivos en el generador de topología y publique los cambios para que el nuevo archivo de almacenamiento disponibles para la implementación.</span><span class="sxs-lookup"><span data-stu-id="dbf88-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>
    
3. <span data-ttu-id="dbf88-109">Mueva los datos al nuevo almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="dbf88-109">Move the data to the new file store.</span></span>
    
4. <span data-ttu-id="dbf88-110">Reinicie los servidores o los servicios.</span><span class="sxs-lookup"><span data-stu-id="dbf88-110">Restart the servers or services.</span></span>
    
5. <span data-ttu-id="dbf88-111">Opcionalmente, quite el recurso compartido de archivos y la carpeta de archivos antiguos.</span><span class="sxs-lookup"><span data-stu-id="dbf88-111">Optionally, remove the old file share and file folder.</span></span>
    
### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="dbf88-112">Para mover los datos de un almacén de archivos a otro nuevo</span><span class="sxs-lookup"><span data-stu-id="dbf88-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="dbf88-113">Inicie sesión como miembro del grupo RTCUniversersalServerAdmins o CsServerAdministrator del grupo donde se instalan los Skype para Business Server, las herramientas administrativas en un equipo.</span><span class="sxs-lookup"><span data-stu-id="dbf88-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>
    
2.  <span data-ttu-id="dbf88-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="dbf88-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="dbf88-115">En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. </span><span class="sxs-lookup"><span data-stu-id="dbf88-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span> 
    
4. <span data-ttu-id="dbf88-116">Para cada grupo de directores, Director, servidor Standard Edition y grupo de servidores Front-End que utiliza el almacén de archivos que se va a quitar, seleccione el servidor o grupo de servidores, haga clic en **acción**y, a continuación, haga clic en **Detener todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="dbf88-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span> 
    
5. <span data-ttu-id="dbf88-117">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="dbf88-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
6. <span data-ttu-id="dbf88-118">Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Business Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="dbf88-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
7. <span data-ttu-id="dbf88-119">Seleccione un servidor o un grupo que use el almacén de archivos y realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dbf88-119">Select a server or pool that uses the file store, and do the following:</span></span>
    
1. <span data-ttu-id="dbf88-120">Haga clic con el botón derecho en el servidor o en el grupo y, a continuación, haga clic en **Editar propiedades**. </span><span class="sxs-lookup"><span data-stu-id="dbf88-120">Right-click the server or pool, and then click **Edit Properties**.</span></span> 
    
2. <span data-ttu-id="dbf88-121">En **Editar propiedades** > **Asociaciones** > **Almacén de archivos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="dbf88-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>
    
3. <span data-ttu-id="dbf88-p103">En **Definir nuevo almacén de archivos**, en **FQDN del servidor de archivos**, escriba el nombre de dominio completo (FQDN) del servidor de archivos. En **Recurso compartido de archivos**, escriba el nombre de la carpeta del nuevo recurso compartido de archivos y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dbf88-p103">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server. Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dbf88-124">En este paso se define un nuevo almacén de archivos para su uso en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="dbf88-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="dbf88-125">Debe definirlo solo una vez, no en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="dbf88-125">You define it only once, not for each server.</span></span> <span data-ttu-id="dbf88-126">Antes de publicar la topología, deberá crear el recurso compartido de archivos definido en el servidor de archivos definido.</span><span class="sxs-lookup"><span data-stu-id="dbf88-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="dbf88-127">Para obtener más información, consulte [definir el almacén de archivos para el Front-End](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="dbf88-127">For details, see [Define the File Store for the Front End](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span> 
  
8. <span data-ttu-id="dbf88-128">Por cada servidor o grupo que use el almacén de archivos, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dbf88-128">For each server or pool that uses the file store, do the following:</span></span>
    
1. <span data-ttu-id="dbf88-129">Haga clic con el botón derecho en el servidor o en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="dbf88-129">Right-click the server or pool, and then click **Edit properties**.</span></span>
    
2. <span data-ttu-id="dbf88-130">En **Editar propiedades** > **Asociaciones** > **Almacén de archivos**, seleccione el nuevo recurso compartido de archivos y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dbf88-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>
    
9. <span data-ttu-id="dbf88-131">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Skype para el Asistente para la implementación de Business Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="dbf88-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="dbf88-132">Para obtener información detallada, vea [Procedimientos comunes para Removing Lync Servers and Components](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="dbf88-132">For details, see [Common Procedures for Removing Lync Servers and Components](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>
    
10. <span data-ttu-id="dbf88-133">Inicie un símbolo del sistema: haga clic en **Inicio**, haga clic en **Ejecutar**y, a continuación, escriba cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="dbf88-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>
    
11. <span data-ttu-id="dbf88-134">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="dbf88-134">At the command line, type the following:</span></span>
    
  ```
  Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
  ```

    > [!TIP]
    > <span data-ttu-id="dbf88-135">El conmutador /S copia los archivos, directorios y subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="dbf88-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="dbf88-136">El conmutador /XF omite los archivos con el nombre Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="dbf88-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="dbf88-137">Las versiones actuales de robocopy.exe con el conmutador /MT dispara considerablemente la velocidad de copiado, debido a que usa varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="dbf88-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="dbf88-138">Para el modificador /LOG, use un nombre de archivo de registro y la ruta de acceso de Active directory en forma de C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="dbf88-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="dbf88-139">Este conmutador crea un archivo de registro de operaciones en la ubicación designada.</span><span class="sxs-lookup"><span data-stu-id="dbf88-139">This switch creates a log file of operations at the named location.</span></span> 
  
12. <span data-ttu-id="dbf88-140">Cuando la copia de datos se complete, en el Panel de Control de Lync Server, haga clic en **topología**y, a continuación, haga clic en **estado**.</span><span class="sxs-lookup"><span data-stu-id="dbf88-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>
    
13. <span data-ttu-id="dbf88-141">Por cada servidor o grupo donde haya detenido los servicios, seleccione el servidor o el grupo, haga clic en **Acción** y después en **Iniciar todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="dbf88-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span> 
    
14. <span data-ttu-id="dbf88-142">Quite el antiguo almacén de archivos de la topología y, a continuación, publique la topología.</span><span class="sxs-lookup"><span data-stu-id="dbf88-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="dbf88-143">Para obtener información detallada, vea [quitar un almacén de archivos](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="dbf88-143">For details, see [Remove a file store](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>
    
15. <span data-ttu-id="dbf88-144">(Opcional) Inicie sesión como miembro del grupo Administradores local o del grupo Administradores del dominio en el equipo que contenía el almacén de archivos que acaba de eliminar y quite el directorio y el recurso compartido de archivos anteriores.</span><span class="sxs-lookup"><span data-stu-id="dbf88-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dbf88-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbf88-145">See also</span></span>

[<span data-ttu-id="dbf88-146">Reasignar un servidor a un almacén de archivos diferente</span><span class="sxs-lookup"><span data-stu-id="dbf88-146">Reassign a Server to a Different File Store</span></span>](http://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)
  
[<span data-ttu-id="dbf88-147">Quitar un almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="dbf88-147">Remove a file store</span></span>](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)