---
title: Plan para el Administrador de estadísticas de Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumen: Lea este tema para obtener más información acerca del Administrador de estadísticas de Skype para Business Server.'
ms.openlocfilehash: a73e58acdd91b4112537fa0028bf2c134e9c0fce
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297861"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="517d8-103">Plan para el Administrador de estadísticas de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="517d8-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="517d8-104">**Resumen:** Lea este tema para obtener más información acerca del Administrador de estadísticas de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="517d8-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="517d8-105">Administrador de estadísticas de Skype para Business Server es una herramienta eficaz que le permite ver Skype para los datos de estado y rendimiento de servidor empresarial en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="517d8-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="517d8-106">Puede sondear los datos de rendimiento a través de cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio Web de estadísticas de administrador.</span><span class="sxs-lookup"><span data-stu-id="517d8-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="517d8-107">Puede usar el Administrador de estadísticas para identificar problemas de rendimiento en curso, ver los resultados de un cambio planeado a su entorno, realizar un seguimiento de resolución de interrupciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="517d8-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="517d8-108">Fuera del cuadro, Administrador de estadísticas está configurado con los umbrales de indicador de estado de clave (KHI) y se puede personalizar para adaptarse a necesidades específicas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="517d8-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="517d8-109">Puede implementar las estadísticas de administrador en una implementación local en la que un único servidor hospeda todos los componentes de estadísticas administrador del servidor.</span><span class="sxs-lookup"><span data-stu-id="517d8-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="517d8-110">Para obtener más información sobre la implementación de las estadísticas de administrador, vea [Implementar el Administrador de estadísticas de Skype para Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="517d8-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="517d8-111">Si ya tiene una implementación existente de las estadísticas de administrador, pero aún no ha actualizado a la versión 2.0, vea [¿Qué es nuevo en la versión 2.0](plan.md#BKMK_WhatsNew) y [Actualizar las estadísticas de administrador de Skype para Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="517d8-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="517d8-112">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="517d8-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="517d8-113">Características y funciones</span><span class="sxs-lookup"><span data-stu-id="517d8-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="517d8-114">¿Qué es nuevo en la versión 2.0</span><span class="sxs-lookup"><span data-stu-id="517d8-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="517d8-115">Componentes</span><span class="sxs-lookup"><span data-stu-id="517d8-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="517d8-116">Implementación local</span><span class="sxs-lookup"><span data-stu-id="517d8-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="517d8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="517d8-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="517d8-118">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="517d8-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="517d8-119">Características y funciones</span><span class="sxs-lookup"><span data-stu-id="517d8-119">Features and capabilities</span></span>
<span data-ttu-id="517d8-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="517d8-120"></span></span>

<span data-ttu-id="517d8-121">Administrador de estadísticas le permite:</span><span class="sxs-lookup"><span data-stu-id="517d8-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="517d8-122">Ver datos sin procesar para todos los servidores en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="517d8-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="517d8-123">(Datos se muestrea a una tasa muy alta y enviados al sitio Web en menos de un segundo.)</span><span class="sxs-lookup"><span data-stu-id="517d8-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="517d8-124">Ver los datos que se agregan a un rol específico; Por ejemplo, servidor Front-End, el servidor de mediación, servidor perimetral y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="517d8-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="517d8-125">Explorar en profundidad datos de vista para sitios específicos, grupos de servidores específicos dentro del sitio y servidores específicos, a continuación, dentro del grupo.</span><span class="sxs-lookup"><span data-stu-id="517d8-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="517d8-126">Crear gráficos personalizados para que elegido contadores se muestran de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="517d8-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="517d8-127">Zoom y panorámica en ambos los ejes x e y- o en el eje x únicamente.</span><span class="sxs-lookup"><span data-stu-id="517d8-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="517d8-128">Usar los intervalos de fechas o puntos en el tiempo para filtrar los datos.</span><span class="sxs-lookup"><span data-stu-id="517d8-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="517d8-129">Ver el rendimiento del servidor en función de indicadores clave de estado establecido (KHIs).</span><span class="sxs-lookup"><span data-stu-id="517d8-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="517d8-130">KHIs representan una colección de contadores de rendimiento con un rango definido correcto.</span><span class="sxs-lookup"><span data-stu-id="517d8-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="517d8-131">Ver las métricas detalladas de cada contador.</span><span class="sxs-lookup"><span data-stu-id="517d8-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="517d8-132">Comparar datos en varios servidores o poblaciones.</span><span class="sxs-lookup"><span data-stu-id="517d8-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="517d8-133">Visualización de informes de contador latente para identificar a los agentes que no son informes de datos actuales para el servicio de panel.</span><span class="sxs-lookup"><span data-stu-id="517d8-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="517d8-134">Guardar una instancia determinada de los datos del gráfico en un archivo.</span><span class="sxs-lookup"><span data-stu-id="517d8-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="517d8-135">Vista KHIs en tiempo real, incluidas las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="517d8-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="517d8-136">Si está habilitada la vista Historial, se muestran sólo los errores de nuevo.</span><span class="sxs-lookup"><span data-stu-id="517d8-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="517d8-137">Ver todos los KHIs a la vez</span><span class="sxs-lookup"><span data-stu-id="517d8-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="517d8-138">Ver KHIs por servidor (vista horizontal)</span><span class="sxs-lookup"><span data-stu-id="517d8-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="517d8-139">Definiciones de vista KHI</span><span class="sxs-lookup"><span data-stu-id="517d8-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="517d8-140">¿Qué es nuevo en la versión 2.0</span><span class="sxs-lookup"><span data-stu-id="517d8-140">What's new in Release 2.0</span></span>
<span data-ttu-id="517d8-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="517d8-141"></span></span>

<span data-ttu-id="517d8-142">El siguiente describe cuáles son las novedades en la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="517d8-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="517d8-143">Si tiene una implementación existente del Administrador de estadísticas y aún no se ha realizado la actualización, vea [Actualizar administrador de estadísticas de Skype para Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="517d8-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="517d8-144">Se han agregado las vistas de escenario para medios perimetrales, estado de Fabric, conmutación por error y escenarios de registro.</span><span class="sxs-lookup"><span data-stu-id="517d8-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="517d8-145">Muchos contadores nuevos se han agregado servidores SQL Server, más Skype para contadores de uso empresarial y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="517d8-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="517d8-146">Integración de nodo de monitor para el agente de administrador de estadísticas - si el agente está instalado en un nodo de monitor, informará de las estadísticas de transacciones sintéticas como contadores de vuelta al administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="517d8-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="517d8-147">Numerosas mejoras de rendimiento y confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="517d8-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="517d8-148">Para comprobar la versión del sitio Web de estadísticas de administrador está ejecutando:</span><span class="sxs-lookup"><span data-stu-id="517d8-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="517d8-149">En el Explorador de archivos, abra (directorio predeterminado) C:\Program Files\Skype para Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="517d8-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="517d8-150">Haga clic con el botón secundario en StatsManHubWebSite.dll y ver sus propiedades</span><span class="sxs-lookup"><span data-stu-id="517d8-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="517d8-151">La versión del producto se mostrará en los detalles de Descripción.</span><span class="sxs-lookup"><span data-stu-id="517d8-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="517d8-152">Components</span><span class="sxs-lookup"><span data-stu-id="517d8-152">Components</span></span>
<span data-ttu-id="517d8-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="517d8-153"></span></span>

<span data-ttu-id="517d8-154">Administrador de estadísticas consta de los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="517d8-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="517d8-155">**Agente.**</span><span class="sxs-lookup"><span data-stu-id="517d8-155">**Agent.**</span></span> <span data-ttu-id="517d8-156">Un agente ligero que se ejecuta en cada servidor supervisado.</span><span class="sxs-lookup"><span data-stu-id="517d8-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="517d8-157">El agente permite sondeo configurable alta tasa de contadores de rendimiento con agregación local.</span><span class="sxs-lookup"><span data-stu-id="517d8-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="517d8-158">**Agente de escucha.**</span><span class="sxs-lookup"><span data-stu-id="517d8-158">**Listener.**</span></span> <span data-ttu-id="517d8-159">La API de lado servidor que recibe los datos de todos los agentes y agrega datos a través de poblaciones.</span><span class="sxs-lookup"><span data-stu-id="517d8-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="517d8-160">**Concentrador.**</span><span class="sxs-lookup"><span data-stu-id="517d8-160">**Hub.**</span></span> <span data-ttu-id="517d8-161">Actúa como la API de cliente para el sistema, se ejecuta en los servidores web y proporciona las actualizaciones de datos en tiempo real a los clientes conectados a través del sitio Web.</span><span class="sxs-lookup"><span data-stu-id="517d8-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="517d8-162">(El concentrador se instala automáticamente como parte del sitio Web msi).</span><span class="sxs-lookup"><span data-stu-id="517d8-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="517d8-163">**Sitio Web.**</span><span class="sxs-lookup"><span data-stu-id="517d8-163">**Website.**</span></span> <span data-ttu-id="517d8-164">Una interfaz de usuario que reúne todas las características disponibles en el sistema.</span><span class="sxs-lookup"><span data-stu-id="517d8-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="517d8-165">Además, el Administrador de estadísticas requiere **Redis**, un servidor de estructura de datos de origen para abrir para almacenar en caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="517d8-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="517d8-166">Para obtener más información acerca de cómo descargar Redis, vea [Implementar el Administrador de estadísticas](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="517d8-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="517d8-167">Implementación local</span><span class="sxs-lookup"><span data-stu-id="517d8-167">On-premises deployment</span></span>
<span data-ttu-id="517d8-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="517d8-168"></span></span>

<span data-ttu-id="517d8-169">En una implementación local, un único servidor hospeda todos los componentes de estadísticas administrador del servidor.</span><span class="sxs-lookup"><span data-stu-id="517d8-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="517d8-170">En el siguiente diagrama se muestra una implementación local, en el que se hospedan el sitio Web del Administrador de estadísticas, concentrador, agente de escucha y Redis almacenamiento en memoria caché del sistema en un solo equipo.</span><span class="sxs-lookup"><span data-stu-id="517d8-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="517d8-171">Administrador de estadísticas está supervisando tres Skype para servidores empresariales, cada uno de los cuales tiene un único agente de transmisión de datos a la escucha.</span><span class="sxs-lookup"><span data-stu-id="517d8-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="517d8-172">Los usuarios se conectan a un solo sitio Web para ver todos los datos agregados por el Administrador de estadísticas:</span><span class="sxs-lookup"><span data-stu-id="517d8-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Implementación local del administrador de estadísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="517d8-174">Requisitos</span><span class="sxs-lookup"><span data-stu-id="517d8-174">Requirements</span></span>
<span data-ttu-id="517d8-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="517d8-175"></span></span>

<span data-ttu-id="517d8-176">Debe tener en cuenta los siguientes requisitos de hardware, redes y software antes de implementar las estadísticas de administrador.</span><span class="sxs-lookup"><span data-stu-id="517d8-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="517d8-177">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="517d8-177">Software requirements</span></span>

- <span data-ttu-id="517d8-178">Windows Server 2016 y 2019</span><span class="sxs-lookup"><span data-stu-id="517d8-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="517d8-179">IIS (instalados automáticamente)</span><span class="sxs-lookup"><span data-stu-id="517d8-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="517d8-180">Redis</span><span class="sxs-lookup"><span data-stu-id="517d8-180">Redis</span></span>

- <span data-ttu-id="517d8-181">Servicios de administrador de estadísticas (instalados automáticamente)</span><span class="sxs-lookup"><span data-stu-id="517d8-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="517d8-182">PSExec - necesario para realizar la implementación de agentes remotos</span><span class="sxs-lookup"><span data-stu-id="517d8-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="517d8-183">.NET 4.5 (incluido con 2012 R2) - necesario para los agentes y componentes de servidor</span><span class="sxs-lookup"><span data-stu-id="517d8-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="517d8-184">Descargar el [Skype para Business Server, el Administrador de estadísticas en tiempo real (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="517d8-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="517d8-185">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="517d8-185">Networking requirements</span></span>


|<span data-ttu-id="517d8-186">**Servidor de hospedaje**</span><span class="sxs-lookup"><span data-stu-id="517d8-186">**Hosting server**</span></span>|<span data-ttu-id="517d8-187">**Agentes.**</span><span class="sxs-lookup"><span data-stu-id="517d8-187">**Agents**</span></span>|<span data-ttu-id="517d8-188">**Agente de escucha**</span><span class="sxs-lookup"><span data-stu-id="517d8-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="517d8-189">La red de gigabit mínimo dúplex completo.</span><span class="sxs-lookup"><span data-stu-id="517d8-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="517d8-190">Puerto TCP saliente 8443 (número de puerto personalizable) para comunicarse con el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="517d8-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="517d8-191">El puerto de escucha debe ser el mismo en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="517d8-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="517d8-192">El puerto TCP 80 o 443 abierto para hospedar el sitio Web de entrada.</span><span class="sxs-lookup"><span data-stu-id="517d8-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="517d8-193">El puerto TCP 8443 (número de puerto personalizable) de entrada para que los agentes para comunicarse con él.</span><span class="sxs-lookup"><span data-stu-id="517d8-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="517d8-194">Durante la instalación, se crean automáticamente los puertos de firewall para el agente de escucha y el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="517d8-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="517d8-195">Para los agentes, la instalación se da por supuesto que se permiten las conexiones TCP salientes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="517d8-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="517d8-196">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="517d8-196">Hardware requirements</span></span>

<span data-ttu-id="517d8-197">En una implementación local, en la que un único servidor hospeda todos los componentes de administrador de las estadísticas del servidor, un servidor con 16 GB de RAM y 4 de la CPU debe ser capaz de admitir aproximadamente 150 muestras por segundo en promedio.</span><span class="sxs-lookup"><span data-stu-id="517d8-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="517d8-198">Para determinar cuántos contadores/agentes puede admitir, use el siguiente cálculo:</span><span class="sxs-lookup"><span data-stu-id="517d8-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="517d8-199">100 servidores \*contadores de 80 \* 1 ejemplo por minuto de cada agente / 60 segundos = ~ 133 muestras por segundo.</span><span class="sxs-lookup"><span data-stu-id="517d8-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="517d8-200">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="517d8-200">Security considerations</span></span>
<span data-ttu-id="517d8-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="517d8-201"></span></span>

<span data-ttu-id="517d8-202">Se cifra todo el tráfico entre servidores.</span><span class="sxs-lookup"><span data-stu-id="517d8-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="517d8-203">Tráfico HTTPS cifrado se enviarán a través del puerto 8443 (de forma predeterminada) del agente de en el servidor de agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="517d8-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="517d8-204">El agente de comprobará si la huella digital SSL en el servidor para asegurarse de que el servidor de agente de escucha es el destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="517d8-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="517d8-205">Tenga en cuenta que el agente usa verificación de certificados por huella digital (en lugar de verificación en cadena).</span><span class="sxs-lookup"><span data-stu-id="517d8-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="517d8-206">No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="517d8-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="517d8-207">Después de que el agente esté satisfecho el agente de escucha es auténtico, se le presentará una contraseña por el agente que, a continuación, se comprueba el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="517d8-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="517d8-208">El agente de comienza la transmisión de datos de rendimiento a través de la conexión con el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="517d8-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="517d8-209">Para más información</span><span class="sxs-lookup"><span data-stu-id="517d8-209">For more information</span></span>
<span data-ttu-id="517d8-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="517d8-210"></span></span>

<span data-ttu-id="517d8-211">Para obtener más información, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="517d8-211">For more information, see the following:</span></span>

- [<span data-ttu-id="517d8-212">Implementar el Administrador de estadísticas de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="517d8-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="517d8-213">Actualizar el Administrador de estadísticas de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="517d8-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="517d8-214">Solucionar problemas de administrador de estadísticas de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="517d8-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
