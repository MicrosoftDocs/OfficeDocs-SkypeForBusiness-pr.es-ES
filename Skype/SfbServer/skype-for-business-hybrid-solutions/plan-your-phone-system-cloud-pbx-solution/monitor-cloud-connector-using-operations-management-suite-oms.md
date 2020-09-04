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
description: Lea este tema para obtener información sobre cómo supervisar la implementación de la versión 2,1 y posteriores de Cloud Connector mediante Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359096"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="118ab-103">Supervisar Cloud Connector con Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="118ab-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="118ab-104">Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="118ab-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="118ab-105">Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="118ab-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="118ab-106">Lea este tema para obtener información sobre cómo supervisar la implementación de la versión 2,1 y posteriores de Cloud Connector mediante Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="118ab-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="118ab-107">Ahora puede supervisar su implementación de Cloud Connector versión 2,1 y posterior mediante Operations Management Suite (OMS), una solución de administración de TI en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="118ab-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="118ab-108">El análisis de registros de OMS le permite supervisar y analizar la disponibilidad y el rendimiento de los recursos, incluidas las máquinas físicas y virtuales.</span><span class="sxs-lookup"><span data-stu-id="118ab-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="118ab-109">Para obtener más información sobre OMS y el análisis de registros, vea [¿Qué es Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="118ab-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="118ab-110">En este tema se presentan las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="118ab-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="118ab-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="118ab-111">Prerequisites</span></span>

- <span data-ttu-id="118ab-112">Configurar Cloud Connector para usar OMS</span><span class="sxs-lookup"><span data-stu-id="118ab-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="118ab-113">Configurar OMS</span><span class="sxs-lookup"><span data-stu-id="118ab-113">Configure OMS</span></span>

- <span data-ttu-id="118ab-114">Analizar las alertas de su repositorio de análisis de registros</span><span class="sxs-lookup"><span data-stu-id="118ab-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="118ab-115">Conjunto de supervisión recomendado</span><span class="sxs-lookup"><span data-stu-id="118ab-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="118ab-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="118ab-116">Prerequisites</span></span>

<span data-ttu-id="118ab-117">Antes de poder usar OMS para supervisar la implementación de Cloud Connector, necesitará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="118ab-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="118ab-118">**Una cuenta de Azure y un área de trabajo de OMS.**</span><span class="sxs-lookup"><span data-stu-id="118ab-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="118ab-119">Si aún no tiene una cuenta de Azure, tendrá que crear una para usar el análisis de registros de OMS.</span><span class="sxs-lookup"><span data-stu-id="118ab-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="118ab-120">Para obtener información sobre cómo crear una cuenta de Azure y configurar un área de trabajo de OMS, consulte Introducción [a un área de trabajo de análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="118ab-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="118ab-121">**Cloud Connector versión 2,1 o posterior**</span><span class="sxs-lookup"><span data-stu-id="118ab-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="118ab-122">Se requiere la **búsqueda de registros nueva de análisis de registros** para la supervisión de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="118ab-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="118ab-123">Para obtener más información, vea [actualizar el área de trabajo de análisis de registros de Azure a nueva búsqueda de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="118ab-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="118ab-124">Configurar Cloud Connector para usar OMS</span><span class="sxs-lookup"><span data-stu-id="118ab-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="118ab-125">Deberá configurar su entorno local de Cloud Connector para usar OMS.</span><span class="sxs-lookup"><span data-stu-id="118ab-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="118ab-126">Para ello, necesitará el identificador y la clave del área de trabajo de OMS, que puede encontrar mediante el portal de OMS, como se indica a continuación: configuración-- \> orígenes conectados-- \> servidores Windows:</span><span class="sxs-lookup"><span data-stu-id="118ab-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Captura de pantalla del OMS de Cloud Connector](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="118ab-128">La configuración de Cloud Connector para que use OMS depende de su escenario:</span><span class="sxs-lookup"><span data-stu-id="118ab-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="118ab-129">**Si va a instalar un nuevo dispositivo de Cloud Connector o desea volver a implementar un dispositivo**, siga estos pasos antes de ejecutar install-CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="118ab-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="118ab-130">En la sección CloudConnector.ini archivo [común], establezca el parámetro OMSEnabled en true.</span><span class="sxs-lookup"><span data-stu-id="118ab-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="118ab-131">Cada vez que se implemente o actualice Cloud Connector, se intentará instalar el agente OMS automáticamente en las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="118ab-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="118ab-132">Habilite esta característica para que el agente OMS pueda sobrevivir a la actualización automática de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="118ab-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="118ab-133">Para configurar el identificador y la clave de OMS, ejecute Set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="118ab-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="118ab-134">**Si va a instalar un agente OMS en un dispositivo existente de Cloud Connector**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="118ab-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="118ab-135">En la sección archivo de CloudConnector.ini [Common], establezca OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="118ab-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="118ab-136">Ejecute Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="118ab-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="118ab-137">Ejecute install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="118ab-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="118ab-138">Si nunca se ha establecido la credencial OMSWorkspace, se le pedirán las credenciales al ejecutar install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="118ab-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="118ab-139">**Si desea actualizar la clave o el identificador del área de trabajo de OMS en un dispositivo de Cloud Connector que ya tiene instalado un agente OMS:**</span><span class="sxs-lookup"><span data-stu-id="118ab-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="118ab-140">Para configurar el identificador y la clave de OMS, ejecute Set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="118ab-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="118ab-141">Para aplicar las actualizaciones, ejecute install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="118ab-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="118ab-142">**Para todos los escenarios, compruebe que los agentes estén conectados de la siguiente manera:**</span><span class="sxs-lookup"><span data-stu-id="118ab-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="118ab-143">En el portal de OMS, vaya a configuración- \> orígenes conectados- \> servidores Windows.</span><span class="sxs-lookup"><span data-stu-id="118ab-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="118ab-144">Verá una lista de las máquinas conectadas.</span><span class="sxs-lookup"><span data-stu-id="118ab-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="118ab-145">Configurar OMS</span><span class="sxs-lookup"><span data-stu-id="118ab-145">Configure OMS</span></span>

<span data-ttu-id="118ab-146">A continuación, tendrá que especificar la configuración de OMS mediante el portal de OMS.</span><span class="sxs-lookup"><span data-stu-id="118ab-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="118ab-147">Concretamente, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="118ab-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="118ab-148">Especifique información sobre los registros de eventos y los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="118ab-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="118ab-149">Cree alertas.</span><span class="sxs-lookup"><span data-stu-id="118ab-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="118ab-150">Especificar información sobre los registros de eventos y los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="118ab-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="118ab-151">En el portal de OMS, debe especificar información sobre los registros de eventos y los contadores de rendimiento de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="118ab-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="118ab-152">Vaya a configuración- \> datos- \> registros de eventos de Windows y agregue registros de eventos para:</span><span class="sxs-lookup"><span data-stu-id="118ab-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="118ab-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="118ab-153">Lync Server</span></span>

   - <span data-ttu-id="118ab-154">Aplicación</span><span class="sxs-lookup"><span data-stu-id="118ab-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="118ab-155">Debe especificar manualmente Lync Server en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="118ab-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="118ab-156">No aparece como una opción en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="118ab-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="118ab-157">Para obtener más información, vea [orígenes de datos del registro de eventos de Windows en el análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events) .</span><span class="sxs-lookup"><span data-stu-id="118ab-157">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="118ab-158">Vaya a configuración- \> datos- \> contadores de rendimiento de Windows y agregue contadores de rendimiento para:</span><span class="sxs-lookup"><span data-stu-id="118ab-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="118ab-159">**Contadores de nivel del sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="118ab-159">**OS level counters**.</span></span> <span data-ttu-id="118ab-160">Puede Agregar contadores a nivel del sistema operativo, como el uso del procesador, el uso de la memoria, el uso de la red o puede usar soluciones existentes como capacidad y rendimiento, monitor de rendimiento de red sin agregar contadores de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="118ab-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="118ab-161">Independientemente de cómo decida supervisarlas, Microsoft recomienda que supervise estos contadores del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="118ab-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="118ab-162">**Contadores de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="118ab-162">**Skype for Business counters**.</span></span> <span data-ttu-id="118ab-163">Hay muchos contadores proporcionados por Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="118ab-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="118ab-164">Puede encontrar estos contadores iniciando sesión en cualquier servidor de mediación y abriendo el monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="118ab-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="118ab-165">Estos contadores comienzan con "LS:".</span><span class="sxs-lookup"><span data-stu-id="118ab-165">These counters start with "LS:".</span></span> <span data-ttu-id="118ab-166">Microsoft recomienda comenzar con los siguientes contadores de capacidad como mínimo y agregar otros que sean de interés:</span><span class="sxs-lookup"><span data-stu-id="118ab-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="118ab-167">Total de llamadas activas:</span><span class="sxs-lookup"><span data-stu-id="118ab-167">Total active calls:</span></span>

       - <span data-ttu-id="118ab-168">LS: MediationServer-llamadas entrantes (_Total) \- actual</span><span class="sxs-lookup"><span data-stu-id="118ab-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="118ab-169">LS: MediationServer-llamadas salientes (_Total) \- actual</span><span class="sxs-lookup"><span data-stu-id="118ab-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="118ab-170">Llamadas de omisión de medios activos totales:</span><span class="sxs-lookup"><span data-stu-id="118ab-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="118ab-171">LS: MediationServer-llamadas entrantes (_Total) \- llamadas de omisión de medios activos</span><span class="sxs-lookup"><span data-stu-id="118ab-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="118ab-172">LS: MediationServer-llamadas salientes (_Total) \- llamadas de omisión de medios activos</span><span class="sxs-lookup"><span data-stu-id="118ab-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="118ab-173">Debe especificar manualmente los contadores de rendimiento en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="118ab-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="118ab-174">No aparecen como opciones en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="118ab-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="118ab-175">Para obtener más información, vea [orígenes de datos de rendimiento de Windows y Linux en el análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters) .</span><span class="sxs-lookup"><span data-stu-id="118ab-175">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="118ab-176">Crear alertas</span><span class="sxs-lookup"><span data-stu-id="118ab-176">Create alerts</span></span>

<span data-ttu-id="118ab-177">Hay dos tipos de alertas en OMS: número de alertas de resultados y alertas de medida métricas.</span><span class="sxs-lookup"><span data-stu-id="118ab-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="118ab-178">Para obtener más información acerca de la creación de alertas, vea [trabajar con reglas de alerta en el análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="118ab-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="118ab-179">Debe tener en cuenta lo siguiente al crear alertas:</span><span class="sxs-lookup"><span data-stu-id="118ab-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="118ab-180">Asegúrese de que la alerta es una alerta de número de resultados, que es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="118ab-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="118ab-181">Las consultas de demostración requieren que "número de resultados" esté establecido en "mayor que 0".</span><span class="sxs-lookup"><span data-stu-id="118ab-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="118ab-182">Se recomienda que establezca la frecuencia de la ventana tiempo y de la alerta en 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="118ab-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="118ab-183">Se recomienda no habilitar "suprimir alertas" para las alertas de demostración.</span><span class="sxs-lookup"><span data-stu-id="118ab-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="118ab-184">Para los escenarios de alerta típicos, Microsoft recomienda crear un par de alertas: un mensaje de error y una alerta de restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="118ab-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="118ab-185">Para la alerta de error, seleccione nivel de gravedad crítico; para la alerta de restablecimiento, seleccione información de nivel de gravedad.</span><span class="sxs-lookup"><span data-stu-id="118ab-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="118ab-186">En las secciones siguientes se describe cómo crear alertas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="118ab-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="118ab-187">**Cree un par de alertas: "RTCMEDSRV no se está ejecutando en los servidores de mediación" y "RTCMEDSRV se ha vuelto a ejecutar en los servidores de mediación"**</span><span class="sxs-lookup"><span data-stu-id="118ab-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="118ab-188">Para crear este par de alertas:</span><span class="sxs-lookup"><span data-stu-id="118ab-188">To create this alert pair:</span></span>

- <span data-ttu-id="118ab-189">La consulta de la alerta de error es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="118ab-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="118ab-190">La consulta usa el filtro del equipo  *en el que el equipo contiene "MediationServer"*  .</span><span class="sxs-lookup"><span data-stu-id="118ab-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="118ab-191">El filtro selecciona solo el equipo cuyo nombre contiene la cadena "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="118ab-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="118ab-192">Debe reemplazar el filtro por su propio filtro de equipo o simplemente quitarlo.</span><span class="sxs-lookup"><span data-stu-id="118ab-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="118ab-193">Puede crear filtros de cadena complejos sin expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="118ab-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="118ab-194">Para obtener más información, consulte [operadores de cadena](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="118ab-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="118ab-195">También puede optar por usar expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="118ab-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="118ab-196">Además, puede crear un grupo de equipos si guarda una consulta de búsqueda y usa ese grupo como filtro de equipo en la consulta de alertas.</span><span class="sxs-lookup"><span data-stu-id="118ab-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="118ab-197">Para obtener más información, vea [grupos de equipos en el registro de registros del análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="118ab-197">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="118ab-198">Para cada equipo, la consulta de error obtendrá el último registro de eventos para el inicio del servicio de RTCMEDSRV y para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="118ab-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="118ab-199">Se devolverá un registro si el último evento es el evento de detención de servicio; no devolverá Nothing si el último evento es el evento de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="118ab-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="118ab-200">En Resumen, la consulta devolvería una lista de servidores cuya RTCMEDSRV se ha detenido en el período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="118ab-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="118ab-201">La consulta para la alerta de restablecimiento es:</span><span class="sxs-lookup"><span data-stu-id="118ab-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="118ab-202">La consulta de restablecimiento hace exactamente lo opuesto a la consulta de error.</span><span class="sxs-lookup"><span data-stu-id="118ab-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="118ab-203">Para cada equipo, se devolverá uno si el último evento es el evento de inicio del servicio; no devolverá Nothing si el último evento es el evento de detención de servicio.</span><span class="sxs-lookup"><span data-stu-id="118ab-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="118ab-204">**Crear un par de alertas: "demasiadas llamadas simultáneas en los servidores de mediación" y "las llamadas simultáneas se revierten a la carga normal"**</span><span class="sxs-lookup"><span data-stu-id="118ab-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="118ab-205">Para crear esta alerta:</span><span class="sxs-lookup"><span data-stu-id="118ab-205">To create this alert:</span></span>

- <span data-ttu-id="118ab-206">La consulta de la alerta de error es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="118ab-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="118ab-207">Para cada equipo, la consulta obtendrá los últimos contadores para las llamadas entrantes y salientes, y sumará esos dos valores.</span><span class="sxs-lookup"><span data-stu-id="118ab-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="118ab-208">Devolverá un registro si el valor de suma supera 500; no devolverá nada si no lo es.</span><span class="sxs-lookup"><span data-stu-id="118ab-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="118ab-209">En Resumen, la consulta devolvería una lista de servidores cuyas llamadas simultáneas son demasiado numerosas en el intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="118ab-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="118ab-210">La consulta para la alerta de restablecimiento es:</span><span class="sxs-lookup"><span data-stu-id="118ab-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="118ab-211">La consulta de restablecimiento hace exactamente lo opuesto a la consulta de error.</span><span class="sxs-lookup"><span data-stu-id="118ab-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="118ab-212">Para cada equipo, la consulta obtendrá los últimos contadores para las llamadas entrantes y salientes, y sumará esos dos valores.</span><span class="sxs-lookup"><span data-stu-id="118ab-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="118ab-213">Devolverá un registro si el valor de sum es inferior a 500; de lo contrario, devolverá Nothing.</span><span class="sxs-lookup"><span data-stu-id="118ab-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="118ab-214">**Cree una alerta: el uso \> de CPU 90 o RTCMEDIARELAY se detuvo en la alerta de los servidores**</span><span class="sxs-lookup"><span data-stu-id="118ab-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="118ab-215">Para crear esta alerta, la consulta es:</span><span class="sxs-lookup"><span data-stu-id="118ab-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="118ab-216">La consulta recibirá todos los contadores de uso del procesador y el evento de detención del servicio de todos los equipos y devolverá un registro si cualquier uso del procesador supera el 90% o si el servicio se detiene alguna vez.</span><span class="sxs-lookup"><span data-stu-id="118ab-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="118ab-217">Analizar las alertas de su repositorio de análisis de registros</span><span class="sxs-lookup"><span data-stu-id="118ab-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="118ab-218">Para analizar las alertas del repositorio, use la solución de administración de alertas.</span><span class="sxs-lookup"><span data-stu-id="118ab-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="118ab-219">Para obtener más información, vea [Alert Management Solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) .</span><span class="sxs-lookup"><span data-stu-id="118ab-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="118ab-220">Conjunto de supervisión mínimo recomendado</span><span class="sxs-lookup"><span data-stu-id="118ab-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="118ab-221">Para identificar problemas con los registros de eventos y los contadores de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="118ab-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="118ab-222">**Registros de eventos.**</span><span class="sxs-lookup"><span data-stu-id="118ab-222">**Event logs.**</span></span> <span data-ttu-id="118ab-223">Para cualquier problema, debe haber un par de eventos, con un conjunto de eventos para indicar que algo es incorrecto, mientras que el otro indica que todo está bien.</span><span class="sxs-lookup"><span data-stu-id="118ab-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="118ab-224">Durante un período de tiempo determinado, es el último evento registrado que indicará si hay algo amiss para ese período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="118ab-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="118ab-225">**Contadores de rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="118ab-225">**Performance Counters.**</span></span> <span data-ttu-id="118ab-226">Debe haber un umbral para los contadores supervisados.</span><span class="sxs-lookup"><span data-stu-id="118ab-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="118ab-227">En la siguiente tabla se enumeran los servicios que Microsoft recomienda supervisar enumerando los identificadores de eventos de detención e Inicio:</span><span class="sxs-lookup"><span data-stu-id="118ab-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="118ab-228">Nombre del servicio</span><span class="sxs-lookup"><span data-stu-id="118ab-228">Service Name</span></span>  <br/> |<span data-ttu-id="118ab-229">Rol de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="118ab-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="118ab-230">Detener identificador de evento</span><span class="sxs-lookup"><span data-stu-id="118ab-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="118ab-231">IDENTIFICADOR de evento de inicio</span><span class="sxs-lookup"><span data-stu-id="118ab-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="118ab-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="118ab-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="118ab-233">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="118ab-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="118ab-234">25003</span><span class="sxs-lookup"><span data-stu-id="118ab-234">25003</span></span>  <br/> |<span data-ttu-id="118ab-235">25002</span><span class="sxs-lookup"><span data-stu-id="118ab-235">25002</span></span>  <br/> |
|<span data-ttu-id="118ab-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="118ab-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="118ab-237">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="118ab-237">Edge Server</span></span>  <br/> |<span data-ttu-id="118ab-238">12289</span><span class="sxs-lookup"><span data-stu-id="118ab-238">12289</span></span>  <br/> |<span data-ttu-id="118ab-239">12288</span><span class="sxs-lookup"><span data-stu-id="118ab-239">12288</span></span>  <br/> |
|<span data-ttu-id="118ab-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="118ab-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="118ab-241">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="118ab-241">Edge Server</span></span>  <br/> |<span data-ttu-id="118ab-242">19003</span><span class="sxs-lookup"><span data-stu-id="118ab-242">19003</span></span>  <br/> |<span data-ttu-id="118ab-243">19002</span><span class="sxs-lookup"><span data-stu-id="118ab-243">19002</span></span>  <br/> |
|<span data-ttu-id="118ab-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="118ab-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="118ab-245">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="118ab-245">Edge Server</span></span>  <br/> |<span data-ttu-id="118ab-246">22003</span><span class="sxs-lookup"><span data-stu-id="118ab-246">22003</span></span>  <br/> |<span data-ttu-id="118ab-247">22002</span><span class="sxs-lookup"><span data-stu-id="118ab-247">22002</span></span>  <br/> |

<span data-ttu-id="118ab-248">En la siguiente tabla se enumeran los problemas de red que Microsoft recomienda supervisar:</span><span class="sxs-lookup"><span data-stu-id="118ab-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="118ab-249">Nombre de monitor</span><span class="sxs-lookup"><span data-stu-id="118ab-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="118ab-250">Rol de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="118ab-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="118ab-251">Expresión de identificador de evento correcto</span><span class="sxs-lookup"><span data-stu-id="118ab-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="118ab-252">Expresión de identificador de evento de error</span><span class="sxs-lookup"><span data-stu-id="118ab-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="118ab-253">Ejemplo de error</span><span class="sxs-lookup"><span data-stu-id="118ab-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="118ab-254">Error de Conectividad del servidor de mediación a la puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="118ab-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="118ab-255">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="118ab-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="118ab-256">25062</span><span class="sxs-lookup"><span data-stu-id="118ab-256">25062</span></span>                              |                                  | <span data-ttu-id="118ab-257">25002</span><span class="sxs-lookup"><span data-stu-id="118ab-257">25002</span></span>  <br/>           |
| <span data-ttu-id="118ab-258">Error de finalización de la llamada del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="118ab-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="118ab-259">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="118ab-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="118ab-260">25064</span><span class="sxs-lookup"><span data-stu-id="118ab-260">25064</span></span>                              |                                  | <span data-ttu-id="118ab-261">25002</span><span class="sxs-lookup"><span data-stu-id="118ab-261">25002</span></span>  <br/>           |
| <span data-ttu-id="118ab-262">Problemas de red críticos</span><span class="sxs-lookup"><span data-stu-id="118ab-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="118ab-263">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="118ab-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="118ab-264">14353</span><span class="sxs-lookup"><span data-stu-id="118ab-264">14353</span></span>                              |                                  | <span data-ttu-id="118ab-265">12288</span><span class="sxs-lookup"><span data-stu-id="118ab-265">12288</span></span>  <br/>           |

<span data-ttu-id="118ab-266">A continuación se enumeran los contadores de capacidad de llamadas que deben supervisarse.</span><span class="sxs-lookup"><span data-stu-id="118ab-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="118ab-267">Estos números deben ser inferiores a 500 para Cloud Connector Standard Edition; menor que 50 para la edición mínima de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="118ab-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="118ab-268">LS: MediationServer-llamadas entrantes (_Total) \- actual</span><span class="sxs-lookup"><span data-stu-id="118ab-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="118ab-269">LS: MediationServer-llamadas salientes (_Total) \- actual</span><span class="sxs-lookup"><span data-stu-id="118ab-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="118ab-270">LS: MediationServer-llamadas entrantes (_Total) \- llamadas de omisión de medios activos</span><span class="sxs-lookup"><span data-stu-id="118ab-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="118ab-271">LS: MediationServer-llamadas salientes (_Total) \- llamadas de omisión de medios activos</span><span class="sxs-lookup"><span data-stu-id="118ab-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="118ab-272">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="118ab-272">See also</span></span>

<span data-ttu-id="118ab-273">Para obtener más información sobre cómo trabajar con OMS, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="118ab-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="118ab-274">Buscar datos mediante búsquedas de registros en el análisis de registros</span><span class="sxs-lookup"><span data-stu-id="118ab-274">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="118ab-275">Referencia de lenguaje de análisis de registros de Azure</span><span class="sxs-lookup"><span data-stu-id="118ab-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="118ab-276">Descripción de las alertas en el análisis de registros</span><span class="sxs-lookup"><span data-stu-id="118ab-276">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="118ab-277">Conectar equipos Windows al servicio log Analytics en Azure</span><span class="sxs-lookup"><span data-stu-id="118ab-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


