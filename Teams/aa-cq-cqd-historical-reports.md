---
title: Informes de historial de operadores automáticos y colas de llamadas actualizados
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: Obtenga información sobre cómo usar el operador automático actualizado de Teams & informe de historial de la cola de llamadas de Power BI para ver los datos históricos del operador automático y de la cola de llamadas.
ms.openlocfilehash: 0ff8e7d1b5a1b9901c5b8a5da49d67fbf8ac5275
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812737"
---
# <a name="auto-attendant-and-call-queue-historical-reports"></a>Informes históricos del operador automático y de la cola de llamadas

>[!NOTE]
> Los clientes de HIgh y DOD de GCC deben seguir usando la versión V1.63 del [operador automático & los informes históricos de la cola de llamadas (CQD).](aa-cq-cqd-historical-reports-v163.md)

Esta plantilla de Power BI proporciona tres informes que permiten a las organizaciones informar sobre el número de llamadas que procesan los operadores automáticos y las colas de llamadas.  También proporciona información sobre el rendimiento de los agentes.

## <a name="v305-published-on-january-9-2023"></a>V3.0.5 publicado el 9 de enero de 2023

La plantilla de Power BI Informe histórico de la cola de llamadas del operador automático de Teams & proporciona los tres informes siguientes:

- El informe [Operador automático](media/aa-cq-historical-report-sample-aa-v305.png) muestra análisis de las llamadas que llegan a sus operadores automáticos.
- El informe [Cola de llamadas](media/aa-cq-historical-report-sample-cq-v305.png) muestra análisis de las llamadas que llegan a las colas de llamadas.
- El informe [Escala de tiempo del agente](media/aa-cq-historical-report-sample-at-v305.png) muestra una vista de escala de tiempo de los agentes que están activos en las llamadas de la cola de llamadas.

Estos informes usan datos del servicio recopilador de análisis de aplicaciones de voz (VAAC).

## <a name="v3xx-prerequisites"></a>Requisitos previos de V3.x.x

### <a name="power-bi-desktop"></a>Power BI Desktop

Debes tener Power BI Desktop instalado. Puedes instalar y usar la versión gratuita de [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

La versión mínima compatible es 2.85.681.0 (septiembre de 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Permisos para obtener acceso a la canalización del CQD

Aunque esta versión de los informes no usa la canalización de datos del Panel de calidad de llamadas (CQD), la cuenta usada para ver los datos históricos aún requiere acceso al panel de calidad de llamadas. Para obtener más información, vea [Rol de acceso del CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

Funcionará cualquier rol del CQD con los campos **Ver informes** y **Ver EUII** establecidos en **Sí** .

- Este requisito se quitará en una versión futura.

## <a name="v3xx-installation"></a>Instalación V3.x.x 

En los pasos siguientes se supone que ya ha instalado Power BI Desktop en el equipo y que su cuenta tiene los permisos necesarios para acceder a la canalización de datos del CQD.

Siga estos pasos:

1. Descargue y guarde el operador [automático de Teams & los informes históricos de la cola de llamadas V3.0.5.zip](https://www.microsoft.com/download/details.aspx?id=104623) archivo en su equipo.

2. Abra el archivo zip.

3. Abra el archivo de `Teams Auto Attendant & Call Queue Historical Reports V3.0.5.pbit` plantilla. Power BI Desktop debería iniciarse.

4. Se le pedirá que seleccione el **origen de datos**.  Seleccione la `api.interfaces.records.teams.microsoft.com` entrada.

  :::image type="content" source="media/aa-cq-historical-report-01-v305.png" alt-text="Captura de pantalla que selecciona el api.interfaces.records.teams.microsoft.com Soure de datos":::

5. Se te pedirá que inicies sesión con una cuenta. Seleccione **Cuenta de la organización** y, a continuación, seleccione **Iniciar sesión**.

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="Captura de pantalla que muestra el inicio de sesión para V3.0.0.":::

6. Selecciona **Conectar** y los datos se actualizarán.

> [!NOTE]
> Si estaba usando v1.63 o una versión anterior, puede encontrar un error cuando v3.x.x intenta recuperar los datos del VAAC.  Para resolver este error, es necesario borrar las credenciales anteriores de Power BI.
> 
> 1. Abra la plantilla v3.x.x para borrar el error. 
> 1. Seleccione Opciones **de archivo** > **& Configuración Configuración** > **del origen de datos**.
> 1. Seleccione la lista desplegable para **Borrar permisos** y, a continuación, seleccione **Borrar todos los permisos**.
> 1. Cierre la plantilla después de que se borren y reinicie Power BI. Se te pedirá que autorices de nuevo. 

## <a name="data-latency-for-auto-attendant-and-call-queue-analytics"></a>Latencia de datos para el análisis de la cola de llamadas y el operador automático

Los datos suelen estar disponibles en un plazo de 30 minutos desde la finalización de la llamada; sin embargo, hay ocasiones en las que puede tardar varias horas en aparecer los datos. 

Tendrá que actualizar los datos para ver los nuevos datos.

## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definiciones de informes históricos del operador automático y de la cola de llamadas

### <a name="cloud-auto-attendant-analytics-report"></a>Informe de análisis de Operador automático en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección informe                          |Descripción                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Origen de llamadas entrantes                    |Distribución de llamadas por origen de llamadas interno o externo            |
|Método de búsqueda en directorios                 |Distribución de llamadas por tipo de búsqueda                              |
|Recuento de acciones del autor de la llamada                     |Distribución de llamadas por número de acción usada durante la llamada       |
|Promedio de segundos en AA                   |Número medio de segundos que pasan los autores de llamadas en la AA                 |
|Acciones de llamada promedio                  |Número medio de acciones que realizan los autores de llamadas en la AA               |
|Resultados de llamadas                            |Distribución de llamadas por estado de llamada final                         |
|Sección inferior del informe                 |Desglose del flujo de llamadas                                               |

#### <a name="report-visual-and-field-mapping"></a>Informar de asignación visual y de campos

|Pestaña Informe            |Nombre de tabla de informe     |Filtro global                          |
|:---------------------|:---------------------|:--------------------------------------|
|Operador automático        |fAutoAttendant        |Ninguna                                   |

|Sección informe                               |Campo(s) Utilizados                                                                                    |Filtros aplicados |
|:--------------------------------------------|:------------------------------------------------------------------------------------------------|:----------|
|Selector de fecha                                |AAStartTime                                                                                      |Ninguna       |
|Selector intervalo de tiempo                          |AAStartHour                                                                                      |Ninguna       |
|Cuentas de recursos de operador automático             |Nombre AA                                                                                          |Ninguna       |
|Origen de llamadas entrantes                         |Tipo de llamada<br>Suma de TotalCallCount         |Llamadas externas: el tipo de llamada es externo<br>Llamadas internas: el tipo de llamada es interno |
|Método de búsqueda en directorios                      |AADirectorySearchMethod<br>AADirectorySearchMethodLegend<br>TotalCallCount  |AADirectorySearchMethod es abs_search_dtmf o abs_search_name    |
|Recuento de acciones del autor de la llamada                          |AACallerActionCount<br>TotalCallCount                                                            |Ninguna       |
|Promedio de segundos en AA                        |AAChainDuration                                                                                  |Ninguna       |
|Acciones de llamada promedio                       |AACallerActionCount                                                                              |Ninguna       |
|Resultados de llamadas                                 |AACallResult<br>AACallResultLegend<br>TotalCallCount                                             |Ninguna       |
|Sección inferior del informe                      |MM-DD<br>Nombre AA<br>AACallFlow<br>Tipo de llamada<br>AACallResult<br>TotalCallCount<br>AAChainDuration |Ninguna       |

#### <a name="fautoattendant-field-description"></a>Descripción del campo fAutoAttendant

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nombre AA                                 |Texto                     |Nombre de la cuenta de recursos adjunta al operador automático<br><br>Si se **aa_test@microsoft.com** el nombre completo de la cuenta de recursos, este valor será: **aa_test** |
|AA Hora de inicio UTC                       |Fecha y hora                |Hora de inicio de llamada del operador automático: UTC                                                     |
|AACallerActionCount                     |Número entero             |Resumir: Suma<br>Recuento de acciones seleccionadas por el autor de la llamada en operador automático durante la llamada  |
|AACallerActionCount (medida)           |Número entero             |Igual que AACallerActionCount excepto será 0 si no hay llamadas en lugar de en blanco                |
|AACallFlow                              |Texto                     |Consulte Dimensiones del operador automático -> AutoAttendantCallFlow                                   |
|AACallResult                            |Texto                     |Vea dimensiones del operador automático -> AutoAttendantCallResult                                 |
|AACallResultLegend                      |Texto                     |Configura elementos de leyenda basados en AACallResult                                               |
|AAChainDuration                         |Número decimal           |Resumir: Suma<br>Duración de la llamada en el operador automático                                     |
|AAChainDuration (medida)               |Número decimal           |Igual que AAChainDuration excepto será 0 si no hay llamadas en lugar de en blanco                    |
|AAChainIndex                            |Número entero             |                                                                                         |
|AAConnectivityType                      |Texto                     |Vea Dimensiones comunes > PSTNConnectivityType                                            |
|AACount                                 |Número entero             |Número de operadores automáticos implicados en la llamada                                               |
|AADirectorySearchMethod                 |Texto                     |Ver dimensiones del operador automático -> AutoAttendantDirectorySearchMethod                      |
|AADirectorySearchMethodLegend           |Texto                     |Configura elementos de leyenda basados en AADirectorySearchMethod                                    |
|AAStartHour                             |Número entero             |Hora de inicio de llamada de Operador automático                                                           |
|AAStartTime                             |Fecha y hora                |Hora de inicio de llamada de Operador automático                                                           |
|AATransferAction                        |Texto                     |Vea Dimensiones del operador automático > AutoAttendantTransferAction                             |
|Segundos de duración de la llamada                   |Número entero             |Duración de la llamada                                                                            |
|Hora de finalización de la llamada local                     |Fecha y hora                |Hora de finalización de la llamada: local (según la zona horaria del equipo que ejecuta el informe)                    |
|Hora de finalización de la llamada UTC                       |Fecha y hora                |Hora de finalización de la llamada: UTC                                                                      |
|Llamar a la hora de inicio local                   |Fecha y hora                |Hora de inicio de la llamada: local (según la zona horaria del equipo que ejecuta el informe)                  |
|Llamar a la hora de inicio UTC                     |Fecha y hora                |Hora de inicio de la llamada: UTC                                                                    |
|Tipo<sup>de llamada 1</sup>                   |Texto                     |Vea Dimensiones comunes > PSTNCallType                                                    |
|Id. de conferencia                            |Texto                     |Se usa con fines de solución de problemas: proporciona esta información al abrir un ticket       |
|Id. del cuadro de diálogo                                |Texto                     |Se usa con fines de solución de problemas: proporciona esta información al abrir un ticket       |
|Id. de documento                              |Texto                     |Se usa con fines de solución de problemas: proporciona esta información al abrir un ticket       |
|MM-DD                                   |Texto                     |Llamada del mes del operador automático                                                            |
|PSTNMinutes                             |Número entero             |Resumir: Suma<br>Uso total de minutos                                                     |
|Suma de TotalCallCount (medida)         |Número entero             |Igual que TotalCallCount excepto será 0 si no hay llamadas en lugar de en blanco                     |
|TotalCallCount                          |Número entero             |Resumir: Suma<br>Siempre 1: se usa para proporcionar la suma de todas las llamadas                            |


### <a name="cloud-call-queue-analytics-report"></a>Informe de análisis de cola de llamadas en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección informe                          |Descripción                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Origen de llamadas entrantes                    |Distribución de llamadas por origen de llamadas interno o externo             |
|Tiempo medio de espera (segundos)             |Esperar tiempo para las llamadas contestadas y abandonadas                         |
|Volumen de llamadas y recuento de agentes aceptados      |Distribución de llamadas por colas de llamadas / Número máximo de opt-ins del agente  |
|Resultados de llamadas                            |Distribución de llamadas por resultado de llamada                               |
|Llamadas abandonadas                         |Distribución de llamadas abandonadas por colas de llamadas                     |
|Duración media de la sesión (segundos)        |Duración de la llamada en segundos agrupada por resultado de llamada                      |
|Destinos de desbordamiento o tiempo de espera de llamadas      |Distribución de llamadas con tiempo de salida o desbordados                 |


#### <a name="report-visual-and-field-mapping"></a>Informar de asignación visual y de campos

|Pestaña Informe            |Nombre de tabla de informe                                   |Filtro global       |
|:---------------------|:---------------------------------------------------|:-------------------|
|Cola de llamadas            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |Ninguna                |

|Sección informe                      |Tabla -> Campo(s) Usados                |Filtros aplicados       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Selector de fecha                       |fCallQueueAnalytics -> Date           |Ninguna                  |
|Selector intervalo de tiempo                 |fCallQueueAnalytics -> CQHour         |Ninguna                  |
|Cuenta de recursos de cola de llamadas         |fCallQueueAnalytics -> nombre del CQ        |Ninguna                  |
|Origen de llamadas entrantes                |fCallQueueAnalytics -> Suma del recuento de llamadas (medida)  |Llamadas externas: el tipo de llamada es externo<br>Llamadas internas: el tipo de llamada es interno |
|Avg Wait Time (seconds)-Before Answered |fCallQueueFinalStateAction -> Avg of Average CQ Duration (Measure) |El resultado de llamadas en cola de llamadas es agent_joined_conference o transferred_to_agent|
|Avg Wait Time (seconds)-Before Abandoned |fCallQueueFinalStateAction -> Avg of Average Call Duration (Measure) |El resultado de llamadas en cola de llamadas no es agent_joined_conference, transferred_to_agent, desbordamiento timed_out |
|Recuento de Opt-In de agente y volumen de llamadas   |fCallQueueAnalytics -> Recuento de llamadas<br>fCallQueueAnalytics -> agente de cola de llamadas Opt In Count<br>fCallQueueAnalytics -> nombre del CQ<br>fCallQueueAnalytics -> Date |Ninguna |
|Llamadas abandonadas                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | La leyenda de resultados de llamadas de la cola de llamadas está abandonada |
|Duración media de la sesión (segundos)    |fCallQueueFinalStateAction -> duración media de la cola de llamadas (seg.)<br>Leyenda de resultados de llamadas de la cola de llamadas |Duración media de la cola de llamadas (seg.) > 0 |
|Destinos de desbordamiento o tiempo de espera de llamadas  |fCallQueueAnalytics -> Recuento de llamadas<br>fCallQueueAnalytics -> tipo de destino de la cola de llamadas<br>Leyenda de tipo de destino fCallQueue |La leyenda de tipo de destino de la cola de llamadas no contiene abandonado y el agente contestado |


#### <a name="fcallqueueanalytics-field-description"></a>Descripción del campo fCallQueueAnalytics

|Nombre                                    |Tipo de datos                |Descripción                                                                              |
|:---------------------------------------|:------------------------|:----------------------------------------------------------------------------------------|
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas                                                        |
|Segundos de duración de la llamada                   |Número entero             |Duración de la llamada                                                                            |
|Hora de finalización de la llamada local                     |Fecha y hora                |Hora de finalización de la llamada: local (según la zona horaria del equipo que ejecuta el informe)                    |
|Hora de finalización de la llamada UTC                       |Fecha y hora                |Hora de finalización de la llamada: UTC                                                                      |
|Recuento del agente de cola de llamadas                  |Número entero             |Resumir: Suma<br>Número de agentes configurados en la cola de llamadas                          |
|Cuenta de la opción Agente de cola de llamadas           |Número entero             |Resumir: Suma<br>Número de agentes que han optado por participar en la cola de llamadas                            |
|Resultado de llamadas en cola de llamadas                  |Texto                     |Consulte Dimensiones de la cola de llamadas -> CallQueueCallResult                                         |
|Leyenda de resultados de llamadas de la cola de llamadas           |Texto                     |Configura elementos de leyenda según el resultado de la cola de llamadas                                          |
|Tipo de destino de la cola de llamadas                  |Texto                     |Vea Dimensiones de la cola de llamadas -> CallQueueTargetType                                         |
|Leyenda de tipo de destino de la cola de llamadas           |Texto                     |Configura elementos de leyenda según el tipo de destino de la cola de llamadas                                     |
|Llamar a la hora de inicio local                   |Fecha y hora                |Hora de inicio de la llamada: local (según la zona horaria del equipo que ejecuta el informe)                  |
|Llamar a la hora de inicio UTC                     |Fecha y hora                |Hora de inicio de la llamada: UTC                                                                    |
|Tipo de llamada                               |Texto                     |Vea Dimensiones comunes > PSTNCallType                                                    |
|Id. de conferencia                            |Texto                     |Se usa con fines de solución de problemas: proporciona esta información al abrir un ticket       |
|Nombre del CQ                                 |Texto                     |Nombre de la cuenta de recursos adjunta a la cola de llamadas<br><br>Si se **cq_test@microsoft.com** el nombre completo de la cuenta de recursos, el valor será: **cq_test** |
|Hora del CQ                                 |Número entero             |Hora de inicio de llamada de la cola de llamadas                                                               |
|Fecha                                    |Fecha y hora                |Fecha y hora de inicio de la llamada en cola de llamadas (hora)                                               | 
|DateTimeCQName                          |Texto                     |Clave única para filtrar en fCallQueueFinalStateAction                                   |
|Id. del cuadro de diálogo                                |Texto                     |Se usa con fines de solución de problemas: proporciona esta información al abrir un ticket       |
|Id. de documento                              |Texto                     |Se usa con fines de solución de problemas: proporciona esta información al abrir un ticket       |
|Tipo de conectividad RTC                  |Texto                     |Vea Dimensiones comunes > PSTNConnectivityType                                            |
|Minutos totales de RTC                      |Número entero             |Resumir: Suma<br>Uso total de minutos para llamadas RTC                                     |
|Suma del recuento de llamadas (medida)             |Número entero             |Igual que el recuento de llamadas, sin embargo, será 0 cuando no se llame                                        |
|TotalCallCount (medida)                |Número entero             |Resumir: Suma<br>Recuento de llamadas                                                             |


#### <a name="fcallqueuefinalstateaction-field-description"></a>Descripción del campo fCallQueueFinalStateAction

|Nombre                                    |Tipo de datos                |Descripción                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Duración media de la llamada (segundos)         |Número decimal           |Resumir: Suma<br>Duración media de llamadas en segundos para llamadas abandonadas     |
|Duración media de la cola de llamadas (s)       |Número decimal           |Resumir: Suma<br>Promedio de tiempo de espera en segundos para las llamadas contestadas       |
|Avg of Average Call Duration (Measure)  |Número entero             |Igual que la duración media de llamadas (segundos), sin embargo, será 0 cuando no haya llamadas    |
|Avg of Average CQ Duration (Measure)    |Número entero             |Igual que la duración media de la cola de llamadas (s), sin embargo, será 0 cuando no haya llamadas  |
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas                                          |
|Resultado de llamadas en cola de llamadas                  |Texto                     |Consulte Dimensiones de la cola de llamadas -> CallQueueCallResult                           |
|Leyenda de resultados de llamadas de la cola de llamadas           |Texto                     |Configura elementos de leyenda según el resultado de llamadas en cola de llamadas                       |
|Acción de estado final de la cola de llamadas           |Texto                     |Vea Dimensiones de la cola de llamadas -> CallQueueFinaleStateAction                    |
|Nombre del CQ                                 |Texto                     |Nombre de la cuenta de recursos adjunta a la cola de llamadas<br><br>Si se **cq_test@microsoft.com** el nombre completo de la cuenta de recursos, el valor será: **cq_test** |
|Hora del CQ                                 |Número                   |Hora en la que tuvo lugar la llamada en
|Fecha                                    |Fecha y hora                |Fecha y hora de inicio de llamadas de la cola de llamadas (hora)                                 |
|DateTimeCQName                          |Texto                     |Clave única para filtrar en fCallQueueFinalStateAction                     |
|IsAbandoned                             |Verdadero/falso               |Verdadero si un agente no responde a la llamada                                    |


### <a name="cloud-call-queue-agent-timeline-report"></a>Informe escala de tiempo del agente de cola de llamadas en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección informe                                          |Descripción                                                         |
|:-------------------------------------------------------|:-------------------------------------------------------------------|
|Número de llamadas por agente                                |Distribución de llamadas por cola de llamadas y agente                       |
|Distribución por agente y toda la cola                     |Distribución de llamadas por agente y cola de llamadas                       |
|Tabla (parte inferior izquierda)                                     |Distribución de llamadas por agente con duración media y total de llamadas |
|Duración media de llamadas (segundos) por agente (esquina inferior derecha) |Duración media (segundos) de llamada por agente                         |

#### <a name="report-visual-field-mapping"></a>Informar de asignación de campo visual

|Pestaña Informe            |Nombre de tabla de informe           |Filtro global       |
|:---------------------|:---------------------------|:-------------------|
|Escala de tiempo del agente        |fAgentTimelineAnalytics     |Ninguna                |


|Sección informe                                |Campo(s) Utilizados                         |Filtros aplicados       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Selector de fecha                                 |Datetime                              |Ninguna                  |
|Selector de nombre de usuario de agente                       |Nombre del agente                            |Ninguna                  |
|Selector de cuentas de recursos de cola de llamadas         |Nombre del CQ                               |Ninguna                  |
|Número de llamadas por agente                      |Recuento de llamadas<br>Nombre del agente<br>Fecha<br>Hour      |Ninguna                  |
|Distribución por agente y cola de llamadas          |Nombre del agente<br>Duración media de llamadas (segundos)<br>Recuento de llamadas<br>Nombre del CQ |Ninguna                      |
|Inferior izquierda                                   |Nombre del agente<br>Duración media de la llamada (segundos)<br>Recuento de llamadas<br>Duración de la llamada (minuto)<br>Nombre del CQ<br>Hour<br>MM-DD | Ninguna |
|Duración media de llamadas (segundos) por agente      |Nombre del agente<br>Duración media de la llamada (segundos) | Ninguna |

#### <a name="fagenttimelineanalytics-field-description"></a>Descripción del campo fAgentTimelineAnalytics

|Nombre                                    |Tipo de datos                |Descripción                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nombre del agente                              |Texto                     |UPN de usuario<br>Si se **user@microsoft.com** el nombre de usuario completo, este valor será: **usuario** |
|Duración media de la llamada (segundos)         |Número decimal           |Resumir: Suma<br>Duración media de las llamadas en cola de llamadas respondidas en segundos |
|Duración de la llamada (minutos)                 |Número entero             |Resumir: Suma<br>Duración total de las llamadas de la cola de llamadas respondidas en minutos (redondeado hacia abajo a los minutos más cercanos)  |
|Llamadas respondidas                          |Número entero             |Número de llamadas contestadas por el agente                        |
|Llamadas no contestadas                      |Número entero             |Número de llamadas no contestadas por el agente                    |
|Nombre del CQ                                 |Texto                     |Nombre de la cuenta de recursos adjunta a la cola de llamadas<br><br>Si se **cq_test@microsoft.com** el nombre completo de la cuenta de recursos, el valor será: **cq_test** |
|Fecha                                    |Fecha                     |Fecha de llamada                                             |
|Datetime                                |Datetime                 |Fecha de llamada                                             |
|Hour                                    |Número entero             |Hora de llamada                                             |
|MM-DD                                   |Texto                     |Mes y día de llamada                                    |
|Total Call Count                        |Número entero             |Resumir: Suma<br>Número de llamadas que se presentan al agente     |

> [!NOTE]
> Cuando una llamada llega a la primera cola de llamadas, si el número de llamadas que ya están en esa cola ha alcanzado el límite de **administración de desbordamiento** de llamadas y si la opción de redirección envía nuevas llamadas a una segunda cola de llamadas, se mostrará que los agentes de la segunda cola de llamadas están en la primera cola de llamadas de este informe. 

## <a name="known-issues"></a>Problemas conocidos

- El objeto visual **Resultados de llamadas** del informe **Cola de llamadas** puede informar de un gran número de llamadas **_desconocidas_** . Esto se debe a un problema de clasificación de llamadas que el soporte técnico está trabajando para corregir.  Este es un problema de clasificación de llamadas solamente, y estas llamadas fueron procesadas correctamente por el sistema.

- Solo se notifican las acciones de llamadas y llamadas del primer operador automático o de la cola de llamadas que responde a la llamada.  Las llamadas y acciones de llamada en operadores automáticos encadenados (cuando un operador automático se transfiere a otro operador automático) o colas de llamadas encadenados (cuando una cola de llamadas se transfiere a otra cola de llamadas) no se notifican. 

- Las colas de llamadas y los operadores automáticos se muestran con el id. de la cuenta de recursos en lugar de con los nombres de la cola de llamadas o de los operadores automáticos.  Para mostrar todo el tráfico de un operador automático o de una cola de llamadas, debe seleccionar todas las cuentas de recursos asignadas al operador automático o a la cola de llamadas.

- Solo hay 28 días de historial disponibles en el panel, ya que los datos de la cola de llamadas y del operador automático se consideran datos personales y están sujetos a las directivas de retención de privacidad de datos.

- En algunos casos, el agente respondió el recuento de llamadas en el informe escala de tiempo del agente de cola de **llamadas** en la nube puede ser diferente al número de llamadas que se muestra en el historial de llamadas del cliente de Teams. El historial de llamadas del cliente de Teams es correcto. El soporte técnico se está investigando, pero no hay tiempo estimado para reparar disponible en este momento.

## <a name="customization"></a>Personalización 

Puede personalizar ciertos aspectos de visualización de los informes, como agregar o quitar campos para que se muestren en las distintas visualizaciones, cambiar el tipo de gráfico y mucho más.

### <a name="change-color-schema"></a>Cambiar esquema de color 

En los pasos siguientes se supone que ya ha completado los pasos de instalación.

Siga estos pasos:

1. Seleccione **la pestaña Vista** en la cinta de opciones.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="Captura de pantalla que selecciona la pestaña vista para cambiar la combinación de colores.":::

2. Seleccione el esquema de color de la lista desplegable.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="Captura de pantalla que muestra varias combinaciones de colores.":::
  
## <a name="dimensions-and-measurements"></a>Dimensiones y medidas

Las siguientes dimensiones y medidas están disponibles para su uso.

### <a name="common-dimensions"></a>Dimensiones comunes

Estas dimensiones son comunes tanto a los operadores automáticos como a las colas de llamadas:

|Nombre (tipo)                                            |Valores posibles                |Descripción                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|Id. de conferencia<br>(Texto)                                 |Identificador único global                           |Identificador de llamada                                                   |
|Fecha<br>(DateTime)                                     |                               |Fecha de llamada (UTC)                                                |
|DialogId<br>(Texto)                                     |Identificador único global                           |Identificador de llamada                                                   |
|Id. de documento<br>(Texto)                                   |Identificador único global                           |Identificador de llamada                                                   |
|Duración<br>(Número entero)                             |                               |Duración de la llamada, en segundos                                      |
|EndTime<br>(DateTime)                                  |                               |Hora de llamada finalizada (UTC)                                             |
|FirstIsCaller<br>(Booleano)                             |                               |[Clasificación del primer y segundo punto de conexión](dimensions-and-measures-available-in-call-quality-dashboard.md)     |
|FirstUPN<br>(Texto)                                     |                               |El nombre principal de usuario (UPN) del usuario del primer punto de conexión        |
|Hour<br>(Texto)                                         |                               |Hora de llamada iniciada (UTC)                                           |
|Minute<br>(Texto)                                       |                               |Llamada de minutos iniciada (UTC)                                         |
|PSTNCallDuration<br>(Número entero)                     |                               |Duración de la llamada                                              |
|PSTNCallType<br>(Texto)                                 |                               |                                                                  |
|                                                       |Externo                       |La llamada proviene de fuera del inquilino                            |
|                                                       |Interno                       |La llamada proviene del espacio empresarial                             |
|PSTNConnectivityType<sup>1</sup><br>(Texto)             |                               |                                                                  |
|                                                       |CallingPlan                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|Segundo<br>(Texto)                                       |                               |Segunda llamada iniciada (UTC)                                         |
|SecondUPN<br>(Texto)                                    |                               |El nombre principal de usuario (UPN) del usuario del segundo punto de conexión       |
|Id. de inquilino<br>(Texto)                                     |                               |ID. del espacio empresarial                                                         |
|Timestamp<br>(DateTime)                                |                               |El registro de hora se escribió (UTC)                                     |
|UserStartTimeUTC<br>(DateTime)                         |                               |Hora de llamada iniciada (UTC)                                           |

- <sup>1</sup> **PSTNConnectivityType** mostrará el origen del tramo de llamada final en lugar del origen del tramo de llamada inicial. Por ejemplo, si un operador automático recibe una llamada externa y transfiere la llamada a otro operador automático o a la cola de llamadas, el **origen de llamadas entrantes** se notificará como **Interno**.


### <a name="auto-attendant-dimensions"></a>Dimensiones del operador automático

|Nombre (tipo)                                            |Valores posibles                |Descripción                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AutoAttendantCallFlow<br>(Texto)                        |                               |Encapsula los diferentes estados de la llamada del operador automático          |
|                                                       |abs_search                     |                                                                  |
|                                                       |Anuncio                   |                                                                  |
|                                                       |automatic_menu                 |                                                                  |
|                                                       |call_termination               |                                                                  |
|                                                       |call_transfer                  |                                                                  |
|                                                       |first_level_menu               |                                                                  |
|                                                       |main_menu                      |                                                                  |
|                                                       |speech_input_confirmation      |                                                                  |
|                                                       |user_selection                 |                                                                  |
|AutoAttendantCallResult<br>(Texto)                      |                               |Resultado final de la llamada                                                 |
|                                                       |failed_to_establish_media      |No se pudo establecer la parte multimedia de la llamada             |
|                                                       |failover_to_operator           |Llamada transferida a operador normalmente debido a un error del sistema      |
|                                                       |oaa_chain_too_long             |Demasiadas piernas en la AA                                           |
|                                                       |oaa_session_too_long           |La sesión de AA ha durado demasiado tiempo                                    |
|                                                       |service_declined               |AA no aceptó la llamada                                         |
|                                                       |service_terminated             |La configuración de AA desconecta la llamada o la llamada colgada             |
|                                                       |terminated_automatic_selection |La configuración de AA desconecta las llamadas                           |
|                                                       |terminated_no_operator         |Todo terminado debido a un error no definido por un operador                   |
|                                                       |terminated_transfer_failed     |La llamada finalizó por error en la transferencia: normalmente a un número externo |
|                                                       |transfer_in_progress           |Transferencia AA->AA                                                   |
|                                                       |transferred_to_operator        |La llamada se ha transferido al operador                                  |
|                                                       |transferred_to_cq              |La llamada se ha transferido a la cola de llamadas                                |
|                                                       |transferred_to_receptionist    |Igual que transferred_to_operator                                   |
|                                                       |transferred_to_self            |La llamada se devolvió al inicio de la AA                          |
|                                                       |transferred_to_shared_voicemail |La llamada se ha transferido al correo de voz compartido                         |
|                                                       |transferred_to_user            |La llamada se ha transferido a un usuario                                    |
|                                                       |Desconocido                        |Se ha producido una condición desconocida                                 |
|                                                       |user_terminated                |El autor de la llamada colgó                                                    |
|AutoAttendantCallerActionCounts<br>(Número entero)      |                               |                                                                  |
|AutoAttendantChainDurationInSecs<br>(Número real)      |                               |                                                                  |
|AutoAttendantChainIndex<br>(Número entero)              |                               |                                                                  |
|AutoAttendantChainStartTime<br>(DateTime)              |                               |                                                                  |
|AutoAttendantCount<br>(Número entero)                   |                               |                                                                  |
|AutoAttendantDirectorySearchMethod<br>(Texto)           |                               |Método de búsqueda en directorios                                           |
|                                                       |abs_search_dtmf                |Tono táctil                                                        |
|                                                       |abs_search_voice               |Voz                                                             |
|AutoAttendantIdentity<br>(Texto)                        |                               |La llamada URI de la cuenta de recursos llegó al                              |
|AutoAttendantTransferAction<br>(Texto)                  |                               |Tipo de destino de transferencia de llamada                                         |
|                                                       |AA                             |Transferido a una AA                                              |
|                                                       |CQ                             |Transferido a un CQ                                               |
|                                                       |external_pstn                  |Transferido a un número externo                                 |
|                                                       |correo de voz compartido               |Transferido al correo de voz compartido                                   |
|                                                       |Desconocido                        |Acción desconocida                                                    |
|HasAA<br>(Booleano)                                     |                               |¿AA participa en la llamada?                                            |


### <a name="call-queue-dimensions"></a>Dimensiones de la cola de llamadas

|Nombre (tipo)                                            |Valores posibles                |Descripción                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|CallQueueAgentCount<br>(Número entero)                  |                               |Número de agentes en la cola de llamadas                                    |
|CallQueueAgentOptInCount<br>(Número entero)             |                               |Número de agentes que han optado por participar en la cola de llamadas                           |
|CallQueueCallResult<br>(Texto)                          |                               |Estado final de llamada de la cola de llamadas                                       |
|                                                       |agent_joined_conference        |Respuesta a la llamada: CQ del modo de conferencia                                |
|                                                       |Disminuido                       |                                                                  |
|                                                       |Desconectado                   |                                                                  |
|                                                       |error                          |                                                                  |
|                                                       |Fallado                         |                                                                  |
|                                                       |No válido                        |                                                                  |
|                                                       |desbordamiento                      |Condición de desbordamiento cumplida                                            |
|                                                       |timed_out                      |Condición de tiempo de espera cumplida                                             |
|                                                       |transferred_to_agent           |Respuesta a la llamada: CQ del modo de transferencia                                  |
|CallQueueDurationSeconds<br>(Número real)              |                               |Duración de llamadas en la cola de llamadas                                   |
|CallQueueFinaleStateAction<br>(Texto)                   |                               |Acción final de la cola de llamadas                                           |
|                                                       |Desconecte                     |time_out llamadas                                                    |
|                                                       |disconnect_with_busy           |llamadas desbordadas                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |Adelante                        |La llamada se desvió a un usuario o externamente                        |
|                                                       |shared_voicemail               |La llamada se envió al correo de voz compartido                                 |
|                                                       |Otro                          |                                                                  |
|                                                       |Mensaje de voz                      |                                                                  |
|CallQueueIdentity<br>(Texto)                            |                               |La llamada URI de la cuenta de recursos llegó al                              |
|CallQueueTargetType<br>(Texto)                          |                               |Destino de redireccionamiento de llamadas                                           |
|                                                       |ApplicationEndpoint            |                                                                  |
|                                                       |Buzón de correo                        |                                                                  |
|                                                       |Otros                          |                                                                  |
|                                                       |Teléfono                          |                                                                  |
|                                                       |Usuario                           |                                                                  |
|HasCQ<br>(Booleano)                                     |                               |¿El CQ participa en la llamada?                                            |
|TransferedFromCallQueueIdentity<br>(Texto)             |                               |                                                                  |

### <a name="measurements"></a>Medidas

|Nombre (tipo)                                            |Valores posibles                |Descripción                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AvgAutoAttendantChainDurationSeconds<br>(Número real)  |                               |                                                                  |
|AvgCallDuration<br>(Número real)                       |                               |                                                                  |
|AvgCallQueueDurationSeconds<br>(Número real)           |                               |                                                                  |
|PSTNTotalMinutes<br>(Número real)                      |                               |                                                                  |
|TotalAudioStreamDuration<br>(Número real)              |                               |                                                                  |
|TotalCallCount<br>(Número entero)                       |                               |                                                                  |

### <a name="constructing-a-valid-query"></a>Crear una consulta válida

Una consulta válida consta de varios atributos en un objeto JSON:

```json
{
   "Filters":[
      {
         "DataModelName":"Date",
         "Value":"2022-04-01",
         "Operand":4
      },
      {
         "DataModelName":"Date",
         "Value":"2022-04-30",
         "Operand":6
      }
   ],
   "Dimensions":[
      {
         "DataModelName":"AutoAttendantIdentity"
      },
      {
         "DataModelName":"AutoAttendantDirectorySearchMethod"
      }
   ],
   "Measurements":[
      {
         "DataModelName":"PSTNTotalMinutes"
      },
      {
         "DataModelName":"TotalCallCount"
      }
   ],
   "Parameters":{
      "UserAgent":"Power BI Desktop"
   },
   "LimitResultRowsCount":100000
}
```

#### <a name="required-fields"></a>Campos obligatorios

- Filtros: se usa para filtrar los datos devueltos por el VAAC
- - DataModelName debe ser una de las dimensiones admitidas
- - El valor debe tener el formato correcto (datetime, string, number etc.)
- - Operandos:
- - - 0: es igual a
- - - 1 - No es igual a
- - - 2: contiene
- - - 3: comienza con
- - - 4 - Mayor que
- - - 5 - Mayor o igual que
- - - 6 - Menor que
- - - 7 - Menor o igual que
- - - 8 - No contiene
- - - 9 - No empieza con

- Dimensiones:
- - DataModelName debe ser una de las dimensiones admitidas

- Medidas:
- - DataModelName debe ser una de las medidas admitidas

- Parámetros: Actualmente solo se admite UserAgent.

- LimitResultRowsCount: el recuento máximo de filas devuelto por VAAC

## <a name="accessing-vaac-outside-of-power-bi"></a>Acceso a VAAC fuera de Power BI

Se puede acceder a la API DE VAAC mediante cualquier aplicación que pueda acceder a aplicaciones RESTful.  En el ejemplo siguiente, se usará [Postman](https://www.postman.com/) .

### <a name="preparation"></a>Preparación

Descargar [Cartero](https://www.postman.com/).

Descargue el repositorio: [sync_pstn_avs-analytics](https://skype.visualstudio.com/SBS/_git/sync_pstn_avs-analytics) y descomprima el repositorio.

Importe la carpeta en Postman. 

:::image type="content" source="media/aa-cq-historical-report-postman-01.png" alt-text="Captura de pantalla que muestra la importación completada":::

### <a name="accessing-vaac-using-postman"></a>Acceso al VAAC con Postman

1. Seleccione **VAAC: msit** en la parte superior derecha **_sin menú desplegable Entorno_** .
2. Seleccione **Entornos** en el menú del carril izquierdo.
3. Seleccione **VAAC - msit** en **Globales**.
4. Reemplace **userName**, **password** y **tenantId** por las credenciales aplicables.
5. Haga clic en **Restablecer todo** en la esquina superior derecha.
6. Haga clic en **Guardar**.

:::image type="content" source="media/aa-cq-historical-report-postman-02.png" alt-text="Captura de pantalla que muestra los campos nombre de usuario, contraseña e id. de inquilino configurados":::


7. Seleccione **Colecciones** en el menú de guía de la izquierda.
8. Seleccione **Token de acceso de API de configuración - Producto** y vaya a la pestaña **Cuerpo** .
9. Haga clic en **Enviar**.

Se devolverá un token de acceso.

:::image type="content" source="media/aa-cq-historical-report-postman-03.png" alt-text="Captura de pantalla que muestra el resultado con el token de acceso devuelto":::

Si no se devuelve un token de acceso, compruebe sus credenciales para que tengan [permisos suficientes](#permissions-to-access-the-cqd-pipeline).

10. Seleccione **VAAC ConfigAPI Prod** y vaya a la pestaña **Parámetros** .

- [Comprimir](#compress-the-json-query) la consulta como se describe a continuación
- [La dirección URL codifica](#url-encode-the-compressed-json-query) el resultado comprimido como se describe a continuación

11. Rellene la cadena [de consulta](#constructing-a-valid-query) .
12. Haga clic en **Enviar**.

### <a name="reading-the-result"></a>Lectura del resultado

Después de enviar tu entrada, habrá un par de resultados posibles:

- Si la entrada no es válida, se devolverá un mensaje de error con el motivo real.
- Si la entrada es válida, el resultado tendrá el siguiente aspecto:

:::image type="content" source="media/aa-cq-historical-report-postman-04.png" alt-text="Captura de pantalla que muestra el resultado de la consulta con el campo dataResult":::

En este caso, los datos estarán en el campo "dataResult" en el mismo orden solicitado en la dimensión de la consulta y en los atributos de medición.


### <a name="compress-the-json-query"></a>Comprimir la consulta JSON

La API vaac solo acepta cadenas GZip comprimidas o codificadas en Base64 como entrada.

Busque cualquier sitio web para comprimir el blob json con GZIP o Base64.

- GZIP: (https://www.multiutil.com/text-to-gzip-compress/)
- Base64: (https://www.multiutil.com/text-to-base64-converter/)

La salida GZIP debe tener el siguiente aspecto:
````
H4sIAAAAAAAACq2SQWsCMRCF7/6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif+9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf+xJLIGhIo12CjXKPM0o+2cLn2BjEjKVZQM1Gqjhhfy+QQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3/hUBqPKya/WyD41bpCXpP+tzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa/Y2Tk/wI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA=
````

La salida Base64 debe tener el siguiente aspecto:
````
ew==
IkZpbHRlcnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0wMSIs
Ik9wZXJhbmQiOjQ=
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0zMCIs
Ik9wZXJhbmQiOjY=
fQ==
XSw=
IkRpbWVuc2lvbnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg==
fQ==
XSw=
Ik1lYXN1cmVtZW50cyI6Ww==
ew==
IkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg==
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI=
fQ==
XSw=
IlBhcmFtZXRlcnMiOns=
IlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai
fSw=
IkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA=
fQ==
````

### <a name="url-encode-the-compressed-json-query"></a>URL-Encode la consulta JSON comprimida

La consulta JSON comprimida de GZIP o Base64 debe tener [codificación URL](https://meyerweb.com/eric/tools/dencoder/).

La salida GZIP URL codificada tendrá el siguiente aspecto:
````
H4sIAAAAAAAACq2SQWsCMRCF7%2F6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif%2B9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf%2BxJLIGhIo12CjXKPM0o%2B2cLn2BjEjKVZQM1Gqjhhfy%2BQQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3%2FhUBqPKya%2FWyD41bpCXpP%2BtzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa%2FY2Tk%2FwI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA%3D
````

La salida con codificación URL de Base64 tendrá el siguiente aspecto:
````
%0Aew%3D%3D%0AIkZpbHRlcnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0wMSIs%0AIk9wZXJhbmQiOjQ%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0zMCIs%0AIk9wZXJhbmQiOjY%3D%0AfQ%3D%3D%0AXSw%3D%0AIkRpbWVuc2lvbnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg%3D%3D%0AfQ%3D%3D%0AXSw%3D%0AIk1lYXN1cmVtZW50cyI6Ww%3D%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg%3D%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI%3D%0AfQ%3D%3D%0AXSw%3D%0AIlBhcmFtZXRlcnMiOns%3D%0AIlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai%0AfSw%3D%0AIkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA%3D%0AfQ%3D%3D
````

## <a name="version-3xx-history"></a>Historial de la versión 3.x.x

Consulte: Operador automático de Teams & informes históricos de la cola de llamadas: cambiar Log.docx en el archivo zip descargado para obtener una lista detallada de los cambios 

|Versión  |Fecha de publicación     |Nombre                                                    |Descripción                                                             |
|:--------|:------------------|:-----------------------------------------------------------|:-----------------------------------------------------------------------|
|3.0.5    |9 de enero de 2023    |El operador automático de Teams & informes históricos de la cola de llamadas v3.0.5 |Objetos visuales de escala de tiempo de agente y destinos de desbordamiento de llamadas mejorados  |
|3.0.4    |18 de noviembre de 2022  |El operador automático de Teams & informes históricos de la cola de llamadas v3.0.4 |Error corregido, clasificación de llamada mejorada, leyenda agregada             |
|3.0.3    |8 de noviembre de 2022   |El operador automático de Teams & informes históricos de la cola de llamadas v3.0.3 |Error corregido, vínculo de documentación agregado y consultas optimizadas            |
|3.0.1    |26 de octubre de 2022   |El operador automático de Teams & informes históricos de la cola de llamadas v3.0.1 |Se quitó la prueba de entrada del origen de datos                                       |
|3.0.0    |25 de octubre de 2022   |Operador automático de Teams & informes históricos de la cola de llamadas v3.0.0 |Nuevo origen de datos back-end                                                 |
