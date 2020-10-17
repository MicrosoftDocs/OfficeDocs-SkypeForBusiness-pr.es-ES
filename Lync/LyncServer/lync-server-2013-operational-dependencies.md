---
title: 'Lync Server 2013: dependencias operativas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e506fbbe204b7248396c25c3728556c61681cbf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526577"
---
# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="a6ff2-102">Dependencias operativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6ff2-102">Operational dependencies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6ff2-103">_**Última modificación del tema:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="a6ff2-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="a6ff2-104">La arquitectura de referencia que se describe en este documento le ayudará a asegurarse de que tiene una implementación de Lync Server 2013 que no solo escala a los requisitos de la organización, sino que está diseñada según los procedimientos recomendados de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="a6ff2-105">Asegúrese de que la implementación de Lync Server 2013 es un servicio dinámico y, al igual que cualquier otro servicio de la empresa, sigue necesitando supervisión y administración proactiva para mantener un alto nivel de disponibilidad de servicio y calidad de servicio para la empresa.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="a6ff2-106">Como Lync Server 2013 se convierte en profundidad en las actividades cotidianas de la organización, es importante que el servicio se administre con una administración de niveles de servicio precisa y tangible.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="a6ff2-107">La arquitectura del sistema Lync puede llegar a ser compleja y muy integrada y para mantener una administración eficaz del nivel de servicio y establecer SLAs para Lync Server 2013 se convierte en crítica para comprender las dependencias del sistema en otras plataformas y servidores.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="a6ff2-108">Igualmente importante es tener en cuenta qué servicios empresariales, como las aplicaciones integradas de voz y de comunicaciones unificadas, se convierten en independientes en Lync.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="a6ff2-109">Lync Server 2013 debe establecerse teniendo en cuentan todas las dependencias mencionadas.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="a6ff2-110">El mapa de servicio le permitirá formular un SLA entre Lync y su servicio dependiente y proporcionar un punto de partida para la negociación del SLA.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="a6ff2-111">En la siguiente tabla se enumeran los servicios de dependencia típicos para una infraestructura de Lync.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="a6ff2-112">Cada una de estas tecnologías debe tener su propia supervisión proactiva.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="a6ff2-113">Servicios de dependencia típicos</span><span class="sxs-lookup"><span data-stu-id="a6ff2-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6ff2-114">Servicio de dependencia</span><span class="sxs-lookup"><span data-stu-id="a6ff2-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-115">Sistemas operativos</span><span class="sxs-lookup"><span data-stu-id="a6ff2-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ff2-116">Hardware de servidor</span><span class="sxs-lookup"><span data-stu-id="a6ff2-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="a6ff2-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ff2-118">Infraestructura de clave pública</span><span class="sxs-lookup"><span data-stu-id="a6ff2-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-119">Servicio de nombres de dominio</span><span class="sxs-lookup"><span data-stu-id="a6ff2-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ff2-120">Servicios de bases de datos</span><span class="sxs-lookup"><span data-stu-id="a6ff2-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-121">Servicios de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="a6ff2-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ff2-122">Administración del sistema: supervisión y distribución</span><span class="sxs-lookup"><span data-stu-id="a6ff2-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-123">Servicios de seguridad: antivirus</span><span class="sxs-lookup"><span data-stu-id="a6ff2-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ff2-124">Infraestructura de red: Internet</span><span class="sxs-lookup"><span data-stu-id="a6ff2-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-125">Infraestructura de red: interna (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="a6ff2-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ff2-126">Infraestructura de telefonía: IP-PBX y puertas de enlace</span><span class="sxs-lookup"><span data-stu-id="a6ff2-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-127">Servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="a6ff2-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a6ff2-128">Se supone que la organización es una tarea muy madura para ejercitar las funciones básicas de administración de nivel de servicio, como la administración de cambios, incidentes y versiones, como se indica en el MOF.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="a6ff2-129">La solución de Lync debe ser adoptada por estas funciones y estar sujeta a los mismos procesos de administración operativos.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="a6ff2-130">A partir de la información obtenida anteriormente, ahora tenemos un conocimiento más profundo de lo que puede afectar al servicio Lync en la empresa.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="a6ff2-131">Para ayudar a garantizar la calidad y disponibilidad del servicio de Lync Server 2013, las siguientes herramientas de supervisión deben acompañar a la implementación de la arquitectura de referencia:</span><span class="sxs-lookup"><span data-stu-id="a6ff2-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="a6ff2-132">Herramientas de supervisión</span><span class="sxs-lookup"><span data-stu-id="a6ff2-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6ff2-133">Componente</span><span class="sxs-lookup"><span data-stu-id="a6ff2-133">Component</span></span></th>
<th><span data-ttu-id="a6ff2-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6ff2-134">Description</span></span></th>
<th><span data-ttu-id="a6ff2-135">Sitio aplicable</span><span class="sxs-lookup"><span data-stu-id="a6ff2-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-136">Servidor de supervisión de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6ff2-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-137">Implemente al menos un rol de servidor de supervisión de Lync Server 2013 por sitio central y configure la calidad de la experiencia (QoE) Reporting Pack.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="a6ff2-138">Consulte la documentación de implementación de Lync Server 2013 para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="a6ff2-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="a6ff2-139"><a href="lync-server-2013-deploying-monitoring.md">Implementación de la supervisión en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a6ff2-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a6ff2-140">Sitios centrales</span><span class="sxs-lookup"><span data-stu-id="a6ff2-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a6ff2-141">Tethering cada grupo a su instancia más cercana del rol del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-142">Sitios centrales</span><span class="sxs-lookup"><span data-stu-id="a6ff2-142">Central sites</span></span></p>
<p><span data-ttu-id="a6ff2-143">Sitios de sucursal</span><span class="sxs-lookup"><span data-stu-id="a6ff2-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="a6ff2-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-145">System Center Operations Manager 2012 con el módulo de administración de Microsoft Lync Server 2013 (MP) importado.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="a6ff2-146">El módulo de administración que implementa la instrumentación tradicional basada en el registro de eventos y el contador de rendimiento se usa, así como la habilitación de la instrumentación reciente disponible en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-147">Sitios centrales</span><span class="sxs-lookup"><span data-stu-id="a6ff2-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a6ff2-148">Asegúrese de que la detección central para la detección de roles y componentes que deben supervisarse se completen automáticamente en función de un script de detección central que lea el documento de topología publicado en la base de datos de administración central.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-149">Sitio central</span><span class="sxs-lookup"><span data-stu-id="a6ff2-149">Central Site</span></span></p>
<p><span data-ttu-id="a6ff2-150">Sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="a6ff2-150">Branch Site</span></span></p>
<p><span data-ttu-id="a6ff2-151">Sitio perimetral</span><span class="sxs-lookup"><span data-stu-id="a6ff2-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="a6ff2-152">Implementar agentes del centro de Operations Manager 2007 en todos los servidores implementados que ejecutan Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-153">Sitio central</span><span class="sxs-lookup"><span data-stu-id="a6ff2-153">Central Site</span></span></p>
<p><span data-ttu-id="a6ff2-154">Sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="a6ff2-154">Branch Site</span></span></p>
<p><span data-ttu-id="a6ff2-155">Sitio perimetral</span><span class="sxs-lookup"><span data-stu-id="a6ff2-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a6ff2-156">Asegúrese de que las alertas con prioridad están configuradas para la notificación:</span><span class="sxs-lookup"><span data-stu-id="a6ff2-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="a6ff2-157">Alertas de prioridad alta</span><span class="sxs-lookup"><span data-stu-id="a6ff2-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="a6ff2-158">Alertas de prioridad media</span><span class="sxs-lookup"><span data-stu-id="a6ff2-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="a6ff2-159">Otras alertas.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-160">Sitio central</span><span class="sxs-lookup"><span data-stu-id="a6ff2-160">Central Site</span></span></p>
<p><span data-ttu-id="a6ff2-161">Sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="a6ff2-161">Branch Site</span></span></p>
<p><span data-ttu-id="a6ff2-162">Sitio perimetral</span><span class="sxs-lookup"><span data-stu-id="a6ff2-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="a6ff2-163">Configure la supervisión de puertos para la implementación.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-164">Sitio central</span><span class="sxs-lookup"><span data-stu-id="a6ff2-164">Central Site</span></span></p>
<p><span data-ttu-id="a6ff2-165">Sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="a6ff2-165">Branch Site</span></span></p>
<p><span data-ttu-id="a6ff2-166">Sitio perimetral</span><span class="sxs-lookup"><span data-stu-id="a6ff2-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a6ff2-167">Configurar la supervisión de direcciones URL para la implementación</span><span class="sxs-lookup"><span data-stu-id="a6ff2-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-168">Sitio central</span><span class="sxs-lookup"><span data-stu-id="a6ff2-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-169">Integración de Lync y System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a6ff2-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-170">Implementar la confiabilidad de las llamadas y la calidad de los medios MonitoringCall la fiabilidad y la supervisión de la calidad de los medios use el equipo servidor de supervisión como nodo de monitor para supervisar la confiabilidad de las llamadas y la calidad de los medios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="a6ff2-171">Estas dos características consultan las bases de datos del servidor de supervisión para realizar el análisis.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-172">Sitio central</span><span class="sxs-lookup"><span data-stu-id="a6ff2-172">Central Site</span></span></p>
<p><span data-ttu-id="a6ff2-173">Sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="a6ff2-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a6ff2-174">Garantizar que los umbrales de advertencia de calidad de medios se configuran correctamente.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="a6ff2-175">En la tabla siguiente se indican los resultados de opinión media de red máxima por códec.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="a6ff2-176">En producción, estos resultados deben supervisarse durante un período de tiempo determinado y los umbrales aceptables deben establecerse en función de los resultados de las puntuaciones NMOS específicas de la organización.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-177">Sitio central</span><span class="sxs-lookup"><span data-stu-id="a6ff2-177">Central Site</span></span></p>
<p><span data-ttu-id="a6ff2-178">Sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="a6ff2-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-179">Monitor de transacción sintética de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6ff2-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-180">Implemente un servidor de Lync dedicado para que sea un monitor de transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="a6ff2-181">Las transacciones sintéticas son cmdlets de Windows PowerShell de Lync Server 2013 que se desencadenan automáticamente por el módulo de administración en un intervalo predefinido.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="a6ff2-182">Se ejecutan en un nodo de monitor de transacciones sintéticas que es un servidor designado por el administrador responsable de la detección y la ejecución de STs para cada grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="a6ff2-183">No se recomienda usar un servidor de Microsoft Lync Server 2013 existente como nodo de monitor de transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="a6ff2-184">Esto se debe a los requisitos de uso intensivo de CPU y memoria para ejecutar STs.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="a6ff2-185">Use un nuevo equipo servidor (o un servidor virtual) para el nodo Monitor de transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-186">Sitio central</span><span class="sxs-lookup"><span data-stu-id="a6ff2-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a6ff2-187">Implementación del nodo de monitor de transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="a6ff2-188">Consulte el documento MonitoringCS_withSCOM.docx de la documentación de UCTAP Connect.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-189">Sitio central</span><span class="sxs-lookup"><span data-stu-id="a6ff2-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="a6ff2-190">Puntuaciones máximas de MOS de red por códec</span><span class="sxs-lookup"><span data-stu-id="a6ff2-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6ff2-191">Escenario</span><span class="sxs-lookup"><span data-stu-id="a6ff2-191">Scenario</span></span></th>
<th><span data-ttu-id="a6ff2-192">Códec</span><span class="sxs-lookup"><span data-stu-id="a6ff2-192">Codec</span></span></th>
<th><span data-ttu-id="a6ff2-193">NMOS máx</span><span class="sxs-lookup"><span data-stu-id="a6ff2-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-194">Llamadas de UC a UC</span><span class="sxs-lookup"><span data-stu-id="a6ff2-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-195">WB RTAudio</span><span class="sxs-lookup"><span data-stu-id="a6ff2-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-196">4.10</span><span class="sxs-lookup"><span data-stu-id="a6ff2-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ff2-197">Llamadas de UC a UC</span><span class="sxs-lookup"><span data-stu-id="a6ff2-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="a6ff2-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-199">2,95</span><span class="sxs-lookup"><span data-stu-id="a6ff2-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-200">Llamada de conferencia</span><span class="sxs-lookup"><span data-stu-id="a6ff2-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-201">Siren</span><span class="sxs-lookup"><span data-stu-id="a6ff2-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-202">3,72</span><span class="sxs-lookup"><span data-stu-id="a6ff2-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ff2-203">Llamada de UC-RTC</span><span class="sxs-lookup"><span data-stu-id="a6ff2-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="a6ff2-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-205">2,95</span><span class="sxs-lookup"><span data-stu-id="a6ff2-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6ff2-206">Llamada de UC-RTC</span><span class="sxs-lookup"><span data-stu-id="a6ff2-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-207">G-711</span><span class="sxs-lookup"><span data-stu-id="a6ff2-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="a6ff2-208">3,61</span><span class="sxs-lookup"><span data-stu-id="a6ff2-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a6ff2-209">Más allá de las anteriores actividades de supervisión proactivas, las tareas de mantenimiento deben ejecutarse para sitios centrales, perimetrales y de sucursal en una periodicidad diaria, semanal y mensual, tal como se define en la guía de operaciones de Lync RA.</span><span class="sxs-lookup"><span data-stu-id="a6ff2-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

