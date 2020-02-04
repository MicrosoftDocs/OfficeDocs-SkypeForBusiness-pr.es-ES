---
title: 'Lync Server 2013: Publicar la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5760315cc60aa53a40457423c2b5402896c2a90c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="deaae-102">Publicar la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="deaae-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="deaae-103">_**Última modificación del tema:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="deaae-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="deaae-104">Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="deaae-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="deaae-105">También es posible delegar los derechos y permisos de administrador adecuados.</span><span class="sxs-lookup"><span data-stu-id="deaae-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="deaae-106">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="deaae-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="deaae-107">Para otros cambios de configuración, solo es necesario pertenecer al grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="deaae-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="deaae-108">Después de definir la topología en el generador de topología, debe publicarla en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="deaae-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="deaae-109">El almacén central de administración proporciona un sólido almacenamiento schematized de los datos necesarios para definir, configurar, mantener, administrar, describir y utilizar una implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="deaae-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="deaae-110">También valida los datos para garantizar la coherencia de la configuración.</span><span class="sxs-lookup"><span data-stu-id="deaae-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="deaae-111">Todos los cambios realizados a esta configuración se producen en el almacén de administración central, excepto los problemas de "sin sincronizar".</span><span class="sxs-lookup"><span data-stu-id="deaae-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="deaae-112">Las copias de solo lectura de los datos se replican en todos los servidores de la topología, incluidos los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="deaae-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="deaae-113">SQL Server necesita un mínimo de 20 GB de espacio libre en el disco para publicar correctamente la topología inicial y crear el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="deaae-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="deaae-114">Solo para Enterprise Edition: para publicar la topología, el servidor back-end basado en SQL Server debe estar conectado y ser accesible con las excepciones de firewall en contexto.</span><span class="sxs-lookup"><span data-stu-id="deaae-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="deaae-115">Para obtener más información sobre cómo especificar excepciones de firewall, consulte <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding Firewall Requirements for SQL Server with Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="deaae-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="deaae-116">Para obtener más información sobre cómo configurar SQL Server, consulte <A href="lync-server-2013-configure-sql-server-for-lync-server.md">configurar SQL Server para Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="deaae-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="deaae-117">Para publicar una topología</span><span class="sxs-lookup"><span data-stu-id="deaae-117">To publish a topology</span></span>

1.  <span data-ttu-id="deaae-118">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="deaae-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="deaae-119">Seleccione para abrir la topología desde un archivo local.</span><span class="sxs-lookup"><span data-stu-id="deaae-119">Select to open the topology from a local file.</span></span> <span data-ttu-id="deaae-120">Si está en el equipo donde definió la topología, esta aparecerá en la ubicación en la que lo guardó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="deaae-120">If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps.</span></span> <span data-ttu-id="deaae-121">Normalmente, será la carpeta documentos del usuario que configuró la topología.</span><span class="sxs-lookup"><span data-stu-id="deaae-121">Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="deaae-122">Haga clic con el botón derecho en el nodo de **2013 de Lync Server** y, después, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="deaae-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="deaae-123">En la página **Publicar la topología**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="deaae-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="deaae-124">En la página **crear bases de datos** , seleccione las bases de datos que desea publicar.</span><span class="sxs-lookup"><span data-stu-id="deaae-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="deaae-125">Si no dispone de los derechos adecuados para crear las bases de datos, puede desactivar las casillas situadas junto a dichas bases de datos y, posteriormente, alguien con los derechos adecuados podrá crearlas.</span><span class="sxs-lookup"><span data-stu-id="deaae-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="deaae-126">Para obtener más información, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="deaae-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="deaae-127">Opcionalmente, haga clic en **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="deaae-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="deaae-128">Las opciones avanzadas de ubicación de los archivos de datos de SQL Server le permiten seleccionar entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="deaae-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="deaae-129">**Determinar automáticamente la ubicación del archivo de base** de datos: esta opción determinará el mejor rendimiento operativo en función de la configuración de disco de su servidor basado en SQL Server distribuyendo los archivos de registro y de datos a la mejor ubicación.</span><span class="sxs-lookup"><span data-stu-id="deaae-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="deaae-p107">**Usar los valores predeterminados de instancia de SQL Server**: esta opción coloca los archivos de datos y de registro en el servidor basado en SQL Server usando la configuración de la instancia. No usa la función operativa del servidor basado en SQL Server para saber cuáles son las mejores ubicaciones para los archivos de datos y de registro. El administrador de SQL Server suele mover los archivos de datos y de registro a ubicaciones que son adecuadas para los procedimientos de administración de la organización y del servidor basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="deaae-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="deaae-133">Haga clic en **Aceptar** y, luego, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="deaae-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="deaae-134">En la página **Seleccionar servidor de administración central** , seleccione un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="deaae-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="deaae-135">Opcionalmente, haga clic en **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="deaae-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="deaae-136">Las opciones avanzadas de ubicación del archivo de datos de SQL Server le permiten seleccionar entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="deaae-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="deaae-137">**Determinar automáticamente la ubicación del archivo de base** de datos: esta opción determinará el mejor rendimiento operativo en función de la configuración de disco de su servidor basado en SQL Server distribuyendo los archivos de registro y de datos a la mejor ubicación.</span><span class="sxs-lookup"><span data-stu-id="deaae-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="deaae-p109">**Usar los valores predeterminados de instancia de SQL Server**: esta opción coloca los archivos de datos y de registro en el servidor basado en SQL Server usando la configuración de la instancia. No usa la función operativa del servidor basado en SQL Server para saber cuáles son las mejores ubicaciones para los archivos de datos y de registro. El administrador de SQL Server suele mover los archivos de datos y de registro a ubicaciones que son adecuadas para los procedimientos de administración de la organización y del servidor basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="deaae-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="deaae-141">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="deaae-141">Click **OK**.</span></span>

9.  <span data-ttu-id="deaae-142">Haga clic en **Siguiente** para completar el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="deaae-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="deaae-143">Cuando el proceso de publicación haya finalizado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="deaae-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="deaae-144">Cuando la topología se ha publicado correctamente, puede empezar a instalar una réplica local del almacén de administración central en cada servidor que ejecute Lync Server 2013 en su topología.</span><span class="sxs-lookup"><span data-stu-id="deaae-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="deaae-145">Recomendamos empezar por el primer grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="deaae-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="deaae-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="deaae-146">See Also</span></span>


[<span data-ttu-id="deaae-147">Configurar servidores front-end y grupos de servidores front-end para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="deaae-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

