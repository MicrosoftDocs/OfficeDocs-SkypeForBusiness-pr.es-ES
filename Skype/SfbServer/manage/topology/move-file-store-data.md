---
title: Mover datos del almacén de archivos a un nuevo almacén de archivos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para su implementación de Skype Empresarial Server, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero debe crear un nuevo recurso compartido. A continuación, debe realizar los siguientes pasos:'
ms.openlocfilehash: 1ea1f6f038a5d589f9a2c3f480a5c9e589c324f3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816370"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="68e4d-104">Mover datos del almacén de archivos a un nuevo almacén de archivos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="68e4d-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="68e4d-105">Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para su implementación de Skype Empresarial Server, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero debe crear un nuevo recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="68e4d-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="68e4d-106">A continuación, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="68e4d-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="68e4d-107">Cierre los servicios de Skype Empresarial Server que usan el almacén de archivos que planea quitar.</span><span class="sxs-lookup"><span data-stu-id="68e4d-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="68e4d-108">Defina el almacén de archivos en topology Builder y publique los cambios para que el nuevo almacén de archivos esté disponible para su implementación.</span><span class="sxs-lookup"><span data-stu-id="68e4d-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="68e4d-109">Mueva los datos al nuevo almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="68e4d-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="68e4d-110">Reinicie los servidores o servicios.</span><span class="sxs-lookup"><span data-stu-id="68e4d-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="68e4d-111">Opcionalmente, quite el recurso compartido de archivos antiguo y la carpeta de archivos.</span><span class="sxs-lookup"><span data-stu-id="68e4d-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="68e4d-112">Para mover los datos de un almacén de archivos a otro nuevo</span><span class="sxs-lookup"><span data-stu-id="68e4d-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="68e4d-113">Inicie sesión en un equipo como miembro del grupo RTCUniversersalServerAdmins o CsServerAdministrator donde está instalado Skype Empresarial Server, Herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="68e4d-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="68e4d-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="68e4d-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="68e4d-115">En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="68e4d-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="68e4d-116">Para cada grupo de directores, director, servidor Standard Edition y grupo de servidores front-end que use el almacén de archivos que desea quitar, seleccione el servidor o grupo de servidores, haga clic en Acción y, a continuación, haga clic en Detener todos los **servicios.**</span><span class="sxs-lookup"><span data-stu-id="68e4d-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="68e4d-117">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="68e4d-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="68e4d-118">Inicie el Generador de topologías: **Haga** clic en Inicio, Todos los **programas,** Skype Empresarial **Server** y, a continuación, haga clic en Generador de topologías de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="68e4d-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="68e4d-119">Seleccione un servidor o grupo de servidores que use el almacén de archivos y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="68e4d-119">Select a server or pool that uses the file store, and do the following:</span></span>

   <span data-ttu-id="68e4d-120">a.</span><span class="sxs-lookup"><span data-stu-id="68e4d-120">a.</span></span> <span data-ttu-id="68e4d-121">Haga clic con el botón secundario en el servidor o grupo de servidores y, a continuación, haga clic **en Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="68e4d-121">Right-click the server or pool, and then click **Edit Properties**.</span></span>

   <span data-ttu-id="68e4d-122">b.</span><span class="sxs-lookup"><span data-stu-id="68e4d-122">b.</span></span> <span data-ttu-id="68e4d-123">En **Editar propiedades**, en **Asociaciones**, en Almacén **de archivos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="68e4d-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

   <span data-ttu-id="68e4d-124">c.</span><span class="sxs-lookup"><span data-stu-id="68e4d-124">c.</span></span> <span data-ttu-id="68e4d-125">En **Definir nuevo almacén de archivos,** en **FQDN** del servidor de archivos, escriba el nombre de dominio completo (FQDN) del servidor de archivos.</span><span class="sxs-lookup"><span data-stu-id="68e4d-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="68e4d-126">En **Recurso compartido de** archivos, escriba el nombre de la carpeta para el nuevo recurso compartido de archivos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68e4d-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="68e4d-127">Este paso define un nuevo almacén de archivos para su uso en topology Builder.</span><span class="sxs-lookup"><span data-stu-id="68e4d-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="68e4d-128">Solo se define una vez, no para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="68e4d-128">You define it only once, not for each server.</span></span> <span data-ttu-id="68e4d-129">Antes de publicar la topología, deberá crear el recurso compartido de archivos definido en el servidor de archivos definido.</span><span class="sxs-lookup"><span data-stu-id="68e4d-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="68e4d-130">Para obtener información detallada, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e4d-130">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

8. <span data-ttu-id="68e4d-131">Para cada servidor o grupo que use el almacén de archivos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="68e4d-131">For each server or pool that uses the file store, do the following:</span></span>

   <span data-ttu-id="68e4d-132">a.</span><span class="sxs-lookup"><span data-stu-id="68e4d-132">a.</span></span> <span data-ttu-id="68e4d-133">Haga clic con el botón secundario en el servidor o grupo de servidores y, a continuación, haga clic **en Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="68e4d-133">Right-click the server or pool, and then click **Edit properties**.</span></span>

   <span data-ttu-id="68e4d-134">b.</span><span class="sxs-lookup"><span data-stu-id="68e4d-134">b.</span></span> <span data-ttu-id="68e4d-135">En **Editar propiedades**, en **Asociaciones**, en almacén **de archivos,** seleccione el nuevo recurso compartido de archivos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68e4d-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

9. <span data-ttu-id="68e4d-136">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Skype Empresarial Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="68e4d-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="68e4d-137">Para obtener más información, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e4d-137">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

10. <span data-ttu-id="68e4d-138">Inicie un símbolo del sistema: haga clic **en Inicio,** en **Ejecutar** y, a continuación, escriba cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="68e4d-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

11. <span data-ttu-id="68e4d-139">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="68e4d-139">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="68e4d-140">El modificador /S copia archivos, directorios y subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="68e4d-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="68e4d-141">El modificador /XF omite los archivos denominados Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="68e4d-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="68e4d-142">Las versiones actuales de robocopy.exe con el conmutador /MT dispara considerablemente la velocidad de copiado, debido a que usa varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="68e4d-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="68e4d-143">Para el modificador /LOG, use una ruta de acceso de directorio y un nombre de archivo de registro en forma de C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="68e4d-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="68e4d-144">Este modificador crea un archivo de registro de operaciones en la ubicación con nombre.</span><span class="sxs-lookup"><span data-stu-id="68e4d-144">This switch creates a log file of operations at the named location.</span></span>

12. <span data-ttu-id="68e4d-145">Una vez completada la copia de datos, en el Panel de control de Lync Server, haga clic en Topología **y,** a continuación, haga clic en **Estado.**</span><span class="sxs-lookup"><span data-stu-id="68e4d-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

13. <span data-ttu-id="68e4d-146">Para cada servidor o grupo en el que detuvo los servicios, seleccione el servidor o grupo de servidores, haga clic en Acción **y,** a continuación, haga clic **en Iniciar todos los servicios.**</span><span class="sxs-lookup"><span data-stu-id="68e4d-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

14. <span data-ttu-id="68e4d-147">Quite el antiguo almacén de archivos de la topología y, a continuación, publique la topología.</span><span class="sxs-lookup"><span data-stu-id="68e4d-147">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="68e4d-148">Para obtener información detallada, consulte [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e4d-148">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

15. <span data-ttu-id="68e4d-149">(Opcional) Inicie sesión como miembro del grupo Administradores local o del grupo Admins. del dominio en el equipo que contenía el almacén de archivos que acaba de eliminar y quite el directorio y el recurso compartido de archivos anteriores.</span><span class="sxs-lookup"><span data-stu-id="68e4d-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="68e4d-150">Ver también</span><span class="sxs-lookup"><span data-stu-id="68e4d-150">See also</span></span>

[<span data-ttu-id="68e4d-151">Reasignar un servidor a un almacén de archivos diferente</span><span class="sxs-lookup"><span data-stu-id="68e4d-151">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="68e4d-152">Quitar un almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="68e4d-152">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
