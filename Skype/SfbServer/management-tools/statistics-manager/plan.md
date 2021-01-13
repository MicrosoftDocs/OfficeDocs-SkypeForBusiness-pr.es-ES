---
title: Plan para el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumen: lea este tema para obtener información sobre el Administrador de estadísticas de Skype Empresarial Server.'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821830"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="bc468-103">Plan para el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc468-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="bc468-104">**Resumen:** Lea este tema para obtener información sobre el Administrador de estadísticas de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bc468-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="bc468-105">El Administrador de estadísticas de Skype Empresarial Server es una herramienta eficaz que le permite ver datos de rendimiento y estado de Skype Empresarial Server en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="bc468-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="bc468-106">Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del Administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="bc468-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="bc468-107">Puede usar el Administrador de estadísticas para identificar problemas de rendimiento continuos, ver los resultados de un cambio planeado en su entorno, realizar un seguimiento de la resolución de interrupciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="bc468-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="bc468-108">De forma rápida, el Administrador de estadísticas está configurado con umbrales de indicador de estado clave (KHI) y se puede personalizar para adaptarse a las necesidades únicas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="bc468-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="bc468-109">Puede implementar el Administrador de estadísticas en una implementación local en la que un único servidor hospeda todos los componentes del Administrador de estadísticas del lado servidor.</span><span class="sxs-lookup"><span data-stu-id="bc468-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="bc468-110">Para obtener más información acerca de la implementación del Administrador de estadísticas, consulte Implementar el Administrador de [estadísticas para Skype Empresarial Server.](deploy.md)</span><span class="sxs-lookup"><span data-stu-id="bc468-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="bc468-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="bc468-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="bc468-112">En este tema se presentan las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="bc468-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="bc468-113">Características y capacidades</span><span class="sxs-lookup"><span data-stu-id="bc468-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="bc468-114">Novedades de la versión 2.0</span><span class="sxs-lookup"><span data-stu-id="bc468-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="bc468-115">Componentes</span><span class="sxs-lookup"><span data-stu-id="bc468-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="bc468-116">Implementación local</span><span class="sxs-lookup"><span data-stu-id="bc468-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- <span data-ttu-id="bc468-117">[Requisitos](plan.md#BKMK_Requirements) </span><span class="sxs-lookup"><span data-stu-id="bc468-117">[Requirements](plan.md#BKMK_Requirements)</span></span>

- [<span data-ttu-id="bc468-118">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="bc468-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="bc468-119">Características y capacidades</span><span class="sxs-lookup"><span data-stu-id="bc468-119">Features and capabilities</span></span>
<span data-ttu-id="bc468-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="bc468-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="bc468-121">El Administrador de estadísticas le permite:</span><span class="sxs-lookup"><span data-stu-id="bc468-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="bc468-122">Ver datos sin procesar para todos los servidores en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="bc468-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="bc468-123">(Los datos se muestra a una velocidad muy alta y se envían al sitio web en menos de un segundo).</span><span class="sxs-lookup"><span data-stu-id="bc468-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="bc468-124">Ver los datos agregados para un rol específico; por ejemplo, servidor front-end, servidor de mediación, servidor perimetral, entre otros.</span><span class="sxs-lookup"><span data-stu-id="bc468-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="bc468-125">Explore en profundidad para ver datos de sitios específicos, grupos específicos dentro del sitio y, a continuación, servidores específicos dentro del grupo.</span><span class="sxs-lookup"><span data-stu-id="bc468-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="bc468-126">Cree gráficos personalizados para que los contadores seleccionados se muestran de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bc468-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="bc468-127">Zoom y movimiento panorámico en los ejes x e y, o solo en el eje X.</span><span class="sxs-lookup"><span data-stu-id="bc468-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="bc468-128">Use intervalos de fechas o puntos de tiempo para filtrar datos.</span><span class="sxs-lookup"><span data-stu-id="bc468-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="bc468-129">Ver el rendimiento del servidor en función de los indicadores clave de estado (KHIs) establecidos.</span><span class="sxs-lookup"><span data-stu-id="bc468-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="bc468-130">Los KHIs representan una colección de contadores de rendimiento con un rango en buen estado definido.</span><span class="sxs-lookup"><span data-stu-id="bc468-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="bc468-131">Ver métricas detalladas para cada contador.</span><span class="sxs-lookup"><span data-stu-id="bc468-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="bc468-132">Compare los datos en varias poblaciones o servidores.</span><span class="sxs-lookup"><span data-stu-id="bc468-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="bc468-133">Ver informes de contadores latentes para identificar agentes que no notifican datos actuales al servicio de panel.</span><span class="sxs-lookup"><span data-stu-id="bc468-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="bc468-134">Guarde una instancia determinada de los datos del gráfico en un archivo.</span><span class="sxs-lookup"><span data-stu-id="bc468-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="bc468-135">Ver los KHIs en tiempo real, incluidas las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="bc468-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="bc468-136">Si la vista de historial está habilitada, solo se muestran nuevos errores.</span><span class="sxs-lookup"><span data-stu-id="bc468-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="bc468-137">Ver todos los KHIs a la vez</span><span class="sxs-lookup"><span data-stu-id="bc468-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="bc468-138">Ver LOS KHIs por servidor (vista horizontal)</span><span class="sxs-lookup"><span data-stu-id="bc468-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="bc468-139">Ver definiciones de KHI</span><span class="sxs-lookup"><span data-stu-id="bc468-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="bc468-140">Novedades de la versión 2.0</span><span class="sxs-lookup"><span data-stu-id="bc468-140">What's new in Release 2.0</span></span>
<span data-ttu-id="bc468-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="bc468-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="bc468-142">A continuación se describen las novedades de la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="bc468-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="bc468-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="bc468-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="bc468-144">Se han agregado vistas de escenario para los escenarios de medios perimetrales, mantenimiento de Fabric, conmutación por error de grupo y registro.</span><span class="sxs-lookup"><span data-stu-id="bc468-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="bc468-145">Se han agregado muchos contadores nuevos para SQL servidores, más contadores de uso de Skype Empresarial, etc.</span><span class="sxs-lookup"><span data-stu-id="bc468-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="bc468-146">Integración del nodo de monitor para el agente del Administrador de estadísticas: si el agente está instalado en un nodo de monitor, se mostrarán las estadísticas de transacciones sintéticas como contadores al Administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="bc468-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="bc468-147">Numerosas mejoras de confiabilidad y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="bc468-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="bc468-148">Para comprobar la versión del sitio web del Administrador de estadísticas que está ejecutando:</span><span class="sxs-lookup"><span data-stu-id="bc468-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="bc468-149">En el Explorador de archivos, abra (directorio predeterminado) C:\Archivos de programa\Skype Empresarial Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="bc468-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="bc468-150">Haga clic con el botón StatsManHubWebSite.dll y vea sus propiedades</span><span class="sxs-lookup"><span data-stu-id="bc468-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="bc468-151">La versión del producto se mostrará en los detalles de descripción.</span><span class="sxs-lookup"><span data-stu-id="bc468-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="bc468-152">Componentes</span><span class="sxs-lookup"><span data-stu-id="bc468-152">Components</span></span>
<span data-ttu-id="bc468-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="bc468-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="bc468-154">El Administrador de estadísticas consta de los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="bc468-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="bc468-155">**Agente.**</span><span class="sxs-lookup"><span data-stu-id="bc468-155">**Agent.**</span></span> <span data-ttu-id="bc468-156">Un agente ligero que se ejecuta en cada servidor supervisado.</span><span class="sxs-lookup"><span data-stu-id="bc468-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="bc468-157">El agente permite sondeos de alta velocidad configurables de contadores de rendimiento con agregación local.</span><span class="sxs-lookup"><span data-stu-id="bc468-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="bc468-158">**Escucha.**</span><span class="sxs-lookup"><span data-stu-id="bc468-158">**Listener.**</span></span> <span data-ttu-id="bc468-159">La API del lado servidor que recibe datos de todos los agentes y agrega datos entre las distintas poblaciones.</span><span class="sxs-lookup"><span data-stu-id="bc468-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="bc468-160">**Hub.**</span><span class="sxs-lookup"><span data-stu-id="bc468-160">**Hub.**</span></span> <span data-ttu-id="bc468-161">Actúa como la API de cliente para el sistema, se ejecuta en los servidores web y proporciona actualizaciones de datos en tiempo real a los clientes conectados a través del sitio web.</span><span class="sxs-lookup"><span data-stu-id="bc468-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="bc468-162">(El concentrador se instala automáticamente como parte del msi del sitio web).</span><span class="sxs-lookup"><span data-stu-id="bc468-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="bc468-163">**Sitio web.**</span><span class="sxs-lookup"><span data-stu-id="bc468-163">**Website.**</span></span> <span data-ttu-id="bc468-164">Una interfaz de usuario que reúne todas las características disponibles en el sistema.</span><span class="sxs-lookup"><span data-stu-id="bc468-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="bc468-165">Además, el Administrador de estadísticas requiere **Redis,** un servidor de estructura de datos de código abierto para el almacenamiento en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="bc468-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="bc468-166">Para obtener más información acerca de cómo descargar Redis, vea [Implementar el Administrador de estadísticas.](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="bc468-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="bc468-167">Implementación local</span><span class="sxs-lookup"><span data-stu-id="bc468-167">On-premises deployment</span></span>
<span data-ttu-id="bc468-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="bc468-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="bc468-169">En una implementación local, un único servidor hospeda todos los componentes del Administrador de estadísticas del lado servidor.</span><span class="sxs-lookup"><span data-stu-id="bc468-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="bc468-170">El siguiente diagrama muestra una implementación local, en la que el sitio web del Administrador de estadísticas, el sistema de almacenamiento en caché de Concentradores, Escucha y Redis se hospedan en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="bc468-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="bc468-171">El Administrador de estadísticas supervisa tres servidores de Skype Empresarial, cada uno de los cuales tiene un único agente que transmite datos a la escucha.</span><span class="sxs-lookup"><span data-stu-id="bc468-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="bc468-172">Los usuarios se conectan a un único sitio web para ver todos los datos agregados por el Administrador de estadísticas:</span><span class="sxs-lookup"><span data-stu-id="bc468-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Implementación local del Administrador de estadísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="bc468-174">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc468-174">Requirements</span></span>
<span data-ttu-id="bc468-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="bc468-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="bc468-176">Deberá tener en cuenta los siguientes requisitos de software, redes y hardware antes de implementar el Administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="bc468-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="bc468-177">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="bc468-177">Software requirements</span></span>

- <span data-ttu-id="bc468-178">Windows Server 2016 y 2019</span><span class="sxs-lookup"><span data-stu-id="bc468-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="bc468-179">IIS (instalado automáticamente)</span><span class="sxs-lookup"><span data-stu-id="bc468-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="bc468-180">Redis</span><span class="sxs-lookup"><span data-stu-id="bc468-180">Redis</span></span>

- <span data-ttu-id="bc468-181">Servicios del Administrador de estadísticas (instalados automáticamente)</span><span class="sxs-lookup"><span data-stu-id="bc468-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="bc468-182">PSExec: necesario para realizar la implementación de agentes remotos</span><span class="sxs-lookup"><span data-stu-id="bc468-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="bc468-183">.NET 4.5 (incluido con 2012 R2): necesario para agentes y componentes del lado servidor</span><span class="sxs-lookup"><span data-stu-id="bc468-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="bc468-184">Descargar Skype [Empresarial Server, administrador de Real-Time de estadísticas (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="bc468-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="bc468-185">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="bc468-185">Networking requirements</span></span>


|<span data-ttu-id="bc468-186">**Servidor de hospedaje**</span><span class="sxs-lookup"><span data-stu-id="bc468-186">**Hosting server**</span></span>|<span data-ttu-id="bc468-187">**Agents**</span><span class="sxs-lookup"><span data-stu-id="bc468-187">**Agents**</span></span>|<span data-ttu-id="bc468-188">**Listener**</span><span class="sxs-lookup"><span data-stu-id="bc468-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bc468-189">Red de dúplex completo de gigabit mínimo.</span><span class="sxs-lookup"><span data-stu-id="bc468-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="bc468-190">Puerto TCP saliente 8443 (número de puerto personalizable) para comunicarse con el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="bc468-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="bc468-191">El puerto de escucha debe ser el mismo en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="bc468-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="bc468-192">El puerto TCP de entrada 80 o 443 se abre para hospedar el sitio web.</span><span class="sxs-lookup"><span data-stu-id="bc468-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="bc468-193">Puerto TCP de entrada 8443 (número de puerto personalizable) para que los agentes se comuniquen con él.</span><span class="sxs-lookup"><span data-stu-id="bc468-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="bc468-194">Durante la instalación, los puertos de firewall para la escucha y el sitio web se crean automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bc468-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="bc468-195">Para los agentes, la instalación supone que las conexiones TCP salientes están permitidas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bc468-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="bc468-196">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="bc468-196">Hardware requirements</span></span>

<span data-ttu-id="bc468-197">En una implementación local, en la que un único servidor hospeda todos los componentes del Administrador de estadísticas del lado servidor, un servidor con 16 GB de RAM y 4 CPU debería ser capaz de admitir una media de 150 muestras por segundo.</span><span class="sxs-lookup"><span data-stu-id="bc468-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="bc468-198">Para determinar cuántos contadores/agentes puede admitir, use el siguiente cálculo:</span><span class="sxs-lookup"><span data-stu-id="bc468-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="bc468-199">100 servidores 80 contadores 1 muestra por minuto de cada agente \* / 60 segundos = ~ \* 133 muestras por segundo.</span><span class="sxs-lookup"><span data-stu-id="bc468-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="bc468-200">Consideraciones acerca de la seguridad</span><span class="sxs-lookup"><span data-stu-id="bc468-200">Security considerations</span></span>
<span data-ttu-id="bc468-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="bc468-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="bc468-202">Todo el tráfico entre servidores está cifrado.</span><span class="sxs-lookup"><span data-stu-id="bc468-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="bc468-203">El tráfico HTTPS cifrado se enviará a través del puerto 8443 (de forma predeterminada) desde el agente al servidor de escucha.</span><span class="sxs-lookup"><span data-stu-id="bc468-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="bc468-204">El agente comprobará la huella digital SSL en el servidor para asegurarse de que el servidor de escucha es el destinatario esperado.</span><span class="sxs-lookup"><span data-stu-id="bc468-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="bc468-205">Tenga en cuenta que el agente usa la comprobación de huella digital del certificado (en lugar de la verificación en cadena).</span><span class="sxs-lookup"><span data-stu-id="bc468-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="bc468-206">No realizará la validación completa del certificado porque es posible usar certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="bc468-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="bc468-207">Una vez que el agente está satisfecho con que la escucha es autenticada, el agente presentará una contraseña que, a continuación, la agente de escucha comprobará.</span><span class="sxs-lookup"><span data-stu-id="bc468-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="bc468-208">El agente comienza a transmitir datos de rendimiento a través de la conexión a la escucha.</span><span class="sxs-lookup"><span data-stu-id="bc468-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="bc468-209">Más información</span><span class="sxs-lookup"><span data-stu-id="bc468-209">For more information</span></span>
<span data-ttu-id="bc468-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="bc468-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="bc468-211">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bc468-211">For more information, see the following:</span></span>

- [<span data-ttu-id="bc468-212">Implementar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc468-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="bc468-213">Actualizar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc468-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="bc468-214">Solucionar problemas del administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc468-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
