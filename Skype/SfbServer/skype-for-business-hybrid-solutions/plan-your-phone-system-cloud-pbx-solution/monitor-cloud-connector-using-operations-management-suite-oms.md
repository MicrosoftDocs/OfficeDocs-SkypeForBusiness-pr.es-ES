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
ms.openlocfilehash: 160fcfc4baade7bc59d41771b0fd86d3cb725cab
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569764"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Supervisar el conector en la nube con el conjunto de aplicaciones de administración de operaciones (OMS)
 
Lea este tema para obtener información acerca de cómo supervisar la versión 2.1 de conector en la nube y la implementación posterior mediante el uso conjunto de aplicaciones de administración de operaciones de Microsoft (OMS).
  
Ahora puede supervisar la versión 2.1 de conector en la nube y la implementación posterior mediante el uso conjunto de aplicaciones de administración de operaciones (OMS), una solución de administración de TI de nube de Microsoft. Análisis del registro de OMS le permite supervisar y analizar la disponibilidad y el rendimiento de los recursos incluidos físicos y máquinas virtuales. Para obtener más información acerca de OMS y análisis de registro, vea [¿Qué es el conjunto de aplicaciones de administración de operaciones (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).
  
Este tema incluye las secciones siguientes:
  
- Requisitos previos
    
- Configurar el conector en la nube para usar OMS
    
- Configuración de OMS
    
- Analizar las alertas en el repositorio de análisis de registro
    
- Conjunto de supervisión recomendado
    
## <a name="prerequisites"></a>Requisitos previos

Antes de que puede usar OMS para supervisar la implementación del conector de la nube, necesitará lo siguiente:
  
- **Una cuenta de Azure y un área de trabajo OMS.** Si aún no tiene una cuenta de Azure, debe crear uno para usar el análisis de registro de OMS. Para obtener información acerca de cómo crear una cuenta de Azure y configurar un área de trabajo OMS, vea [Introducción a un área de trabajo de análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).
    
- **Conector de nube versión 2.1 o posterior**
    
- **Nueva búsqueda de registro de análisis de registro** es necesario para la supervisión de conector en la nube. Para obtener más información, vea [actualizar su área de trabajo de análisis de registro de Azure para nueva búsqueda de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).
    
## <a name="configure-cloud-connector-to-use-oms"></a>Configurar el conector en la nube para usar OMS

Debe configurar el entorno de nube conector local para usar OMS. Para ello, necesitará el identificador del área de trabajo OMS y la clave, que puede encontrar mediante el portal de OMS como sigue: configuración--\>orígenes conectados--\> servidores Windows:
  
![Captura de pantalla de Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)
  
Cómo configurar el conector en la nube para usar OMS depende de su escenario:
  
- **Si va a instalar un nuevo dispositivo de conector en la nube o desea volver a implementar un dispositivo**, siga estos pasos antes de ejecutar Install-CcAppliance:
    
1. En la sección [Common] del archivo de CloudConnector.ini, establezca el parámetro OMSEnabled en True.
    
    Cada vez que se implementa o se actualiza, conector en la nube intentará instalar al agente OMS automáticamente en las máquinas virtuales. Habilitar esta característica, por lo que el agente de OMS puede sobrevivir la actualización automática del conector en la nube.
    
2. Para configurar el identificador de OMS y la clave, ejecute Set-CcCredential - AccountType OMSWorkspace. 
    
- **Si va a instalar un agente OMS en un dispositivo de conector en la nube existente**, siga estos pasos:
    
1. En la sección [Common] del archivo de CloudConnector.ini, establezca OMSEnabled = true. 
    
2. Ejecute CcConfiguration de importación. 
    
3. Ejecute Install-CcOMSAgent. 
    
    > [!NOTE]
    > Si nunca se ha establecido la credencial del OMSWorkspace, se le pedirán de las credenciales al ejecutar install-CcOMSAgent. 
  
- **Si desea actualizar la clave en un dispositivo de conector en la nube o el identificador del área de trabajo OMS ya ha instalado a un agente OMS:**
    
1. Para configurar el identificador de OMS y la clave, ejecute Set-CcCredential - AccountType OMSWorkspace. 
    
2. Para aplicar las actualizaciones, ejecute Install-CcOMSAgent. 
    
- **Para todos los escenarios, compruebe que los agentes están conectados como se indica a continuación:**
    
    En el portal de OMS, vaya a configuración -\> orígenes conectados -\> servidores de Windows. Verá una lista de equipos conectados. 
    
## <a name="configure-oms"></a>Configuración de OMS

A continuación, debe especificar la configuración de OMS a través del portal OMS. Específicamente, necesitará:
  
- Especifique información sobre los registros de eventos y contadores de rendimiento.
    
- Crear alertas. 
    
### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especificar información acerca de los registros de eventos y contadores de rendimiento

En el portal de OMS, debe especificar información acerca de los registros de eventos y contadores de rendimiento de la siguiente manera:
  
1. Vaya a configuración -\>datos -\>registros de eventos de Windows y agregar los registros de eventos: 
    
  - Lync Server
    
  - Aplicación
    
    > [!NOTE]
    > Debe escribir manualmente Lync Server en el cuadro de texto. No aparece como una opción en la lista desplegable. 
  
    Para obtener más información, vea [orígenes de datos de registro de eventos de Windows en el registro de análisis](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)
    
2. Vaya a configuración -\>datos -\> contadores de rendimiento de Windows, y agregar contadores de rendimiento para: 
    
  - **Contadores de nivel de sistema operativo**. Puede agregar contadores de nivel de sistema operativo, como el uso del procesador, el uso de memoria, el uso de la red, o puede usar soluciones existentes, como la capacidad y rendimiento, Monitor de rendimiento de red sin agregar contadores de forma explícita. Independientemente de cómo decida supervisarlos, Microsoft recomienda supervisar estos contadores de sistema operativo.
    
  - **Skype para contadores de negocio**. Hay numerosas contadores proporcionados por Skype para la empresa. Puede encontrar estos contadores, inicio de sesión en cualquier servidor de mediación y abra al Monitor de rendimiento. Iniciar estos contadores con "LS:". Microsoft recomienda que comience con los siguientes contadores de capacidad como mínimo y agregar a otras personas que son de interés:
    
    Total de llamadas activo:
    
  - LS:MediationServer - Calls(_Total) entrantes\- actual 
    
  - LS:MediationServer - Calls(_Total) saliente\- actual 
    
    Total de medios active el desvío de llamadas:
    
  - LS:MediationServer - Calls(_Total) entrantes\- multimedia activo el desvío de llamadas 
    
  - LS:MediationServer - Calls(_Total) saliente\- multimedia activo el desvío de llamadas 
    
    > [!NOTE]
    > Debe escribir manualmente los contadores de rendimiento en el cuadro de texto. No aparecen como opciones en la lista desplegable. 
  
    Para obtener más información, vea [orígenes de datos de rendimiento de Windows y Linux en análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)
    
### <a name="create-alerts"></a>Crear alertas

Hay dos tipos de alertas en OMS: número de alertas de los resultados y métrico. Para obtener más información acerca de cómo crear alertas, vea [trabajar con las reglas de alertas en el registro de análisis](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).
  
Debe tener en cuenta lo siguiente al crear alertas:
  
- Asegúrese de que la alerta es una alerta de número de resultados, que es la selección predeterminada. 
    
- Las consultas de demostración requieren que "El número de resultados" se establece en "mayor que 0". 
    
- Se recomienda establecer la ventana de tiempo y frecuencia de alertas en 5 minutos. 
    
- Se recomienda que no habilite "Suprimir alertas" para alertas de demostración. 
    
- Para los escenarios típicos de alerta, Microsoft recomienda crear un par de alertas: alerta de un error y una restablecer alerta. De la alerta de error, seleccione el nivel de gravedad crítico; de la alerta de restablecimiento, seleccione el nivel de gravedad informativo.
    
Las secciones siguientes describen cómo crear alertas de ejemplo.
  
 **Crear un par de alerta: "RTCMEDSRV no se está ejecutando en los servidores de mediación" y "RTCMEDSRV es nuevo en el que se ejecuta en los servidores de mediación"**
  
Para crear este par de alerta:
  
- La consulta de la alerta de error es:
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La consulta usa el filtro de equipo *donde equipo contiene "MediationServer"* . El filtro selecciona sólo el equipo cuyo nombre contiene la cadena "MediationServer".
    
     ¿Reemplazar el filtro con su propio filtro del equipo o simplemente quitarlo. Puede crear filtros de cadena compleja sin expresiones regulares. Para obtener más información, vea [operadores de cadena](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). También puede elegir utilizar expresiones regulares. Además, puede crear un grupo de equipos por guardar una consulta de búsqueda y el uso de ese grupo como el filtro de equipo en la consulta de la alerta. Para obtener más información, vea [grupos de equipo en el registro de análisis iniciar las búsquedas](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).
    
    Para cada equipo, la consulta de error obtendrá el último registro de eventos para el inicio de servicio RTCMEDSRV y detención del servicio. Devolverá uno inicie sesión si el último evento es el evento de detención del servicio; devolverá nothing si el último evento es el evento de inicio del servicio. En resumen, la consulta devolvería una lista de servidores cuyo RTCMEDSRV se ha detenido en la ventana de tiempo. 
    
- La consulta de la alerta de restablecimiento es:
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La consulta de restablecimiento hace exactamente lo opuesto de la consulta de error. Para cada equipo, devolverá uno si el último evento es el servicio de inicio de evento; devolverá nothing si el último evento es el evento de detención del servicio.
    
 **Crear un par de alerta: "demasiados muchas llamadas simultáneas en los servidores de mediación" y "llamadas simultáneas a carga normal"**
  
Para crear esta alerta:
  
- La consulta de la alerta de error es:
    
  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada equipo, la consulta obtendrá los contadores de última de llamada entrante y saliente llamada y suma esos dos valores. Devolverá uno inicie sesión si el valor de la suma supera 500; devolverá nothing si no lo hace. En resumen, la consulta devolvería una lista de servidores cuyas llamadas simultáneas son demasiados en la ventana de tiempo.
    
- La consulta de la alerta de restablecimiento es:
    
  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La consulta de restablecimiento hace exactamente lo opuesto de la consulta de error. Para cada equipo, la consulta obtendrá los contadores de última de llamada entrante y saliente llamada y suma esos dos valores. Devolverá un registro si el valor de suma es menor que 500; devolverá nothing en caso contrario.
    
 **Crear una alerta: "el uso de CPU \> 90 o RTCMEDIARELAY detenido en servidores" alerta**
  
Para crear esta alerta, la consulta es:
  
```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La consulta obtendrá todos los contadores de uso de procesador y eventos de detención del servicio de todos los equipos y devolver un registro si puede ser el uso del procesador supera el 90% o servicio nunca se ha detenido. 
  
## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analizar las alertas en el repositorio de análisis de registro

Para analizar las alertas en el repositorio, use la solución de administración de alertas. Para obtener más información, vea [solución de administración de alertas en conjunto de aplicaciones de administración de operaciones (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)
  
## <a name="recommended-minimal-monitoring-set"></a>Conjunto de supervisión mínimo recomendado

Para identificar problemas con los registros de eventos y contadores de rendimiento: 
  
- **Registros de eventos.** Para cualquier problema, debería haber un par de eventos, con un conjunto de eventos para indicar que algo está mal, mientras que la otra indica que todo está bien. Para cualquier período de tiempo determinado, es el último evento registrado que va a indicar si algo es avisan para ese período de tiempo.
    
- **Contadores de rendimiento.** Debe haber un umbral de los contadores supervisados.
    
En la siguiente tabla se enumera los servicios que Microsoft recomienda supervisión con una lista de los identificadores de sucesos detener e iniciar:
  
|Nombre de servicio  <br/> |Función de servidor de destino  <br/> |Detener el identificador de evento  <br/> |Identificador de evento de inicio  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de mediación  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor perimetral  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor perimetral  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor perimetral  <br/> |22003  <br/> |22002  <br/> |
   
En la siguiente tabla se enumera los problemas de red que Microsoft recomienda supervisión:
  
|Nombre de Monitor  <br/> |Función de servidor de destino  <br/> |Expresión de identificador de evento de éxito  <br/> |Expresión de identificador de evento de error  <br/> |Ejemplo de error  <br/> |
|:-----|:-----|:-----|:-----|:-----|
|Error de conectividad de puerta de enlace con el servidor de mediación  <br/> |Servidor de mediación  <br/> |25062 || 25002  <br/> |25061  <br/> |Error de PING (opción) puerta de enlace de MS  <br/> |
|Error de finalización de llamadas de servidor de mediación a la puerta de enlace  <br/> |Servidor de mediación  <br/> |25064 || 25002  <br/> |25063  <br/> |Error al intentar realizar una llamada a la puerta de enlace de MS  <br/> |
|Problemas de la red  <br/> |Servidor perimetral  <br/> |14353 || 12288  <br/> |14624  <br/> |No se pudo iniciar en la dirección IP local 192.168.231.14 en el puerto 5061 transporte TLS  <br/> |
   
A continuación enumeran los contadores de la capacidad de llamadas que deben supervisarse. Estos números deben ser menor que 500 para standard edition en la nube conector; menos de 50 para edición mínima de conector en la nube.
  
- LS:MediationServer - Calls(_Total) entrantes\- actual 
    
- LS:MediationServer - Calls(_Total) saliente\- actual 
    
- LS:MediationServer - Calls(_Total) entrantes\- multimedia activo el desvío de llamadas
    
- LS:MediationServer - Calls(_Total) saliente\- multimedia activo el desvío de llamadas
    
## <a name="see-also"></a>Vea también

Para obtener más información sobre cómo trabajar con OMS, consulte lo siguiente:
  
- [Buscar datos de uso de búsquedas de registro en el registro de análisis](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)
    
- [Referencia del lenguaje de análisis de registro de Azure](https://docs.loganalytics.io/docs/Language-Reference)
    
- [Conceptos básicos sobre alertas en el registro de análisis](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)
    
- [Conectar los equipos de Windows con el servicio de análisis de registro en Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)
    

