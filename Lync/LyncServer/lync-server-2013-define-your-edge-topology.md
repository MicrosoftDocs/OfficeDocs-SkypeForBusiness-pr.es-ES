---
title: 'Lync Server 2013: Definir la topología perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8364d2167b719e020ecebc3808c2ca850d14bc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="960fc-102">Definir la topología perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="960fc-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="960fc-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="960fc-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="960fc-104">Debe usar topología Builder para crear su topología y debe configurar al menos un grupo de servidores front-end interno o un servidor Standard Edition para poder implementar el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="960fc-105">Use el siguiente procedimiento para definir la topología de borde para un único servidor perimetral y, a continuación, use los procedimientos de [publicar su topología en Lync server 2013](lync-server-2013-publish-your-topology.md) y [exportar su topología de Lync Server 2013 y copiarla en medios externos para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) . para publicar la topología y ponerla a disposición de su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="960fc-p102">La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga de DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="960fc-108">Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="960fc-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="960fc-109">También puede conceder derechos y permisos de administrador necesarios para agregar roles de servidor a una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="960fc-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="960fc-110">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="960fc-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="960fc-111">Para otros cambios de configuración, solo es necesario pertenecer al grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="960fc-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="960fc-112">Si definió la topología de borde cuando definió y publicó su topología interna, y no se necesitan cambios en la topología perimetral que definió anteriormente, no es necesario que la defina y la publique de nuevo.</span><span class="sxs-lookup"><span data-stu-id="960fc-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="960fc-113">Use el siguiente procedimiento solo si necesita realizar cambios en la topología de borde.</span><span class="sxs-lookup"><span data-stu-id="960fc-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="960fc-114">Debe hacer que la topología previamente definida y publicada esté disponible para los servidores perimetrales, que puede hacer con el procedimiento de [exportar su topología de Lync Server 2013 y copiarla en medios externos para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="960fc-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="960fc-115">No se puede ejecutar el generador de topologías desde un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="960fc-116">Debe ejecutarla desde el servidor front-end o los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="960fc-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="960fc-117">El proceso para definir la topología del servidor perimetral se realiza en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="960fc-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="960fc-118">A continuación, se muestran los tres tipos principales de topologías de servidores perimetrales que se planean y se configuran:</span><span class="sxs-lookup"><span data-stu-id="960fc-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="960fc-119">Para definir la topología de un único servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="960fc-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="960fc-120">Para definir la topología de un grupo de servidores perimetrales de carga equilibrada</span><span class="sxs-lookup"><span data-stu-id="960fc-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="960fc-121">Para definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="960fc-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="960fc-122">Para definir la topología de un único servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="960fc-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="960fc-123">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="960fc-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="960fc-124">En el árbol de consola, expanda el sitio en el que desea implementar un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="960fc-125">Haga clic con \*\*\*\* el botón secundario en agrupaciones perimetrales y luego haga clic en **nuevo borde**.</span><span class="sxs-lookup"><span data-stu-id="960fc-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="960fc-126">En **definir el nuevo grupo de límites**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="960fc-127">En **definir el FQDN del grupo perimetral**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-128">En **FQDN del grupo**, escriba el nombre de dominio completo (FQDN) de la interfaz interna para el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="960fc-129">El nombre que especifique debe ser idéntico al nombre de equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="960fc-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="960fc-130">De forma predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre corto, no un FQDN.</span><span class="sxs-lookup"><span data-stu-id="960fc-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="960fc-131">El Generador de topologías usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="960fc-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="960fc-132">Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="960fc-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="960fc-133">Utilice únicamente caracteres estándar (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos.</span><span class="sxs-lookup"><span data-stu-id="960fc-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="960fc-134">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="960fc-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="960fc-135">A menudo, los caracteres no estándar de un FQDN no son compatibles con las entidades de certificación públicas y DNS externas (cuando se debe asignar el FQDN al SN en el certificado).</span><span class="sxs-lookup"><span data-stu-id="960fc-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="960fc-136">Para más información sobre cómo agregar un sufijo DNS al nombre de un equipo, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">configurar DNS para la compatibilidad con Edge en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="960fc-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="960fc-137">Haga clic en **grupo de equipos únicos**y, a continuación, en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="960fc-138">En **seleccionar características**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-139">Si planea usar un único FQDN e dirección IP para el servicio de acceso SIP, el servicio de conferencias web de Lync Server 2013 y los servicios perimetrales A/V, active la casilla **usar un único FQDN e dirección IP** .</span><span class="sxs-lookup"><span data-stu-id="960fc-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="960fc-140">Si planea habilitar la Federación, active la casilla **Habilitar la Federación para este grupo perimetral (puerto 5061)** .</span><span class="sxs-lookup"><span data-stu-id="960fc-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="960fc-141">Puede seleccionar esta opción, pero solo se puede publicar externamente un grupo perimetral o un servidor perimetral en su organización para la Federación.</span><span class="sxs-lookup"><span data-stu-id="960fc-141">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="960fc-142">Todo el acceso de usuarios federados, incluidos los usuarios de mensajería instantánea (mi) pública, con el mismo grupo perimetral o servidor de borde único.</span><span class="sxs-lookup"><span data-stu-id="960fc-142">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="960fc-143">Por ejemplo, si la implementación incluye un grupo perimetral o un solo servidor perimetral implementado en Nueva York y uno implementado en Londres y habilita la compatibilidad con la Federación en el grupo de servidores perimetrales de Nueva York o en el único servidor de borde, la señal de tráfico para usuarios federados pasará por la Nueva York. Grupo Edge o servidor perimetral único.</span><span class="sxs-lookup"><span data-stu-id="960fc-143">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="960fc-144">Esto es así incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres usa el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V.</span><span class="sxs-lookup"><span data-stu-id="960fc-144">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="960fc-145">Si tiene previsto admitir el protocolo de presencia y mensajería extensible (XMPP) para su implementación, active la casilla de verificación **Habilitar Federación XMPP (puerto 5269)**</span><span class="sxs-lookup"><span data-stu-id="960fc-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="960fc-146">En **seleccionar opciones de IP**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-147">**Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz interna de grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="960fc-148">**Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz interna de la agrupación perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="960fc-149">**Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz externa del grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="960fc-150">**Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="960fc-151">También puede configurar el servidor perimetral o el grupo Edge para usar una dirección de traducción de direcciones de red para las direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="960fc-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="960fc-152">Para ello, active la casilla **la dirección IP externa de este grupo de límites la traduce nat**.</span><span class="sxs-lookup"><span data-stu-id="960fc-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="960fc-153">En los **FQDN externos**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-154">Si en **seleccionar características** ha elegido usar un único FQDN e dirección IP para el acceso SIP, el servicio de conferencias web y el servicio perimetral a/V, escriba el FQDN externo en el **acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="960fc-155">Si elige esta opción, debe especificar un número de puerto diferente para cada uno de los servicios perimetrales (configuración de Puerto recomendado: 5061 para el servicio perimetral de Access, 444 para el servicio perimetral de conferencias web y 443 para el servicio perimetral de a/V).</span><span class="sxs-lookup"><span data-stu-id="960fc-155">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="960fc-156">Seleccionar esta opción puede ayudar a evitar posibles problemas de conectividad y simplificar la configuración, ya que puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.</span><span class="sxs-lookup"><span data-stu-id="960fc-156">Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="960fc-157">Si en **seleccionar características** no ha elegido usar un FQDN y una dirección IP únicos, escriba los FQDN externos para el **acceso SIP**, las **conferencias web** y el **audio video**, manteniendo los puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="960fc-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="960fc-158">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-158">Click **Next**.</span></span>

10. <span data-ttu-id="960fc-159">En **definir la dirección IP interna**, escriba la dirección IP de su servidor perimetral en la **dirección IPv4 interna** y la **dirección IPv6 interna** , según corresponda a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="960fc-159">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements.</span></span> <span data-ttu-id="960fc-160">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-160">Click **Next**.</span></span>

11. <span data-ttu-id="960fc-161">En **definir la dirección IP externa**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-162">Si decide usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral A/V, escriba la dirección IPv4 externa del servidor perimetral en **acceso SIP**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="960fc-163">Si decide usar direcciones IPv6, escriba la dirección IPv6 externa del servidor perimetral en **acceso SIP**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="960fc-164">Si no ha elegido usar un único FQDN e dirección IP para el acceso SIP, el servicio de conferencias web y el servicio perimetral A/V, escriba las direcciones IPv4 externas del servidor perimetral en **acceso SIP**, **conferencias web**y **conferencias a/v**y, a continuación, Haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="960fc-165">Si decide usar direcciones IPv6 y no ha elegido usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral a/V, escriba las direcciones IPv6 externas del servidor perimetral en **acceso SIP**, **conferencias web**y **a/ V Conferencia**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="960fc-166">Si no ha elegido habilitar ni asignar direcciones IPv6, no podrá ver este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="960fc-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="960fc-167">Si decide usar NAT, aparecerá un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="960fc-167">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="960fc-168">En **dirección IPv4 pública para el servicio a/V Edge**, escriba la dirección IPv4 pública que quiere que traduzca NAT y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-168">In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-169">Debe ser la dirección IP externa del servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="960fc-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="960fc-170">Si decide usar direcciones NAT e IPv6, aparecerá un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="960fc-170">If you chose to use NAT and IPv6 addresses, a dialog box appears.</span></span> <span data-ttu-id="960fc-171">En **dirección IPv6 pública para el servicio a/V Edge**, escriba la dirección IPv6 pública que quiere que traduzca NAT y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-171">In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-172">Debe ser la dirección IP externa del servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="960fc-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="960fc-173">En **definir el próximo salto**, en **grupo de próximo salto**, seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo de servidores Standard.</span><span class="sxs-lookup"><span data-stu-id="960fc-173">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="960fc-174">O bien, si su implementación incluye un director, seleccione el director.</span><span class="sxs-lookup"><span data-stu-id="960fc-174">Or, if your deployment includes a Director, select the Director.</span></span> <span data-ttu-id="960fc-175">A continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-175">Then, click **Next**.</span></span>

15. <span data-ttu-id="960fc-176">En la opción **asociar grupos front end**, especifique uno o varios pools internos, que pueden incluir grupos front-end y servidores Standard Edition, que se asociarán con este servidor perimetral, seleccionando los nombres de los pools internos para los que se usará este servidor perimetral. comunicación con usuarios externos admitidos.</span><span class="sxs-lookup"><span data-stu-id="960fc-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-177">Solo se puede asociar un grupo perimetral de carga equilibrada o un único servidor perimetral con cada grupo interno para tráfico de A/V.</span><span class="sxs-lookup"><span data-stu-id="960fc-177">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="960fc-178">Si ya tiene un grupo interno asociado con un grupo perimetral o un servidor perimetral, aparece una advertencia que indica que el grupo interno ya está asociado a un grupo perimetral o a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-178">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="960fc-179">Si selecciona un grupo que ya está asociado a otro servidor perimetral, este cambiará la asociación.</span><span class="sxs-lookup"><span data-stu-id="960fc-179">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="960fc-180">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="960fc-180">Click **Finish**.</span></span>

17. <span data-ttu-id="960fc-181">Publique su topología.</span><span class="sxs-lookup"><span data-stu-id="960fc-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="960fc-182">Para definir la topología de un grupo de servidores perimetrales de carga equilibrada de DNS</span><span class="sxs-lookup"><span data-stu-id="960fc-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="960fc-183">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="960fc-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="960fc-184">En el árbol de consola, expanda el sitio en el que desea implementar servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="960fc-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="960fc-185">Haga clic con \*\*\*\* el botón secundario en agrupaciones perimetrales y luego haga clic en **nuevo borde**.</span><span class="sxs-lookup"><span data-stu-id="960fc-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="960fc-186">En **definir el nuevo grupo de límites**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="960fc-187">En **definir el FQDN del grupo perimetral**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-188">En **FQDN del grupo**, escriba el nombre de dominio completo (FQDN) para la conexión interna del grupo Edge.</span><span class="sxs-lookup"><span data-stu-id="960fc-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="960fc-189">El nombre que especifique para el grupo debe ser el nombre del grupo de bordes interno.</span><span class="sxs-lookup"><span data-stu-id="960fc-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="960fc-190">Debe definirse como un FQDN.</span><span class="sxs-lookup"><span data-stu-id="960fc-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="960fc-191">El Generador de topologías usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="960fc-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="960fc-192">Utilice únicamente caracteres estándar (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos.</span><span class="sxs-lookup"><span data-stu-id="960fc-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="960fc-193">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="960fc-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="960fc-194">A menudo, los caracteres no estándar de un FQDN no son compatibles con las entidades de certificación públicas y DNS externas (cuando se debe asignar el FQDN al SN en el certificado).</span><span class="sxs-lookup"><span data-stu-id="960fc-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="960fc-195">Haga clic en **grupo de varios equipos**y, a continuación, en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="960fc-196">En **seleccionar características**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-197">Si tiene pensado usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web de Lync Server 2013 y los servicios perimetrales A/V, active la casilla **usar un único FQDN e dirección IP** .</span><span class="sxs-lookup"><span data-stu-id="960fc-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="960fc-198">Si tiene previsto habilitar la Federación, active la casilla **Habilitar la Federación para este grupo perimetral (puerto 5061)** .</span><span class="sxs-lookup"><span data-stu-id="960fc-198">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span> <span data-ttu-id="960fc-199">Haga clic en **siguiente**</span><span class="sxs-lookup"><span data-stu-id="960fc-199">Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="960fc-200">Puede seleccionar esta opción, pero solo se puede publicar externamente un grupo perimetral o un servidor perimetral en su organización para la Federación.</span><span class="sxs-lookup"><span data-stu-id="960fc-200">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="960fc-201">Todo el acceso de usuarios federados, incluidos los usuarios de mensajería instantánea (mi) pública, con el mismo grupo perimetral o servidor de borde único.</span><span class="sxs-lookup"><span data-stu-id="960fc-201">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="960fc-202">Por ejemplo, si la implementación incluye la implementación en Nueva York de un grupo de servidores perimetrales o un servidor perimetral único y la implementación de uno en Londres y habilita la compatibilidad de federación en el grupo de servidores perimetrales o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federales pasará por el grupo de servidores perimetrales o el servidor perimetral único de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="960fc-202">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="960fc-203">Esto es así incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres usa el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V.</span><span class="sxs-lookup"><span data-stu-id="960fc-203">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="960fc-204">Si tiene previsto admitir el protocolo de presencia y mensajería extensible (XMPP) para su implementación, active la casilla de verificación **Habilitar Federación XMPP (puerto 5269)**</span><span class="sxs-lookup"><span data-stu-id="960fc-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="960fc-205">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-205">Click **Next**.</span></span>

8.  <span data-ttu-id="960fc-206">En **seleccionar opciones de IP**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-207">**Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz interna de grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="960fc-208">**Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz interna de la agrupación perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="960fc-209">**Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz externa del grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="960fc-210">**Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="960fc-211">También puede configurar el servidor perimetral o el grupo Edge para usar una dirección de traducción de direcciones de red para las direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="960fc-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="960fc-212">Para ello, active la casilla **la dirección IP externa de este grupo de límites la traduce nat**.</span><span class="sxs-lookup"><span data-stu-id="960fc-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="960fc-213">En los **FQDN externos**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-214">Si en **seleccionar características** ha elegido usar un único FQDN e dirección IP para el acceso SIP, el servicio de conferencias web y el servicio perimetral a/V, escriba el FQDN externo en el **acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="960fc-215">Si elige esta opción, debe especificar un número de puerto diferente para cada uno de los servicios perimetrales (configuración de Puerto recomendado: 5061 para el servicio perimetral de Access, 444 para el servicio perimetral de conferencias web y 443 para el servicio perimetral de a/V).</span><span class="sxs-lookup"><span data-stu-id="960fc-215">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="960fc-216">Al seleccionar esta opción, puede ayudar a evitar posibles problemas de conectividad y simplificar la configuración porque puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.</span><span class="sxs-lookup"><span data-stu-id="960fc-216">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="960fc-217">Si en **seleccionar características** no ha elegido usar un FQDN y una dirección IP únicos, escriba el FQDN que ha elegido para el lado público al que está enfrentada el grupo perimetral para el **acceso por SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-217">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="960fc-218">En **conferencias web**, escriba el FQDN que ha elegido para el lado público al que está enfrentada el grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-218">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="960fc-219">En **audio o vídeo**, escriba el nombre de dominio completo que haya elegido para el lado al que se enfrentará el grupo del borde.</span><span class="sxs-lookup"><span data-stu-id="960fc-219">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="960fc-220">Use los puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="960fc-220">Use the default ports.</span></span>

10. <span data-ttu-id="960fc-221">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-221">Click **Next**.</span></span>

11. <span data-ttu-id="960fc-222">En **definir los equipos de este grupo**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="960fc-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="960fc-223">En **nombre completo y dirección IP internos**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-224">En **dirección IPv4 interna**, escriba la dirección IPv4 y la **dirección IPv6 interna** , según corresponda a sus requisitos para el primer servidor perimetral que desea crear en este grupo.</span><span class="sxs-lookup"><span data-stu-id="960fc-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="960fc-225">En **nombre de dominio interno**, escriba el FQDN del primer servidor perimetral que desea crear en este grupo.</span><span class="sxs-lookup"><span data-stu-id="960fc-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="960fc-226">El nombre que especifique necesita ser idéntico al nombre del equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="960fc-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="960fc-227">Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="960fc-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="960fc-228">El Generador de topologías usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="960fc-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="960fc-229">Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="960fc-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="960fc-230">Use solo caracteres estándar (incluidos A-Z, a-z, 0-9 y guiones) al asignar FQDN de sus servidores de Lync, servidores perimetrales, grupos y matrices.</span><span class="sxs-lookup"><span data-stu-id="960fc-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="960fc-231">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="960fc-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="960fc-232">A menudo, los caracteres no estándar de un FQDN no son compatibles con las entidades de certificación públicas y DNS externas (cuando se debe asignar el FQDN al SN en el certificado).</span><span class="sxs-lookup"><span data-stu-id="960fc-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="960fc-233">Para más información sobre cómo agregar un sufijo DNS al nombre de un equipo, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">configurar DNS para la compatibilidad con Edge en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="960fc-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="960fc-234">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-234">Click **Next**.</span></span>

14. <span data-ttu-id="960fc-235">En **definir las direcciones IP externas**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-236">Si decide usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral A/V, escriba la dirección IP externa del servidor perimetral en **acceso de SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="960fc-237">Si no ha elegido usar un FQDN y una dirección IP únicos para el servicio de conferencia de acceso por SIP, servicio de conferencias por Internet y a/V, escriba la dirección IP que haya elegido para el lado de cara pública de este servidor de grupo de bordes para el **acceso de SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-237">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="960fc-238">En **conferencias web**, escriba la dirección IP que ha elegido para el lado de la dirección pública de este servidor de la agrupación perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-238">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="960fc-239">En **conferencia A/V**, escriba la dirección IP que ha elegido para el lado al que va dirigida la pública de este servidor de la agrupación perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-239">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="960fc-240">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-240">Click **Next**.</span></span>

16. <span data-ttu-id="960fc-241">Si decide habilitar las direcciones IPv6, en **definir las direcciones IP externas**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-242">Si decide usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral A/V, escriba la dirección IPv6 externa del servidor perimetral en **acceso de SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="960fc-243">Si no ha elegido usar un FQDN y una dirección IP únicos para el servicio de conferencia de acceso por SIP, servicio de conferencias por Internet y a/V, escriba la dirección IPv6 que haya elegido para el lado de cara pública de este servidor de grupo de bordes para el **acceso de SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-243">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="960fc-244">En **conferencias web**, escriba la dirección IPv6 que haya elegido para el lado al que va dirigida la pública de este servidor de grupo de bordes.</span><span class="sxs-lookup"><span data-stu-id="960fc-244">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="960fc-245">En **conferencias A/V**, escriba la dirección IPv6 que ha elegido para el lado al que se enfrenta su público en este servidor de la agrupación perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-245">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-246">Si no ha elegido habilitar ni asignar direcciones IPv6, no podrá ver este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="960fc-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="960fc-247">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="960fc-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-248">Ahora verá el primer servidor perimetral que creó en su grupo en el cuadro de diálogo <STRONG>definir los equipos de este grupo</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="960fc-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="960fc-249">En **definir los equipos de este grupo**, haga clic en **Agregar**y, a continuación, repita los pasos 11 a 14 para el segundo servidor perimetral que desea agregar al grupo de bordes.</span><span class="sxs-lookup"><span data-stu-id="960fc-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="960fc-250">Después de repetir los pasos 11 a 14, haga clic en **siguiente** en **definir los equipos de este grupo**.</span><span class="sxs-lookup"><span data-stu-id="960fc-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-251">En este momento, puede ver ambos servidores perimetrales en su grupo.</span><span class="sxs-lookup"><span data-stu-id="960fc-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="960fc-252">Si decide usar NAT, aparecerá un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="960fc-252">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="960fc-253">En **dirección IP pública**, escriba las direcciones IPv4 e IPv6 públicas (según corresponda) que NAT va a traducir y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-253">In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-254">Debe ser la dirección IP externa del borde A/V.</span><span class="sxs-lookup"><span data-stu-id="960fc-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="960fc-255">En **definir el próximo salto**, en la lista **siguiente grupo** de saltos, seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="960fc-255">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="960fc-256">O bien, si su implementación incluye un director, seleccione el nombre del director.</span><span class="sxs-lookup"><span data-stu-id="960fc-256">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="960fc-257">A continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-257">Then, click **Next**.</span></span>

22. <span data-ttu-id="960fc-258">En la sección **asociar grupos front end**, especifique uno o varios grupos internos, que pueden incluir grupos de aplicaciones para el usuario y servidores Standard Edition, que se asociarán con este servidor perimetral seleccionando los nombres de los pools internos que usarán este servidor perimetral para comunicación con usuarios externos admitidos.</span><span class="sxs-lookup"><span data-stu-id="960fc-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-259">Solo se puede asociar un grupo perimetral de carga equilibrada o un único servidor perimetral con cada grupo interno para tráfico de A/V.</span><span class="sxs-lookup"><span data-stu-id="960fc-259">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="960fc-260">Si ya tiene un grupo interno asociado con un grupo perimetral o un servidor perimetral, aparece una advertencia que indica que el grupo interno ya está asociado a un grupo perimetral o a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-260">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="960fc-261">Si selecciona un grupo que ya está asociado a otro servidor perimetral, este cambiará la asociación.</span><span class="sxs-lookup"><span data-stu-id="960fc-261">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="960fc-262">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="960fc-262">Click **Finish**.</span></span>

24. <span data-ttu-id="960fc-263">Publique su topología.</span><span class="sxs-lookup"><span data-stu-id="960fc-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="960fc-264">Para definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="960fc-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="960fc-265">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="960fc-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="960fc-266">En el árbol de consola, expanda el sitio en el que desea implementar servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="960fc-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="960fc-267">Haga clic con \*\*\*\* el botón secundario en agrupaciones perimetrales y seleccione **nuevo grupo perimetral**.</span><span class="sxs-lookup"><span data-stu-id="960fc-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="960fc-268">En **definir el nuevo grupo de límites**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="960fc-269">En **definir el FQDN del grupo perimetral**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-270">En **FQDN**, escriba el nombre de dominio completo (FQDN) que ha elegido para el lado interno del grupo Edge.</span><span class="sxs-lookup"><span data-stu-id="960fc-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="960fc-271">El nombre que especifique para el grupo debe ser el nombre del grupo de bordes interno.</span><span class="sxs-lookup"><span data-stu-id="960fc-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="960fc-272">Debe definirse como un FQDN.</span><span class="sxs-lookup"><span data-stu-id="960fc-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="960fc-273">El Generador de topologías usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="960fc-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="960fc-274">Utilice únicamente caracteres estándar (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos.</span><span class="sxs-lookup"><span data-stu-id="960fc-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="960fc-275">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="960fc-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="960fc-276">A menudo, los caracteres no estándar de un FQDN no son compatibles con las entidades de certificación públicas y DNS externas (cuando se debe asignar el FQDN al SN en el certificado).</span><span class="sxs-lookup"><span data-stu-id="960fc-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="960fc-277">Haga clic en **varios grupos de equipos**y luego en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="960fc-278">En **seleccionar características** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="960fc-279">Si tiene pensado usar un FQDN y una dirección IP únicos para el servicio de acceso SIP, el servicio de conferencias web de Lync Server y el servicio perimetral A/V, active la casilla **usar un solo FQDN & dirección IP** .</span><span class="sxs-lookup"><span data-stu-id="960fc-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="960fc-280">Si tiene previsto habilitar la Federación, active la casilla **Habilitar la Federación para este grupo perimetral (puerto 5061)** .</span><span class="sxs-lookup"><span data-stu-id="960fc-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="960fc-281">Puede seleccionar esta opción, pero solo se puede publicar externamente un grupo perimetral o un servidor perimetral en su organización para la Federación.</span><span class="sxs-lookup"><span data-stu-id="960fc-281">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation.</span></span> <span data-ttu-id="960fc-282">Todo el acceso de usuarios federados, incluidos los usuarios de mensajería instantánea (mi) pública, con el mismo grupo perimetral o servidor de borde único.</span><span class="sxs-lookup"><span data-stu-id="960fc-282">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="960fc-283">Por ejemplo, si la implementación incluye la implementación en Nueva York de un grupo de servidores perimetrales o un servidor perimetral único y la implementación de uno en Londres y habilita la compatibilidad de federación en el grupo de servidores perimetrales o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federales pasará por el grupo de servidores perimetrales o el servidor perimetral único de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="960fc-283">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="960fc-284">Esto es así incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres usa el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V.</span><span class="sxs-lookup"><span data-stu-id="960fc-284">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="960fc-285">Si tiene previsto admitir el protocolo de presencia y mensajería extensible (XMPP) para su implementación, active la casilla de verificación **Habilitar Federación XMPP (puerto 5269)**</span><span class="sxs-lookup"><span data-stu-id="960fc-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="960fc-286">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-286">Click **Next**.</span></span>

8.  <span data-ttu-id="960fc-287">En **seleccionar opciones de IP**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-288">**Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz interna de grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="960fc-289">**Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz interna de la agrupación perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="960fc-290">**Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz externa del grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="960fc-291">**Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="960fc-292"><STRONG>No</STRONG> seleccione la casilla de verificación <STRONG>la dirección IP externa del grupo de servidores perimetrales está traducida por NAT</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="960fc-292"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box.</span></span> <span data-ttu-id="960fc-293">La traducción de direcciones de red (NAT) no es compatible cuando se usa el equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="960fc-293">Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="960fc-294">En los **FQDN externos**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-295">Si en **seleccionar características** ha elegido usar un único FQDN e dirección IP para el acceso SIP, el servicio de conferencias web y el servicio perimetral a/V, escriba el FQDN externo en el **acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="960fc-296">Si elige esta opción, debe especificar un número de puerto diferente para cada uno de los servicios perimetrales (configuración de Puerto recomendado: 5061 para el servicio perimetral de Access, 444 para el servicio perimetral de conferencias web y 443 para el servicio perimetral a/V).</span><span class="sxs-lookup"><span data-stu-id="960fc-296">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="960fc-297">Al seleccionar esta opción, puede ayudar a evitar posibles problemas de conectividad y simplificar la configuración porque puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.</span><span class="sxs-lookup"><span data-stu-id="960fc-297">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="960fc-298">Si en **seleccionar características** no ha elegido usar un FQDN y una dirección IP únicos, escriba el FQDN que ha elegido para el lado público al que está enfrentada el grupo perimetral para el **acceso por SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-298">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="960fc-299">En **conferencias web**, escriba el FQDN que ha elegido para el lado público al que está enfrentada el grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-299">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="960fc-300">En **audio o vídeo**, escriba el nombre de dominio completo que haya elegido para el lado al que se enfrentará el grupo del borde.</span><span class="sxs-lookup"><span data-stu-id="960fc-300">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="960fc-301">Use los puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="960fc-301">Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="960fc-302">Estos serán los FQDN de IP virtual (VIP) de orientación pública para el grupo.</span><span class="sxs-lookup"><span data-stu-id="960fc-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="960fc-303">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-303">Click **Next**.</span></span>

11. <span data-ttu-id="960fc-304">En **definir los equipos de este grupo**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="960fc-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="960fc-305">En **definir las direcciones IP externas**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-306">Si decide usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral de A/V, escriba la dirección IPv4 externa del servidor perimetral en el **acceso por SIP**. dirección IP externa del servidor perimetral en **acceso de SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="960fc-307">Si no ha elegido usar un FQDN y una dirección IP únicos para el servicio de conferencia de acceso por SIP, servicio de conferencias por Internet y a/V, escriba la dirección IP que haya elegido para el lado de cara pública de este servidor de grupo de bordes para el **acceso de SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-307">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="960fc-308">En **conferencias web**, escriba la dirección IP que ha elegido para el lado de la dirección pública de este servidor de la agrupación perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-308">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="960fc-309">En **conferencia A/V**, escriba la dirección IP que ha elegido para el lado al que va dirigida la pública de este servidor de la agrupación perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-309">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="960fc-310">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-310">Click **Next**.</span></span>

14. <span data-ttu-id="960fc-311">Si decide habilitar las direcciones IPv6, en **definir las direcciones IP externas**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960fc-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="960fc-312">Si decide usar un FQDN y una dirección IP únicos para el acceso SIP, el servicio de conferencias web y el servicio perimetral A/V, escriba la dirección IPv6 externa del servidor perimetral en **acceso de SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="960fc-313">Si no ha elegido usar un FQDN y una dirección IP únicos para el servicio de conferencia de acceso por SIP, servicio de conferencias por Internet y a/V, escriba la dirección IPv6 que haya elegido para el lado de cara pública de este servidor de grupo de bordes para el **acceso de SIP**.</span><span class="sxs-lookup"><span data-stu-id="960fc-313">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="960fc-314">En **conferencias web**, escriba la dirección IPv6 que haya elegido para el lado al que va dirigida la pública de este servidor de grupo de bordes.</span><span class="sxs-lookup"><span data-stu-id="960fc-314">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="960fc-315">En **conferencias A/V**, escriba la dirección IPv6 que ha elegido para el lado al que se enfrenta su público en este servidor de la agrupación perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-315">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-316">Si no ha elegido habilitar ni asignar direcciones IPv6, no podrá ver este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="960fc-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="960fc-317">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="960fc-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-318">Ahora verá el primer servidor perimetral que creó en su grupo en el cuadro de diálogo <STRONG>definir los equipos de este grupo</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="960fc-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="960fc-319">En **definir los equipos de este grupo**, haga clic en **Agregar**y, a continuación, repita los pasos 11 a 14 para el segundo servidor perimetral que desea agregar al grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="960fc-320">Después de repetir los pasos 11 a 14, haga clic en **siguiente** en **definir los equipos de este grupo**.</span><span class="sxs-lookup"><span data-stu-id="960fc-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-321">En este momento, puede ver ambos servidores perimetrales en su grupo.</span><span class="sxs-lookup"><span data-stu-id="960fc-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="960fc-322">En **definir el próximo salto**, en la lista **siguiente grupo** de saltos, seleccione el nombre del grupo interno, que puede ser un grupo de servidores front-end o un grupo Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="960fc-322">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="960fc-323">O bien, si su implementación incluye un director, seleccione el nombre del director.</span><span class="sxs-lookup"><span data-stu-id="960fc-323">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="960fc-324">A continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="960fc-324">Then, click **Next**.</span></span>

19. <span data-ttu-id="960fc-325">En la sección **asociar grupos front end**, especifique uno o varios grupos internos, que pueden incluir grupos de aplicaciones para el usuario y servidores Standard Edition, que se asociarán con este servidor perimetral seleccionando los nombres de los pools internos que usarán este servidor perimetral para comunicación con usuarios externos admitidos.</span><span class="sxs-lookup"><span data-stu-id="960fc-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="960fc-326">Solo se puede asociar un grupo perimetral de carga equilibrada o un único servidor perimetral con cada grupo interno para tráfico de A/V.</span><span class="sxs-lookup"><span data-stu-id="960fc-326">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="960fc-327">Si ya tiene un grupo interno asociado con un grupo perimetral o un servidor perimetral, aparece una advertencia que indica que el grupo interno ya está asociado a un grupo perimetral o a un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="960fc-327">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="960fc-328">Si selecciona un grupo que ya está asociado a otro servidor perimetral, este cambiará la asociación.</span><span class="sxs-lookup"><span data-stu-id="960fc-328">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="960fc-329">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="960fc-329">Click **Finish**.</span></span>

21. <span data-ttu-id="960fc-330">Publique su topología.</span><span class="sxs-lookup"><span data-stu-id="960fc-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

