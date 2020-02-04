---
title: 'Restaurar un servidor de servicios de fondo de la edición empresarial duplicada: principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07546b59839631cbd558e91e3e617fefd1c6e362
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="ed551-102">Restaurar un servidor de servicios de fondo de la edición empresarial duplicada en Lync Server 2013-principal</span><span class="sxs-lookup"><span data-stu-id="ed551-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed551-103">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="ed551-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="ed551-104">Si tiene un servidor de servicios de fondo Enterprise Edition en una configuración reflejada y solo se produce un error en la base de datos principal, siga los procedimientos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="ed551-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="ed551-105">Si la base de datos principal y el reflejo fallan, consulte [restaurar un servidor de servicios de fondo de la edición empresarial en Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="ed551-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="ed551-106">Si solo se produce un error en el reflejo, vea [restaurar un servidor de servicios de fondo empresarial duplicado en Lync server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span><span class="sxs-lookup"><span data-stu-id="ed551-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="ed551-107">Si se produce un error en la base de datos que hospeda el almacén de administración central, consulte [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="ed551-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="ed551-108">Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, consulte [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="ed551-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="ed551-109">Le recomendamos que tome una copia de la imagen del sistema antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="ed551-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="ed551-110">Puede usar esta imagen como punto de reversión, en caso de que algo falle durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="ed551-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="ed551-111">Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="ed551-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="ed551-112">En este tema, la base de datos principal de ejemplo tendrá un nombre de dominio completo (FQDN) de BE1.contoso.com y la base de datos reflejada tendrá un FQDN de BE2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ed551-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="ed551-113">Para restaurar una base de datos principal del servidor de servicios de fondo de la edición Enterprise</span><span class="sxs-lookup"><span data-stu-id="ed551-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="ed551-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="ed551-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="ed551-115">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ed551-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ed551-116">Fuerce la conmutación por error de todas las bases de datos configuradas en el reflejo.</span><span class="sxs-lookup"><span data-stu-id="ed551-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="ed551-117">Para cada uno de los tipos de base de datos que ha configurado en este servidor, escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ed551-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="ed551-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ed551-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="ed551-119">Si ha configurado la base de datos back-end para usar el reflejo sincronizado con un testigo, la conmutación por error es automática.</span><span class="sxs-lookup"><span data-stu-id="ed551-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="ed551-120">Después de completar la conmutación por error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed551-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="ed551-121">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ed551-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="ed551-122">Deshabilite el reflejo en el servidor back-end: haga clic con el botón derecho en la agrupación de **servidores front-end de Enterprise Edition** y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ed551-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="ed551-123">En la pestaña **General** , en **asociaciones**, desactive la casilla habilitar el reflejo de la **tienda de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="ed551-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="ed551-124">Haga esto para archivar y supervisar según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ed551-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="ed551-125">A continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ed551-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="ed551-126">Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **topología**y, a continuación, en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="ed551-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="ed551-127">Seleccione el back-end en funcionamiento continuado (BE2.contoso.com) para que sea la nueva tienda SQL.</span><span class="sxs-lookup"><span data-stu-id="ed551-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="ed551-128">Para ello, haga clic con el botón secundario en el grupo de **servidores Enterprise Edition front end** y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ed551-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="ed551-129">En la pestaña **General** , en **asociaciones**, escriba el FQDN del back-end en el campo del **almacén de SQL Server** (en nuestro ejemplo, BE2.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ed551-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="ed551-130">Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **topología**y, a continuación, en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="ed551-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="ed551-131">Reinicie servicios para que cada servidor pueda leer la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="ed551-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="ed551-132">Desde un shell de administración de Lync Server, ejecute los siguientes cmdlets en cada servidor front-end que pertenece a este grupo:</span><span class="sxs-lookup"><span data-stu-id="ed551-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="ed551-133">Desinstalar reflejo.</span><span class="sxs-lookup"><span data-stu-id="ed551-133">Uninstall mirroring.</span></span> <span data-ttu-id="ed551-134">Desde un shell de administración de Lync Server, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ed551-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="ed551-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ed551-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="ed551-136">Haga esto para todos los tipos de base de datos en este servidor.</span><span class="sxs-lookup"><span data-stu-id="ed551-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="ed551-137">Cree un servidor limpio o nuevo que tenga el mismo FQDN (en este ejemplo, DB1.contoso.com) como el equipo que ha fallado, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="ed551-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="ed551-138">Este servidor funcionará como el nuevo reflejo.</span><span class="sxs-lookup"><span data-stu-id="ed551-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="ed551-139">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="ed551-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="ed551-140">Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los mismos nombres de instancia que antes del error.</span><span class="sxs-lookup"><span data-stu-id="ed551-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="ed551-141">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="ed551-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="ed551-142">Use el generador de topología para instalar la BD de reflejo.</span><span class="sxs-lookup"><span data-stu-id="ed551-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="ed551-143">Realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="ed551-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="ed551-144">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ed551-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="ed551-145">Habilitar el reflejo en el servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="ed551-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="ed551-146">Para ello, haga clic con el botón secundario en el grupo de **servidores Enterprise Edition front end** y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ed551-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="ed551-147">En la pestaña **General** , en **asociaciones**, seleccione la casilla de verificación Habilitar el reflejo de la **tienda de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="ed551-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="ed551-148">También puede hacer esto para archivar y supervisar, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ed551-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="ed551-149">A continuación, en el campo **reflejar el almacén de SQL Server** , escriba el nombre completo del servidor nuevo (n este ejemplo, BE1.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ed551-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="ed551-150">A continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ed551-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="ed551-151">Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **topología**y, a continuación, en **instalar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="ed551-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="ed551-152">Siga el Asistente para la **instalación de bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="ed551-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="ed551-153">En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.</span><span class="sxs-lookup"><span data-stu-id="ed551-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="ed551-154">Siga el asistente hasta que llegue a la pregunta, **cree una base de datos de reflejo**.</span><span class="sxs-lookup"><span data-stu-id="ed551-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="ed551-155">Seleccione la base de datos que desee instalar y complete este proceso.</span><span class="sxs-lookup"><span data-stu-id="ed551-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

