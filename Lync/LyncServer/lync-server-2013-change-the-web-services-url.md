---
title: 'Lync Server 2013: cambiar la dirección URL de los servicios Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 872f971537205826a8927b77563476181f3001c4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="76dac-102">Cambiar la dirección URL de los servicios web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76dac-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76dac-103">_**Última modificación del tema:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="76dac-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="76dac-104">Cuando configura los grupos de servidores front-end y los servidores Standard Edition, tiene la opción de configurar un nombre de dominio completo (FQDN) de la granja de servidores web externa y los puertos asociados.</span><span class="sxs-lookup"><span data-stu-id="76dac-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="76dac-105">Si no configuró esta dirección URL cuando ejecutó el Asistente para la implementación de Lync Server, tendrá que configurar estas opciones de forma manual.</span><span class="sxs-lookup"><span data-stu-id="76dac-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="76dac-106">Un administrador no suele necesitar modificar estos parámetros, ya que son los puertos predeterminados y recomendados.</span><span class="sxs-lookup"><span data-stu-id="76dac-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76dac-107">La siguiente captura de pantalla se realizó al configurar un servidor Standard Edition, por lo que la opción reemplazar FQDN está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="76dac-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="76dac-108">Esta opción está habilitada al configurar un servidor Enterprise Edition en un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="76dac-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="76dac-109">![Edición de la configuración del grupo de servicios Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edición de la configuración del grupo de servicios Web")</span><span class="sxs-lookup"><span data-stu-id="76dac-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="76dac-110">Para configurar los servicios Web</span><span class="sxs-lookup"><span data-stu-id="76dac-110">To configure web services</span></span>

1.  <span data-ttu-id="76dac-111">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="76dac-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="76dac-112">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="76dac-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="76dac-113">En el generador de topologías, en el árbol de la consola, en **servidores front-end Standard Edition**, **grupos de servidores front-end Enterprise Edition**y **grupos de directorios**, seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="76dac-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="76dac-114">Haga clic con el botón secundario en el nombre, seleccione **Editar propiedades** y después haga clic en **Servicios web**.</span><span class="sxs-lookup"><span data-stu-id="76dac-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="76dac-115">Agregue o edite el **FQDN de servicios web externos** y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="76dac-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="76dac-116">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="76dac-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="76dac-117">Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como <STRONG>pool01.contoso.com</STRONG>, no puede usar <STRONG>pool01.contoso.com</STRONG> para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="76dac-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="76dac-118">Si también está implementando directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="76dac-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="76dac-119">Verifique que los puertos de escucha y los puertos publicados están configurados correctamente para su entorno.</span><span class="sxs-lookup"><span data-stu-id="76dac-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="76dac-120">Repita estos pasos para todos los servidores Standard Edition, los grupos de servidores front-end y los grupos de servidores de Active Directory de su entorno.</span><span class="sxs-lookup"><span data-stu-id="76dac-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="76dac-121">En el árbol de la consola, haga clic en **Lync Server 2013** y después en el panel **Acciones**, haga clic en **Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="76dac-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="76dac-122">A continuación se enumeran algunos requisitos que es necesario conocer a la hora de configurar los puertos de escucha y publicación.</span><span class="sxs-lookup"><span data-stu-id="76dac-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="76dac-123">Los puertos de escucha que se muestran son los puertos configurados para Internet Information Server (IIS) en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="76dac-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="76dac-p105">Los puertos de escucha internos y externos deben ser diferentes para IIS. En el caso de los puertos de escucha externos, suele tratarse del mismo puerto, ya que uno representa el equilibrador de carga de hardware para el tráfico web interno y otro representa el servidor proxy inverso para el tráfico web externo.</span><span class="sxs-lookup"><span data-stu-id="76dac-p105">The internal and external listening ports must be different for IIS. For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="76dac-126">Puede invalidar los servicios Web internos en un grupo de servidores front-end, en un director o en un grupo de directores y definir su propio FQDN.</span><span class="sxs-lookup"><span data-stu-id="76dac-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="76dac-127">Si decide reemplazar los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único en cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="76dac-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="76dac-128">Los puertos publicados deben configurarse como puertos de escucha en el servidor proxy inverso o el equilibrador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="76dac-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="76dac-p106">En el caso de un grupo de servidores front-end (que no aparecen en el ejemplo), el FQDN del grupo de servidores SIP interno debe ser diferente al FQDN de servicios web internos, ya que el tráfico web viaja a través del equilibrador de carga de hardware, mientras que el tráfico del grupo de servidores SIP interno viaja a través el equilibrador de carga de DNS. Este requisito se debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="76dac-p106">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer. This requirement must be met.</span></span>

  - <span data-ttu-id="76dac-131">Una implementación de Lync Server Standard Edition no necesita ni permitir que se invalide un FQDN de servicios Web interno porque no se puede equilibrar la carga de este servidor.</span><span class="sxs-lookup"><span data-stu-id="76dac-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="76dac-132">Si tiene un equilibrador de carga de hardware en su entorno que se usa para el tráfico SIP y Web interno, el generador de topologías no puede hacer la distinción.</span><span class="sxs-lookup"><span data-stu-id="76dac-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="76dac-133">Los FQDN de servicio Web deben diferenciarse fácilmente entre sí; Esto ayuda a garantizar que los clientes apunten a los clientes hacia el servidor adecuado.</span><span class="sxs-lookup"><span data-stu-id="76dac-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="76dac-134">Por ejemplo, si tiene dos FQDN, podría considerar la posibilidad de asignar un nombre a un meeting.contoso.com y el otro conferencing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="76dac-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="76dac-135">Podría tener problemas de redirección si tiene FQDN con nombres más similares, como meet1.contoso.com y meet2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="76dac-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="76dac-136">Los servicios web externos trabajan en combinación con un proxy inverso en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="76dac-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="76dac-137">Proporciona a los clientes acceso externo a con estos servicios Web.</span><span class="sxs-lookup"><span data-stu-id="76dac-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="76dac-138">Los FQDN configurados aquí se envían a los clientes cuando inician sesión y se usan para hacer una conexión HTTPS con el proxy inverso en conexiones remotas.</span><span class="sxs-lookup"><span data-stu-id="76dac-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="76dac-139">El servidor proxy inverso reenvía el FQDN de servicios web externo a un equilibrador de carga de hardware, o directamente al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="76dac-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="76dac-140">El proxy inverso debe poder resolver el FQDN de servicios web externos en la dirección IP del servidor web interno.</span><span class="sxs-lookup"><span data-stu-id="76dac-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="76dac-141">El FDQN de servicios web externos debe poder resolverse en Internet.</span><span class="sxs-lookup"><span data-stu-id="76dac-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="76dac-142">Si el servidor interno es un servidor Standard Edition, el FQDN interno es el FQDN del servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="76dac-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="76dac-143">Si el servidor interno es un grupo de servidores front-end, el FQDN es una IP virtual (VIP) de equilibrador de carga de hardware que equilibra la carga de la granja de servidores web internos.</span><span class="sxs-lookup"><span data-stu-id="76dac-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="76dac-144">Es necesario un equilibrador de carga de hardware en un grupo de servidores front-end con varios servidores Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="76dac-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="76dac-145">No se requiere un equilibrador de carga para un servidor Standard Edition o un solo servidor front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="76dac-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

