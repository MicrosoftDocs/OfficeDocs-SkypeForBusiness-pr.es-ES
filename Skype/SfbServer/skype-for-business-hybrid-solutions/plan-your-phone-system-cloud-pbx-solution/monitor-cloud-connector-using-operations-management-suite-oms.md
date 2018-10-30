---
title: Supervisar el conector en la nube con el conjunto de aplicaciones de administración de operaciones (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lea este tema para obtener información acerca de cómo supervisar la versión 2.1 de conector en la nube y la implementación posterior mediante el uso conjunto de aplicaciones de administración de operaciones de Microsoft (OMS).
ms.openlocfilehash: 36d70a1504eab085d319e46d03c3c6f0bd9d14f3
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839826"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="4a27f-103">Supervisar el conector en la nube con el conjunto de aplicaciones de administración de operaciones (OMS)</span><span class="sxs-lookup"><span data-stu-id="4a27f-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="4a27f-104">Lea este tema para obtener información acerca de cómo supervisar la versión 2.1 de conector en la nube y la implementación posterior mediante el uso conjunto de aplicaciones de administración de operaciones de Microsoft (OMS).</span><span class="sxs-lookup"><span data-stu-id="4a27f-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="4a27f-105">Ahora puede supervisar la versión 2.1 de conector en la nube y la implementación posterior mediante el uso conjunto de aplicaciones de administración de operaciones (OMS), una solución de administración de TI de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4a27f-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="4a27f-106">Análisis del registro de OMS le permite supervisar y analizar la disponibilidad y el rendimiento de los recursos incluidos físicos y máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="4a27f-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="4a27f-107">Para obtener más información acerca de OMS y análisis de registro, vea [¿Qué es el conjunto de aplicaciones de administración de operaciones (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="4a27f-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span>

<span data-ttu-id="4a27f-108">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4a27f-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="4a27f-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4a27f-109">Prerequisites</span></span>

- <span data-ttu-id="4a27f-110">Configurar el conector en la nube para usar OMS</span><span class="sxs-lookup"><span data-stu-id="4a27f-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="4a27f-111">Configuración de OMS</span><span class="sxs-lookup"><span data-stu-id="4a27f-111">Configure OMS</span></span>

- <span data-ttu-id="4a27f-112">Analizar las alertas en el repositorio de análisis de registro</span><span class="sxs-lookup"><span data-stu-id="4a27f-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="4a27f-113">Conjunto de supervisión recomendado</span><span class="sxs-lookup"><span data-stu-id="4a27f-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4a27f-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4a27f-114">Prerequisites</span></span>

<span data-ttu-id="4a27f-115">Antes de que puede usar OMS para supervisar la implementación del conector de la nube, necesitará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a27f-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="4a27f-116">**Una cuenta de Azure y un área de trabajo OMS.**</span><span class="sxs-lookup"><span data-stu-id="4a27f-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="4a27f-117">Si aún no tiene una cuenta de Azure, debe crear uno para usar el análisis de registro de OMS.</span><span class="sxs-lookup"><span data-stu-id="4a27f-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="4a27f-118">Para obtener información acerca de cómo crear una cuenta de Azure y configurar un área de trabajo OMS, vea [Introducción a un área de trabajo de análisis de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="4a27f-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="4a27f-119">**Conector de nube versión 2.1 o posterior**</span><span class="sxs-lookup"><span data-stu-id="4a27f-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="4a27f-120">**Nueva búsqueda de registro de análisis de registro** es necesario para la supervisión de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="4a27f-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="4a27f-121">Para obtener más información, vea [actualizar su área de trabajo de análisis de registro de Azure para nueva búsqueda de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="4a27f-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="4a27f-122">Configurar el conector en la nube para usar OMS</span><span class="sxs-lookup"><span data-stu-id="4a27f-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="4a27f-123">Debe configurar el entorno de nube conector local para usar OMS.</span><span class="sxs-lookup"><span data-stu-id="4a27f-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="4a27f-124">Para ello, necesitará el identificador del área de trabajo OMS y la clave, que puede encontrar mediante el portal de OMS como sigue: configuración--\>orígenes conectados--\> servidores Windows:</span><span class="sxs-lookup"><span data-stu-id="4a27f-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Captura de pantalla de Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="4a27f-126">Cómo configurar el conector en la nube para usar OMS depende de su escenario:</span><span class="sxs-lookup"><span data-stu-id="4a27f-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="4a27f-127">**Si va a instalar un nuevo dispositivo de conector en la nube o desea volver a implementar un dispositivo**, siga estos pasos antes de ejecutar Install-CcAppliance:</span><span class="sxs-lookup"><span data-stu-id="4a27f-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

1. <span data-ttu-id="4a27f-128">En la sección [Common] del archivo de CloudConnector.ini, establezca el parámetro OMSEnabled en True.</span><span class="sxs-lookup"><span data-stu-id="4a27f-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

    <span data-ttu-id="4a27f-129">Cada vez que se implementa o se actualiza, conector en la nube intentará instalar al agente OMS automáticamente en las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="4a27f-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="4a27f-130">Habilitar esta característica, por lo que el agente de OMS puede sobrevivir la actualización automática del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="4a27f-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

2. <span data-ttu-id="4a27f-131">Para configurar el identificador de OMS y la clave, ejecute Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="4a27f-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="4a27f-132">**Si va a instalar un agente OMS en un dispositivo de conector en la nube existente**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4a27f-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

1. <span data-ttu-id="4a27f-133">En la sección [Common] del archivo de CloudConnector.ini, establezca OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="4a27f-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

2. <span data-ttu-id="4a27f-134">Ejecute CcConfiguration de importación.</span><span class="sxs-lookup"><span data-stu-id="4a27f-134">Run Import-CcConfiguration.</span></span> 

3. <span data-ttu-id="4a27f-135">Ejecute Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="4a27f-135">Run Install-CcOMSAgent.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="4a27f-136">Si nunca se ha establecido la credencial del OMSWorkspace, se le pedirán de las credenciales al ejecutar install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="4a27f-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="4a27f-137">**Si desea actualizar la clave en un dispositivo de conector en la nube o el identificador del área de trabajo OMS ya ha instalado a un agente OMS:**</span><span class="sxs-lookup"><span data-stu-id="4a27f-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

1. <span data-ttu-id="4a27f-138">Para configurar el identificador de OMS y la clave, ejecute Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="4a27f-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

2. <span data-ttu-id="4a27f-139">Para aplicar las actualizaciones, ejecute Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="4a27f-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="4a27f-140">**Para todos los escenarios, compruebe que los agentes están conectados como se indica a continuación:**</span><span class="sxs-lookup"><span data-stu-id="4a27f-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="4a27f-141">En el portal de OMS, vaya a configuración -\> orígenes conectados -\> servidores de Windows.</span><span class="sxs-lookup"><span data-stu-id="4a27f-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="4a27f-142">Verá una lista de equipos conectados.</span><span class="sxs-lookup"><span data-stu-id="4a27f-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="4a27f-143">Configuración de OMS</span><span class="sxs-lookup"><span data-stu-id="4a27f-143">Configure OMS</span></span>

<span data-ttu-id="4a27f-144">A continuación, debe especificar la configuración de OMS a través del portal OMS.</span><span class="sxs-lookup"><span data-stu-id="4a27f-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="4a27f-145">Específicamente, necesitará:</span><span class="sxs-lookup"><span data-stu-id="4a27f-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="4a27f-146">Especifique información sobre los registros de eventos y contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4a27f-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="4a27f-147">Crear alertas.</span><span class="sxs-lookup"><span data-stu-id="4a27f-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="4a27f-148">Especificar información acerca de los registros de eventos y contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="4a27f-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="4a27f-149">En el portal de OMS, debe especificar información acerca de los registros de eventos y contadores de rendimiento de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4a27f-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="4a27f-150">Vaya a configuración -\>datos -\>registros de eventos de Windows y agregar los registros de eventos:</span><span class="sxs-lookup"><span data-stu-id="4a27f-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="4a27f-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="4a27f-151">Lync Server</span></span>

   - <span data-ttu-id="4a27f-152">Aplicación</span><span class="sxs-lookup"><span data-stu-id="4a27f-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="4a27f-153">Debe escribir manualmente Lync Server en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="4a27f-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="4a27f-154">No aparece como una opción en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4a27f-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="4a27f-155">Para obtener más información, vea [orígenes de datos de registro de eventos de Windows en el registro de análisis](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="4a27f-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="4a27f-156">Vaya a configuración -\>datos -\> contadores de rendimiento de Windows, y agregar contadores de rendimiento para:</span><span class="sxs-lookup"><span data-stu-id="4a27f-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="4a27f-157">**Contadores de nivel de sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="4a27f-157">**OS level counters**.</span></span> <span data-ttu-id="4a27f-158">Puede agregar contadores de nivel de sistema operativo, como el uso del procesador, el uso de memoria, el uso de la red, o puede usar soluciones existentes, como la capacidad y rendimiento, Monitor de rendimiento de red sin agregar contadores de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="4a27f-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="4a27f-159">Independientemente de cómo decida supervisarlos, Microsoft recomienda supervisar estos contadores de sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4a27f-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="4a27f-160">**Skype para contadores de negocio**.</span><span class="sxs-lookup"><span data-stu-id="4a27f-160">**Skype for Business counters**.</span></span> <span data-ttu-id="4a27f-161">Hay numerosas contadores proporcionados por Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="4a27f-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="4a27f-162">Puede encontrar estos contadores, inicio de sesión en cualquier servidor de mediación y abra al Monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4a27f-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="4a27f-163">Iniciar estos contadores con "LS:".</span><span class="sxs-lookup"><span data-stu-id="4a27f-163">These counters start with "LS:".</span></span> <span data-ttu-id="4a27f-164">Microsoft recomienda que comience con los siguientes contadores de capacidad como mínimo y agregar a otras personas que son de interés:</span><span class="sxs-lookup"><span data-stu-id="4a27f-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="4a27f-165">Total de llamadas activo:</span><span class="sxs-lookup"><span data-stu-id="4a27f-165">Total active calls:</span></span>

   - <span data-ttu-id="4a27f-166">LS:MediationServer - Calls(_Total) entrantes\- actual</span><span class="sxs-lookup"><span data-stu-id="4a27f-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

   - <span data-ttu-id="4a27f-167">LS:MediationServer - Calls(_Total) saliente\- actual</span><span class="sxs-lookup"><span data-stu-id="4a27f-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="4a27f-168">Total de medios active el desvío de llamadas:</span><span class="sxs-lookup"><span data-stu-id="4a27f-168">Total active media bypass calls:</span></span>

   - <span data-ttu-id="4a27f-169">LS:MediationServer - Calls(_Total) entrantes\- multimedia activo el desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="4a27f-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

   - <span data-ttu-id="4a27f-170">LS:MediationServer - Calls(_Total) saliente\- multimedia activo el desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="4a27f-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="4a27f-171">Debe escribir manualmente los contadores de rendimiento en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="4a27f-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="4a27f-172">No aparecen como opciones en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4a27f-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="4a27f-173">Para obtener más información, vea [orígenes de datos de rendimiento de Windows y Linux en análisis de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="4a27f-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="4a27f-174">Crear alertas</span><span class="sxs-lookup"><span data-stu-id="4a27f-174">Create alerts</span></span>

<span data-ttu-id="4a27f-175">Hay dos tipos de alertas en OMS: número de alertas de los resultados y métrico.</span><span class="sxs-lookup"><span data-stu-id="4a27f-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="4a27f-176">Para obtener más información acerca de cómo crear alertas, vea [trabajar con las reglas de alertas en el registro de análisis](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="4a27f-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="4a27f-177">Debe tener en cuenta lo siguiente al crear alertas:</span><span class="sxs-lookup"><span data-stu-id="4a27f-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="4a27f-178">Asegúrese de que la alerta es una alerta de número de resultados, que es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4a27f-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="4a27f-179">Las consultas de demostración requieren que "El número de resultados" se establece en "mayor que 0".</span><span class="sxs-lookup"><span data-stu-id="4a27f-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="4a27f-180">Se recomienda establecer la ventana de tiempo y frecuencia de alertas en 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="4a27f-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="4a27f-181">Se recomienda que no habilite "Suprimir alertas" para alertas de demostración.</span><span class="sxs-lookup"><span data-stu-id="4a27f-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="4a27f-182">Para los escenarios típicos de alerta, Microsoft recomienda crear un par de alertas: alerta de un error y una restablecer alerta.</span><span class="sxs-lookup"><span data-stu-id="4a27f-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="4a27f-183">De la alerta de error, seleccione el nivel de gravedad crítico; de la alerta de restablecimiento, seleccione el nivel de gravedad informativo.</span><span class="sxs-lookup"><span data-stu-id="4a27f-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="4a27f-184">Las secciones siguientes describen cómo crear alertas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4a27f-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="4a27f-185">**Crear un par de alerta: "RTCMEDSRV no se está ejecutando en los servidores de mediación" y "RTCMEDSRV es nuevo en el que se ejecuta en los servidores de mediación"**</span><span class="sxs-lookup"><span data-stu-id="4a27f-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="4a27f-186">Para crear este par de alerta:</span><span class="sxs-lookup"><span data-stu-id="4a27f-186">To create this alert pair:</span></span>

- <span data-ttu-id="4a27f-187">La consulta de la alerta de error es:</span><span class="sxs-lookup"><span data-stu-id="4a27f-187">The query for the error alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="4a27f-188">La consulta usa el filtro de equipo *donde equipo contiene "MediationServer"* .</span><span class="sxs-lookup"><span data-stu-id="4a27f-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="4a27f-189">El filtro selecciona sólo el equipo cuyo nombre contiene la cadena "MediationServer".</span><span class="sxs-lookup"><span data-stu-id="4a27f-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="4a27f-190">¿Reemplazar el filtro con su propio filtro del equipo o simplemente quitarlo.</span><span class="sxs-lookup"><span data-stu-id="4a27f-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="4a27f-191">Puede crear filtros de cadena compleja sin expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="4a27f-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="4a27f-192">Para obtener más información, vea [operadores de cadena](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="4a27f-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="4a27f-193">También puede elegir utilizar expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="4a27f-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="4a27f-194">Además, puede crear un grupo de equipos por guardar una consulta de búsqueda y el uso de ese grupo como el filtro de equipo en la consulta de la alerta.</span><span class="sxs-lookup"><span data-stu-id="4a27f-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="4a27f-195">Para obtener más información, vea [grupos de equipo en el registro de análisis iniciar las búsquedas](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="4a27f-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="4a27f-196">Para cada equipo, la consulta de error obtendrá el último registro de eventos para el inicio de servicio RTCMEDSRV y detención del servicio.</span><span class="sxs-lookup"><span data-stu-id="4a27f-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="4a27f-197">Devolverá uno inicie sesión si el último evento es el evento de detención del servicio; devolverá nothing si el último evento es el evento de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="4a27f-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="4a27f-198">En resumen, la consulta devolvería una lista de servidores cuyo RTCMEDSRV se ha detenido en la ventana de tiempo.</span><span class="sxs-lookup"><span data-stu-id="4a27f-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="4a27f-199">La consulta de la alerta de restablecimiento es:</span><span class="sxs-lookup"><span data-stu-id="4a27f-199">The query for the reset alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="4a27f-200">La consulta de restablecimiento hace exactamente lo opuesto de la consulta de error.</span><span class="sxs-lookup"><span data-stu-id="4a27f-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="4a27f-201">Para cada equipo, devolverá uno si el último evento es el servicio de inicio de evento; devolverá nothing si el último evento es el evento de detención del servicio.</span><span class="sxs-lookup"><span data-stu-id="4a27f-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

  <span data-ttu-id="4a27f-202">**Crear un par de alerta: "demasiados muchas llamadas simultáneas en los servidores de mediación" y "llamadas simultáneas a carga normal"**</span><span class="sxs-lookup"><span data-stu-id="4a27f-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="4a27f-203">Para crear esta alerta:</span><span class="sxs-lookup"><span data-stu-id="4a27f-203">To create this alert:</span></span>

- <span data-ttu-id="4a27f-204">La consulta de la alerta de error es:</span><span class="sxs-lookup"><span data-stu-id="4a27f-204">The query for the error alert is:</span></span>

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="4a27f-205">Para cada equipo, la consulta obtendrá los contadores de última de llamada entrante y saliente llamada y suma esos dos valores.</span><span class="sxs-lookup"><span data-stu-id="4a27f-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="4a27f-206">Devolverá uno inicie sesión si el valor de la suma supera 500; devolverá nothing si no lo hace.</span><span class="sxs-lookup"><span data-stu-id="4a27f-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="4a27f-207">En resumen, la consulta devolvería una lista de servidores cuyas llamadas simultáneas son demasiados en la ventana de tiempo.</span><span class="sxs-lookup"><span data-stu-id="4a27f-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="4a27f-208">La consulta de la alerta de restablecimiento es:</span><span class="sxs-lookup"><span data-stu-id="4a27f-208">The query for the reset alert is:</span></span>

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="4a27f-209">La consulta de restablecimiento hace exactamente lo opuesto de la consulta de error.</span><span class="sxs-lookup"><span data-stu-id="4a27f-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="4a27f-210">Para cada equipo, la consulta obtendrá los contadores de última de llamada entrante y saliente llamada y suma esos dos valores.</span><span class="sxs-lookup"><span data-stu-id="4a27f-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="4a27f-211">Devolverá un registro si el valor de suma es menor que 500; devolverá nothing en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="4a27f-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

  <span data-ttu-id="4a27f-212">**Crear una alerta: "el uso de CPU \> 90 o RTCMEDIARELAY detenido en servidores" alerta**</span><span class="sxs-lookup"><span data-stu-id="4a27f-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="4a27f-213">Para crear esta alerta, la consulta es:</span><span class="sxs-lookup"><span data-stu-id="4a27f-213">To create this alert, the query is:</span></span>

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="4a27f-214">La consulta obtendrá todos los contadores de uso de procesador y eventos de detención del servicio de todos los equipos y devolver un registro si puede ser el uso del procesador supera el 90% o servicio nunca se ha detenido.</span><span class="sxs-lookup"><span data-stu-id="4a27f-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="4a27f-215">Analizar las alertas en el repositorio de análisis de registro</span><span class="sxs-lookup"><span data-stu-id="4a27f-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="4a27f-216">Para analizar las alertas en el repositorio, use la solución de administración de alertas.</span><span class="sxs-lookup"><span data-stu-id="4a27f-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="4a27f-217">Para obtener más información, vea [solución de administración de alertas en conjunto de aplicaciones de administración de operaciones (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="4a27f-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="4a27f-218">Conjunto de supervisión mínimo recomendado</span><span class="sxs-lookup"><span data-stu-id="4a27f-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="4a27f-219">Para identificar problemas con los registros de eventos y contadores de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="4a27f-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="4a27f-220">**Registros de eventos.**</span><span class="sxs-lookup"><span data-stu-id="4a27f-220">**Event logs.**</span></span> <span data-ttu-id="4a27f-221">Para cualquier problema, debería haber un par de eventos, con un conjunto de eventos para indicar que algo está mal, mientras que la otra indica que todo está bien.</span><span class="sxs-lookup"><span data-stu-id="4a27f-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="4a27f-222">Para cualquier período de tiempo determinado, es el último evento registrado que va a indicar si algo es avisan para ese período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="4a27f-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="4a27f-223">**Contadores de rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="4a27f-223">**Performance Counters.**</span></span> <span data-ttu-id="4a27f-224">Debe haber un umbral de los contadores supervisados.</span><span class="sxs-lookup"><span data-stu-id="4a27f-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="4a27f-225">En la siguiente tabla se enumera los servicios que Microsoft recomienda supervisión con una lista de los identificadores de sucesos detener e iniciar:</span><span class="sxs-lookup"><span data-stu-id="4a27f-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="4a27f-226">Nombre de servicio</span><span class="sxs-lookup"><span data-stu-id="4a27f-226">Service Name</span></span>  <br/> |<span data-ttu-id="4a27f-227">Función de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="4a27f-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="4a27f-228">Detener el identificador de evento</span><span class="sxs-lookup"><span data-stu-id="4a27f-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="4a27f-229">Identificador de evento de inicio</span><span class="sxs-lookup"><span data-stu-id="4a27f-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4a27f-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="4a27f-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="4a27f-231">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="4a27f-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="4a27f-232">25003</span><span class="sxs-lookup"><span data-stu-id="4a27f-232">25003</span></span>  <br/> |<span data-ttu-id="4a27f-233">25002</span><span class="sxs-lookup"><span data-stu-id="4a27f-233">25002</span></span>  <br/> |
|<span data-ttu-id="4a27f-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="4a27f-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="4a27f-235">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4a27f-235">Edge Server</span></span>  <br/> |<span data-ttu-id="4a27f-236">12289</span><span class="sxs-lookup"><span data-stu-id="4a27f-236">12289</span></span>  <br/> |<span data-ttu-id="4a27f-237">12288</span><span class="sxs-lookup"><span data-stu-id="4a27f-237">12288</span></span>  <br/> |
|<span data-ttu-id="4a27f-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="4a27f-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="4a27f-239">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4a27f-239">Edge Server</span></span>  <br/> |<span data-ttu-id="4a27f-240">19003</span><span class="sxs-lookup"><span data-stu-id="4a27f-240">19003</span></span>  <br/> |<span data-ttu-id="4a27f-241">19002</span><span class="sxs-lookup"><span data-stu-id="4a27f-241">19002</span></span>  <br/> |
|<span data-ttu-id="4a27f-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="4a27f-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="4a27f-243">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4a27f-243">Edge Server</span></span>  <br/> |<span data-ttu-id="4a27f-244">22003</span><span class="sxs-lookup"><span data-stu-id="4a27f-244">22003</span></span>  <br/> |<span data-ttu-id="4a27f-245">22002</span><span class="sxs-lookup"><span data-stu-id="4a27f-245">22002</span></span>  <br/> |

<span data-ttu-id="4a27f-246">En la siguiente tabla se enumera los problemas de red que Microsoft recomienda supervisión:</span><span class="sxs-lookup"><span data-stu-id="4a27f-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="4a27f-247">Nombre de Monitor</span><span class="sxs-lookup"><span data-stu-id="4a27f-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="4a27f-248">Función de servidor de destino</span><span class="sxs-lookup"><span data-stu-id="4a27f-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="4a27f-249">Expresión de identificador de evento de éxito</span><span class="sxs-lookup"><span data-stu-id="4a27f-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="4a27f-250">Expresión de identificador de evento de error</span><span class="sxs-lookup"><span data-stu-id="4a27f-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="4a27f-251">Ejemplo de error</span><span class="sxs-lookup"><span data-stu-id="4a27f-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="4a27f-252">Error de conectividad de puerta de enlace con el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="4a27f-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="4a27f-253">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="4a27f-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="4a27f-254">25062</span><span class="sxs-lookup"><span data-stu-id="4a27f-254">25062</span></span>                              |                                  | <span data-ttu-id="4a27f-255">25002</span><span class="sxs-lookup"><span data-stu-id="4a27f-255">25002</span></span>  <br/>           |
| <span data-ttu-id="4a27f-256">Error de finalización de llamadas de servidor de mediación a la puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="4a27f-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="4a27f-257">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="4a27f-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="4a27f-258">25064</span><span class="sxs-lookup"><span data-stu-id="4a27f-258">25064</span></span>                              |                                  | <span data-ttu-id="4a27f-259">25002</span><span class="sxs-lookup"><span data-stu-id="4a27f-259">25002</span></span>  <br/>           |
| <span data-ttu-id="4a27f-260">Problemas de la red</span><span class="sxs-lookup"><span data-stu-id="4a27f-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="4a27f-261">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4a27f-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="4a27f-262">14353</span><span class="sxs-lookup"><span data-stu-id="4a27f-262">14353</span></span>                              |                                  | <span data-ttu-id="4a27f-263">12288</span><span class="sxs-lookup"><span data-stu-id="4a27f-263">12288</span></span>  <br/>           |

<span data-ttu-id="4a27f-264">A continuación enumeran los contadores de la capacidad de llamadas que deben supervisarse.</span><span class="sxs-lookup"><span data-stu-id="4a27f-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="4a27f-265">Estos números deben ser menor que 500 para standard edition en la nube conector; menos de 50 para edición mínima de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="4a27f-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="4a27f-266">LS:MediationServer - Calls(_Total) entrantes\- actual</span><span class="sxs-lookup"><span data-stu-id="4a27f-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="4a27f-267">LS:MediationServer - Calls(_Total) saliente\- actual</span><span class="sxs-lookup"><span data-stu-id="4a27f-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="4a27f-268">LS:MediationServer - Calls(_Total) entrantes\- multimedia activo el desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="4a27f-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="4a27f-269">LS:MediationServer - Calls(_Total) saliente\- multimedia activo el desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="4a27f-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="4a27f-270">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a27f-270">See also</span></span>

<span data-ttu-id="4a27f-271">Para obtener más información sobre cómo trabajar con OMS, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a27f-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="4a27f-272">Buscar datos de uso de búsquedas de registro en el registro de análisis</span><span class="sxs-lookup"><span data-stu-id="4a27f-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="4a27f-273">Referencia del lenguaje de análisis de registro de Azure</span><span class="sxs-lookup"><span data-stu-id="4a27f-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="4a27f-274">Conceptos básicos sobre alertas en el registro de análisis</span><span class="sxs-lookup"><span data-stu-id="4a27f-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="4a27f-275">Conectar los equipos de Windows con el servicio de análisis de registro en Azure</span><span class="sxs-lookup"><span data-stu-id="4a27f-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


