---
title: 'Lync Server 2013: supervisar el rendimiento de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="008ac-102">Supervisar el rendimiento de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="008ac-102">Monitoring network performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="008ac-103">_**Última modificación del tema:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="008ac-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="008ac-104">Lync Server 2013 es una tecnología de comunicaciones en tiempo real que depende principalmente de la red para habilitar la comunicación entre los usuarios, ya sea a través de la mensajería instantánea (mi), las llamadas de voz o la comunicación de vídeo.</span><span class="sxs-lookup"><span data-stu-id="008ac-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="008ac-105">Por lo tanto, es importante supervisar el rendimiento de la red continuamente para ayudar a garantizar que la modalidad de comunicación elegida por un usuario ofrezca la mejor experiencia posible.</span><span class="sxs-lookup"><span data-stu-id="008ac-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="008ac-106">El rendimiento de la red puede medirse a dos niveles:</span><span class="sxs-lookup"><span data-stu-id="008ac-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="008ac-107">**Rendimiento general de la red**   este nivel de rendimiento permite a una organización crear una vista de "panorama general" de su red y suele implementarse a través de sistemas de supervisión de redes de terceros.</span><span class="sxs-lookup"><span data-stu-id="008ac-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="008ac-108">Estos sistemas recibirán datos de rendimiento y capacidad de los dispositivos de red remotos, como los enrutadores y se han cambiado por la red, lo que permite a los administradores determinar el estado de cualquier componente de red determinado en cualquier momento del día.</span><span class="sxs-lookup"><span data-stu-id="008ac-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="008ac-109">**Rendimiento del servidor individual**   este nivel de rendimiento se limita a un servidor específico y ayudará a los administradores a medir el rendimiento de la red de un servidor específico para ayudarle a solucionar un determinado rendimiento. problema o para evaluar el rendimiento del servidor correspondiente a lo largo de un período determinado como parte de un proceso de planeación de capacidad.</span><span class="sxs-lookup"><span data-stu-id="008ac-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="008ac-110">Puede supervisar la red con las herramientas que se describen en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="008ac-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="008ac-111">Herramientas para la supervisión general del rendimiento de la red</span><span class="sxs-lookup"><span data-stu-id="008ac-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="008ac-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="008ac-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="008ac-113">System Center Operations Manager proporciona administración de servicios de extremo a extremo que es fácil de personalizar y extender para mejorar los niveles de servicio en un entorno de ti.</span><span class="sxs-lookup"><span data-stu-id="008ac-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="008ac-114">Esto permite a las operaciones y a los equipos de administración de ti identificar y resolver los problemas que afectan al estado de los servicios de ti distribuidos.</span><span class="sxs-lookup"><span data-stu-id="008ac-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="008ac-115">La administración de servicios end-to-end no está restringida a entornos basados en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="008ac-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="008ac-116">La compatibilidad con los servicios web para administración (WS-Management), el Protocolo simple de administración de redes (SNMP) y las soluciones de socio permiten que los sistemas que no ejecutan sistemas operativos y hardware de Microsoft se incluyan en la supervisión de servicios de System Center. Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="008ac-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="008ac-117">System Center Operations Manager 2012 y soluciones de administración de redes de terceros</span><span class="sxs-lookup"><span data-stu-id="008ac-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="008ac-118">\*\*\*\*   Las soluciones de EMC Smarts de EMC para Operations Manager le ayudan a resolver rápidamente los problemas que afectan a los niveles de servicio.</span><span class="sxs-lookup"><span data-stu-id="008ac-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="008ac-119">Al usar las soluciones de EMC para Operations Manager, puede administrar y monitorear toda su cadena de servicios de TI con una solución integrada y automática.</span><span class="sxs-lookup"><span data-stu-id="008ac-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="008ac-120">Podrá identificar fácilmente las causas de origen y los problemas de disponibilidad y resolverlos más rápido, lo que reduce los efectos y los costos.</span><span class="sxs-lookup"><span data-stu-id="008ac-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="008ac-121">Entre las principales ventajas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="008ac-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="008ac-122">El enfoque de administración avanzada y fácil de usar es ofrecer un valor comercial estratégico en lugar de ordenar y filtrar de forma manual alertas confusas.</span><span class="sxs-lookup"><span data-stu-id="008ac-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="008ac-123">**Resolución más rápida**   solucione problemas de ti y responda a las necesidades empresariales más rápidamente, reduciendo el efecto y el costo.</span><span class="sxs-lookup"><span data-stu-id="008ac-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="008ac-124">**Las operaciones**   simplificadas evitan la complejidad de TI al combinar varias herramientas de administración, aplicaciones y terminales.</span><span class="sxs-lookup"><span data-stu-id="008ac-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="008ac-125">Puede encontrar más información aquí:</span><span class="sxs-lookup"><span data-stu-id="008ac-125">More information can be found here:</span></span>

[<span data-ttu-id="008ac-126">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="008ac-126">Microsoft System Center Operations Manager</span></span>](http://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="008ac-127">Soluciones para Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="008ac-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="008ac-128">Soluciones de terceros</span><span class="sxs-lookup"><span data-stu-id="008ac-128">Third-Party Solutions</span></span>

<span data-ttu-id="008ac-129">**Centro de administración de redes HP (anteriormente conocido como HP OpenView)** El    [centro de administración de redes HP](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) ofrece administración integrada de errores y rendimiento para mejorar la disponibilidad y el rendimiento de la red.</span><span class="sxs-lookup"><span data-stu-id="008ac-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="008ac-130">El centro de administración de redes es parte de la solución de administración automatizada de redes HP, que unifica los errores, el rendimiento, la configuración y la administración de los cambios.</span><span class="sxs-lookup"><span data-stu-id="008ac-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="008ac-131">**Productos de administración de redes y de automatización de Cisco**   para empresas, Cisco tiene varios productos de administración disponibles, como la solución de administración LAN de CiscoWorks y el módulo de análisis de redes Cisco, para ayudar a mejorar la eficacia operativa y reduce el tiempo de inactividad de la red.</span><span class="sxs-lookup"><span data-stu-id="008ac-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="008ac-132">Para obtener más información sobre estos productos, visite el sitio web de [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)Cisco en.</span><span class="sxs-lookup"><span data-stu-id="008ac-132">For additional data on these products, refer to the Cisco website at [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="008ac-133">El Protocolo simple de administración de redes (SNMP) es un estándar de administración de redes que define una estrategia de administración de redes TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="008ac-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="008ac-134">SNMP le permite capturar información de configuración y estado de la red, y enviar la información a un equipo designado para su supervisión de eventos.</span><span class="sxs-lookup"><span data-stu-id="008ac-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="008ac-135">Este protocolo basado en estándares de administración de redes usa una arquitectura distribuida que incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="008ac-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="008ac-136">Varios nodos administrados, cada uno con una entidad SNMP denominada agente, que proporciona acceso remoto al instrumental de administración.</span><span class="sxs-lookup"><span data-stu-id="008ac-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="008ac-137">Al menos una entidad SNMP denominada administrador que ejecuta las aplicaciones de administración para supervisar y controlar los elementos administrados.</span><span class="sxs-lookup"><span data-stu-id="008ac-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="008ac-138">Los elementos administrados son dispositivos como los hosts, los enrutadores, etc.</span><span class="sxs-lookup"><span data-stu-id="008ac-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="008ac-139">Se supervisan y controlan accediendo a su información de administración.</span><span class="sxs-lookup"><span data-stu-id="008ac-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="008ac-140">Se usa un protocolo de administración, SNMP, para comunicar la información de administración entre las estaciones y los agentes de administración.</span><span class="sxs-lookup"><span data-stu-id="008ac-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="008ac-141">La información de administración hace referencia a una colección de objetos administrados que residen en un almacén de información virtual denominado base de información de administración (MIB).</span><span class="sxs-lookup"><span data-stu-id="008ac-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="008ac-142">Anteriormente se proporcionan ejemplos de soluciones de supervisión de red de terceros.</span><span class="sxs-lookup"><span data-stu-id="008ac-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="008ac-143">Esta lista no es definitiva y Microsoft no favorece la solución de un proveedor específico.</span><span class="sxs-lookup"><span data-stu-id="008ac-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="008ac-144">Comuníquese con un proveedor de servicios de red o con su proveedor de tecnología respectivo para determinar la mejor solución de supervisión de red para su organización.</span><span class="sxs-lookup"><span data-stu-id="008ac-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="008ac-145">Herramientas para supervisar el rendimiento de la red del servidor</span><span class="sxs-lookup"><span data-stu-id="008ac-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="008ac-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="008ac-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="008ac-147">System Center Operations Manager 2012 permite a los administradores ver el rendimiento de la red de servidores individuales a través del módulo de administración de Windows Server 2012: el módulo de administración de sistema operativo Windows Server incluye un módulo de administración de "rendimiento" eso permitiría que los administradores supervisaran el rendimiento del adaptador de red y el estado del adaptador.</span><span class="sxs-lookup"><span data-stu-id="008ac-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="008ac-148">Monitor de red de Windows</span><span class="sxs-lookup"><span data-stu-id="008ac-148">Windows Network Monitor</span></span>

<span data-ttu-id="008ac-149">Recopila, muestra, analiza el uso de recursos en un servidor y mide el tráfico de red.</span><span class="sxs-lookup"><span data-stu-id="008ac-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="008ac-150">Monitor de red supervisa la actividad de la red de modo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="008ac-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="008ac-151">Al capturar y analizar datos de red, y usar estos datos con registros de rendimiento, puede determinar el uso de la red, identificar problemas de red y prever las necesidades futuras de la red.</span><span class="sxs-lookup"><span data-stu-id="008ac-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="008ac-152">Para obtener más información sobre el monitor de red 3,4, y para obtener información sobre cómo instalar y configurar el monitor de red y capturar y analizar datos, consulte la descripción de esta sesión: monitor de red 3,3.</span><span class="sxs-lookup"><span data-stu-id="008ac-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="008ac-153">Además, revise el [blog del monitor de red](http://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="008ac-153">Also, review the [Network Monitor blog](http://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

