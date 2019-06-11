---
title: 'Lync Server 2013: Configurar el DNS para el equilibrio de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e370d3b66e82b02bd5668fc1c9cab4ee41da759
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="ab91d-102">Configurar el DNS para el equilibrio de carga en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab91d-102">Configure DNS for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab91d-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ab91d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ab91d-104">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o en miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab91d-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="ab91d-105">El equilibrio de carga del sistema de nombres de dominio (DNS) equilibra el tráfico de red que es exclusivo de Lync Server 2013, como el tráfico SIP y el tráfico de medios.</span><span class="sxs-lookup"><span data-stu-id="ab91d-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="ab91d-106">El equilibrio de carga de DNS es compatible con los grupos de aplicaciones front-end, los conjuntos de extremos, los grupos de directores y los conjuntos de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="ab91d-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="ab91d-107">Un grupo configurado para usar el equilibrio de carga de DNS debe tener dos nombres de dominio completos (FQDN) definidos: el FQDN de la agrupación normal que usa el equilibrio de carga de DNS (por ejemplo, pool1.contoso.com) y que se resuelve en la IP física de los servidores del grupo y otro FQDN para los servicios web del grupo (por ejemplo, web1.contoso.net), que se resuelve en la dirección IP virtual del grupo.</span><span class="sxs-lookup"><span data-stu-id="ab91d-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="ab91d-108">Para obtener más información sobre el equilibrio de carga de DNS, consulte [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="ab91d-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab91d-109">El equilibrio de carga de hardware sigue siendo necesario para el tráfico HTTPS del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="ab91d-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="ab91d-110">Para poder usar el equilibrio de carga de DNS, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab91d-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="ab91d-111">Invalide el FQDN del grupo de servicios Web interno.</span><span class="sxs-lookup"><span data-stu-id="ab91d-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="ab91d-112">Si decide invalidar los servicios Web internos con un FQDN definido por el usuario, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="ab91d-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="ab91d-113">Cree registros de host DNS para resolver el FQDN del grupo a las direcciones IP de todos los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="ab91d-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="ab91d-114">Habilite la aleatoriedad de la dirección IP o, para DNS de Windows Server, habilite la operación por turnos.</span><span class="sxs-lookup"><span data-stu-id="ab91d-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab91d-115">La operación por turnos debe estar habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ab91d-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="ab91d-116">Para invalidar el FQDN de los servicios Web internos</span><span class="sxs-lookup"><span data-stu-id="ab91d-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="ab91d-117">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ab91d-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ab91d-118">En el árbol de la consola, expanda el nodo agrupaciones front-end de Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="ab91d-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="ab91d-119">Haga clic con el botón secundario en el grupo, haga clic en **Editar propiedades**y, a continuación, en **servicios web**.</span><span class="sxs-lookup"><span data-stu-id="ab91d-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="ab91d-120">Debajo de **servicios Web internos**, seleccione la casilla invalidar **FQDN** .</span><span class="sxs-lookup"><span data-stu-id="ab91d-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="ab91d-121">Escriba el FQDN del grupo de servidores que se resuelve en las direcciones IP físicas de los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="ab91d-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="ab91d-122">Debajo de **servicios web externos**, escriba el FQDN del grupo externo que se resuelve en las direcciones IP virtuales del grupo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab91d-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="ab91d-123">En el árbol de consola, haga clic en **Lync Server 2013**y, a continuación, en el panel **acciones** , haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="ab91d-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="ab91d-124">Para crear registros de host DNS (A) para todos los servidores de grupo internos</span><span class="sxs-lookup"><span data-stu-id="ab91d-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="ab91d-125">Haga clic en **Inicio**, seleccione **todos los programas**, **herramientas administrativas**y, a continuación, haga clic en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="ab91d-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="ab91d-126">En el **Administrador de DNS**, haga clic en el servidor DNS que administra los registros para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="ab91d-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="ab91d-127">Haga clic en **zonas de búsqueda directa** para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="ab91d-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="ab91d-128">Haga clic con el botón secundario en el dominio DNS al que tiene que agregar registros y, a continuación, haga clic en **nuevo host (a o aaaa)**.</span><span class="sxs-lookup"><span data-stu-id="ab91d-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="ab91d-129">En el cuadro **Nombre**, escriba el nombre del registro de host (el nombre de dominio se anexará automáticamente).</span><span class="sxs-lookup"><span data-stu-id="ab91d-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="ab91d-130">En el cuadro Dirección IP, escriba la dirección IP del servidor frontal individual y, después, seleccione **crear registro de puntero (PTR) asociado** o **permitir que cualquier usuario autenticado actualice los registros DNS con el mismo nombre de propietario**, si procede.</span><span class="sxs-lookup"><span data-stu-id="ab91d-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="ab91d-131">Siga creando registros para todos los servidores front-end de miembros que participarán en el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="ab91d-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="ab91d-132">Por ejemplo, si tiene un grupo denominado pool1.contoso.com y tres servidores front-end, deberá crear las siguientes entradas DNS:</span><span class="sxs-lookup"><span data-stu-id="ab91d-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ab91d-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="ab91d-133">FQDN</span></span></th>
    <th><span data-ttu-id="ab91d-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab91d-134">Type</span></span></th>
    <th><span data-ttu-id="ab91d-135">Datos</span><span class="sxs-lookup"><span data-stu-id="ab91d-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ab91d-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab91d-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="ab91d-137">Host (A)</span><span class="sxs-lookup"><span data-stu-id="ab91d-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="ab91d-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="ab91d-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ab91d-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab91d-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="ab91d-140">Host (A)</span><span class="sxs-lookup"><span data-stu-id="ab91d-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="ab91d-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="ab91d-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ab91d-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab91d-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="ab91d-143">Host (A)</span><span class="sxs-lookup"><span data-stu-id="ab91d-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="ab91d-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="ab91d-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="ab91d-145">Para obtener información detallada sobre la creación de registros de host DNS (A), vea [configurar registros de host DNS para Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span><span class="sxs-lookup"><span data-stu-id="ab91d-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="ab91d-146">Para habilitar la operación por turnos en Windows Server</span><span class="sxs-lookup"><span data-stu-id="ab91d-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="ab91d-147">Haga clic en **Inicio**, seleccione **todos los programas**, **herramientas administrativas**y, a continuación, haga clic en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="ab91d-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="ab91d-148">Expanda **DNS**, haga clic con el botón secundario en el servidor DNS que desea configurar y, después, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ab91d-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="ab91d-149">Haga clic en la pestaña **avanzadas** , seleccione **Habilitar** ordenación por turnos y **Habilitar ordenación de máscaras de máscara**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab91d-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="ab91d-150">![Cuadro de diálogo Round Robin de DNS] (images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Cuadro de diálogo Round Robin de DNS")</span><span class="sxs-lookup"><span data-stu-id="ab91d-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab91d-151">Esta característica debe estar habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ab91d-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab91d-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab91d-152">See Also</span></span>


[<span data-ttu-id="ab91d-153">Equilibrio de carga de DNS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab91d-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

