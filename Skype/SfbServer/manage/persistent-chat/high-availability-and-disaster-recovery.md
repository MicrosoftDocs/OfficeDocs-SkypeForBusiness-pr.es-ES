---
title: Administrar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Resumen: Obtenga información sobre cómo administrar el servidor de Chat persistente alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015.'
ms.openlocfilehash: b7c898be275a4a3642eae88412a14686b258130f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232685"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="303ed-103">Administrar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="303ed-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="303ed-104">**Resumen:** Obtenga información sobre cómo administrar el servidor de Chat persistente alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="303ed-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="303ed-105">En este tema se describe cómo conmutar por error y se producirá un error en servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="303ed-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="303ed-106">Antes de leer este tema, asegúrese de leer [planeación de alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) y [Configure una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para 2015 empresariales de servidor](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="303ed-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="303ed-107">Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="303ed-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="303ed-108">La misma funcionalidad está disponible en los equipos.</span><span class="sxs-lookup"><span data-stu-id="303ed-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="303ed-109">Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="303ed-109">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="303ed-110">Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="303ed-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="303ed-111">Conmutar por error servidor de Chat persistente</span><span class="sxs-lookup"><span data-stu-id="303ed-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="303ed-112">Conmutación por error para el servidor de Chat persistente está diseñada para ser principalmente un proceso manual.</span><span class="sxs-lookup"><span data-stu-id="303ed-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="303ed-113">El procedimiento de conmutación por error se basa en la suposición de que el centro de datos secundario es copia de seguridad y que se está ejecutando, pero los servicios de servidor de Chat persistente donde se encuentra la base de datos principal de Chat persistente no están completamente disponibles, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="303ed-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="303ed-114">Persistent base de datos principal del servidor de Chat y base de datos de servidor de Chat persistente reflejada están inactivos.</span><span class="sxs-lookup"><span data-stu-id="303ed-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="303ed-115">Skype para Business Server Front-End Server está inactivo.</span><span class="sxs-lookup"><span data-stu-id="303ed-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="303ed-116">El procedimiento se basa en dos pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="303ed-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="303ed-117">Recuperar el Chat persistente base de datos principal (mgc).</span><span class="sxs-lookup"><span data-stu-id="303ed-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="303ed-118">Establecer la creación de reflejo para la nueva base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="303ed-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="303ed-119">El Chat persistente base de datos cumplimiento (mgccomp) no se conmuta por error.</span><span class="sxs-lookup"><span data-stu-id="303ed-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="303ed-120">El contenido de esta base de datos es transitorio y se purga cuando el adaptador de cumplimiento procesa los datos.</span><span class="sxs-lookup"><span data-stu-id="303ed-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="303ed-121">Es su responsabilidad, como administrador de Chat persistente, para administrar correctamente la salida del adaptador para evitar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="303ed-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="303ed-122">Para llevar a cabo la conmutación por error del servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="303ed-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="303ed-123">Quitar trasvase de registros de la base de datos Persistent Chat Server copia de seguridad del trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="303ed-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="303ed-124">Con SQL Server Management Studio, conéctese a la instancia de base de datos donde se encuentra la base de datos de CGM de copia de seguridad del servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="303ed-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="303ed-125">Abra una ventana de consulta en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="303ed-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="303ed-126">Utilice el siguiente comando para colocar el trasvase de registros:</span><span class="sxs-lookup"><span data-stu-id="303ed-126">Use the following command to drop log shipping:</span></span>
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="303ed-127">Copie cualquier archivo de copia de seguridad no copiado desde el recurso compartido de copia de seguridad a la carpeta de destino de copias del servidor de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="303ed-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="303ed-128">Aplique cualquier copia de seguridad de registro de transacciones no aplicadas en secuencia a la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="303ed-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="303ed-129">Para obtener información detallada, vea [Cómo: aplicar una copia de seguridad del registro de transacciones (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="303ed-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="303ed-p105">Publique en línea la base de datos mgc de copia de seguridad. Utilizando la ventana de consultas que se abre en el paso 1b, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="303ed-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="303ed-132">Finalice todas las conexiones a la base de datos mgc, si existe alguna:</span><span class="sxs-lookup"><span data-stu-id="303ed-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="303ed-133">**exec sp_who2** identifica las conexiones a la base de datos mgc.</span><span class="sxs-lookup"><span data-stu-id="303ed-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="303ed-134">\*\*kill \<spid\> \*\* para finalizar estas conexiones.</span><span class="sxs-lookup"><span data-stu-id="303ed-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="303ed-135">Publique en línea la base de datos:</span><span class="sxs-lookup"><span data-stu-id="303ed-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="303ed-136">**Restaurar la base de datos mgc con la recuperación**.</span><span class="sxs-lookup"><span data-stu-id="303ed-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="303ed-137">En Skype para Shell de administración de servidor empresarial, use el comando **Set-CsPersistentChatState-Identity "service: atl-cs-001.litwareinc.com" - PoolState FailedOver** para conmutar por error a la base de datos de copia de seguridad de CGM.</span><span class="sxs-lookup"><span data-stu-id="303ed-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="303ed-138">No olvide sustituir el nombre de dominio completo del grupo de chat persistente por atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="303ed-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="303ed-139">La base de datos de copia de seguridad mgc funciona actualmente como base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="303ed-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="303ed-140">En Skype para Shell de administración de servidor empresarial, use el cmdlet **Install-CsMirrorDatabase** para establecer un reflejo de alta disponibilidad para la base de datos de copia de seguridad que ahora sirve como la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="303ed-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="303ed-141">Utilice la instancia de la base de datos de copia de seguridad como base de datos principal y la instancia de la base de datos reflejada de copia de seguridad como instancia reflejada.</span><span class="sxs-lookup"><span data-stu-id="303ed-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="303ed-142">Este no es el mismo reflejo de lo que se configuró inicialmente para la base de datos principal durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="303ed-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="303ed-143">Establecer los servidores activos del servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="303ed-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="303ed-144">De Skype para Shell de administración de servidor empresarial, use el cmdlet **Set-CsPersistentChatActiveServer** para establecer la lista de servidores de activos.</span><span class="sxs-lookup"><span data-stu-id="303ed-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="303ed-145">Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="303ed-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="303ed-146">En este momento, la conmutación por error desde la base de datos principal de servidor de Chat persistente a la base de datos de copia de seguridad de servidor de Chat persistente se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="303ed-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="303ed-147">Producirá un error en servidor de Chat persistente</span><span class="sxs-lookup"><span data-stu-id="303ed-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="303ed-148">Este procedimiento describe los pasos necesarios para recuperarse de un error del servidor de Chat persistente y restablecer las operaciones desde el centro de datos principal.</span><span class="sxs-lookup"><span data-stu-id="303ed-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="303ed-149">Durante errores del servidor de Chat persistente, el centro de datos principal sufre una interrupción completa y la principal y bases de datos reflejadas dejan de estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="303ed-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="303ed-150">El centro de datos principal se conmuta por error al servidor de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="303ed-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="303ed-151">En el siguiente procedimiento, se restaura el funcionamiento normal después de realizar una copia de seguridad del centro de datos principal y volver a generar los servidores.</span><span class="sxs-lookup"><span data-stu-id="303ed-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="303ed-152">El procedimiento se supone que se ha recuperado el centro de datos principal de interrupción total, y que la base de datos de CGM y la base de datos mgccomp se han reconstrucción y volver a instalar mediante el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="303ed-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="303ed-153">También se da por hecho que no se ha implementado ningún servidor reflejado ni de copia de seguridad nuevo durante el período de conmutación por error y, asimismo, que el único servidor implementado es el de copia de seguridad y su servidor reflejado, tal como se especificó anteriormente en Conmutación por error del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="303ed-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="303ed-154">Estos pasos están pensados para recuperar la configuración tal y como estaba antes del desastre, lo que resulta en la conmutación por error del servidor principal al servidor de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="303ed-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="303ed-155">Borrar todos los servidores de la lista de Persistent Chat Server Active Server mediante el cmdlet **Set-CsPersistentChatActiveServer** desde el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="303ed-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="303ed-156">Esto detiene todos los servidores de Chat persistente de conectarse a la base de datos de CGM y la base de datos mgccomp durante la conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="303ed-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="303ed-157">El agente de SQL Server en el servidor secundario Persistent Chat Server servidor Back-End se debe ejecutar bajo una cuenta con privilegios.</span><span class="sxs-lookup"><span data-stu-id="303ed-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="303ed-158">En concreto, la cuenta debe incluir:</span><span class="sxs-lookup"><span data-stu-id="303ed-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="303ed-159">Acceso de lectura al recurso compartido de red en el que están las copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="303ed-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="303ed-160">Acceso de escritura al directorio local específico en el que las copias de seguridad se copian</span><span class="sxs-lookup"><span data-stu-id="303ed-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="303ed-161">Deshabilite la creación de reflejo en la base de datos mgc de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="303ed-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="303ed-162">Mediante SQL Server Management Studio, conéctese a la instancia mgc de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="303ed-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="303ed-163">Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas** y, luego, haga clic en **Reflejo**.</span><span class="sxs-lookup"><span data-stu-id="303ed-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="303ed-164">Haga clic en **Quitar creación de reflejo**.</span><span class="sxs-lookup"><span data-stu-id="303ed-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="303ed-165">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="303ed-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="303ed-166">Lleve a cabo los mismos pasos con la base de datos mgccomp.</span><span class="sxs-lookup"><span data-stu-id="303ed-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="303ed-167">Realice una copia de seguridad de la base de datos mgc, de modo que se pueda restaurar a la nueva base de datos principal:</span><span class="sxs-lookup"><span data-stu-id="303ed-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="303ed-168">Mediante SQL Server Management Studio, conéctese a la instancia mgc de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="303ed-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="303ed-p113">Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas** y, luego, haga clic en **Copia de seguridad**. Aparecerá el cuadro de diálogo de la **Base de datos de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="303ed-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="303ed-171">En **Tipo de copia de seguridad**, seleccione **Completo**.</span><span class="sxs-lookup"><span data-stu-id="303ed-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="303ed-172">Para el **Componente de copia de seguridad**, haga clic en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="303ed-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="303ed-173">Puede aceptar el nombre del conjunto de copia de seguridad predeterminado que se sugiere en **Nombre**, o bien especificar otro.</span><span class="sxs-lookup"><span data-stu-id="303ed-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="303ed-174">\* \<Opcional\> \*  En **Descripción**, escriba una descripción del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="303ed-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="303ed-175">Elimine la ubicación de copia de seguridad predeterminada de la lista de destino.</span><span class="sxs-lookup"><span data-stu-id="303ed-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="303ed-p114">Agregue un archivo a la lista por medio de la ruta de acceso a la ubicación del recurso compartido que haya definido para el trasvase de registros. Esta ruta se encuentra disponible tanto para la base de datos principal como para la de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="303ed-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="303ed-178">Haga clic en **Aceptar** para cerrar el cuadro de diálogo e iniciar el proceso de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="303ed-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="303ed-179">Restaure la base de datos principal a partir de la copia de seguridad creada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="303ed-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="303ed-180">Mediante SQL Server Management Studio, conéctese a la instancia mgc principal.</span><span class="sxs-lookup"><span data-stu-id="303ed-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="303ed-p115">Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas**, **Restaurar** y, luego, haga clic en **Base de datos**. Aparecerá el cuadro de diálogo **Restaurar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="303ed-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="303ed-183">Seleccione **Desde dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="303ed-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="303ed-p116">Haga clic en el botón Examinar, que abre el cuadro de diálogo **Especificar copia de seguridad**. En **Medio para copia de seguridad**, seleccione **Archivo**. Haga clic en **Agregar**, seleccione el archivo de copia de seguridad que creó en el paso 3 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="303ed-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="303ed-187">En **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**, seleccione la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="303ed-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="303ed-188">Haga clic en **Opciones** en el panel **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="303ed-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="303ed-189">En **Restaurar opciones**, seleccione **Sobrescribir la base de datos existente**.</span><span class="sxs-lookup"><span data-stu-id="303ed-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="303ed-190">En **Estado de recuperación**, seleccione **Dejar la base de datos lista para su uso**.</span><span class="sxs-lookup"><span data-stu-id="303ed-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="303ed-191">Haga clic en **Aceptar** para iniciar el proceso de restauración.</span><span class="sxs-lookup"><span data-stu-id="303ed-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="303ed-192">Configure el trasvase de registros de SQL Server para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="303ed-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="303ed-193">Siga los procedimientos descritos en [Configure una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) para establecer el trasvase de registros para la base de datos mgc principal.</span><span class="sxs-lookup"><span data-stu-id="303ed-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="303ed-194">Establecer los servidores activos del servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="303ed-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="303ed-195">De Skype para Shell de administración de servidor empresarial, use el cmdlet **Set-CsPersistentChatActiveServer** para establecer la lista de servidores de activos.</span><span class="sxs-lookup"><span data-stu-id="303ed-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="303ed-196">Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="303ed-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="303ed-197">Para restaurar el grupo de servidores a su estado normal, ejecute el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="303ed-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="303ed-198">Para más información, consulte el tema de ayuda para el cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="303ed-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

