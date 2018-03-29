---
title: Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implementar implementación (instalación) un grupo de disponibilidad AlwaysOn en su Skype para Business Server.
ms.openlocfilehash: 858f8cd317ecccde315475bc6489c74d79bf72c6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-an-alwayson-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="4ce8c-103">Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4ce8c-103">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4ce8c-104">Implementar implementación (instalación) un grupo de disponibilidad AlwaysOn en su Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-104">Deploy (install) an AlwaysOn Availability Group in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="4ce8c-105">Cómo implementar un grupo de disponibilidad AlwaysOn depende de si se está implementando en un nuevo grupo, un grupo existente que utiliza espejado o un grupo existente que actualmente no tiene alta disponibilidad para la base de datos Back End.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-105">How you deploy an AlwaysOn Availability Group depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ce8c-106">No se admite el uso de un grupo de disponibilidad AlwaysOn con un rol de servidor de charla persistente.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-106">Using an AlwaysOn Availability Group with a Persistent Chat Server role is not supported.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4ce8c-107">Nombres de instancia para varias instancias del grupo de disponibilidad AlwaysOn deben ser el mismo.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-107">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
- [<span data-ttu-id="4ce8c-108">Implementar un grupo de disponibilidad AlwaysOn en un nuevo grupo front-end</span><span class="sxs-lookup"><span data-stu-id="4ce8c-108">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="4ce8c-109">Implementar un grupo de disponibilidad AlwaysOn en un grupo de servidores existente que use reflejos de bases de datos</span><span class="sxs-lookup"><span data-stu-id="4ce8c-109">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="4ce8c-110">Implementar un grupo de disponibilidad AlwaysOn en un grupo de servidores existente que no use reflejos de bases de datos</span><span class="sxs-lookup"><span data-stu-id="4ce8c-110">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-alwayson-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="4ce8c-111">Implementar un grupo de disponibilidad AlwaysOn en un nuevo grupo front-end</span><span class="sxs-lookup"><span data-stu-id="4ce8c-111">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>
<span data-ttu-id="4ce8c-112"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="4ce8c-112"></span></span>

1. <span data-ttu-id="4ce8c-113">Configurar clústeres de conmutación por error de Windows Server en todos los servidores de base de datos que formarán parte del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-113">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-114">En cada uno de los servidores, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="4ce8c-114">On each server, do the following</span></span>
    
   - <span data-ttu-id="4ce8c-115">Abra Administrador de servidores y haga clic en **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-115">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="4ce8c-p102">Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="4ce8c-118">En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-118">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="4ce8c-119">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-119">Click **Install**.</span></span>
    
2. <span data-ttu-id="4ce8c-120">Valide la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-120">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="4ce8c-121">En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-121">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="4ce8c-122">En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-122">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="4ce8c-123">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-123">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-124">Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-124">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="4ce8c-125">En el cuadro**Resumen** , revise los errores que el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-125">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="4ce8c-126">Luego haga clic en **Finalizar** para completar la validación.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-126">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="4ce8c-p104">Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="4ce8c-130">Cree el clúster.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-130">Create the cluster.</span></span>
    
   - <span data-ttu-id="4ce8c-131">En el asistente **Administración del clúster de conmutación por error**, haga clic con el botón derecho en **Administración del clúster de conmutación por error** y luego haga clic en **Crear clúster**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-131">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="4ce8c-132">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-132">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-p105">Agregue el nombre del clúster y una dirección IP. Cuando la configuración se valide, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-135">En la página Confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-135">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-136">Una vez que se cree el clúster, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-136">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="4ce8c-p106">Le recomendamos que configure el cuórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="4ce8c-139">Haga clic con el botón derecho en el nombre del clúster, haga clic en **Más acciones** y haga clic en **Configurar opciones de cuórum de clúster**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-139">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="4ce8c-140">En la página **Seleccionar opción de configuración de cuórum**, haga clic en **Seleccionar el testigo de cuórum**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-140">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="4ce8c-141">En la página **Seleccionar el testigo de cuórum**, haga clic en **Configurar un testigo de recurso compartido de archivos**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-141">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="4ce8c-142">En la página **Configurar testigo de recurso compartido de archivos**, escriba la ruta de acceso del recurso compartido de archivos que desea usar y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-142">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-143">En la página **Confirmación**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-143">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="4ce8c-144">En cada uno de los servidores en el clúster, habilite Always On en el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-144">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="4ce8c-p107">Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server. </span><span class="sxs-lookup"><span data-stu-id="4ce8c-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="4ce8c-p108">En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="4ce8c-149">Cree el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-149">Create the availability group.</span></span>
    
   - <span data-ttu-id="4ce8c-150">Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-150">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="4ce8c-p109">En Explorador de objetos, expanda la carpeta **AlwaysOn alta disponibilidad**. Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p109">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="4ce8c-153">Si aparece la página **Introducción**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-153">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-154">En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-154">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-155">En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-155">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-156">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-156">Then click **Next**.</span></span>
    
    <span data-ttu-id="4ce8c-157">No incluya el **ReportServer**, **ReportServerTempDB**o charla persistente de bases de datos en el grupo de disponibilidad AlwaysOn, ya no se admiten en este escenario.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-157">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="4ce8c-158">Puede incluir todas las demás Skype para bases de datos de Business Server en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-158">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="4ce8c-159">En la página **Especificar réplicas**, haga clic en la pestaña **Réplicas**. Después haga clic en el botón **Agregar réplicas** y conéctese a las otras instancias de SQL a las que se unió como nodos del clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-159">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="4ce8c-p112">Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="4ce8c-162">Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-162">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="4ce8c-p113">Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="4ce8c-165">Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-165">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="4ce8c-p114">En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="4ce8c-p115">Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="4ce8c-170">En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-170">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-171">En la página**Resumen** , compruebe todas las configuraciones y haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-171">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="4ce8c-172">Utilice el generador de topología para crear la agrupación de Front-End, como se explica en [crear y publicar la nueva topología en Skype para Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="4ce8c-172">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="4ce8c-173">Cuando lo haga, especifique el grupo de disponibilidad AlwaysOn como almacén de SQL para el grupo.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-173">When you do, specify the AlwaysOn Availability Group as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="4ce8c-174">Después de implementan la agrupación y el grupo de disponibilidad AlwaysOn, realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-174">After the pool and the AlwaysOn Availability Group are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="4ce8c-175">Abrir el generador de topología, seleccione **Descargar la topología de implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-175">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="4ce8c-176">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-176">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="4ce8c-177">Haga el almacén SQL del nuevo grupo de disponibilidad AlwaysOn y ** editar propiedades **.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-177">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="4ce8c-178">En la parte inferior de la página, en el cuadro **Nombre de dominio completo de SQL Server** , cambie el valor para el nombre completo del agente de escucha del grupo disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-178">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="4ce8c-p118">Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="4ce8c-183">Abra SQL Server Management Studio y vaya hasta el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-183">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-184">Conmútelo por error a una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-184">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="4ce8c-185">Abre Skype para negocios de Shell de administración de servidor y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-185">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="4ce8c-186">Repita los dos pasos anteriores (error en el grupo a una segunda réplica, luego use `Install-CsDatabase -Update`) para cada réplica en el grupo.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-186">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="4ce8c-187">Implementar un grupo de disponibilidad AlwaysOn en un grupo de servidores existente que use reflejos de bases de datos</span><span class="sxs-lookup"><span data-stu-id="4ce8c-187">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="4ce8c-188"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="4ce8c-188"></span></span>

> [!NOTE]
> <span data-ttu-id="4ce8c-189">Si el grupo que se va a actualizar a los hosts de un grupo de disponibilidad AlwaysOn la Administración Central se almacena para su organización, primero debe mover el CMS a otro grupo antes de actualizar este grupo.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-189">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="4ce8c-190">Use el cmdlet Move-CsManagementServer para mover el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-190">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="4ce8c-191">Si no tiene otro grupo en su organización, puede implementar un servidor Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo para el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-191">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="4ce8c-192">Todos los datos desde el espejo al nodo principal por error abriendo Skype para el Shell de administración de servidor empresarial y escribiendo el siguiente cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-192">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="4ce8c-p121">Repita este cmdlet para cada tipo de base de datos en el grupo de servidores. Puede usar el siguiente cmdlet para buscar todos los tipos de base de datos almacenados en este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="4ce8c-195">Usar el Generador de topologías para quitar el reflejo de bases de datos del grupo</span><span class="sxs-lookup"><span data-stu-id="4ce8c-195">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="4ce8c-196">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-196">Open Topology Builder.</span></span> <span data-ttu-id="4ce8c-197">En su topología, expanda **Grupos de servidores front-end Enterprise Edition**, haga clic derecho en el nombre del grupo de servidores y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-197">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="4ce8c-198">Para cada tipo de almacén SQL en el grupo, desactive la casilla **Habilitar la creación de reflejos de almacén SQL**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-198">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="4ce8c-p123">Publique la nueva topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="4ce8c-202">Use SQL Server Management Studio para separar el reflejo.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-202">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="4ce8c-p124">Abra SQL Server Management Studio, vaya a las bases de datos, haga clic con el botón derecho en **Tareas** y haga clic en **Reflejo**. Luego, haga clic en **Quitar la creación de reflejos** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="4ce8c-205">Repita este paso para todas las bases de datos en el grupo que se convertirá en un grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-205">Repeat this for all databases in the pool which will be converted to an AlwaysOn Availability Group.</span></span>
    
5. <span data-ttu-id="4ce8c-206">Configurar clústeres de conmutación por error de Windows Server en todos los servidores de base de datos que formarán parte del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-206">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-207">En cada uno de los servidores, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="4ce8c-207">On each server, do the following</span></span>
    
   - <span data-ttu-id="4ce8c-208">Abra Administrador de servidores y haga clic en **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-208">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="4ce8c-p126">Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="4ce8c-211">En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-211">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="4ce8c-212">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-212">Click **Install**.</span></span>
    
6. <span data-ttu-id="4ce8c-213">Valide la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-213">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="4ce8c-214">En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-214">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="4ce8c-215">En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-215">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="4ce8c-216">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-216">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-217">Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-217">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="4ce8c-218">En el cuadro**Resumen** , revise los errores que el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-218">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="4ce8c-219">Luego haga clic en **Finalizar** para completar la validación.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-219">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="4ce8c-p128">Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="4ce8c-223">Cree el clúster.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-223">Create the cluster.</span></span>
    
   - <span data-ttu-id="4ce8c-224">En el asistente **Administración del clúster de conmutación por error**, haga clic con el botón derecho en **Administración del clúster de conmutación por error** y luego haga clic en **Crear clúster**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-224">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="4ce8c-225">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-225">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-p129">Agregue el nombre del clúster y una dirección IP. Cuando la configuración se valide, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-228">En la página Confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-228">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-229">Una vez que se cree el clúster, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-229">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="4ce8c-p130">Le recomendamos que configure el cuórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="4ce8c-232">Haga clic con el botón derecho en el nombre del clúster, haga clic en **Más acciones** y haga clic en **Configurar opciones de cuórum de clúster**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-232">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="4ce8c-233">En la página **Seleccionar opción de configuración de cuórum**, haga clic en **Seleccionar el testigo de cuórum**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-233">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="4ce8c-234">En la página **Seleccionar el testigo de cuórum**, haga clic en **Configurar un testigo de recurso compartido de archivos**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-234">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="4ce8c-235">En la página **Configurar testigo de recurso compartido de archivos**, escriba la ruta de acceso del recurso compartido de archivos que desea usar y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-235">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-236">En la página **Confirmación**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-236">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="4ce8c-237">En cada uno de los servidores en el clúster, habilite Always On en el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-237">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="4ce8c-p131">Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server. </span><span class="sxs-lookup"><span data-stu-id="4ce8c-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="4ce8c-p132">En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="4ce8c-242">Cree el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-242">Create the availability group.</span></span>
    
    - <span data-ttu-id="4ce8c-243">Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-243">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="4ce8c-p133">En Explorador de objetos, expanda la carpeta **AlwaysOn alta disponibilidad**. Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p133">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="4ce8c-246">Si aparece la página **Introducción**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-246">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="4ce8c-247">En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-247">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="4ce8c-248">En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-248">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-249">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-249">Then click **Next**.</span></span>
    
    <span data-ttu-id="4ce8c-250">No incluya el **ReportServer**, **ReportServerTempDB**o charla persistente de bases de datos en el grupo de disponibilidad AlwaysOn, ya no se admiten en este escenario.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-250">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="4ce8c-251">Puede incluir todas las demás Skype para bases de datos de Business Server en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-251">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="4ce8c-252">En la página **Especificar réplicas**, haga clic en la pestaña **Réplicas**. Después haga clic en el botón **Agregar réplicas** y conéctese a las otras instancias de SQL a las que se unió como nodos del clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-252">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="4ce8c-p136">Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="4ce8c-255">Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-255">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
     - <span data-ttu-id="4ce8c-p137">Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="4ce8c-258">Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-258">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="4ce8c-p138">En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="4ce8c-p139">Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="4ce8c-263">En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-263">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="4ce8c-264">En la página **Resumen**, compruebe todas las opciones de configuración y haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-264">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="4ce8c-265">Crear un nuevo almacén especificando la escucha del grupo de disponibilidad AlwaysOn y especificando la entidad de seguridad del espejo antiguo como el nodo principal del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-265">Create a new store specifying the AlwaysOn Availability Group listener, and specifying the principal of the old mirror as the primary node of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="4ce8c-266">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-266">Open Topology Builder.</span></span> <span data-ttu-id="4ce8c-267">En la topología, expanda **Componentes compartidos**, haga clic con el botón derecho en **Almacenes de SQL Server** y haga clic en **Nuevo almacén de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-267">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="4ce8c-268">En la página **Definir nuevo almacén de SQL**, seleccione en primer lugar la casilla **Configuración de alta disponibilidad** y luego asegúrese de que Grupos de disponibilidad AlwaysOn de SQL aparece en el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-268">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="4ce8c-269">En el cuadro **FQDN de escucha de disponibilidad de SQL Server**, escriba el FQDN de la escucha que creó al crear el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-269">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="4ce8c-270">En el cuadro **Nombre de dominio completo de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-270">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span> <span data-ttu-id="4ce8c-271">Esto debería ser la entidad de seguridad del reflejo antiguo de este almacén.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-271">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="4ce8c-272">Asociar el nuevo grupo de disponibilidad AlwaysOn con el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-272">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
    - <span data-ttu-id="4ce8c-273">Generador de topología, haga clic en el grupo que desee asociar al grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-273">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="4ce8c-274">En **las asociaciones**, en el cuadro **Almacén de SQL Server** , seleccione el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-274">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-275">Seleccione el mismo grupo para otras bases de datos en el grupo que desea mover al grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-275">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="4ce8c-276">Cuando esté seguro de que todas las bases de datos necesarias se establecen en el grupo de disponibilidad AlwaysOn, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-276">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
13. <span data-ttu-id="4ce8c-p143">Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="4ce8c-280">Realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-280">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="4ce8c-281">Abrir el generador de topología, seleccione **Descargar la topología de implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-281">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="4ce8c-282">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-282">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="4ce8c-283">(Ratón) en el almacén SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-283">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="4ce8c-284">En la parte inferior de la página, en el cuadro **Nombre de dominio completo de SQL Server** , cambie el valor para el nombre completo del agente de escucha del grupo disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-284">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="4ce8c-p145">Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="4ce8c-289">Abra SQL Server Management Studio y vaya hasta el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-289">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-290">Conmútelo por error a una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-290">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="4ce8c-291">Abre Skype para negocios de Shell de administración de servidor y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-291">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="4ce8c-292">Repita los dos pasos anteriores (error en el grupo a una segunda réplica, luego use `Install-CsDatabase -Update`) para cada réplica en el grupo.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-292">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="4ce8c-293">Implementar un grupo de disponibilidad AlwaysOn en un grupo de servidores existente que no use reflejos de bases de datos</span><span class="sxs-lookup"><span data-stu-id="4ce8c-293">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="4ce8c-294"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="4ce8c-294"></span></span>

> [!NOTE]
> <span data-ttu-id="4ce8c-295">Si el grupo que se va a actualizar a los hosts de un grupo de disponibilidad AlwaysOn la Administración Central se almacena para su organización, primero debe mover el CMS a otro grupo antes de actualizar este grupo.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-295">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="4ce8c-296">Use el cmdlet Move-CsManagementServer para mover el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-296">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="4ce8c-297">Si no tiene otro grupo en su organización, puede implementar un servidor Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo para el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-297">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="4ce8c-298">Configurar clústeres de conmutación por error de Windows Server en todos los servidores de base de datos que formarán parte del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-298">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-299">En cada uno de los servidores, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="4ce8c-299">On each server, do the following</span></span>
    
   - <span data-ttu-id="4ce8c-300">Abra Administrador de servidores y haga clic en **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-300">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="4ce8c-p149">Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="4ce8c-303">En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-303">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="4ce8c-304">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-304">Click **Install**.</span></span>
    
2. <span data-ttu-id="4ce8c-305">Valide la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-305">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="4ce8c-306">En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-306">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="4ce8c-307">En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-307">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="4ce8c-308">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-308">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-309">Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-309">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="4ce8c-310">En el cuadro**Resumen** , revise los errores que el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-310">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="4ce8c-311">Luego haga clic en **Finalizar** para completar la validación.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-311">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="4ce8c-p151">Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="4ce8c-315">Cree el clúster.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-315">Create the cluster.</span></span>
    
   - <span data-ttu-id="4ce8c-316">En el asistente **Administración del clúster de conmutación por error**, haga clic con el botón derecho en **Administración del clúster de conmutación por error** y luego haga clic en **Crear clúster**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-316">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="4ce8c-317">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-317">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-p152">Agregue el nombre del clúster y una dirección IP. Cuando la configuración se valide, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-320">En la página Confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-320">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-321">Una vez que se cree el clúster, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-321">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="4ce8c-p153">Le recomendamos que configure el cuórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="4ce8c-324">Haga clic con el botón derecho en el nombre del clúster, haga clic en **Más acciones** y haga clic en **Configurar opciones de cuórum de clúster**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-324">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="4ce8c-325">En la página **Seleccionar opción de configuración de cuórum**, haga clic en **Seleccionar el testigo de cuórum**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-325">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="4ce8c-326">En la página **Seleccionar el testigo de cuórum**, haga clic en **Configurar un testigo de recurso compartido de archivos**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-326">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="4ce8c-327">En la página **Configurar testigo de recurso compartido de archivos**, escriba la ruta de acceso del recurso compartido de archivos que desea usar y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-327">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-328">En la página **Confirmación**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-328">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="4ce8c-329">En cada uno de los servidores en el clúster, habilite Always On en el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-329">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="4ce8c-p154">Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server. </span><span class="sxs-lookup"><span data-stu-id="4ce8c-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="4ce8c-p155">En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="4ce8c-334">Cree el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-334">Create the availability group.</span></span>
    
   - <span data-ttu-id="4ce8c-335">Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-335">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="4ce8c-p156">En Explorador de objetos, expanda la carpeta **AlwaysOn alta disponibilidad**. Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p156">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="4ce8c-338">Si aparece la página **Introducción**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-338">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-339">En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-339">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-340">En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-340">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-341">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-341">Then click **Next**.</span></span>
    
    <span data-ttu-id="4ce8c-342">No incluya el **ReportServer**, **ReportServerTempDB**o charla persistente de bases de datos en el grupo de disponibilidad AlwaysOn, ya no se admiten en este escenario.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-342">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="4ce8c-343">Puede incluir todas las demás Skype para bases de datos de Business Server en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-343">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="4ce8c-344">En la página **Especificar réplicas**, haga clic en la pestaña **Réplicas**. Después haga clic en el botón **Agregar réplicas** y conéctese a las otras instancias de SQL a las que se unió como nodos del clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-344">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="4ce8c-p159">Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="4ce8c-347">Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-347">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="4ce8c-p160">Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="4ce8c-350">Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-350">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="4ce8c-p161">En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="4ce8c-p162">Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="4ce8c-355">En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-355">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="4ce8c-356">En la página **Resumen**, compruebe todas las opciones de configuración y haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-356">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="4ce8c-357">Crear un nuevo almacén especificando la escucha del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-357">Create a new store specifying the AlwaysOn Availability Group listener.</span></span>
    
   - <span data-ttu-id="4ce8c-358">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-358">Open Topology Builder.</span></span> <span data-ttu-id="4ce8c-359">En la topología, expanda **Componentes compartidos**, haga clic con el botón derecho en **Almacenes de SQL Server** y haga clic en **Nuevo almacén de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-359">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="4ce8c-360">En la página **Definir nuevo almacén de SQL**, seleccione en primer lugar la casilla **Configuración de alta disponibilidad** y luego asegúrese de que Grupos de disponibilidad AlwaysOn de SQL aparece en el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-360">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="4ce8c-361">En el cuadro **FQDN de escucha de disponibilidad de SQL Server**, escriba el FQDN de la escucha que creó al crear el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-361">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="4ce8c-362">En el cuadro **Nombre de dominio completo de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-362">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span>
    
8. <span data-ttu-id="4ce8c-363">Asociar el nuevo grupo de disponibilidad AlwaysOn con el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-363">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="4ce8c-364">Generador de topología, haga clic en el grupo que desee asociar al grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-364">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="4ce8c-365">En **las asociaciones**, en el cuadro **Almacén de SQL Server** , seleccione el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-365">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-366">Seleccione el mismo grupo para otras bases de datos en el grupo que desea mover al grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-366">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="4ce8c-367">Cuando esté seguro de que todas las bases de datos necesarias se establecen en el grupo de disponibilidad AlwaysOn, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-367">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
9. <span data-ttu-id="4ce8c-p165">Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="4ce8c-371">Realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-371">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="4ce8c-372">Abrir el generador de topología, seleccione **Descargar la topología de implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-372">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="4ce8c-373">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-373">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="4ce8c-374">Haga el almacén SQL del nuevo grupo de disponibilidad AlwaysOn y ** editar propiedades **.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-374">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="4ce8c-375">En la parte inferior de la página, en el cuadro **Nombre de dominio completo de SQL Server** , cambie el valor para el nombre completo del agente de escucha del grupo disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-375">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="4ce8c-p167">Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="4ce8c-380">Abra SQL Server Management Studio y vaya hasta el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-380">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="4ce8c-381">Conmútelo por error a una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-381">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="4ce8c-382">Abre Skype para negocios de Shell de administración de servidor y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:</span><span class="sxs-lookup"><span data-stu-id="4ce8c-382">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
     ```
     Install-CsDatabase -Update
     ```

     - <span data-ttu-id="4ce8c-383">Repita los dos pasos anteriores (error en el grupo a una segunda réplica, luego use `Install-CsDatabase -Update`) para cada réplica en el grupo.</span><span class="sxs-lookup"><span data-stu-id="4ce8c-383">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    

