---
title: Implementar SQL creación de reflejos para la alta disponibilidad del servidor back-end en Skype Empresarial Server 2015
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
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar un mínimo de SQL Server 2008 R2. Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo. Para obtener más información, vea Paquete de actualización acumulativa 9 para SQL Server 2008 Service Pack 1 .'
ms.openlocfilehash: 38c3e749b39cd510623232e9f29ace03a1c19f6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100726"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="31c9b-105">Implementar SQL creación de reflejos para la alta disponibilidad del servidor back-end en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="31c9b-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="31c9b-106">Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar un mínimo de SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="31c9b-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="31c9b-107">Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="31c9b-108">Para obtener más información, vea Paquete de actualización [acumulativa 9 para SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span><span class="sxs-lookup"><span data-stu-id="31c9b-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="31c9b-109">En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="31c9b-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="31c9b-110">La versión del servidor principal de SQL Server debe admitir SQL creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="31c9b-111">El servidor principal, reflejo y testigo (si se implementan) deben tener la misma versión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="31c9b-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="31c9b-p103">El servidor principal y el reflejo deben tener la misma edición de SQL Server. El testigo puede tener una edición diferente.</span><span class="sxs-lookup"><span data-stu-id="31c9b-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="31c9b-114">Para SQL procedimientos recomendados en términos de lo que SQL versiones son compatibles con un rol testigo, vea Testigo de [creación de reflejo de base de datos](/sql/database-engine/database-mirroring/database-mirroring-witness).</span><span class="sxs-lookup"><span data-stu-id="31c9b-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).</span></span>

<span data-ttu-id="31c9b-115">El Generador de topologías se usa para implementar SQL creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="31c9b-116">Seleccione una opción en el Generador de topologías para reflejar las bases de datos y el Generador de topologías configura la creación de reflejos (incluida la configuración de un testigo, si lo desea) al publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="31c9b-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="31c9b-117">Tenga en cuenta que configura o quita el testigo al mismo tiempo que configura o quita el reflejo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="31c9b-118">No hay ningún comando independiente para implementar o quitar solo un testigo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="31c9b-119">Para configurar la creación de reflejo de servidor, es necesario que primero configure los permisos de base de datos SQL correctamente.</span><span class="sxs-lookup"><span data-stu-id="31c9b-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="31c9b-120">Para obtener más información, vea [Set Up Login Accounts for Database Mirroring o AlwaysOn Availability Groups (SQL Server).](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)</span><span class="sxs-lookup"><span data-stu-id="31c9b-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).</span></span>

<span data-ttu-id="31c9b-121">Con la creación de reflejo de SQL, el modo de recuperación de bases de datos siempre está establecido en **Completo,** lo que significa que debe supervisar estrechamente el tamaño del registro de transacciones y hacer una copia de seguridad de los registros de transacciones de forma regular para evitar que se queme el espacio en disco en los servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="31c9b-121">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="31c9b-122">La frecuencia de las copias de seguridad del registro de transacciones depende de la tasa de crecimiento del registro, que a su vez depende de las transacciones de base de datos en las que incurran las actividades del usuario en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="31c9b-122">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="31c9b-123">Se recomienda determinar cuánto crecimiento del registro de transacciones se espera para la carga de trabajo de implementación, de modo que pueda realizar la planeación en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="31c9b-123">We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="31c9b-124">Los siguientes artículos proporcionan información adicional sobre la SQL de copia de seguridad y registro:</span><span class="sxs-lookup"><span data-stu-id="31c9b-124">The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="31c9b-125">Modelos de recuperación de bases de datos</span><span class="sxs-lookup"><span data-stu-id="31c9b-125">Database recovery models</span></span>](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [<span data-ttu-id="31c9b-126">Introducción a la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="31c9b-126">Backup overview</span></span>](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [<span data-ttu-id="31c9b-127">Registro de transacciones de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="31c9b-127">Backup transaction log</span></span>](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

<span data-ttu-id="31c9b-128">Con el reflejo de SQL, puede configurar la topología de creación de reflejos al crear los grupos o después de que ya se hayan creado los grupos.</span><span class="sxs-lookup"><span data-stu-id="31c9b-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31c9b-129">El uso del Generador de topologías o cmdlets para configurar y quitar la creación de reflejo de SQL solo se admite cuando los servidores principales, reflejados y testigos (si se desea) pertenecen al mismo dominio.</span><span class="sxs-lookup"><span data-stu-id="31c9b-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="31c9b-130">Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación sobre SQL Server.</span><span class="sxs-lookup"><span data-stu-id="31c9b-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31c9b-131">Siempre que haga algún cambio en las conexiones entre reflejos de la base de datos back-end, deberá reiniciar todos los servidores front-end del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="31c9b-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="31c9b-132">> Para un cambio en la creación de reflejos (como cambiar la ubicación de un reflejo), debe usar el Generador de topologías para realizar estos tres pasos:</span><span class="sxs-lookup"><span data-stu-id="31c9b-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="31c9b-133">Quitar reflejos del servidor reflejado antiguo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="31c9b-134">Agregar reflejos al servidor reflejado nuevo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="31c9b-135">Publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="31c9b-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="31c9b-136">Debe crearse un recurso compartido de archivos para que se escriban los archivos reflejados y el servicio en el que SQL Server y SQL agente se ejecuten en necesita acceso de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="31c9b-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="31c9b-137">Si el servicio SQL Server se ejecuta en el contexto del servicio de red, puede agregar \<Domain\> \\<SQLSERVERNAME $ de los servidores principales y de SQL reflejados a los permisos de recurso \> compartido.</span><span class="sxs-lookup"><span data-stu-id="31c9b-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="31c9b-138">El valor $ es importante para identificar que se trata de una cuenta de equipo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="31c9b-139">Para configurar SQL creación de reflejos mientras se crea un grupo en el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="31c9b-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="31c9b-140">En la página **Definir el almacén de SQL**, haga clic en **Nuevo** junto al cuadro **Almacén de SQL**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="31c9b-141">En la página **Definir nuevo almacén de SQL**, especifique el almacén principal, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejo de SQL (el valor predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="31c9b-142">De vuelta en la página **Definir el almacén de SQL**, seleccione **Activar la creación de reflejo del almacén de SQL**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="31c9b-p110">En la página **Definir nuevo almacén de SQL**, especifique el almacén de SQL que se utilizará como reflejo, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto (el valor predeterminado es 5022) y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="31c9b-145">Si desea un testigo para este reflejo, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="31c9b-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="31c9b-146">a.</span><span class="sxs-lookup"><span data-stu-id="31c9b-146">a.</span></span> <span data-ttu-id="31c9b-147">Seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="31c9b-148">b.</span><span class="sxs-lookup"><span data-stu-id="31c9b-148">b.</span></span> <span data-ttu-id="31c9b-149">En la página **Definir el almacén de SQL**, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y especifique el almacén de SQL que se utilizará como testigo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="31c9b-150">c.</span><span class="sxs-lookup"><span data-stu-id="31c9b-150">c.</span></span> <span data-ttu-id="31c9b-151">Especifique el número de puerto (el valor predeterminado es 7022) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="31c9b-152">Una vez que haya terminado de definir el grupo de servidores front-end y todos los demás roles de la topología, use el Generador de topologías para publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="31c9b-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="31c9b-153">Cuando se publique la topología, si el grupo de servidores front-end que hospeda el almacén de administración central tiene habilitada la creación de reflejos SQL, verá una opción para crear bases de datos de almacén principal y SQL reflejo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="31c9b-154">Haga clic en **Configuración** y escriba la ruta de acceso que se utilizará como recurso compartido de archivos para la copia de seguridad del reflejo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="31c9b-p115">Haga clic en **Aceptar** y luego en **Siguiente** para crear las bases de datos y publicar la topología. Se implementarán los servidores de reflejo y de testigo (si se especificó).</span><span class="sxs-lookup"><span data-stu-id="31c9b-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="31c9b-157">Puede usar el Generador de topologías para editar las propiedades de un grupo de servidores ya existente para habilitar SQL creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="31c9b-158">Para agregar SQL creación de reflejo a un grupo de servidores front-end existente en el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="31c9b-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="31c9b-159">En el Generador de topologías, haga clic con el botón secundario en el grupo y, a continuación, haga clic **en Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="31c9b-160">Seleccione **Habilitar creación de reflejos del almacén de SQL** y, después, haga clic en **Nuevo**, junto a **Creación de reflejos del almacén de SQL**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="31c9b-161">Especifique el almacén de SQL que desea utilizar como reflejo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="31c9b-162">Seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="31c9b-163">Si desea configurar un testigo, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="31c9b-164">Especifique el almacén de SQL que desea utilizar como testigo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="31c9b-165">Seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 7022) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="31c9b-166">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-166">Click **OK**.</span></span>

9. <span data-ttu-id="31c9b-p116">Publique la topología. Al hacerlo, se le va a solicitar instalar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="31c9b-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="31c9b-169">Durante el proceso de publicación de topología, se le pedirá que defina una ruta de acceso de recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="31c9b-169">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="31c9b-170">Los SQL que participan en la creación de reflejos deben tener acceso de lectura y escritura a este recurso compartido de archivos para que se establezca el reflejo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-170">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="31c9b-171">A continuación, debe instalar la base de datos antes de continuar con el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="31c9b-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="31c9b-172">Debe tener en cuenta lo siguiente al configurar la creación de reflejos de SQL:</span><span class="sxs-lookup"><span data-stu-id="31c9b-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="31c9b-173">Si ya existe un extremo de creación de reflejos, se volverá a utilizar junto con los puertos definidos allí y pasará por alto los que especifique en la topología.</span><span class="sxs-lookup"><span data-stu-id="31c9b-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="31c9b-p118">Cualquier puerto que ya haya sido asignado a otras aplicaciones en el mismo servidor, incluidos aquellos para otras instancias de SQL, no deben utilizarse para las instancias de SQL instaladas a mano. Esto implica que si tiene más de una instancia de SQL instalada en el mismo servidor, no deben usar el mismo puerto para la creación de reflejos. Para obtener más información, consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="31c9b-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="31c9b-177">Especificar una dirección de red de servidor (creación de reflejo de la base de datos)</span><span class="sxs-lookup"><span data-stu-id="31c9b-177">Specify a Server Network Address (Database Mirroring)</span></span>](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [<span data-ttu-id="31c9b-178">El extremo de creación de reflejo de la base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31c9b-178">The Database Mirroring Endpoint (SQL Server)</span></span>](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="31c9b-179">Uso de cmdlets del Shell de administración de Skype Empresarial Server 2015 para configurar SQL creación de reflejos</span><span class="sxs-lookup"><span data-stu-id="31c9b-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="31c9b-180">La forma más sencilla de configurar la creación de reflejos es mediante el Generador de topologías, pero también puede hacerlo con cmdlets.</span><span class="sxs-lookup"><span data-stu-id="31c9b-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="31c9b-181">Abra una ventana del Shell de administración de Skype Empresarial Server 2015 y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="31c9b-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="31c9b-182">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="31c9b-182">For example:</span></span>

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="31c9b-183">Aparecerá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="31c9b-183">You will see the following:</span></span>

   <pre>
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
   </pre>

2. <span data-ttu-id="31c9b-184">Compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="31c9b-184">Verify the following:</span></span>

    - <span data-ttu-id="31c9b-185">El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server primario e04-ocs.los_a.lsipt.local\rtc.</span><span class="sxs-lookup"><span data-stu-id="31c9b-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="31c9b-186">El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server de reflejo K16-ocs.los_a.lsipt.local\rtc.</span><span class="sxs-lookup"><span data-stu-id="31c9b-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="31c9b-187">El puerto 7022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server testigo AB14-lct.los_a.lsipt.local\rtc.</span><span class="sxs-lookup"><span data-stu-id="31c9b-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="31c9b-188">Las cuentas que ejecutan los servidores SQL en todos los servidores de SQL principales y reflejados tienen permiso de lectura y escritura para el recurso compartido de archivos \\ E04-OCS\csdatabackup</span><span class="sxs-lookup"><span data-stu-id="31c9b-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="31c9b-p119">Asegúrese de que el proveedor de Instrumental de administración de Windows (WMI) se está ejecutando en todos estos servidores. El cmdlet utiliza dicho proveedor para encontrar la información de cuenta de los servicios de SQL Server que se ejecutan en el servidor principal, el reflejado y el testigo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="31c9b-191">Asegúrese de que la cuenta que ejecuta este cmdlet tiene permiso para crear las carpetas que contendrán los archivos de registro y los datos de todos los servidores reflejados.</span><span class="sxs-lookup"><span data-stu-id="31c9b-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="31c9b-p120">Es necesario que la cuenta de usuario en que se ejecuta la instancia de SQL tenga permisos de lectura y escritura en el recurso compartido de archivos. Si este recurso se encuentra en un servidor distinto y la instancia de SQL se ejecuta en una cuenta del sistema local, asegúrese de conceder los permisos del recurso compartido de archivos al servidor en que se hospeda la instancia de SQL.</span><span class="sxs-lookup"><span data-stu-id="31c9b-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="31c9b-194">Escriba A y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="31c9b-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="31c9b-195">Se configurará la creación de reflejos.</span><span class="sxs-lookup"><span data-stu-id="31c9b-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="31c9b-196">**Install-CsMirrorDatabase** instala el reflejo y configura la creación de reflejos para todas las bases de datos que están presentes en el almacén principal de SQL.</span><span class="sxs-lookup"><span data-stu-id="31c9b-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="31c9b-197">Si desea configurar la creación de reflejos solo para bases de datos específicas, puede usar la opción -DatabaseType o si desea configurar la creación de reflejo para todas las bases de datos excepto para algunas, puede usar la opción -ExcludeDatabaseList, junto con una lista separada por comas de nombres de base de datos para excluir.</span><span class="sxs-lookup"><span data-stu-id="31c9b-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="31c9b-198">Por ejemplo, si agrega la opción siguiente a **Install-CsMirrorDatabase**, se creará un reflejo de todas las bases de datos, excepto rtcab y rtcxds.</span><span class="sxs-lookup"><span data-stu-id="31c9b-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="31c9b-199">Por ejemplo, si agrega la opción siguiente a **Install-CsMirrorDatabase**, solo se creará un reflejo de las bases de datos rtcab, rtcshared y rtcxds.</span><span class="sxs-lookup"><span data-stu-id="31c9b-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="31c9b-200">Supresión o cambio de un reflejo de SQL</span><span class="sxs-lookup"><span data-stu-id="31c9b-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="31c9b-p122">Para quitar un reflejo de SQL de un grupo de servidores en el Generador de topologías, primero se debe quitar el reflejo en SQL Server utilizando un cmdlet. Después, podrá usar el Generador de topologías para quitar el reflejo de la topología. Para quitar el reflejo de SQL Server, use este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="31c9b-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="31c9b-204">Por ejemplo, para quitar reflejos y anular las bases de datos de las bases de datos del usuario, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="31c9b-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="31c9b-205">La  `-DropExistingDatabasesOnMirror` opción hace que las bases de datos afectadas se eliminen del reflejo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="31c9b-206">Después, para quitar el reflejo de la topología, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="31c9b-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="31c9b-207">En Topology Builder, haga clic con el botón secundario en el grupo y haga clic en **Modificar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="31c9b-208">Desactive **Habilitar creación de reflejos del almacén de SQL** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="31c9b-209">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="31c9b-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="31c9b-210">Supresión de un testigo de creación de reflejo</span><span class="sxs-lookup"><span data-stu-id="31c9b-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="31c9b-211">Use este procedimiento si necesita quitar el testigo de una configuración de creación de reflejo del servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="31c9b-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="31c9b-212">En Topology Builder, haga clic con el botón secundario en el grupo y haga clic en **Modificar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="31c9b-213">Desactive **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c9b-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="31c9b-214">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="31c9b-214">Publish the topology.</span></span>

    <span data-ttu-id="31c9b-215">Después de publicar la topología, el Generador de topologías verá un mensaje que incluye lo siguiente</span><span class="sxs-lookup"><span data-stu-id="31c9b-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="31c9b-216">Sin embargo, no siga ese paso y no escriba lo que  `Uninstall-CsMirrorDatabase` desinstale toda la configuración de creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="31c9b-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="31c9b-217">Para quitar solo el testigo de la configuración SQL Server, siga las instrucciones de Quitar el testigo de una sesión de creación de reflejo de base de datos [(SQL Server).](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server)</span><span class="sxs-lookup"><span data-stu-id="31c9b-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server).</span></span>