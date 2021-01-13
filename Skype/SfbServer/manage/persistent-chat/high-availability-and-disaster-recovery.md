---
title: Administrar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Resumen: obtenga información sobre cómo administrar la alta disponibilidad y la recuperación ante desastres del servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 7ec7182d8fe2866499f731b43df712a69c44bc42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815050"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="433bb-103">Administrar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="433bb-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="433bb-104">**Resumen:** Obtenga información sobre cómo administrar la alta disponibilidad y la recuperación ante desastres del servidor de chat persistente en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="433bb-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="433bb-105">En este tema se describe cómo conmutar por error y conmutar por recuperación el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="433bb-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="433bb-106">Antes de leer este tema, asegúrese de leer [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="433bb-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="433bb-107">El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="433bb-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="433bb-108">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="433bb-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="433bb-109">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="433bb-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="433bb-110">Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="433bb-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="433bb-111">Conmutación por error del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="433bb-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="433bb-112">La conmutación por error para el servidor de chat persistente está diseñada para ser principalmente un proceso manual.</span><span class="sxs-lookup"><span data-stu-id="433bb-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="433bb-113">El procedimiento de conmutación por error se basa en la suposición de que el centro de datos secundario está en funcionamiento, pero los servicios del servidor de chat persistente donde se encuentra la base de datos de chat persistente principal no están completamente disponibles, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="433bb-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="433bb-114">La base de datos principal del servidor de chat persistente y la base de datos reflejada del servidor de chat persistente están sin servicio.</span><span class="sxs-lookup"><span data-stu-id="433bb-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="433bb-115">El servidor front-end de Skype Empresarial Server no está disponible.</span><span class="sxs-lookup"><span data-stu-id="433bb-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="433bb-116">El procedimiento se basa en dos pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="433bb-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="433bb-117">Recupere la base de datos de chat persistente principal (mgc).</span><span class="sxs-lookup"><span data-stu-id="433bb-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="433bb-118">La creación de reflejos para la nueva base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="433bb-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="433bb-119">La base de datos de cumplimiento de chat persistente (mgccomp) no se ha conversado.</span><span class="sxs-lookup"><span data-stu-id="433bb-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="433bb-120">Los contenidos de esta base de datos son transitorios y se purgan cuando el adaptador de conformidad procesa los datos.</span><span class="sxs-lookup"><span data-stu-id="433bb-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="433bb-121">Es su responsabilidad, como administrador de chat persistente, administrar correctamente la salida del adaptador para evitar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="433bb-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="433bb-122">Para conmutar por error el servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="433bb-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="433bb-123">Quite el trasvase de registros de la base de datos de trasvase de registros de copia de seguridad del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="433bb-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="433bb-124">Mediante SQL Server Management Studio, conéctese a la instancia de base de datos donde se encuentra la base de datos mgc de copia de seguridad del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="433bb-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="433bb-125">Abra una ventana de consulta en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="433bb-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="433bb-126">Utilice el siguiente comando para colocar el trasvase de registros:</span><span class="sxs-lookup"><span data-stu-id="433bb-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="433bb-127">Copie cualquier archivo de copia de seguridad no copiado desde el recurso compartido de copia de seguridad a la carpeta de destino de copias del servidor de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="433bb-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="433bb-128">Aplique cualquier copia de seguridad de registro de transacciones no aplicadas en secuencia con la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="433bb-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="433bb-129">Para obtener más información, [consulte How to: Apply a Transaction Log Backup (Transact-SQL).](https://go.microsoft.com/fwlink/p/?linkid=247428)</span><span class="sxs-lookup"><span data-stu-id="433bb-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="433bb-p105">Publique en línea la base de datos mgc de copia de seguridad. Utilizando la ventana de consultas que se abre en el paso 1b, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="433bb-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="433bb-132">Finalice todas las conexiones a la base de datos mgc, si existe alguna:</span><span class="sxs-lookup"><span data-stu-id="433bb-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="433bb-133">**exec sp_who2** para identificar las conexiones a la base de datos mgc.</span><span class="sxs-lookup"><span data-stu-id="433bb-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="433bb-134">**kill \<spid\>** para finalizar estas conexiones.</span><span class="sxs-lookup"><span data-stu-id="433bb-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="433bb-135">Publique en línea la base de datos:</span><span class="sxs-lookup"><span data-stu-id="433bb-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="433bb-136">**restaurar base de datos mgc con recuperación.**</span><span class="sxs-lookup"><span data-stu-id="433bb-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="433bb-137">En el Shell de administración de Skype Empresarial Server, use el comando **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** para conmutar por error a la base de datos de copia de seguridad mgc.</span><span class="sxs-lookup"><span data-stu-id="433bb-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="433bb-138">Asegúrese de sustituir el nombre de dominio completo del grupo de chat persistente por atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="433bb-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="433bb-139">La base de datos de copia de seguridad mgc funciona actualmente como base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="433bb-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="433bb-140">En el Shell de administración de Skype Empresarial Server, use el cmdlet **Install-CsMirrorDatabase** para establecer un reflejo de alta disponibilidad para la base de datos de copia de seguridad que ahora sirve como base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="433bb-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="433bb-141">Utilice la instancia de la base de datos de copia de seguridad como base de datos principal y la instancia de la base de datos reflejada de copia de seguridad como instancia reflejada.</span><span class="sxs-lookup"><span data-stu-id="433bb-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="433bb-142">Este no es el mismo reflejo de lo que se configuró inicialmente para la base de datos principal durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="433bb-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="433bb-143">Establezca los servidores activos del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="433bb-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="433bb-144">Desde el Shell de administración de Skype Empresarial Server, use el cmdlet **Set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.</span><span class="sxs-lookup"><span data-stu-id="433bb-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="433bb-145">Todos los servidores activos deben estar ubicados dentro del mismo centro de datos como la nueva base de datos principal o en un centro de datos que tenga una latencia baja o un ancho de banda alto.</span><span class="sxs-lookup"><span data-stu-id="433bb-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="433bb-146">En este punto, la conmutación por error de la base de datos principal del servidor de chat persistente a la base de datos de copia de seguridad del servidor de chat persistente finaliza correctamente.</span><span class="sxs-lookup"><span data-stu-id="433bb-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="433bb-147">Conmutación por recuperación del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="433bb-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="433bb-148">En este procedimiento se describen los pasos necesarios para recuperarse de un error del servidor de chat persistente y para restablecer las operaciones desde el centro de datos principal.</span><span class="sxs-lookup"><span data-stu-id="433bb-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="433bb-149">Durante el error del servidor de chat persistente, el centro de datos principal sufre una interrupción completa y las bases de datos principal y reflejada no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="433bb-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="433bb-150">El centro de datos principal se conmuta por error al servidor de reserva.</span><span class="sxs-lookup"><span data-stu-id="433bb-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="433bb-151">En el siguiente procedimiento, se restaura el funcionamiento normal después de realizar una copia de seguridad del centro de datos principal y volver a generar los servidores.</span><span class="sxs-lookup"><span data-stu-id="433bb-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="433bb-152">El procedimiento presupone que el centro de datos principal se ha recuperado de una interrupción total y que la base de datos mgc y la base de datos mgccomp se han vuelto a generar y volver a instalar mediante el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="433bb-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="433bb-153">El procedimiento también supone que no se implementaron servidores reflejados y de copia de seguridad nuevos durante el período de conmutación por error y que el único servidor implementado es el servidor de copia de seguridad y su servidor reflejado, tal como se definió anteriormente en El servidor de conmutación por error de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="433bb-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="433bb-154">Estos pasos están pensados para recuperar la configuración tal y como estaba antes del desastre, lo que resulta en la conmutación por error del servidor principal al servidor de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="433bb-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="433bb-155">Borre todos los servidores de la lista Active Server del servidor de chat persistente con el cmdlet **Set-CsPersistentChatActiveServer** desde el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="433bb-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="433bb-156">Esto impide que todos los servidores de chat persistente se conecten a la base de datos mgc y a la base de datos mgccomp durante la conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="433bb-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="433bb-157">El SQL Server en el servidor back-end secundario del servidor de chat persistente debe ejecutarse con una cuenta con privilegios.</span><span class="sxs-lookup"><span data-stu-id="433bb-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="433bb-158">En concreto, la cuenta debe incluir:</span><span class="sxs-lookup"><span data-stu-id="433bb-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="433bb-159">Acceso de lectura al recurso compartido de red en el que están las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="433bb-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="433bb-160">Acceso de escritura al directorio local en el que las copias de seguridad se copien.</span><span class="sxs-lookup"><span data-stu-id="433bb-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="433bb-161">Deshabilitación de la creación de reflejos en la base de datos mgc de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="433bb-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="433bb-162">Con SQL Server Management Studio, conéctese a la instancia mgc de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="433bb-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="433bb-163">Haga clic con el botón secundario en la base de datos mgc, apunte a **Tareas** y, a continuación, haga clic en **Reflejo**.</span><span class="sxs-lookup"><span data-stu-id="433bb-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="433bb-164">Haga clic en **Eliminar creación de reflejos**.</span><span class="sxs-lookup"><span data-stu-id="433bb-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="433bb-165">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="433bb-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="433bb-166">Lleve a cabo los mismos pasos con la base de datos mgccomp.</span><span class="sxs-lookup"><span data-stu-id="433bb-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="433bb-167">Realice una copia de seguridad de la base de datos mgc de modo que se pueda restaurar a la nueva base de datos principal:</span><span class="sxs-lookup"><span data-stu-id="433bb-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="433bb-168">Con SQL Server Management Studio, conéctese a la instancia mgc de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="433bb-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="433bb-p113">Haga clic con el botón secundario a la base de datos mgc, apunte a **Tareas** y, a continuación, haga clic en **Copia de seguridad**. Aparecerá el cuadro de diálogo de la **Base de datos de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="433bb-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="433bb-171">En **Tipo de copia de seguridad**, seleccione **Completo**.</span><span class="sxs-lookup"><span data-stu-id="433bb-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="433bb-172">Para el **componente de copia de seguridad**, haga clic en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="433bb-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="433bb-173">Puede aceptar el nombre del conjunto de copia de seguridad predeterminado que se sugiere en **Nombre**, o bien especificar otro.</span><span class="sxs-lookup"><span data-stu-id="433bb-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="433bb-174">*\<Optional\>*  En **Descripción,** escriba una descripción del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="433bb-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="433bb-175">Elimine la ubicación de copia de seguridad predeterminada de la lista de destino.</span><span class="sxs-lookup"><span data-stu-id="433bb-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="433bb-p114">Agregue un archivo a la lista por medio de la ruta de acceso a la ubicación del recurso compartido que haya definido para el trasvase de registros. Esta ruta se encuentra disponible tanto para la base de datos principal como para la de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="433bb-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="433bb-178">Haga clic en **Aceptar** para cerrar el cuadro de diálogo e iniciar el proceso de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="433bb-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="433bb-179">Restaure la base de datos principal a partir de la copia de seguridad creada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="433bb-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="433bb-180">Mediante SQL Server Management Studio, conéctese a la instancia mgc principal.</span><span class="sxs-lookup"><span data-stu-id="433bb-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="433bb-p115">Haga doble clic con el botón secundario en la base de datos mgc, apunte a **Tareas**, apunte a **Restaurar** y, a continuación, haga clic en **Base de datos**. Aparecerá el cuadro de diálogo **Restaurar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="433bb-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="433bb-183">Seleccione **Desde dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="433bb-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="433bb-p116">Haga clic en el botón Examinar, que abre el cuadro de diálogo **Especificar copia de seguridad**. En **Medio para copia de seguridad**, seleccione **Archivo**. Haga clic en **Agregar**, seleccione el archivo de copia de seguridad que creó en el paso 3 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="433bb-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="433bb-187">Seleccione la copia de seguridad en **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**.</span><span class="sxs-lookup"><span data-stu-id="433bb-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="433bb-188">Haga clic en **Opciones** en el panel **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="433bb-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="433bb-189">En **Restaurar opciones**, seleccione **Sobrescribir la base de datos existente**.</span><span class="sxs-lookup"><span data-stu-id="433bb-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="433bb-190">En **Estado de recuperación**, seleccione **Dejar la base de datos lista para usar**.</span><span class="sxs-lookup"><span data-stu-id="433bb-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="433bb-191">Haga clic en **Aceptar** para iniciar el proceso de restauración.</span><span class="sxs-lookup"><span data-stu-id="433bb-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="433bb-192">Configure SQL Server trasvase de registros para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="433bb-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="433bb-193">Siga los procedimientos descritos en [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) para establecer el trasvase de registros para la base de datos mgc principal.</span><span class="sxs-lookup"><span data-stu-id="433bb-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="433bb-194">Establezca los servidores activos del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="433bb-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="433bb-195">Desde el Shell de administración de Skype Empresarial Server, use el cmdlet **Set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.</span><span class="sxs-lookup"><span data-stu-id="433bb-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="433bb-196">Todos los servidores activos deben estar ubicados dentro del mismo centro de datos como la nueva base de datos principal o en un centro de datos que tenga una latencia baja o un ancho de banda alto.</span><span class="sxs-lookup"><span data-stu-id="433bb-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="433bb-197">Para restaurar el grupo a su estado normal, ejecute el siguiente Windows PowerShell comando:</span><span class="sxs-lookup"><span data-stu-id="433bb-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="433bb-198">Para obtener más información, consulte el tema de ayuda del cmdlet [Set-CsPersistentChatState.](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="433bb-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

