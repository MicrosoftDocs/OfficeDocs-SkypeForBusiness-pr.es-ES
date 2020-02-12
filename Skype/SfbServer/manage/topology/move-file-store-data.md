---
title: Mover los datos del almacén de archivos a un nuevo almacén de archivos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para su implementación de Skype empresarial Server, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero necesita crear un nuevo recurso compartido. Después deberá realizar los siguientes pasos:'
ms.openlocfilehash: 91ba8393a958188e368ff3f8f5d2a85bcfcc1396
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888459"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="e8778-104">Mover los datos del almacén de archivos a un nuevo almacén de archivos en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e8778-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="e8778-105">Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para su implementación de Skype empresarial Server, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero necesita crear un nuevo recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="e8778-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="e8778-106">Después deberá realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e8778-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="e8778-107">Cierre los servicios de Skype empresarial Server que usan el almacén de archivos que planea quitar.</span><span class="sxs-lookup"><span data-stu-id="e8778-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="e8778-108">Defina el almacén de archivos en el generador de topología y publique los cambios para que el nuevo almacén de archivos esté disponible para su implementación.</span><span class="sxs-lookup"><span data-stu-id="e8778-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="e8778-109">Mueva los datos al nuevo almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="e8778-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="e8778-110">Reinicie los servidores o los servicios.</span><span class="sxs-lookup"><span data-stu-id="e8778-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="e8778-111">Opcionalmente, quite el recurso compartido de archivos y la carpeta de archivos antiguos.</span><span class="sxs-lookup"><span data-stu-id="e8778-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="e8778-112">Para mover los datos de un almacén de archivos a otro nuevo</span><span class="sxs-lookup"><span data-stu-id="e8778-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="e8778-113">Inicie sesión en un equipo como miembro del grupo RTCUniversersalServerAdmins o CsServerAdministrator en el que están instaladas las herramientas administrativas de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e8778-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="e8778-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e8778-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e8778-115">En la barra de navegación izquierda, haga clic en \*\*Topología \*\* y, a continuación, en \*\*Estado \*\*. </span><span class="sxs-lookup"><span data-stu-id="e8778-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="e8778-116">Para cada grupo de directores, un director, un servidor Standard Edition y un grupo de servidores front-end que usen el almacén de archivos que planea quitar, seleccione el servidor o grupo, haga clic en **acción**y, a continuación, haga clic en **detener todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="e8778-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="e8778-117">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e8778-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="e8778-118">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Skype empresarial Server**y, a continuación, haga clic en **generador de topologías de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="e8778-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="e8778-119">Seleccione un servidor o un grupo que use el almacén de archivos y realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8778-119">Select a server or pool that uses the file store, and do the following:</span></span>

   <span data-ttu-id="e8778-120">a.</span><span class="sxs-lookup"><span data-stu-id="e8778-120">a.</span></span> <span data-ttu-id="e8778-121">Haga clic con el botón derecho en el servidor o en el grupo y, a continuación, haga clic en **Editar propiedades**. </span><span class="sxs-lookup"><span data-stu-id="e8778-121">Right-click the server or pool, and then click **Edit Properties**.</span></span>

   <span data-ttu-id="e8778-122">b.</span><span class="sxs-lookup"><span data-stu-id="e8778-122">b.</span></span> <span data-ttu-id="e8778-123">En **Editar propiedades** > **Asociaciones** > **Almacén de archivos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e8778-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

   <span data-ttu-id="e8778-124">c.</span><span class="sxs-lookup"><span data-stu-id="e8778-124">c.</span></span> <span data-ttu-id="e8778-125">En **Definir nuevo almacén de archivos**, en **FQDN del servidor de archivos**, escriba el nombre de dominio completo (FQDN) del servidor de archivos.</span><span class="sxs-lookup"><span data-stu-id="e8778-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="e8778-126">En **Recurso compartido de archivos**, escriba el nombre de la carpeta del nuevo recurso compartido de archivos y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e8778-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="e8778-127">Este paso define un nuevo almacén de archivos para usar en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="e8778-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="e8778-128">Debe definirlo solo una vez, no en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="e8778-128">You define it only once, not for each server.</span></span> <span data-ttu-id="e8778-129">Antes de publicar la topología, deberá crear el recurso compartido de archivos definido en el servidor de archivos definido.</span><span class="sxs-lookup"><span data-stu-id="e8778-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="e8778-130">Para obtener información detallada, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8778-130">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

8. <span data-ttu-id="e8778-131">Por cada servidor o grupo que use el almacén de archivos, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8778-131">For each server or pool that uses the file store, do the following:</span></span>

   <span data-ttu-id="e8778-132">a.</span><span class="sxs-lookup"><span data-stu-id="e8778-132">a.</span></span> <span data-ttu-id="e8778-133">Haga clic con el botón derecho en el servidor o en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e8778-133">Right-click the server or pool, and then click **Edit properties**.</span></span>

   <span data-ttu-id="e8778-134">b.</span><span class="sxs-lookup"><span data-stu-id="e8778-134">b.</span></span> <span data-ttu-id="e8778-135">En **Editar propiedades** > **Asociaciones** > **Almacén de archivos**, seleccione el nuevo recurso compartido de archivos y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e8778-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

9. <span data-ttu-id="e8778-136">Publique la topología, compruebe el estado de la replicación y, a continuación, ejecute el Asistente para la implementación de Skype empresarial Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e8778-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="e8778-137">Para obtener información detallada, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8778-137">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

10. <span data-ttu-id="e8778-138">Inicie un símbolo del sistema: haga clic en **Inicio**, haga clic en **Ejecutar**y, a continuación, escriba cmd. exe.</span><span class="sxs-lookup"><span data-stu-id="e8778-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

11. <span data-ttu-id="e8778-139">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="e8778-139">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="e8778-140">El conmutador /S copia los archivos, directorios y subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="e8778-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="e8778-141">El conmutador /XF omite los archivos con el nombre Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="e8778-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="e8778-142">Las versiones actuales de robocopy.exe con el conmutador /MT dispara considerablemente la velocidad de copiado, debido a que usa varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e8778-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="e8778-143">Para el modificador/LOG, use una ruta de acceso del directorio y un nombre de archivo de registro con el formato C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="e8778-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="e8778-144">Este conmutador crea un archivo de registro de operaciones en la ubicación designada.</span><span class="sxs-lookup"><span data-stu-id="e8778-144">This switch creates a log file of operations at the named location.</span></span>

12. <span data-ttu-id="e8778-145">Cuando la copia de datos se haya completado, en el panel de control de Lync Server, haga clic en **topología**y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="e8778-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

13. <span data-ttu-id="e8778-146">Por cada servidor o grupo donde haya detenido los servicios, seleccione el servidor o el grupo, haga clic en **Acción** y después en **Iniciar todos los servicios**.         </span><span class="sxs-lookup"><span data-stu-id="e8778-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

14. <span data-ttu-id="e8778-p111">Quite el antiguo almacén de archivos de la topología y, a continuación, publique la topología. Para obtener información detallada, consulte [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8778-p111">Remove the old file store from the topology and then publish the topology. For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

15. <span data-ttu-id="e8778-149">(Opcional) Inicie sesión como miembro del grupo Administradores local o del grupo Administradores del dominio en el equipo que contenía el almacén de archivos que acaba de eliminar y quite el directorio y el recurso compartido de archivos anteriores.</span><span class="sxs-lookup"><span data-stu-id="e8778-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8778-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8778-150">See also</span></span>

[<span data-ttu-id="e8778-151">Reasignar un servidor a otro almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="e8778-151">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="e8778-152">Quitar un almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="e8778-152">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
