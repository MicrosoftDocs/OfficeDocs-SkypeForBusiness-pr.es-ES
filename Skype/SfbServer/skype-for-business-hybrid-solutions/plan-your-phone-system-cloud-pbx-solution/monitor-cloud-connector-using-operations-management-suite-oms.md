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
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lea este tema para obtener información sobre cómo supervisar la implementación de la versión 2,1 y posteriores de su conector de la nube mediante Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 6258ad9386b895f97a6f6dc0a1b40ce1076568aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287268"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Supervisar Cloud Connector con Operations Management Suite (OMS)

Lea este tema para obtener información sobre cómo supervisar la implementación de la versión 2,1 y posteriores de su conector de la nube mediante Microsoft Operations Management Suite (OMS).

Ahora puede supervisar la implementación de la versión 2,1 y posterior de su conector de nube con Operations Management Suite (OMS), una solución de administración de TI en la nube de Microsoft. El análisis de registros de OMS le permite supervisar y analizar la disponibilidad y el rendimiento de los recursos, incluidas las máquinas físicas y virtuales. Para obtener más información sobre OMS y el análisis de registros, consulte [¿Qué es Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).

Este tema incluye las secciones siguientes:

- Requisitos previos

- Configurar el conector de nube para usar OMS

- Configurar OMS

- Analizar las alertas de su repositorio de análisis de registros

- Conjunto de supervisión recomendado

## <a name="prerequisites"></a>Requisitos previos

Antes de poder usar OMS para supervisar la implementación de su conector de nube, necesitará lo siguiente:

- **Una cuenta de Azure y un área de trabajo de OMS.** Si aún no tiene una cuenta de Azure, tendrá que crear una para usar análisis de registros de OMS. Para obtener información sobre cómo crear una cuenta de Azure y configurar un área de trabajo de OMS, consulte [Introducción a un área de trabajo de análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versión 2,1 o posterior**

- Análisis de registros se requiere una **nueva búsqueda de registros** para la supervisión del conector en la nube. Para obtener más información, vea [actualizar el área de trabajo de análisis de registros de Azure a nueva búsqueda de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurar el conector de nube para usar OMS

Tendrá que configurar su entorno local de conector de nube para usar OMS. Para ello, necesitará su identificador de área de trabajo de OMS y clave, que puede encontrar mediante el portal de OMS de la siguiente manera:\>configuración: orígenes conectados\> --servidores de Windows:

![Captura de pantalla de Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La configuración del conector de nube para usar OMS depende de su escenario:

- **Si está instalando un nuevo dispositivo de conexión en la nube o desea volver a implementar un dispositivo**, siga estos pasos antes de ejecutar install-CcAppliance:

1. En la sección [Common] del archivo CloudConnector. ini, establezca el parámetro OMSEnabled en true.

    Cada vez que se implemente o actualice un conector de nube, intentará instalar el agente OMS automáticamente en las máquinas virtuales. Habilite esta característica para que el agente OMS pueda sobrevivir a la actualización automática de conector de nube.

2. Para configurar la clave y el identificador de OMS, ejecute Set-CcCredential-AccountType OMSWorkspace. 

- **Si va a instalar un agente OMS en un dispositivo de conector de nube existente**, siga estos pasos:

1. En la sección [Common] del archivo CloudConnector. ini, establezca OMSEnabled = true. 

2. Ejecute Import-CcConfiguration. 

3. Ejecute install-CcOMSAgent. 

    > [!NOTE]
    > Si la credencial OMSWorkspace nunca se ha establecido, se le solicitará la credencial cuando ejecute install-CcOMSAgent. 

- **Si desea actualizar el identificador de área de trabajo de OMS o clave en un dispositivo de conector de nube que ya tiene instalado un agente OMS:**

1. Para configurar la clave y el identificador de OMS, ejecute Set-CcCredential-AccountType OMSWorkspace. 

2. Para aplicar las actualizaciones, ejecute install-CcOMSAgent. 

- **Para todos los escenarios, verifique que los agentes estén conectados de la siguiente manera:**

    En el portal de OMS, vaya a configuración\> -orígenes conectados\> -servidores de Windows. Verá una lista de las máquinas conectadas. 

## <a name="configure-oms"></a>Configurar OMS

A continuación, tendrá que especificar la configuración de OMS mediante el portal de OMS. En concreto, necesitará lo siguiente:

- Especifique la información sobre los registros de eventos y los contadores de rendimiento.

- Crear alertas. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especificar información sobre los registros de eventos y los contadores de rendimiento

En el portal de OMS, debe especificar información sobre los registros de eventos y los contadores de rendimiento de la siguiente manera:

1. Vaya a configuración-\>datos-\>registros de eventos de Windows y agregue registros de eventos para: 

   - Lync Server

   - Aplicación

     > [!NOTE]
     > Debe introducir manualmente Lync Server en el cuadro de texto. No aparece como una opción en la lista desplegable. 

     Para obtener más información, consulte [orígenes de datos del registro de eventos de Windows en análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Vaya a configuración-\>datos-\> contadores de rendimiento de Windows y agregue contadores de rendimiento para: 

   - **Contadores de nivel del sistema operativo**. Puede Agregar contadores de nivel del sistema operativo, como el uso del procesador, el uso de la memoria, el uso de la red, o puede usar soluciones existentes como capacidad y rendimiento, monitor de rendimiento de red sin agregar contadores de forma explícita. Independientemente de cómo decida supervisarlos, Microsoft recomienda que supervise estos contadores del sistema operativo.

   - **Contadores de Skype empresarial**. Hay muchos contadores proporcionados por Skype empresarial. Puede encontrar estos contadores iniciando sesión en cualquier servidor de mediación y abriendo el monitor de rendimiento. Estos contadores comienzan con "LS:". Microsoft recomienda que comience con los siguientes contadores de capacidad como mínimo y agregue otros que tengan interés:

     Total de llamadas activas:

   - LS: MediationServer: llamadas entrantes (_ total\- ) actuales 

   - LS: MediationServer-llamadas salientes (_ total\- ) Current 

     Llamadas de omisión de medios activos totales:

   - LS: MediationServer-llamadas entrantes (_ total\- ) llamadas de omisión de medios activos 

   - LS: MediationServer-llamadas salientes (_ total\- ) llamadas de omisión de medios activos 

     > [!NOTE]
     > Debe introducir manualmente los contadores de rendimiento en el cuadro de texto. No aparecen como opciones en la lista desplegable. 

     Para obtener más información, vea [orígenes de datos de rendimiento de Windows y Linux en análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Crear alertas

Existen dos tipos de alertas en OMS: número de alertas de resultados y alertas de medición de métricas. Para obtener más información sobre cómo crear alertas, consulte [trabajar con reglas de alertas en análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Debe tener en cuenta lo siguiente al crear alertas:

- Asegúrese de que la alerta es una alerta de número de resultados, que es la selección predeterminada. 

- Las consultas de demostración requieren que "número de resultados" esté establecido en "mayor que 0". 

- Se recomienda configurar la frecuencia de la ventana tiempo y la alerta en 5 minutos. 

- Se recomienda no habilitar "suprimir alertas" para las alertas de demostración. 

- Para los escenarios de alerta típicos, Microsoft recomienda crear un par de alertas: una alerta de error y una alerta de restablecimiento. Para la alerta de error, seleccione nivel de gravedad crítico; para la alerta de restablecimiento, seleccione nivel de gravedad de la información.

En las siguientes secciones se describe cómo crear alertas de ejemplo.

 **Crear un par de alertas: "RTCMEDSRV no se está ejecutando en servidores de mediación" y "RTCMEDSRV está en ejecución en servidores de mediación"**

Para crear este par de alertas:

- La consulta para la alerta de error es la siguiente:

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La consulta usa el filtro de equipo *donde equipo contiene "MediationServer"* . El filtro selecciona solo el equipo cuyo nombre contiene la cadena "MediationServer".

     Debería reemplazar el filtro con su propio filtro informático o simplemente quitarlo. Puede crear filtros de cadena complejos sin expresiones regulares. Para obtener más información, consulte [operadores de cadena](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). También puede optar por usar expresiones regulares. Además, puede crear un grupo de equipos guardando una consulta de búsqueda y utilizando ese grupo como filtro de equipo en la consulta de alertas. Para obtener más información, consulte [grupos de equipos en las búsquedas del registro de análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Para cada equipo, la consulta de error recibirá el último registro de eventos para el inicio del servicio RTCMEDSRV y la detención de servicio. Devolverá un registro si el último evento es el evento de detención de servicio; no devolverá Nothing si el último evento es el evento de inicio de servicio. En Resumen, la consulta devolvería una lista de servidores cuya RTCMEDSRV está detenida en la ventana de tiempo. 

- La consulta para la alerta de restablecimiento es la siguiente:

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La consulta de restablecimiento hace exactamente lo opuesto de la consulta de error. Para cada equipo, devolverá uno si el último evento es el evento de inicio del servicio; no devolverá nada si el último evento es el evento de detención de servicio.

  **Crear un par de alertas: "demasiadas llamadas simultáneas en servidores de mediación" y "las llamadas simultáneas vuelven a carga normal"**

Para crear esta alerta:

- La consulta para la alerta de error es la siguiente:

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada equipo, la consulta recibirá los últimos contadores para las llamadas entrantes y salientes, y sumará esos dos valores. Devolverá un registro si el valor de suma supera 500; no volverá nada si lo hace. En Resumen, la consulta devolvería una lista de servidores cuyas llamadas simultáneas son demasiado numerosas en la ventana de tiempo.

- La consulta para la alerta de restablecimiento es la siguiente:

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La consulta de restablecimiento hace exactamente lo opuesto de la consulta de error. Para cada equipo, la consulta recibirá los últimos contadores para las llamadas entrantes y salientes, y sumará esos dos valores. Devolverá un registro si el valor de suma es menor que 500; de lo contrario, no devolverá nada.

  **Crear una alerta: alerta "uso \> de CPU 90 o RTCMEDIARELAY detenidas en los servidores"**

Para crear esta alerta, la consulta es la siguiente:

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La consulta obtendrá todo el contador de uso del procesador y el evento de detención de servicio de todos los equipos y devolverá un registro si alguno de los usos del procesador supera el 90% o el servicio se detiene. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analizar las alertas de su repositorio de análisis de registros

Para analizar las alertas de su repositorio, use la solución de administración de alertas. Para obtener más información, vea [solución de administración de alertas en Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) .

## <a name="recommended-minimal-monitoring-set"></a>Conjunto de supervisión mínimo recomendado

Para identificar problemas con los registros de eventos y los contadores de rendimiento: 

- **Registros de eventos.** Para cualquier problema, debería haber un par de eventos, con un conjunto de eventos para indicar que algo está mal, mientras que el otro indica que todo está bien. Durante un período de tiempo determinado, es el último evento registrado que indicará si hay algo incorrecto para ese período de tiempo.

- **Contadores de rendimiento.** Debe haber un umbral para los contadores supervisados.

En la tabla siguiente se enumeran los servicios que Microsoft recomienda supervisar al hacer una lista de los identificadores de sucesos detener y iniciar:

|Nombre del servicio  <br/> |Rol de servidor de destino  <br/> |Detener identificador de evento  <br/> |IDENTIFICADOR de evento de inicio  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de mediación  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor perimetral  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor perimetral  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor perimetral  <br/> |22003  <br/> |22002  <br/> |

En la tabla siguiente se enumeran los problemas de red que Microsoft recomienda supervisar:


| Nombre del monitor  <br/>                                        | Rol de servidor de destino  <br/> | Expresión de identificador de evento de éxito  <br/> | Expresión de identificador de evento de error  <br/> | Ejemplo de error  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Error de conectividad de servidor de mediación a puerta de enlace  <br/>    | Servidor de mediación  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Error de finalización de llamada de servidor de mediación a puerta de enlace  <br/> | Servidor de mediación  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemas de red críticos  <br/>                           | Servidor perimetral  <br/>        | 14353                              |                                  | 12288  <br/>           |

A continuación se enumeran los contadores de capacidad de llamadas que deberían supervisarse. Estos números deberían ser menos de 500 para el conector de nube Standard Edition; menos de 50 para la edición mínima de Cloud Connector.

- LS: MediationServer: llamadas entrantes (_ total\- ) actuales 

- LS: MediationServer-llamadas salientes (_ total\- ) Current 

- LS: MediationServer-llamadas entrantes (_ total\- ) llamadas de omisión de medios activos

- LS: MediationServer-llamadas salientes (_ total\- ) llamadas de omisión de medios activos

## <a name="see-also"></a>Vea también

Para obtener más información sobre cómo trabajar con OMS, consulte lo siguiente:

- [Buscar datos mediante búsquedas de registro en análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Referencia del lenguaje de análisis de registros de Azure](https://docs.loganalytics.io/docs/Language-Reference)

- [Descripción de las alertas de análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Conectar equipos de Windows con el servicio de análisis de registros en Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


