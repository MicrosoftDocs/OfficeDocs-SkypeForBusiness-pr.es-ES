---
title: 'Restauración de un servidor back-end de Enterprise Edition reflejado: principal'
description: 'Restaurar un servidor back-end de Enterprise Edition reflejado: principal.'
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
ms.openlocfilehash: 3f186bc304dccc363e5a7e0bf89a2276043e361e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542416"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="0bf45-103">Restauración de un servidor back-end de Enterprise Edition reflejado en Lync Server 2013-Primary</span><span class="sxs-lookup"><span data-stu-id="0bf45-103">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bf45-104">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="0bf45-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="0bf45-105">Si tiene un servidor back-end Enterprise Edition en una configuración reflejada y solo se produce un error en la base de datos principal, siga los procedimientos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="0bf45-105">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="0bf45-106">Si se produce un error en la base de datos principal y en el reflejo, consulte [restaurar un servidor back-end de Enterprise Edition en Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="0bf45-106">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="0bf45-107">Si solo se produce un error en el reflejo, consulte [restaurar un servidor back-end de Enterprise Edition en Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span><span class="sxs-lookup"><span data-stu-id="0bf45-107">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="0bf45-108">Si se produce un error en la base de datos que hospeda el almacén de administración central, vea [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="0bf45-108">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="0bf45-109">Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, vea [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="0bf45-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="0bf45-110">Le recomendamos que tome una copia de imagen del sistema antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="0bf45-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="0bf45-111">Puede usar esta imagen como un punto de reversión, en caso de que algo salga mal durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="0bf45-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="0bf45-112">Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="0bf45-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="0bf45-113">En este tema, la base de datos principal de ejemplo tendrá un nombre de dominio completo (FQDN) de BE1.contoso.com y la base de datos reflejada tendrá un FQDN de BE2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0bf45-113">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="0bf45-114">Para restaurar una base de datos principal del servidor back-end de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="0bf45-114">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="0bf45-115">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="0bf45-115">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="0bf45-116">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0bf45-117">Obligar a todas las bases de datos configuradas a conmutar por error al reflejo.</span><span class="sxs-lookup"><span data-stu-id="0bf45-117">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="0bf45-118">Para cada uno de los tipos de bases de datos que ha configurado en este servidor, escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0bf45-118">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="0bf45-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0bf45-119">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="0bf45-120">Si ha configurado su base de datos back-end para que use la creación de reflejos sincronizados con un testigo, la conmutación por error es automática.</span><span class="sxs-lookup"><span data-stu-id="0bf45-120">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="0bf45-121">Después de completar la conmutación por error, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bf45-121">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="0bf45-122">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-122">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="0bf45-123">Deshabilite la creación de reflejos en el servidor back-end: haga clic con el botón secundario en el grupo de **servidores front-end Enterprise Edition** y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-123">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="0bf45-124">En la pestaña **General** , en **asociaciones**, desactive la casilla **Habilitar la creación de reflejo del almacén de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="0bf45-124">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="0bf45-125">Haga esto para el archivado y la supervisión según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0bf45-125">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="0bf45-126">Después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-126">Then click **OK**.</span></span>
    
      - <span data-ttu-id="0bf45-127">Haga clic con el botón secundario en el nodo Lync Server 2013, haga clic en **topología**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="0bf45-128">Seleccione el back-end que sigue funcionando (BE2.contoso.com) para que sea el nuevo almacén de SQL.</span><span class="sxs-lookup"><span data-stu-id="0bf45-128">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="0bf45-129">Para ello, haga clic con el botón secundario en el grupo de **servidores front-end Enterprise Edition** y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-129">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="0bf45-130">En la pestaña **General** , en **asociaciones**, escriba el FQDN del back-end que funciona en el campo **almacén de SQL Server** (en nuestro ejemplo, BE2.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0bf45-130">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="0bf45-131">Haga clic con el botón secundario en el nodo Lync Server 2013, haga clic en **topología**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-131">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="0bf45-132">Reinicie los servicios para que cada servidor pueda leer la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="0bf45-132">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="0bf45-133">Desde un shell de administración de Lync Server, ejecute los cmdlets siguientes en cada servidor front-end que pertenezca a este grupo:</span><span class="sxs-lookup"><span data-stu-id="0bf45-133">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="0bf45-134">Desinstalación de la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="0bf45-134">Uninstall mirroring.</span></span> <span data-ttu-id="0bf45-135">Desde un shell de administración de Lync Server, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0bf45-135">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="0bf45-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0bf45-136">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="0bf45-137">Haga esto para todos los tipos de bases de datos en este servidor.</span><span class="sxs-lookup"><span data-stu-id="0bf45-137">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="0bf45-138">Cree un servidor nuevo o limpio que tenga el mismo FQDN (en este ejemplo, DB1.contoso.com) que el equipo con errores, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="0bf45-138">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="0bf45-139">Este servidor funcionará como el nuevo reflejo.</span><span class="sxs-lookup"><span data-stu-id="0bf45-139">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="0bf45-140">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="0bf45-140">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="0bf45-141">Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los nombres de instancia iguales que antes del error.</span><span class="sxs-lookup"><span data-stu-id="0bf45-141">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="0bf45-142">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="0bf45-142">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="0bf45-143">Use el generador de topologías para instalar la BD de reflejo.</span><span class="sxs-lookup"><span data-stu-id="0bf45-143">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="0bf45-144">Realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0bf45-144">Perform the following steps:</span></span>
    
      - <span data-ttu-id="0bf45-145">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="0bf45-146">Habilite la creación de reflejos en el servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="0bf45-146">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="0bf45-147">Para ello, haga clic con el botón secundario en el grupo de **servidores front-end Enterprise Edition** y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-147">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="0bf45-148">En la pestaña **General** , en **asociaciones**, active la casilla **Habilitar la creación de reflejo del almacén de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="0bf45-148">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="0bf45-149">También puede hacerlo para archivado y supervisión, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="0bf45-149">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="0bf45-150">A continuación, en el campo **reflejo del almacén de SQL Server** , escriba el FQDN del nuevo servidor (n este ejemplo, BE1.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0bf45-150">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="0bf45-151">Después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-151">Then click **OK**.</span></span>
    
      - <span data-ttu-id="0bf45-152">Haga clic con el botón secundario en el nodo Lync Server 2013, haga clic en **topología**y, a continuación, haga clic en **instalar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-152">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="0bf45-153">Siga el Asistente para **instalar base de datos** .</span><span class="sxs-lookup"><span data-stu-id="0bf45-153">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="0bf45-154">En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.</span><span class="sxs-lookup"><span data-stu-id="0bf45-154">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="0bf45-155">Siga el asistente hasta que llegue al mensaje, **cree una base de datos reflejada**.</span><span class="sxs-lookup"><span data-stu-id="0bf45-155">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="0bf45-156">Seleccione la base de datos que desea instalar y complete este proceso.</span><span class="sxs-lookup"><span data-stu-id="0bf45-156">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

