---
title: Implementación de la creación de reflejos de SQL para alta disponibilidad de servidores back-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577d6bb312ae2b31f96fed5f3e5b02e84844adf6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="25139-102">Implementación de la creación de reflejos de SQL para la alta disponibilidad del servidor back-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25139-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25139-103">_**Última modificación del tema:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="25139-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="25139-104">Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar un mínimo de SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="25139-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="25139-105">Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo.</span><span class="sxs-lookup"><span data-stu-id="25139-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="25139-106">Para obtener más información [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921), consulte.</span><span class="sxs-lookup"><span data-stu-id="25139-106">For details, see [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="25139-107">En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25139-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="25139-108">La versión del servidor principal de SQL Server debe admitir la creación de reflejo de SQL.</span><span class="sxs-lookup"><span data-stu-id="25139-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="25139-109">El servidor principal, reflejo y testigo (si se implementan) deben tener la misma versión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25139-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="25139-p102">El servidor principal y el reflejo deben tener la misma edición de SQL Server. El testigo puede tener una edición diferente.</span><span class="sxs-lookup"><span data-stu-id="25139-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="25139-112">Para conocer los procedimientos recomendados de SQL en relación con las versiones de SQL compatibles con un rol de testigo, consulte "testigo de creación de reflejo de [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345)la base de datos" en MSDN Library, en.</span><span class="sxs-lookup"><span data-stu-id="25139-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="25139-113">El generador de topologías se usa para implementar la creación de reflejos de SQL.</span><span class="sxs-lookup"><span data-stu-id="25139-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="25139-114">Seleccione una opción en el generador de topologías para reflejar las bases de datos y el generador de topologías configura la creación de reflejos (incluida la configuración de un testigo, si lo desea) cuando publique la topología.</span><span class="sxs-lookup"><span data-stu-id="25139-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="25139-115">Tenga en cuenta que puede configurar o quitar el testigo al mismo tiempo que configura o quita el reflejo.</span><span class="sxs-lookup"><span data-stu-id="25139-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="25139-116">No hay ningún comando independiente para implementar o quitar un solo testigo.</span><span class="sxs-lookup"><span data-stu-id="25139-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="25139-117">Para configurar la creación de reflejo de servidor, es necesario que primero configure los permisos de base de datos SQL correctamente.</span><span class="sxs-lookup"><span data-stu-id="25139-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="25139-118">Para obtener más información, consulte "configurar cuentas de inicio de sesión para la creación de reflejo de la base de datos o [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454)grupos de disponibilidad AlwaysOn (SQL Server)" en.</span><span class="sxs-lookup"><span data-stu-id="25139-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="25139-p105">Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa**. Esto significa que deberá controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se deben crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Le recomendamos que determine el crecimiento estimado del registro de transacciones que se necesitará para la carga de trabajo de su implementación de Lync, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:</span><span class="sxs-lookup"><span data-stu-id="25139-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="25139-123">Modelos de recuperación de bases de datos: "modelos de recuperación (SQL Server)" en[https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="25139-123">Database recovery models: "Recovery Models (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="25139-124">Información general sobre copia de seguridad: "información general de copia de seguridad (SQL Server)" en[https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="25139-124">Backup overview: "Backup Overview (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="25139-125">Registro de transacciones de copia de seguridad: "copia de seguridad de un registro de transacciones (SQL Server)" en[https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="25139-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="25139-126">Con el reflejo de SQL, puede configurar la topología de creación de reflejos al crear los grupos o después de que ya se hayan creado los grupos.</span><span class="sxs-lookup"><span data-stu-id="25139-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="25139-127">Usar el generador de topologías o los cmdlets para configurar y quitar la creación de reflejos de SQL solo se admite cuando los servidores principal, reflejado y testigo (si lo desea) pertenecen al mismo dominio.</span><span class="sxs-lookup"><span data-stu-id="25139-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="25139-128">Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación sobre SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25139-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="25139-129">Siempre que haga algún cambio en las conexiones entre reflejos de la base de datos back-end, deberá reiniciar todos los servidores front-end del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="25139-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="25139-130">Para realizar un cambio en la creación de reflejos (como cambiar la ubicación de un reflejo), debe usar el generador de topologías para realizar estos tres pasos:</span><span class="sxs-lookup"><span data-stu-id="25139-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="25139-131">Quitar reflejos del servidor reflejado antiguo.</span><span class="sxs-lookup"><span data-stu-id="25139-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="25139-132">Agregar reflejos al servidor reflejado nuevo.</span><span class="sxs-lookup"><span data-stu-id="25139-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="25139-133">Publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="25139-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="25139-134">Se debe crear un recurso compartido de archivos para que se escriban los archivos reflejados y el servicio en el que se ejecutan SQL Server y SQL Agent necesita acceso de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="25139-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="25139-135">Si el servicio de SQL Server se está ejecutando en el contexto del servicio de red, &lt;puede&gt; agregar &lt;el&gt;&#92;de dominio SQLSERVERNAME $ de los servidores SQL principal y de reflejo a los permisos de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="25139-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="25139-136">La $ es importante para identificar que se trata de una cuenta de equipo.</span><span class="sxs-lookup"><span data-stu-id="25139-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="25139-137">Para configurar la creación de reflejos de SQL al crear un grupo de servidores en el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="25139-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="25139-138">En la página **Definir el almacén de SQL**, haga clic en **Nuevo** junto al cuadro **Almacén de SQL**.</span><span class="sxs-lookup"><span data-stu-id="25139-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="25139-139">En la página **Definir nuevo almacén de SQL**, especifique el almacén principal, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejo de SQL (el valor predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25139-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="25139-140">De vuelta en la página **Definir el almacén de SQL**, seleccione **Activar la creación de reflejo del almacén de SQL**.</span><span class="sxs-lookup"><span data-stu-id="25139-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="25139-p108">En la página **Definir nuevo almacén de SQL**, especifique el almacén de SQL que se utilizará como reflejo, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto (el valor predeterminado es 5022) y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25139-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="25139-143">Si desea un testigo para este reflejo, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25139-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="25139-144">Seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática**.</span><span class="sxs-lookup"><span data-stu-id="25139-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="25139-145">En la página **Definir el almacén de SQL**, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y especifique el almacén de SQL que se utilizará como testigo.</span><span class="sxs-lookup"><span data-stu-id="25139-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="25139-146">Especifique el número de puerto (el valor predeterminado es 7022) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25139-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="25139-147">Una vez que haya terminado de definir el grupo de servidores front-end y todos los demás roles de la topología, use el generador de topologías para publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="25139-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="25139-148">Una vez publicada la topología, si el grupo de servidores front-end que hospeda el almacén de administración central tiene habilitada la creación de reflejo de SQL, verá una opción para crear las bases de datos de SQL Store principal y reflejada.</span><span class="sxs-lookup"><span data-stu-id="25139-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="25139-149">Haga clic en **Configuración** y escriba la ruta de acceso que se utilizará como recurso compartido de archivos para la copia de seguridad del reflejo.</span><span class="sxs-lookup"><span data-stu-id="25139-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="25139-p110">Haga clic en \*\*Aceptar \*\* y luego en **Siguiente** para crear las bases de datos y publicar la topología. Se implementarán los servidores de reflejo y de testigo (si se especificó).</span><span class="sxs-lookup"><span data-stu-id="25139-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="25139-152">Puede usar el generador de topologías para editar las propiedades de un grupo ya existente para habilitar la creación de reflejos de SQL.</span><span class="sxs-lookup"><span data-stu-id="25139-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="25139-153">Para agregar la creación de reflejos de SQL a un grupo de servidores front-end existente en el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="25139-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="25139-154">En el generador de topologías, haga clic con el botón secundario en el grupo y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="25139-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="25139-155">Seleccione **Habilitar creación de reflejos del almacén de SQL** y, después, haga clic en **Nuevo**, junto a **Creación de reflejos del almacén de SQL**.</span><span class="sxs-lookup"><span data-stu-id="25139-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="25139-156">Especifique el almacén de SQL que desea utilizar como reflejo.</span><span class="sxs-lookup"><span data-stu-id="25139-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="25139-157">Seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25139-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="25139-158">Si desea configurar un testigo, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="25139-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="25139-159">Especifique el almacén de SQL que desea utilizar como testigo.</span><span class="sxs-lookup"><span data-stu-id="25139-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="25139-160">Seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 7022) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25139-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="25139-161">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25139-161">Click **OK**.</span></span>

9.  <span data-ttu-id="25139-p111">Publique la topología. Al hacerlo, se le va a solicitar instalar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="25139-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="25139-164">Durante el proceso de publicación de la topología, se le pedirá que defina una ruta de acceso al recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="25139-164">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="25139-165">Los servidores SQL que participan en la creación de reflejos deben tener acceso de lectura y escritura a este recurso compartido de archivos para que se pueda establecer el reflejo.</span><span class="sxs-lookup"><span data-stu-id="25139-165">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="25139-166">A continuación, debe instalar la base de datos antes de continuar con el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="25139-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="25139-167">Debe tener en cuenta lo siguiente al configurar la creación de reflejos de SQL:</span><span class="sxs-lookup"><span data-stu-id="25139-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="25139-168">Si ya existe un extremo de creación de reflejos, se volverá a utilizar junto con los puertos definidos allí y pasará por alto los que especifique en la topología.</span><span class="sxs-lookup"><span data-stu-id="25139-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="25139-p113">Cualquier puerto que ya haya sido asignado a otras aplicaciones en el mismo servidor, incluidos aquellos para otras instancias de SQL, no deben utilizarse para las instancias de SQL instaladas a mano. Esto implica que si tiene más de una instancia de SQL instalada en el mismo servidor, no deben usar el mismo puerto para la creación de reflejos. Para obtener más información, consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="25139-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="25139-172">"Especificar una dirección de red de servidor (creación de reflejo de la base de datos)" en MSDN Library, en[https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="25139-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="25139-173">"El punto de conexión de creación de reflejo de la base de datos (SQL Server)" en[https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="25139-173">"The Database Mirroring Endpoint (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="25139-174">Uso de cmdlets del shell de administración de Lync Server para configurar la creación de reflejos de SQL</span><span class="sxs-lookup"><span data-stu-id="25139-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="25139-175">La forma más sencilla de configurar la creación de reflejos es con el generador de topologías, pero también puede hacerlo con los cmdlets de.</span><span class="sxs-lookup"><span data-stu-id="25139-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="25139-176">Abra una ventana del shell de administración de Lync Server y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="25139-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="25139-177">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="25139-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="25139-178">Aparecerá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25139-178">You will see the following:</span></span>
    
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

2.  <span data-ttu-id="25139-179">Compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25139-179">Verify the following:</span></span>
    
      - <span data-ttu-id="25139-180">El puerto 5022 es accesible a través del firewall si firewall de Windows está habilitado en la primario E04 de\_SQL Server principal. RTC\\local. OCS. local.</span><span class="sxs-lookup"><span data-stu-id="25139-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="25139-181">El puerto 5022 es accesible a través del firewall si firewall de Windows está habilitado en la copia de\_seguridad de SQL Server reflejo K16\\. OCS. RTC local.</span><span class="sxs-lookup"><span data-stu-id="25139-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="25139-182">El puerto 7022 es accesible a través del firewall si firewall de Windows está habilitado en el testigo SQL\_Server testigo ab14. RTC local\\. OCS. local.</span><span class="sxs-lookup"><span data-stu-id="25139-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="25139-183">Las cuentas que ejecutan los servidores SQL en todos los servidores SQL Server principal y de reflejo tienen permiso de \\ \\lectura y escritura\\en el recurso compartido de archivos E04-OCS csdatabackup</span><span class="sxs-lookup"><span data-stu-id="25139-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="25139-p114">Asegúrese de que el proveedor de Instrumental de administración de Windows (WMI) se está ejecutando en todos estos servidores. El cmdlet utiliza dicho proveedor para encontrar la información de cuenta de los servicios de SQL Server que se ejecutan en el servidor principal, el reflejado y el testigo.</span><span class="sxs-lookup"><span data-stu-id="25139-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="25139-186">Asegúrese de que la cuenta que ejecuta este cmdlet tiene permiso para crear las carpetas que contendrán los archivos de registro y los datos de todos los servidores reflejados.</span><span class="sxs-lookup"><span data-stu-id="25139-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="25139-p115">Es necesario que la cuenta de usuario en que se ejecuta la instancia de SQL tenga permisos de lectura y escritura en el recurso compartido de archivos. Si este recurso se encuentra en un servidor distinto y la instancia de SQL se ejecuta en una cuenta del sistema local, asegúrese de conceder los permisos del recurso compartido de archivos al servidor en que se hospeda la instancia de SQL.</span><span class="sxs-lookup"><span data-stu-id="25139-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="25139-189">Escriba A y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="25139-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="25139-190">Se configurará la creación de reflejos.</span><span class="sxs-lookup"><span data-stu-id="25139-190">The mirroring will be configured.</span></span>

<span data-ttu-id="25139-191">**Install-CsMirrorDatabase** instala el reflejo y configura la creación de reflejos para todas las bases de datos que están presentes en el almacén principal de SQL.</span><span class="sxs-lookup"><span data-stu-id="25139-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="25139-192">Si desea configurar la creación de reflejos solo para bases de datos específicas, puede utilizar la opción de –DatabaseType; si desea configurar la creación de reflejos para todas las bases de datos excepto unas pocas, puede utilizar la opción –ExcludeDatabaseList, junto con una lista separada por comas que contengan los nombres de las bases de datos que se deban excluir.</span><span class="sxs-lookup"><span data-stu-id="25139-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="25139-193">Por ejemplo, si agrega la opción siguiente a **Install-CsMirrorDatabase**, se creará un reflejo de todas las bases de datos, excepto rtcab y rtcxds.</span><span class="sxs-lookup"><span data-stu-id="25139-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="25139-194">Por ejemplo, si agrega la opción siguiente a **Install-CsMirrorDatabase**, solo se creará un reflejo de las bases de datos rtcab, rtcshared y rtcxds.</span><span class="sxs-lookup"><span data-stu-id="25139-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="25139-195">Supresión o cambio de un reflejo de SQL</span><span class="sxs-lookup"><span data-stu-id="25139-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="25139-p117">Para quitar un reflejo de SQL de un grupo de servidores en el Generador de topologías, primero se debe quitar el reflejo en SQL Server utilizando un cmdlet. Después, podrá usar el Generador de topologías para quitar el reflejo de la topología. Para quitar el reflejo de SQL Server, use este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="25139-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="25139-199">Por ejemplo, para quitar reflejos y anular las bases de datos de las bases de datos del usuario, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25139-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="25139-200">La `-DropExistingDatabasesOnMirror` opción hace que las bases de datos afectadas se eliminen del reflejo.</span><span class="sxs-lookup"><span data-stu-id="25139-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="25139-201">Después, para quitar el reflejo de la topología, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25139-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="25139-202">En Topology Builder, haga clic con el botón secundario en el grupo y haga clic en **Modificar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="25139-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="25139-203">Desactive **Habilitar creación de reflejos del almacén de SQL** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25139-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="25139-204">Publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="25139-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="25139-205">Supresión de un testigo de creación de reflejo</span><span class="sxs-lookup"><span data-stu-id="25139-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="25139-206">Use este procedimiento si necesita quitar el testigo de una configuración de creación de reflejo del servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="25139-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="25139-207">En Topology Builder, haga clic con el botón secundario en el grupo y haga clic en **Modificar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="25139-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="25139-208">Desactive **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25139-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="25139-209">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="25139-209">Publish the topology.</span></span>
    
    <span data-ttu-id="25139-210">Después de publicar la topología, el generador de topologías verá un mensaje que incluirá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25139-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="25139-211">Sin embargo, no siga este paso y no escriba `Uninstall-CsMirrorDatabase` como eso que desinstalaría toda la configuración de creación de reflejos.</span><span class="sxs-lookup"><span data-stu-id="25139-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="25139-212">Para quitar solo el testigo de la configuración de SQL Server, siga las instrucciones que se indican en "quitar el testigo de una sesión de creación de reflejo de [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456)la base de datos (SQL Server)" en.</span><span class="sxs-lookup"><span data-stu-id="25139-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

