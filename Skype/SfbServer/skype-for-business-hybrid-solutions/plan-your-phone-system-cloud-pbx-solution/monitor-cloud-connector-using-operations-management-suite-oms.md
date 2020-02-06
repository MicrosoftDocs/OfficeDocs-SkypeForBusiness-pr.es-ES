---
title: Supervisar Cloud Connector con Operations Management Suite (OMS)
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lea este tema para obtener información sobre cómo supervisar la implementación de la versión 2,1 y posteriores de su conector de la nube mediante Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 1dcac3519624cef898622f915b08b24363453b84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799630"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="ba463-103">Supervisar Cloud Connector con Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="ba463-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="ba463-104">Lea este tema para obtener información sobre cómo supervisar la implementación de la versión 2,1 y posteriores de su conector de la nube mediante Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="ba463-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="ba463-105">Ahora puede supervisar la implementación de la versión 2,1 y posterior de su conector de nube con Operations Management Suite (OMS), una solución de administración de TI en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba463-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="ba463-106">El análisis de registros de OMS le permite supervisar y analizar la disponibilidad y el rendimiento de los recursos, incluidas las máquinas físicas y virtuales.</span><span class="sxs-lookup"><span data-stu-id="ba463-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="ba463-107">Para obtener más información sobre OMS y el análisis de registros, consulte [¿Qué es Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="ba463-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span>

<span data-ttu-id="ba463-108">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ba463-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="ba463-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ba463-109">Prerequisites</span></span>

- <span data-ttu-id="ba463-110">Configurar el conector de nube para usar OMS</span><span class="sxs-lookup"><span data-stu-id="ba463-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="ba463-111">Configurar OMS</span><span class="sxs-lookup"><span data-stu-id="ba463-111">Configure OMS</span></span>

- <span data-ttu-id="ba463-112">Analizar las alertas de su repositorio de análisis de registros</span><span class="sxs-lookup"><span data-stu-id="ba463-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="ba463-113">Conjunto de supervisión recomendado</span><span class="sxs-lookup"><span data-stu-id="ba463-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ba463-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ba463-114">Prerequisites</span></span>

<span data-ttu-id="ba463-115">Antes de poder usar OMS para supervisar la implementación de su conector de nube, necesitará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba463-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="ba463-116">**Una cuenta de Azure y un área de trabajo de OMS.**</span><span class="sxs-lookup"><span data-stu-id="ba463-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="ba463-117">Si aún no tiene una cuenta de Azure, tendrá que crear una para usar análisis de registros de OMS.</span><span class="sxs-lookup"><span data-stu-id="ba463-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="ba463-118">Para obtener información sobre cómo crear una cuenta de Azure y configurar un área de trabajo de OMS, consulte [Introducción a un área de trabajo de análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="ba463-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="ba463-119">**Cloud Connector versión 2,1 o posterior**</span><span class="sxs-lookup"><span data-stu-id="ba463-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="ba463-120">Análisis de registros se requiere una **nueva búsqueda de registros** para la supervisión del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="ba463-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="ba463-121">Para obtener más información, vea [actualizar el área de trabajo de análisis de registros de Azure a nueva búsqueda de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="ba463-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="ba463-122">Configurar el conector de nube para usar OMS</span><span class="sxs-lookup"><span data-stu-id="ba463-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="ba463-123">Tendrá que configurar su entorno local de conector de nube para usar OMS.</span><span class="sxs-lookup"><span data-stu-id="ba463-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="ba463-124">Para ello, necesitará su identificador de área de trabajo de OMS y clave, que puede encontrar mediante el portal de OMS de la siguiente manera:\>configuración: orígenes conectados\> --servidores de Windows:</span><span class="sxs-lookup"><span data-stu-id="ba463-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Captura de pantalla de Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="ba463-126">La configuración del conector de nube para usar OMS depende de su escenario:</span><span class="sxs-lookup"><span data-stu-id="ba463-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="ba463-127">**Si está instalando un nuevo dispositivo de conexión en la nube o desea volver a implementar un dispositivo**, siga estos pasos antes de ejecutar install-CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="ba463-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

1. <span data-ttu-id="ba463-128">En la sección [Common] del archivo CloudConnector. ini, establezca el parámetro OMSEnabled en true.</span><span class="sxs-lookup"><span data-stu-id="ba463-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

    <span data-ttu-id="ba463-129">Cada vez que se implemente o actualice un conector de nube, intentará instalar el agente OMS automáticamente en las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="ba463-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="ba463-130">Habilite esta característica para que el agente OMS pueda sobrevivir a la actualización automática de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="ba463-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

2. <span data-ttu-id="ba463-131">Para configurar la clave y el identificador de OMS, ejecute Set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="ba463-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="ba463-132">**Si va a instalar un agente OMS en un dispositivo de conector de nube existente**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ba463-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

1. <span data-ttu-id="ba463-133">En la sección [Common] del archivo CloudConnector. ini, establezca OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="ba463-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

2. <span data-ttu-id="ba463-134">Ejecute Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ba463-134">Run Import-CcConfiguration.</span></span> 

3. <span data-ttu-id="ba463-135">Ejecute install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="ba463-135">Run Install-CcOMSAgent.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="ba463-136">Si la credencial OMSWorkspace nunca se ha establecido, se le solicitará la credencial cuando ejecute install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="ba463-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="ba463-137">**Si desea actualizar el identificador de área de trabajo de OMS o clave en un dispositivo de conector de nube que ya tiene instalado un agente OMS:**</span><span class="sxs-lookup"><span data-stu-id="ba463-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

1. <span data-ttu-id="ba463-138">Para configurar la clave y el identificador de OMS, ejecute Set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="ba463-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

2. <span data-ttu-id="ba463-139">Para aplicar las actualizaciones, ejecute install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="ba463-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="ba463-140">**Para todos los escenarios, verifique que los agentes estén conectados de la siguiente manera:**</span><span class="sxs-lookup"><span data-stu-id="ba463-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="ba463-141">En el portal de OMS, vaya a configuración\> -orígenes conectados\> -servidores de Windows.</span><span class="sxs-lookup"><span data-stu-id="ba463-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="ba463-142">Verá una lista de las máquinas conectadas.</span><span class="sxs-lookup"><span data-stu-id="ba463-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="ba463-143">Configurar OMS</span><span class="sxs-lookup"><span data-stu-id="ba463-143">Configure OMS</span></span>

<span data-ttu-id="ba463-144">A continuación, tendrá que especificar la configuración de OMS mediante el portal de OMS.</span><span class="sxs-lookup"><span data-stu-id="ba463-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="ba463-145">En concreto, necesitará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba463-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="ba463-146">Especifique la información sobre los registros de eventos y los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ba463-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="ba463-147">Crear alertas.</span><span class="sxs-lookup"><span data-stu-id="ba463-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="ba463-148">Especificar información sobre los registros de eventos y los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="ba463-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="ba463-149">En el portal de OMS, debe especificar información sobre los registros de eventos y los contadores de rendimiento de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ba463-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="ba463-150">Vaya a configuración-\>datos-\>registros de eventos de Windows y agregue registros de eventos para:</span><span class="sxs-lookup"><span data-stu-id="ba463-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="ba463-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba463-151">Lync Server</span></span>

   - <span data-ttu-id="ba463-152">Aplicación</span><span class="sxs-lookup"><span data-stu-id="ba463-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="ba463-153">Debe introducir manualmente Lync Server en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="ba463-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="ba463-154">No aparece como una opción en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ba463-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="ba463-155">Para obtener más información, consulte [orígenes de datos del registro de eventos de Windows en análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="ba463-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="ba463-156">Vaya a configuración-\>datos-\> contadores de rendimiento de Windows y agregue contadores de rendimiento para:</span><span class="sxs-lookup"><span data-stu-id="ba463-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="ba463-157">**Contadores de nivel del sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="ba463-157">**OS level counters**.</span></span> <span data-ttu-id="ba463-158">Puede Agregar contadores de nivel del sistema operativo, como el uso del procesador, el uso de la memoria, el uso de la red, o puede usar soluciones existentes como capacidad y rendimiento, monitor de rendimiento de red sin agregar contadores de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="ba463-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="ba463-159">Independientemente de cómo decida supervisarlos, Microsoft recomienda que supervise estos contadores del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ba463-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="ba463-160">**Contadores de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="ba463-160">**Skype for Business counters**.</span></span> <span data-ttu-id="ba463-161">Hay muchos contadores proporcionados por Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="ba463-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="ba463-162">Puede encontrar estos contadores iniciando sesión en cualquier servidor de mediación y abriendo el monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ba463-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="ba463-163">Estos contadores comienzan con "LS:".</span><span class="sxs-lookup"><span data-stu-id="ba463-163">These counters start with "LS:".</span></span> <span data-ttu-id="ba463-164">Microsoft recomienda que comience con los siguientes contadores de capacidad como mínimo y agregue otros que tengan interés:</span><span class="sxs-lookup"><span data-stu-id="ba463-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="ba463-165">Total de llamadas activas:</span><span class="sxs-lookup"><span data-stu-id="ba463-165">Total active calls:</span></span>

   - <span data-ttu-id="ba463-166">LS: MediationServer: llamadas entrantes (_Total)\- actuales</span><span class="sxs-lookup"><span data-stu-id="ba463-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

   - <span data-ttu-id="ba463-167">LS: MediationServer: llamadas salientes (_Total)\- al día</span><span class="sxs-lookup"><span data-stu-id="ba463-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="ba463-168">Llamadas de omisión de medios activos totales:</span><span class="sxs-lookup"><span data-stu-id="ba463-168">Total active media bypass calls:</span></span>

   - <span data-ttu-id="ba463-169">LS: MediationServer-llamadas entrantes (_Total)\- llamadas de omisión de medios activos</span><span class="sxs-lookup"><span data-stu-id="ba463-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

   - <span data-ttu-id="ba463-170">LS: MediationServer-llamadas salientes (_Total)\- llamadas de omisión de medios activos</span><span class="sxs-lookup"><span data-stu-id="ba463-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="ba463-171">Debe introducir manualmente los contadores de rendimiento en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="ba463-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="ba463-172">No aparecen como opciones en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ba463-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="ba463-173">Para obtener más información, vea [orígenes de datos de rendimiento de Windows y Linux en análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="ba463-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="ba463-174">Crear alertas</span><span class="sxs-lookup"><span data-stu-id="ba463-174">Create alerts</span></span>

<span data-ttu-id="ba463-175">Existen dos tipos de alertas en OMS: número de alertas de resultados y alertas de medición de métricas.</span><span class="sxs-lookup"><span data-stu-id="ba463-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="ba463-176">Para obtener más información sobre cómo crear alertas, consulte [trabajar con reglas de alertas en análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="ba463-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="ba463-177">Debe tener en cuenta lo siguiente al crear alertas:</span><span class="sxs-lookup"><span data-stu-id="ba463-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="ba463-178">Asegúrese de que la alerta es una alerta de número de resultados, que es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ba463-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="ba463-179">Las consultas de demostración requieren que "número de resultados" esté establecido en "mayor que 0".</span><span class="sxs-lookup"><span data-stu-id="ba463-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="ba463-180">Se recomienda configurar la frecuencia de la ventana tiempo y la alerta en 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="ba463-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="ba463-181">Se recomienda no habilitar "suprimir alertas" para las alertas de demostración.</span><span class="sxs-lookup"><span data-stu-id="ba463-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="ba463-182">Para los escenarios de alerta típicos, Microsoft recomienda crear un par de alertas: una alerta de error y una alerta de restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="ba463-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="ba463-183">Para la alerta de error, seleccione nivel de gravedad crítico; para la alerta de restablecimiento, seleccione nivel de gravedad de la información.</span><span class="sxs-lookup"><span data-stu-id="ba463-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="ba463-184">En las siguientes secciones se describe cómo crear alertas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ba463-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="ba463-185">**Crear un par de alertas: "RTCMEDSRV no se está ejecutando en servidores de mediación" y "RTCMEDSRV está en ejecución en servidores de mediación"**</span><span class="sxs-lookup"><span data-stu-id="ba463-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="ba463-186">Para crear este par de alertas:</span><span class="sxs-lookup"><span data-stu-id="ba463-186">To create this alert pair:</span></span>

- <span data-ttu-id="ba463-187">La consulta para la alerta de error es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba463-187">The query for the error alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="ba463-188">La consulta usa el filtro de equipo *donde equipo contiene "MediationServer"* .</span><span class="sxs-lookup"><span data-stu-id="ba463-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="ba463-189">El filtro selecciona solo el equipo cuyo nombre contiene la cadena "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="ba463-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="ba463-190">Debería reemplazar el filtro con su propio filtro informático o simplemente quitarlo.</span><span class="sxs-lookup"><span data-stu-id="ba463-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="ba463-191">Puede crear filtros de cadena complejos sin expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="ba463-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="ba463-192">Para obtener más información, consulte [operadores de cadena](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="ba463-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="ba463-193">También puede optar por usar expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="ba463-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="ba463-194">Además, puede crear un grupo de equipos guardando una consulta de búsqueda y utilizando ese grupo como filtro de equipo en la consulta de alertas.</span><span class="sxs-lookup"><span data-stu-id="ba463-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="ba463-195">Para obtener más información, consulte [grupos de equipos en las búsquedas del registro de análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="ba463-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="ba463-196">Para cada equipo, la consulta de error recibirá el último registro de eventos para el inicio del servicio RTCMEDSRV y la detención de servicio.</span><span class="sxs-lookup"><span data-stu-id="ba463-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="ba463-197">Devolverá un registro si el último evento es el evento de detención de servicio; no devolverá Nothing si el último evento es el evento de inicio de servicio.</span><span class="sxs-lookup"><span data-stu-id="ba463-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="ba463-198">En Resumen, la consulta devolvería una lista de servidores cuya RTCMEDSRV está detenida en la ventana de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ba463-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="ba463-199">La consulta para la alerta de restablecimiento es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba463-199">The query for the reset alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="ba463-200">La consulta de restablecimiento hace exactamente lo opuesto de la consulta de error.</span><span class="sxs-lookup"><span data-stu-id="ba463-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="ba463-201">Para cada equipo, devolverá uno si el último evento es el evento de inicio del servicio; no devolverá nada si el último evento es el evento de detención de servicio.</span><span class="sxs-lookup"><span data-stu-id="ba463-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

  <span data-ttu-id="ba463-202">**Crear un par de alertas: "demasiadas llamadas simultáneas en servidores de mediación" y "las llamadas simultáneas vuelven a carga normal"**</span><span class="sxs-lookup"><span data-stu-id="ba463-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="ba463-203">Para crear esta alerta:</span><span class="sxs-lookup"><span data-stu-id="ba463-203">To create this alert:</span></span>

- <span data-ttu-id="ba463-204">La consulta para la alerta de error es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba463-204">The query for the error alert is:</span></span>

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="ba463-205">Para cada equipo, la consulta recibirá los últimos contadores para las llamadas entrantes y salientes, y sumará esos dos valores.</span><span class="sxs-lookup"><span data-stu-id="ba463-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="ba463-206">Devolverá un registro si el valor de suma supera 500; no volverá nada si lo hace.</span><span class="sxs-lookup"><span data-stu-id="ba463-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="ba463-207">En Resumen, la consulta devolvería una lista de servidores cuyas llamadas simultáneas son demasiado numerosas en la ventana de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ba463-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="ba463-208">La consulta para la alerta de restablecimiento es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba463-208">The query for the reset alert is:</span></span>

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="ba463-209">La consulta de restablecimiento hace exactamente lo opuesto de la consulta de error.</span><span class="sxs-lookup"><span data-stu-id="ba463-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="ba463-210">Para cada equipo, la consulta recibirá los últimos contadores para las llamadas entrantes y salientes, y sumará esos dos valores.</span><span class="sxs-lookup"><span data-stu-id="ba463-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="ba463-211">Devolverá un registro si el valor de suma es menor que 500; de lo contrario, no devolverá nada.</span><span class="sxs-lookup"><span data-stu-id="ba463-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

  <span data-ttu-id="ba463-212">**Crear una alerta: alerta "uso \> de CPU 90 o RTCMEDIARELAY detenidas en los servidores"**</span><span class="sxs-lookup"><span data-stu-id="ba463-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="ba463-213">Para crear esta alerta, la consulta es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba463-213">To create this alert, the query is:</span></span>

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="ba463-214">La consulta obtendrá todo el contador de uso del procesador y el evento de detención de servicio de todos los equipos y devolverá un registro si alguno de los usos del procesador supera el 90% o el servicio se detiene.</span><span class="sxs-lookup"><span data-stu-id="ba463-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="ba463-215">Analizar las alertas de su repositorio de análisis de registros</span><span class="sxs-lookup"><span data-stu-id="ba463-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="ba463-216">Para analizar las alertas de su repositorio, use la solución de administración de alertas.</span><span class="sxs-lookup"><span data-stu-id="ba463-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="ba463-217">Para obtener más información, vea [solución de administración de alertas en Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) .</span><span class="sxs-lookup"><span data-stu-id="ba463-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="ba463-218">Conjunto de supervisión mínimo recomendado</span><span class="sxs-lookup"><span data-stu-id="ba463-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="ba463-219">Para identificar problemas con los registros de eventos y los contadores de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="ba463-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="ba463-220">**Registros de eventos.**</span><span class="sxs-lookup"><span data-stu-id="ba463-220">**Event logs.**</span></span> <span data-ttu-id="ba463-221">Para cualquier problema, debería haber un par de eventos, con un conjunto de eventos para indicar que algo está mal, mientras que el otro indica que todo está bien.</span><span class="sxs-lookup"><span data-stu-id="ba463-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="ba463-222">Durante un período de tiempo determinado, es el último evento registrado que indicará si hay algo incorrecto para ese período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ba463-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="ba463-223">**Contadores de rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="ba463-223">**Performance Counters.**</span></span> <span data-ttu-id="ba463-224">Debe haber un umbral para los contadores supervisados.</span><span class="sxs-lookup"><span data-stu-id="ba463-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="ba463-225">En la tabla siguiente se enumeran los servicios que Microsoft recomienda supervisar al hacer una lista de los identificadores de sucesos detener y iniciar:</span><span class="sxs-lookup"><span data-stu-id="ba463-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="ba463-226">Nombre del servicio</span><span class="sxs-lookup"><span data-stu-id="ba463-226">Service Name</span></span>  <br/> |<span data-ttu-id="ba463-227">Rol de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="ba463-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="ba463-228">Detener identificador de evento</span><span class="sxs-lookup"><span data-stu-id="ba463-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="ba463-229">IDENTIFICADOR de evento de inicio</span><span class="sxs-lookup"><span data-stu-id="ba463-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ba463-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="ba463-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="ba463-231">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="ba463-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="ba463-232">25003</span><span class="sxs-lookup"><span data-stu-id="ba463-232">25003</span></span>  <br/> |<span data-ttu-id="ba463-233">25002</span><span class="sxs-lookup"><span data-stu-id="ba463-233">25002</span></span>  <br/> |
|<span data-ttu-id="ba463-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="ba463-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="ba463-235">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ba463-235">Edge Server</span></span>  <br/> |<span data-ttu-id="ba463-236">12289</span><span class="sxs-lookup"><span data-stu-id="ba463-236">12289</span></span>  <br/> |<span data-ttu-id="ba463-237">12288</span><span class="sxs-lookup"><span data-stu-id="ba463-237">12288</span></span>  <br/> |
|<span data-ttu-id="ba463-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="ba463-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="ba463-239">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ba463-239">Edge Server</span></span>  <br/> |<span data-ttu-id="ba463-240">19003</span><span class="sxs-lookup"><span data-stu-id="ba463-240">19003</span></span>  <br/> |<span data-ttu-id="ba463-241">19002</span><span class="sxs-lookup"><span data-stu-id="ba463-241">19002</span></span>  <br/> |
|<span data-ttu-id="ba463-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="ba463-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="ba463-243">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ba463-243">Edge Server</span></span>  <br/> |<span data-ttu-id="ba463-244">22003</span><span class="sxs-lookup"><span data-stu-id="ba463-244">22003</span></span>  <br/> |<span data-ttu-id="ba463-245">22002</span><span class="sxs-lookup"><span data-stu-id="ba463-245">22002</span></span>  <br/> |

<span data-ttu-id="ba463-246">En la tabla siguiente se enumeran los problemas de red que Microsoft recomienda supervisar:</span><span class="sxs-lookup"><span data-stu-id="ba463-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="ba463-247">Nombre del monitor</span><span class="sxs-lookup"><span data-stu-id="ba463-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="ba463-248">Rol de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="ba463-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="ba463-249">Expresión de identificador de evento de éxito</span><span class="sxs-lookup"><span data-stu-id="ba463-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="ba463-250">Expresión de identificador de evento de error</span><span class="sxs-lookup"><span data-stu-id="ba463-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="ba463-251">Ejemplo de error</span><span class="sxs-lookup"><span data-stu-id="ba463-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="ba463-252">Error de conectividad de servidor de mediación a puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="ba463-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="ba463-253">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="ba463-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="ba463-254">25062</span><span class="sxs-lookup"><span data-stu-id="ba463-254">25062</span></span>                              |                                  | <span data-ttu-id="ba463-255">25002</span><span class="sxs-lookup"><span data-stu-id="ba463-255">25002</span></span>  <br/>           |
| <span data-ttu-id="ba463-256">Error de finalización de llamada de servidor de mediación a puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="ba463-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="ba463-257">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="ba463-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="ba463-258">25064</span><span class="sxs-lookup"><span data-stu-id="ba463-258">25064</span></span>                              |                                  | <span data-ttu-id="ba463-259">25002</span><span class="sxs-lookup"><span data-stu-id="ba463-259">25002</span></span>  <br/>           |
| <span data-ttu-id="ba463-260">Problemas de red críticos</span><span class="sxs-lookup"><span data-stu-id="ba463-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="ba463-261">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ba463-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="ba463-262">14353</span><span class="sxs-lookup"><span data-stu-id="ba463-262">14353</span></span>                              |                                  | <span data-ttu-id="ba463-263">12288</span><span class="sxs-lookup"><span data-stu-id="ba463-263">12288</span></span>  <br/>           |

<span data-ttu-id="ba463-264">A continuación se enumeran los contadores de capacidad de llamadas que deberían supervisarse.</span><span class="sxs-lookup"><span data-stu-id="ba463-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="ba463-265">Estos números deberían ser menos de 500 para el conector de nube Standard Edition; menos de 50 para la edición mínima de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ba463-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="ba463-266">LS: MediationServer: llamadas entrantes (_Total)\- actuales</span><span class="sxs-lookup"><span data-stu-id="ba463-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="ba463-267">LS: MediationServer: llamadas salientes (_Total)\- al día</span><span class="sxs-lookup"><span data-stu-id="ba463-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="ba463-268">LS: MediationServer-llamadas entrantes (_Total)\- llamadas de omisión de medios activos</span><span class="sxs-lookup"><span data-stu-id="ba463-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="ba463-269">LS: MediationServer-llamadas salientes (_Total)\- llamadas de omisión de medios activos</span><span class="sxs-lookup"><span data-stu-id="ba463-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="ba463-270">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba463-270">See also</span></span>

<span data-ttu-id="ba463-271">Para obtener más información sobre cómo trabajar con OMS, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba463-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="ba463-272">Buscar datos mediante búsquedas de registro en análisis de registros</span><span class="sxs-lookup"><span data-stu-id="ba463-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="ba463-273">Referencia del lenguaje de análisis de registros de Azure</span><span class="sxs-lookup"><span data-stu-id="ba463-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="ba463-274">Descripción de las alertas de análisis de registros</span><span class="sxs-lookup"><span data-stu-id="ba463-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="ba463-275">Conectar equipos de Windows con el servicio de análisis de registros en Azure</span><span class="sxs-lookup"><span data-stu-id="ba463-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


