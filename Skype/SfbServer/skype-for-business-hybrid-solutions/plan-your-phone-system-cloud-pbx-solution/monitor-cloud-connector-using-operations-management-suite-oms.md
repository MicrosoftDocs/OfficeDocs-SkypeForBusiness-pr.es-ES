---
title: Supervisar el conector de nube mediante Operations Management Suite (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lea este tema para aprender a supervisar la versión del conector de nube 2.1 y posterior implementación mediante Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 8cb454cfcb61bb11e0545ab5ff7dd45d1403ce55
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="34688-103">Supervisar el conector de nube mediante Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="34688-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>
 
<span data-ttu-id="34688-104">Lea este tema para aprender a supervisar la versión del conector de nube 2.1 y posterior implementación mediante Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="34688-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>
  
<span data-ttu-id="34688-105">Ahora puede supervisar la versión del conector de nube 2.1 y posterior implementación mediante Operations Management Suite (OMS), una solución de administración de TI de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34688-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="34688-106">Análisis del registro de OMS permite supervisar y analizar la disponibilidad y el rendimiento de los recursos incluidos físicos y máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="34688-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="34688-107">Para obtener más información acerca de OMS y análisis de registro, consulte [¿Qué es la serie de administración de operaciones (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="34688-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span></span>
  
<span data-ttu-id="34688-108">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="34688-108">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="34688-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="34688-109">Prerequisites</span></span>
    
- <span data-ttu-id="34688-110">Configurar el conector de nube para usar OMS</span><span class="sxs-lookup"><span data-stu-id="34688-110">Configure Cloud Connector to use OMS</span></span>
    
- <span data-ttu-id="34688-111">Configurar OMS</span><span class="sxs-lookup"><span data-stu-id="34688-111">Configure OMS</span></span>
    
- <span data-ttu-id="34688-112">Analizar las alertas en el repositorio de análisis de registro</span><span class="sxs-lookup"><span data-stu-id="34688-112">Analyze the alerts in your Log Analytics repository</span></span>
    
- <span data-ttu-id="34688-113">Conjunto recomendado de supervisión</span><span class="sxs-lookup"><span data-stu-id="34688-113">Recommended monitoring set</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="34688-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="34688-114">Prerequisites</span></span>

<span data-ttu-id="34688-115">Para poder utilizar OMS para supervisar la implementación del conector de la nube, necesitará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="34688-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>
  
- <span data-ttu-id="34688-116">**Una cuenta de Azure y un área de trabajo OMS.**</span><span class="sxs-lookup"><span data-stu-id="34688-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="34688-117">Si ya no tienes una cuenta de Azure, debe crear uno para utilizar el análisis del registro de OMS.</span><span class="sxs-lookup"><span data-stu-id="34688-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="34688-118">Para obtener información acerca de cómo crear una cuenta de Azure y establecer un área de trabajo OMS, consulte [Introducción a un área de trabajo de análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="34688-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span></span>
    
- <span data-ttu-id="34688-119">**Conector de nube versión 2.1 o posterior**</span><span class="sxs-lookup"><span data-stu-id="34688-119">**Cloud Connector version 2.1 or later**</span></span>
    
- <span data-ttu-id="34688-120">**Nueva búsqueda de registros de análisis de registro** es necesario para la supervisión del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="34688-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="34688-121">Para obtener más información, consulte [actualizar el área de trabajo de análisis de registro de Azure a nueva búsqueda de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="34688-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>
    
## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="34688-122">Configurar el conector de nube para usar OMS</span><span class="sxs-lookup"><span data-stu-id="34688-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="34688-123">Debe configurar el entorno de nube conector local para usar OMS.</span><span class="sxs-lookup"><span data-stu-id="34688-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="34688-124">Para ello, necesitará su Id. de área de trabajo OMS y clave, que puede encontrar mediante el portal OMS como sigue: configuración--\>orígenes conectados--\> servidores Windows:</span><span class="sxs-lookup"><span data-stu-id="34688-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>
  
![Captura de pantalla de Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)
  
<span data-ttu-id="34688-126">Cómo configurar el conector de nube para usar OMS depende de su escenario:</span><span class="sxs-lookup"><span data-stu-id="34688-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>
  
- <span data-ttu-id="34688-127">**Si va a instalar un nuevo dispositivo conector de nube o desea volver a implementar un dispositivo**, siga estos pasos antes de ejecutar CcAppliance de instalación:</span><span class="sxs-lookup"><span data-stu-id="34688-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>
    
1. <span data-ttu-id="34688-128">En la sección [Common] del archivo de CloudConnector.ini, establezca el parámetro OMSEnabled en True.</span><span class="sxs-lookup"><span data-stu-id="34688-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>
    
    <span data-ttu-id="34688-129">Cada vez se implementan o actualizado, conector de nube intentará instalar al agente OMS automáticamente en las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="34688-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="34688-130">Habilitar esta característica para que el agente OMS puede sobrevivir a la actualización automática del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="34688-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>
    
2. <span data-ttu-id="34688-131">Para configurar el ID de la OMS y la clave, ejecute Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="34688-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 
    
- <span data-ttu-id="34688-132">**Si va a instalar un agente OMS en un dispositivo conector de nube existente**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="34688-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>
    
1. <span data-ttu-id="34688-133">En la sección [Common] del archivo de CloudConnector.ini, establezca OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="34688-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 
    
2. <span data-ttu-id="34688-134">Ejecute CcConfiguration de importación.</span><span class="sxs-lookup"><span data-stu-id="34688-134">Run Import-CcConfiguration.</span></span> 
    
3. <span data-ttu-id="34688-135">Ejecute la instalación CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="34688-135">Run Install-CcOMSAgent.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="34688-136">Si nunca se ha establecido la credencial de OMSWorkspace, se pedirá la credencial al ejecutar install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="34688-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 
  
- <span data-ttu-id="34688-137">**Si desea actualizar el identificador de área de trabajo OMS o clave en un dispositivo conector de nube ya ha instalado a un agente OMS:**</span><span class="sxs-lookup"><span data-stu-id="34688-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>
    
1. <span data-ttu-id="34688-138">Para configurar el ID de la OMS y la clave, ejecute Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="34688-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 
    
2. <span data-ttu-id="34688-139">Para aplicar las actualizaciones, ejecute Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="34688-139">To apply the updates, run Install-CcOMSAgent.</span></span> 
    
- <span data-ttu-id="34688-140">**Para todos los escenarios, compruebe que los agentes están conectados como se indica a continuación:**</span><span class="sxs-lookup"><span data-stu-id="34688-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>
    
    <span data-ttu-id="34688-141">En el portal OMS, vaya a configuración -\> orígenes conectados -\> servidores Windows.</span><span class="sxs-lookup"><span data-stu-id="34688-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="34688-142">Verá una lista de los equipos conectados.</span><span class="sxs-lookup"><span data-stu-id="34688-142">You will see a list of connected machines.</span></span> 
    
## <a name="configure-oms"></a><span data-ttu-id="34688-143">Configurar OMS</span><span class="sxs-lookup"><span data-stu-id="34688-143">Configure OMS</span></span>

<span data-ttu-id="34688-144">A continuación, debe especificar la configuración de OMS mediante el portal OMS.</span><span class="sxs-lookup"><span data-stu-id="34688-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="34688-145">Específicamente, necesitará:</span><span class="sxs-lookup"><span data-stu-id="34688-145">Specifically, you will need to:</span></span>
  
- <span data-ttu-id="34688-146">Especificar información sobre registros de eventos y contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="34688-146">Specify information about event logs and performance counters.</span></span>
    
- <span data-ttu-id="34688-147">Crear alertas.</span><span class="sxs-lookup"><span data-stu-id="34688-147">Create alerts.</span></span> 
    
### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="34688-148">Especificar información sobre registros de eventos y contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="34688-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="34688-149">En el portal de la OMS, debe especificar información sobre los registros de sucesos y contadores de rendimiento como sigue:</span><span class="sxs-lookup"><span data-stu-id="34688-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>
  
1. <span data-ttu-id="34688-150">Vaya a configuración -\>de datos -\>registros de sucesos de Windows y agregar los registros de sucesos:</span><span class="sxs-lookup"><span data-stu-id="34688-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 
    
  - <span data-ttu-id="34688-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="34688-151">Lync Server</span></span>
    
  - <span data-ttu-id="34688-152">Aplicación</span><span class="sxs-lookup"><span data-stu-id="34688-152">Application</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="34688-153">Debe especificar manualmente Lync Server en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="34688-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="34688-154">No aparece como opción en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="34688-154">It does not appear as an option in the drop-down list.</span></span> 
  
    <span data-ttu-id="34688-155">Para obtener más información, vea [orígenes de datos de registro de sucesos de Windows en análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="34688-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>
    
2. <span data-ttu-id="34688-156">Vaya a configuración -\>de datos -\> contadores de rendimiento de Windows, y agregar los contadores de rendimiento para:</span><span class="sxs-lookup"><span data-stu-id="34688-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 
    
  - <span data-ttu-id="34688-157">**Contadores de nivel de sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="34688-157">**OS level counters**.</span></span> <span data-ttu-id="34688-158">Puede agregar contadores de nivel de sistema operativo, como el uso del procesador, uso de memoria, uso de la red, o puede usar soluciones existentes, como la capacidad y rendimiento, Monitor de rendimiento de red sin agregar contadores explícitamente.</span><span class="sxs-lookup"><span data-stu-id="34688-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="34688-159">Independientemente de cómo decida supervisarlos, Microsoft recomienda que supervise estos contadores de sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="34688-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>
    
  - <span data-ttu-id="34688-160">**Skype para contadores de negocios**.</span><span class="sxs-lookup"><span data-stu-id="34688-160">**Skype for Business counters**.</span></span> <span data-ttu-id="34688-161">Hay muchos contadores proporcionados por Skype para empresas.</span><span class="sxs-lookup"><span data-stu-id="34688-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="34688-162">Puede encontrar estos contadores, iniciar sesión en cualquier servidor de mediación y abra al Monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="34688-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="34688-163">Estos contadores se inicia con "LS:".</span><span class="sxs-lookup"><span data-stu-id="34688-163">These counters start with "LS:".</span></span> <span data-ttu-id="34688-164">Microsoft recomienda que comience con los siguientes contadores de capacidad como mínimo y agregar otras que son de interés:</span><span class="sxs-lookup"><span data-stu-id="34688-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>
    
    <span data-ttu-id="34688-165">Número total de llamadas activa:</span><span class="sxs-lookup"><span data-stu-id="34688-165">Total active calls:</span></span>
    
  - <span data-ttu-id="34688-166">LS:MediationServer - Calls(_Total) entrada\- actual</span><span class="sxs-lookup"><span data-stu-id="34688-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 
    
  - <span data-ttu-id="34688-167">LS:MediationServer - Calls(_Total) de salida\- actual</span><span class="sxs-lookup"><span data-stu-id="34688-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 
    
    <span data-ttu-id="34688-168">Total de medios active omitir las llamadas:</span><span class="sxs-lookup"><span data-stu-id="34688-168">Total active media bypass calls:</span></span>
    
  - <span data-ttu-id="34688-169">LS:MediationServer - Calls(_Total) entrada\- multimedia activo omitir las llamadas</span><span class="sxs-lookup"><span data-stu-id="34688-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 
    
  - <span data-ttu-id="34688-170">LS:MediationServer - Calls(_Total) de salida\- multimedia activo omitir las llamadas</span><span class="sxs-lookup"><span data-stu-id="34688-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="34688-171">Debe especificar manualmente los contadores de rendimiento en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="34688-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="34688-172">No aparecen como opciones en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="34688-172">They do not appear as options in the drop-down list.</span></span> 
  
    <span data-ttu-id="34688-173">Para obtener más información, vea [orígenes de datos de rendimiento de Windows y Linux en el análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="34688-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>
    
### <a name="create-alerts"></a><span data-ttu-id="34688-174">Crear alertas</span><span class="sxs-lookup"><span data-stu-id="34688-174">Create alerts</span></span>

<span data-ttu-id="34688-175">Hay dos tipos de avisos de OMS: número de alertas de resultados y métrico.</span><span class="sxs-lookup"><span data-stu-id="34688-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="34688-176">Para obtener más información acerca de la creación de alertas, consulte [trabajar con reglas de alertas en el registro de análisis](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="34688-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span></span>
  
<span data-ttu-id="34688-177">Debe considerar lo siguiente al crear alertas:</span><span class="sxs-lookup"><span data-stu-id="34688-177">You should consider the following when creating alerts:</span></span>
  
- <span data-ttu-id="34688-178">Asegúrese de que la alerta es una alerta de número de los resultados, que es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="34688-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 
    
- <span data-ttu-id="34688-179">Las consultas de demostración requieren que "El número de resultados" está establecido a "mayor que 0".</span><span class="sxs-lookup"><span data-stu-id="34688-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 
    
- <span data-ttu-id="34688-180">Se recomienda establecer lapso de tiempo y frecuencia de alertas a 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="34688-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 
    
- <span data-ttu-id="34688-181">Se recomienda que no habilite "Suprimir alertas" para alertas de demostración.</span><span class="sxs-lookup"><span data-stu-id="34688-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 
    
- <span data-ttu-id="34688-182">Para los escenarios típicos de alerta, Microsoft recomienda crear un par de alertas: alerta de un error y una restablecer alerta.</span><span class="sxs-lookup"><span data-stu-id="34688-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="34688-183">La alerta de error, seleccione el nivel de gravedad crítico; la alerta de reinicio, seleccione el nivel de gravedad informativo.</span><span class="sxs-lookup"><span data-stu-id="34688-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>
    
<span data-ttu-id="34688-184">Las secciones siguientes describen cómo crear alertas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="34688-184">The following sections describe how to create sample alerts.</span></span>
  
 <span data-ttu-id="34688-185">**Crear un par de alerta: "RTCMEDSRV no se ejecuta en los servidores de mediación" y "RTCMEDSRV está en ejecución en servidores de mediación"**</span><span class="sxs-lookup"><span data-stu-id="34688-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>
  
<span data-ttu-id="34688-186">Para crear este par de alerta:</span><span class="sxs-lookup"><span data-stu-id="34688-186">To create this alert pair:</span></span>
  
- <span data-ttu-id="34688-187">La consulta para la alerta de error es:</span><span class="sxs-lookup"><span data-stu-id="34688-187">The query for the error alert is:</span></span>
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="34688-188">La consulta usa el filtro de equipo *en equipo contiene "MediationServer"* .</span><span class="sxs-lookup"><span data-stu-id="34688-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="34688-189">El filtro selecciona sólo el equipo cuyo nombre contiene la cadena "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="34688-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>
    
     <span data-ttu-id="34688-190">¿Reemplazar el filtro con el filtro de su propio equipo o simplemente eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="34688-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="34688-191">Puede crear filtros de cadena compleja sin expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="34688-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="34688-192">Para obtener más información, vea [operadores de cadena](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="34688-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="34688-193">También puede utilizar expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="34688-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="34688-194">Además, puede crear un grupo de equipos por guardar una consulta de búsqueda y el uso de ese grupo como filtro de equipo en la consulta de alerta.</span><span class="sxs-lookup"><span data-stu-id="34688-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="34688-195">Para obtener más información, vea [grupos de equipo de análisis de registro iniciar búsquedas](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="34688-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span></span>
    
    <span data-ttu-id="34688-196">Para cada equipo, el error de la consulta obtendrá el último registro de eventos para el inicio de servicio RTCMEDSRV y detención de servicios.</span><span class="sxs-lookup"><span data-stu-id="34688-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="34688-197">Devolverá una iniciar sesión si el último evento es el evento de detención del servicio; no devolverá nada si el último evento es el evento de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="34688-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="34688-198">En resumen, la consulta devolvería una lista de servidores cuyo RTCMEDSRV se detiene en la ventana de tiempo.</span><span class="sxs-lookup"><span data-stu-id="34688-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 
    
- <span data-ttu-id="34688-199">La consulta para la alerta de restablecimiento es:</span><span class="sxs-lookup"><span data-stu-id="34688-199">The query for the reset alert is:</span></span>
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="34688-200">La consulta de reinicio hace exactamente lo opuesto de la consulta de error.</span><span class="sxs-lookup"><span data-stu-id="34688-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="34688-201">Para cada equipo, devolverá uno si el último evento es el servicio de inicio de evento; no devolverá nada si el último evento es el evento de detención del servicio.</span><span class="sxs-lookup"><span data-stu-id="34688-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>
    
 <span data-ttu-id="34688-202">**Crear un par de alerta: "demasiados muchas llamadas simultáneas en servidores de mediación" y "llamadas simultáneas a carga normal"**</span><span class="sxs-lookup"><span data-stu-id="34688-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>
  
<span data-ttu-id="34688-203">Para crear esta alerta:</span><span class="sxs-lookup"><span data-stu-id="34688-203">To create this alert:</span></span>
  
- <span data-ttu-id="34688-204">La consulta para la alerta de error es:</span><span class="sxs-lookup"><span data-stu-id="34688-204">The query for the error alert is:</span></span>
    
  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName 
== "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="34688-205">Para cada equipo, la consulta obtendrá los contadores última llamada entrante, llamada saliente y suma esos dos valores.</span><span class="sxs-lookup"><span data-stu-id="34688-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="34688-206">Devolverá una sesión si el valor de la suma supera 500; no devolverá nada si no es así.</span><span class="sxs-lookup"><span data-stu-id="34688-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="34688-207">En resumen, la consulta devolvería una lista de servidores cuyas llamadas simultáneas son demasiados en la ventana de tiempo.</span><span class="sxs-lookup"><span data-stu-id="34688-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>
    
- <span data-ttu-id="34688-208">La consulta para la alerta de restablecimiento es:</span><span class="sxs-lookup"><span data-stu-id="34688-208">The query for the reset alert is:</span></span>
    
  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==
 "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500

  ```

    <span data-ttu-id="34688-209">La consulta de reinicio hace exactamente lo opuesto de la consulta de error.</span><span class="sxs-lookup"><span data-stu-id="34688-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="34688-210">Para cada equipo, la consulta obtendrá los contadores última llamada entrante, llamada saliente y suma esos dos valores.</span><span class="sxs-lookup"><span data-stu-id="34688-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="34688-211">Devolverá un registro si el valor de la suma es menor que 500; devolverá nothing en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="34688-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>
    
 <span data-ttu-id="34688-212">**Crear una alerta: "uso de la CPU \> 90 o RTCMEDIARELAY detenido en servidores" alerta**</span><span class="sxs-lookup"><span data-stu-id="34688-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>
  
<span data-ttu-id="34688-213">Para crear esta alerta, la consulta es:</span><span class="sxs-lookup"><span data-stu-id="34688-213">To create this alert, the query is:</span></span>
  
```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==
 "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="34688-214">La consulta obtendrá todos los contadores de uso del procesador y el evento de detención del servicio de todos los equipos y devuelve un registro si el uso del procesador supera el 90% o servicio nunca se detiene.</span><span class="sxs-lookup"><span data-stu-id="34688-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 
  
## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="34688-215">Analizar las alertas en el repositorio de análisis de registro</span><span class="sxs-lookup"><span data-stu-id="34688-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="34688-216">Para analizar las alertas en el repositorio, utilice la solución de administración de alertas.</span><span class="sxs-lookup"><span data-stu-id="34688-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="34688-217">Para obtener más información, consulte [solución de administración de alertas de Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="34688-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span></span>
  
## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="34688-218">Conjunto de supervisión mínimo recomendado</span><span class="sxs-lookup"><span data-stu-id="34688-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="34688-219">Para identificar problemas con los registros de sucesos y contadores de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="34688-219">To identify issues with event logs and performance counters:</span></span> 
  
- <span data-ttu-id="34688-220">**Registros de eventos.**</span><span class="sxs-lookup"><span data-stu-id="34688-220">**Event logs.**</span></span> <span data-ttu-id="34688-221">Para cualquier problema, debería haber un par de eventos, con un conjunto de eventos que indican que algo va mal, mientras que el otro indica que todo está bien.</span><span class="sxs-lookup"><span data-stu-id="34688-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="34688-222">Durante cualquier período de tiempo, es el último suceso grabado que indicará si algo está mal durante ese período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="34688-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>
    
- <span data-ttu-id="34688-223">**Contadores de rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="34688-223">**Performance Counters.**</span></span> <span data-ttu-id="34688-224">Debe haber un umbral de los contadores supervisados.</span><span class="sxs-lookup"><span data-stu-id="34688-224">There should be a threshold for the monitored counters.</span></span>
    
<span data-ttu-id="34688-225">En la tabla siguiente se enumera los servicios que Microsoft recomienda supervisar con una lista de los identificadores de sucesos de inicio y de parada:</span><span class="sxs-lookup"><span data-stu-id="34688-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>
  
|<span data-ttu-id="34688-226">Nombre de servicio</span><span class="sxs-lookup"><span data-stu-id="34688-226">Service Name</span></span>  <br/> |<span data-ttu-id="34688-227">Función de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="34688-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="34688-228">Id. de suceso de detener</span><span class="sxs-lookup"><span data-stu-id="34688-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="34688-229">Id. de suceso de inicio</span><span class="sxs-lookup"><span data-stu-id="34688-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34688-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="34688-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="34688-231">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="34688-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="34688-232">25003</span><span class="sxs-lookup"><span data-stu-id="34688-232">25003</span></span>  <br/> |<span data-ttu-id="34688-233">25002</span><span class="sxs-lookup"><span data-stu-id="34688-233">25002</span></span>  <br/> |
|<span data-ttu-id="34688-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="34688-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="34688-235">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="34688-235">Edge Server</span></span>  <br/> |<span data-ttu-id="34688-236">12289</span><span class="sxs-lookup"><span data-stu-id="34688-236">12289</span></span>  <br/> |<span data-ttu-id="34688-237">12288</span><span class="sxs-lookup"><span data-stu-id="34688-237">12288</span></span>  <br/> |
|<span data-ttu-id="34688-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="34688-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="34688-239">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="34688-239">Edge Server</span></span>  <br/> |<span data-ttu-id="34688-240">19003</span><span class="sxs-lookup"><span data-stu-id="34688-240">19003</span></span>  <br/> |<span data-ttu-id="34688-241">19002</span><span class="sxs-lookup"><span data-stu-id="34688-241">19002</span></span>  <br/> |
|<span data-ttu-id="34688-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="34688-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="34688-243">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="34688-243">Edge Server</span></span>  <br/> |<span data-ttu-id="34688-244">22003</span><span class="sxs-lookup"><span data-stu-id="34688-244">22003</span></span>  <br/> |<span data-ttu-id="34688-245">22002</span><span class="sxs-lookup"><span data-stu-id="34688-245">22002</span></span>  <br/> |
   
<span data-ttu-id="34688-246">En la tabla siguiente enumera los problemas de red que Microsoft recomienda la supervisión:</span><span class="sxs-lookup"><span data-stu-id="34688-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>
  
|<span data-ttu-id="34688-247">Nombre de Monitor</span><span class="sxs-lookup"><span data-stu-id="34688-247">Monitor Name</span></span>  <br/> |<span data-ttu-id="34688-248">Función de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="34688-248">Target Server Role</span></span>  <br/> |<span data-ttu-id="34688-249">Expresión de ID de evento de éxito</span><span class="sxs-lookup"><span data-stu-id="34688-249">Success Event ID expression</span></span>  <br/> |<span data-ttu-id="34688-250">Expresión de ID de evento de error</span><span class="sxs-lookup"><span data-stu-id="34688-250">Error Event ID expression</span></span>  <br/> |<span data-ttu-id="34688-251">Ejemplo de error</span><span class="sxs-lookup"><span data-stu-id="34688-251">Failure example</span></span>  <br/> |
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34688-252">Servidor de mediación para error de conectividad de la puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="34688-252">Mediation Server to gateway connectivity failure</span></span>  <br/> |<span data-ttu-id="34688-253">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="34688-253">Mediation Server</span></span>  <br/> |<span data-ttu-id="34688-254">25062</span><span class="sxs-lookup"><span data-stu-id="34688-254">25062</span></span> || <span data-ttu-id="34688-255">25002</span><span class="sxs-lookup"><span data-stu-id="34688-255">25002</span></span>  <br/> |<span data-ttu-id="34688-256">25061</span><span class="sxs-lookup"><span data-stu-id="34688-256">25061</span></span>  <br/> |<span data-ttu-id="34688-257">Error de MS PING Gateway (opción)</span><span class="sxs-lookup"><span data-stu-id="34688-257">MS PING (option) Gateway failed</span></span>  <br/> |
|<span data-ttu-id="34688-258">Servidor de mediación para la puerta de enlace de llamar a error de finalización</span><span class="sxs-lookup"><span data-stu-id="34688-258">Mediation Server to gateway call completion failure</span></span>  <br/> |<span data-ttu-id="34688-259">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="34688-259">Mediation Server</span></span>  <br/> |<span data-ttu-id="34688-260">25064</span><span class="sxs-lookup"><span data-stu-id="34688-260">25064</span></span> || <span data-ttu-id="34688-261">25002</span><span class="sxs-lookup"><span data-stu-id="34688-261">25002</span></span>  <br/> |<span data-ttu-id="34688-262">25063</span><span class="sxs-lookup"><span data-stu-id="34688-262">25063</span></span>  <br/> |<span data-ttu-id="34688-263">Error de MS trata de realizar la llamada a la puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="34688-263">MS trying to make call to Gateway failed</span></span>  <br/> |
|<span data-ttu-id="34688-264">Problemas de la red</span><span class="sxs-lookup"><span data-stu-id="34688-264">Critical network problems</span></span>  <br/> |<span data-ttu-id="34688-265">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="34688-265">Edge Server</span></span>  <br/> |<span data-ttu-id="34688-266">14353</span><span class="sxs-lookup"><span data-stu-id="34688-266">14353</span></span> || <span data-ttu-id="34688-267">12288</span><span class="sxs-lookup"><span data-stu-id="34688-267">12288</span></span>  <br/> |<span data-ttu-id="34688-268">14624</span><span class="sxs-lookup"><span data-stu-id="34688-268">14624</span></span>  <br/> |<span data-ttu-id="34688-269">No se pudo iniciar en la dirección IP local 192.168.231.14 en el puerto 5061 transporte TLS</span><span class="sxs-lookup"><span data-stu-id="34688-269">Transport TLS has failed to start on local IP address 192.168.231.14 at port 5061</span></span>  <br/> |
   
<span data-ttu-id="34688-270">A continuación enumeran los contadores de capacidad de llamada que se deben supervisar.</span><span class="sxs-lookup"><span data-stu-id="34688-270">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="34688-271">Estos números deben ser menor que 500 para standard edition nube conector; menos de 50 para edición mínima del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="34688-271">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>
  
- <span data-ttu-id="34688-272">LS:MediationServer - Calls(_Total) entrada\- actual</span><span class="sxs-lookup"><span data-stu-id="34688-272">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 
    
- <span data-ttu-id="34688-273">LS:MediationServer - Calls(_Total) de salida\- actual</span><span class="sxs-lookup"><span data-stu-id="34688-273">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 
    
- <span data-ttu-id="34688-274">LS:MediationServer - Calls(_Total) entrada\- multimedia activo omitir las llamadas</span><span class="sxs-lookup"><span data-stu-id="34688-274">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>
    
- <span data-ttu-id="34688-275">LS:MediationServer - Calls(_Total) de salida\- multimedia activo omitir las llamadas</span><span class="sxs-lookup"><span data-stu-id="34688-275">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>
    
## <a name="see-also"></a><span data-ttu-id="34688-276">Vea también</span><span class="sxs-lookup"><span data-stu-id="34688-276">See also</span></span>

<span data-ttu-id="34688-277">Para obtener más información acerca de cómo trabajar con la OMS, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="34688-277">For more information about working with OMS, see the following:</span></span>
  
- [<span data-ttu-id="34688-278">Buscar datos mediante búsquedas de registro de análisis de registro</span><span class="sxs-lookup"><span data-stu-id="34688-278">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)
    
- [<span data-ttu-id="34688-279">Referencia del lenguaje de registro Azure Analytics</span><span class="sxs-lookup"><span data-stu-id="34688-279">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)
    
- [<span data-ttu-id="34688-280">Información sobre alertas en el registro de análisis</span><span class="sxs-lookup"><span data-stu-id="34688-280">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)
    
- [<span data-ttu-id="34688-281">Conectar los equipos de Windows para el servicio de análisis de registro en Azure</span><span class="sxs-lookup"><span data-stu-id="34688-281">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)
    

