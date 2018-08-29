---
title: Planeación para el Administrador de estadísticas de Skype para Business Server 2015
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
description: 'Resumen: Lea este tema para obtener más información acerca del Administrador de estadísticas de Skype para Business Server 2015.'
ms.openlocfilehash: de4f2bedcbd03191b852366504423ebb031cf5f1
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244009"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="d3af2-103">Planeación para el Administrador de estadísticas de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d3af2-103">Plan for Statistics Manager for Skype for Business Server 2015</span></span>

<span data-ttu-id="d3af2-104">**Resumen:** Lea este tema para obtener más información acerca del Administrador de estadísticas de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d3af2-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server 2015.</span></span>

 <span data-ttu-id="d3af2-105">Administrador de estadísticas de Skype para Business Server es una herramienta eficaz que le permite ver Skype para los datos de estado y rendimiento de servidor empresarial en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="d3af2-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="d3af2-106">Puede sondear los datos de rendimiento a través de cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio Web de estadísticas de administrador.</span><span class="sxs-lookup"><span data-stu-id="d3af2-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="d3af2-107">Puede usar el Administrador de estadísticas para identificar problemas de rendimiento en curso, ver los resultados de un cambio planeado a su entorno, realizar un seguimiento de resolución de interrupciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="d3af2-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="d3af2-108">Fuera del cuadro, Administrador de estadísticas está configurado con los umbrales de indicador de estado de clave (KHI) y se puede personalizar para adaptarse a necesidades específicas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="d3af2-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="d3af2-109">Puede implementar las estadísticas de administrador en una implementación local en la que un único servidor hospeda todos los componentes de estadísticas administrador del servidor.</span><span class="sxs-lookup"><span data-stu-id="d3af2-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="d3af2-110">Para obtener más información sobre la implementación de las estadísticas de administrador, vea [Implementar el Administrador de estadísticas de Skype para Business Server 2015](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="d3af2-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="d3af2-111">Si ya tiene una implementación existente de las estadísticas de administrador, pero aún no ha actualizado a la versión 1.1, vea [¿Qué es nuevo en la versión 1.1](plan.md#BKMK_WhatsNew) y [Actualizar las estadísticas de administrador de Skype para Business Server 2015](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="d3af2-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 1.1, see [What's new in Release 1.1](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>

<span data-ttu-id="d3af2-112">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3af2-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="d3af2-113">Características y funciones</span><span class="sxs-lookup"><span data-stu-id="d3af2-113">Features and capabilities</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)

- [<span data-ttu-id="d3af2-114">¿Qué es nuevo en la versión 1.1</span><span class="sxs-lookup"><span data-stu-id="d3af2-114">What's new in Release 1.1</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="d3af2-115">Componentes</span><span class="sxs-lookup"><span data-stu-id="d3af2-115">Components</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)

- [<span data-ttu-id="d3af2-116">Implementación local</span><span class="sxs-lookup"><span data-stu-id="d3af2-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="d3af2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3af2-117">Requirements</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)

- [<span data-ttu-id="d3af2-118">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="d3af2-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="d3af2-119">Características y funciones</span><span class="sxs-lookup"><span data-stu-id="d3af2-119">Features and capabilities</span></span>
<span data-ttu-id="d3af2-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="d3af2-120"></span></span>

<span data-ttu-id="d3af2-121">Administrador de estadísticas le permite:</span><span class="sxs-lookup"><span data-stu-id="d3af2-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="d3af2-122">Ver datos sin procesar para todos los servidores en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="d3af2-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="d3af2-123">(Datos se muestrea a una tasa muy alta y enviados al sitio Web en menos de un segundo.)</span><span class="sxs-lookup"><span data-stu-id="d3af2-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="d3af2-124">Ver los datos que se agregan a un rol específico; Por ejemplo, servidor Front-End, el servidor de mediación, servidor perimetral y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="d3af2-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="d3af2-125">Explorar en profundidad datos de vista para sitios específicos, grupos de servidores específicos dentro del sitio y servidores específicos, a continuación, dentro del grupo.</span><span class="sxs-lookup"><span data-stu-id="d3af2-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="d3af2-126">Crear gráficos personalizados para que elegido contadores se muestran de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d3af2-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="d3af2-127">Zoom y panorámica en ambos los ejes x e y- o en el eje x únicamente.</span><span class="sxs-lookup"><span data-stu-id="d3af2-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="d3af2-128">Usar los intervalos de fechas o puntos en el tiempo para filtrar los datos.</span><span class="sxs-lookup"><span data-stu-id="d3af2-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="d3af2-129">Ver el rendimiento del servidor en función de indicadores clave de estado establecido (KHIs).</span><span class="sxs-lookup"><span data-stu-id="d3af2-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="d3af2-130">KHIs representan una colección de contadores de rendimiento con un rango definido correcto.</span><span class="sxs-lookup"><span data-stu-id="d3af2-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="d3af2-131">Ver las métricas detalladas de cada contador.</span><span class="sxs-lookup"><span data-stu-id="d3af2-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="d3af2-132">Comparar datos en varios servidores o poblaciones.</span><span class="sxs-lookup"><span data-stu-id="d3af2-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="d3af2-133">Visualización de informes de contador latente para identificar a los agentes que no son informes de datos actuales para el servicio de panel.</span><span class="sxs-lookup"><span data-stu-id="d3af2-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="d3af2-134">Guardar una instancia determinada de los datos del gráfico en un archivo.</span><span class="sxs-lookup"><span data-stu-id="d3af2-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="d3af2-135">Vista KHIs en tiempo real, incluidas las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="d3af2-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="d3af2-136">Si está habilitada la vista Historial, se muestran sólo los errores de nuevo.</span><span class="sxs-lookup"><span data-stu-id="d3af2-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="d3af2-137">Ver todos los KHIs a la vez</span><span class="sxs-lookup"><span data-stu-id="d3af2-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="d3af2-138">Ver KHIs por servidor (vista horizontal)</span><span class="sxs-lookup"><span data-stu-id="d3af2-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="d3af2-139">Definiciones de vista KHI</span><span class="sxs-lookup"><span data-stu-id="d3af2-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-11"></a><span data-ttu-id="d3af2-140">¿Qué es nuevo en la versión 1.1</span><span class="sxs-lookup"><span data-stu-id="d3af2-140">What's new in Release 1.1</span></span>
<span data-ttu-id="d3af2-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="d3af2-141"></span></span>

<span data-ttu-id="d3af2-142">El siguiente describe cuáles son las novedades en la versión 1.1.</span><span class="sxs-lookup"><span data-stu-id="d3af2-142">The following describes what's new in Release 1.1.</span></span> <span data-ttu-id="d3af2-143">Si tiene una implementación existente del Administrador de estadísticas y aún no se ha realizado la actualización, vea [Actualizar administrador de estadísticas de Skype para Business Server 2015](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="d3af2-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>

- <span data-ttu-id="d3af2-144">Se han agregado las vistas de escenario para medios perimetrales, estado de Fabric, conmutación por error y escenarios de registro.</span><span class="sxs-lookup"><span data-stu-id="d3af2-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="d3af2-145">PerfAgentStorageManager.exe línea de comandos (instalado con el agente de escucha) ahora pueden exportar los datos del contador como un CSV.</span><span class="sxs-lookup"><span data-stu-id="d3af2-145">Command line PerfAgentStorageManager.exe (installed with the Listener) can now export counter data as a CSV.</span></span>

- <span data-ttu-id="d3af2-146">Muchos contadores nuevos se han agregado para servidores SQL Server, más de los contadores de Windows Fabric, más Skype para contadores de uso empresarial y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="d3af2-146">Many new counters have been added for SQL servers, more Windows Fabric counters, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="d3af2-147">Integración de nodo de monitor para el agente de administrador de estadísticas - si el agente está instalado en un nodo de monitor, informará de las estadísticas de transacciones sintéticas como contadores de vuelta al administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="d3af2-147">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="d3af2-148">Numerosas mejoras de rendimiento y confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="d3af2-148">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="d3af2-149">Para comprobar la versión del sitio Web de estadísticas de administrador está ejecutando:</span><span class="sxs-lookup"><span data-stu-id="d3af2-149">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="d3af2-150">En el Explorador de archivos, abra (directorio predeterminado) C:\Program Files\Skype para Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="d3af2-150">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="d3af2-151">Haga clic con el botón secundario en StatsManHubWebSite.dll y ver sus propiedades</span><span class="sxs-lookup"><span data-stu-id="d3af2-151">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="d3af2-152">La versión del producto se mostrará en los detalles de Descripción.</span><span class="sxs-lookup"><span data-stu-id="d3af2-152">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="d3af2-153">Components</span><span class="sxs-lookup"><span data-stu-id="d3af2-153">Components</span></span>
<span data-ttu-id="d3af2-154"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="d3af2-154"></span></span>

<span data-ttu-id="d3af2-155">Administrador de estadísticas consta de los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="d3af2-155">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="d3af2-156">**Agente.**</span><span class="sxs-lookup"><span data-stu-id="d3af2-156">**Agent.**</span></span> <span data-ttu-id="d3af2-157">Un agente ligero que se ejecuta en cada servidor supervisado.</span><span class="sxs-lookup"><span data-stu-id="d3af2-157">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="d3af2-158">El agente permite sondeo configurable alta tasa de contadores de rendimiento con agregación local.</span><span class="sxs-lookup"><span data-stu-id="d3af2-158">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="d3af2-159">**Agente de escucha.**</span><span class="sxs-lookup"><span data-stu-id="d3af2-159">**Listener.**</span></span> <span data-ttu-id="d3af2-160">La API de lado servidor que recibe los datos de todos los agentes y agrega datos a través de poblaciones.</span><span class="sxs-lookup"><span data-stu-id="d3af2-160">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="d3af2-161">**Concentrador.**</span><span class="sxs-lookup"><span data-stu-id="d3af2-161">**Hub.**</span></span> <span data-ttu-id="d3af2-162">Actúa como la API de cliente para el sistema, se ejecuta en los servidores web y proporciona las actualizaciones de datos en tiempo real a los clientes conectados a través del sitio Web.</span><span class="sxs-lookup"><span data-stu-id="d3af2-162">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="d3af2-163">(El concentrador se instala automáticamente como parte del sitio Web msi).</span><span class="sxs-lookup"><span data-stu-id="d3af2-163">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="d3af2-164">**Sitio Web.**</span><span class="sxs-lookup"><span data-stu-id="d3af2-164">**Website.**</span></span> <span data-ttu-id="d3af2-165">Una interfaz de usuario que reúne todas las características disponibles en el sistema.</span><span class="sxs-lookup"><span data-stu-id="d3af2-165">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="d3af2-166">Además, el Administrador de estadísticas requiere **Redis**, un servidor de estructura de datos de origen para abrir para almacenar en caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="d3af2-166">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="d3af2-167">Para obtener más información acerca de cómo descargar Redis, vea [Implementar el Administrador de estadísticas](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="d3af2-167">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="d3af2-168">Implementación local</span><span class="sxs-lookup"><span data-stu-id="d3af2-168">On-premises deployment</span></span>
<span data-ttu-id="d3af2-169"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="d3af2-169"></span></span>

<span data-ttu-id="d3af2-170">En una implementación local, un único servidor hospeda todos los componentes de estadísticas administrador del servidor.</span><span class="sxs-lookup"><span data-stu-id="d3af2-170">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="d3af2-171">En el siguiente diagrama se muestra una implementación local, en el que se hospedan el sitio Web del Administrador de estadísticas, concentrador, agente de escucha y Redis almacenamiento en memoria caché del sistema en un solo equipo.</span><span class="sxs-lookup"><span data-stu-id="d3af2-171">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="d3af2-172">Administrador de estadísticas está supervisando tres Skype para servidores empresariales, cada uno de los cuales tiene un único agente de transmisión de datos a la escucha.</span><span class="sxs-lookup"><span data-stu-id="d3af2-172">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="d3af2-173">Los usuarios se conectan a un solo sitio Web para ver todos los datos agregados por el Administrador de estadísticas:</span><span class="sxs-lookup"><span data-stu-id="d3af2-173">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Implementación local del administrador de estadísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="d3af2-175">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3af2-175">Requirements</span></span>
<span data-ttu-id="d3af2-176"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="d3af2-176"></span></span>

<span data-ttu-id="d3af2-177">Debe tener en cuenta los siguientes requisitos de hardware, redes y software antes de implementar las estadísticas de administrador.</span><span class="sxs-lookup"><span data-stu-id="d3af2-177">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="d3af2-178">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="d3af2-178">Software requirements</span></span>

- <span data-ttu-id="d3af2-179">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d3af2-179">Windows Server 2012 R2</span></span>

- <span data-ttu-id="d3af2-180">IIS (instalados automáticamente)</span><span class="sxs-lookup"><span data-stu-id="d3af2-180">IIS (automatically installed)</span></span>

- <span data-ttu-id="d3af2-181">Redis</span><span class="sxs-lookup"><span data-stu-id="d3af2-181">Redis</span></span>

- <span data-ttu-id="d3af2-182">Servicios de administrador de estadísticas (instalados automáticamente)</span><span class="sxs-lookup"><span data-stu-id="d3af2-182">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="d3af2-183">PSExec - necesario para realizar la implementación de agentes remotos</span><span class="sxs-lookup"><span data-stu-id="d3af2-183">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="d3af2-184">.NET 4.5 (incluido con 2012 R2) - necesario para los componentes del lado del servidor</span><span class="sxs-lookup"><span data-stu-id="d3af2-184">.NET 4.5 (included with 2012 R2) - Required for server-side components</span></span>

- <span data-ttu-id="d3af2-185">.NET 4.0 - necesarios para los agentes</span><span class="sxs-lookup"><span data-stu-id="d3af2-185">.NET 4.0 - Required for agents</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="d3af2-186">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="d3af2-186">Networking requirements</span></span>


|<span data-ttu-id="d3af2-187">**Servidor de hospedaje**</span><span class="sxs-lookup"><span data-stu-id="d3af2-187">**Hosting server**</span></span>|<span data-ttu-id="d3af2-188">**Agentes.**</span><span class="sxs-lookup"><span data-stu-id="d3af2-188">**Agents**</span></span>|<span data-ttu-id="d3af2-189">**Agente de escucha**</span><span class="sxs-lookup"><span data-stu-id="d3af2-189">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3af2-190">La red de gigabit mínimo dúplex completo.</span><span class="sxs-lookup"><span data-stu-id="d3af2-190">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="d3af2-191">Puerto TCP saliente 8443 (número de puerto personalizable) para comunicarse con el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="d3af2-191">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="d3af2-192">El puerto de escucha debe ser el mismo en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="d3af2-192">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="d3af2-193">El puerto TCP 80 o 443 abierto para hospedar el sitio Web de entrada.</span><span class="sxs-lookup"><span data-stu-id="d3af2-193">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="d3af2-194">El puerto TCP 8443 (número de puerto personalizable) de entrada para que los agentes para comunicarse con él.</span><span class="sxs-lookup"><span data-stu-id="d3af2-194">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="d3af2-195">Durante la instalación, se crean automáticamente los puertos de firewall para el agente de escucha y el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="d3af2-195">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="d3af2-196">Para los agentes, la instalación se da por supuesto que se permiten las conexiones TCP salientes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d3af2-196">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="d3af2-197">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="d3af2-197">Hardware requirements</span></span>

<span data-ttu-id="d3af2-198">En una implementación local, en la que un único servidor hospeda todos los componentes de administrador de las estadísticas del servidor, un servidor con 16 GB de RAM y 4 de la CPU debe ser capaz de admitir aproximadamente 150 muestras por segundo en promedio.</span><span class="sxs-lookup"><span data-stu-id="d3af2-198">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="d3af2-199">Para determinar cuántos contadores/agentes puede admitir, use el siguiente cálculo:</span><span class="sxs-lookup"><span data-stu-id="d3af2-199">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="d3af2-200">100 servidores \*contadores de 80 \* 1 ejemplo por minuto de cada agente / 60 segundos = ~ 133 muestras por segundo.</span><span class="sxs-lookup"><span data-stu-id="d3af2-200">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="d3af2-201">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="d3af2-201">Security considerations</span></span>
<span data-ttu-id="d3af2-202"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="d3af2-202"></span></span>

<span data-ttu-id="d3af2-203">Se cifra todo el tráfico entre servidores.</span><span class="sxs-lookup"><span data-stu-id="d3af2-203">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="d3af2-204">Tráfico HTTPS cifrado se enviarán a través del puerto 8443 (de forma predeterminada) del agente de en el servidor de agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="d3af2-204">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="d3af2-205">El agente de comprobará si la huella digital SSL en el servidor para asegurarse de que el servidor de agente de escucha es el destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="d3af2-205">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="d3af2-206">Tenga en cuenta que el agente usa verificación de certificados por huella digital (en lugar de verificación en cadena).</span><span class="sxs-lookup"><span data-stu-id="d3af2-206">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="d3af2-207">No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="d3af2-207">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="d3af2-208">Después de que el agente esté satisfecho el agente de escucha es auténtico, se le presentará una contraseña por el agente que, a continuación, se comprueba el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="d3af2-208">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="d3af2-209">El agente de comienza la transmisión de datos de rendimiento a través de la conexión con el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="d3af2-209">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d3af2-210">Más información</span><span class="sxs-lookup"><span data-stu-id="d3af2-210">For more information</span></span>
<span data-ttu-id="d3af2-211"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="d3af2-211"></span></span>

<span data-ttu-id="d3af2-212">Para obtener más información, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3af2-212">For more information, see the following:</span></span>

- [<span data-ttu-id="d3af2-213">Implementar el administrador de estadísticas para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d3af2-213">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)

- [<span data-ttu-id="d3af2-214">Actualizar el administrador de estadísticas para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d3af2-214">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>](upgrade.md)

- [<span data-ttu-id="d3af2-215">Solucionar problemas del administrador de estadísticas para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d3af2-215">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)

- [<span data-ttu-id="d3af2-216">Skype para Business Server Manager de estadísticas de blog</span><span class="sxs-lookup"><span data-stu-id="d3af2-216">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)


