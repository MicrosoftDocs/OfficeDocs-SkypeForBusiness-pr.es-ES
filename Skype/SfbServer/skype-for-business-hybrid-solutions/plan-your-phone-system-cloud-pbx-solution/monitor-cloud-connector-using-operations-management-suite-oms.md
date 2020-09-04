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
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Supervisar Cloud Connector con Operations Management Suite (OMS)

> [!Important]
> Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Lea este tema para obtener información sobre cómo supervisar la implementación de la versión 2,1 y posteriores de Cloud Connector mediante Microsoft Operations Management Suite (OMS).

Ahora puede supervisar su implementación de Cloud Connector versión 2,1 y posterior mediante Operations Management Suite (OMS), una solución de administración de TI en la nube de Microsoft. El análisis de registros de OMS le permite supervisar y analizar la disponibilidad y el rendimiento de los recursos, incluidas las máquinas físicas y virtuales. Para obtener más información sobre OMS y el análisis de registros, vea [¿Qué es Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

En este tema se presentan las siguientes secciones:

- Requisitos previos

- Configurar Cloud Connector para usar OMS

- Configurar OMS

- Analizar las alertas de su repositorio de análisis de registros

- Conjunto de supervisión recomendado

## <a name="prerequisites"></a>Requisitos previos

Antes de poder usar OMS para supervisar la implementación de Cloud Connector, necesitará lo siguiente:

- **Una cuenta de Azure y un área de trabajo de OMS.** Si aún no tiene una cuenta de Azure, tendrá que crear una para usar el análisis de registros de OMS. Para obtener información sobre cómo crear una cuenta de Azure y configurar un área de trabajo de OMS, consulte Introducción [a un área de trabajo de análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versión 2,1 o posterior**

- Se requiere la **búsqueda de registros nueva de análisis de registros** para la supervisión de Cloud Connector. Para obtener más información, vea [actualizar el área de trabajo de análisis de registros de Azure a nueva búsqueda de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurar Cloud Connector para usar OMS

Deberá configurar su entorno local de Cloud Connector para usar OMS. Para ello, necesitará el identificador y la clave del área de trabajo de OMS, que puede encontrar mediante el portal de OMS, como se indica a continuación: configuración-- \> orígenes conectados-- \> servidores Windows:

![Captura de pantalla del OMS de Cloud Connector](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La configuración de Cloud Connector para que use OMS depende de su escenario:

- **Si va a instalar un nuevo dispositivo de Cloud Connector o desea volver a implementar un dispositivo**, siga estos pasos antes de ejecutar install-CcAppliance:

    1. En la sección CloudConnector.ini archivo [común], establezca el parámetro OMSEnabled en true.

        Cada vez que se implemente o actualice Cloud Connector, se intentará instalar el agente OMS automáticamente en las máquinas virtuales. Habilite esta característica para que el agente OMS pueda sobrevivir a la actualización automática de Cloud Connector.

    2. Para configurar el identificador y la clave de OMS, ejecute Set-CcCredential-AccountType OMSWorkspace. 

- **Si va a instalar un agente OMS en un dispositivo existente de Cloud Connector**, siga estos pasos:

    1. En la sección archivo de CloudConnector.ini [Common], establezca OMSEnabled = true. 

    2. Ejecute Import-CcConfiguration. 

    3. Ejecute install-CcOMSAgent. 

        > [!NOTE]
        > Si nunca se ha establecido la credencial OMSWorkspace, se le pedirán las credenciales al ejecutar install-CcOMSAgent. 

- **Si desea actualizar la clave o el identificador del área de trabajo de OMS en un dispositivo de Cloud Connector que ya tiene instalado un agente OMS:**

    1. Para configurar el identificador y la clave de OMS, ejecute Set-CcCredential-AccountType OMSWorkspace. 

    2. Para aplicar las actualizaciones, ejecute install-CcOMSAgent. 

- **Para todos los escenarios, compruebe que los agentes estén conectados de la siguiente manera:**

    En el portal de OMS, vaya a configuración- \> orígenes conectados- \> servidores Windows. Verá una lista de las máquinas conectadas. 

## <a name="configure-oms"></a>Configurar OMS

A continuación, tendrá que especificar la configuración de OMS mediante el portal de OMS. Concretamente, tendrá que:

- Especifique información sobre los registros de eventos y los contadores de rendimiento.

- Cree alertas. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especificar información sobre los registros de eventos y los contadores de rendimiento

En el portal de OMS, debe especificar información sobre los registros de eventos y los contadores de rendimiento de la siguiente manera:

1. Vaya a configuración- \> datos- \> registros de eventos de Windows y agregue registros de eventos para: 

   - Lync Server

   - Aplicación

     > [!NOTE]
     > Debe especificar manualmente Lync Server en el cuadro de texto. No aparece como una opción en la lista desplegable. 

     Para obtener más información, vea [orígenes de datos del registro de eventos de Windows en el análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events) .

2. Vaya a configuración- \> datos- \> contadores de rendimiento de Windows y agregue contadores de rendimiento para: 

   - **Contadores de nivel del sistema operativo**. Puede Agregar contadores a nivel del sistema operativo, como el uso del procesador, el uso de la memoria, el uso de la red o puede usar soluciones existentes como capacidad y rendimiento, monitor de rendimiento de red sin agregar contadores de forma explícita. Independientemente de cómo decida supervisarlas, Microsoft recomienda que supervise estos contadores del sistema operativo.

   - **Contadores de Skype empresarial**. Hay muchos contadores proporcionados por Skype empresarial. Puede encontrar estos contadores iniciando sesión en cualquier servidor de mediación y abriendo el monitor de rendimiento. Estos contadores comienzan con "LS:". Microsoft recomienda comenzar con los siguientes contadores de capacidad como mínimo y agregar otros que sean de interés:

     Total de llamadas activas:

       - LS: MediationServer-llamadas entrantes (_Total) \- actual 

       - LS: MediationServer-llamadas salientes (_Total) \- actual 

     Llamadas de omisión de medios activos totales:

       - LS: MediationServer-llamadas entrantes (_Total) \- llamadas de omisión de medios activos 

       - LS: MediationServer-llamadas salientes (_Total) \- llamadas de omisión de medios activos 

     > [!NOTE]
     > Debe especificar manualmente los contadores de rendimiento en el cuadro de texto. No aparecen como opciones en la lista desplegable. 

     Para obtener más información, vea [orígenes de datos de rendimiento de Windows y Linux en el análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters) .

### <a name="create-alerts"></a>Crear alertas

Hay dos tipos de alertas en OMS: número de alertas de resultados y alertas de medida métricas. Para obtener más información acerca de la creación de alertas, vea [trabajar con reglas de alerta en el análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Debe tener en cuenta lo siguiente al crear alertas:

- Asegúrese de que la alerta es una alerta de número de resultados, que es la selección predeterminada. 

- Las consultas de demostración requieren que "número de resultados" esté establecido en "mayor que 0". 

- Se recomienda que establezca la frecuencia de la ventana tiempo y de la alerta en 5 minutos. 

- Se recomienda no habilitar "suprimir alertas" para las alertas de demostración. 

- Para los escenarios de alerta típicos, Microsoft recomienda crear un par de alertas: un mensaje de error y una alerta de restablecimiento. Para la alerta de error, seleccione nivel de gravedad crítico; para la alerta de restablecimiento, seleccione información de nivel de gravedad.

En las secciones siguientes se describe cómo crear alertas de ejemplo.

 **Cree un par de alertas: "RTCMEDSRV no se está ejecutando en los servidores de mediación" y "RTCMEDSRV se ha vuelto a ejecutar en los servidores de mediación"**

Para crear este par de alertas:

- La consulta de la alerta de error es la siguiente:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La consulta usa el filtro del equipo  *en el que el equipo contiene "MediationServer"*  . El filtro selecciona solo el equipo cuyo nombre contiene la cadena "MediationServer".

     Debe reemplazar el filtro por su propio filtro de equipo o simplemente quitarlo. Puede crear filtros de cadena complejos sin expresiones regulares. Para obtener más información, consulte [operadores de cadena](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). También puede optar por usar expresiones regulares. Además, puede crear un grupo de equipos si guarda una consulta de búsqueda y usa ese grupo como filtro de equipo en la consulta de alertas. Para obtener más información, vea [grupos de equipos en el registro de registros del análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Para cada equipo, la consulta de error obtendrá el último registro de eventos para el inicio del servicio de RTCMEDSRV y para detener el servicio. Se devolverá un registro si el último evento es el evento de detención de servicio; no devolverá Nothing si el último evento es el evento de inicio del servicio. En Resumen, la consulta devolvería una lista de servidores cuya RTCMEDSRV se ha detenido en el período de tiempo. 

- La consulta para la alerta de restablecimiento es:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La consulta de restablecimiento hace exactamente lo opuesto a la consulta de error. Para cada equipo, se devolverá uno si el último evento es el evento de inicio del servicio; no devolverá Nothing si el último evento es el evento de detención de servicio.

**Crear un par de alertas: "demasiadas llamadas simultáneas en los servidores de mediación" y "las llamadas simultáneas se revierten a la carga normal"**

Para crear esta alerta:

- La consulta de la alerta de error es la siguiente:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada equipo, la consulta obtendrá los últimos contadores para las llamadas entrantes y salientes, y sumará esos dos valores. Devolverá un registro si el valor de suma supera 500; no devolverá nada si no lo es. En Resumen, la consulta devolvería una lista de servidores cuyas llamadas simultáneas son demasiado numerosas en el intervalo de tiempo.

- La consulta para la alerta de restablecimiento es:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La consulta de restablecimiento hace exactamente lo opuesto a la consulta de error. Para cada equipo, la consulta obtendrá los últimos contadores para las llamadas entrantes y salientes, y sumará esos dos valores. Devolverá un registro si el valor de sum es inferior a 500; de lo contrario, devolverá Nothing.

**Cree una alerta: el uso \> de CPU 90 o RTCMEDIARELAY se detuvo en la alerta de los servidores**

Para crear esta alerta, la consulta es:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La consulta recibirá todos los contadores de uso del procesador y el evento de detención del servicio de todos los equipos y devolverá un registro si cualquier uso del procesador supera el 90% o si el servicio se detiene alguna vez. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analizar las alertas de su repositorio de análisis de registros

Para analizar las alertas del repositorio, use la solución de administración de alertas. Para obtener más información, vea [Alert Management Solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) .

## <a name="recommended-minimal-monitoring-set"></a>Conjunto de supervisión mínimo recomendado

Para identificar problemas con los registros de eventos y los contadores de rendimiento: 

- **Registros de eventos.** Para cualquier problema, debe haber un par de eventos, con un conjunto de eventos para indicar que algo es incorrecto, mientras que el otro indica que todo está bien. Durante un período de tiempo determinado, es el último evento registrado que indicará si hay algo amiss para ese período de tiempo.

- **Contadores de rendimiento.** Debe haber un umbral para los contadores supervisados.

En la siguiente tabla se enumeran los servicios que Microsoft recomienda supervisar enumerando los identificadores de eventos de detención e Inicio:

|Nombre del servicio  <br/> |Rol de servidor de destino  <br/> |Detener identificador de evento  <br/> |IDENTIFICADOR de evento de inicio  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de mediación  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor perimetral  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor perimetral  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor perimetral  <br/> |22003  <br/> |22002  <br/> |

En la siguiente tabla se enumeran los problemas de red que Microsoft recomienda supervisar:


| Nombre de monitor  <br/>                                        | Rol de servidor de destino  <br/> | Expresión de identificador de evento correcto  <br/> | Expresión de identificador de evento de error  <br/> | Ejemplo de error  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Error de Conectividad del servidor de mediación a la puerta de enlace  <br/>    | Servidor de mediación  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Error de finalización de la llamada del servidor de mediación  <br/> | Servidor de mediación  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemas de red críticos  <br/>                           | Servidor perimetral  <br/>        | 14353                              |                                  | 12288  <br/>           |

A continuación se enumeran los contadores de capacidad de llamadas que deben supervisarse. Estos números deben ser inferiores a 500 para Cloud Connector Standard Edition; menor que 50 para la edición mínima de Cloud Connector.

- LS: MediationServer-llamadas entrantes (_Total) \- actual 

- LS: MediationServer-llamadas salientes (_Total) \- actual 

- LS: MediationServer-llamadas entrantes (_Total) \- llamadas de omisión de medios activos

- LS: MediationServer-llamadas salientes (_Total) \- llamadas de omisión de medios activos

## <a name="see-also"></a>Recursos adicionales

Para obtener más información sobre cómo trabajar con OMS, consulte lo siguiente:

- [Buscar datos mediante búsquedas de registros en el análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Referencia de lenguaje de análisis de registros de Azure](https://docs.loganalytics.io/docs/Language-Reference)

- [Descripción de las alertas en el análisis de registros](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Conectar equipos Windows al servicio log Analytics en Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


