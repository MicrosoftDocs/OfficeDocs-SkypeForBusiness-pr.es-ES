---
title: Implementar un grupo de disponibilidad siempre en un servidor Back-End de Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implementar (instalar) un siempre en grupo de disponibilidad en su Skype para Business Server implementación.
ms.openlocfilehash: eaf0c935f246cfdd00aa0707475442c88dc89b8a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374375"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="ade5a-103">Implementar un grupo de disponibilidad siempre en un servidor Back-End de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="ade5a-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="ade5a-104">Implementar (instalar) una siempre en disponibilidad grupo (AG) en su Skype para Business Server implementación.</span><span class="sxs-lookup"><span data-stu-id="ade5a-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="ade5a-105">Cómo implementar un AG depende de si se implementa en un nuevo grupo de servidores, un grupo de servidores existente que usa la creación de reflejos o un grupo de servidores existente que tiene actualmente no hay una alta disponibilidad para la base de datos back-End.</span><span class="sxs-lookup"><span data-stu-id="ade5a-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ade5a-106">No se admite el uso de un AG con un rol de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ade5a-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="ade5a-107">Implementar un siempre en grupo de disponibilidad en un nuevo grupo de servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ade5a-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="ade5a-108">Implementar un siempre en grupo de disponibilidad en un grupo de servidores existente que usa la creación de reflejo de base de datos</span><span class="sxs-lookup"><span data-stu-id="ade5a-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="ade5a-109">Implementar un siempre en grupo de disponibilidad en un grupo de servidores existente que no se utiliza la creación de reflejo de base de datos</span><span class="sxs-lookup"><span data-stu-id="ade5a-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="ade5a-110">Implementar un siempre en grupo de disponibilidad en un nuevo grupo de servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ade5a-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="ade5a-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="ade5a-111"></span></span>

1. <span data-ttu-id="ade5a-112">Habilitar la característica de agrupación en clústeres de conmutación por error en todos los servidores de base de datos que formarán parte de la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="ade5a-113">En cada uno de los servidores, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="ade5a-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="ade5a-114">Abra Administrador de servidores y haga clic en **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="ade5a-p102">Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="ade5a-117">En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="ade5a-118">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="ade5a-119">Valide la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="ade5a-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="ade5a-120">En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="ade5a-121">En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="ade5a-122">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-123">Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="ade5a-124">En el cuadro**Resumen** , compruebe los errores que el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="ade5a-124">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="ade5a-125">Luego haga clic en **Finalizar** para completar la validación.</span><span class="sxs-lookup"><span data-stu-id="ade5a-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="ade5a-p104">Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="ade5a-129">Crear el clúster de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="ade5a-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="ade5a-130">En el asistente **Administración del clúster de conmutación por error**, haga clic con el botón derecho en **Administración del clúster de conmutación por error** y luego haga clic en **Crear clúster**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="ade5a-131">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-p105">Agregue el nombre del clúster y una dirección IP. Cuando la configuración se valide, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-134">En la página Confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-135">Una vez que se cree el clúster, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="ade5a-p106">Le recomendamos que configure el cuórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ade5a-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="ade5a-138">Haga clic con el botón derecho en el nombre del clúster, haga clic en **Más acciones** y haga clic en **Configurar opciones de cuórum de clúster**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="ade5a-139">En la página **Seleccionar opción de configuración de cuórum**, haga clic en **Seleccionar el testigo de cuórum**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="ade5a-140">En la página **Seleccionar el testigo de cuórum**, haga clic en **Configurar un testigo de recurso compartido de archivos**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="ade5a-141">En la página **Configurar testigo de recurso compartido de archivos**, escriba la ruta de acceso del recurso compartido de archivos que desea usar y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-142">En la página **Confirmación**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="ade5a-143">En cada servidor del clúster, habilitar la característica de AG en el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ade5a-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="ade5a-p107">Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server. </span><span class="sxs-lookup"><span data-stu-id="ade5a-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="ade5a-p108">En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="ade5a-148">Cree el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="ade5a-148">Create the availability group.</span></span>
    
   - <span data-ttu-id="ade5a-149">Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ade5a-149">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="ade5a-150">En el Explorador de objetos, expanda la carpeta **Siempre en alta disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="ade5a-150">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="ade5a-151">Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-151">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="ade5a-152">Si aparece la página **Introducción**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-152">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-153">En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-153">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-154">En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="ade5a-154">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="ade5a-155">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-155">Then click **Next**.</span></span>
    
     <span data-ttu-id="ade5a-156">No incluya el **ReportServer**, **ReportServerTempDB**o bases de datos de Chat persistente en el grupo de disponibilidad AlwaysOn, como no se admiten en este escenario.</span><span class="sxs-lookup"><span data-stu-id="ade5a-156">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="ade5a-157">Puede incluir todos los demás Skype para bases de datos de Business Server en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="ade5a-157">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="ade5a-158">En la página **Especificar réplicas**, haga clic en la pestaña **Réplicas**. Después haga clic en el botón **Agregar réplicas** y conéctese a las otras instancias de SQL a las que se unió como nodos del clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ade5a-158">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="ade5a-p112">Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="ade5a-161">Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.</span><span class="sxs-lookup"><span data-stu-id="ade5a-161">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="ade5a-p113">Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).</span><span class="sxs-lookup"><span data-stu-id="ade5a-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="ade5a-164">Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-164">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="ade5a-p114">En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="ade5a-p115">Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="ade5a-169">En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-169">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-170">En la página**Resumen** , compruebe todas las opciones y haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="ade5a-170">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="ade5a-171">Usar el generador de topología para crear el grupo de servidores Front-End, como se explica en [crear y publicar la nueva topología de Skype para Business Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="ade5a-171">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="ade5a-172">Cuando lo hace, especifique el AG como el almacén de SQL para el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ade5a-172">When you do, specify the AG as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="ade5a-173">Después de que el grupo de servidores y el AG se implementan, realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="ade5a-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="ade5a-174">Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="ade5a-175">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="ade5a-176">Haga clic en el almacén de SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="ade5a-177">En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , cambie el valor para el FQDN del agente de escucha de la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="ade5a-p118">Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="ade5a-182">Abra SQL Server Management Studio y navegue a la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="ade5a-183">Conmútelo por error a una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="ade5a-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="ade5a-184">Abra Skype para Shell de administración de servidor empresarial y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:</span><span class="sxs-lookup"><span data-stu-id="ade5a-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="ade5a-185">Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria, a continuación, usar `Install-CsDatabase -Update`) para cada réplica en el grupo.</span><span class="sxs-lookup"><span data-stu-id="ade5a-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="ade5a-186">Implementar un siempre en grupo de disponibilidad en un grupo de servidores existente que usa la creación de reflejo de base de datos</span><span class="sxs-lookup"><span data-stu-id="ade5a-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="ade5a-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="ade5a-187"></span></span>

> [!NOTE]
> <span data-ttu-id="ade5a-188">Si el grupo que se va a actualizar a una AG hospeda el almacén de Administración Central para su organización, primero debe mover el CMS a otro grupo de servidores antes de actualizar este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ade5a-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="ade5a-189">Use el cmdlet Move-CsManagementServer para mover el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ade5a-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="ade5a-190">Si no tiene otro grupo de servidores en su organización, puede implementar un servidor Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo de servidores a la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="ade5a-191">Conmutación por error todos los datos desde el reflejo para el nodo de entidad de seguridad abriendo Skype para Shell de administración de servidor empresarial y escribiendo el siguiente cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ade5a-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="ade5a-p121">Repita este cmdlet para cada tipo de base de datos en el grupo de servidores. Puede usar el siguiente cmdlet para buscar todos los tipos de base de datos almacenados en este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="ade5a-194">Usar el Generador de topologías para quitar el reflejo de bases de datos del grupo</span><span class="sxs-lookup"><span data-stu-id="ade5a-194">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="ade5a-195">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ade5a-195">Open Topology Builder.</span></span> <span data-ttu-id="ade5a-196">En su topología, expanda **Grupos de servidores front-end Enterprise Edition**, haga clic derecho en el nombre del grupo de servidores y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="ade5a-197">Para cada tipo de almacén SQL en el grupo, desactive la casilla **Habilitar la creación de reflejos de almacén SQL**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="ade5a-p123">Publique la nueva topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="ade5a-201">Use SQL Server Management Studio para separar el reflejo.</span><span class="sxs-lookup"><span data-stu-id="ade5a-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="ade5a-p124">Abra SQL Server Management Studio, vaya a las bases de datos, haga clic con el botón derecho en **Tareas** y haga clic en **Reflejo**. Luego, haga clic en **Quitar la creación de reflejos** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="ade5a-204">Repita este paso para todas las bases de datos en el grupo de servidores que se convertirá a un AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="ade5a-205">Configurar la característica de agrupación en clústeres de conmutación por error en todos los servidores de base de datos que formarán parte de la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="ade5a-206">En cada uno de los servidores, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="ade5a-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="ade5a-207">Abra Administrador de servidores y haga clic en **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="ade5a-p126">Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="ade5a-210">En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="ade5a-211">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="ade5a-212">Valide la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="ade5a-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="ade5a-213">En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="ade5a-214">En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="ade5a-215">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-216">Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="ade5a-217">En el cuadro**Resumen** , compruebe los errores que el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="ade5a-217">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="ade5a-218">Luego haga clic en **Finalizar** para completar la validación.</span><span class="sxs-lookup"><span data-stu-id="ade5a-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="ade5a-p128">Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="ade5a-222">Crear el clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ade5a-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="ade5a-223">En el asistente **Administración del clúster de conmutación por error**, haga clic con el botón derecho en **Administración del clúster de conmutación por error** y luego haga clic en **Crear clúster**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="ade5a-224">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-p129">Agregue el nombre del clúster y una dirección IP. Cuando la configuración se valide, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-227">En la página Confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-228">Una vez que se cree el clúster, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="ade5a-p130">Le recomendamos que configure el cuórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ade5a-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="ade5a-231">Haga clic con el botón derecho en el nombre del clúster, haga clic en **Más acciones** y haga clic en **Configurar opciones de cuórum de clúster**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="ade5a-232">En la página **Seleccionar opción de configuración de cuórum**, haga clic en **Seleccionar el testigo de cuórum**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="ade5a-233">En la página **Seleccionar el testigo de cuórum**, haga clic en **Configurar un testigo de recurso compartido de archivos**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="ade5a-234">En la página **Configurar testigo de recurso compartido de archivos**, escriba la ruta de acceso del recurso compartido de archivos que desea usar y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-235">En la página **Confirmación**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="ade5a-236">En cada servidor del clúster, habilitar la característica de AG en el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ade5a-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="ade5a-p131">Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server. </span><span class="sxs-lookup"><span data-stu-id="ade5a-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="ade5a-p132">En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="ade5a-241">Cree el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="ade5a-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="ade5a-242">Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ade5a-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="ade5a-243">En el Explorador de objetos, expanda la carpeta **Siempre en alta disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="ade5a-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="ade5a-244">Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="ade5a-245">Si aparece la página **Introducción**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="ade5a-246">En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="ade5a-247">En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="ade5a-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="ade5a-248">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="ade5a-249">No incluya el **ReportServer**, **ReportServerTempDB**o bases de datos de Chat persistente en el grupo de disponibilidad AlwaysOn, como no se admiten en este escenario.</span><span class="sxs-lookup"><span data-stu-id="ade5a-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="ade5a-250">Puede incluir todos los demás Skype para bases de datos de Business Server en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="ade5a-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="ade5a-251">En la página **Especificar réplicas**, haga clic en la pestaña **Réplicas**. Después haga clic en el botón **Agregar réplicas** y conéctese a las otras instancias de SQL a las que se unió como nodos del clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ade5a-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="ade5a-p136">Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="ade5a-254">Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.</span><span class="sxs-lookup"><span data-stu-id="ade5a-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="ade5a-p137">Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).</span><span class="sxs-lookup"><span data-stu-id="ade5a-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="ade5a-257">Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="ade5a-p138">En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="ade5a-p139">Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="ade5a-262">En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="ade5a-263">En la página **Resumen**, compruebe todas las opciones de configuración y haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="ade5a-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="ade5a-264">Crear un nuevo almacén especificando el agente de escucha AG y especificando la entidad de seguridad del reflejo antiguo como el nodo principal de la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="ade5a-265">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ade5a-265">Open Topology Builder.</span></span> <span data-ttu-id="ade5a-266">En la topología, expanda **Componentes compartidos**, haga clic con el botón derecho en **Almacenes de SQL Server** y haga clic en **Nuevo almacén de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="ade5a-267">En la página **Definir nuevo almacén de SQL**, seleccione en primer lugar la casilla **Configuración de alta disponibilidad** y luego asegúrese de que Grupos de disponibilidad AlwaysOn de SQL aparece en el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="ade5a-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="ade5a-268">En el cuadro **FQDN de escucha de disponibilidad de SQL Server**, escriba el FQDN de la escucha que creó al crear el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="ade5a-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="ade5a-269">En el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal de la AG y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="ade5a-270">Esto debería ser la entidad de seguridad del reflejo antiguo de este almacén.</span><span class="sxs-lookup"><span data-stu-id="ade5a-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="ade5a-271">Asociar el nuevo AG con el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="ade5a-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="ade5a-272">En el generador, haga clic en el grupo que se va a asociar con el AG y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="ade5a-273">En **asociaciones**, en el cuadro **Almacén de SQL Server** , seleccione el AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="ade5a-274">Seleccione el mismo grupo para otras bases de datos en el grupo que desea mover a la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="ade5a-275">Cuando esté seguro de que todas las bases de datos necesarias se establecen en el AG, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="ade5a-p143">Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="ade5a-279">Realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="ade5a-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="ade5a-280">Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="ade5a-281">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="ade5a-282">Haga clic en el almacén de SQL de la nueva AG y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="ade5a-283">En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , cambie el valor para el FQDN del agente de escucha de la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="ade5a-p145">Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="ade5a-288">Abra SQL Server Management Studio y navegue a la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="ade5a-289">Conmútelo por error a una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="ade5a-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="ade5a-290">Abra Skype para Shell de administración de servidor empresarial y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:</span><span class="sxs-lookup"><span data-stu-id="ade5a-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="ade5a-291">Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria, a continuación, usar `Install-CsDatabase -Update`) para cada réplica en el grupo.</span><span class="sxs-lookup"><span data-stu-id="ade5a-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="ade5a-292">Implementar un siempre en grupo de disponibilidad en un grupo de servidores existente que no se utiliza la creación de reflejo de base de datos</span><span class="sxs-lookup"><span data-stu-id="ade5a-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="ade5a-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="ade5a-293"></span></span>

> [!NOTE]
> <span data-ttu-id="ade5a-294">Si el grupo que se va a actualizar a una AG hospeda el almacén de Administración Central para su organización, primero debe mover el CMS a otro grupo de servidores antes de actualizar este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ade5a-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="ade5a-295">Use el cmdlet Move-CsManagementServer para mover el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ade5a-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="ade5a-296">Si no tiene otro grupo de servidores en su organización, puede implementar un servidor Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo de servidores a la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="ade5a-297">Configurar la característica de agrupación en clústeres de conmutación por error en todos los servidores de base de datos que formarán parte de la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="ade5a-298">En cada uno de los servidores, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="ade5a-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="ade5a-299">Abra Administrador de servidores y haga clic en **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="ade5a-p149">Haga clic en **Siguiente** hasta llegar al cuadro **Seleccionar características**. Aquí seleccione la casilla **Clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="ade5a-302">En el cuadro **¿Agregar características que son necesarias para los clústeres de conmutación por error?**, haga clic en **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="ade5a-303">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="ade5a-304">Valide la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="ade5a-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="ade5a-305">En el Administrador de servidores, haga clic en el menú **Herramientas** y luego haga clic en **Administrador de clústeres de conmutación por error**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="ade5a-306">En **Acciones** en la parte derecha de la pantalla, haga clic en **Validar configuración**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="ade5a-307">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-308">Seleccione los servidores que añadir al clúster y después haga clic en **Ejecutar todas las pruebas**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="ade5a-309">En el cuadro**Resumen** , compruebe los errores que el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="ade5a-309">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="ade5a-310">Luego haga clic en **Finalizar** para completar la validación.</span><span class="sxs-lookup"><span data-stu-id="ade5a-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="ade5a-p151">Puede que el asistente le informe de varias advertencias, especialmente si no usa el almacenamiento compartido. No tiene que usar el almacenamiento compartido, pero si ve cualquier mensaje de **Error**, debe corregir estos problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="ade5a-314">Crear el clúster de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="ade5a-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="ade5a-315">En el asistente **Administración del clúster de conmutación por error**, haga clic con el botón derecho en **Administración del clúster de conmutación por error** y luego haga clic en **Crear clúster**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="ade5a-316">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-p152">Agregue el nombre del clúster y una dirección IP. Cuando la configuración se valide, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-319">En la página Confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-320">Una vez que se cree el clúster, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="ade5a-p153">Le recomendamos que configure el cuórum del clúster para usar un testigo de recurso compartido de archivos. Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ade5a-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="ade5a-323">Haga clic con el botón derecho en el nombre del clúster, haga clic en **Más acciones** y haga clic en **Configurar opciones de cuórum de clúster**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="ade5a-324">En la página **Seleccionar opción de configuración de cuórum**, haga clic en **Seleccionar el testigo de cuórum**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="ade5a-325">En la página **Seleccionar el testigo de cuórum**, haga clic en **Configurar un testigo de recurso compartido de archivos**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="ade5a-326">En la página **Configurar testigo de recurso compartido de archivos**, escriba la ruta de acceso del recurso compartido de archivos que desea usar y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-327">En la página **Confirmación**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="ade5a-328">En cada servidor del clúster, habilitar AG en el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ade5a-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="ade5a-p154">Abra el Administrador de configuración de SQL Server. En el árbol de la parte izquierda de la pantalla, haga clic en **Servicios de SQL Server** y luego haga doble clic en el servicio de SQL Server. </span><span class="sxs-lookup"><span data-stu-id="ade5a-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="ade5a-p155">En el cuadro **Propiedades**, seleccione la pestaña **AlwaysOn alta disponibilidad**. Seleccione la casilla **Habilitar Grupos de disponibilidad AlwaysOn**. Reinicie el servicio de SQL Server cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="ade5a-333">Cree el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="ade5a-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="ade5a-334">Abra SQL Server Management Studio y conéctese a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ade5a-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="ade5a-335">En el Explorador de objetos, expanda la carpeta **Siempre en alta disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="ade5a-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="ade5a-336">Haga clic con el botón derecho en la carpeta **Grupos de disponibilidad** y haga clic en **Asistente de nuevo grupo de disponibilidad**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="ade5a-337">Si aparece la página **Introducción**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-338">En la página **Especificar nombre del grupo de disponibilidad**, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-339">En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="ade5a-340">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="ade5a-341">No incluir la **ReportServer**, **ReportServerTempDB**o bases de datos de Chat persistente en el AG, como no se admiten en este escenario.</span><span class="sxs-lookup"><span data-stu-id="ade5a-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="ade5a-342">Puede incluir todos los demás Skype para bases de datos de Business Server en el AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="ade5a-343">En la página **Especificar réplicas** , haga clic en la ficha **réplicas** . A continuación, haga clic en el botón **Agregar réplicas** y conectarse a las instancias SQL que se ha unido a como nodos de la WSFC.</span><span class="sxs-lookup"><span data-stu-id="ade5a-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="ade5a-p159">Para cada instancia, seleccione las opciones **Conmutación por error automática** y **Confirmación sincrónica**. No seleccione la opción **Secundaria legible**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="ade5a-346">Haga clic en la pestaña **Extremos** y compruebe que el **Número de puerto** está establecido en 5022.</span><span class="sxs-lookup"><span data-stu-id="ade5a-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="ade5a-p160">Haga clic en la ficha **Escucha** y seleccione la opción **Crear una escucha de grupo de disponibilidad**. En esta opción, escriba un nombre para el receptor y establezca el **Puerto** en 1433 (no se admiten otros puertos para esta opción).</span><span class="sxs-lookup"><span data-stu-id="ade5a-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="ade5a-349">Haga clic en **Agregar** y después en el cuadro **Dirección IPv4**, proporcione su dirección IP virtual preferida y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="ade5a-p161">En la página **Seleccione sincronización inicial de datos**, seleccione Completo y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta del servicio de SQL Server usada por ambas réplicas tenga permisos de escritura. Después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="ade5a-p162">Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos. Si trabaja con bases de datos grandes, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no admita el tamaño de las copias de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="ade5a-354">En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="ade5a-355">En la página **Resumen**, compruebe todas las opciones de configuración y haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="ade5a-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="ade5a-356">Crear un nuevo almacén de especificación de la escucha de AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="ade5a-357">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ade5a-357">Open Topology Builder.</span></span> <span data-ttu-id="ade5a-358">En la topología, expanda **Componentes compartidos**, haga clic con el botón derecho en **Almacenes de SQL Server** y haga clic en **Nuevo almacén de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="ade5a-359">En la página **Definir nuevo almacén de SQL**, seleccione en primer lugar la casilla **Configuración de alta disponibilidad** y luego asegúrese de que Grupos de disponibilidad AlwaysOn de SQL aparece en el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="ade5a-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="ade5a-360">En el cuadro **FQDN de escucha de disponibilidad de SQL Server**, escriba el FQDN de la escucha que creó al crear el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="ade5a-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="ade5a-361">En el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal de la AG y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="ade5a-362">Asociar el nuevo siempre en grupo de disponibilidad con el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="ade5a-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="ade5a-363">En el generador, haga clic en el grupo que se va a asociar con el AG y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="ade5a-364">En **asociaciones**, en el cuadro **Almacén de SQL Server** , seleccione el AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="ade5a-365">Seleccione el mismo grupo para otras bases de datos en el grupo que desea mover a la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="ade5a-366">Cuando esté seguro de que todas las bases de datos necesarias se establecen en el AG, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="ade5a-p165">Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="ade5a-370">Realizar algunos pasos finales para asegurarse de que los inicios de sesión SQL se encuentran en cada una de las réplicas en el AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="ade5a-371">Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="ade5a-372">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="ade5a-373">Haga clic en el almacén de SQL de la nueva AG y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ade5a-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="ade5a-374">En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , cambie el valor para el FQDN del agente de escucha de la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="ade5a-p167">Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**. Espere unos minutos hasta que la nueva topología se replique.</span><span class="sxs-lookup"><span data-stu-id="ade5a-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="ade5a-379">Abra SQL Server Management Studio y navegue a la AG.</span><span class="sxs-lookup"><span data-stu-id="ade5a-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="ade5a-380">Conmútelo por error a una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="ade5a-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="ade5a-381">Abra Skype para Shell de administración de servidor empresarial y escriba el siguiente cmdlet para crear los inicios de sesión SQL en esta réplica:</span><span class="sxs-lookup"><span data-stu-id="ade5a-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="ade5a-382">Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria, a continuación, usar `Install-CsDatabase -Update`) para cada réplica en el grupo.</span><span class="sxs-lookup"><span data-stu-id="ade5a-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>