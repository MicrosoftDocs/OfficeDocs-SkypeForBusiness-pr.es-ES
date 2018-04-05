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
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Supervisar el conector de nube mediante Operations Management Suite (OMS)
 
Lea este tema para aprender a supervisar la versión del conector de nube 2.1 y posterior implementación mediante Microsoft Operations Management Suite (OMS).
  
Ahora puede supervisar la versión del conector de nube 2.1 y posterior implementación mediante Operations Management Suite (OMS), una solución de administración de TI de nube de Microsoft. Análisis del registro de OMS permite supervisar y analizar la disponibilidad y el rendimiento de los recursos incluidos físicos y máquinas virtuales. Para obtener más información acerca de OMS y análisis de registro, consulte [¿Qué es la serie de administración de operaciones (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).
  
Este tema incluye las secciones siguientes:
  
- Requisitos previos
    
- Configurar el conector de nube para usar OMS
    
- Configurar OMS
    
- Analizar las alertas en el repositorio de análisis de registro
    
- Conjunto recomendado de supervisión
    
## <a name="prerequisites"></a>Requisitos previos

Para poder utilizar OMS para supervisar la implementación del conector de la nube, necesitará lo siguiente:
  
- **Una cuenta de Azure y un área de trabajo OMS.** Si ya no tienes una cuenta de Azure, debe crear uno para utilizar el análisis del registro de OMS. Para obtener información acerca de cómo crear una cuenta de Azure y establecer un área de trabajo OMS, consulte [Introducción a un área de trabajo de análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).
    
- **Conector de nube versión 2.1 o posterior**
    
- **Nueva búsqueda de registros de análisis de registro** es necesario para la supervisión del conector de la nube. Para obtener más información, consulte [actualizar el área de trabajo de análisis de registro de Azure a nueva búsqueda de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).
    
## <a name="configure-cloud-connector-to-use-oms"></a>Configurar el conector de nube para usar OMS

Debe configurar el entorno de nube conector local para usar OMS. Para ello, necesitará su Id. de área de trabajo OMS y clave, que puede encontrar mediante el portal OMS como sigue: configuración--\>orígenes conectados--\> servidores Windows:
  
![Captura de pantalla de Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)
  
Cómo configurar el conector de nube para usar OMS depende de su escenario:
  
- **Si va a instalar un nuevo dispositivo conector de nube o desea volver a implementar un dispositivo**, siga estos pasos antes de ejecutar CcAppliance de instalación:
    
1. En la sección [Common] del archivo de CloudConnector.ini, establezca el parámetro OMSEnabled en True.
    
    Cada vez se implementan o actualizado, conector de nube intentará instalar al agente OMS automáticamente en las máquinas virtuales. Habilitar esta característica para que el agente OMS puede sobrevivir a la actualización automática del conector de la nube.
    
2. Para configurar el ID de la OMS y la clave, ejecute Set-CcCredential - AccountType OMSWorkspace. 
    
- **Si va a instalar un agente OMS en un dispositivo conector de nube existente**, siga estos pasos:
    
1. En la sección [Common] del archivo de CloudConnector.ini, establezca OMSEnabled = true. 
    
2. Ejecute CcConfiguration de importación. 
    
3. Ejecute la instalación CcOMSAgent. 
    
    > [!NOTE]
    > Si nunca se ha establecido la credencial de OMSWorkspace, se pedirá la credencial al ejecutar install-CcOMSAgent. 
  
- **Si desea actualizar el identificador de área de trabajo OMS o clave en un dispositivo conector de nube ya ha instalado a un agente OMS:**
    
1. Para configurar el ID de la OMS y la clave, ejecute Set-CcCredential - AccountType OMSWorkspace. 
    
2. Para aplicar las actualizaciones, ejecute Install-CcOMSAgent. 
    
- **Para todos los escenarios, compruebe que los agentes están conectados como se indica a continuación:**
    
    En el portal OMS, vaya a configuración -\> orígenes conectados -\> servidores Windows. Verá una lista de los equipos conectados. 
    
## <a name="configure-oms"></a>Configurar OMS

A continuación, debe especificar la configuración de OMS mediante el portal OMS. Específicamente, necesitará:
  
- Especificar información sobre registros de eventos y contadores de rendimiento.
    
- Crear alertas. 
    
### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especificar información sobre registros de eventos y contadores de rendimiento

En el portal de la OMS, debe especificar información sobre los registros de sucesos y contadores de rendimiento como sigue:
  
1. Vaya a configuración -\>de datos -\>registros de sucesos de Windows y agregar los registros de sucesos: 
    
  - Lync Server
    
  - Aplicación
    
    > [!NOTE]
    > Debe especificar manualmente Lync Server en el cuadro de texto. No aparece como opción en la lista desplegable. 
  
    Para obtener más información, vea [orígenes de datos de registro de sucesos de Windows en análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)
    
2. Vaya a configuración -\>de datos -\> contadores de rendimiento de Windows, y agregar los contadores de rendimiento para: 
    
  - **Contadores de nivel de sistema operativo**. Puede agregar contadores de nivel de sistema operativo, como el uso del procesador, uso de memoria, uso de la red, o puede usar soluciones existentes, como la capacidad y rendimiento, Monitor de rendimiento de red sin agregar contadores explícitamente. Independientemente de cómo decida supervisarlos, Microsoft recomienda que supervise estos contadores de sistema operativo.
    
  - **Skype para contadores de negocios**. Hay muchos contadores proporcionados por Skype para empresas. Puede encontrar estos contadores, iniciar sesión en cualquier servidor de mediación y abra al Monitor de rendimiento. Estos contadores se inicia con "LS:". Microsoft recomienda que comience con los siguientes contadores de capacidad como mínimo y agregar otras que son de interés:
    
    Número total de llamadas activa:
    
  - LS:MediationServer - Calls(_Total) entrada\- actual 
    
  - LS:MediationServer - Calls(_Total) de salida\- actual 
    
    Total de medios active omitir las llamadas:
    
  - LS:MediationServer - Calls(_Total) entrada\- multimedia activo omitir las llamadas 
    
  - LS:MediationServer - Calls(_Total) de salida\- multimedia activo omitir las llamadas 
    
    > [!NOTE]
    > Debe especificar manualmente los contadores de rendimiento en el cuadro de texto. No aparecen como opciones en la lista desplegable. 
  
    Para obtener más información, vea [orígenes de datos de rendimiento de Windows y Linux en el análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)
    
### <a name="create-alerts"></a>Crear alertas

Hay dos tipos de avisos de OMS: número de alertas de resultados y métrico. Para obtener más información acerca de la creación de alertas, consulte [trabajar con reglas de alertas en el registro de análisis](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).
  
Debe considerar lo siguiente al crear alertas:
  
- Asegúrese de que la alerta es una alerta de número de los resultados, que es la selección predeterminada. 
    
- Las consultas de demostración requieren que "El número de resultados" está establecido a "mayor que 0". 
    
- Se recomienda establecer lapso de tiempo y frecuencia de alertas a 5 minutos. 
    
- Se recomienda que no habilite "Suprimir alertas" para alertas de demostración. 
    
- Para los escenarios típicos de alerta, Microsoft recomienda crear un par de alertas: alerta de un error y una restablecer alerta. La alerta de error, seleccione el nivel de gravedad crítico; la alerta de reinicio, seleccione el nivel de gravedad informativo.
    
Las secciones siguientes describen cómo crear alertas de ejemplo.
  
 **Crear un par de alerta: "RTCMEDSRV no se ejecuta en los servidores de mediación" y "RTCMEDSRV está en ejecución en servidores de mediación"**
  
Para crear este par de alerta:
  
- La consulta para la alerta de error es:
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La consulta usa el filtro de equipo *en equipo contiene "MediationServer"* . El filtro selecciona sólo el equipo cuyo nombre contiene la cadena "MediationServer".
    
     ¿Reemplazar el filtro con el filtro de su propio equipo o simplemente eliminarlo. Puede crear filtros de cadena compleja sin expresiones regulares. Para obtener más información, vea [operadores de cadena](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). También puede utilizar expresiones regulares. Además, puede crear un grupo de equipos por guardar una consulta de búsqueda y el uso de ese grupo como filtro de equipo en la consulta de alerta. Para obtener más información, vea [grupos de equipo de análisis de registro iniciar búsquedas](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).
    
    Para cada equipo, el error de la consulta obtendrá el último registro de eventos para el inicio de servicio RTCMEDSRV y detención de servicios. Devolverá una iniciar sesión si el último evento es el evento de detención del servicio; no devolverá nada si el último evento es el evento de inicio del servicio. En resumen, la consulta devolvería una lista de servidores cuyo RTCMEDSRV se detiene en la ventana de tiempo. 
    
- La consulta para la alerta de restablecimiento es:
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La consulta de reinicio hace exactamente lo opuesto de la consulta de error. Para cada equipo, devolverá uno si el último evento es el servicio de inicio de evento; no devolverá nada si el último evento es el evento de detención del servicio.
    
 **Crear un par de alerta: "demasiados muchas llamadas simultáneas en servidores de mediación" y "llamadas simultáneas a carga normal"**
  
Para crear esta alerta:
  
- La consulta para la alerta de error es:
    
  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName 
== "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada equipo, la consulta obtendrá los contadores última llamada entrante, llamada saliente y suma esos dos valores. Devolverá una sesión si el valor de la suma supera 500; no devolverá nada si no es así. En resumen, la consulta devolvería una lista de servidores cuyas llamadas simultáneas son demasiados en la ventana de tiempo.
    
- La consulta para la alerta de restablecimiento es:
    
  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==
 "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500

  ```

    La consulta de reinicio hace exactamente lo opuesto de la consulta de error. Para cada equipo, la consulta obtendrá los contadores última llamada entrante, llamada saliente y suma esos dos valores. Devolverá un registro si el valor de la suma es menor que 500; devolverá nothing en caso contrario.
    
 **Crear una alerta: "uso de la CPU \> 90 o RTCMEDIARELAY detenido en servidores" alerta**
  
Para crear esta alerta, la consulta es:
  
```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==
 "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La consulta obtendrá todos los contadores de uso del procesador y el evento de detención del servicio de todos los equipos y devuelve un registro si el uso del procesador supera el 90% o servicio nunca se detiene. 
  
## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analizar las alertas en el repositorio de análisis de registro

Para analizar las alertas en el repositorio, utilice la solución de administración de alertas. Para obtener más información, consulte [solución de administración de alertas de Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)
  
## <a name="recommended-minimal-monitoring-set"></a>Conjunto de supervisión mínimo recomendado

Para identificar problemas con los registros de sucesos y contadores de rendimiento: 
  
- **Registros de eventos.** Para cualquier problema, debería haber un par de eventos, con un conjunto de eventos que indican que algo va mal, mientras que el otro indica que todo está bien. Durante cualquier período de tiempo, es el último suceso grabado que indicará si algo está mal durante ese período de tiempo.
    
- **Contadores de rendimiento.** Debe haber un umbral de los contadores supervisados.
    
En la tabla siguiente se enumera los servicios que Microsoft recomienda supervisar con una lista de los identificadores de sucesos de inicio y de parada:
  
|Nombre de servicio  <br/> |Función de servidor de destino  <br/> |Id. de suceso de detener  <br/> |Id. de suceso de inicio  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de mediación  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor perimetral  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor perimetral  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor perimetral  <br/> |22003  <br/> |22002  <br/> |
   
En la tabla siguiente enumera los problemas de red que Microsoft recomienda la supervisión:
  
|Nombre de Monitor  <br/> |Función de servidor de destino  <br/> |Expresión de ID de evento de éxito  <br/> |Expresión de ID de evento de error  <br/> |Ejemplo de error  <br/> |
|:-----|:-----|:-----|:-----|:-----|
|Servidor de mediación para error de conectividad de la puerta de enlace  <br/> |Servidor de mediación  <br/> |25062 || 25002  <br/> |25061  <br/> |Error de MS PING Gateway (opción)  <br/> |
|Servidor de mediación para la puerta de enlace de llamar a error de finalización  <br/> |Servidor de mediación  <br/> |25064 || 25002  <br/> |25063  <br/> |Error de MS trata de realizar la llamada a la puerta de enlace  <br/> |
|Problemas de la red  <br/> |Servidor perimetral  <br/> |14353 || 12288  <br/> |14624  <br/> |No se pudo iniciar en la dirección IP local 192.168.231.14 en el puerto 5061 transporte TLS  <br/> |
   
A continuación enumeran los contadores de capacidad de llamada que se deben supervisar. Estos números deben ser menor que 500 para standard edition nube conector; menos de 50 para edición mínima del conector de la nube.
  
- LS:MediationServer - Calls(_Total) entrada\- actual 
    
- LS:MediationServer - Calls(_Total) de salida\- actual 
    
- LS:MediationServer - Calls(_Total) entrada\- multimedia activo omitir las llamadas
    
- LS:MediationServer - Calls(_Total) de salida\- multimedia activo omitir las llamadas
    
## <a name="see-also"></a>Vea también

Para obtener más información acerca de cómo trabajar con la OMS, consulte lo siguiente:
  
- [Buscar datos mediante búsquedas de registro de análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)
    
- [Referencia del lenguaje de registro Azure Analytics](https://docs.loganalytics.io/docs/Language-Reference)
    
- [Información sobre alertas en el registro de análisis](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)
    
- [Conectar los equipos de Windows para el servicio de análisis de registro en Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)
    

