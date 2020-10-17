---
title: 'Lync Server 2013: supervisión del rendimiento de la red'
description: 'Lync Server 2013: supervisión del rendimiento de la red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ead7e3f9001b06c783c9b22327581e795a20322
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549456"
---
# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="df231-103">Supervisión del rendimiento de la red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df231-103">Monitoring network performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df231-104">_**Última modificación del tema:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="df231-104">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="df231-105">Lync Server 2013 es una tecnología de comunicaciones en tiempo real que depende en gran medida de la red para habilitar la comunicación entre los usuarios, ya sea a través de la mensajería instantánea (mi), las llamadas de voz o la comunicación de vídeo.</span><span class="sxs-lookup"><span data-stu-id="df231-105">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="df231-106">Por lo tanto, es importante supervisar el rendimiento de la red de forma continua para ayudar a garantizar que la modalidad de comunicación elegida por un usuario ofrezca la mejor experiencia posible.</span><span class="sxs-lookup"><span data-stu-id="df231-106">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="df231-107">El rendimiento de la red se puede medir en dos niveles:</span><span class="sxs-lookup"><span data-stu-id="df231-107">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="df231-108">Rendimiento general de la **red**     Este nivel de rendimiento permitirá que una organización cree una vista de "gran tamaño" de la red y se implemente normalmente a través de sistemas de supervisión de red de terceros.</span><span class="sxs-lookup"><span data-stu-id="df231-108">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="df231-109">Estos sistemas recibirán datos de rendimiento y capacidad de los dispositivos de red remotos, como enrutadores y cambiados a través de la red, para permitir que los administradores determinen el estado de cualquier componente de red determinado en cualquier momento del día.</span><span class="sxs-lookup"><span data-stu-id="df231-109">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="df231-110">Rendimiento del servidor **individual**     Este nivel de medida de rendimiento se limita a un servidor específico y ayudará a los administradores a evaluar el rendimiento de la red de un servidor específico para ayudarle a solucionar un problema de rendimiento específico o para medir el rendimiento del servidor respectivo en un período determinado como parte de un proceso de planeación de capacidad.</span><span class="sxs-lookup"><span data-stu-id="df231-110">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="df231-111">Puede supervisar la red con las herramientas que se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="df231-111">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="df231-112">Herramientas para la supervisión general del rendimiento de la red</span><span class="sxs-lookup"><span data-stu-id="df231-112">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="df231-113">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="df231-113">System Center Operations Manager 2012</span></span>

<span data-ttu-id="df231-114">System Center Operations Manager proporciona administración de servicios de un extremo a otro que es fácil de personalizar y ampliar para los niveles de servicio mejorados en un entorno de ti.</span><span class="sxs-lookup"><span data-stu-id="df231-114">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="df231-115">Esto permite a las operaciones y a los equipos de administración de ti identificar y resolver los problemas que afectan al estado de los servicios de ti distribuidos.</span><span class="sxs-lookup"><span data-stu-id="df231-115">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="df231-116">La administración de servicios de un extremo a otro no se limita a los entornos basados en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df231-116">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="df231-117">La compatibilidad con los servicios web para la administración (WS-Management), el Protocolo simple de administración de redes (SNMP) y las soluciones de asociados permiten que los sistemas que no ejecutan sistemas operativos de Microsoft y hardware se incluyan en la supervisión de servicios de System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="df231-117">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="df231-118">System Center Operations Manager 2012 y soluciones de administración de redes de terceros</span><span class="sxs-lookup"><span data-stu-id="df231-118">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="df231-119">**Smarts**     de EMC Las soluciones de EMC para Operations Manager le ayudan a resolver rápidamente los problemas que afectan a los niveles de servicio en todo el.</span><span class="sxs-lookup"><span data-stu-id="df231-119">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="df231-120">Mediante el uso de soluciones de EMC para Operations Manager, puede administrar y monitorear toda su cadena de servicios de TI con una solución integrada y automatizada.</span><span class="sxs-lookup"><span data-stu-id="df231-120">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="df231-121">Puede identificar fácilmente las causas de origen de los problemas de rendimiento y disponibilidad y resolverlos con mayor rapidez, lo que reduce los efectos y los costos.</span><span class="sxs-lookup"><span data-stu-id="df231-121">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="df231-122">Entre las principales ventajas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="df231-122">Key benefits include the following:</span></span>

  - <span data-ttu-id="df231-123">La administración avanzada y fácil de usar se centra en proporcionar valor empresarial estratégico en lugar de ordenar y filtrar de forma manual las alertas confusas.</span><span class="sxs-lookup"><span data-stu-id="df231-123">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="df231-124">**Resolución**     más rápida Resolver los problemas de ti y responder a las necesidades del negocio más rápidamente, lo que reduce el efecto y el costo.</span><span class="sxs-lookup"><span data-stu-id="df231-124">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="df231-125">**Operaciones**     simplificadas Evite la complejidad de ti combinando varias herramientas, aplicaciones y terminales de administración.</span><span class="sxs-lookup"><span data-stu-id="df231-125">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="df231-126">Puede encontrar más información aquí:</span><span class="sxs-lookup"><span data-stu-id="df231-126">More information can be found here:</span></span>

[<span data-ttu-id="df231-127">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="df231-127">Microsoft System Center Operations Manager</span></span>](https://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="df231-128">Soluciones para Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="df231-128">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="df231-129">Soluciones de otros fabricantes</span><span class="sxs-lookup"><span data-stu-id="df231-129">Third-Party Solutions</span></span>

<span data-ttu-id="df231-130">**HP Network Management Center (anteriormente conocido como HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) ofrece una administración integrada de errores y rendimiento para mejorar la disponibilidad y el rendimiento de la red.</span><span class="sxs-lookup"><span data-stu-id="df231-130">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="df231-131">El centro de administración de redes forma parte de la solución de administración automatizada de redes de HP que unifica los errores, el rendimiento, la configuración y la administración de cambios.</span><span class="sxs-lookup"><span data-stu-id="df231-131">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="df231-132">**Productos de automatización y administración de redes de Cisco**     Para la empresa, Cisco tiene varios productos de administración disponibles, incluidos la solución de administración de LAN de CiscoWorks y el módulo de análisis de red de Cisco, para mejorar la eficiencia operativa y reducir el tiempo de inactividad de la red.</span><span class="sxs-lookup"><span data-stu-id="df231-132">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="df231-133">Para obtener información adicional sobre estos productos, consulte el sitio web de Cisco en [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html) .</span><span class="sxs-lookup"><span data-stu-id="df231-133">For additional data on these products, refer to the Cisco website at [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="df231-134">Protocolo simple de administración de redes (SNMP) Protocolo simple de administración de redes (SNMP) es un estándar de administración de redes que define una estrategia para administrar redes TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="df231-134">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="df231-135">SNMP permite capturar información de configuración y estado sobre la red y enviar la información a un equipo designado para la supervisión de eventos.</span><span class="sxs-lookup"><span data-stu-id="df231-135">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="df231-136">Este protocolo de administración de red basado en estándares usa una arquitectura distribuida que incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="df231-136">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="df231-137">Varios nodos administrados, cada uno con una entidad SNMP llamada un agente que proporciona acceso remoto a instrumental de administración.</span><span class="sxs-lookup"><span data-stu-id="df231-137">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="df231-138">Al menos una entidad SNMP conocida como administrador que ejecuta las aplicaciones de administración para supervisar y controlar los elementos administrados.</span><span class="sxs-lookup"><span data-stu-id="df231-138">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="df231-139">Los elementos administrados son dispositivos como hosts, enrutadores, etc.</span><span class="sxs-lookup"><span data-stu-id="df231-139">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="df231-140">Se supervisan y controlan mediante el acceso a su información de administración.</span><span class="sxs-lookup"><span data-stu-id="df231-140">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="df231-141">Se usa un protocolo de administración, SNMP, para comunicar la información de administración entre las estaciones de administración y los agentes.</span><span class="sxs-lookup"><span data-stu-id="df231-141">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="df231-142">La información de administración se refiere a una colección de objetos administrados que residen en un almacén de información virtual denominado base de datos de información de administración (MIB).</span><span class="sxs-lookup"><span data-stu-id="df231-142">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df231-143">A continuación se ofrecen ejemplos de soluciones de supervisión de red de terceros.</span><span class="sxs-lookup"><span data-stu-id="df231-143">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="df231-144">Esta lista no es definitiva y Microsoft no favorece a ninguna solución de proveedor específica.</span><span class="sxs-lookup"><span data-stu-id="df231-144">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="df231-145">Consulte a un proveedor de servicios de red o a su proveedor de tecnología respectivo para determinar la mejor solución de supervisión de red para su organización.</span><span class="sxs-lookup"><span data-stu-id="df231-145">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="df231-146">Herramientas para supervisar el rendimiento de una red de servidor individual</span><span class="sxs-lookup"><span data-stu-id="df231-146">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="df231-147">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="df231-147">System Center Operations Manager 2012</span></span>

<span data-ttu-id="df231-148">System Center Operations Manager 2012 permitiría a los administradores ver el rendimiento de red de servidores individuales a través del módulo de administración de Windows Server 2012: el módulo de administración del sistema operativo Windows Server incluye un módulo de administración de "rendimiento" que permite que los administradores supervisen el rendimiento del adaptador de red y el estado del adaptador.</span><span class="sxs-lookup"><span data-stu-id="df231-148">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="df231-149">Monitor de red de Windows</span><span class="sxs-lookup"><span data-stu-id="df231-149">Windows Network Monitor</span></span>

<span data-ttu-id="df231-150">Recopila, muestra, analiza el uso de recursos en un servidor y mide el tráfico de red.</span><span class="sxs-lookup"><span data-stu-id="df231-150">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="df231-151">Monitor de red supervisa exclusivamente la actividad de la red.</span><span class="sxs-lookup"><span data-stu-id="df231-151">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="df231-152">Al capturar y analizar datos de red y usar estos datos con registros de rendimiento, puede determinar el uso de la red, identificar problemas de red y prever las necesidades futuras de la red.</span><span class="sxs-lookup"><span data-stu-id="df231-152">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="df231-153">Para obtener más información acerca del monitor de red 3,4 y para saber cómo instalar y configurar el monitor de red, y capturar y analizar datos, revise esta sesión: Introducción al monitor de red 3,3.</span><span class="sxs-lookup"><span data-stu-id="df231-153">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="df231-154">Además, revise el [blog del monitor de red](https://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="df231-154">Also, review the [Network Monitor blog](https://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

