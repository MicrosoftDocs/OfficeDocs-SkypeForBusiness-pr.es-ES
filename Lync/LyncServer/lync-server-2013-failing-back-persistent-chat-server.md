---
title: 'Lync Server 2013: Conmutación por recuperación de servidor de chat persistente'
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
ms.openlocfilehash: ca00a71c88b917b9e59f2e9039e7960b51f64157
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="44390-102">Conmutación por recuperación de servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44390-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44390-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="44390-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="44390-104">Este procedimiento indica los pasos necesarios para recuperarse de un error del servidor de chat persistente y para restablecer las operaciones desde el centro de datos principal.</span><span class="sxs-lookup"><span data-stu-id="44390-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="44390-105">Durante un error de servidor de chat persistente, el centro de datos principal sufre una interrupción completa y las bases de datos principal y reflejada dejan de estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="44390-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="44390-106">El centro de datos principal se conmuta por error al servidor de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="44390-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="44390-107">En el siguiente procedimiento, se restaura el funcionamiento normal después de realizar una copia de seguridad del centro de datos principal y volver a generar los servidores.</span><span class="sxs-lookup"><span data-stu-id="44390-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="44390-108">El procedimiento presupone que el centro de datos principal se ha recuperado de la interrupción total y que la base de datos MGC y la base de datos mgccomp se han reconstruido y vuelto a instalar con el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="44390-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="44390-109">El procedimiento también presupone que no se han implementado nuevos servidores de reflejo y copia de seguridad durante el período de conmutación por error y que el único servidor implementado es el servidor de copia de seguridad y su servidor reflejado, según se define en [conmutación por error en el servidor de chat persistente en Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="44390-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="44390-110">Estos pasos están pensados para recuperar la configuración tal y como estaba antes del desastre, lo que resulta en la conmutación por error del servidor principal al servidor de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="44390-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="44390-111">Para recuperar el servidor de la conversación persistente</span><span class="sxs-lookup"><span data-stu-id="44390-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="44390-112">Borre todos los servidores de la lista de servidores activa del servidor de chat `Set-CsPersistentChatActiveServer` persistente mediante el cmdlet del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44390-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="44390-113">Esto impide que todos los servidores de chat persistentes se conecten a la base de datos MGC y la base de datos mgccomp durante la conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="44390-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="44390-114">El Agente SQL Server en el servidor de back-end de la mensajería instantánea secundaria debe estar ejecutándose en una cuenta privilegiada.</span><span class="sxs-lookup"><span data-stu-id="44390-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="44390-115">En concreto, la cuenta debe incluir:</span><span class="sxs-lookup"><span data-stu-id="44390-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="44390-116">Acceso de lectura al recurso compartido de red en el que están las copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="44390-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="44390-117">Acceso de escritura al directorio local específico en el que las copias de seguridad se copian</span><span class="sxs-lookup"><span data-stu-id="44390-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="44390-118">Deshabilite la creación de reflejo en la base de datos mgc de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="44390-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="44390-119">Con SQL Server Management Studio, conéctese a la instancia de la copia de seguridad MGC.</span><span class="sxs-lookup"><span data-stu-id="44390-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="44390-120">Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas** y, luego, haga clic en **Reflejo**.</span><span class="sxs-lookup"><span data-stu-id="44390-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="44390-121">Haga clic en **Quitar creación de reflejo**.</span><span class="sxs-lookup"><span data-stu-id="44390-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="44390-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="44390-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="44390-123">Lleve a cabo los mismos pasos con la base de datos mgccomp.</span><span class="sxs-lookup"><span data-stu-id="44390-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="44390-124">Realice una copia de seguridad de la base de datos mgc, de modo que se pueda restaurar a la nueva base de datos principal:</span><span class="sxs-lookup"><span data-stu-id="44390-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="44390-125">Con SQL Server Management Studio, conéctese a la instancia de la copia de seguridad MGC.</span><span class="sxs-lookup"><span data-stu-id="44390-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="44390-p105">Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas** y, luego, haga clic en **Copia de seguridad**. Aparecerá el cuadro de diálogo de la **Base de datos de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="44390-p105">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="44390-128">En **Tipo de copia de seguridad**, seleccione **Completo**.</span><span class="sxs-lookup"><span data-stu-id="44390-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="44390-129">Para el **Componente de copia de seguridad**, haga clic en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="44390-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="44390-130">Puede aceptar el nombre del conjunto de copia de seguridad predeterminado que se sugiere en **Nombre**, o bien especificar otro.</span><span class="sxs-lookup"><span data-stu-id="44390-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="44390-131">\* \<Opcional\> \* En **Descripción**, escriba una descripción para el conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="44390-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="44390-132">Elimine la ubicación de copia de seguridad predeterminada de la lista de destino.</span><span class="sxs-lookup"><span data-stu-id="44390-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="44390-p106">Agregue un archivo a la lista por medio de la ruta de acceso a la ubicación del recurso compartido que haya definido para el trasvase de registros. Esta ruta se encuentra disponible tanto para la base de datos principal como para la de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="44390-p106">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="44390-135">Haga clic en **Aceptar** para cerrar el cuadro de diálogo e iniciar el proceso de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="44390-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="44390-136">Restaure la base de datos principal a partir de la copia de seguridad creada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="44390-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="44390-137">Con SQL Server Management Studio, conéctese a la instancia de MGC principal.</span><span class="sxs-lookup"><span data-stu-id="44390-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="44390-p107">Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas**, **Restaurar** y, luego, haga clic en **Base de datos**. Aparecerá el cuadro de diálogo **Restaurar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="44390-p107">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="44390-140">Seleccione **Desde dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="44390-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="44390-p108">Haga clic en el botón Examinar, que abre el cuadro de diálogo **Especificar copia de seguridad**. En **Medio para copia de seguridad**, seleccione **Archivo**. Haga clic en **Agregar**, seleccione el archivo de copia de seguridad que creó en el paso 3 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="44390-p108">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="44390-144">En **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**, seleccione la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="44390-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="44390-145">Haga clic en **Opciones** en el panel **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="44390-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="44390-146">En **Restaurar opciones**, seleccione **Sobrescribir la base de datos existente**.</span><span class="sxs-lookup"><span data-stu-id="44390-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="44390-147">En **Estado de recuperación**, seleccione **Dejar la base de datos lista para su uso**.</span><span class="sxs-lookup"><span data-stu-id="44390-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="44390-148">Haga clic en **Aceptar** para iniciar el proceso de restauración.</span><span class="sxs-lookup"><span data-stu-id="44390-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="44390-149">Configure el trasvase de registros de SQL Server para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="44390-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="44390-150">Siga los procedimientos que se describen en [configurar el servidor de chat persistente para una alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) para establecer el trasvase de registros para la base de datos principal de MGC.</span><span class="sxs-lookup"><span data-stu-id="44390-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="44390-151">Configure los servidores activos del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="44390-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="44390-152">Desde el shell de administración de Lync Server, use el cmdlet **set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.</span><span class="sxs-lookup"><span data-stu-id="44390-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="44390-153">Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44390-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="44390-154">Para restaurar el grupo a su estado normal, ejecute el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="44390-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="44390-155">Consulte el tema de ayuda sobre el cmdlet [set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="44390-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

