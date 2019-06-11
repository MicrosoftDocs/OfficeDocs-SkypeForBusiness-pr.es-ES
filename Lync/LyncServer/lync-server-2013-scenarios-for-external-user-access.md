---
title: 'Lync Server 2013: Escenarios para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e4f7410d7038971c6ddefe1af1c7b3ecd97ab9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="8b167-102">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b167-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b167-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8b167-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8b167-104">Para proporcionar acceso a usuarios externos para Lync Server 2013, debe implementar al menos un servidor perimetral y un proxy inverso en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="8b167-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="8b167-105">De manera opcional, puede implementar un director o un grupo de directores en su red interna.</span><span class="sxs-lookup"><span data-stu-id="8b167-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="8b167-106">Si necesita una mayor capacidad de la que un solo servidor perimetral puede proporcionar, o si necesita una alta disponibilidad para la implementación de su servidor perimetral, puede configurar el equilibrio de carga e implementar varios servidores perimetrales en un grupo de carga equilibrada.</span><span class="sxs-lookup"><span data-stu-id="8b167-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="8b167-107">Si su organización tiene varios centros de datos, puede tener implementaciones de servidores perimetrales o de conjuntos de límites en más de una ubicación.</span><span class="sxs-lookup"><span data-stu-id="8b167-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="8b167-108">Sin embargo, solo se puede designar una de las implementaciones de servidor perimetral como la ruta de Federación.</span><span class="sxs-lookup"><span data-stu-id="8b167-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="8b167-109">En esta sección se definen los escenarios para las implementaciones de servidores perimetrales y se asignan las secciones de planeación a los posibles escenarios.</span><span class="sxs-lookup"><span data-stu-id="8b167-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="8b167-110">Por ejemplo, si su implementación requiere alta disponibilidad, Federación con contactos de presencia y mensajería extensible (XMPP) y movilidad de Lync, debe seleccionar las entradas coincidentes de la siguiente tabla que cumplan estos requisitos y usar el se hace referencia a las secciones de planeación para definir la implementación, como se muestra en el siguiente diagrama de flujo.</span><span class="sxs-lookup"><span data-stu-id="8b167-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="8b167-111">**Proceso de selección del escenario de implementación del servidor perimetral**</span><span class="sxs-lookup"><span data-stu-id="8b167-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="8b167-112">![Diagrama de flujo de implementación de ejemplo] (images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Diagrama de flujo de implementación de ejemplo")</span><span class="sxs-lookup"><span data-stu-id="8b167-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="8b167-113">Mediante este proceso, puede planear y documentar la configuración de todas las características potenciales que desea implementar para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="8b167-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="8b167-114">Sin embargo, puede agregar servicios de Federación y movilidad después de haber implementado el servidor perimetral y haber confirmado la operación correcta antes de agregar otras características.</span><span class="sxs-lookup"><span data-stu-id="8b167-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="8b167-115">El proceso de agregar características a una implementación existente de un servidor perimetral se trata en la sección implementación.</span><span class="sxs-lookup"><span data-stu-id="8b167-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="8b167-116">Para obtener más información sobre la implementación, consulte [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) incluyendo la planificación de estas características durante el proceso de planeación inicial, puede prepararse para los requisitos de DNS, Firewall y certificados para las características agregadas. lo que le permite adquirir los certificados y configurar DNS y los requisitos de puerto y Protocolo por adelantado.</span><span class="sxs-lookup"><span data-stu-id="8b167-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="8b167-117">Si planea instalar los servidores perimetrales y el proxy inverso y agregar características más adelante (por ejemplo, Federación y movilidad), determine qué certificados necesitará para todos los servicios después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="8b167-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="8b167-118">Planear y adquirir certificados para todas las características de antemano, inicialmente implementadas o no, evita tener que pedir certificados nuevos para cumplir los requisitos de Federación (es decir, en los servidores perimetrales) o el proxy inverso (es decir, para la movilidad). servicios).</span><span class="sxs-lookup"><span data-stu-id="8b167-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8b167-119">Todos los servicios de Edge se ejecutan en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="8b167-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="8b167-120">Los servicios no se pueden dividir entre dos servidores perimetrales diferentes.</span><span class="sxs-lookup"><span data-stu-id="8b167-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="8b167-121">Si implementa un grupo perimetral para escalabilidad, todos los servicios perimetrales se implementan en cada servidor perimetral en el grupo.</span><span class="sxs-lookup"><span data-stu-id="8b167-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="8b167-122">La Federación de XMPP, Office Communications Server y Lync Server, la conectividad de mensajería instantánea pública y la movilidad de clientes son servicios adicionales que se pueden implementar después de implementar el primer servidor perimetral o el grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="8b167-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="8b167-123">Mobility Services es una característica que usa el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="8b167-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="8b167-124">La instalación de Mobility Services no agregará características a los servidores perimetrales, pero requerirá la reconfiguración de su proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="8b167-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="8b167-125">La columna <STRONG>objetivo de instalación</STRONG> que contiene estas características proporciona instrucciones de planeación en la columna asociada de la sección de planeación del <STRONG>servidor EDGE o secciones</STRONG> para planear de forma simultánea estas características que se implementarán cuando los servidores perimetrales estén instalado y configurado.</span><span class="sxs-lookup"><span data-stu-id="8b167-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="8b167-126">Identificar y asignar los objetivos de implementación</span><span class="sxs-lookup"><span data-stu-id="8b167-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b167-127">Objetivo de instalación</span><span class="sxs-lookup"><span data-stu-id="8b167-127">Installation goal</span></span></th>
<th><span data-ttu-id="8b167-128">Documentación de planeación del servidor EDGE</span><span class="sxs-lookup"><span data-stu-id="8b167-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b167-129">Ha decidido que un solo servidor es suficiente para los servicios de vanguardia de su infraestructura.</span><span class="sxs-lookup"><span data-stu-id="8b167-129">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="8b167-130">También desea usar direcciones IP privadas para las interfaces externas de servidor perimetral con NAT a Internet.</span><span class="sxs-lookup"><span data-stu-id="8b167-130">You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="8b167-131">Use esta sección de planificación si va a implementar un único servidor perimetral en su perímetro.</span><span class="sxs-lookup"><span data-stu-id="8b167-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="8b167-132">Implementará un servidor perimetral con direcciones IP privadas asignadas al servidor perimetral y usará NAT para proporcionar las direcciones IP públicas de los usuarios externos en Internet.</span><span class="sxs-lookup"><span data-stu-id="8b167-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="8b167-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Servidor perimetral consolidado simple con direcciones IP privadas y NAT en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8b167-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b167-134">Ha decidido que un solo servidor es suficiente para los servicios de vanguardia de su infraestructura.</span><span class="sxs-lookup"><span data-stu-id="8b167-134">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="8b167-135">También desea usar direcciones IP públicas para las interfaces externas de servidor perimetral a Internet.</span><span class="sxs-lookup"><span data-stu-id="8b167-135">You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="8b167-136">Use esta sección de planificación si va a implementar un único servidor perimetral en su perímetro.</span><span class="sxs-lookup"><span data-stu-id="8b167-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="8b167-137">Implementará un servidor perimetral con direcciones IP públicas asignadas al servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="8b167-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="8b167-138">En lugar de NAT, usará el enrutamiento en este escenario.</span><span class="sxs-lookup"><span data-stu-id="8b167-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="8b167-139">La dirección IP pública real del servidor perimetral está disponible para las conexiones de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="8b167-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="8b167-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Topología perimetral consolidada de un solo equipo con direcciones IP públicas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8b167-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b167-141">Ha decidido que la alta disponibilidad de los servicios perimetrales es importante para sus usuarios y que va a implementar dos o más servidores perimetrales en este grupo.</span><span class="sxs-lookup"><span data-stu-id="8b167-141">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="8b167-142">También desea usar direcciones IP privadas para las interfaces externas de servidor perimetral con NAT a Internet.</span><span class="sxs-lookup"><span data-stu-id="8b167-142">You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="8b167-143">Use esta sección de planificación si está implementando un grupo de servidores perimetrales en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="8b167-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="8b167-144">Implementará los servidores perimetrales con direcciones IP privadas asignadas al servidor perimetral, usando el equilibrio de carga de DNS para distribuir la comunicación en el grupo.</span><span class="sxs-lookup"><span data-stu-id="8b167-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="8b167-145">Usará NAT para proporcionar las direcciones IP públicas para los usuarios externos en Internet.</span><span class="sxs-lookup"><span data-stu-id="8b167-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="8b167-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8b167-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b167-147">Ha decidido que la alta disponibilidad de los servicios perimetrales es importante para sus usuarios y que va a implementar dos o más servidores perimetrales en este grupo.</span><span class="sxs-lookup"><span data-stu-id="8b167-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="8b167-148">También desea usar direcciones IP públicas para las interfaces externas de servidor perimetral a Internet.</span><span class="sxs-lookup"><span data-stu-id="8b167-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="8b167-149">Use esta sección de planificación si está implementando un grupo de servidores perimetrales en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="8b167-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="8b167-150">Implementará los servidores perimetrales con direcciones IP públicas asignadas al servidor perimetral, usando el equilibrio de carga de DNS para distribuir la comunicación en el grupo.</span><span class="sxs-lookup"><span data-stu-id="8b167-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="8b167-151">En lugar de NAT, usará el enrutamiento para proporcionar las direcciones IP públicas de los usuarios externos en Internet.</span><span class="sxs-lookup"><span data-stu-id="8b167-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="8b167-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Perímetro consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8b167-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b167-153">Ha decidido que la alta disponibilidad de los servicios perimetrales es importante para sus usuarios y que va a implementar dos o más servidores perimetrales en este grupo con un equilibrador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="8b167-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="8b167-154">Use esta sección de planificación si está implementando un grupo de servidores perimetrales en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="8b167-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="8b167-155">Implementará los servidores perimetrales con direcciones IP públicas asignadas al servidor perimetral, con equilibradores de carga de hardware para distribuir la comunicación en el grupo.</span><span class="sxs-lookup"><span data-stu-id="8b167-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="8b167-156">En lugar de NAT, usará el enrutamiento para proporcionar las direcciones IP públicas de los usuarios externos en Internet.</span><span class="sxs-lookup"><span data-stu-id="8b167-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="8b167-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8b167-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b167-158">Los escenarios de Federación le permiten planear la característica que extenderá los tipos de socios con los que se pueden comunicar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8b167-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="8b167-159">Federación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b167-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="8b167-160">Federación de Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="8b167-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="8b167-161">Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="8b167-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="8b167-162">Federación XMPP</span><span class="sxs-lookup"><span data-stu-id="8b167-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8b167-163">Planeamiento de escenarios de Federación</span><span class="sxs-lookup"><span data-stu-id="8b167-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="8b167-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planificación de la Federación de Lync Server 2013 y Office Communications Server</a></span><span class="sxs-lookup"><span data-stu-id="8b167-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="8b167-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planeamiento de la conectividad de mensajería instantánea pública en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8b167-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="8b167-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planeamiento de la Federación de protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8b167-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b167-167">Los servicios de movilidad se ofrecen a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="8b167-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="8b167-168">Los servicios que permiten la movilidad para los usuarios externos se implementan en el servidor front-end o en el grupo front-end.</span><span class="sxs-lookup"><span data-stu-id="8b167-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="8b167-169">Puede crear o modificar las reglas de publicación existentes en el proxy inverso para habilitar los servicios de movilidad para los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="8b167-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="8b167-170"><a href="lync-server-2013-planning-for-mobility.md">Planeación de movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8b167-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="8b167-171">En las siguientes secciones, se incluyen arquitecturas de referencia, DNS de ejemplo, definiciones de puerto y Protocolo, y requisitos de certificado.</span><span class="sxs-lookup"><span data-stu-id="8b167-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="8b167-172">También se incluyen diagramas de su DNS, definiciones de puertos y puertos, y necesidades de certificados.</span><span class="sxs-lookup"><span data-stu-id="8b167-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="8b167-173">Los diagramas proporcionarán una plantilla que le permitirá rellenar y distribuir a otros equipos (por ejemplo, el equipo de red de su organización, el equipo de infraestructura de clave pública y el equipo de implementación de servidores).</span><span class="sxs-lookup"><span data-stu-id="8b167-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="8b167-174">El objetivo de los diagramas es mejorar la comunicación y garantizar el éxito al comunicar los elementos de configuración del servidor perimetral requeridos a las personas que realizarán el trabajo de configuración real.</span><span class="sxs-lookup"><span data-stu-id="8b167-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="8b167-175">Le recomendamos que use los diagramas y las arquitecturas de referencia asociadas para planificar su implementación.</span><span class="sxs-lookup"><span data-stu-id="8b167-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

