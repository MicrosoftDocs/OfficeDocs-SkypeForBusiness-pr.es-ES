---
title: Informe de historial de la cola de llamadas del operador automático &
author: CarolynRowe
ms.author: crowe
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
description: Obtenga información sobre cómo usar el panel de calidad de llamadas Power BI informe para ver los datos históricos del operador automático y de la cola de llamadas.
ms.openlocfilehash: e2d71410d10fb809debd1699afcf452c71a6e088
ms.sourcegitcommit: 193aec6f3f6b6ac14b07e778b3485eed813f5e99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046452"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Informe de historial de la cola de llamadas del operador automático &

La plantilla de Power BI informe de historial de la cola de llamadas & operador automático de Teams proporciona los tres informes siguientes:

- [Operador automático](media/cqd-teams-aa-cq-historical-report-sample-aa.png) : muestra análisis de llamadas que llegan a sus operadores automáticos.
- [Cola de llamadas](media/cqd-teams-aa-cq-historical-report-sample-cq.png) : muestra análisis de llamadas que llegan a las colas de llamadas.
- [Línea de tiempo del agente](media/cqd-teams-aa-cq-historical-report-sample-at.png) : muestra una vista de escala de tiempo de agentes que están activos en las llamadas de la cola de llamadas.

Estos informes usan datos del almacén de datos del [panel de calidad de llamadas](CQD-Power-BI-query-templates.md) . Los informes permiten a las organizaciones informar sobre el número de llamadas que procesan los operadores automáticos y las colas de llamadas.  Los informes también proporcionan información sobre el rendimiento del agente en las colas de llamadas.

## <a name="prerequisites"></a>Requisitos previos

### <a name="power-bi-desktop"></a>Power BI Desktop
Debes tener Power BI Desktop instalado. Puedes instalarlo desde [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

Puede usar la versión gratuita de Power BI Desktop. La versión mínima compatible es 2.85.681.0 (septiembre de 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Permisos para obtener acceso a la canalización del CQD

La cuenta que use para ver el informe histórico debe tener permisos para acceder a la canalización de datos del CQD. Para obtener más información, vea [Rol de acceso del CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="installation"></a>Instalación 

En los pasos siguientes se supone que ya ha instalado Power BI Desktop en el equipo y que su cuenta tiene los permisos necesarios para acceder a la canalización de datos del CQD.

Siga estos pasos:

- Descargue las [plantillas de consulta de Power BI del CQD](https://www.microsoft.com/download/details.aspx?id=102291) y guarde el archivo zip en un directorio del equipo.

- Haz doble clic en el archivo zip para abrirlo.

- Haga doble clic en el archivo de plantilla "CQ y AA combined Analytics 20201105.pbit". El Power BI Desktop debería iniciarse.

- Se le pedirá que seleccione la región de canalización de datos del CQD. Seleccione la región donde se encuentra el inquilino.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de pantalla que selecciona la región de la canalización de datos del CQD.":::

- La región donde se encuentra su inquilino se puede obtener mediante el cmdlet [Get-CsTenant](/powershell/module/skype/get-cstenant) .

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - La región se mostrará después de la **/** como en el ejemplo anterior donde la región es: noam

 - El informe se iniciará con datos de ejemplo.
 
 - Para ver sus propios datos, seleccione **Actualizar** en la pestaña Inicio en Consultas en Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de pantalla que selecciona la opción de actualización.":::

- A continuación, se le pedirá que inicie sesión. Seleccione **Cuenta de la organización** y, a continuación, seleccione **Iniciar sesión**.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de pantalla que muestra el inicio de sesión.":::

- Seleccione **Conectar** y vea cómo se actualizan los datos.

## <a name="data-latency-and-aa--cq-analytics"></a>Latencia de datos y análisis de AA & CQ

Los datos estarán disponibles en la canalización de datos del CQD en 30 minutos.

Tendrá que actualizar los datos para ver los nuevos datos de análisis. 

## <a name="customization"></a>Personalización 

Puede personalizar ciertos aspectos de visualización de los informes, como agregar o quitar campos para que se muestren en las distintas visualizaciones, cambiar el tipo de gráfico, etc.

No puede agregar más campos de datos al informe.

### <a name="change-color-schema"></a>Cambiar esquema de color 

En los pasos siguientes se supone que ya ha completado los pasos de instalación.

Siga estos pasos:
- Seleccione **la pestaña Vista** en la cinta de opciones.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de pantalla que selecciona la pestaña vista para cambiar la combinación de colores.":::

- Seleccione el esquema de color de la lista desplegable.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Captura de pantalla que muestra varias combinaciones de colores.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Definiciones de informes históricos del operador automático y de la cola de llamadas

### <a name="cloud-auto-attendant-analytics"></a>Análisis de operadores automáticos en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección informe                          |Descripción                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Origen de llamadas<sup>entrantes 1</sup>        |Distribución de llamadas por origen de llamadas interno o externo             |
|Totales del método de búsqueda en directorios          |Distribución de llamadas por tipo de búsqueda                               |
|Acción del autor de la llamada                           |Distribución de llamadas por receptor de llamadas                             |
|Resultado de llamada                             |Distribución de llamadas por estado de llamada final                          |
|Recuento de acciones del autor de la llamada                     |Distribución de llamadas por número de acción usada durante la llamada        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Informar sobre la tabla y asignación de campos del CQD

|Pestaña Informe            |Nombre de tabla de informe     |Filtro global                          |
|:---------------------|:---------------------|:--------------------------------------|
|Operador automático        |fAutoAttendant        |AAStartTime está dentro de los últimos 28 días |


|Nombre de tabla de informe            |Nombre de la tabla de origen            |Tratamiento       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant, <br>#"Filas filtradas" = Table.SelectRows(Source, each true), <br>#"Operador automático" = Table.AddColumn(#"Filas filtradas", "Nombre AA", cada Lista.Primero(Text.Split([AAIdentity], "@"))), <br>#"Changed Type" = Table.TransformColumnTypes(#"Auto Attendant",{{"AAStartTime", type datetime}}), <br>#"Removed Columns" = Table.RemoveColumns(#"Changed Type",{"AAIdentity"}) |


|Sección informe                                  |Campo(s) Utilizados                              |Filtros aplicados     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Selector de fecha                                   |AAStartTime                                |Ninguna                |
|Operador automático                                  |Nombre AA                                    |Ninguna                |
|Origen de llamadas<sup>entrantes 1</sup>                |Tipo de llamada<br>TotalCallCount                |Llamadas externas: el tipo de llamada es externo<br>Llamadas internas: el tipo de llamada es interno |
|Totales del método de búsqueda en directorios                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod es abs_search_dtmf o abs_search_name    |
|Acciones del autor de la llamada                                  |AATransferAction<br>TotalCallCount         |Ninguna                                                             |
|Promedio de segundos en AA<br>Acciones de llamada promedio |AAChainDuration<br>AACallerActionCount     |Ninguna                                                             |
|Resultados de llamadas                                    |AACallResult<br>TotalCallCount             |Ninguna                                                             |
|Recuento de acciones del autor de la llamada                            |AACallerActionCount<br>TotalCallCount      |Ninguna                                                             |
|Sección inferior del informe                         |Nombre AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Tipo de llamada<br>TotalCallCount |Ninguna                |

#### <a name="fautoattendant-cqd-fields-description"></a>Descripción de los campos fAutoAttendant CQD

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nombre AA                                 |Texto                     |Nombre de la cuenta de recursos adjunta al operador automático<br><br>Si se **aa_test@microsoft.com** el nombre completo de la cuenta de recursos, este valor será: **aa_test** |
|AACallerActionCount                     |Número entero             |Resumir: Suma<br>Recuento de acciones seleccionadas por el autor de la llamada en operador automático durante la llamada  |
|AACallFlow                              |Texto                     |Encapsula los diferentes estados de la llamada del operador automático (valores posibles):<br><br>§ abs_search<br>§ anuncio<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Texto                     |Resultado de la llamada final: valores posibles:<br><br>§ failed_to_establish_media (no se pudo establecer la parte multimedia de la llamada)<br>§ failover_to_operator (llamada transferida al operador normalmente debido a un error del sistema)<br>§ oaa_chain_too_long (demasiadas piernas en la AA)<br>§ oaa_session_too_long (la sesión de AA ha durado demasiado tiempo)<br>§ service_declined (AA no aceptó la llamada)<br>§ service_terminated (la configuración AA desconecta la llamada)<br>§ terminated_automatic_selection (la configuración AA desconecta las llamadas)<br>§ terminated_no_operator (llamada finalizada debido a un error no definido por un operador) <br>§ terminated_transfer_failed (llamada cancelada por error en la transferencia - normalmente a número expernal)<br>***§ transferred_to_operator*** (la llamada se transfirieron al operador- normalmente debido a un error de entrada del usuario)<br>§ transferred_to_receptionist (igual que transferred_to_operator)<br>§ transferred_to_self (la llamada se devolvió al inicio de la AA - normalmente desde una opción de anuncio de menú)<br>§ transferred_to_shared_voicemail (la llamada se transfirieron al correo de voz compartido)<br>§ transferred_to_user (la llamada se ha transferido a un usuario- incluye colas de llamadas)<br>§ Desconocido (se ha producido un error desconocido)<br>§ user_terminated (el llamador colgó) |
|AAChainDuration                         |Número decimal           |Resumir: Suma<br>Duración de la llamada en el operador automático                     |
|AAChainIndex                            |Texto                     |                                                                         |
|AAConnectivityType                      |Texto                     |Tipo de llamada: valores posibles:<br><br>§ Llamada externa<br>§ InternalCall |
|AACount                                 |Texto                     |Número de operadores automáticos implicados en la llamada                               |
|AADirectorySearchMethod                 |Texto                     |Método de búsqueda última libreta de direcciones: valores posibles:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |Fecha y hora                |Hora de inicio de llamada de Operador automático                                           |
|AATransferAction                        |Texto                     |Tipo de destino de transferencia de llamada: posibles valores:<br><br>***§ aplicación - entidad** _<br>de aplicación de voz§ external_pstn<br>_*_§ hunt_group - entidad_*_<br>_* de cola de _llamadas§ orgaa - Entidad operador automático organizativo_**<br>§ shared_voicemail<br>§ desconocido<br>§ usuario |
|Tipo<sup>de llamada 1</sup>                   |Texto                     |Tipo de llamada: valores posibles:<br><br>§ Externo<br>§ Interno         |
|IsAAInvolved                            |Texto                     |Siempre 1                                                                 |
|PSTNMinutes                             |Número entero             |Resumir: Suma<br>Uso total de minutos                                     |
|TotalCallCount                          |Número entero             |Resumir: Suma<br>Siempre 1: se usa para proporcionar la suma de todas las llamadas            |


### <a name="cloud-call-queue-analytics"></a>Análisis de cola de llamadas en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección informe                          |Descripción                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Origen de llamadas<sup>entrantes 1</sup>        |Distribución de llamadas por origen de llamada interno o externo              |
|Volumen de llamadas                             |Distribución de llamadas por colas de llamadas                                |
|Resultado del autor de la llamada                           |Distribución de llamadas por resultado de llamada                                |
|Tiempo de espera/desbordamiento acción total de llamada      |Distribución de NO desviados(abandonados) llamadas por resultado de llamada       |
|Totales de destino de transferencia o reenvío          |Distribución de llamadas desviadas por resultado de llamada                      |
|Relación de llamadas abandonadas                   |Relación entre el número de llamadas exitosas y las llamadas abandonadas                        |
|Duración media de la sesión (segundos)        |Duración de la llamada en segundos agrupada por llamadas abandonadas o correctas       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Informar sobre la tabla y asignación de campos del CQD

|Pestaña Informe         |Nombres de tabla de informe                                                          |Filtro global |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|Cola de llamadas         |Fechas<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |Ninguna          |
 
|Nombre de tabla de informe            |Nombre de la tabla de origen            |Tratamiento       |
|:----------------------------|:----------------------------|:----------------|
|Fechas                        |Fechas                        |Ninguna             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Removed Columns" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Result", "Date", "PSTN Connectivity Type", "Call Queue Target Type", "PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Columnas quitadas") |
|fCallQueueAnalytics          |CallQueueAnalytics           |Ninguna             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |Ninguna             |

|Sección informe                      |Tabla -> Campo(s) Usados                |Filtros aplicados       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Selector de fecha                       |Dates -> DateTime                     |Ninguna                  |
|Identidad de la cola de llamadas                 |dCQ-CQIdentity -> identidad de la cola de llamadas |Ninguna                  |
|Origen de llamadas<sup>entrantes 1</sup>    |fCallQueueAnalytics -> Recuento de llamadas<br>fCallQueueAnalytics -> tipo de llamada    |Llamadas externas: el tipo de llamada es externo<br>Llamadas internas: el tipo de llamada es interno |
|Avg Waiting Time                    |fCallQueueFinalStateAction -> duración media de llamadas (segundos) |Antes de la transferencia: el resultado de llamadas en cola de llamadas se agent_joined_conference o se transferred_to_agent<br>Antes de colgar: el resultado de llamadas en cola de llamadas no está agent_joined_conference ni transferred_to_agent |
|Resultado de llamada                         |fCallQueueAnalytics -> Recuento de llamadas<br>fCallQueueAnalytics -> resultado de llamadas de la cola de llamadas | Ninguna |
|Tiempo de espera/desbordamiento de llamadas acción total |fCallQueueFinalStateAction -> Call Count<br>fCallQueueFinalStateAction -> acción de estado final de la cola de llamadas |La acción de estado final de la cola de llamadas no se reenvía |
|Totales de destino de Transferencia/Forard       |fCallQueueAnalytics -> Recuento de llamadas<br>fCallQueueAnalytics -> tipo de destino de la cola de llamadas |Ninguna |
|Volúmenes de llamadas                        |fCallQueueAnalytics -> Recuento de llamadas<br>fCallQueueAnalytics -> identificación de la cola de llamadas<br>fCallQueueAnalytics -> Date |Ninguna |
|Llamadas abandonadas                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics -> Recuento de llamadas<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned es verdadero |
|Duración media de la sesión (segundos)    |fCallQueueFinalStateAction -> duración media de llamadas<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |Ninguna |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>Descripción de los campos del dCQ-CQIdenity CQD

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identidad de la cola de llamadas                     |Texto                     |Nombre de la cuenta de recursos adjunta a la cola de llamadas<br><br>Si se **cq_test@microsoft.com** el nombre completo de la cuenta de recursos, el valor será: **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Descripción de los campos fCallQueueAnalytics CQD

|Nombre                                    |Tipo de datos                |Descripción                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas                                          |
|Resultado de llamadas en cola de llamadas                  |Texto                     |Estado final de la llamada de la cola de llamadas: posibles valores:<br><br>§ agent_joined_conference (llamadas en modo conferencia contestadas)<br>§ rechazada<br>§ desconectado<br>§ error<br>§ Error<br>§ no válido<br>§ desbordamiento (condición de desbordamiento cumplida)<br>§ timed_out (condición de tiempo de espera cumplida)<br>§ transferred_to_agent (llamadas en modo de transcripción contestadas {default}) |
|Identidad de la cola de llamadas                     |Texto                     |Nombre de la cuenta de recursos adjunta a la cola de llamadas<br><br>Si se **cq_test@microsoft.com** el nombre completo de la cuenta de recursos, el valor será: **cq_test** |
|Tipo de destino de la cola de llamadas                  |Texto                     |***Tipo de destino de redireccionamiento de llamadas: posibles valores:***<br><br>§ ApplicationEndpoint<br>§ Buzón<br>§ Otros<br>§ Usuario |
|Tipo<sup>de llamada 1</sup>                   |Texto                     |Tipo de llamada: valores posibles:<br><br>§ Externo<br>§ Interno           |
|Fecha                                    |Fecha y hora                |Fecha y hora de inicio de llamadas de la cola de llamadas (hora) (UTC)                           | 
|IsAbandoned                             |Verdadero/falso               |Verdadero si un agente no responde a la llamada                                   |
|Tipo de conectividad RTC                  |Texto                     |Tipo de llamada: valores posibles:<br><br>§ Llamada externa<br>§ InternalCall   |
|Minutos totales de RTC                      |Número entero             |Resumir: Suma<br>Uso total de minutos para llamadas RTC                       |

#### <a name="fcallqueueanalytics-measures-description"></a>descripción de medidas fCallQueueAnalytics

|Nombre                                    |Tipo de datos                |Descripción                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% de llamadas abandonadas***                 |Porcentaje               |Medida: Número de llamadas abandonadas/llamadas totales    |
|Total de llamadas                             |Número entero             |Medida: el agente de Suma respondió llamadas        |
|TotalCallCount                          |Número entero             |Medida: Suma(Recuento de llamadas)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>descripción de los campos fCallQueueFinalStateAction CQD

|Nombre                                    |Tipo de datos                |Descripción                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Duración media de la llamada (segundos)         |Número decimal           |Resumir: Suma<br>Duración media de la llamada en segundos |
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas                  |
|Resultado de llamadas en cola de llamadas                  |Texto                     |Estado final de llamada de la cola de llamadas: valores posibles:<br><br>§ agent_joined_conference (llamadas en modo conferencia contestadas)<br>§ rechazada<br>§ desconectado<br>§ error<br>§ Error<br>§ no válido<br>§ desbordamiento (condición de desbordamiento cumplida)<br>§ timed_out (condición de tiempo de espera cumplida)<br>§ transferred_to_agent (llamadas en modo de transferencia contestadas {default} |
|Acción de estado final de la cola de llamadas           |Texto                     |Acción final de la cola de llamadas: valores posibles:<br><br>§ Desconectar (llamadas timed_out)<br>§ disconnect_with_busy (llamadas desbordadas)<br>§ failed_to_accept_call<br>§ adelante<br>§ shared_voicemail<br>§ otro<br>§ correo de voz |
|Identidad de la cola de llamadas                     |Texto                     |Nombre de la cuenta de recursos adjunta a la cola de llamadas<br><br>Si se **cq_test@microsoft.com** el nombre completo de la cuenta de recursos, el valor será: **cq_test** |
|Fecha                                    |Fecha y hora                |Fecha y hora de inicio de llamadas de la cola de llamadas (hora) (UTC)   |
|IsAbandoned                             |Verdadero/falso               |Verdadero si un agente no responde a la llamada           |


### <a name="cloud-call-queue-agent-timeline"></a>Escala de tiempo del agente de cola de llamadas en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección informe                                          |Descripción                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# llamadas por agente                                        |Distribución de llamadas por cola de llamadas y agente                 |
|Duración total de llamadas (segundos) por agente y cola de llamadas   |Duración total (segundos) de llamadas por agente y cola de llamadas     |
|Duración media de llamadas (segundos) por nombre de agente           |Duración media (segundos) de llamada por agente                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Informar sobre la tabla y asignación de campos del CQD

|Pestaña Informe         |Nombres de tabla de informe        |Filtro global |
|:------------------|:-------------------------|:-------------|
|Escala de tiempo del agente     |fAgentTimelineAnalytics   |Ninguna          |
 
|Nombre de tabla de informe            |Nombre de la tabla de origen            |Tratamiento       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Changed Type" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration (Minute)", Int64.Type}, {"Average Call Duration (Second)", type number}, {"Date", type date}})|

|Sección informe                                |Campo(s) Utilizados                         |Filtros aplicados       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Nombre del agente                                    |Nombre del agente                            |Ninguna                  |
|Nombre de la cola de llamadas                               |Nombre de la cola de llamadas                       |Ninguna                  |
|#Calls por agente                               |Nombre del agente<br>Recuento de llamadas<br>Fecha      |Ninguna                  |
|Distribución por agente y cola de llamadas          |Nombre del agente<br>Recuento de llamadas<br>Duración de la llamada (minutos)<br>Nombre de la cola de llamadas |Ninguna                      |
|Inferior izquierda                                   |Nombre del agente<br>Duración media de llamadas (segundo)<br>Recuento de llamadas<br>Duración de la llamada (minuto)<br>Nombre de la cola de llamadas | Ninguna |
|Duración media de llamadas (segundos) por nombre de agente |Nombre del agente<br>Duración media de llamadas (segundo)<br>Recuento de llamadas<br>Duración de la llamada (minuto)<br>Nombre de la cola de llamadas | Ninguna |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Descripción de los campos fAgentTimelineAnalytics CQD

|Nombre                                    |Tipo de datos                |Descripción                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nombre del agente                              |Texto                     |UPN de usuario<br>Si se **user@microsoft.com** el nombre de usuario completo, este valor será: **usuario** |
|Duración media de llamadas (segundo)          |Número decimal           |Resumir: Suma<br>Duración media de las llamadas en cola de llamadas respondidas en segundos |
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas que se presentan al agente     |
|Duración de la llamada (minuto)                  |Número entero             |Resumir: Suma<br>Duración total de las llamadas de la cola de llamadas respondidas en minutos (redondeado hacia abajo a los minutos más cercanos)  |
|Nombre de la cola de llamadas                         |Texto                     |Nombre de la cuenta de recursos adjunta a la cola de llamadas<br><br>Si se **cq_test@microsoft.com** el nombre completo de la cuenta de recursos, el valor será: **cq_test** |
|Fecha                                    |Fecha                     |                                                    |


> [!NOTE]
> 1) Este informe muestra el recuento de llamadas desde la perspectiva de los agentes y, por lo tanto, el número total de llamadas de este informe suele ser mayor que el número total de llamadas en el informe análisis de cola de **llamadas** en la nube. Cada llamada de la cola se puede presentar a uno o más agentes al menos una vez antes de que se responda. Todas las llamadas a la cola de llamadas que se presentan a un agente se cuentan en este informe, incluso si el agente no la ha respondido. La diferencia en el recuento de llamadas entre estos dos informes se pronuncia más con la opción de **enrutamiento de Attendant** que suena a cada agente para cada llamada. 
> 2) Cuando una llamada llega por primera vez a la primera cola de llamadas, si el número de llamadas que ya están en esa cola supera el límite de **administración de desbordamiento** de llamadas y si la opción de redirección envía llamadas a una segunda cola de llamadas, los agentes de la segunda cola de llamadas se mostrarán como en la primera cola de llamadas de este informe. 

## <a name="known-issues"></a>Problemas conocidos

- La cola de llamadas y los operadores automáticos se muestran mediante el id. de la cuenta de recursos en lugar de los nombres de la cola de llamadas o los operadores automáticos.  Para mostrar todo el tráfico de un operador automático o de una cola de llamadas, debe seleccionar todas las cuentas de recursos asignadas al operador automático o a la cola de llamadas.

- Solo hay 28 días de historial disponibles en el panel, ya que los datos de la cola de llamadas o del operador automático se consideran datos personales y están sujetos a las directivas de retención de privacidad de datos.

- En algunos casos, el agente respondió el recuento de llamadas en el informe de escala de tiempo del agente de cola de llamadas en la nube puede ser diferente del número de llamadas que se muestra en el Teams historial de llamadas del cliente. El historial de llamadas del cliente Teams es correcto. El soporte técnico se está investigando, pero no hay tiempo estimado para reparar disponible en este momento.

- <sup>1</sup> **La fuente de llamada entrante** en el operador automático y los gráficos de la cola de llamadas muestran el origen final del tramo de llamada en lugar del origen del tramo de llamada inicial. Por ejemplo, si un operador automático recibe una llamada externa y transfiere la llamada a otro operador automático o a la cola de llamadas, el **origen de llamadas entrantes** se notificará como Interno.
