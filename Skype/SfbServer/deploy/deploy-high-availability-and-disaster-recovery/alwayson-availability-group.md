---
title: Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implemente (instale) un grupo de disponibilidad AlwaysOn en su implementación de Skype Empresarial Server.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830660"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="042e9-103">Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="042e9-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="042e9-104">Implemente (instale) un grupo de disponibilidad AlwaysOn (AG) en su implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="042e9-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="042e9-105">La forma en que se implementa una AG depende de si se implementa en un nuevo grupo de servidores, un grupo existente que usa la creación de reflejos o un grupo existente que actualmente no tiene alta disponibilidad para la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="042e9-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="042e9-106">No se admite el uso de una AG con un rol de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="042e9-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="042e9-107">Implementar un grupo de disponibilidad AlwaysOn en un nuevo grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="042e9-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="042e9-108">Implementar un grupo de disponibilidad AlwaysOn en un grupo existente que usa la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="042e9-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="042e9-109">Implementar un grupo de disponibilidad AlwaysOn en un grupo existente que no usa la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="042e9-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="042e9-110">Implementar un grupo de disponibilidad AlwaysOn en un nuevo grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="042e9-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="042e9-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="042e9-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="042e9-112">Habilite la característica clústeres de conmutación por error en todos los servidores de bases de datos que formarán parte de ag.</span><span class="sxs-lookup"><span data-stu-id="042e9-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="042e9-113">En cada servidor, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="042e9-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="042e9-114">Abra el Administrador del servidor y haga **clic en Agregar roles y características.**</span><span class="sxs-lookup"><span data-stu-id="042e9-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="042e9-115">Haga **clic en Siguiente** hasta que llegue al cuadro **Seleccionar** características.</span><span class="sxs-lookup"><span data-stu-id="042e9-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="042e9-116">En este caso, active la casilla clústeres de **conmutación** por error.</span><span class="sxs-lookup"><span data-stu-id="042e9-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="042e9-117">En el **cuadro Agregar características necesarias para clústeres de** conmutación por error, haga clic en Agregar **características.**</span><span class="sxs-lookup"><span data-stu-id="042e9-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="042e9-118">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="042e9-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="042e9-119">Validar la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="042e9-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="042e9-120">En el Administrador de servidores, haga clic en el **menú Herramientas** y, a continuación, haga clic en Administrador **de clústeres de conmutación por error.**</span><span class="sxs-lookup"><span data-stu-id="042e9-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="042e9-121">En **Acciones** en el lado derecho de la pantalla, haga clic **en Validar configuración.**</span><span class="sxs-lookup"><span data-stu-id="042e9-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="042e9-122">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-123">Seleccione los servidores que desea agregar al clúster y, a continuación, haga clic **en Ejecutar todas las pruebas.**</span><span class="sxs-lookup"><span data-stu-id="042e9-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="042e9-124">En el **cuadro Resumen,** compruebe los errores que informe el asistente.</span><span class="sxs-lookup"><span data-stu-id="042e9-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="042e9-125">A **continuación, haga clic** en Finalizar para completar la validación.</span><span class="sxs-lookup"><span data-stu-id="042e9-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="042e9-126">El asistente probablemente mostrará varias advertencias, especialmente si no usa almacenamiento compartido.</span><span class="sxs-lookup"><span data-stu-id="042e9-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="042e9-127">No es necesario usar el almacenamiento compartido.</span><span class="sxs-lookup"><span data-stu-id="042e9-127">You are not required to use shared storage.</span></span> <span data-ttu-id="042e9-128">Sin embargo, si ve algún **mensaje de error,** debe corregir esos problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="042e9-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="042e9-129">Crear el clúster de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="042e9-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="042e9-130">En el Asistente **para la administración de clústeres de** conmutación por error, haga clic con el botón secundario en Administración de **clústeres de** conmutación por error y, a continuación, haga clic en Crear **clúster.**</span><span class="sxs-lookup"><span data-stu-id="042e9-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="042e9-131">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-132">Agregue el nombre del clúster y la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="042e9-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="042e9-133">Cuando se valide la configuración, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-134">En la página Confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-135">Después de crear el clúster, haga clic **en Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="042e9-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="042e9-136">Se recomienda configurar las opciones de quórum del clúster para usar un testigo de recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="042e9-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="042e9-137">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="042e9-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="042e9-138">Haga clic con el botón secundario en el nombre del clúster, haga clic en **Más acciones** y, a continuación, haga clic en Configurar la configuración de quórum **del clúster.**</span><span class="sxs-lookup"><span data-stu-id="042e9-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="042e9-139">En la página **Seleccionar opción de configuración de** quórum, haga clic en Seleccionar el testigo de **quórum.**</span><span class="sxs-lookup"><span data-stu-id="042e9-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="042e9-140">En la página **Seleccionar testigo de** quórum, haga clic en Configurar un testigo de recurso compartido de **archivos.**</span><span class="sxs-lookup"><span data-stu-id="042e9-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="042e9-141">En la **página Configurar testigo de recurso** compartido de archivos, escriba la ruta de acceso del recurso compartido de archivos que desea usar y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="042e9-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-142">En la página **Confirmación**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="042e9-143">En cada servidor del clúster, habilita la característica AG en SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="042e9-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="042e9-144">Abra el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="042e9-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="042e9-145">En el árbol del lado izquierdo de la pantalla, haga clic en **SQL Server Servicios** y, a continuación, haga doble clic en SQL Server servicio.</span><span class="sxs-lookup"><span data-stu-id="042e9-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="042e9-146">En el **cuadro Propiedades,** seleccione la **pestaña Alta disponibilidad de AlwaysOn.** Active la casilla **Habilitar grupos de disponibilidad AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="042e9-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="042e9-147">Reinicie el servicio SQL Server cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="042e9-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="042e9-148">Use topology Builder para crear el grupo de servidores front-end, como se explica en Crear y publicar una nueva [topología en Skype Empresarial Server.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="042e9-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="042e9-149">Cuando lo haga, especifique el grupo de disponibilidad como SQL almacén para el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="042e9-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="042e9-150">Cree el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="042e9-151">Abra SQL Server Management Studio y conéctese a la SQL Server predeterminada.</span><span class="sxs-lookup"><span data-stu-id="042e9-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="042e9-152">En el Explorador de objetos, expanda la **carpeta De alta disponibilidad de AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="042e9-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="042e9-153">Haga clic con el botón secundario en **la carpeta Grupos de** disponibilidad y haga clic en Asistente para nuevo grupo de **disponibilidad.**</span><span class="sxs-lookup"><span data-stu-id="042e9-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="042e9-154">Si aparece **la página** Introducción, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-155">En la **página Especificar nombre del grupo de** disponibilidad, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="042e9-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-156">En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="042e9-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="042e9-157">A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="042e9-158">No incluya las bases de datos **ReportServer,** **ReportServerTempDB** o Persistent Chat en el grupo de disponibilidad AlwaysOn, ya que no se admiten en este escenario.</span><span class="sxs-lookup"><span data-stu-id="042e9-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="042e9-159">Puede incluir todas las demás bases de datos de Skype Empresarial Server en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="042e9-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="042e9-160">En la **página Especificar réplicas,** haga clic en **la pestaña Réplicas.** A continuación, haga clic en el botón Agregar **réplicas** y conéctese a las otras instancias de SQL que ha unido como nodos del clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="042e9-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="042e9-161">Para cada instancia, seleccione las opciones **De conmutación por error automática** y Confirmación sincrónica. </span><span class="sxs-lookup"><span data-stu-id="042e9-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="042e9-162">No seleccione la opción **Secundaria legible.**</span><span class="sxs-lookup"><span data-stu-id="042e9-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="042e9-163">Haga clic **en la pestaña Puntos** de conexión y compruebe que el número **de** puerto esté establecido en 5022.</span><span class="sxs-lookup"><span data-stu-id="042e9-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="042e9-164">Haga clic en **la pestaña** Escucha y seleccione la opción Crear un agente de escucha de **grupo de** disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="042e9-165">En esa opción, escriba un nombre para el agente de escucha y establezca **el** puerto en 1433 (no se admiten otros puertos para esta opción).</span><span class="sxs-lookup"><span data-stu-id="042e9-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="042e9-166">Haga **clic en** Agregar y, a continuación, en el cuadro Dirección **IPv4,** proporcione su dirección IP virtual preferida y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="042e9-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="042e9-167">En  la página Seleccionar sincronización de datos iniciales, seleccione Completa y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta de servicio de SQL Server usada por ambas réplicas tenga permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="042e9-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="042e9-168">A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="042e9-169">Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="042e9-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="042e9-170">Si trabaja con bases de datos de gran tamaño, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no pueda acomodar el tamaño de las copias de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="042e9-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="042e9-171">En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-172">En la **página Resumen,** compruebe toda la configuración y haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="042e9-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="042e9-173">Después de implementar el grupo de servidores y el grupo de disponibilidad, realice algunos pasos finales para asegurarse de que los inicios de sesión SQL estén en cada una de las réplicas del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="042e9-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="042e9-174">Abra el Generador de topologías, **seleccione Descargar topología de la implementación existente** y haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="042e9-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="042e9-175">Expanda Skype Empresarial Server, expanda la topología y expanda **SQL Server store.**</span><span class="sxs-lookup"><span data-stu-id="042e9-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="042e9-176">Haga clic con el botón secundario en SQL almacén del nuevo grupo de disponibilidad AlwaysOn y, a continuación, haga clic **en Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="042e9-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="042e9-177">En la parte inferior de la página, en el cuadro **SQL Server FQDN,** cambie el valor al FQDN del agente de escucha del GRUPO.</span><span class="sxs-lookup"><span data-stu-id="042e9-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="042e9-178">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="042e9-178">Publish the topology.</span></span> <span data-ttu-id="042e9-179">En el **menú Acción,** haga **clic en Topología** y, a continuación, **publique**.</span><span class="sxs-lookup"><span data-stu-id="042e9-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="042e9-180">A continuación, en la página de confirmación, haga **clic en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="042e9-181">A continuación, espere unos minutos para que se replique la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="042e9-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="042e9-182">Abra SQL Server Management Studio y vaya al GRUPO.</span><span class="sxs-lookup"><span data-stu-id="042e9-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="042e9-183">Conmutación por error a una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="042e9-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="042e9-184">Abra el Shell de administración de Skype Empresarial Server y escriba el siguiente cmdlet para crear SQL inicios de sesión en esta réplica:</span><span class="sxs-lookup"><span data-stu-id="042e9-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="042e9-185">Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria y, a continuación,  `Install-CsDatabase -Update` use) para cada réplica del grupo.</span><span class="sxs-lookup"><span data-stu-id="042e9-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="042e9-186">Implementar un grupo de disponibilidad AlwaysOn en un grupo existente que usa la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="042e9-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="042e9-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="042e9-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="042e9-188">Si el grupo de servidores que va a actualizar a una AG hospeda el almacén de administración central de su organización, primero debe mover el CMS a otro grupo antes de actualizar este grupo.</span><span class="sxs-lookup"><span data-stu-id="042e9-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="042e9-189">Use el cmdlet Move-CsManagementServer para mover el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="042e9-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="042e9-190">Si no tiene otro grupo de servidores en la organización, puede implementar un servidor Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo a ag.</span><span class="sxs-lookup"><span data-stu-id="042e9-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="042e9-191">Para conmutar por error todos los datos del reflejo al nodo principal, abra el Shell de administración de Skype Empresarial Server y escriba el siguiente cmdlet.</span><span class="sxs-lookup"><span data-stu-id="042e9-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="042e9-192">Repita este cmdlet para cada tipo de base de datos del grupo.</span><span class="sxs-lookup"><span data-stu-id="042e9-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="042e9-193">Puede usar el siguiente cmdlet para buscar todos los tipos de base de datos almacenados en este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="042e9-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="042e9-194">Use topology Builder para quitar la creación de reflejo de la base de datos del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="042e9-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="042e9-195">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="042e9-195">Open Topology Builder.</span></span> <span data-ttu-id="042e9-196">En la topología, expanda Grupos de servidores **front-end Enterprise Edition,** haga clic con el botón secundario en el nombre del grupo y, a continuación, haga clic **en Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="042e9-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="042e9-197">Para cada tipo de SQL almacén en el grupo de servidores, desactive la casilla SQL creación de reflejo **del** almacén.</span><span class="sxs-lookup"><span data-stu-id="042e9-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="042e9-198">Publique la topología modificada.</span><span class="sxs-lookup"><span data-stu-id="042e9-198">Publish the changed topology.</span></span> <span data-ttu-id="042e9-199">En el **menú Acción,** haga **clic en Topología** y, a continuación, **publique**.</span><span class="sxs-lookup"><span data-stu-id="042e9-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="042e9-200">A continuación, en la página de confirmación, haga clic **en Siguiente**</span><span class="sxs-lookup"><span data-stu-id="042e9-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="042e9-201">Use SQL Server Management Studio para romper el reflejo.</span><span class="sxs-lookup"><span data-stu-id="042e9-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="042e9-202">Abra SQL Server Management Studio, vaya a las bases de datos, haga clic con el botón secundario en **Tareas** y haga clic en **Reflejo.**</span><span class="sxs-lookup"><span data-stu-id="042e9-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="042e9-203">A continuación, **haga clic en Quitar creación** de reflejos y en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="042e9-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="042e9-204">Repita esto para todas las bases de datos del grupo de servidores que se convertirán en una AG.</span><span class="sxs-lookup"><span data-stu-id="042e9-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="042e9-205">Configure la característica clústeres de conmutación por error en todos los servidores de bases de datos que formarán parte de ag.</span><span class="sxs-lookup"><span data-stu-id="042e9-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="042e9-206">En cada servidor, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="042e9-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="042e9-207">Abra el Administrador del servidor y haga **clic en Agregar roles y características.**</span><span class="sxs-lookup"><span data-stu-id="042e9-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="042e9-208">Haga **clic en Siguiente** hasta que llegue al cuadro **Seleccionar** características.</span><span class="sxs-lookup"><span data-stu-id="042e9-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="042e9-209">En este caso, active la casilla clústeres de **conmutación** por error.</span><span class="sxs-lookup"><span data-stu-id="042e9-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="042e9-210">En el **cuadro Agregar características necesarias para clústeres de** conmutación por error, haga clic en Agregar **características.**</span><span class="sxs-lookup"><span data-stu-id="042e9-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="042e9-211">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="042e9-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="042e9-212">Validar la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="042e9-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="042e9-213">En el Administrador de servidores, haga clic en el **menú Herramientas** y, a continuación, haga clic en Administrador **de clústeres de conmutación por error.**</span><span class="sxs-lookup"><span data-stu-id="042e9-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="042e9-214">En **Acciones** en el lado derecho de la pantalla, haga clic **en Validar configuración.**</span><span class="sxs-lookup"><span data-stu-id="042e9-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="042e9-215">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-216">Seleccione los servidores que desea agregar al clúster y, a continuación, haga clic **en Ejecutar todas las pruebas.**</span><span class="sxs-lookup"><span data-stu-id="042e9-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="042e9-217">En el **cuadro Resumen,** compruebe los errores que informe el asistente.</span><span class="sxs-lookup"><span data-stu-id="042e9-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="042e9-218">A **continuación, haga clic** en Finalizar para completar la validación.</span><span class="sxs-lookup"><span data-stu-id="042e9-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="042e9-219">El asistente probablemente mostrará varias advertencias, especialmente si no usa almacenamiento compartido.</span><span class="sxs-lookup"><span data-stu-id="042e9-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="042e9-220">No es necesario usar el almacenamiento compartido.</span><span class="sxs-lookup"><span data-stu-id="042e9-220">You are not required to use shared storage.</span></span> <span data-ttu-id="042e9-221">Sin embargo, si ve algún **mensaje de error,** debe corregir esos problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="042e9-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="042e9-222">Cree el clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="042e9-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="042e9-223">En el Asistente **para la administración de clústeres de** conmutación por error, haga clic con el botón secundario en Administración de **clústeres de** conmutación por error y, a continuación, haga clic en Crear **clúster.**</span><span class="sxs-lookup"><span data-stu-id="042e9-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="042e9-224">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-225">Agregue el nombre del clúster y la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="042e9-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="042e9-226">Cuando se valide la configuración, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-227">En la página Confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-228">Después de crear el clúster, haga clic **en Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="042e9-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="042e9-229">Se recomienda configurar las opciones de quórum del clúster para usar un testigo de recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="042e9-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="042e9-230">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="042e9-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="042e9-231">Haga clic con el botón secundario en el nombre del clúster, haga clic en **Más acciones** y, a continuación, haga clic en Configurar la configuración de quórum **del clúster.**</span><span class="sxs-lookup"><span data-stu-id="042e9-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="042e9-232">En la página **Seleccionar opción de configuración de** quórum, haga clic en Seleccionar el testigo de **quórum.**</span><span class="sxs-lookup"><span data-stu-id="042e9-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="042e9-233">En la página **Seleccionar testigo de** quórum, haga clic en Configurar un testigo de recurso compartido de **archivos.**</span><span class="sxs-lookup"><span data-stu-id="042e9-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="042e9-234">En la **página Configurar testigo de recurso** compartido de archivos, escriba la ruta de acceso del recurso compartido de archivos que desea usar y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="042e9-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-235">En la página **Confirmación**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="042e9-236">En cada servidor del clúster, habilita la característica AG en SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="042e9-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="042e9-237">Abra el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="042e9-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="042e9-238">En el árbol del lado izquierdo de la pantalla, haga clic en **SQL Server Servicios** y, a continuación, haga doble clic en SQL Server servicio.</span><span class="sxs-lookup"><span data-stu-id="042e9-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="042e9-239">En el **cuadro Propiedades,** seleccione la **pestaña Alta disponibilidad de AlwaysOn.** Active la casilla **Habilitar grupos de disponibilidad AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="042e9-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="042e9-240">Reinicie el servicio SQL Server cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="042e9-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="042e9-241">Cree el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="042e9-242">Abra SQL Server Management Studio y conéctese a la SQL Server predeterminada.</span><span class="sxs-lookup"><span data-stu-id="042e9-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="042e9-243">En el Explorador de objetos, expanda la **carpeta De alta disponibilidad de AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="042e9-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="042e9-244">Haga clic con el botón secundario en **la carpeta Grupos de** disponibilidad y haga clic en Asistente para nuevo grupo de **disponibilidad.**</span><span class="sxs-lookup"><span data-stu-id="042e9-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="042e9-245">Si aparece **la página** Introducción, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="042e9-246">En la **página Especificar nombre del grupo de** disponibilidad, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="042e9-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="042e9-247">En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="042e9-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="042e9-248">A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="042e9-249">No incluya las bases de datos **ReportServer,** **ReportServerTempDB** o Persistent Chat en el grupo de disponibilidad AlwaysOn, ya que no se admiten en este escenario.</span><span class="sxs-lookup"><span data-stu-id="042e9-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="042e9-250">Puede incluir todas las demás bases de datos de Skype Empresarial Server en el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="042e9-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="042e9-251">En la **página Especificar réplicas,** haga clic en **la pestaña Réplicas.** A continuación, haga clic en el botón Agregar **réplicas** y conéctese a las otras instancias de SQL que ha unido como nodos del clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="042e9-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="042e9-252">Para cada instancia, seleccione las opciones **De conmutación por error automática** y Confirmación sincrónica. </span><span class="sxs-lookup"><span data-stu-id="042e9-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="042e9-253">No seleccione la opción **Secundaria legible.**</span><span class="sxs-lookup"><span data-stu-id="042e9-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="042e9-254">Haga clic **en la pestaña Puntos** de conexión y compruebe que el número **de** puerto esté establecido en 5022.</span><span class="sxs-lookup"><span data-stu-id="042e9-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="042e9-255">Haga clic en **la pestaña** Escucha y seleccione la opción Crear un agente de escucha de **grupo de** disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="042e9-256">En esa opción, escriba un nombre para el agente de escucha y establezca **el** puerto en 1433 (no se admiten otros puertos para esta opción).</span><span class="sxs-lookup"><span data-stu-id="042e9-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="042e9-257">Haga **clic en** Agregar y, a continuación, en el cuadro Dirección **IPv4,** proporcione su dirección IP virtual preferida y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="042e9-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="042e9-258">En  la página Seleccionar sincronización de datos iniciales, seleccione Completa y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta de servicio de SQL Server usada por ambas réplicas tenga permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="042e9-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="042e9-259">A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="042e9-260">Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="042e9-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="042e9-261">Si trabaja con bases de datos de gran tamaño, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no pueda acomodar el tamaño de las copias de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="042e9-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="042e9-262">En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="042e9-263">En la **página Resumen,** compruebe toda la configuración y haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="042e9-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="042e9-264">Cree un nuevo almacén que especifique el agente de escucha de AG y especifique la entidad de seguridad del reflejo antiguo como nodo principal del AG.</span><span class="sxs-lookup"><span data-stu-id="042e9-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="042e9-265">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="042e9-265">Open Topology Builder.</span></span> <span data-ttu-id="042e9-266">En la topología, expanda **Componentes** compartidos, haga clic con el botón secundario **en SQL Server Almacenes** y haga clic en Nuevo almacén SQL Server **compartido.**</span><span class="sxs-lookup"><span data-stu-id="042e9-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="042e9-267">En la página Definir nuevo almacén de  **SQL,** active primero la casilla configuración de alta disponibilidad y, a continuación, asegúrese de que SQL grupos de disponibilidad AlwaysOn aparece en el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="042e9-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="042e9-268">En el **SQL Server FQDN del** agente de escucha de disponibilidad, escriba el FQDN del agente de escucha que creó al crear el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="042e9-269">En el **SQL Server FQDN,** escriba el FQDN del nodo principal del GRUPO y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="042e9-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="042e9-270">Debe ser la entidad de seguridad del reflejo antiguo de este almacén.</span><span class="sxs-lookup"><span data-stu-id="042e9-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="042e9-271">Asocie el nuevo grupo de disponibilidad con el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="042e9-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="042e9-272">En el Generador de topologías, haga clic con el botón secundario en el grupo de servidores que desea asociar con el GRUPO y, a continuación, haga clic **en Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="042e9-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="042e9-273">En **Asociaciones**, en el cuadro **SQL Server Tienda,** seleccione la AG.</span><span class="sxs-lookup"><span data-stu-id="042e9-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="042e9-274">Seleccione el mismo grupo para cualquier otra base de datos del grupo de servidores que desee mover al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="042e9-275">Cuando esté seguro de que todas las bases de datos necesarias están establecidas en ag, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="042e9-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="042e9-276">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="042e9-276">Publish the topology.</span></span> <span data-ttu-id="042e9-277">En el **menú Acción,** haga **clic en Topología** y, a continuación, **publique**.</span><span class="sxs-lookup"><span data-stu-id="042e9-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="042e9-278">A continuación, en la página de confirmación, haga **clic en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="042e9-279">Realice algunos pasos finales para asegurarse de que SQL inicios de sesión en cada una de las réplicas del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="042e9-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="042e9-280">Abra el Generador de topologías, **seleccione Descargar topología de la implementación existente** y haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="042e9-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="042e9-281">Expanda Skype Empresarial Server, expanda la topología y expanda **SQL Server store.**</span><span class="sxs-lookup"><span data-stu-id="042e9-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="042e9-282">Haga clic con el botón secundario en SQL almacén de la nueva AG y, a continuación, haga clic **en Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="042e9-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="042e9-283">En la parte inferior de la página, en el cuadro **SQL Server FQDN,** cambie el valor al FQDN del agente de escucha del GRUPO.</span><span class="sxs-lookup"><span data-stu-id="042e9-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="042e9-284">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="042e9-284">Publish the topology.</span></span> <span data-ttu-id="042e9-285">En el **menú Acción,** haga **clic en Topología** y, a continuación, **publique**.</span><span class="sxs-lookup"><span data-stu-id="042e9-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="042e9-286">A continuación, en la página de confirmación, haga **clic en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="042e9-287">A continuación, espere unos minutos para que se replique la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="042e9-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="042e9-288">Abra SQL Server Management Studio y vaya al GRUPO.</span><span class="sxs-lookup"><span data-stu-id="042e9-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="042e9-289">Conmutación por error a una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="042e9-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="042e9-290">Abra el Shell de administración de Skype Empresarial Server y escriba el siguiente cmdlet para crear SQL inicios de sesión en esta réplica:</span><span class="sxs-lookup"><span data-stu-id="042e9-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="042e9-291">Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria y, a continuación,  `Install-CsDatabase -Update` use) para cada réplica del grupo.</span><span class="sxs-lookup"><span data-stu-id="042e9-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="042e9-292">Implementar un grupo de disponibilidad AlwaysOn en un grupo existente que no usa la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="042e9-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="042e9-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="042e9-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="042e9-294">Si el grupo de servidores que va a actualizar a una AG hospeda el almacén de administración central de su organización, primero debe mover el CMS a otro grupo antes de actualizar este grupo.</span><span class="sxs-lookup"><span data-stu-id="042e9-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="042e9-295">Use el cmdlet Move-CsManagementServer para mover el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="042e9-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="042e9-296">Si no tiene otro grupo de servidores en la organización, puede implementar un servidor Standard Edition temporalmente y mover el CMS a este servidor antes de actualizar el grupo a ag.</span><span class="sxs-lookup"><span data-stu-id="042e9-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="042e9-297">Configure la característica clústeres de conmutación por error en todos los servidores de bases de datos que formarán parte de ag.</span><span class="sxs-lookup"><span data-stu-id="042e9-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="042e9-298">En cada servidor, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="042e9-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="042e9-299">Abra el Administrador del servidor y haga **clic en Agregar roles y características.**</span><span class="sxs-lookup"><span data-stu-id="042e9-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="042e9-300">Haga **clic en Siguiente** hasta que llegue al cuadro **Seleccionar** características.</span><span class="sxs-lookup"><span data-stu-id="042e9-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="042e9-301">En este caso, active la casilla clústeres de **conmutación** por error.</span><span class="sxs-lookup"><span data-stu-id="042e9-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="042e9-302">En el **cuadro Agregar características necesarias para clústeres de** conmutación por error, haga clic en Agregar **características.**</span><span class="sxs-lookup"><span data-stu-id="042e9-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="042e9-303">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="042e9-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="042e9-304">Validar la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="042e9-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="042e9-305">En el Administrador de servidores, haga clic en el **menú Herramientas** y, a continuación, haga clic en Administrador **de clústeres de conmutación por error.**</span><span class="sxs-lookup"><span data-stu-id="042e9-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="042e9-306">En **Acciones** en el lado derecho de la pantalla, haga clic **en Validar configuración.**</span><span class="sxs-lookup"><span data-stu-id="042e9-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="042e9-307">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-308">Seleccione los servidores que desea agregar al clúster y, a continuación, haga clic **en Ejecutar todas las pruebas.**</span><span class="sxs-lookup"><span data-stu-id="042e9-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="042e9-309">En el **cuadro Resumen,** compruebe los errores que informe el asistente.</span><span class="sxs-lookup"><span data-stu-id="042e9-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="042e9-310">A **continuación, haga clic** en Finalizar para completar la validación.</span><span class="sxs-lookup"><span data-stu-id="042e9-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="042e9-311">El asistente probablemente mostrará varias advertencias, especialmente si no usa almacenamiento compartido.</span><span class="sxs-lookup"><span data-stu-id="042e9-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="042e9-312">No es necesario usar el almacenamiento compartido.</span><span class="sxs-lookup"><span data-stu-id="042e9-312">You are not required to use shared storage.</span></span> <span data-ttu-id="042e9-313">Sin embargo, si ve algún **mensaje de error,** debe corregir esos problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="042e9-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="042e9-314">Crear el clúster de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="042e9-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="042e9-315">En el Asistente **para la administración de clústeres de** conmutación por error, haga clic con el botón secundario en Administración de **clústeres de** conmutación por error y, a continuación, haga clic en Crear **clúster.**</span><span class="sxs-lookup"><span data-stu-id="042e9-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="042e9-316">En la página **Antes de empezar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-317">Agregue el nombre del clúster y la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="042e9-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="042e9-318">Cuando se valide la configuración, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-319">En la página Confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-320">Después de crear el clúster, haga clic **en Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="042e9-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="042e9-321">Se recomienda configurar las opciones de quórum del clúster para usar un testigo de recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="042e9-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="042e9-322">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="042e9-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="042e9-323">Haga clic con el botón secundario en el nombre del clúster, haga clic en **Más acciones** y, a continuación, haga clic en Configurar la configuración de quórum **del clúster.**</span><span class="sxs-lookup"><span data-stu-id="042e9-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="042e9-324">En la página **Seleccionar opción de configuración de** quórum, haga clic en Seleccionar el testigo de **quórum.**</span><span class="sxs-lookup"><span data-stu-id="042e9-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="042e9-325">En la página **Seleccionar testigo de** quórum, haga clic en Configurar un testigo de recurso compartido de **archivos.**</span><span class="sxs-lookup"><span data-stu-id="042e9-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="042e9-326">En la **página Configurar testigo de recurso** compartido de archivos, escriba la ruta de acceso del recurso compartido de archivos que desea usar y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="042e9-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-327">En la página **Confirmación**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="042e9-328">En cada servidor del clúster, habilita AG en SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="042e9-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="042e9-329">Abra el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="042e9-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="042e9-330">En el árbol del lado izquierdo de la pantalla, haga clic en **SQL Server Servicios** y, a continuación, haga doble clic en SQL Server servicio.</span><span class="sxs-lookup"><span data-stu-id="042e9-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="042e9-331">En el **cuadro Propiedades,** seleccione la **pestaña Alta disponibilidad de AlwaysOn.** Active la casilla **Habilitar grupos de disponibilidad AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="042e9-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="042e9-332">Reinicie el servicio SQL Server cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="042e9-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="042e9-333">Cree el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="042e9-334">Abra SQL Server Management Studio y conéctese a la SQL Server predeterminada.</span><span class="sxs-lookup"><span data-stu-id="042e9-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="042e9-335">En el Explorador de objetos, expanda la **carpeta De alta disponibilidad de AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="042e9-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="042e9-336">Haga clic con el botón secundario en **la carpeta Grupos de** disponibilidad y haga clic en Asistente para nuevo grupo de **disponibilidad.**</span><span class="sxs-lookup"><span data-stu-id="042e9-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="042e9-337">Si aparece **la página** Introducción, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-338">En la **página Especificar nombre del grupo de** disponibilidad, escriba el nombre del grupo de disponibilidad y haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="042e9-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-339">En la página Seleccionar bases de datos, seleccione las bases de datos que desea incluir en el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="042e9-340">A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="042e9-341">No incluya las bases de datos **ReportServer,** **ReportServerTempDB** o Persistent Chat en la AG, ya que no se admiten en este escenario.</span><span class="sxs-lookup"><span data-stu-id="042e9-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="042e9-342">Puede incluir todas las demás bases de datos de Skype Empresarial Server en la AG.</span><span class="sxs-lookup"><span data-stu-id="042e9-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="042e9-343">En la **página Especificar réplicas,** haga clic en **la pestaña Réplicas.** A continuación, haga clic en el botón Agregar **réplicas** y conéctese a las demás instancias SQL que ha unido como nodos de WSFC.</span><span class="sxs-lookup"><span data-stu-id="042e9-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="042e9-344">Para cada instancia, seleccione las opciones **De conmutación por error automática** y Confirmación sincrónica. </span><span class="sxs-lookup"><span data-stu-id="042e9-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="042e9-345">No seleccione la opción **Secundaria legible.**</span><span class="sxs-lookup"><span data-stu-id="042e9-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="042e9-346">Haga clic **en la pestaña Puntos** de conexión y compruebe que el número **de** puerto esté establecido en 5022.</span><span class="sxs-lookup"><span data-stu-id="042e9-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="042e9-347">Haga clic en **la pestaña** Escucha y seleccione la opción Crear un agente de escucha de **grupo de** disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="042e9-348">En esa opción, escriba un nombre para el agente de escucha y establezca **el** puerto en 1433 (no se admiten otros puertos para esta opción).</span><span class="sxs-lookup"><span data-stu-id="042e9-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="042e9-349">Haga **clic en** Agregar y, a continuación, en el cuadro Dirección **IPv4,** proporcione su dirección IP virtual preferida y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="042e9-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="042e9-350">En  la página Seleccionar sincronización de datos iniciales, seleccione Completa y especifique una carpeta que sea accesible para las réplicas y para la que la cuenta de servicio de SQL Server usada por ambas réplicas tenga permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="042e9-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="042e9-351">A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="042e9-352">Este recurso compartido de archivos se usará temporalmente al inicializar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="042e9-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="042e9-353">Si trabaja con bases de datos de gran tamaño, le recomendamos que las inicialice manualmente en caso de que el ancho de banda de red no pueda acomodar el tamaño de las copias de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="042e9-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="042e9-354">En la página Validación, compruebe que todas las comprobaciones de validación se realizan correctamente y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="042e9-355">En la **página Resumen,** compruebe toda la configuración y haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="042e9-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="042e9-356">Cree un nuevo almacén que especifique el agente de escucha de AG.</span><span class="sxs-lookup"><span data-stu-id="042e9-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="042e9-357">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="042e9-357">Open Topology Builder.</span></span> <span data-ttu-id="042e9-358">En la topología, expanda **Componentes** compartidos, haga clic con el botón secundario **en SQL Server Almacenes** y haga clic en Nuevo almacén SQL Server **compartido.**</span><span class="sxs-lookup"><span data-stu-id="042e9-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="042e9-359">En la página Definir nuevo almacén de  **SQL,** active primero la casilla configuración de alta disponibilidad y, a continuación, asegúrese de que SQL grupos de disponibilidad AlwaysOn aparece en el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="042e9-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="042e9-360">En el **SQL Server FQDN del** agente de escucha de disponibilidad, escriba el FQDN del agente de escucha que creó al crear el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="042e9-361">En el **SQL Server FQDN,** escriba el FQDN del nodo principal del GRUPO y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="042e9-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="042e9-362">Asocie el nuevo grupo de disponibilidad AlwaysOn con el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="042e9-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="042e9-363">En el Generador de topologías, haga clic con el botón secundario en el grupo de servidores que desea asociar con el GRUPO y, a continuación, haga clic **en Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="042e9-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="042e9-364">En **Asociaciones**, en el cuadro **SQL Server Tienda,** seleccione la AG.</span><span class="sxs-lookup"><span data-stu-id="042e9-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="042e9-365">Seleccione el mismo grupo para cualquier otra base de datos del grupo de servidores que desee mover al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="042e9-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="042e9-366">Cuando esté seguro de que todas las bases de datos necesarias están establecidas en ag, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="042e9-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="042e9-367">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="042e9-367">Publish the topology.</span></span> <span data-ttu-id="042e9-368">En el **menú Acción,** haga **clic en Topología** y, a continuación, **publique**.</span><span class="sxs-lookup"><span data-stu-id="042e9-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="042e9-369">A continuación, en la página de confirmación, haga **clic en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="042e9-370">Realice algunos pasos finales para asegurarse de que los SQL inicios de sesión están en cada una de las réplicas del GRUPO.</span><span class="sxs-lookup"><span data-stu-id="042e9-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="042e9-371">Abra el Generador de topologías, **seleccione Descargar topología de la implementación existente** y haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="042e9-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="042e9-372">Expanda Skype Empresarial Server, expanda la topología y expanda **SQL Server store.**</span><span class="sxs-lookup"><span data-stu-id="042e9-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="042e9-373">Haga clic con el botón secundario en SQL almacén de la nueva AG y, a continuación, haga clic **en Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="042e9-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="042e9-374">En la parte inferior de la página, en el cuadro **SQL Server FQDN,** cambie el valor al FQDN del agente de escucha del GRUPO.</span><span class="sxs-lookup"><span data-stu-id="042e9-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="042e9-375">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="042e9-375">Publish the topology.</span></span> <span data-ttu-id="042e9-376">En el **menú Acción,** haga **clic en Topología** y, a continuación, **publique**.</span><span class="sxs-lookup"><span data-stu-id="042e9-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="042e9-377">A continuación, en la página de confirmación, haga **clic en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="042e9-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="042e9-378">A continuación, espere unos minutos para que se replique la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="042e9-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="042e9-379">Abra SQL Server Management Studio y vaya al GRUPO.</span><span class="sxs-lookup"><span data-stu-id="042e9-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="042e9-380">Conmutación por error a una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="042e9-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="042e9-381">Abra el Shell de administración de Skype Empresarial Server y escriba el siguiente cmdlet para crear SQL inicios de sesión en esta réplica:</span><span class="sxs-lookup"><span data-stu-id="042e9-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="042e9-382">Repita los dos pasos anteriores (conmutar por error el grupo a una réplica secundaria y, a continuación,  `Install-CsDatabase -Update` use) para cada réplica del grupo.</span><span class="sxs-lookup"><span data-stu-id="042e9-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
