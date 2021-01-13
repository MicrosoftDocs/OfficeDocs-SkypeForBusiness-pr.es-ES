---
title: Cambiar las opciones de la base de datos de archivado en Skype Empresarial Server
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
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumen: obtenga información sobre cómo cambiar las opciones de bases de datos de archivado para Skype Empresarial Server.'
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817700"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="39937-103">Cambiar las opciones de la base de datos de archivado en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="39937-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="39937-104">**Resumen:** Obtenga información sobre cómo cambiar las opciones de bases de datos de archivado para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="39937-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="39937-105">Si implementa el archivado con SQL Server almacenamiento de archivado para cualquiera de los usuarios, puede realizar los siguientes cambios en el almacenamiento de la base de datos:</span><span class="sxs-lookup"><span data-stu-id="39937-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="39937-106">Use una base de SQL Server de datos de archivado diferente para el almacenamiento de archivado.</span><span class="sxs-lookup"><span data-stu-id="39937-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="39937-107">Esto incluye la base de datos de archivado principal y cualquier base de datos que use para SQL Server creación de reflejos.</span><span class="sxs-lookup"><span data-stu-id="39937-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="39937-108">Cambie a la integración de Microsoft Exchange para almacenar archivos y datos de archivado en servidores exchange.</span><span class="sxs-lookup"><span data-stu-id="39937-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="39937-109">Si todos los usuarios están en sus servidores de Exchange y desea usar el almacenamiento de Microsoft Exchange para todos los usuarios de la implementación, debe quitar las bases de datos del almacén de SQL Server de la topología.</span><span class="sxs-lookup"><span data-stu-id="39937-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="39937-110">Para realizar cualquiera de estos cambios, debe ejecutar el Generador de topologías, realizar los cambios y, a continuación, volver a publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="39937-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="39937-111">No especifique el almacén **de SQL Server** ni habilite la información de creación de reflejos del almacén de **SQL Server, a** menos que tenga usuarios de Skype Empresarial que no estén en servidores de Exchange.</span><span class="sxs-lookup"><span data-stu-id="39937-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="39937-112">Cambiar las opciones de base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="39937-112">Change Archiving database options</span></span>

1. <span data-ttu-id="39937-113">En un equipo que ejecute Skype Empresarial Server o en el que estén instaladas las herramientas administrativas de Skype Empresarial Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).</span><span class="sxs-lookup"><span data-stu-id="39937-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="39937-114">Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesario para agregar  un componente a la topología, debe usar una cuenta que sea miembro del grupo Administradores de dominio y del grupo **RTCUniversalServerAdmins,** y que tenga permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Skype Empresarial Server (es decir, para que topology Builder pueda configurar las listas de control de acceso discrecional (DACL) necesarias o una cuenta con derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="39937-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="39937-115">Inicie el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="39937-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="39937-116">En el árbol de consola, explore el grupo de servidores front-end en los que ha implementado el servidor de archivado y, a continuación, haga clic en el nombre del grupo de servidores front-end al que quiere modificar las opciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="39937-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="39937-117">En el menú **Acción**, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="39937-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="39937-118">En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="39937-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="39937-119">Desplácese hacia abajo hasta **Servidor de archivado**.</span><span class="sxs-lookup"><span data-stu-id="39937-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="39937-120">En **Servidor de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39937-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="39937-121">Para cambiar a un almacén de SQL Server existente diferente, en  **Almacén SQL Server de archivado**, en el cuadro de desplegable, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39937-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="39937-122">Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.</span><span class="sxs-lookup"><span data-stu-id="39937-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="39937-123">Para especificar un nuevo almacén de SQL Server, haga clic en **Nuevo** y en el cuadro de diálogo **Definir un nuevo almacén de SQL Server** lleve a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39937-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="39937-124">Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.</span><span class="sxs-lookup"><span data-stu-id="39937-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="39937-125">Para especificar un nuevo almacén SQL Server, haga clic  en Nuevo y, a continuación, en el cuadro de diálogo Definir nuevo almacén de SQL Server, haga lo siguiente: </span><span class="sxs-lookup"><span data-stu-id="39937-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="39937-126">En **SQL Server FQDN,** especifique el FQDN del servidor en el que desea crear el nuevo SQL Server almacén.</span><span class="sxs-lookup"><span data-stu-id="39937-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="39937-127">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre** y especifique la instancia que desee usar.</span><span class="sxs-lookup"><span data-stu-id="39937-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="39937-128">Si la instancia SQL Server especificada está en una relación de creación de reflejos, active la casilla Esta instancia **SQL** está en relación de reflejo y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="39937-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="39937-129">Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39937-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="39937-130">Para usar un almacén de SQL Server existente para  la creación de reflejos, en el cuadro de lista desplegable Reflejo del almacén de SQL Server de archivado, haga clic en el nombre del almacén de SQL Server que desea usar para la creación de reflejos.</span><span class="sxs-lookup"><span data-stu-id="39937-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="39937-131">Para especificar un nuevo almacén SQL Server para creación de reflejos, haga clic en Nuevo y, a continuación, en el cuadro de diálogo Definir nuevo almacén de **SQL Server,** realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="39937-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="39937-132">a.</span><span class="sxs-lookup"><span data-stu-id="39937-132">a.</span></span> <span data-ttu-id="39937-133">En **SQL Server FQDN,** especifique el FQDN de la SQL Server en la que desea crear el nuevo SQL Server almacén.</span><span class="sxs-lookup"><span data-stu-id="39937-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="39937-134">b.</span><span class="sxs-lookup"><span data-stu-id="39937-134">b.</span></span> <span data-ttu-id="39937-135">Haga clic en **Instancia predeterminada** para utilizar la instancia predeterminada o, para especificar una instancia diferente, haga clic en **Instancia denominada** y, a continuación, haga clic en la instancia que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="39937-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="39937-136">c.</span><span class="sxs-lookup"><span data-stu-id="39937-136">c.</span></span> <span data-ttu-id="39937-137">Si la instancia SQL Server especificada está en una relación de creación de reflejos, active la casilla Esta instancia **SQL** está en relación de reflejo y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="39937-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="39937-138">Si habilita la creación de reflejos de SQL Server y desea agregar o cambiar un testigo de creación de reflejo de SQL Server (una tercera instancia independiente de SQL Server que puede detectar el estado del servidor SQL Server principal y las instancias reflejadas), active la casilla Usar testigo de creación de reflejos de SQL Server para habilitar la conmutación por error automática y, **a** continuación, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="39937-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="39937-139">a.</span><span class="sxs-lookup"><span data-stu-id="39937-139">a.</span></span> <span data-ttu-id="39937-140">En **SQL Server FQDN,** especifique el FQDN del servidor en el que desea crear el nuevo testigo de creación SQL Server reflejo.</span><span class="sxs-lookup"><span data-stu-id="39937-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="39937-141">b.</span><span class="sxs-lookup"><span data-stu-id="39937-141">b.</span></span> <span data-ttu-id="39937-142">Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="39937-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="39937-143">c.</span><span class="sxs-lookup"><span data-stu-id="39937-143">c.</span></span> <span data-ttu-id="39937-144">Si la instancia SQL Server especificada está en una relación de creación de reflejos, active la casilla Esta instancia **SQL** está en relación de reflejo y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="39937-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="39937-145">Para cambiar a la integración de Microsoft Exchange para almacenar archivos y datos de archivado en servidores exchange (si todos los usuarios de la implementación están en sus servidores exchange), elimine toda la información de las bases de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="39937-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="39937-146">Si tiene usuarios de Skype Empresarial que no están en servidores de Exchange, no elimine la SQL Server almacenar.</span><span class="sxs-lookup"><span data-stu-id="39937-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="39937-147">Para guardar la configuración, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39937-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="39937-148">Los cambios realizados en el Generador de topologías no tienen efecto hasta que se publique la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="39937-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="39937-149">Para obtener más información, consulte [Agregar bases de datos de archivado a una implementación existente en Skype Empresarial Server.](../../deploy/deploy-archiving/add-archiving-databases.md)</span><span class="sxs-lookup"><span data-stu-id="39937-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="39937-150">Cambiar la ubicación de la base de datos de archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39937-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="39937-151">En la mayoría de los casos, no será necesario cambiar la ubicación de la base de datos de archivado, que se especifica al instalar el servidor de archivado.</span><span class="sxs-lookup"><span data-stu-id="39937-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="39937-152">Sin embargo, si se produce un error de hardware u otro problema, puede apuntar el servidor de archivado a una nueva base de datos mediante el cmdlet **Set-CsArchivingServer.**</span><span class="sxs-lookup"><span data-stu-id="39937-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="39937-153">En el siguiente ejemplo se cambia la ubicación de la base de datos de archivado para el servidor de archivado ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span><span class="sxs-lookup"><span data-stu-id="39937-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="39937-154">En este ejemplo, la nueva base de datos se encuentra en ArchivingDatabase:atl-sql-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="39937-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


