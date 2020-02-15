---
title: 'Lync Server 2013: conmutación por recuperación de servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7a0e7bef65773c20c5d97a1b625d2ef39255f64
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="da61c-102">Conmutación por recuperación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da61c-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da61c-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="da61c-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="da61c-104">Este procedimiento describe los pasos necesarios para recuperarse de un error del servidor de chat persistente y para restablecer las operaciones desde el centro de datos principal.</span><span class="sxs-lookup"><span data-stu-id="da61c-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="da61c-105">Durante un error del servidor de chat persistente, el centro de datos principal sufre una interrupción completa y las bases de datos principal y reflejada dejan de estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="da61c-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="da61c-106">El centro de datos principal se conmuta por error al servidor de reserva.</span><span class="sxs-lookup"><span data-stu-id="da61c-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="da61c-107">En el siguiente procedimiento, se restaura el funcionamiento normal después de realizar una copia de seguridad del centro de datos principal y volver a generar los servidores.</span><span class="sxs-lookup"><span data-stu-id="da61c-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="da61c-108">El procedimiento presupone que el centro de datos principal se ha recuperado de la interrupción total, y que la base de datos de MGC y la base de datos de mgccomp se han reconstruido y reinstalado mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="da61c-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="da61c-109">El procedimiento también presupone que no se han implementado nuevos servidores de reflejo y copia de seguridad durante el período de conmutación por error y que el único servidor implementado es el servidor de copia de seguridad y su servidor reflejado, tal como se define en [conmutar por error en el servidor de chat persistente en Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="da61c-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="da61c-110">Estos pasos están pensados para recuperar la configuración tal y como estaba antes del desastre, lo que resulta en la conmutación por error del servidor principal al servidor de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="da61c-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="da61c-111">Para conmutar por recuperación el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="da61c-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="da61c-112">Borre todos los servidores de la lista de servidores activos del servidor de chat `Set-CsPersistentChatActiveServer` persistente con el cmdlet del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da61c-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="da61c-113">Esto impide que todos los servidores de chat persistente se conecten a la base de datos MGC y a la base de datos mgccomp durante la conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="da61c-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="da61c-114">El Agente SQL Server en el servidor back-end del servidor de chat persistente secundario debe ejecutarse en una cuenta privilegiada.</span><span class="sxs-lookup"><span data-stu-id="da61c-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="da61c-115">En concreto, la cuenta debe incluir:</span><span class="sxs-lookup"><span data-stu-id="da61c-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="da61c-116">Acceso de lectura al recurso compartido de red en el que están las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="da61c-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="da61c-117">Acceso de escritura al directorio local en el que las copias de seguridad se copien.</span><span class="sxs-lookup"><span data-stu-id="da61c-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="da61c-118">Deshabilitación de la creación de reflejos en la base de datos mgc de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="da61c-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="da61c-119">Mediante SQL Server Management Studio, conéctese a la instancia de copia de seguridad MGC.</span><span class="sxs-lookup"><span data-stu-id="da61c-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="da61c-120">Haga clic con el botón secundario en la base de datos mgc, apunte a **Tareas** y, a continuación, haga clic en **Reflejo**.</span><span class="sxs-lookup"><span data-stu-id="da61c-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="da61c-121">Haga clic en **Eliminar creación de reflejos**.</span><span class="sxs-lookup"><span data-stu-id="da61c-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="da61c-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da61c-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="da61c-123">Lleve a cabo los mismos pasos con la base de datos mgccomp.</span><span class="sxs-lookup"><span data-stu-id="da61c-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="da61c-124">Realice una copia de seguridad de la base de datos mgc de modo que se pueda restaurar a la nueva base de datos principal:</span><span class="sxs-lookup"><span data-stu-id="da61c-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="da61c-125">Mediante SQL Server Management Studio, conéctese a la instancia de copia de seguridad MGC.</span><span class="sxs-lookup"><span data-stu-id="da61c-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="da61c-p105">Haga clic con el botón secundario a la base de datos mgc, apunte a **Tareas** y, a continuación, haga clic en **Copia de seguridad**. Aparecerá el cuadro de diálogo de la **Base de datos de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="da61c-p105">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="da61c-128">En **Tipo de copia de seguridad**, seleccione **Completo**.</span><span class="sxs-lookup"><span data-stu-id="da61c-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="da61c-129">Para el **componente de copia de seguridad**, haga clic en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="da61c-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="da61c-130">Puede aceptar el nombre del conjunto de copia de seguridad predeterminado que se sugiere en **Nombre**, o bien especificar otro.</span><span class="sxs-lookup"><span data-stu-id="da61c-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="da61c-131">\* \<Opcional\> \* En **Descripción**, escriba una descripción del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="da61c-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="da61c-132">Elimine la ubicación de copia de seguridad predeterminada de la lista de destino.</span><span class="sxs-lookup"><span data-stu-id="da61c-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="da61c-p106">Agregue un archivo a la lista por medio de la ruta de acceso a la ubicación del recurso compartido que haya definido para el trasvase de registros. Esta ruta se encuentra disponible tanto para la base de datos principal como para la de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="da61c-p106">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="da61c-135">Haga clic en **Aceptar** para cerrar el cuadro de diálogo e iniciar el proceso de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="da61c-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="da61c-136">Restaure la base de datos principal a partir de la copia de seguridad creada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="da61c-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="da61c-137">Mediante SQL Server Management Studio, conéctese a la instancia de MGC principal.</span><span class="sxs-lookup"><span data-stu-id="da61c-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="da61c-p107">Haga doble clic con el botón secundario en la base de datos mgc, apunte a **Tareas**, apunte a **Restaurar** y, a continuación, haga clic en **Base de datos**. Aparecerá el cuadro de diálogo **Restaurar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="da61c-p107">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="da61c-140">Seleccione **Desde dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="da61c-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="da61c-p108">Haga clic en el botón Examinar, que abre el cuadro de diálogo **Especificar copia de seguridad**. En **Medio para copia de seguridad**, seleccione **Archivo**. Haga clic en **Agregar**, seleccione el archivo de copia de seguridad que creó en el paso 3 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da61c-p108">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="da61c-144">Seleccione la copia de seguridad en **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**.</span><span class="sxs-lookup"><span data-stu-id="da61c-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="da61c-145">Haga clic en **Opciones** en el panel **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="da61c-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="da61c-146">En **Restaurar opciones**, seleccione **Sobrescribir la base de datos existente**.</span><span class="sxs-lookup"><span data-stu-id="da61c-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="da61c-147">En **Estado de recuperación**, seleccione **Dejar la base de datos lista para usar**.</span><span class="sxs-lookup"><span data-stu-id="da61c-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="da61c-148">Haga clic en **Aceptar** para iniciar el proceso de restauración.</span><span class="sxs-lookup"><span data-stu-id="da61c-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="da61c-149">Configurar el trasvase de registros de SQL Server para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="da61c-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="da61c-150">Siga los procedimientos que se describen en [Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) para establecer el trasvase de registros para la base de datos de MGC principal.</span><span class="sxs-lookup"><span data-stu-id="da61c-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="da61c-151">Establezca los servidores activos del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="da61c-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="da61c-152">Desde el shell de administración de Lync Server, use el cmdlet **set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.</span><span class="sxs-lookup"><span data-stu-id="da61c-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="da61c-153">Todos los servidores activos deben estar ubicados dentro del mismo centro de datos como la nueva base de datos principal o en un centro de datos que tenga una latencia baja o un ancho de banda alto.</span><span class="sxs-lookup"><span data-stu-id="da61c-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="da61c-154">La restauración del grupo a su estado normal ejecuta el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="da61c-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="da61c-155">Consulte el tema de ayuda del cmdlet [set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="da61c-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

