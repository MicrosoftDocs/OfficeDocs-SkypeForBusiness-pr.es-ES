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
ms.localizationpriority: medium
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lea este tema para obtener información sobre cómo supervisar la implementación de Cloud Connector versión 2.1 y posteriores mediante Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: c10eac34e065ab76cb570a21752838c308b6afd8
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676512"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Supervisar Cloud Connector con Operations Management Suite (OMS)

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que la organización se haya actualizado a Teams, aprenda a conectar la red de telefonía local a Teams mediante [enrutamiento directo](/MicrosoftTeams/direct-routing-landing-page).

Lea este tema para obtener información sobre cómo supervisar la implementación de Cloud Connector versión 2.1 y posteriores mediante Microsoft Operations Management Suite (OMS).

Ahora puede supervisar la implementación de Cloud Connector versión 2.1 y posteriores mediante Operations Management Suite (OMS), una solución de administración de TI en la nube de Microsoft. Log Analytics de OMS le permite supervisar y analizar la disponibilidad y el rendimiento de los recursos, incluidas las máquinas físicas y virtuales. Para obtener más información sobre OMS y Log Analytics, consulte [¿Qué es Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)

En este tema se presentan las siguientes secciones:

- Requisitos previos

- Configuración de Cloud Connector para usar OMS

- Configuración de OMS

- Análisis de las alertas en el repositorio de Log Analytics

- Conjunto de supervisión recomendado

## <a name="prerequisites"></a>Requisitos previos

Para poder usar OMS para supervisar la implementación de Cloud Connector, necesitará lo siguiente:

- **Una cuenta de Azure y un área de trabajo de OMS.** Si aún no tiene una cuenta de Azure, deberá crear una para usar Log Analytics de OMS. Para obtener información sobre cómo crear una cuenta de Azure y configurar un área de trabajo de OMS, consulte [Comenzar con un área de trabajo de Log Analytics](/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versión 2.1 o posterior**

- Se requiere **una nueva búsqueda de registros de Log Analytics** para la supervisión de Cloud Connector. Para obtener más información, consulte [Actualización del área de trabajo de Azure Log Analytics a una nueva búsqueda de registros](/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configuración de Cloud Connector para usar OMS

Tendrá que configurar el entorno local de Cloud Connector para usar OMS. Para ello, necesitará el identificador y la clave del área de trabajo de OMS, que puede encontrar mediante el portal de OMS como se indica a continuación: Configuración --\>Connected Sources--\> Windows Servers:

![Captura de pantalla para OMS de Cloud Connector.](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La configuración de Cloud Connector para usar OMS depende de su escenario:

- **Si va a instalar un nuevo dispositivo de Cloud Connector o quiere volver a implementar un dispositivo**, siga estos pasos antes de ejecutar Install-CcAppliance:

  1. En la sección CloudConnector.ini archivo [Común], establezca el parámetro OMSEnabled en True.

     Cada vez que Cloud Connector se implementa o actualiza, intentará instalar el agente de OMS automáticamente en las máquinas virtuales. Habilite esta característica para que el agente de OMS pueda sobrevivir a la actualización automática de Cloud Connector.

  2. Para configurar el identificador y la clave de OMS, ejecute Set-CcCredential -AccountType OMSWorkspace.

- **Si va a instalar un agente de OMS en un dispositivo de Cloud Connector existente**, siga estos pasos:

  1. En la sección archivo CloudConnector.ini [Común], establezca OMSEnabled=true.

  2. Ejecute Import-CcConfiguration.

  3. Ejecute Install-CcOMSAgent.

     > [!NOTE]
     > Si la credencial OMSWorkspace nunca se ha establecido, se le pedirá la credencial al ejecutar install-CcOMSAgent.

- **Si desea actualizar el identificador o la clave del área de trabajo de OMS en un dispositivo de Cloud Connector que ya haya instalado un agente de OMS:**

  1. Para configurar el identificador y la clave de OMS, ejecute Set-CcCredential -AccountType OMSWorkspace.

  2. Para aplicar las actualizaciones, ejecute Install-CcOMSAgent.

- **En todos los escenarios, compruebe que los agentes están conectados de la siguiente manera:**

    En el portal de OMS, vaya a Configuración -\> Orígenes conectados Windows\> Servidores. Verá una lista de máquinas conectadas.

## <a name="configure-oms"></a>Configuración de OMS

A continuación, deberá especificar la configuración de OMS mediante el portal de OMS. En concreto, deberá hacer lo siguiente:

- Especifique información sobre los registros de eventos y los contadores de rendimiento.

- Cree alertas.

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especificar información sobre los registros de eventos y los contadores de rendimiento

En el portal de OMS, debe especificar información sobre los registros de eventos y los contadores de rendimiento de la siguiente manera:

1. Vaya a Configuración-Data-Windows\>\> Registros de eventos y agregue registros de eventos para:

   - Lync Server

   - Aplicación

     > [!NOTE]
     > Debe escribir manualmente Lync Server en el cuadro de texto. No aparece como una opción en la lista desplegable.

     Para obtener más información, consulte [Windows orígenes de datos de registro de eventos en Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events).

2. Vaya a Configuración-Data\>-\> Windows Los contadores de rendimiento y agregue contadores de rendimiento para:

   - **Contadores de nivel de sistema operativo**. Puede agregar contadores de nivel de sistema operativo, como el uso del procesador, el uso de memoria, el uso de red, o bien puede usar soluciones existentes como capacidad y rendimiento, Monitor de rendimiento de red sin agregar contadores explícitamente. Independientemente de cómo decida supervisarlos, Microsoft recomienda supervisar estos contadores del sistema operativo.

   - **Skype Empresarial contadores**. Hay numerosos contadores proporcionados por Skype Empresarial. Para encontrar estos contadores, inicie sesión en cualquier servidor de mediación y abra el Monitor de rendimiento. Estos contadores comienzan por "LS:". Microsoft recomienda empezar con los siguientes contadores de capacidad como mínimo y agregar otros que sean de interés:

     Total de llamadas activas:

     - LS:MediationServer: llamadas entrantes (_Total)\- actual

     - LS:MediationServer: llamadas salientes (_Total)\- actual

     Total de llamadas de omisión de medios activos:

     - LS:MediationServer: llamadas entrantes (_Total)\- Llamadas de omisión de medios activos

     - LS:MediationServer: llamadas salientes (_Total)\- Llamadas de omisión de medios activos

     > [!NOTE]
     > Debe escribir manualmente los contadores de rendimiento en el cuadro de texto. No aparecen como opciones en la lista desplegable.

     Para obtener más información, consulte [orígenes de datos de rendimiento de Windows y Linux en Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters).

### <a name="create-alerts"></a>Creación de alertas

En OMS hay dos tipos de alertas: número de alertas de resultados y alertas de medición de métricas. Para obtener más información sobre cómo crear alertas, consulte [Trabajar con reglas de alertas en Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).

Debe tener en cuenta lo siguiente al crear alertas:

- Asegúrese de que la alerta es una alerta de número de resultados, que es la selección predeterminada.

- Las consultas de demostración requieren que "Número de resultados" se establezca en "Mayor que 0".

- Se recomienda establecer el período de tiempo y la frecuencia de alerta en 5 minutos.

- Se recomienda no habilitar "Suprimir alertas" para las alertas de demostración.

- Para escenarios de alerta típicos, Microsoft recomienda crear un par de alertas: una alerta de error y una alerta de restablecimiento. Para la alerta de error, seleccione Nivel de gravedad Crítico; para la alerta de restablecimiento, seleccione nivel de gravedad Informativo .

En las secciones siguientes se describe cómo crear alertas de ejemplo.

#### <a name="create-an-alert-pair-rtcmedsrv-is-not-running-in-mediation-servers-and-rtcmedsrv-is-back-in-running-in-mediation-servers"></a>Cree un par de alertas: "RTCMEDSRV no se ejecuta en servidores de mediación" y "RTCMEDSRV vuelve a ejecutarse en servidores de mediación"

Para crear este par de alertas:

- La consulta de la alerta de error es:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La consulta usa el filtro de equipo  *donde Equipo contiene "MediationServer"*  . El filtro selecciona solo el equipo cuyo nombre contiene la cadena "MediationServer".

     Reemplazaría el filtro por su propio filtro de equipo o simplemente lo quitaría. Puede crear filtros de cadena complejos sin expresiones regulares. También puede optar por usar expresiones regulares. Además, puede crear un grupo de equipos guardando una consulta de búsqueda y usando ese grupo como filtro de equipo en la consulta de alertas. Para obtener más información, consulte [Grupos de equipos en búsquedas de registros de Log Analytics](/azure/log-analytics/log-analytics-computer-groups).

    Para cada equipo, la consulta de errores obtendrá el último registro de eventos tanto para el inicio del servicio RTCMEDSRV como para la detención del servicio. Devolverá un registro si el último evento es el evento de detención de servicio; no devolverá nada si el último evento es el evento de inicio del servicio. En resumen, la consulta devolvería una lista de servidores cuyo RTCMEDSRV se detiene en el período de tiempo.

- La consulta de la alerta de restablecimiento es:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La consulta de restablecimiento hace exactamente lo contrario de la consulta de error. Para cada equipo, devolverá uno si el último evento es el evento de inicio del servicio; no devolverá nada si el último evento es el evento de detención del servicio.

#### <a name="create-an-alert-pair--too-many-concurrent-calls-in-mediation-servers-and-concurrent-calls-fall-back-to-normal-load"></a>Crear un par de alertas: "Demasiadas llamadas simultáneas en servidores de mediación" y "Llamadas simultáneas vuelven a la carga normal"

Para crear esta alerta:

- La consulta de la alerta de error es:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada equipo, la consulta obtendrá los últimos contadores de llamada entrante y llamada saliente y sumará esos dos valores. Devolverá un registro si el valor de suma supera los 500; no devolverá nada si no lo hace. En resumen, la consulta devolvería una lista de servidores cuyas llamadas simultáneas son demasiadas en el período de tiempo.

- La consulta de la alerta de restablecimiento es:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La consulta de restablecimiento hace exactamente lo contrario de la consulta de error. Para cada equipo, la consulta obtendrá los últimos contadores de llamada entrante y llamada saliente y sumará esos dos valores. Devolverá un registro si el valor de suma es menor que 500; no devolverá nada de lo contrario.

#### <a name="create-an-alert-cpu-usage--90-or-rtcmediarelay-stopped-in-servers-alert"></a>Crear una alerta: alerta "Uso de \> CPU 90 o RTCMEDIARELAY detenido en servidores"

Para crear esta alerta, la consulta es:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La consulta obtendrá todo el contador de uso del procesador y el evento de detención de servicio de todos los equipos y devolverá un registro si el uso del procesador supera el 90 % o si el servicio se detiene alguna vez.

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Análisis de las alertas en el repositorio de Log Analytics

Para analizar las alertas en el repositorio, use la solución Administración de alertas. Para obtener más información, consulte [Solución de administración de alertas en Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Conjunto de supervisión mínimo recomendado

Para identificar problemas con los registros de eventos y los contadores de rendimiento:

- **Registros de eventos.** Para cualquier problema, debe haber un par de eventos, con un conjunto de eventos para indicar que algo está mal, mientras que el otro indica que todo está bien. Para un período de tiempo determinado, es el último evento registrado el que indicará si algo es incorrecto para ese período de tiempo.

- **Contadores de rendimiento.** Debe haber un umbral para los contadores supervisados.

En la tabla siguiente se enumeran los servicios que Microsoft recomienda supervisar enumerando los identificadores de evento de detención e inicio:

|Nombre del servicio  <br/> |Rol de servidor de destino  <br/> |Detener identificador de evento  <br/> |Id. de evento de inicio  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de mediación  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor perimetral  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor perimetral  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor perimetral  <br/> |22003  <br/> |22002  <br/> |

En la tabla siguiente se enumeran los problemas de red que Microsoft recomienda supervisar:


| Nombre del monitor  <br/>                                        | Rol de servidor de destino  <br/> | Expresión de identificador de evento correcto  <br/> | Expresión de identificador de evento de error  <br/> | Ejemplo de error  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Error de conectividad del servidor de mediación a la puerta de enlace  <br/>    | Servidor de mediación  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Error de finalización de llamadas del servidor de mediación a la puerta de enlace  <br/> | Servidor de mediación  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemas críticos de red  <br/>                           | Servidor perimetral  <br/>        | 14353                              |                                  | 12288  <br/>           |

A continuación se enumeran los contadores de capacidad de llamada que se deben supervisar. Estos números deben ser menores que 500 para la edición estándar de Cloud Connector; menos de 50 para la edición mínima de Cloud Connector.

- LS:MediationServer: llamadas entrantes (_Total)\- actual

- LS:MediationServer: llamadas salientes (_Total)\- actual

- LS:MediationServer: llamadas entrantes (_Total)\- Llamadas de omisión de medios activos

- LS:MediationServer: llamadas salientes (_Total)\- Llamadas de omisión de medios activos

## <a name="see-also"></a>Vea también

Para obtener más información sobre cómo trabajar con OMS, consulte lo siguiente:

- [Búsqueda de datos mediante búsquedas de registros en Log Analytics](/azure/log-analytics/log-analytics-log-searches)

- [Descripción de las alertas en Log Analytics](/azure/log-analytics/log-analytics-alerts)

- [Conectar Windows equipos al servicio Log Analytics en Azure](/azure/log-analytics/log-analytics-windows-agents)