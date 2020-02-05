---
title: Agregar bases de datos de archivado a una implementación existente en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumen: Lea este tema para obtener información sobre cómo agregar bases de datos de archivado a su implementación de Skype empresarial Server.'
ms.openlocfilehash: 26cdd1befb695fbaf0656611ed65c7afa778af6c
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769053"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="3c5f6-103">Agregar bases de datos de archivado a una implementación existente en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3c5f6-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="3c5f6-104">**Resumen:** Lea este tema para obtener información sobre cómo agregar bases de datos de archivado a su implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="3c5f6-105">Es preciso incorporar el archivado a la topología para poder configurar la implementación a fin de admitir el archivado.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="3c5f6-106">La información de este tema explica cómo usar el generador de topología para:</span><span class="sxs-lookup"><span data-stu-id="3c5f6-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="3c5f6-107">Agregar una base de datos de archivado a la topología.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="3c5f6-108">Publique la topología actualizada para agregar la base de datos de archivado a su implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3c5f6-109">Si desea usar la integración de Microsoft Exchange para almacenar los datos y archivos de los servidores de Exchange de todos los usuarios de su implementación, no especifique el **almacenamiento de SQL Server** en el almacén o use la información de reflejo de la **tienda de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="3c5f6-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="3c5f6-110">Agregar una base de datos de archivado a la topología</span><span class="sxs-lookup"><span data-stu-id="3c5f6-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="3c5f6-111">En un equipo que ejecute Skype empresarial Server o en el que estén instaladas las herramientas administrativas de Skype empresarial Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).</span><span class="sxs-lookup"><span data-stu-id="3c5f6-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="3c5f6-112">Iniciar el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="3c5f6-113">En el árbol de consola, vaya al grupo de servidores front-end en el que desee implementar el archivado y, luego, haga clic en el nombre de dicho grupo donde desee implementar el archivado.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="3c5f6-114">En el menú **Acción**, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="3c5f6-115">En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="3c5f6-116">Desplácese hacia abajo hasta **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="3c5f6-117">Marque la casilla **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="3c5f6-118">En **archivar almacén de SQL Server,** realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3c5f6-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="3c5f6-119">Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="3c5f6-120">Si todos los usuarios están alojados en Microsoft Exchange Server 2013 o una versión posterior, puede archivar las comunicaciones de Skype empresarial para todos los usuarios de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="3c5f6-121">En este caso, no es necesario configurar el almacén de archivado de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="3c5f6-122">Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c5f6-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="3c5f6-123">En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="3c5f6-124">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="3c5f6-125">Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="3c5f6-126">Si desea usar el reflejo de la tienda SQL Server, seleccione **Habilitar reflejo de la tienda SQL Server**y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c5f6-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="3c5f6-127">Para usar un almacén de SQL Server existente para la creación de reflejo, en el cuadro de lista desplegable **archivado reflejado de SQL Server** , haga clic en el nombre del almacén de SQL Server que desea usar para el reflejo.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="3c5f6-128">Para especificar un nuevo almacén de SQL Server para la creación de reflejo, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3c5f6-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="3c5f6-129">a.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-129">a.</span></span> <span data-ttu-id="3c5f6-130">En **FQDN de SQL Server**, especifique el nombre completo del servidor SQL Server en el que desea crear el nuevo almacén de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="3c5f6-131">b.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-131">b.</span></span> <span data-ttu-id="3c5f6-132">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="3c5f6-133">c.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-133">c.</span></span> <span data-ttu-id="3c5f6-134">Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="3c5f6-135">Si habilita el reflejo de SQL Server y desea incluir un testigo de reflejo de SQL Server (una tercera, instancia de SQL Server independiente que puede detectar el estado del servidor SQL Server principal y de las instancias reflejadas), seleccione la casilla **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="3c5f6-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="3c5f6-136">a.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-136">a.</span></span> <span data-ttu-id="3c5f6-137">En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo testigo de reflejo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="3c5f6-138">b.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-138">b.</span></span> <span data-ttu-id="3c5f6-139">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="3c5f6-140">c.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-140">c.</span></span> <span data-ttu-id="3c5f6-141">Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="3c5f6-142">Para guardar la configuración, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="3c5f6-143">Publicar la topología actualizada para agregar una base de datos de archivado a la implementación</span><span class="sxs-lookup"><span data-stu-id="3c5f6-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="3c5f6-144">En un equipo que ejecute Skype empresarial Server o en el que estén instaladas las herramientas administrativas de Skype empresarial Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).</span><span class="sxs-lookup"><span data-stu-id="3c5f6-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c5f6-145">Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para agregar un servidor a la topología. debe usar una cuenta que sea miembro del grupo de **administradores del dominio** y el grupo **RTCUniversalServerAdmins** , y que tenga permisos de control total (lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Skype empresarial Server (para que el generador de topología pueda configurar la lista de control de acceso discrecional (DACL) obligatoria o una cuenta con derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="3c5f6-146">Abra la topología que creó en la sección anterior con el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="3c5f6-147">En el árbol de consola, haga clic con el botón secundario en **Skype empresarial Server**y, a continuación, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="3c5f6-148">En la página **Publicar la topología**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="3c5f6-149">En la página **Crear bases de datos**, compruebe que la base de datos está seleccionada y, luego, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3c5f6-150">Si no tiene los permisos adecuados para crear bases de datos, puede cancelar la selección de la base de datos y alguien con permisos adecuados podrá crear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="3c5f6-151">> solo se pueden instalar bases de datos en servidores SQL dedicados mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="3c5f6-152">Las bases de datos en servidores SQL Server que se han combinado con otros componentes de servidor necesitan instalarse al ejecutar la instalación local en dicho equipo.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="3c5f6-153">En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3c5f6-154">Una vez publicada la topología, necesita configurar las opciones y las directivas para el archivado antes de que se pueda archivar cualquier contenido.</span><span class="sxs-lookup"><span data-stu-id="3c5f6-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="3c5f6-155">Para obtener más información, vea [configurar las opciones de archivado para Skype empresarial Server](configure-archiving-options.md) y [configurar directivas de archivado para Skype empresarial Server](configure-archiving-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3c5f6-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

