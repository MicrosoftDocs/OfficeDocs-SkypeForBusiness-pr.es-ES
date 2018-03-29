---
title: Plan para el Gestor de estadísticas de Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/23/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumen: Leer este tema para aprender sobre el Gestor de estadísticas de Skype para Business Server 2015.'
ms.openlocfilehash: 63f064f9a6632250f3cfadddbcbb5fca2120f07b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="fe0cb-103">Plan para el Gestor de estadísticas de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe0cb-103">Plan for Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fe0cb-104">**Resumen:** Lea este tema para aprender sobre el Gestor de estadísticas de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="fe0cb-105">Administrador de estadísticas de Skype para Business Server es una eficaz herramienta que permite ver Skype para los datos de rendimiento y la salud de Business Server en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="fe0cb-106">Puede sondear los datos de rendimiento a través de cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio Web del Administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="fe0cb-107">Puede utilizar Administrador de estadísticas para identificar problemas de rendimiento en curso, ver los resultados de un cambio planificado para su entorno, realizar un seguimiento de la resolución de las interrupciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="fe0cb-108">Fuera de la caja, Gestor de estadísticas está configurado con umbrales del indicador de estado de clave (KHI) y pueden personalizarse para satisfacer las necesidades únicas de su implementación.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span> 
  
<span data-ttu-id="fe0cb-109">Gestor de estadísticas se pueden implementar en una implementación de local en la que un único servidor aloja todos los componentes del Administrador de las estadísticas del servidor.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="fe0cb-110">Para obtener más información acerca de cómo implementar el Gestor de estadísticas, vea [Implementar Administrador de estadísticas de Skype para Business Server 2015](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="fe0cb-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="fe0cb-111">Si ya tiene una implementación existente de gestor de estadísticas, pero aún no ha actualizado a la versión 1.1, vea [Novedades de versión 1.1](plan.md#BKMK_WhatsNew) y [Actualizar estadísticas Administrador de Skype para Business Server 2015](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="fe0cb-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 1.1, see [What's new in Release 1.1](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>
  
<span data-ttu-id="fe0cb-112">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe0cb-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="fe0cb-113">Características y funciones</span><span class="sxs-lookup"><span data-stu-id="fe0cb-113">Features and capabilities</span></span>](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)
    
- [<span data-ttu-id="fe0cb-114">Novedades de la versión 1.1</span><span class="sxs-lookup"><span data-stu-id="fe0cb-114">What's new in Release 1.1</span></span>](plan.md#BKMK_WhatsNew)
    
- [<span data-ttu-id="fe0cb-115">Componentes</span><span class="sxs-lookup"><span data-stu-id="fe0cb-115">Components</span></span>](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)
    
- [<span data-ttu-id="fe0cb-116">Implementación local</span><span class="sxs-lookup"><span data-stu-id="fe0cb-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)
    
- [<span data-ttu-id="fe0cb-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe0cb-117">Requirements</span></span>](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)
    
- [<span data-ttu-id="fe0cb-118">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="fe0cb-118">Security considerations</span></span>](plan.md#BKMK_Security)
    
## <a name="features-and-capabilities"></a><span data-ttu-id="fe0cb-119">Características y funciones</span><span class="sxs-lookup"><span data-stu-id="fe0cb-119">Features and capabilities</span></span>
<span data-ttu-id="fe0cb-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="fe0cb-120"></span></span>

<span data-ttu-id="fe0cb-121">Gestor de estadísticas le permite:</span><span class="sxs-lookup"><span data-stu-id="fe0cb-121">Statistics Manager allows you to:</span></span>
  
- <span data-ttu-id="fe0cb-122">Ver los datos sin procesar para todos los servidores en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="fe0cb-123">(Datos se muestrean a una velocidad muy alta y enviados al sitio Web en menos de un segundo.)</span><span class="sxs-lookup"><span data-stu-id="fe0cb-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>
    
- <span data-ttu-id="fe0cb-124">Ver los datos que se agregan a una función específica; Por ejemplo, servidor Front-End, servidor de mediación, servidor perimetral y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>
    
- <span data-ttu-id="fe0cb-125">Profundizar para ver datos de sitios específicos, grupos específicos dentro del sitio y servidores específicos, a continuación, en la agrupación.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>
    
- <span data-ttu-id="fe0cb-126">Crear gráficos personalizados para que elige los contadores aparecen de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-126">Create custom charts so that chosen counters are shown by default.</span></span>
    
- <span data-ttu-id="fe0cb-127">Zoom y panorámica en ambos los ejes x e y- o en el eje x únicamente.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>
    
- <span data-ttu-id="fe0cb-128">Utilizar rangos de fechas o puntos en el tiempo para filtrar los datos.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-128">Use date ranges or points in time to filter data.</span></span> 
    
- <span data-ttu-id="fe0cb-129">Ver el rendimiento del servidor basándose en indicadores clave de estado establecido (KHIs).</span><span class="sxs-lookup"><span data-stu-id="fe0cb-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="fe0cb-130">KHIs representan un conjunto de contadores de rendimiento con un rango saludable definido.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span> 
    
- <span data-ttu-id="fe0cb-131">Ver las métricas detalladas para cada contador.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-131">View detailed metrics for each counter.</span></span>
    
- <span data-ttu-id="fe0cb-132">Comparar datos entre varios servidores o poblaciones.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-132">Compare data across multiple populations or servers.</span></span>
    
- <span data-ttu-id="fe0cb-133">Ver informes de contador latente para identificar los agentes que no están reportando datos actuales para el servicio de escritorio.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>
    
- <span data-ttu-id="fe0cb-134">Guardar una instancia determinada de los datos del gráfico en un archivo.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-134">Save a particular instance of chart data to a file.</span></span>
    
- <span data-ttu-id="fe0cb-135">KHIs vista en tiempo real, incluidas las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="fe0cb-136">Si está habilitada la vista Historial, se muestran sólo los nuevos errores.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-136">If the history view is enabled, only new failures are shown.</span></span>
    
  - <span data-ttu-id="fe0cb-137">Ver al mismo tiempo todos los KHIs</span><span class="sxs-lookup"><span data-stu-id="fe0cb-137">View all KHIs at one time</span></span>
    
  - <span data-ttu-id="fe0cb-138">Ver KHIs por servidor (vista horizontal)</span><span class="sxs-lookup"><span data-stu-id="fe0cb-138">View KHIs by server (Landscape view)</span></span>
    
  - <span data-ttu-id="fe0cb-139">Definiciones de vista KHI</span><span class="sxs-lookup"><span data-stu-id="fe0cb-139">View KHI definitions</span></span>
    
## <a name="whats-new-in-release-11"></a><span data-ttu-id="fe0cb-140">Novedades de la versión 1.1</span><span class="sxs-lookup"><span data-stu-id="fe0cb-140">What's new in Release 1.1</span></span>
<span data-ttu-id="fe0cb-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="fe0cb-141"></span></span>

<span data-ttu-id="fe0cb-142">A continuación describen qué es lo nuevo en la versión 1.1.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-142">The following describes what's new in Release 1.1.</span></span> <span data-ttu-id="fe0cb-143">Si tiene una implementación existente de estadísticas Manager y aún no ha realizado la actualización, vea [Actualizar estadísticas Administrador de Skype para Business Server 2015](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="fe0cb-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>
  
- <span data-ttu-id="fe0cb-144">Vistas del escenario se han agregado para medios de borde, tela de salud, grupo de conmutación por error y escenarios de registro.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>
    
- <span data-ttu-id="fe0cb-145">PerfAgentStorageManager.exe línea de comandos (que se instala con el agente de escucha) pueden exportar los datos del contador como un CSV.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-145">Command line PerfAgentStorageManager.exe (installed with the Listener) can now export counter data as a CSV.</span></span>
    
- <span data-ttu-id="fe0cb-146">Muchos contadores nuevos se han agregado servidores SQL, más contadores Fabric de Windows, más Skype para contadores de uso del negocio y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-146">Many new counters have been added for SQL servers, more Windows Fabric counters, more Skype for Business usage counters, and so on.</span></span>
    
- <span data-ttu-id="fe0cb-147">Integración de nodo supervisora para el agente Administrador de estadísticas - si el agente está instalado en un nodo supervisora, informará de las estadísticas de transacciones sintéticas como contadores de volver al administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-147">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>
    
- <span data-ttu-id="fe0cb-148">Numerosas mejoras de confiabilidad y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-148">Numerous reliability and performance improvements.</span></span>
    
<span data-ttu-id="fe0cb-149">Para comprobar la versión del sitio Web del Administrador de estadísticas está ejecutando:</span><span class="sxs-lookup"><span data-stu-id="fe0cb-149">To verify the version of the Statistics Manager Website you are running:</span></span>
  
- <span data-ttu-id="fe0cb-150">En el Explorador de archivos, abrir (el directorio por defecto) C:\Program Files\Skype para Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="fe0cb-150">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>
    
- <span data-ttu-id="fe0cb-151">Haga clic con el botón secundario en StatsManHubWebSite.dll y ver sus propiedades</span><span class="sxs-lookup"><span data-stu-id="fe0cb-151">Right click on StatsManHubWebSite.dll and view its properties</span></span>
    
- <span data-ttu-id="fe0cb-152">La versión del producto se mostrará en los detalles de Descripción.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-152">The product version will be shown in the Description details.</span></span>
    
## <a name="components"></a><span data-ttu-id="fe0cb-153">Components</span><span class="sxs-lookup"><span data-stu-id="fe0cb-153">Components</span></span>
<span data-ttu-id="fe0cb-154"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="fe0cb-154"></span></span>

<span data-ttu-id="fe0cb-155">Gestor de estadísticas consta de los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="fe0cb-155">Statistics Manager consists of the following components:</span></span>
  
- <span data-ttu-id="fe0cb-156">**Agente.**</span><span class="sxs-lookup"><span data-stu-id="fe0cb-156">**Agent.**</span></span> <span data-ttu-id="fe0cb-157">Un agente ligero que se ejecuta en cada servidor supervisado.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-157">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="fe0cb-158">El agente permite sondeo configurables alta tasa de contadores de rendimiento con la agregación local.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-158">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>
    
- <span data-ttu-id="fe0cb-159">**Agente de escucha.**</span><span class="sxs-lookup"><span data-stu-id="fe0cb-159">**Listener.**</span></span> <span data-ttu-id="fe0cb-160">La API del lado servidor que recibe los datos de todos los agentes y agrega los datos a través de las poblaciones.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-160">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>
    
- <span data-ttu-id="fe0cb-161">**Concentrador.**</span><span class="sxs-lookup"><span data-stu-id="fe0cb-161">**Hub.**</span></span> <span data-ttu-id="fe0cb-162">Sirve como la API de cliente para el sistema, se ejecuta en los servidores web y proporciona las actualizaciones de datos en tiempo real a los clientes conectados a través del sitio Web.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-162">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="fe0cb-163">(El concentrador se instala automáticamente como parte del sitio Web msi).</span><span class="sxs-lookup"><span data-stu-id="fe0cb-163">(The Hub is automatically installed as part of the Website msi.)</span></span>
    
- <span data-ttu-id="fe0cb-164">**Sitio Web.**</span><span class="sxs-lookup"><span data-stu-id="fe0cb-164">**Website.**</span></span> <span data-ttu-id="fe0cb-165">Una interfaz de usuario que reúne todas las características disponibles en el sistema.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-165">A user interface that pulls together all the features available in the system.</span></span>
    
<span data-ttu-id="fe0cb-166">Además, el Administrador de estadísticas requiere **Redis**, un servidor de estructura de datos de código abierto para el almacenamiento en caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-166">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="fe0cb-167">Para obtener más información acerca de cómo descargar Redis, vea [Implementar Gestor de estadísticas](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="fe0cb-167">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>
  
## <a name="on-premises-deployment"></a><span data-ttu-id="fe0cb-168">Implementación local</span><span class="sxs-lookup"><span data-stu-id="fe0cb-168">On-premises deployment</span></span>
<span data-ttu-id="fe0cb-169"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="fe0cb-169"></span></span>

<span data-ttu-id="fe0cb-170">En una implementación local, un único servidor aloja todos los componentes del Administrador de las estadísticas del servidor.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-170">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span> 
  
<span data-ttu-id="fe0cb-171">El diagrama siguiente muestra una implementación local, en la que el sitio Web del Administrador de estadísticas, concentrador, escucha y Redis caché sistema se alojan en un solo equipo.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-171">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="fe0cb-172">Gestor de estadísticas está supervisando tres Skype para servidores empresariales, cada uno de los cuales tiene un solo agente de transmisión de datos a la escucha.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-172">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="fe0cb-173">Los usuarios conectarse a un solo sitio Web para ver todos los datos agregados por el Administrador de estadísticas:</span><span class="sxs-lookup"><span data-stu-id="fe0cb-173">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>
  
![Implementación local del administrador de estadísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)
  
## <a name="requirements"></a><span data-ttu-id="fe0cb-175">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe0cb-175">Requirements</span></span>
<span data-ttu-id="fe0cb-176"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="fe0cb-176"></span></span>

<span data-ttu-id="fe0cb-177">Debe tener en cuenta los siguientes requisitos de hardware, redes y software antes de implementar Administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-177">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span> 
  
### <a name="software-requirements"></a><span data-ttu-id="fe0cb-178">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="fe0cb-178">Software requirements</span></span>

- <span data-ttu-id="fe0cb-179">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="fe0cb-179">Windows Server 2012 R2</span></span>
    
- <span data-ttu-id="fe0cb-180">IIS (instalados automáticamente)</span><span class="sxs-lookup"><span data-stu-id="fe0cb-180">IIS (automatically installed)</span></span>
    
- <span data-ttu-id="fe0cb-181">Redis</span><span class="sxs-lookup"><span data-stu-id="fe0cb-181">Redis</span></span>
    
- <span data-ttu-id="fe0cb-182">Servicios de gestor de estadísticas (instalados automáticamente)</span><span class="sxs-lookup"><span data-stu-id="fe0cb-182">Statistics Manager services (automatically installed)</span></span>
    
- <span data-ttu-id="fe0cb-183">PSExec - necesario para realizar el despliegue del agente remoto</span><span class="sxs-lookup"><span data-stu-id="fe0cb-183">PSExec - Required to do remote agent deployment</span></span>
    
- <span data-ttu-id="fe0cb-184">4.5 de .NET (incluido con 2012 R2) - necesario para los componentes del servidor</span><span class="sxs-lookup"><span data-stu-id="fe0cb-184">.NET 4.5 (included with 2012 R2) - Required for server-side components</span></span>
    
- <span data-ttu-id="fe0cb-185">.NET 4.0 - requerido para agentes</span><span class="sxs-lookup"><span data-stu-id="fe0cb-185">.NET 4.0 - Required for agents</span></span>
    
### <a name="networking-requirements"></a><span data-ttu-id="fe0cb-186">Requisitos para redes</span><span class="sxs-lookup"><span data-stu-id="fe0cb-186">Networking requirements</span></span>


|<span data-ttu-id="fe0cb-187">**Servidor de alojamiento**</span><span class="sxs-lookup"><span data-stu-id="fe0cb-187">**Hosting server**</span></span>|<span data-ttu-id="fe0cb-188">**Agentes.**</span><span class="sxs-lookup"><span data-stu-id="fe0cb-188">**Agents**</span></span>|<span data-ttu-id="fe0cb-189">**Agente de escucha**</span><span class="sxs-lookup"><span data-stu-id="fe0cb-189">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fe0cb-190">Red gigabit mínimo dúplex completo.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-190">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="fe0cb-191">Puerto TCP saliente 8443 (número de puerto personalizables) para comunicarse con el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-191">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="fe0cb-192">El puerto de escucha debe ser el mismo en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-192">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="fe0cb-193">El puerto TCP 80 o 443 abierto para alojar el sitio Web de entrada.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-193">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="fe0cb-194">Puerto TCP 8443 (número de puerto personalizable) de entrada de los agentes para comunicarse con él.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-194">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||
   
<span data-ttu-id="fe0cb-195">Durante la instalación, se crean automáticamente los puertos de firewall para la escucha y el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-195">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="fe0cb-196">Para los agentes, la instalación supone que se permiten las conexiones TCP salientes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-196">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>
  
### <a name="hardware-requirements"></a><span data-ttu-id="fe0cb-197">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="fe0cb-197">Hardware requirements</span></span>

<span data-ttu-id="fe0cb-198">En una implementación local, en la que un único servidor aloja todos los componentes de administrador de las estadísticas del servidor, un servidor con 16 GB de RAM y 4 CPU debe ser capaz de admitir en promedio unos 150 muestras por segundo.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-198">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="fe0cb-199">Para determinar cuántos contadores/agentes puede admitir, utilice el siguiente cálculo:</span><span class="sxs-lookup"><span data-stu-id="fe0cb-199">To determine how many counters/agents you can support, use the following calculation:</span></span> 
  
<span data-ttu-id="fe0cb-200">100 servidores \*80 contadores \* 1 ejemplo por minuto de cada agente / 60 segundos = ~ 133 muestras por segundo.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-200">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>
  
## <a name="security-considerations"></a><span data-ttu-id="fe0cb-201">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="fe0cb-201">Security considerations</span></span>
<span data-ttu-id="fe0cb-202"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="fe0cb-202"></span></span>

<span data-ttu-id="fe0cb-203">Se cifra todo el tráfico entre servidores.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-203">All traffic between servers is encrypted.</span></span> 
  
- <span data-ttu-id="fe0cb-204">Tráfico HTTPS cifrado se enviará por el puerto 8443 (por defecto) desde el agente al servidor de agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-204">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>
    
- <span data-ttu-id="fe0cb-205">El agente comprobará la huella digital SSL en el servidor para asegurarse de que el servidor de agente de escucha es el destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-205">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="fe0cb-206">Tenga en cuenta que el agente usa verificación de certificados por huella digital (en lugar de verificación en cadena).</span><span class="sxs-lookup"><span data-stu-id="fe0cb-206">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="fe0cb-207">No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-207">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
- <span data-ttu-id="fe0cb-208">Una vez satisfecho el agente el agente de escucha es auténtico, una contraseña será presentada por el agente que después es confirmado por el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-208">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span> 
    
- <span data-ttu-id="fe0cb-209">El agente comienza a transmitir datos de rendimiento a través de la conexión con el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-209">The Agent begins transmitting performance data over the connection to the Listener.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="fe0cb-210">Más información</span><span class="sxs-lookup"><span data-stu-id="fe0cb-210">For more information</span></span>
<span data-ttu-id="fe0cb-211"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="fe0cb-211"></span></span>

<span data-ttu-id="fe0cb-212">Para obtener más información, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe0cb-212">For more information, see the following:</span></span>
  
- [<span data-ttu-id="fe0cb-213">Implementar el administrador estadísticas de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe0cb-213">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)
    
- [<span data-ttu-id="fe0cb-214">Actualizar estadísticas Administrador de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe0cb-214">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>](upgrade.md)
    
- [<span data-ttu-id="fe0cb-215">Solucionar problemas de administrador de estadísticas de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe0cb-215">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="fe0cb-216">Skype para blog Business Manager de estadísticas de servidor</span><span class="sxs-lookup"><span data-stu-id="fe0cb-216">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

