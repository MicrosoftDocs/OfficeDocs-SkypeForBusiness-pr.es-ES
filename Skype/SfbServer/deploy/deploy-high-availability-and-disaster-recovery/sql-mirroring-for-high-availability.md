---
title: Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar como mínimo SQL Server 2008 R2. Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo. Para obtener información detallada, vea acumulado 9 de paquete de actualización para el Service Pack 1 de SQL Server 2008.'
ms.openlocfilehash: 8de94fc0e15b1d851b43b386b476abfa776fad2d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="70326-105">Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="70326-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>
 

<span data-ttu-id="70326-106">Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar como mínimo SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="70326-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="70326-107">Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo.</span><span class="sxs-lookup"><span data-stu-id="70326-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="70326-108">Para obtener información detallada, vea [9 para SQL Server 2008 Service Pack 1 del paquete de actualización acumulativa ](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span><span class="sxs-lookup"><span data-stu-id="70326-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1 ](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>
  
<span data-ttu-id="70326-109">En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70326-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="70326-110">Versión del servidor principal de SQL Server debe ser compatible con la creación de reflejos de SQL.</span><span class="sxs-lookup"><span data-stu-id="70326-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="70326-111">El servidor principal, el reflejo y el testigo (si se implementan) necesitan tener la misma versión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70326-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="70326-p103">El servidor principal y el reflejo necesitan tener la misma edición de SQL Server. El testigo puede tener una edición diferente.</span><span class="sxs-lookup"><span data-stu-id="70326-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="70326-114">Para recomendaciones SQL en términos de qué versiones SQL son compatibles para un rol de testigo, vea [Testigo de reflejo de base de datos](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span><span class="sxs-lookup"><span data-stu-id="70326-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>
  
<span data-ttu-id="70326-115">Utilice el generador de topología para implementar la creación de reflejos de SQL.</span><span class="sxs-lookup"><span data-stu-id="70326-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="70326-116">Seleccione una opción en el generador de topología para reflejar las bases de datos y generador de topología configura el reflejo (incluyendo la configuración de un testigo, si se desea) al publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="70326-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="70326-117">Tenga en cuenta que configurar o quitar al testigo al mismo tiempo, configurar o quitar el espejo.</span><span class="sxs-lookup"><span data-stu-id="70326-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="70326-118">No hay ningún comando independiente para implementar o quitar a sólo un testigo.</span><span class="sxs-lookup"><span data-stu-id="70326-118">There is no separate command to deploy or remove only a witness.</span></span>
  
<span data-ttu-id="70326-119">Para configurar la creación de reflejo de servidor, es necesario que primero configure los permisos de base de datos SQL correctamente.</span><span class="sxs-lookup"><span data-stu-id="70326-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="70326-120">Para obtener más información, consulte [Set Up Accounts inicio de sesión para la creación de reflejo de base de datos o grupos de disponibilidad AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span><span class="sxs-lookup"><span data-stu-id="70326-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="70326-p106">Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa**. Esto significa que es preciso controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se necesita crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Recomendamos que determine el crecimiento estimado del registro de transacciones para la carga de trabajo de la implementación, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:</span><span class="sxs-lookup"><span data-stu-id="70326-p106">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
- [<span data-ttu-id="70326-125">Modelos de recuperación de base de datos</span><span class="sxs-lookup"><span data-stu-id="70326-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)
    
- [<span data-ttu-id="70326-126">Visión general de backup</span><span class="sxs-lookup"><span data-stu-id="70326-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)
    
- [<span data-ttu-id="70326-127">Registro de copia de seguridad de transacciones</span><span class="sxs-lookup"><span data-stu-id="70326-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)
    
<span data-ttu-id="70326-128">Con el reflejo de SQL, puede configurar la topología de creación de reflejos al crear los grupos o después de que ya se hayan creado los grupos.</span><span class="sxs-lookup"><span data-stu-id="70326-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="70326-129">Mediante el generador de topología o cmdlets para configurar y quitar SQL reflejo sólo se admite cuando el principal, réplica y servidores testigo (si lo desea) pertenecen al mismo dominio.</span><span class="sxs-lookup"><span data-stu-id="70326-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="70326-130">Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70326-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="70326-131">Siempre que haga algún cambio en las conexiones entre reflejos de la base de datos back-end, deberá reiniciar todos los servidores front-end del grupo de servidores. </span><span class="sxs-lookup"><span data-stu-id="70326-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="70326-132">> Para un cambio en el reflejo, (como cambiar la ubicación de un espejo), debe utilizar el generador de topología para realizar estos tres pasos:</span><span class="sxs-lookup"><span data-stu-id="70326-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
  
1. <span data-ttu-id="70326-133">Quite reflejos del servidor reflejado antiguo.</span><span class="sxs-lookup"><span data-stu-id="70326-133">Remove mirroring from the old mirror server.</span></span>
    
2. <span data-ttu-id="70326-134">Agregue reflejos al servidor reflejado nuevo.</span><span class="sxs-lookup"><span data-stu-id="70326-134">Add mirroring to the new mirror server.</span></span>
    
3. <span data-ttu-id="70326-135">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="70326-135">Publish the topology.</span></span>
    
> [!NOTE]
> <span data-ttu-id="70326-136">Hay que crear un recurso compartido de archivos en el que puedan escribirse los archivos reflejados, y el servicio en el que se ejecutan SQL Server y SQL Agent necesita acceso de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="70326-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="70326-137">Si el servicio SQL Server se ejecuta bajo el contexto de servicio de red, puede agregar \<dominio\>\\< SQLSERVERNAME\>$ de los servidores SQL de espejo y Principal a los permisos de recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="70326-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="70326-138">El $ es importante para identificar si se trata de una cuenta de equipo.</span><span class="sxs-lookup"><span data-stu-id="70326-138">The $ is important to identify that this is a computer account.</span></span> 
  
## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="70326-139">Para configurar la creación de reflejos de SQL al crear un grupo en el generador de topología</span><span class="sxs-lookup"><span data-stu-id="70326-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="70326-140">En la página **Definir el almacén de SQL**, haga clic en **Nuevo** junto al cuadro **Almacén de SQL**. </span><span class="sxs-lookup"><span data-stu-id="70326-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>
    
2. <span data-ttu-id="70326-141">En la página **Definir nuevo almacén de SQL**, especifique el almacén principal, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejo de SQL (el valor predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="70326-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>
    
3. <span data-ttu-id="70326-142">De vuelta en la página **Definir el almacén de SQL**, seleccione **Activar la creación de reflejo del almacén de SQL**. </span><span class="sxs-lookup"><span data-stu-id="70326-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span> 
    
4. <span data-ttu-id="70326-p110">En la página **Definir nuevo almacén de SQL**, especifique el almacén de SQL que se utilizará como reflejo, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto (el valor predeterminado es 5022) y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="70326-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>
    
5. <span data-ttu-id="70326-145">Si desea un testigo para este reflejo, realice lo siguiente: </span><span class="sxs-lookup"><span data-stu-id="70326-145">If you want a witness for this mirror, do the following:</span></span> 
    
    <span data-ttu-id="70326-146">a.</span><span class="sxs-lookup"><span data-stu-id="70326-146">a.</span></span> <span data-ttu-id="70326-147">Seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática**. </span><span class="sxs-lookup"><span data-stu-id="70326-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span> 
    
    <span data-ttu-id="70326-148">b.</span><span class="sxs-lookup"><span data-stu-id="70326-148">b.</span></span> <span data-ttu-id="70326-149">En la página **Definir el almacén de SQL**, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y especifique el almacén de SQL que se utilizará como testigo. </span><span class="sxs-lookup"><span data-stu-id="70326-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span> 
    
    <span data-ttu-id="70326-150">c.</span><span class="sxs-lookup"><span data-stu-id="70326-150">c.</span></span> <span data-ttu-id="70326-151">Especifique el número de puerto (el valor predeterminado es 7022) y haga clic en **Aceptar**. </span><span class="sxs-lookup"><span data-stu-id="70326-151">Specify the port number (the default is 7022) and click **OK**.</span></span> 
    
6. <span data-ttu-id="70326-152">Cuando termine de definir el grupo de servidores Front-End y todas las demás funciones en la topología, utilice el generador de topología para publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="70326-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="70326-153">Cuando se publica la topología, si el grupo de Front-End que aloja el almacén de Administración Central tiene la creación de reflejos de SQL habilitado, verá una opción para crear ambos principal y realiza espejado de bases de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="70326-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="70326-154">Haga clic en **Configuración** y escriba la ruta de acceso que se utilizará como recurso compartido de archivos para la copia de seguridad del reflejo.</span><span class="sxs-lookup"><span data-stu-id="70326-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="70326-p115">Haga clic en **Aceptar** y luego en **Siguiente** para crear las bases de datos y publicar la topología. Se implementarán los servidores de reflejo y de testigo (si se especificó).</span><span class="sxs-lookup"><span data-stu-id="70326-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>
    
<span data-ttu-id="70326-157">Puede utilizar el generador de topología para editar las propiedades de un grupo ya existente para permitir la creación de reflejos de SQL.</span><span class="sxs-lookup"><span data-stu-id="70326-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span> 
  
## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="70326-158">Para agregar la creación de reflejos de SQL a un grupo existente de Front-End en el generador de topología</span><span class="sxs-lookup"><span data-stu-id="70326-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="70326-159">En el generador de topología (ratón) en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="70326-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="70326-160">Seleccione **Habilitar creación de reflejos del almacén de SQL** y, después, haga clic en **Nuevo**, junto a **Creación de reflejos del almacén de SQL**. </span><span class="sxs-lookup"><span data-stu-id="70326-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span> 
    
3. <span data-ttu-id="70326-161">Especifique el almacén de SQL que desea utilizar como reflejo. </span><span class="sxs-lookup"><span data-stu-id="70326-161">Specify the SQL store that you want to use as the mirror.</span></span> 
    
4. <span data-ttu-id="70326-162">Seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="70326-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>
    
5. <span data-ttu-id="70326-163">Si desea configurar un testigo, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Nuevo**. </span><span class="sxs-lookup"><span data-stu-id="70326-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span> 
    
6. <span data-ttu-id="70326-164">Especifique el almacén de SQL que desea utilizar como testigo. </span><span class="sxs-lookup"><span data-stu-id="70326-164">Specify the SQL store that you want to use as the witness.</span></span> 
    
7. <span data-ttu-id="70326-165">Seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 7022) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="70326-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>
    
8. <span data-ttu-id="70326-166">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="70326-166">Click **OK**.</span></span>
    
9. <span data-ttu-id="70326-p116">Publique la topología. Al hacerlo, se le va a solicitar instalar la base de datos. </span><span class="sxs-lookup"><span data-stu-id="70326-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span> 
    
    <span data-ttu-id="70326-p117">Durante el proceso de publicación de la topología, se le pedirá que defina una ruta del recurso compartido de archivos. Los servidores SQL Server que participan en el reflejo deben tener acceso de lectura y escritura a este recurso compartido de archivos para que se establezca el reflejo.</span><span class="sxs-lookup"><span data-stu-id="70326-p117">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>
    
<span data-ttu-id="70326-171">A continuación, debe instalar la base de datos antes de continuar con el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="70326-171">You must then install the database before going on to the next procedure.</span></span>
  
<span data-ttu-id="70326-172">Debe tener en cuenta lo siguiente al configurar la creación de reflejos de SQL:</span><span class="sxs-lookup"><span data-stu-id="70326-172">You should keep the following in mind when setting up SQL mirroring:</span></span>
  
- <span data-ttu-id="70326-173">Si ya existe un extremo de creación de reflejos, se volverá a utilizar junto con los puertos definidos allí y pasará por alto los que especifique en la topología.</span><span class="sxs-lookup"><span data-stu-id="70326-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>
    
- <span data-ttu-id="70326-p118">Cualquier puerto que ya haya sido asignado a otras aplicaciones en el mismo servidor, incluidos aquellos para otras instancias de SQL, no deben utilizarse para las instancias de SQL instaladas a mano. Esto implica que si tiene más de una instancia de SQL instalada en el mismo servidor, no deben usar el mismo puerto para la creación de reflejos. Para obtener más información, consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="70326-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
  - [<span data-ttu-id="70326-177">Especificar una dirección de red de servidor (creación de reflejo de base de datos)</span><span class="sxs-lookup"><span data-stu-id="70326-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)
    
  - [<span data-ttu-id="70326-178">La base de datos reflejada extremo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="70326-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)
    
## <a name="using-skype-for-business-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="70326-179">Utiliza Skype para los Cmdlets del Shell de administración de Business Server para configurar el reflejo de SQL</span><span class="sxs-lookup"><span data-stu-id="70326-179">Using Skype for Business Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="70326-180">La forma más sencilla de establecer la creación de reflejos es mediante el generador de topología, pero también puede hacerlo mediante cmdlets.</span><span class="sxs-lookup"><span data-stu-id="70326-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>
  
1. <span data-ttu-id="70326-181">Abra un Skype para la ventana de Shell de administración de servidor empresarial y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="70326-181">Open a Skype for Business Server Management Shell window and run the following cmdlet:</span></span>
    
   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 

   ```

    <span data-ttu-id="70326-182">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="70326-182">For example:</span></span>
    
   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 

   ```

    <span data-ttu-id="70326-183">Aparecerá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70326-183">You will see the following:</span></span>
    
  ```
  Database Name:rtcxds 
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rtcshared 
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rtcab 
        Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
         Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rgsconfig 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rgsdyn 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:cpsdyn 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:xds 
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:lis 
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

  ```

2. <span data-ttu-id="70326-184">Compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70326-184">Verify the following:</span></span>
    
    - <span data-ttu-id="70326-185">El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server primario e04-ocs.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="70326-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span> 
    
    - <span data-ttu-id="70326-186">El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server de reflejo K16-ocs.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="70326-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span> 
    
    - <span data-ttu-id="70326-187">El puerto 7022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server testigo AB14-lct.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="70326-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span> 
    
   - <span data-ttu-id="70326-188">Las cuentas de los servidores de SQL en todos los principales y los servidores SQL de espejo tienen permiso de lectura y escritura al recurso compartido de archivo \\E04 OCS\csdatabackup</span><span class="sxs-lookup"><span data-stu-id="70326-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span> 
    
   - <span data-ttu-id="70326-p119">Asegúrese de que el proveedor de Instrumental de administración de Windows (WMI) se está ejecutando en todos estos servidores. El cmdlet utiliza dicho proveedor para encontrar la información de cuenta de los servicios de SQL Server que se ejecutan en el servidor principal, el reflejado y el testigo. </span><span class="sxs-lookup"><span data-stu-id="70326-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span> 
    
   - <span data-ttu-id="70326-191">Asegúrese de que la cuenta que ejecuta este cmdlet tiene permiso para crear las carpetas que contendrán los archivos de registro y los datos de todos los servidores reflejados. </span><span class="sxs-lookup"><span data-stu-id="70326-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span> 
    
   - <span data-ttu-id="70326-p120">Es necesario que la cuenta de usuario en que se ejecuta la instancia de SQL tenga permisos de lectura y escritura en el recurso compartido de archivos. Si este recurso se encuentra en un servidor distinto y la instancia de SQL se ejecuta en una cuenta del sistema local, asegúrese de conceder los permisos del recurso compartido de archivos al servidor en que se hospeda la instancia de SQL.</span><span class="sxs-lookup"><span data-stu-id="70326-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>
    
3. <span data-ttu-id="70326-194">Escriba A y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="70326-194">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="70326-195">Se configurará la creación de reflejos.</span><span class="sxs-lookup"><span data-stu-id="70326-195">The mirroring will be configured.</span></span>
    
    <span data-ttu-id="70326-196">**CsMirrorDatabase de instalación** instala el espejo y configura espejado para todas las bases de datos están presentes en el almacén principal de SQL.</span><span class="sxs-lookup"><span data-stu-id="70326-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="70326-197">Si desea configurar el reflejo de bases de datos específicas, puede utilizar la opción - tipodebasededatos, o si desea configurar el reflejo de todas las bases de datos excepto algunos, puede utilizar la opción - ExcludeDatabaseList, junto con una lista separada por comas de base de datos Para excluir los nombres.</span><span class="sxs-lookup"><span data-stu-id="70326-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>
  
    <span data-ttu-id="70326-198">Por ejemplo, si agrega la opción siguiente para **Instalar CsMirrorDatabase**, se reflejará todas las bases de datos excepto rtcab y rtcxds.</span><span class="sxs-lookup"><span data-stu-id="70326-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>
  
    `-ExcludeDatabaseList rtcab,rtcxds`
  
   <span data-ttu-id="70326-199">Por ejemplo, si agrega la opción siguiente para **Instalar CsMirrorDatabase**, se reflejará sólo las bases de datos rtcab, rtcshared y rtcxds.</span><span class="sxs-lookup"><span data-stu-id="70326-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>
  
    `-DatabaseType User`
  
## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="70326-200">Supresión o cambio de un reflejo de SQL</span><span class="sxs-lookup"><span data-stu-id="70326-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="70326-p122">Para quitar un reflejo de SQL de un grupo de servidores en el Generador de topologías, primero se debe quitar el reflejo en SQL Server utilizando un cmdlet. Después, podrá usar el Generador de topologías para quitar el reflejo de la topología. Para quitar el reflejo de SQL Server, use este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="70326-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

```

<span data-ttu-id="70326-204">Por ejemplo, para quitar reflejos y anular las bases de datos de las bases de datos del usuario, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70326-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

```

<span data-ttu-id="70326-205">La `-DropExistingDatabasesOnMirror` opción hace que las bases de datos afectadas se eliminarán del espejo retrovisor.</span><span class="sxs-lookup"><span data-stu-id="70326-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>
  
<span data-ttu-id="70326-206">Luego, para quitar el reflejo de la topología, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70326-206">Then, to remove the mirror from the topology, do the following:</span></span>
  
1. <span data-ttu-id="70326-207">En Generador de topologías, haga clic con el botón derecho en el grupo y haga clic en **Modificar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="70326-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="70326-208">Desactive **Habilitar creación de reflejos del almacén de SQL** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="70326-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>
    
3. <span data-ttu-id="70326-209">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="70326-209">Publish the topology.</span></span>
    
## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="70326-210">Supresión de un testigo de creación de reflejo</span><span class="sxs-lookup"><span data-stu-id="70326-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="70326-211">Utilice este procedimiento si necesita quitar al testigo de un nuevo servidor configuración de creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="70326-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>
  
1. <span data-ttu-id="70326-212">En Generador de topologías, haga clic con el botón derecho en el grupo y haga clic en **Modificar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="70326-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span> 
    
2. <span data-ttu-id="70326-213">Desactive **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="70326-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>
    
3. <span data-ttu-id="70326-214">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="70326-214">Publish the topology.</span></span>
    
    <span data-ttu-id="70326-215">Después de publicar la topología, el generador de topología se verá un mensaje que incluye la siguiente</span><span class="sxs-lookup"><span data-stu-id="70326-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="70326-216">Sin embargo, no siga este paso y no escriba `Uninstall-CsMirrorDatabase` como que sería desinstalar toda la configuración de creación de reflejos.</span><span class="sxs-lookup"><span data-stu-id="70326-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>
    
4. <span data-ttu-id="70326-217">Para quitar a sólo el testigo de la configuración de SQL Server, siga las instrucciones para [quitar al testigo de una sesión de creación de reflejo de base de datos (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span><span class="sxs-lookup"><span data-stu-id="70326-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>
    

