---
title: Planear el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumen: Lea este tema para obtener información sobre statistic Manager para Skype empresarial Server.'
ms.openlocfilehash: a58ca8ea8ed2d612e00a0705bb28e8d6fe95eb45
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299740"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="80573-103">Planear el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="80573-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="80573-104">**Resumen:** Lea este tema para obtener información sobre statistic Manager para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="80573-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="80573-105">El administrador de estadísticas de Skype Empresarial Server es una eficaz herramienta que le permite ver los datos de mantenimiento y rendimiento de Skype Empresarial Server en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="80573-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="80573-106">Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="80573-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="80573-107">Puede usar Statistics Manager para identificar problemas de rendimiento continuo, ver los resultados de un cambio planificado en su entorno, realizar un seguimiento de la resolución de las interrupciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="80573-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="80573-108">El administrador de estadísticas está configurado con los umbrales del indicador de mantenimiento de clave (KHI), y se puede personalizar según las necesidades exclusivas de su implementación.</span><span class="sxs-lookup"><span data-stu-id="80573-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="80573-109">Puede implementar el administrador de estadísticas en una implementación local en la que un solo servidor hospede todos los componentes del administrador de estadísticas del servidor.</span><span class="sxs-lookup"><span data-stu-id="80573-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="80573-110">Para obtener más información sobre cómo implementar statistic Manager, consulte [implementar el administrador de estadísticas para Skype empresarial Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="80573-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="80573-111">Si ya tiene una implementación existente de Statistics Manager, pero aún no ha actualizado a la versión 2,0, consulte [novedades de la versión 2,0](plan.md#BKMK_WhatsNew) y al [Administrador de estadísticas de actualización para Skype empresarial Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="80573-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="80573-112">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="80573-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="80573-113">Características y capacidades</span><span class="sxs-lookup"><span data-stu-id="80573-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="80573-114">Novedades de la versión 2,0</span><span class="sxs-lookup"><span data-stu-id="80573-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="80573-115">Componentes</span><span class="sxs-lookup"><span data-stu-id="80573-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="80573-116">Implementación local</span><span class="sxs-lookup"><span data-stu-id="80573-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- <span data-ttu-id="80573-117">[Requisitos](plan.md#BKMK_Requirements) </span><span class="sxs-lookup"><span data-stu-id="80573-117">[Requirements](plan.md#BKMK_Requirements)</span></span>

- [<span data-ttu-id="80573-118">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="80573-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="80573-119">Características y capacidades</span><span class="sxs-lookup"><span data-stu-id="80573-119">Features and capabilities</span></span>
<span data-ttu-id="80573-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="80573-120"></span></span>

<span data-ttu-id="80573-121">Statistic Manager le permite:</span><span class="sxs-lookup"><span data-stu-id="80573-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="80573-122">Ver datos sin procesar de todos los servidores en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="80573-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="80573-123">(Los datos se muestrean a una tasa muy alta y se envían al sitio web en menos de un segundo).</span><span class="sxs-lookup"><span data-stu-id="80573-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="80573-124">Ver datos agregados para un rol específico; por ejemplo, el servidor front-end, el servidor de mediación, el servidor perimetral, etc.</span><span class="sxs-lookup"><span data-stu-id="80573-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="80573-125">Desplácese hacia abajo para ver los datos de sitios específicos, agrupaciones específicas dentro del sitio y, a continuación, servidores específicos dentro de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="80573-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="80573-126">Crear gráficos personalizados para que se muestren los contadores elegidos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="80573-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="80573-127">Zoom y panorámica en los ejes x e y o solo en el eje x.</span><span class="sxs-lookup"><span data-stu-id="80573-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="80573-128">Use intervalos de fechas o puntos en el tiempo para filtrar datos.</span><span class="sxs-lookup"><span data-stu-id="80573-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="80573-129">Ver el rendimiento del servidor basado en indicadores de estado clave establecidos (KHIs).</span><span class="sxs-lookup"><span data-stu-id="80573-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="80573-130">KHIs representa una colección de contadores de rendimiento con un rango correcto definido.</span><span class="sxs-lookup"><span data-stu-id="80573-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="80573-131">Ver métricas detalladas de cada contador.</span><span class="sxs-lookup"><span data-stu-id="80573-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="80573-132">Comparar datos entre varios poblaciones o servidores.</span><span class="sxs-lookup"><span data-stu-id="80573-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="80573-133">Ver los informes latentes para identificar agentes que no están notificando los datos actuales al servicio de panel.</span><span class="sxs-lookup"><span data-stu-id="80573-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="80573-134">Guardar una instancia determinada de datos del gráfico en un archivo.</span><span class="sxs-lookup"><span data-stu-id="80573-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="80573-135">Ver KHIs en tiempo real, incluidas las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="80573-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="80573-136">Si la vista historial está habilitada, solo se muestran los errores nuevos.</span><span class="sxs-lookup"><span data-stu-id="80573-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="80573-137">Ver todos los KHIs a la vez</span><span class="sxs-lookup"><span data-stu-id="80573-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="80573-138">Ver KHIs por servidor (vista horizontal)</span><span class="sxs-lookup"><span data-stu-id="80573-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="80573-139">Ver definiciones de KHI</span><span class="sxs-lookup"><span data-stu-id="80573-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="80573-140">Novedades de la versión 2,0</span><span class="sxs-lookup"><span data-stu-id="80573-140">What's new in Release 2.0</span></span>
<span data-ttu-id="80573-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="80573-141"></span></span>

<span data-ttu-id="80573-142">A continuación se describen las novedades de la versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="80573-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="80573-143">Si ya tiene una implementación de Statistics Manager y aún no la ha actualizado, consulte actualizar el [Administrador de estadísticas para Skype empresarial Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="80573-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="80573-144">Se han agregado vistas de escenario para los escenarios de los extremos, la Health, la conmutación por error y el registro.</span><span class="sxs-lookup"><span data-stu-id="80573-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="80573-145">Se han agregado muchos contadores nuevos para servidores SQL, más contadores de uso de Skype empresarial, etc.</span><span class="sxs-lookup"><span data-stu-id="80573-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="80573-146">Integración del nodo de monitor para el agente del administrador de estadísticas: Si el agente está instalado en un nodo de supervisor, notificará las estadísticas de transacción sintéticas a los contadores como recuentos al administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="80573-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="80573-147">Numerosas mejoras de confiabilidad y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="80573-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="80573-148">Para comprobar la versión del sitio web de statistic Manager que está ejecutando:</span><span class="sxs-lookup"><span data-stu-id="80573-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="80573-149">En el explorador de archivos, abra (directorio predeterminado) C:\Archivos de Files\Skype para Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="80573-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="80573-150">Haga clic con el botón secundario en StatsManHubWebSite. dll y vea sus propiedades</span><span class="sxs-lookup"><span data-stu-id="80573-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="80573-151">La versión del producto se mostrará en los detalles de Descripción.</span><span class="sxs-lookup"><span data-stu-id="80573-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="80573-152">Components</span><span class="sxs-lookup"><span data-stu-id="80573-152">Components</span></span>
<span data-ttu-id="80573-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="80573-153"></span></span>

<span data-ttu-id="80573-154">Statistics Manager consta de los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="80573-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="80573-155">**Transportista.**</span><span class="sxs-lookup"><span data-stu-id="80573-155">**Agent.**</span></span> <span data-ttu-id="80573-156">Un agente liviano que se ejecuta en cada servidor supervisado.</span><span class="sxs-lookup"><span data-stu-id="80573-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="80573-157">El agente permite sondeo configurable de alta tasa de contadores de rendimiento con agregación local.</span><span class="sxs-lookup"><span data-stu-id="80573-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="80573-158">**Escucha.**</span><span class="sxs-lookup"><span data-stu-id="80573-158">**Listener.**</span></span> <span data-ttu-id="80573-159">La API del servidor que recibe datos de todos los agentes y agrega datos entre los mismos.</span><span class="sxs-lookup"><span data-stu-id="80573-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="80573-160">**Perimetral.**</span><span class="sxs-lookup"><span data-stu-id="80573-160">**Hub.**</span></span> <span data-ttu-id="80573-161">Actúa como la API de cliente para el sistema, se ejecuta en los servidores web y proporciona actualizaciones de datos en tiempo real a clientes conectados a través del sitio Web.</span><span class="sxs-lookup"><span data-stu-id="80573-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="80573-162">(El concentrador se instala automáticamente como parte del MSI del sitio web).</span><span class="sxs-lookup"><span data-stu-id="80573-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="80573-163">**Página.**</span><span class="sxs-lookup"><span data-stu-id="80573-163">**Website.**</span></span> <span data-ttu-id="80573-164">Una interfaz de usuario que reúne todas las características disponibles en el sistema.</span><span class="sxs-lookup"><span data-stu-id="80573-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="80573-165">Además, statistic Manager requiere **Redis**, un servidor de estructura de datos de código abierto para la caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="80573-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="80573-166">Para obtener más información sobre cómo descargar Redis, consulte [implementar el administrador de estadísticas](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="80573-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="80573-167">Implementación local</span><span class="sxs-lookup"><span data-stu-id="80573-167">On-premises deployment</span></span>
<span data-ttu-id="80573-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="80573-168"></span></span>

<span data-ttu-id="80573-169">En una implementación local, un único servidor hospeda todos los componentes del administrador de estadísticas del servidor.</span><span class="sxs-lookup"><span data-stu-id="80573-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="80573-170">En el siguiente diagrama se muestra una implementación local en la que el sitio web del administrador de estadísticas, Hub, escucha y sistema de caché en Redis se hospedan en un solo equipo.</span><span class="sxs-lookup"><span data-stu-id="80573-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="80573-171">Statistic Manager está supervisando tres servidores de Skype empresarial, cada uno de los cuales transmite los datos de un único agente a la escucha.</span><span class="sxs-lookup"><span data-stu-id="80573-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="80573-172">Los usuarios se conectan a un solo sitio web para ver todos los datos agregados por statistic Manager:</span><span class="sxs-lookup"><span data-stu-id="80573-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Implementación local del administrador de estadísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="80573-174">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80573-174">Requirements</span></span>
<span data-ttu-id="80573-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="80573-175"></span></span>

<span data-ttu-id="80573-176">Antes de implementar statistic Manager, tendrá que tener en cuenta los siguientes requisitos de software, de red y de hardware.</span><span class="sxs-lookup"><span data-stu-id="80573-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="80573-177">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="80573-177">Software requirements</span></span>

- <span data-ttu-id="80573-178">Windows Server 2016 y 2019</span><span class="sxs-lookup"><span data-stu-id="80573-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="80573-179">IIS (instalado automáticamente)</span><span class="sxs-lookup"><span data-stu-id="80573-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="80573-180">Redis</span><span class="sxs-lookup"><span data-stu-id="80573-180">Redis</span></span>

- <span data-ttu-id="80573-181">Servicios de administración de estadísticas (instalados automáticamente)</span><span class="sxs-lookup"><span data-stu-id="80573-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="80573-182">PSExec: se necesita para realizar la implementación de agentes remotos</span><span class="sxs-lookup"><span data-stu-id="80573-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="80573-183">.NET 4,5 (incluido con 2012 R2): necesario para los agentes y componentes del servidor</span><span class="sxs-lookup"><span data-stu-id="80573-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="80573-184">Descargar [Skype empresarial Server, administrador de estadísticas en tiempo real (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="80573-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="80573-185">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="80573-185">Networking requirements</span></span>


|<span data-ttu-id="80573-186">**Servidor de hospedaje**</span><span class="sxs-lookup"><span data-stu-id="80573-186">**Hosting server**</span></span>|<span data-ttu-id="80573-187">**Agentes.**</span><span class="sxs-lookup"><span data-stu-id="80573-187">**Agents**</span></span>|<span data-ttu-id="80573-188">**Escucha**</span><span class="sxs-lookup"><span data-stu-id="80573-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80573-189">Una red Gigabit dúplex completa mínima.</span><span class="sxs-lookup"><span data-stu-id="80573-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="80573-190">Puerto TCP saliente 8443 (número de Puerto personalizable) para comunicarse con el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="80573-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="80573-191">El puerto de escucha debe ser el mismo en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="80573-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="80573-192">Puerto TCP entrante 80 o 443 abierto para hospedar el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="80573-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="80573-193">Puerto TCP entrante 8443 (número de Puerto personalizable) para que los agentes se comuniquen con él.</span><span class="sxs-lookup"><span data-stu-id="80573-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="80573-194">Durante la instalación, se crean automáticamente puertos de Firewall para el agente de escucha y el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="80573-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="80573-195">Para los agentes, la instalación supone que las conexiones TCP salientes están permitidas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="80573-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="80573-196">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="80573-196">Hardware requirements</span></span>

<span data-ttu-id="80573-197">En una implementación local, en la que un único servidor hospeda a todos los componentes del administrador de estadísticas del servidor, un servidor con 16 GB de RAM y 4 CPU debe poder admitir aproximadamente 150 muestras por segundo por segundo.</span><span class="sxs-lookup"><span data-stu-id="80573-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="80573-198">Para determinar cuántos contadores/agentes puede admitir, use el siguiente cálculo:</span><span class="sxs-lookup"><span data-stu-id="80573-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="80573-199">100 servidores \*80 contadores \* 1 ejemplo por minuto de cada agente/60 segundos = ~ 133 muestras por segundo.</span><span class="sxs-lookup"><span data-stu-id="80573-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="80573-200">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="80573-200">Security considerations</span></span>
<span data-ttu-id="80573-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="80573-201"></span></span>

<span data-ttu-id="80573-202">Todo el tráfico entre los servidores está cifrado.</span><span class="sxs-lookup"><span data-stu-id="80573-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="80573-203">El tráfico HTTPS cifrado se enviará a través del puerto 8443 (de forma predeterminada) desde el agente al servidor de escucha.</span><span class="sxs-lookup"><span data-stu-id="80573-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="80573-204">El agente verificará la huella digital SSL en el servidor para asegurarse de que el servidor de escucha sea el destinatario esperado.</span><span class="sxs-lookup"><span data-stu-id="80573-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="80573-205">Tenga en cuenta que el agente usa verificación de certificados por huella digital (en lugar de verificación en cadena).</span><span class="sxs-lookup"><span data-stu-id="80573-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="80573-206">No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="80573-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="80573-207">Una vez que el agente está satisfecho, el oyente es auténtico, el agente que comprueba la contraseña será presentado por el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="80573-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="80573-208">El agente comienza a transmitir datos de rendimiento a través de la conexión a la escucha.</span><span class="sxs-lookup"><span data-stu-id="80573-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="80573-209">Más información</span><span class="sxs-lookup"><span data-stu-id="80573-209">For more information</span></span>
<span data-ttu-id="80573-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="80573-210"></span></span>

<span data-ttu-id="80573-211">Para obtener más información, vea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="80573-211">For more information, see the following:</span></span>

- [<span data-ttu-id="80573-212">Implementar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="80573-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="80573-213">Actualizar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="80573-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="80573-214">Solucionar problemas del administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="80573-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
