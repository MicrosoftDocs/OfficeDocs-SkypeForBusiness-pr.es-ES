---
title: 'Lync Server 2013: escenarios para el acceso de usuarios externos'
description: 'Lync Server 2013: escenarios para el acceso de usuarios externos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b212d371d5a87470fc3d849f185bb5c8659ce05
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547646"
---
# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="312b9-103">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312b9-103">Scenarios for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="312b9-104">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="312b9-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="312b9-105">Para permitir el acceso de usuarios externos para Lync Server 2013, es necesario que implemente al menos un servidor perimetral y un proxy inverso en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="312b9-105">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="312b9-106">Opcionalmente, puede implementar un director o un grupo de directores en su red interna.</span><span class="sxs-lookup"><span data-stu-id="312b9-106">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="312b9-107">Si necesita una capacidad mayor a la que un solo servidor perimetral puede proporcionar, o si necesita una alta disponibilidad para la implementación del servidor perimetral, puede configurar el equilibrio de carga e implementar varios servidores perimetrales en un grupo de carga equilibrada.</span><span class="sxs-lookup"><span data-stu-id="312b9-107">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="312b9-108">Si su organización tiene varios centros de datos, puede tener implementaciones del servidor perimetral o del grupo de servidores perimetrales en más de una ubicación.</span><span class="sxs-lookup"><span data-stu-id="312b9-108">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="312b9-109">Sin embargo, solo una de las implementaciones del servidor perimetral se puede designar como la ruta de Federación.</span><span class="sxs-lookup"><span data-stu-id="312b9-109">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="312b9-110">En esta sección se definen los escenarios para las implementaciones del servidor perimetral y se asignan las secciones de planeación a los escenarios posibles.</span><span class="sxs-lookup"><span data-stu-id="312b9-110">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="312b9-111">Por ejemplo, si la implementación requiere alta disponibilidad, Federación con contactos extensibles de mensajería y presencia (XMPP) y movilidad de Lync, debe seleccionar las entradas coincidentes de la siguiente tabla que satisfarían estos requisitos y usar las secciones de planeación a las que se hace referencia para definir la implementación, como se muestra en el siguiente diagrama de flujo.</span><span class="sxs-lookup"><span data-stu-id="312b9-111">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="312b9-112">**Proceso de selección del escenario de implementación del servidor perimetral**</span><span class="sxs-lookup"><span data-stu-id="312b9-112">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="312b9-113">![Diagrama de flujo de implementación de ejemplo](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Diagrama de flujo de implementación de ejemplo")</span><span class="sxs-lookup"><span data-stu-id="312b9-113">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="312b9-114">Mediante este proceso, puede planear y documentar la configuración de todas las características potenciales que desea implementar para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="312b9-114">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="312b9-115">Sin embargo, puede agregar servicios de Federación y de movilidad después de implementar el servidor perimetral y haber confirmado la operación correcta antes de agregar otras características.</span><span class="sxs-lookup"><span data-stu-id="312b9-115">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="312b9-116">En la sección implementación se describe el proceso de agregar características a una implementación de servidor perimetral existente.</span><span class="sxs-lookup"><span data-stu-id="312b9-116">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="312b9-117">Para obtener información detallada sobre la implementación, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) al incluir la planeación de estas características durante el proceso de planeación inicial, puede preparar los requisitos de DNS, Firewall y certificado para las características agregadas, lo que le permite adquirir los certificados y configurar los requisitos de protocolo y Puerto DNS con antelación.</span><span class="sxs-lookup"><span data-stu-id="312b9-117">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="312b9-118">Si tiene previsto instalar los servidores perimetrales y el proxy inverso y, a continuación, agregar características más adelante (por ejemplo, Federación y movilidad), determine qué certificados necesitará para todos los servicios después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="312b9-118">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="312b9-119">La planeación y adquisición de los certificados para todas las características de antemano, implementadas inicialmente o no, le evita tener que pedir nuevos certificados para satisfacer los requisitos de la Federación (es decir, en los servidores perimetrales) o el proxy inverso (es decir, para los servicios de movilidad).</span><span class="sxs-lookup"><span data-stu-id="312b9-119">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="312b9-120">Todos los servicios perimetrales se ejecutan en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="312b9-120">All edge services run on each Edge Server.</span></span> <span data-ttu-id="312b9-121">Los servicios no se pueden dividir entre dos servidores perimetrales diferentes.</span><span class="sxs-lookup"><span data-stu-id="312b9-121">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="312b9-122">Si implementa un grupo de servidores perimetrales para la escalabilidad, todos los servicios perimetrales se implementan en cada servidor perimetral del grupo.</span><span class="sxs-lookup"><span data-stu-id="312b9-122">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="312b9-123">La Federación de XMPP, Office Communications Server y Lync Server, la conectividad de mensajería instantánea pública y la movilidad de clientes son servicios adicionales que se pueden implementar una vez que se ha implementado el primer servidor perimetral o el grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="312b9-123">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="312b9-124">Los servicios de movilidad son una función que utiliza el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="312b9-124">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="312b9-125">La instalación de los servicios de movilidad no agregará características a los servidores perimetrales, pero será necesario volver a configurar el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="312b9-125">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="312b9-126">La columna de <STRONG>objetivo de instalación</STRONG> que enumera estas características proporciona instrucciones de planeación en la columna asociada de la <STRONG>sección planeación del servidor perimetral o en secciones</STRONG> para planear de forma simultánea estas características que se van a implementar al instalar y configurar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="312b9-126">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="312b9-127">Identificación y asignación de los objetivos de implementación</span><span class="sxs-lookup"><span data-stu-id="312b9-127">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="312b9-128">Objetivo de instalación</span><span class="sxs-lookup"><span data-stu-id="312b9-128">Installation goal</span></span></th>
<th><span data-ttu-id="312b9-129">Documentación de planificación del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="312b9-129">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="312b9-p107">Ha decidido que un único servidor es suficiente para los servicios perimetrales en la infraestructura. También desea utilizar direcciones de IP privadas para las interfaces externas del servidor perimetral con NAT a internet.</span><span class="sxs-lookup"><span data-stu-id="312b9-p107">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="312b9-132">Use esta sección de planeación si va a implementar un solo servidor perimetral en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="312b9-132">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="312b9-133">Implementará un servidor perimetral con direcciones IP privadas asignadas al servidor perimetral y usará NAT para proporcionar las direcciones IP públicas para los usuarios externos en Internet.</span><span class="sxs-lookup"><span data-stu-id="312b9-133">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="312b9-134"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Servidor perimetral consolidado único con direcciones IP privadas y NAT en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="312b9-134"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="312b9-p109">Ha decidido que un único servidor es suficiente para los servicios perimetrales en la infraestructura. También desea utilizar direcciones de IP públicas para las interfaces externas del servidor perimetral en internet.</span><span class="sxs-lookup"><span data-stu-id="312b9-p109">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="312b9-137">Use esta sección de planeación si va a implementar un solo servidor perimetral en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="312b9-137">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="312b9-138">Implementará un servidor perimetral con direcciones IP públicas asignadas al servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="312b9-138">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="312b9-139">En este escenario, se utiliza el enrutamiento en lugar de NAT.</span><span class="sxs-lookup"><span data-stu-id="312b9-139">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="312b9-140">La dirección IP pública real del servidor perimetral está disponible para las conexiones de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="312b9-140">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="312b9-141"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="312b9-141"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="312b9-p111">Ha decidido que la disponibilidad alta de los servicios perimetrales es importante para los usuarios e implementará dos o más servidores perimetrales en este grupo de servidores. También desea utilizar direcciones IP privadas para las interfaces externas del servidor perimetral con NAT a internet.</span><span class="sxs-lookup"><span data-stu-id="312b9-p111">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool. You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="312b9-144">Use esta sección de planeación si va a implementar un grupo de servidores perimetrales en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="312b9-144">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="312b9-145">Implementará los servidores perimetrales con direcciones IP privadas asignadas al servidor perimetral mediante el equilibrio de carga de DNS para distribuir la comunicación en el grupo.</span><span class="sxs-lookup"><span data-stu-id="312b9-145">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="312b9-146">Se utilizará NAT para proporcionar las direcciones IP públicas para los usuarios externos en internet.</span><span class="sxs-lookup"><span data-stu-id="312b9-146">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="312b9-147"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="312b9-147"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="312b9-148">Ha decidido que la disponibilidad alta de los servicios perimetrales es importante para los usuarios e implementará dos o más servidores perimetrales en este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="312b9-148">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="312b9-149">También tiene previsto usar direcciones IP públicas para las interfaces externas del servidor perimetral a Internet.</span><span class="sxs-lookup"><span data-stu-id="312b9-149">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="312b9-150">Use esta sección de planeación si va a implementar un grupo de servidores perimetrales en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="312b9-150">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="312b9-151">Implementará los servidores perimetrales con direcciones IP públicas asignadas al servidor perimetral mediante el equilibrio de carga de DNS para distribuir la comunicación en el grupo.</span><span class="sxs-lookup"><span data-stu-id="312b9-151">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="312b9-152">Se utilizará el enrutamiento en lugar de NAT para proporcionar las direcciones IP públicas para los usuarios externos en internet.</span><span class="sxs-lookup"><span data-stu-id="312b9-152">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="312b9-153"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Servidor perimetral consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="312b9-153"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="312b9-154">Ha decidido que la alta disponibilidad de los servicios perimetrales es importante para los usuarios e implementará dos o más servidores perimetrales en este grupo mediante un equilibrador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="312b9-154">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="312b9-155">Use esta sección de planeación si va a implementar un grupo de servidores perimetrales en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="312b9-155">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="312b9-156">Implementará los servidores perimetrales con direcciones IP públicas asignadas al servidor perimetral, mediante equilibradores de carga de hardware para distribuir la comunicación en el grupo.</span><span class="sxs-lookup"><span data-stu-id="312b9-156">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="312b9-157">Se utilizará el enrutamiento en lugar de NAT para proporcionar las direcciones IP públicas para los usuarios externos en internet.</span><span class="sxs-lookup"><span data-stu-id="312b9-157">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="312b9-158"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="312b9-158"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="312b9-159">Los escenarios de federación permiten planificar la función que ampliará los tipos de socios con los que pueden comunicarse los usuarios.</span><span class="sxs-lookup"><span data-stu-id="312b9-159">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="312b9-160">Federación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="312b9-160">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="312b9-161">Federación de Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="312b9-161">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="312b9-162">Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="312b9-162">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="312b9-163">Federación XMPP</span><span class="sxs-lookup"><span data-stu-id="312b9-163">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="312b9-164">Planificación de escenarios de federación</span><span class="sxs-lookup"><span data-stu-id="312b9-164">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="312b9-165"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planeación de la Federación de Lync Server 2013 y Office Communications Server</a></span><span class="sxs-lookup"><span data-stu-id="312b9-165"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="312b9-166"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planeación de la conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="312b9-166"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="312b9-167"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planeación de la Federación de protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="312b9-167"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="312b9-168">Los servicios de movilidad se ofrecen a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="312b9-168">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="312b9-169">Los servicios que habilitan la movilidad para los usuarios externos se implementan en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="312b9-169">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="312b9-170">Para habilitar los servicios de movilidad para los usuarios externos, crea o modifica las reglas de publicación existentes en el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="312b9-170">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="312b9-171"><a href="lync-server-2013-planning-for-mobility.md">Planeación de movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="312b9-171"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="312b9-172">En las siguientes secciones Escenarios hay arquitecturas de referencia, DNS de ejemplo, definiciones de puerto/protocolo y requisitos de certificados.</span><span class="sxs-lookup"><span data-stu-id="312b9-172">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="312b9-173">También se incluyen diagramas del DNS, las definiciones de puerto/protocolo y los requisitos de certificados.</span><span class="sxs-lookup"><span data-stu-id="312b9-173">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="312b9-174">Los diagramas proporcionarán una plantilla para que complete y distribuya a otros equipos (por ejemplo, el equipo de redes de su organización, el equipo de infraestructura de clave pública y el equipo de implementación del servidor).</span><span class="sxs-lookup"><span data-stu-id="312b9-174">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="312b9-175">El objetivo de los diagramas es mejorar la comunicación y garantizar el éxito al comunicar los elementos de configuración del servidor perimetral necesario a las personas que van a realizar el trabajo de configuración real.</span><span class="sxs-lookup"><span data-stu-id="312b9-175">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="312b9-176">Se recomienda el uso de los diagramas y de la arquitectura de referencia asociada para planificar la implementación.</span><span class="sxs-lookup"><span data-stu-id="312b9-176">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

