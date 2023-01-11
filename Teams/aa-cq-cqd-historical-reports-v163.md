---
title: Informes históricos del operador automático y de la cola de llamadas para GCC High y DoD
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
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo usar el operador automático de Teams & informe de historial de la cola de llamadas de Power BI para ver los datos históricos del operador automático y de la cola de llamadas de los clientes de GCC High y DoD.
ms.openlocfilehash: cde953bfd8e9c95c60c795f6de91488506c2addf
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763681"
---
# <a name="auto-attendant-and-call-queue-historical-reports-for-gcc-high-and-dod"></a>Informes históricos del operador automático y de la cola de llamadas para GCC High y DoD

> [!IMPORTANT]
> El soporte de nube pública para la plantilla V1.63 finalizará el 25 de noviembre de 2022.
>
> Los clientes de la nube pública deben usar V3.x.x de [Operador automático & informes históricos de la cola de llamadas](aa-cq-cqd-historical-reports.md)

## <a name="v163-published-on-august-24-2022"></a>V1.63 publicado el 24 de agosto de 2022

La **plantilla de Power BI Para el operador automático de Teams & informe histórico de la cola de llamadas** proporciona los tres informes siguientes:

- El informe [Operador automático](media/aa-cq-historical-report-sample-aa-v163.png) muestra análisis de las llamadas que llegan a sus operadores automáticos.
- El informe [Cola de llamadas](media/aa-cq-historical-report-sample-cq-v163.png) muestra análisis de las llamadas que llegan a las colas de llamadas.
- El informe [Escala de tiempo del agente](media/aa-cq-historical-report-sample-at-v163.png) muestra una vista de escala de tiempo de los agentes que están activos en las llamadas de la cola de llamadas.

Estos informes usan datos del almacén de datos del [Panel de calidad de llamadas (CQD](CQD-Power-BI-query-templates.md) ). 

## <a name="v163-prerequisites"></a>Requisitos previos de V1.63

### <a name="power-bi-desktop"></a>Power BI Desktop
Debes tener Power BI Desktop instalado. Puedes instalar y usar la versión gratuita de [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

La versión mínima compatible es 2.85.681.0 (septiembre de 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Permisos para obtener acceso a la canalización del CQD

La cuenta que use para ver el informe histórico debe tener permisos para acceder a la canalización de datos del CQD. Para obtener más información, vea [Rol de acceso del CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="v163-installation"></a>Instalación v1.63 

En los pasos siguientes se supone que ya ha instalado Power BI Desktop en el equipo y que su cuenta tiene los permisos necesarios para acceder a la canalización de datos del CQD.

Siga estos pasos:

1. Descargue y guarde el archivo zip de [plantillas de consulta de Power BI del CQD](https://www.microsoft.com/download/details.aspx?id=102291) en el equipo.

2. Abra el archivo zip.

3. Abra el archivo de `CQD Teams Auto Attendant & Call Queue Historical Report V1.63.pbit` plantilla. Power BI Desktop debería iniciarse.

4. Se le pedirá que seleccione la región de canalización de datos del CQD. Seleccione la región donde se encuentra el inquilino.

     :::image type="content" source="media/aa-cq-historical-report-01-v163.png" alt-text="Captura de pantalla que selecciona la región de la canalización de datos del CQD.":::

    Inquilinos en la nube pública

5. La región donde se encuentra su inquilino se puede obtener mediante el cmdlet [Get-CsTenant](/powershell/module/skype/get-cstenant) .

    ```powershell
    (Get-CsTenant).ServiceInstance

    microsoftcommunicationsonline/noam-4a-s7
    ```

    La región se mostrará después de la **/** como en el ejemplo anterior donde la región es `noam`.

    Inquilinos de GCC High y DoD

6. Actualice la plantilla para usar uno de los siguientes conectores:

   - GCCH: `https://data.cqd.gov.teams.microsoft.us/RunQuery`
   - Dod: `https://data.cqd.dod.teams.microsoft.us/RunQuery`


7. El informe se iniciará con datos de ejemplo.
 
8. Para ver sus propios datos, seleccione **Actualizar** en la pestaña **Inicio** en **Consultas** en Power BI Desktop.

   :::image type="content" source="media/aa-cq-historical-report-02-v163.png" alt-text="Captura de pantalla que selecciona la opción de actualización.":::

9. Se le pedirá que inicie sesión. Seleccione **Cuenta de la organización** y, a continuación, seleccione **Iniciar sesión**.

   :::image type="content" source="media/aa-cq-historical-report-03-v163.png" alt-text="Captura de pantalla que muestra el inicio de sesión para V1.63.":::

10. Selecciona **Conectar** y los datos se actualizarán.

## <a name="data-latency-for-aa-and-cq-analytics"></a>Latencia de datos para análisis de AA y CQ

Los datos suelen estar disponibles en un plazo de 30 minutos desde la finalización de la llamada; sin embargo, hay ocasiones en las que puede tardar varias horas en aparecer los datos.

Tendrá que actualizar los datos para ver los nuevos datos.

## <a name="customization"></a>Personalización

Puede personalizar ciertos aspectos de visualización de los informes, como agregar o quitar campos para que se muestren en las distintas visualizaciones, cambiar el tipo de gráfico, etc.

El informe contiene todas las métricas de datos disponibles actualmente.

### <a name="change-color-schema"></a>Cambiar esquema de color

En los pasos siguientes se supone que ya ha completado los pasos de instalación.

Siga estos pasos:

1. Seleccione **la pestaña Vista** en la cinta de opciones.

    :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="Captura de pantalla que selecciona la pestaña vista para cambiar la combinación de colores.":::

2. Seleccione el esquema de color de la lista desplegable.

    :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="Captura de pantalla que muestra varias combinaciones de colores.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definiciones de informes históricos del operador automático y de la cola de llamadas

### <a name="cloud-auto-attendant-analytics-report"></a>Informe de análisis de Operador automático en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección informe                          |Descripción                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Origen de llamadas entrantes<sup>1</sup>        |Distribución de llamadas por origen de llamadas interno o externo            |
|Método de búsqueda en directorios                 |Distribución de llamadas por tipo de búsqueda                              |
|Recuento de acciones del autor de la llamada                     |Distribución de llamadas por número de acción usada durante la llamada       |
|Promedio de segundos en AA                   |Número medio de segundos que pasan los autores de llamadas en la AA                 |
|Acciones de llamada promedio                  |Número medio de acciones que realizan los autores de llamadas en la AA               |
|Resultados de llamadas                            |Distribución de llamadas por estado de llamada final                         |
|Sección inferior del informe                 |Desglose del flujo de llamadas                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>Informar sobre la tabla y asignación de campos del CQD

|Pestaña Informe            |Nombre de tabla de informe     |Nombre de la tabla de origen            |Filtro global                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|Operador automático        |fAutoAttendant        |AutoAttendant                |Ninguna                                   |

|Sección informe                                  |Campo(s) Utilizados                              |Filtros aplicados     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Selector de fecha                                   |AAStartTime                                |Ninguna                |
|Selector intervalo de tiempo                             |AAStartHour                                |Ninguna                |
|Operador automático                                  |Nombre AA                                    |Ninguna                |
|Origen de llamadas entrantes<sup>1</sup>                |Tipo de llamada<br>Suma de TotalCallCount (medida) |Llamadas externas: el tipo de llamada es externo<br>Llamadas internas: el tipo de llamada es interno |
|Método de búsqueda en directorios                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod es abs_search_dtmf o abs_search_name    |
|Recuento de acciones del autor de la llamada                             |AACallerActionCount<br>TotalCallCount      |Ninguna                                                             |
|Promedio de segundos en AA                           |AAChainDuration (medida)                  |Ninguna                                                             |
|Acciones de llamada promedio                          |AACallerActionCount (medida)              |Ninguna                                                             |
|Resultados de llamadas                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |Ninguna                                       |
|Sección inferior del informe                         |Nombre AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Tipo de llamada<br>MM-DD<br>TotalCallCount |Ninguna       |

#### <a name="fautoattendant-cqd-fields-description"></a>Descripción de los campos fAutoAttendant CQD

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nombre AA                                 |Texto                     |Nombre de la cuenta de recursos adjunta al operador automático<br><br>Si se **aa_test@microsoft.com** el nombre completo de la cuenta de recursos, este valor será: **aa_test** |
|AACallerActionCount                     |Número entero             |Resumir: Suma<br>Recuento de acciones seleccionadas por el autor de la llamada en operador automático durante la llamada  |
|AACallerActionCount (medida)          |Número entero             |Igual que antes, excepto será 0 si no hay llamadas en lugar de en blanco                              |
|AACallFlow                              |Texto                     |Encapsula los diferentes estados de la llamada del operador automático (valores posibles):<br><br>§ abs_search<br>§ anuncio<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Texto                     |Resultado de la llamada final: valores posibles:<br><br>§ failed_to_establish_media (no se pudo establecer la parte multimedia de la llamada)<br>§ failover_to_operator (llamada transferida al operador normalmente debido a un error del sistema)<br>§ oaa_chain_too_long (demasiadas piernas en la AA)<br>§ oaa_session_too_long (la sesión de AA ha durado demasiado tiempo)<br>§ service_declined (AA no aceptó la llamada)<br>§ service_terminated (la configuración AA desconecta la llamada o la llamada colgada)<br>§ terminated_automatic_selection (la configuración AA desconecta las llamadas)<br>§ terminated_no_operator (llamada finalizada debido a un error no definido por un operador) <br>§ terminated_transfer_failed (llamada terminada como error en la transferencia - normalmente a un número externo)<br>§ transfer_in_progress (transferencia AA->AA)<br>§ transferred_to_operator (la llamada se transfirieron al operador- normalmente debido a un error del usuario)<br>§ transferred_to_receptionist (igual que transferred_to_operator)<br>§ transferred_to_self (la llamada se devolvió al inicio de la AA - normalmente desde una opción de anuncio de menú)<br>§ transferred_to_shared_voicemail (la llamada se transfirieron al correo de voz compartido)<br>§ transferred_to_user (la llamada se ha transferido a un usuario- incluye colas de llamadas)<br>§ Desconocido (se ha producido una condición desconocida)<br>§ user_terminated (el llamador colgó) |
|Leyenda de llamada de AA                          |Texto                     |Configura elementos de leyenda basados en AACallResult                               |
|AAChainDuration                         |Número decimal           |Resumir: Suma<br>Duración de la llamada en el operador automático                     |
|AAChainDuration (medida)               |Número decimal           |Igual que antes, excepto será 0 si no hay llamadas en lugar de en blanco              |
|AAChainIndex                            |Texto                     |                                                                         |
|AAConnectivityType                      |Texto                     |Tipo de llamada: valores posibles:<br><br>§ Llamada externa<br>§ InternalCall |
|AACount                                 |Texto                     |Número de operadores automáticos implicados en la llamada                               |
|AADirectorySearchMethod                 |Texto                     |Método de búsqueda última libreta de direcciones: valores posibles:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |Número decimal           |Hora de inicio de llamada de Operador automático                                           |
|AAStartTime                             |Fecha y hora                |Hora de inicio de llamada de Operador automático                                           |
|AATransferAction                        |Texto                     |Tipo de destino de transferencia de llamada: posibles valores:<br><br>§ aplicación - entidad de aplicación de voz<br>§ external_pstn<br>§ hunt_group - Entidad de cola de llamadas<br>§ orgaa: entidad Operador automático<br>§ shared_voicemail<br>§ desconocido<br>§ usuario |
|Tipo<sup>de llamada 1</sup>                   |Texto                     |Tipo de llamada: valores posibles:<br><br>§ Externo<br>§ Interno           |
|IsAAInvolved                            |Texto                     |Siempre 1                                                                 |
|MM-DD                                   |Texto                     |Llamada del mes del operador automático                                            |
|PSTNMinutes                             |Número entero             |Resumir: Suma<br>Uso total de minutos                                     |
|TotalCallCount                          |Número entero             |Resumir: Suma<br>Siempre 1: se usa para proporcionar la suma de todas las llamadas            |
|Suma de TotalCallCount (medida)         |Número entero             |Igual que antes, excepto será 0 si no hay llamadas en lugar de en blanco              |


### <a name="cloud-call-queue-analytics-report"></a>Informe de análisis de cola de llamadas en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección informe                          |Descripción                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Origen de llamadas entrantes<sup>1</sup>        |Distribución de llamadas por origen de llamadas interno o externo             |
|Tiempo medio de espera (segundos)             |Esperar tiempo para las llamadas contestadas y abandonadas                          |
|Volumen de llamadas y recuento de agentes aceptados      |Distribución de llamadas por colas de llamadas / Número máximo de opt-ins del agente  |
|Resultados de llamadas                            |Distribución de llamadas por resultado de llamada                               |
|Llamadas abandonadas                         |Distribución de llamadas abandonadas por colas de llamadas                     |
|Duración media de la sesión (segundos)        |Duración de la llamada en segundos agrupada por resultado de llamada                      |
|Destinos de desbordamiento o tiempo de espera de llamadas      |Distribución de llamadas con tiempo de salida o desbordados                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Informar sobre la tabla y asignación de campos del CQD

|Pestaña Informe            |Nombre de tabla de informe                                   |Nombre de la tabla de origen                               |Filtro global       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|Cola de llamadas            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |Ninguna                |

|Sección informe                      |Tabla -> Campo(s) Usados                |Filtros aplicados       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Selector de fecha                       |fCallQueueAnalytics -> Date           |Ninguna                  |
|Selector intervalo de tiempo                 |fCallQueueAnalytics -> CQHour         |Ninguna                  |
|Cuenta de recursos de cola de llamadas         |fCallQueueAnalytics -> nombre del CQ        |Ninguna                  |
|Origen de llamadas<sup>entrantes 1</sup>    |fCallQueueAnalytics -> Suma del recuento de llamadas (medida)<br>fCallQueueAnalytics -> tipo de llamada    |Llamadas externas: el tipo de llamada es externo<br>Llamadas internas: el tipo de llamada es interno |
|Avg Wait Time (seconds)-Before Answered |fCallQueueFinalStateAction -> Avg of Average CQ Duration (Measure) |El resultado de llamadas en cola de llamadas es agent_joined_conference o transferred_to_agent|
|Avg Wait Time (seconds)-Before Abandoned |fCallQueueFinalStateAction -> Avg of Average Call Duration (Measure) |El resultado de llamadas en cola de llamadas no es agent_joined_conference, transferred_to_agent, desbordamiento timed_out |
|Recuento de Opt-In de agente y volumen de llamadas   |fCallQueueAnalytics -> Recuento de llamadas<br>fCallQueueAnalytics -> agente de cola de llamadas Opt In Count<br>fCallQueueAnalytics -> nombre del CQ<br>fCallQueueAnalytics -> Date |Ninguna |
|Llamadas abandonadas                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | La leyenda de resultados de llamadas de la cola de llamadas está abandonada |
|Duración media de la sesión (segundos)    |fCallQueueFinalStateAction -> duración media de la cola de llamadas (seg.)<br>Leyenda de resultados de llamadas de la cola de llamadas |Duración media de la cola de llamadas (seg.) > 0 |
|Destinos de desbordamiento o tiempo de espera de llamadas  |fCallQueueAnalytics -> Recuento de llamadas<br>fCallQueueAnalytics -> tipo de destino de la cola de llamadas<br>Leyenda de tipo de destino fCallQueue |La leyenda de tipo de destino de la cola de llamadas no contiene abandonado y el agente contestado |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Descripción de los campos fCallQueueAnalytics CQD

|Nombre                                    |Tipo de datos                |Descripción                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas                                          |
|Recuento del agente de cola de llamadas                  |Número entero             |Resumir: Suma<br>Número de agentes configurados en la cola de llamadas            |
|Cuenta de la opción Agente de cola de llamadas           |Número entero             |Resumir: Suma<br>Número de agentes que han optado por participar en la cola de llamadas              |
|Resultado de llamadas en cola de llamadas                  |Texto                     |Estado final de llamada de la cola de llamadas: valores posibles:<br><br>§ agent_joined_conference (llamadas en modo conferencia contestadas)<br>§ rechazada<br>§ desconectado<br>§ error<br>§ Error<br>§ no válido<br>§ desbordamiento (condición de desbordamiento cumplida)<br>§ timed_out (condición de tiempo de espera cumplida)<br>§ transferred_to_agent (llamadas en modo de transferencia contestadas {default}) |
|Leyenda de resultados de llamadas de la cola de llamadas           |Texto                     |Configura elementos de leyenda según el resultado de la cola de llamadas                             |
|Tipo de destino de la cola de llamadas                  |Texto                     |***Tipo de destino de redireccionamiento de llamadas: posibles valores:***<br><br>§ ApplicationEndpoint<br>§ Buzón<br>§ Otros<br>§ Usuario |
|Leyenda de tipo de destino de la cola de llamadas           |Texto                     |Configura elementos de leyenda según el tipo de destino de la cola de llamadas                        |
|Tipo<sup>de llamada 1</sup>                   |Texto                     |Tipo de llamada: valores posibles:<br><br>§ Externo<br>§ Interno             |
|Nombre del CQ                                 |Texto                     |Nombre de la cuenta de recursos adjunta a la cola de llamadas<br><br>Si se **cq_test@microsoft.com** el nombre completo de la cuenta de recursos, el valor será: **cq_test** |
|Hora del CQ                                 |Número entero             |Hora de inicio de llamada de la cola de llamadas                                                 |
|Fecha                                    |Fecha y hora                |Fecha y hora de inicio de la llamada en cola de llamadas (hora)                                 | 
|DateTimeCQName                          |Texto                     |Clave única para filtrar en fCallQueueFinalStateAction                     |
|Tipo de conectividad RTC                  |Texto                     |Tipo de llamada: valores posibles:<br><br>§ Llamada externa<br>§ InternalCall     |
|Minutos totales de RTC                      |Número entero             |Resumir: Suma<br>Uso total de minutos para llamadas RTC                       |
|Suma del recuento de llamadas (medida)             |Número entero             |Igual que el recuento de llamadas, sin embargo, será 0 cuando no se llame                          |
|TotalCallCount (medida)                |Número entero             |Resumir: Suma<br>Recuento de llamadas                                                |


#### <a name="fcallqueuefinalstateaction-cqd-fields-description"></a>descripción de los campos fCallQueueFinalStateAction CQD

|Nombre                                    |Tipo de datos                |Descripción                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Duración media de la llamada (segundos)         |Número decimal           |Resumir: Suma<br>Duración media de llamadas en segundos para llamadas abandonadas    |
|Duración media de la cola de llamadas (s)       |Número decimal           |Resumir: Suma<br>Promedio de espera en segundos para las llamadas contestadas           |
|Avg of Average Call Duration (Measure)  |Número entero             |Igual que la duración media de llamadas (segundos), sin embargo, será 0 cuando no haya llamadas   |
|Avg of Average CQ Duration (Measure)    |Número entero             |Igual que la duración media de la cola de llamadas (s), sin embargo, será 0 cuando no haya llamadas |
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas                                         |
|Resultado de llamadas en cola de llamadas                  |Texto                     |Estado final de llamada de la cola de llamadas: valores posibles:<br><br>§ agent_joined_conference (llamadas en modo conferencia contestadas)<br>§ rechazada<br>§ desconectado<br>§ error<br>§ Error<br>§ no válido<br>§ desbordamiento (condición de desbordamiento cumplida)<br>§ timed_out (condición de tiempo de espera cumplida)<br>§ transferred_to_agent (llamadas en modo de transferencia contestadas {default} |
|Leyenda de resultados de llamadas de la cola de llamadas           |Texto                     |Configura elementos de leyenda según el resultado de llamadas en cola de llamadas                      |
|Acción de estado final de la cola de llamadas           |Texto                     |Acción final de la cola de llamadas: valores posibles:<br><br>§ Desconectar (llamadas timed_out)<br>§ disconnect_with_busy (llamadas desbordadas)<br>§ failed_to_accept_call<br>§ adelante<br>§ shared_voicemail<br>§ otro<br>§ correo de voz                |
|Nombre del CQ                                 |Texto                     |Nombre de la cuenta de recursos adjunta a la cola de llamadas<br><br>Si se **cq_test@microsoft.com** el nombre completo de la cuenta de recursos, el valor será: **cq_test** |
|Fecha                                    |Fecha y hora                |Fecha y hora de inicio de llamadas de la cola de llamadas (hora)                                 |
|DateTimeCQName                          |Texto                     |Clave única para filtrar en fCallQueueFinalStateAction                     |
|IsAbandoned                             |Verdadero/falso               |Verdadero si un agente no responde a la llamada                                   |


### <a name="cloud-call-queue-agent-timeline-report"></a>Informe escala de tiempo del agente de cola de llamadas en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección informe                                          |Descripción                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Número de llamadas por agente                                |Distribución de llamadas por cola de llamadas y agente                |
|Distribución por agente y toda la cola                     |Distribución de llamadas por agente y cola de llamadas                |
|Tabla (inferior derecha)                                    |Distribución de llamadas por agente con duración media y total de llamadas |
|Duración media de llamadas (segundos) por agente                |Duración media (segundos) de llamada por agente                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Informar sobre la tabla y asignación de campos del CQD

|Pestaña Informe            |Nombre de tabla de informe           |Nombre de la tabla de origen         |Filtro global       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|Escala de tiempo del agente        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |Ninguna                |


|Sección informe                                |Campo(s) Utilizados                         |Filtros aplicados       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Selector de fecha                                 |Datetime                              |Ninguna                  |
|Selector de nombre de usuario de agente                       |Nombre del agente                            |Ninguna                  |
|Selector de cuentas de recursos de cola de llamadas          |Nombre del CQ                               |Ninguna                  |
|Número de llamadas por agente                      |Nombre del agente<br>Recuento de llamadas<br>Hour      |Ninguna                  |
|Distribución por agente y cola de llamadas          |Nombre del agente<br>Duración media de llamadas (segundos)<br>Recuento de llamadas<br>Nombre del CQ |Ninguna                      |
|Inferior izquierda                                   |Nombre del agente<br>Duración media de la llamada (segundos)<br>Recuento de llamadas<br>Duración de la llamada (minuto)<br>Nombre del CQ<br>Hour<br>MM-DD | Ninguna |
|Duración media de llamadas (segundos) por agente      |Nombre del agente<br>Duración media de la llamada (segundos) | Ninguna |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Descripción de los campos fAgentTimelineAnalytics CQD

|Nombre                                    |Tipo de datos                |Descripción                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nombre del agente                              |Texto                     |UPN de usuario<br>Si se **user@microsoft.com** el nombre de usuario completo, este valor será: **usuario** |
|Duración media de la llamada (segundos)         |Número decimal           |Resumir: Suma<br>Duración media de las llamadas en cola de llamadas respondidas en segundos |
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas contestadas por el agente     |
|Duración de la llamada (minutos)                 |Número entero             |Resumir: Suma<br>Duración total de las llamadas de la cola de llamadas respondidas en minutos (redondeado hacia abajo a los minutos más cercanos)  |
|Nombre del CQ                                 |Texto                     |Nombre de la cuenta de recursos adjunta a la cola de llamadas<br><br>Si se **cq_test@microsoft.com** el nombre completo de la cuenta de recursos, el valor será: **cq_test** |
|Fecha                                    |Fecha                     |Fecha de llamada                                             |
|Datetime                                |Datetime                 |Fecha de llamada                                             |
|Hour                                    |Número entero             |Hora de llamada                                             |
|MM-DD                                   |Texto                     |Mes y día de llamada                                    |


> [!NOTE]
> Cuando una llamada llega a la primera cola de llamadas, si el número de llamadas que ya están en esa cola ha alcanzado el límite de **administración de desbordamiento** de llamadas y si la opción de redirección envía nuevas llamadas a una segunda cola de llamadas, se mostrará que los agentes de la segunda cola de llamadas están en la primera cola de llamadas de este informe. 

## <a name="known-issues"></a>Problemas conocidos

- La cola de llamadas y los operadores automáticos se muestran con el id. de la cuenta de recursos en lugar de con los nombres de la cola de llamadas y los operadores automáticos.  Para mostrar todo el tráfico de un operador automático o de una cola de llamadas, debe seleccionar todas las cuentas de recursos asignadas al operador automático o a la cola de llamadas.

- Solo hay 28 días de historial disponibles en el panel, ya que los datos de la cola de llamadas o del operador automático se consideran datos personales y están sujetos a las directivas de retención de privacidad de datos.

- En algunos casos, el agente respondió el recuento de llamadas en el informe escala de tiempo del agente de cola de **llamadas** en la nube puede ser diferente al número de llamadas que se muestra en el historial de llamadas del cliente de Teams. El historial de llamadas del cliente de Teams es correcto. El soporte técnico se está investigando, pero no hay tiempo estimado para reparar disponible en este momento.

- <sup>1</sup> **La fuente de llamada entrante** en el operador automático y los gráficos de la cola de llamadas muestran el origen final del tramo de llamada en lugar del origen del tramo de llamada inicial. Por ejemplo, si un operador automático recibe una llamada externa y transfiere la llamada a otro operador automático o a la cola de llamadas, el **origen de llamadas entrantes** se notificará como Interno.

## <a name="version-1xx-history"></a>Historial de la versión 1.xx

Consulte: Operador automático de Teams del CQD & informes históricos de la cola de llamadas: cambiar Log.docx en el archivo zip descargado para obtener una lista detallada de los cambios                         

|Versión  |Fecha de publicación     |Nombre                                                           |Descripción                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------
|1.63     |24 de agosto de 2022    |Operador automático de Teams del CQD & informe de historial de la cola de llamadas V1.63.pbit |                                                    |
|1.60     |22 de julio de 2022      |Operador automático de Teams del CQD & informe histórico de la cola de llamadas V1.60.pbit |                                                    |
|1.00     |5 de noviembre de 2020   |Análisis combinado de CQ y AA 20201105.pbit                         |Versión inicial                                     |

