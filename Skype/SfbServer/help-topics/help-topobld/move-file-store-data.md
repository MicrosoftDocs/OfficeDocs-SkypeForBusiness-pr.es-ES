---
title: Mover los datos del almacén de archivos a un nuevo almacén de archivos en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para la implementación de Skype empresarial Server 2015, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero debe crear un nuevo recurso compartido. A continuación, debe realizar los siguientes pasos:'
ms.openlocfilehash: c9bdc7ac572ecd8a71022e5a267454b795ef7cc6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215591"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="48457-104">Mover los datos del almacén de archivos a un nuevo almacén de archivos en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="48457-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="48457-105">Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para la implementación de Skype empresarial Server 2015, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero debe crear un nuevo recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="48457-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="48457-106">A continuación, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="48457-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="48457-107">Apague los servicios de Skype empresarial Server 2015 que usan el almacén de archivos que planea quitar.</span><span class="sxs-lookup"><span data-stu-id="48457-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="48457-108">Definir el almacén de archivos en Topology Builder y publicar los cambios para poner el nuevo almacén de archivos a disposición de la implementación.</span><span class="sxs-lookup"><span data-stu-id="48457-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="48457-109">Mueva los datos al nuevo almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="48457-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="48457-110">Reinicie los servidores o los servicios.</span><span class="sxs-lookup"><span data-stu-id="48457-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="48457-111">Si lo desea, puede quitar el recurso compartido de archivos y la carpeta de archivos antiguos.</span><span class="sxs-lookup"><span data-stu-id="48457-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="48457-112">Para mover los datos de un almacén de archivos a otro nuevo</span><span class="sxs-lookup"><span data-stu-id="48457-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="48457-113">Inicie sesión en un equipo como miembro del grupo Grupo rtcuniversersalserveradmins o CsServerAdministrator donde están instaladas las herramientas administrativas de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="48457-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="48457-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="48457-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="48457-115">En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="48457-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="48457-116">Para cada grupo de directores, Director, servidor Standard Edition y grupo de servidores front-end que use el almacén de archivos que piensa quitar, seleccione el servidor o grupo de servidores, haga clic en **acción**y, a continuación, haga clic en **detener todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="48457-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="48457-117">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="48457-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="48457-118">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="48457-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="48457-119">Seleccione un servidor o grupo de servidores que use el almacén de archivos y realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="48457-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="48457-120">Haga clic con el botón secundario en el servidor o grupo de servidores y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="48457-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="48457-121">En **Editar propiedades**, en **asociaciones**, en **almacén de archivos**, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="48457-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="48457-122">En **definir nuevo almacén de archivos**, en **FQDN del servidor de archivos**, escriba el nombre de dominio completo (FQDN) del servidor de archivos.</span><span class="sxs-lookup"><span data-stu-id="48457-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="48457-123">En **recurso compartido de archivos**, escriba el nombre de la carpeta para el nuevo recurso compartido de archivos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="48457-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="48457-124">En este paso se define un nuevo almacén de archivos para su uso en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="48457-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="48457-125">Solo tiene que definirla una vez, no para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="48457-125">You define it only once, not for each server.</span></span> <span data-ttu-id="48457-126">Antes de publicar la topología, deberá crear el recurso compartido de archivos definido en el servidor de archivos definido.</span><span class="sxs-lookup"><span data-stu-id="48457-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="48457-127">Para obtener información detallada, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="48457-127">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

11. <span data-ttu-id="48457-128">Para cada servidor o grupo de servidores que use el almacén de archivos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="48457-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="48457-129">Haga clic con el botón secundario en el servidor o grupo de servidores y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="48457-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="48457-130">En **Editar propiedades**, en **asociaciones**, en **almacén de archivos**, seleccione el nuevo recurso compartido de archivos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="48457-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="48457-131">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Skype empresarial Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="48457-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="48457-132">Para obtener más información, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="48457-132">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

15. <span data-ttu-id="48457-133">Inicie un símbolo del sistema: haga clic en **Inicio**y en **Ejecutar**y, a continuación, escriba cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="48457-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="48457-134">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="48457-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="48457-135">El modificador/S copia sobre archivos, directorios y subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="48457-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="48457-136">El modificador/XF omite los archivos denominados Meeting. Active.</span><span class="sxs-lookup"><span data-stu-id="48457-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="48457-137">Las versiones actuales de robocopy.exe con el conmutador /MT dispara considerablemente la velocidad de copiado, debido a que usa varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="48457-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="48457-138">Para el conmutador/LOG, use una ruta de acceso de directorio y un nombre de archivo de registro con el formato C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="48457-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="48457-139">Este modificador crea un archivo de registro de operaciones en la ubicación indicada.</span><span class="sxs-lookup"><span data-stu-id="48457-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="48457-140">Una vez completada la copia de datos, en el panel de control de Lync Server, haga clic en **topología**y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="48457-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="48457-141">Para cada servidor o grupo de servidores donde haya detenido los servicios, seleccione el servidor o el grupo de servidores, haga clic en **acción**y, a continuación, haga clic en **iniciar todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="48457-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="48457-142">Quite el antiguo almacén de archivos de la topología y, a continuación, publique la topología.</span><span class="sxs-lookup"><span data-stu-id="48457-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="48457-143">Para obtener información detallada, consulte [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="48457-143">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

20. <span data-ttu-id="48457-144">(Opcional) Inicie sesión como miembro del grupo Administradores local o del grupo Admins. del dominio en el equipo que contenía el almacén de archivos que acaba de eliminar y quite el directorio y el recurso compartido de archivos anteriores.</span><span class="sxs-lookup"><span data-stu-id="48457-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="48457-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="48457-145">See also</span></span>

[<span data-ttu-id="48457-146">Reasignar un servidor a un almacén de archivos diferente</span><span class="sxs-lookup"><span data-stu-id="48457-146">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="48457-147">Quitar un almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="48457-147">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
