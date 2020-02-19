---
title: 'Lync Server 2013: definir la topología perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55653e39086c311778335999d2e9fc2101b28d40
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="22077-102">Definir la topología perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22077-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22077-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="22077-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="22077-104">Debe usar el generador de topologías para crear la topología y debe configurar al menos un grupo de servidores front-end interno o un servidor Standard Edition para poder implementar el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="22077-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="22077-105">Use el siguiente procedimiento para definir la topología perimetral para un solo servidor perimetral y, a continuación, use los procedimientos descritos en [Publish Your Topology in Lync server 2013](lync-server-2013-publish-your-topology.md) y [Export your Lync Server 2013 Topology y cópielo en medios externos para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) para publicar la topología y ponerla a disposición de su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="22077-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22077-p102">La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.</span><span class="sxs-lookup"><span data-stu-id="22077-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="22077-108">Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como usuario miembro de los grupos Administradores del dominio y RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="22077-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="22077-109">También puede conceder los derechos y permisos de administrador necesarios para agregar roles de servidor a una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="22077-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="22077-110">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="22077-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="22077-111">Para realizar otros cambios de configuración, solo se requiere pertenecer al grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="22077-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="22077-112">Si definió la topología perimetral cuando definió y publicó la topología interna y no es necesario modificarla, no tendrá que volver a definirla y publicarla .</span><span class="sxs-lookup"><span data-stu-id="22077-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="22077-113">Use el procedimiento siguiente solo si debe realizar cambios en la topología perimetral.</span><span class="sxs-lookup"><span data-stu-id="22077-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="22077-114">Debe hacer que la topología previamente definida y publicada esté disponible para los servidores perimetrales, lo que lo hace mediante el procedimiento descrito en [exportar su topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="22077-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="22077-115">No se puede ejecutar el generador de topologías desde un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="22077-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="22077-116">Debe ejecutarlo desde un servidor front-end o servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="22077-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="22077-117">El proceso para definir la topología del servidor perimetral se realiza en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="22077-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="22077-118">Los tres tipos principales de topologías del servidor perimetral que planea y configura se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="22077-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="22077-119">Procedimiento para definir la topología de un solo servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="22077-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="22077-120">Procedimiento para definir la topología para un grupo de servidores perimetrales con equilibrio de carga</span><span class="sxs-lookup"><span data-stu-id="22077-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="22077-121">Procedimiento para definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="22077-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="22077-122">Procedimiento para definir la topología de un solo servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="22077-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="22077-123">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="22077-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="22077-124">En el árbol de consola, expanda el sitio en el que desea implementar un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="22077-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="22077-125">Haga clic con el botón secundario en **grupos**de servidores perimetrales y haga clic en **nuevo grupo de servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="22077-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="22077-126">En **Definir el nuevo grupo de servidores perimetrales**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="22077-127">En **Definir el FQDN del grupo perimetral**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="22077-128">En **FQDN del grupo de servidores**, escriba el nombre de dominio completo (FQDN) de la interfaz interna del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="22077-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="22077-129">El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="22077-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="22077-130">De manera predeterminada, el nombre de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="22077-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="22077-131">Topology Builder usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="22077-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="22077-132">Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio.</span><span class="sxs-lookup"><span data-stu-id="22077-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="22077-133">Utilice únicamente caracteres estándar  (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores Lync, servidores perimetrales y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="22077-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="22077-134">No use caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="22077-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="22077-135">Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).</span><span class="sxs-lookup"><span data-stu-id="22077-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="22077-136">Para obtener información detallada sobre cómo agregar un sufijo DNS a un nombre de equipo, vea <A href="lync-server-2013-configure-dns-for-edge-support.md">configurar DNS para compatibilidad con servidores perimetrales en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="22077-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="22077-137">Haga clic en **Grupo de servidores de un solo equipo** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="22077-138">En **Seleccionar características**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="22077-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="22077-139">Si planea usar un solo FQDN y una dirección IP para el servicio de acceso SIP, el servicio de conferencia Web de Lync Server 2013 y los servicios perimetrales A/V, active la casilla **usar un solo FQDN y una dirección IP** .</span><span class="sxs-lookup"><span data-stu-id="22077-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="22077-140">Si piensa habilitar la federación, active la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="22077-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="22077-p108">Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="22077-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="22077-145">Si piensa admitir el Protocolo extensible de mensajería y presencia (XMPP) en su implementación, active la casilla **Habilitar federación (puerto 5269)**.</span><span class="sxs-lookup"><span data-stu-id="22077-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="22077-146">En **Seleccionar características de IP**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="22077-147">**Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="22077-148">**Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="22077-149">**Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="22077-150">**Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="22077-151">También puede configurar el servidor perimetral o el grupo de servidores perimetrales para que usen una dirección de traducción de direcciones de red para las direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="22077-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="22077-152">Para hacerlo, active la casilla **La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT**.</span><span class="sxs-lookup"><span data-stu-id="22077-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="22077-153">En **FQDN externos**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="22077-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="22077-154">Si, en **Seleccionar características**, decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba el FQDN externo en **Acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="22077-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="22077-p110">Si selecciona esta opción, debe especificar un número de puerto distinto para cada uno de los servicios perimetrales (configuración de puertos recomendada: 5061 para el servicio perimetral de acceso, 444 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Al seleccionar esta opción, se evitan posibles problemas de conectividad y se simplifica la configuración, ya que se puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.</span><span class="sxs-lookup"><span data-stu-id="22077-p110">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="22077-157">Si, en **Seleccionar características**, no eligió la opción de usar un solo FQDN y una dirección IP, escriba los nombres de dominio completos externos de **Acceso SIP**, **Conferencia web** y **Audio/vídeo**, sin cambiar los puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="22077-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="22077-158">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-158">Click **Next**.</span></span>

10. <span data-ttu-id="22077-p111">En **Definir la dirección IP interna**, escriba la dirección IP del servidor perimetral en **Dirección IPv4 interna** y en **Dirección IPv6 interna** según corresponda. Después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-p111">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements. Click **Next**.</span></span>

11. <span data-ttu-id="22077-161">En **Definir la dirección IP externa**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="22077-162">Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv4 externa del servidor perimetral en **Acceso SIP** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="22077-163">Si decidió usar direcciones IPv6, escriba la dirección IPv6 externa del servidor perimetral en **Acceso SIP** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="22077-164">Si decidió no usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba las direcciones IPv4 externas del servidor perimetral en **Acceso SIP**, **Conferencia web** y **Conferencia A/V** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="22077-165">Si decidió usar direcciones IPv6 pero no eligió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba las direcciones IPv6 externas del servidor perimetral en **Acceso SIP**, **Conferencia web** y **Conferencia A/V** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="22077-166">Si no eligió habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="22077-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="22077-p112">Si decidió usar NAT, aparecerá un cuadro de diálogo. En **Dirección IPv4 pública para el servicio perimetral A/V**, escriba la dirección IPv4 pública que deberá traducir NAT y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-p112">If you chose to use NAT, a dialog box appears. In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-169">Debe ser la dirección IP externa del servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="22077-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="22077-p113">Si decidió usar NAT y direcciones IPv6, aparecerá un cuadro de diálogo. En **Dirección IPv6 pública para el servicio perimetral A/V**, escriba la dirección IPv6 pública que deberá traducir NAT y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-p113">If you chose to use NAT and IPv6 addresses, a dialog box appears. In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-172">Debe ser la dirección IP externa del servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="22077-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="22077-p114">En **Definir el próximo salto**, en **Grupo de servidores del próximo salto**, seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores front-end o Standard Edition. O, si la implementación incluye un director, selecciónelo. A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-p114">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the Director. Then, click **Next**.</span></span>

15. <span data-ttu-id="22077-176">En **Asociar grupos front-end**, especifique uno o más grupos de servidores internos, que pueden incluir grupos de servidores front-end y servidores Standard Edition, para asociarlos a este servidor perimetral; para ello, seleccione los nombres de los grupos de servidores internos que usarán este servidor perimetral para comunicarse con los usuarios externos compatibles.</span><span class="sxs-lookup"><span data-stu-id="22077-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-p115">Solo se puede asociar un servidor perimetral único o un grupo de servidores perimetrales de carga equilibrada a cada grupo interno para el tráfico de A/V. Si ya ha asociado un grupo de servidores interno a un servidor perimetral o a un grupo de servidores perimetrales, aparecerá una advertencia para indicarle que el grupo de servidores interno ya está asociado a un servidor perimetral o a un grupo de servidores perimetrales. Si selecciona un grupo de servidores que ya está asociado a otro servidor perimetral, cambiará la asociación.</span><span class="sxs-lookup"><span data-stu-id="22077-p115">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="22077-180">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="22077-180">Click **Finish**.</span></span>

17. <span data-ttu-id="22077-181">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="22077-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="22077-182">Procedimiento para definir la topología para un grupo de servidores perimetrales con equilibrio de carga DNS</span><span class="sxs-lookup"><span data-stu-id="22077-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="22077-183">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="22077-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="22077-184">En el árbol de consola, expanda el sitio en el que desea implementar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="22077-185">Haga clic con el botón secundario en \*\*Grupos de servidores perimetrales \*\* y, a continuación, en \*\*Nuevo grupo de servidores perimetrales \*\*.</span><span class="sxs-lookup"><span data-stu-id="22077-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="22077-186">En **Definir el nuevo grupo de servidores perimetrales**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="22077-187">En **Definir el FQDN del grupo perimetral**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="22077-188">En **FQDN del grupo de servidores**, escriba el nombre de dominio completo (FQDN) de la conexión interna del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="22077-189">El nombre que especifique para el grupo de servidores debe ser el nombre del grupo de servidores perimetrales interno.</span><span class="sxs-lookup"><span data-stu-id="22077-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="22077-190">Debe definirse como un FQDN.</span><span class="sxs-lookup"><span data-stu-id="22077-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="22077-191">Topology Builder usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="22077-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="22077-192">Use únicamente caracteres estándar (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores Lync, servidores perimetrales y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="22077-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="22077-193">No use caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="22077-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="22077-194">Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).</span><span class="sxs-lookup"><span data-stu-id="22077-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="22077-195">Haga clic en **Grupo de servidores de varios equipos** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="22077-196">En **Seleccionar características**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="22077-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="22077-197">Si planea usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia Web de Lync Server 2013 y los servicios perimetrales A/V, active la casilla **usar un solo FQDN y una dirección IP** .</span><span class="sxs-lookup"><span data-stu-id="22077-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="22077-p117">Si piensa habilitar la federación, active la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-p117">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box. Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="22077-p118">Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="22077-p118">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="22077-204">Si piensa admitir el Protocolo extensible de mensajería y presencia (XMPP) en su implementación, active la casilla **Habilitar federación (puerto 5269)**.</span><span class="sxs-lookup"><span data-stu-id="22077-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="22077-205">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-205">Click **Next**.</span></span>

8.  <span data-ttu-id="22077-206">En **Seleccionar características de IP**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="22077-207">**Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="22077-208">**Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="22077-209">**Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="22077-210">**Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="22077-211">También puede configurar el servidor perimetral o el grupo de servidores perimetrales para que usen una dirección de traducción de direcciones de red para las direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="22077-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="22077-212">Para hacerlo, active la casilla **La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT**.</span><span class="sxs-lookup"><span data-stu-id="22077-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="22077-213">En **FQDN externos**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="22077-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="22077-214">Si, en **Seleccionar características**, decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba el FQDN externo en **Acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="22077-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="22077-p120">Si selecciona esta opción, debe especificar un número de puerto distinto para cada uno de los servicios perimetrales (configuración de puertos recomendada: 5061 para el servicio perimetral de acceso, 444 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Al seleccionar esta opción, se evitan posibles problemas de conectividad y se simplifica la configuración, ya que se puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.</span><span class="sxs-lookup"><span data-stu-id="22077-p120">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="22077-p121">Si, en **Seleccionar características**, no eligió la opción de usar un solo FQDN y una dirección IP, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales en **Acceso SIP**. En **Conferencia web**, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. En **Audio/Vídeo**, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. Use los puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="22077-p121">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>

10. <span data-ttu-id="22077-221">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-221">Click **Next**.</span></span>

11. <span data-ttu-id="22077-222">En **Definir los equipos de este grupo**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="22077-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="22077-223">En **FQDN y dirección IP internos**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="22077-224">En **Dirección IPv4 interna** y en **Dirección IPv6 interna**, escriba las direcciones IPv4 y IPv6 correspondientes del primer servidor perimetral que desea crear en este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="22077-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="22077-225">En **FQDN interno**, escriba el FQDN del primer servidor perimetral que desea crear en este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="22077-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="22077-226">El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="22077-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="22077-227">De forma predeterminada, un equipo no incorporado a un dominio tiene un nombre corto, no un nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="22077-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="22077-228">Topology Builder usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="22077-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="22077-229">Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como un servidor perimetral no unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="22077-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="22077-230">Utilice únicamente caracteres estándar (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores Lync, servidores perimetrales y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="22077-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="22077-231">No use caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="22077-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="22077-232">Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).</span><span class="sxs-lookup"><span data-stu-id="22077-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="22077-233">Para obtener información detallada sobre cómo agregar un sufijo DNS a un nombre de equipo, vea <A href="lync-server-2013-configure-dns-for-edge-support.md">configurar DNS para compatibilidad con servidores perimetrales en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="22077-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="22077-234">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-234">Click **Next**.</span></span>

14. <span data-ttu-id="22077-235">En **Definir las direcciones IP externas**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="22077-236">Si decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IP externa del servidor perimetral en **Acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="22077-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="22077-p123">Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP**. En **Conferencia web**, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V**, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-p123">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="22077-240">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-240">Click **Next**.</span></span>

16. <span data-ttu-id="22077-241">Si habilitó las direcciones IPv6, en **Definir las direcciones IP externas** haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="22077-242">Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv6 externa del servidor perimetral en **Acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="22077-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="22077-p124">Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP**. En **Conferencia web**, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V**, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-p124">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-246">Si no eligió habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="22077-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="22077-247">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="22077-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-248">Ahora verá el primer servidor perimetral que creó en el grupo de servidores perimetrales, en el cuadro de diálogo <STRONG>Definir los equipos de este grupo</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="22077-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="22077-249">En **Definir los equipos de este grupo**, haga clic en **Agregar** y, a continuación, repita los pasos del 11 al 14 para agregar el segundo servidor perimetral que desee al grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="22077-250">Después de repetir los pasos del 11 al 14, haga clic en **Siguiente** en **Definir los equipos de este grupo**.</span><span class="sxs-lookup"><span data-stu-id="22077-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-251">En ese momento, podrá ver ambos servidores perimetrales en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="22077-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="22077-p125">Si decidió usar NAT, aparecerá un cuadro de diálogo. En **Dirección IP pública**, escriba las direcciones IPv4 y IPv6 públicas correspondientes que deberá traducir NAT y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-p125">If you chose to use NAT, a dialog box appears. In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-254">Debe ser la dirección IP externa del servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="22077-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="22077-p126">En **Definir el próximo salto**, en la lista **Grupo de servidores del próximo salto**, seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores front-end o un grupo de servidores Standard Edition. O, si la implementación incluye un director, seleccione el nombre del director. A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-p126">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

22. <span data-ttu-id="22077-258">En **Asociar grupos front-end**, especifique uno o más grupos de servidores internos, que pueden incluir grupos de servidores front-end y servidores Standard Edition, para asociarlos a este servidor perimetral; para ello, seleccione los nombres de los grupos de servidores internos que usarán este servidor perimetral para comunicarse con los usuarios externos compatibles.</span><span class="sxs-lookup"><span data-stu-id="22077-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-p127">Solo se puede asociar un servidor perimetral único o un grupo de servidores perimetrales de carga equilibrada a cada grupo interno para el tráfico de A/V. Si ya ha asociado un grupo de servidores interno a un servidor perimetral o a un grupo de servidores perimetrales, aparecerá una advertencia para indicarle que el grupo de servidores interno ya está asociado a un servidor perimetral o a un grupo de servidores perimetrales. Si selecciona un grupo de servidores que ya está asociado a otro servidor perimetral, cambiará la asociación.</span><span class="sxs-lookup"><span data-stu-id="22077-p127">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="22077-262">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="22077-262">Click **Finish**.</span></span>

24. <span data-ttu-id="22077-263">Publique su topología.</span><span class="sxs-lookup"><span data-stu-id="22077-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="22077-264">Procedimiento para definir la topología de un grupo de servidores perimetrales con equilibrio de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="22077-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="22077-265">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="22077-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="22077-266">En el árbol de consola, expanda el sitio en el que desea implementar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="22077-267">Haga clic con el botón secundario en grupos de servidores **perimetrales**y seleccione **nuevo grupo de servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="22077-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="22077-268">En **Definir el nuevo grupo de servidores perimetrales**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="22077-269">En **Definir el FQDN del grupo de servidores perimetrales**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="22077-270">En **FQDN**, escriba el nombre de dominio completo (FQDN) que haya elegido para el lado interno del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="22077-271">El nombre que especifique para el grupo de servidores debe ser el nombre del grupo de servidores perimetrales interno.</span><span class="sxs-lookup"><span data-stu-id="22077-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="22077-272">Debe definirse como un FQDN.</span><span class="sxs-lookup"><span data-stu-id="22077-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="22077-273">Topology Builder usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="22077-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="22077-274">Use únicamente caracteres estándar (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo a los servidores Lync, servidores perimetrales y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="22077-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="22077-275">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="22077-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="22077-276">Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).</span><span class="sxs-lookup"><span data-stu-id="22077-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="22077-277">Haga clic en **grupo de varios equipos**y, a continuación, en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="22077-278">En **Seleccionar características**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="22077-279">Si planea usar un solo FQDN y una dirección IP para el servicio de acceso SIP, el servicio de conferencia Web de Lync Server y el servicio perimetral A/V, active la casilla **usar un solo FQDN & dirección IP** .</span><span class="sxs-lookup"><span data-stu-id="22077-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="22077-280">Si piensa habilitar la federación, active la casilla **Habilitar federación (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="22077-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="22077-p129">Puede seleccionar esta opción, pero solo se puede publicar externamente para la federación un servidor perimetral o un grupo de servidores perimetrales de su organización. Cualquier acceso de usuarios federados, incluidos los usuarios de mensajería instantánea pública, se realiza a través del mismo grupo de servidores perimetrales o de un único servidor perimetral. Por ejemplo, si la implementación incluye un grupo de servidores perimetrales o un único servidor perimetral implementado en Nueva York y otro implementado en Londres y habilita la compatibilidad con la federación en el grupo de servidores o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federados se realizará a través del grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto ocurre incluso para las comunicaciones con los usuarios de Londres, aunque un usuario interno de Londres que llama a un usuario federado de Londres use el grupo de servidores o el servidor perimetral de Londres para el tráfico de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="22077-p129">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="22077-285">Si piensa admitir el Protocolo extensible de mensajería y presencia (XMPP) en su implementación, active la casilla **Habilitar federación (puerto 5269)**.</span><span class="sxs-lookup"><span data-stu-id="22077-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="22077-286">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-286">Click **Next**.</span></span>

8.  <span data-ttu-id="22077-287">En **Seleccionar características de IP**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="22077-288">**Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="22077-289">**Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="22077-290">**Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="22077-291">**Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="22077-p130"><STRONG>No</STRONG> active la casilla <STRONG>La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT</STRONG>. La traducción de direcciones de red (NAT) no es compatible con el uso del equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="22077-p130"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box. Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="22077-294">En **FQDN externos**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="22077-295">Si, en **Seleccionar características** decidió usar un FQDN único y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba el FQDN externo en **Acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="22077-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="22077-p131">Si selecciona esta opción, debe especificar un número de puerto distinto para cada uno de los servicios perimetrales (configuración de puertos recomendada: 5061 para el servicio perimetral de acceso, 444 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Al seleccionar esta opción, se evitan posibles problemas de conectividad y se simplifica la configuración, ya que se puede usar el mismo número de puerto (por ejemplo, 443) para los tres servicios.</span><span class="sxs-lookup"><span data-stu-id="22077-p131">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="22077-p132">Si, en **Seleccionar características**, no eligió la opción de usar un solo FQDN y una dirección IP, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales en **Acceso SIP**. En **Conferencia web**, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. En **Audio/Vídeo**, escriba el nombre de dominio completo que haya elegido para el lado de cara al público del grupo de servidores perimetrales. Use los puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="22077-p132">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="22077-302">Serán los nombres de dominio completos de IP virtual (VIP) de cara al público del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="22077-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="22077-303">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-303">Click **Next**.</span></span>

11. <span data-ttu-id="22077-304">En **Definir los equipos de este grupo**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="22077-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="22077-305">En **Definir las direcciones IP externas**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="22077-306">Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv4 externa del servidor perimetral en **acceso SIP**. dirección IP externa del servidor perimetral en **acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="22077-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="22077-p133">Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP**. En **Conferencia web**, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V**, escriba la dirección IP que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-p133">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="22077-310">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-310">Click **Next**.</span></span>

14. <span data-ttu-id="22077-311">Si habilitó las direcciones IPv6, en **Definir las direcciones IP externas** haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22077-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="22077-312">Si decidió usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio perimetral A/V, escriba la dirección IPv6 externa del servidor perimetral en **Acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="22077-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="22077-p134">Si no eligió la opción de usar un solo FQDN y una dirección IP para el acceso SIP, el servicio de conferencia web y el servicio de conferencia A/V, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales para el **Acceso SIP**. En **Conferencia web**, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales. En **Conferencia A/V**, escriba la dirección IPv6 que haya elegido para el lado de cara al público de este servidor del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-p134">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-316">Si no eligió habilitar y asignar direcciones IPv6, no verá este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="22077-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="22077-317">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="22077-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-318">Verá el primer servidor perimetral que ha creado en el grupo de servidores en el cuadro de diálogo <STRONG>Definir los equipos de este grupo de servidores</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="22077-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="22077-319">En **Definir los equipos de este grupo de servidores**, haga clic en **Agregar** y repita los pasos 11 a 14 para el segundo servidor perimetral que desea agregar al grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="22077-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="22077-320">Después de repetir los pasos 11 a 14, haga clic en **Siguiente** en **Definir los equipos de este grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="22077-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-321">En ese momento, podrá ver ambos servidores perimetrales en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="22077-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="22077-p135">En **Definir el próximo salto**, en la lista **Grupo de servidores del próximo salto**, seleccione el nombre del grupo de servidores interno, que puede ser un grupo de servidores front-end o un grupo de servidores Standard Edition. O, si la implementación incluye un director, escriba el nombre del director. A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="22077-p135">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

19. <span data-ttu-id="22077-325">En **Asociar grupos front-end**, especifique uno o más grupos de servidores internos, que pueden incluir grupos de servidores front-end y servidores Standard Edition, para asociarlos a este servidor perimetral; para ello, seleccione los nombres de los grupos de servidores internos que usarán este servidor perimetral para comunicarse con los usuarios externos compatibles.</span><span class="sxs-lookup"><span data-stu-id="22077-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22077-p136">Solo se puede asociar un servidor perimetral único o un grupo de servidores perimetrales de carga equilibrada a cada grupo interno para el tráfico de A/V. Si ya ha asociado un grupo de servidores interno a un servidor perimetral o a un grupo de servidores perimetrales, aparecerá una advertencia para indicarle que el grupo de servidores interno ya está asociado a un servidor perimetral o a un grupo de servidores perimetrales. Si selecciona un grupo de servidores que ya está asociado a otro servidor perimetral, cambiará la asociación.</span><span class="sxs-lookup"><span data-stu-id="22077-p136">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="22077-329">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="22077-329">Click **Finish**.</span></span>

21. <span data-ttu-id="22077-330">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="22077-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

