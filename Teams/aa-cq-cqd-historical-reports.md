---
title: Operador automático & histórico de cola de llamadas
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
description: Obtenga información sobre cómo usar el panel de calidad de Power BI para ver los datos históricos Operador automático y Cola de llamadas.
ms.openlocfilehash: 22c2152401cd9ec08ae1fbad2bbd42eb29fc0726
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457240"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Operador automático & histórico de cola de llamadas

La Teams Operador automático & histórico de cola de Power BI de llamadas proporciona los tres informes siguientes:

- [Operador automático](media/cqd-teams-aa-cq-historical-report-sample-aa.png) : muestra análisis de las llamadas que llegan a los Operadores automáticos.
- [Cola de llamadas](media/cqd-teams-aa-cq-historical-report-sample-cq.png) : muestra análisis de las llamadas que llegan a las colas de llamadas.
- [Escala de tiempo del](media/cqd-teams-aa-cq-historical-report-sample-at.png) agente: muestra una vista de escala de tiempo de los agentes que están activos en las llamadas de cola de llamadas.

Estos informes usan datos del almacén de datos Panel [de calidad de](CQD-Power-BI-query-templates.md) llamadas. Los informes permiten a las organizaciones informar sobre el número de llamadas que están procesando los operadores automáticos y las colas de llamadas.  Los informes también proporcionan información sobre el rendimiento del agente en las colas de llamadas.

## <a name="prerequisites"></a>Requisitos previos

### <a name="power-bi-desktop"></a>Power BI Desktop
Debe tener Power BI Desktop instalado. Puede instalarlo desde Microsoft [Windows Store](https://aka.ms/pbidesktopstore).

Puede usar la versión gratuita de Power BI Desktop. La versión mínima compatible es 2.85.681.0 (septiembre de 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Permisos para obtener acceso a la canalización de CQD

La cuenta que use para ver el informe histórico debe tener permisos para obtener acceso a la canalización de datos de CQD. Para obtener más información, vea [Rol de acceso CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="installation"></a>Instalación 

Los pasos siguientes suponen que ya ha instalado Power BI Desktop en el equipo y que su cuenta tiene los permisos necesarios para obtener acceso a la canalización de datos CQD.

Realice los pasos siguientes:

- Descargue el [archivo CQD Power BI de consulta](https://www.microsoft.com/download/details.aspx?id=102291) y guarde el archivo zip en un directorio del equipo.

- Haga doble clic en el archivo zip para abrirlo.

- Haga doble clic en el archivo de plantilla "CQ y AA combined Analytics 20201105.pbit". El Power BI Desktop debe iniciarse.

- Se le pedirá que seleccione la región de canalización de datos CQD. Seleccione la región donde se encuentra el inquilino.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de pantalla que selecciona la región de canalización de datos de CQD.":::

- La región donde se encuentra el espacio empresarial se puede obtener mediante el cmdlet [Get-CsTenant](/powershell/module/skype/get-cstenant) .

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - La región se mostrará después del **/** ejemplo como en el ejemplo anterior donde hay una región: noam

 - El informe se iniciará con datos de ejemplo.
 
 - Para ver sus propios datos, seleccione **Actualizar en** la pestaña Inicio en Consultas en Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de pantalla que selecciona la opción de actualización.":::

- A continuación, se le pedirá que inicie sesión. Seleccione **Cuenta de organización** y, a continuación, **seleccione Iniciar sesión**.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de pantalla que muestra el inicio de sesión.":::

- Seleccione **Conectar** y vea la actualización de datos.

## <a name="data-latency-and-aa--cq-analytics"></a>Latencia de datos y AA & análisis de CQ

Los datos estarán disponibles en la canalización de datos CQD en un plazo de 30 minutos.

Tendrá que actualizar los datos para ver los nuevos datos de análisis. 

## <a name="customization"></a>Personalización 

Puede personalizar determinados aspectos de visualización de los informes, como agregar o quitar campos que se mostrarán en las distintas visualizaciones, cambiar el tipo de gráfico, y así sucesivamente.

No puede agregar campos de datos adicionales al informe.

### <a name="change-color-schema"></a>Cambiar esquema de color 

Los pasos siguientes suponen que ya ha completado los pasos de instalación.

Realice los pasos siguientes:
- Seleccione **la pestaña Vista** en la cinta de opciones.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de pantalla seleccionando la pestaña vista para cambiar la combinación de colores.":::

- Seleccione el esquema de color de la lista desplegable.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Captura de pantalla que muestra varias combinación de colores.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Operador automático y definiciones de informes históricos de cola de llamadas

### <a name="cloud-auto-attendant-analytics"></a>Cloud Operador automático Analytics

#### <a name="report-description"></a>Descripción del informe

|Sección Informe                          |Descripción                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Origen de llamadas <sup>entrantes1</sup>        |Distribución de llamadas por origen de llamadas internos/externos             |
|Totales de métodos de búsqueda de directorios          |Distribución de llamadas por tipo de búsqueda                               |
|Acción de autor de llamadas                           |Distribución de llamadas por receptor de llamadas                             |
|Resultado de la llamada                             |Distribución de llamadas por estado de llamada final                          |
|Recuento de acciones de llamada                     |Distribución de llamadas por acción de número usada durante la llamada        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Informar a la tabla CQD y la asignación de campos

|Pestaña Informe            |Nombre de tabla de informe     |Filtro global                          |
|:---------------------|:---------------------|:--------------------------------------|
|Operador automático        |fAutoAttendant        |AAStartTime está dentro de los últimos 28 días |


|Nombre de tabla de informe            |Nombre de tabla de origen            |Procesamiento       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |Autoattendant                |Source = AutoAttendant, <br>#"Filas filtradas" = Table.SelectRows(Source, each true), <br>#"Operador automático" = Table.AddColumn(#"Filas filtradas", "Nombre AA", cada lista.First(Text.Split([AAIdentity], "@"))), <br>#"Tipo cambiado" = Table.TransformColumnTypes(#"Operador automático",{{{"AAStartTime", escriba datetime}}), <br>#"Columnas eliminadas" = Table.RemoveColumns(#"Tipo cambiado",{"AAIdentity"}) |


|Sección Informe                                  |Campos usados                              |Filtros aplicados     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Selector de fecha                                   |AAStartTime                                |Ninguna                |
|Operador automático                                  |Nombre AA                                    |Ninguna                |
|Origen de llamadas <sup>entrantes1</sup>                |Tipo de llamada<br>TotalCallCount                |Llamadas externas: el tipo de llamada es Externo<br>Llamadas internas: el tipo de llamada es Interno |
|Totales de métodos de búsqueda de directorios                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod es abs_search_dtmf o abs_search_name    |
|Acciones del autor de la llamada                                  |AATransferAction<br>TotalCallCount         |Ninguna                                                             |
|Promedio de segundos en AA<br>Promedio de acciones de llamada |AAChainDuration<br>AACallerActionCount     |Ninguna                                                             |
|Resultados de la llamada                                    |AACallResult<br>TotalCallCount             |Ninguna                                                             |
|Recuento de acciones de llamada                            |AACallerActionCount<br>TotalCallCount      |Ninguna                                                             |
|Sección inferior del informe                         |Nombre AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Tipo de llamada<br>TotalCallCount |Ninguna                |

#### <a name="fautoattendant-cqd-fields-description"></a>descripción de campos CQD de fAutoAttendant

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nombre AA                                 |Texto                     |Nombre de la cuenta de recursos adjunta a Operador automático<br><br>Si el nombre completo de la cuenta de **recursos aa_test@microsoft.com** , este valor será: **aa_test** |
|AACallerActionCount                     |Número entero             |Resumir: Suma<br>Recuento de acciones seleccionadas por el autor de la llamada Operador automático durante la llamada  |
|AACallFlow                              |Texto                     |Encapsula los distintos estados de Operador automático llamada: valores posibles:<br><br>§ abs_search<br>Anuncio de §<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Texto                     |Resultado final de la llamada: posibles valores:<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ desconocido<br>§ user_terminated |
|AAChainDuration                         |Número decimal           |Resumir: Suma<br>Duración de la llamada en Operador automático                     |
|AAChainIndex                            |Texto                     |                                                                         |
|AAConnectivityType                      |Texto                     |Tipo de llamada: valores posibles:<br><br>§ ExternalCall<br>§ Llamada interna |
|AACount                                 |Texto                     |Número de operadores automáticos implicados en la llamada                               |
|AADirectorySearchMethod                 |Texto                     |Método de búsqueda de la última libreta de direcciones: valores posibles:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |Fecha y hora                |Operador automático hora de inicio de llamada                                           |
|AATransferAction                        |Texto                     |Tipo de destino de transferencia de llamadas: posibles valores:<br><br>***§ aplicación - entidad de aplicación** _<br>de voz§ external_pstn<br>_*_§ hunt_group - Entidad cola_*_<br>_* de llamadas _§ orgaa - Entidad Operador automático organización_**<br>§ shared_voicemail<br>§ desconocido<br>§ usuario |
|Tipo de <sup>llamada1</sup>                   |Texto                     |Tipo de llamada: valores posibles:<br><br>§ Externo<br>§ Interno         |
|IsAAInvolved                            |Texto                     |Siempre 1                                                                 |
|RTCMinutes                             |Número entero             |Resumir: Suma<br>Uso total de minutos                                     |
|TotalCallCount                          |Número entero             |Resumir: Suma<br>Siempre 1: se usa para proporcionar la suma de todas las llamadas            |


### <a name="cloud-call-queue-analytics"></a>Análisis de cola de llamadas en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección Informe                          |Descripción                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Origen de llamadas <sup>entrantes1</sup>        |Distribución de llamadas por origen de llamada interno/externo              |
|Volumen de llamadas                             |Distribución de las colas de llamadas por llamada                                |
|Resultado del autor de la llamada                           |Distribución del resultado de llamada por llamada                                |
|Acción total de llamada de tiempo de espera/desbordamiento      |Distribución de llamadas NO reenviadas (abandonados) por el resultado de la llamada       |
|Transferir o reenviar totales de destino          |Distribución de llamadas reenviadas por resultado de llamada                      |
|Relación de llamadas abandonadas                   |Relación de éxito a recuento de llamadas abandonado                        |
|Duración media de la sesión (segundos)        |Duración de la llamada en segundos agrupadas por llamadas desasistidos o correctas       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Informar a la tabla CQD y la asignación de campos

|Pestaña Informe         |Nombres de tabla de informe                                                          |Filtro global |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|Cola de llamadas         |Fechas<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |Ninguna          |
 
|Nombre de tabla de informe            |Nombre de tabla de origen            |Procesamiento       |
|:----------------------------|:----------------------------|:----------------|
|Fechas                        |Fechas                        |Ninguna             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Columnas eliminadas" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Call Result", "Date", "PSTN Connectivity Type", "Call Queue Target Type", "PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Columnas eliminadas") |
|fCallQueueAnalytics          |CallQueueAnalytics           |Ninguna             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |Ninguna             |

|Sección Informe                      |Tabla -> campos usados                |Filtros aplicados       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Selector de fecha                       |Dates -> DateTime                     |Ninguna                  |
|Identidad de cola de llamadas                 |dCQ-CQIdentity -> de cola de llamadas |Ninguna                  |
|Origen de llamadas <sup>entrantes1</sup>    |fCallQueueAnalytics -> recuento de llamadas<br>fCallQueueAnalytics -> de llamada    |Llamadas externas: el tipo de llamada es Externo<br>Llamadas internas: el tipo de llamada es Interno |
|Tiempo medio de espera                    |fCallQueueFinalStateAction -> duración media de la llamada (segundos) |Antes de transferir: el resultado de la llamada de cola de llamadas agent_joined_conference o transferred_to_agent<br>Antes de colgar: el resultado de la llamada de cola de llamadas no agent_joined_conference o transferred_to_agent |
|Resultado de la llamada                         |fCallQueueAnalytics -> recuento de llamadas<br>fCallQueueAnalytics -> de llamada de cola de llamadas | Ninguna |
|Acción total de llamadas de tiempo de espera/desbordamiento |fCallQueueFinalStateAction -> call count<br>fCallQueueFinalStateAction -> acción de estado final de la cola de llamadas |La acción de estado final de la cola de llamadas no se reenvía |
|Totales de destino de Transferencia/Forard       |fCallQueueAnalytics -> recuento de llamadas<br>fCallQueueAnalytics -> de destino de cola de llamadas |Ninguna |
|Volúmenes de llamadas                        |fCallQueueAnalytics -> recuento de llamadas<br>fCallQueueAnalytics -> de cola de llamadas<br>fCallQueueAnalytics -> fecha |Ninguna |
|Llamadas abandonadas                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics -> recuento de llamadas<br>fCallQueueAnalytics -> fecha<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned es Verdadero |
|Duración media de la sesión (segundos)    |fCallQueueFinalStateAction -> duración media de la llamada<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |Ninguna |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>dCQ-CQIdenity CQD descripción de campos CQD

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identidad de cola de llamadas                     |Texto                     |Nombre de la cuenta de recursos adjunta a cola de llamadas<br><br>Si el nombre completo de la cuenta de **recursos cq_test@microsoft.com** , este valor será: **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>descripción de los campos CQD de fCallQueueAnalytics

|Nombre                                    |Tipo de datos                |Descripción                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas                                          |
|Resultado de la llamada en cola de llamadas                  |Texto                     |Estado final de la llamada de cola de llamadas: posibles valores:<br><br>§ agent_joined_conference<br>§ rechazado<br>§ desconectado<br>Error de §<br>Error en el §<br>§ no válido<br>§ desbordado<br>§ timed_out<br>§ transferred_to_agent |
|Identidad de cola de llamadas                     |Texto                     |Nombre de la cuenta de recursos adjunta a cola de llamadas<br><br>Si el nombre completo de la cuenta de **recursos cq_test@microsoft.com** , este valor será: **cq_test** |
|Tipo de destino de cola de llamadas                  |Texto                     |***Tipo de destino de redireccionamiento de llamadas: posibles valores:***<br><br>§ ApplicationEndpoint<br>§ Buzón<br>§ Otros<br>§ Usuario |
|Tipo de <sup>llamada1</sup>                   |Texto                     |Tipo de llamada: valores posibles:<br><br>§ Externo<br>§ Interno           |
|Fecha                                    |Fecha y hora                |Fecha y hora de inicio de la llamada en cola de llamadas (hora UTC)                           | 
|IsAbandoned                             |Verdadero/falso               |Verdadero si un agente no responde a la llamada                                   |
|Tipo de conectividad RTC                  |Texto                     |Tipo de llamada: valores posibles:<br><br>§ ExternalCall<br>§ Llamada interna   |
|Minutos totales RTC                      |Número entero             |Resumir: Suma<br>Uso total de minutos para llamadas RTC                       |

#### <a name="fcallqueueanalytics-measures-description"></a>descripción de las medidas de fCallQueueAnalytics

|Nombre                                    |Tipo de datos                |Descripción                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% de llamadas abandonadas***                 |Porcentaje               |Medida: TotalCallCount / Total Calls<br>Relación de éxito a recuento de llamadas abandonado    |
|Total de llamadas                             |Número entero             |Medida: Agente de suma respondió llamadas        |
|TotalCallCount                          |Número entero             |Medida: Suma(recuento de llamadas)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction Descripción de campos CQD

|Nombre                                    |Tipo de datos                |Descripción                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Duración media de la llamada (segundos)         |Número decimal           |Resumir: Suma<br>Duración media de la llamada en segundos |
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas                  |
|Resultado de la llamada en cola de llamadas                  |Texto                     |Estado final de la llamada de cola de llamadas: posibles valores:<br><br>§ agent_joined_conference<br>§ rechazado<br>§ desconectado<br>Error de §<br>Error en el §<br>§ no válido<br>§ desbordado<br>§ timed_out<br>§ transferred_to_agent |
|Acción de estado final de la cola de llamadas           |Texto                     |Acción final de cola de llamadas: posibles valores:<br><br>§ desconectar (timed_out llamadas)<br>§ disconnect_with_busy (llamadas desbordadas)<br>§ failed_to_accept_call<br>§ hacia delante<br>§ shared_voicemail<br>§ otros<br>§ correo de voz |
|Identidad de cola de llamadas                     |Texto                     |Nombre de la cuenta de recursos adjunta a cola de llamadas<br><br>Si el nombre completo de la cuenta de **recursos cq_test@microsoft.com** , este valor será: **cq_test** |
|Fecha                                    |Fecha y hora                |Fecha y hora de inicio de la llamada en cola de llamadas (hora UTC)   |
|IsAbandoned                             |Verdadero/falso               |Verdadero si un agente no responde a la llamada           |


### <a name="cloud-call-queue-agent-timeline"></a>Escala de tiempo del agente de cola de llamadas en la nube

#### <a name="report-description"></a>Descripción del informe

|Sección Informe                                          |Descripción                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# llamadas por agente                                        |Distribución de llamadas por cola de llamadas y agente                 |
|Duración total de la llamada (segundos) por agente y Cola de llamadas   |Duración total (segundos) de llamada por agente y cola de llamadas     |
|Duración media de la llamada (segundos) por nombre del agente           |Duración media (segundos) de llamada por agente                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Informar a la tabla CQD y la asignación de campos

|Pestaña Informe         |Nombres de tabla de informe        |Filtro global |
|:------------------|:-------------------------|:-------------|
|Escala de tiempo del agente     |fAgentTimelineAnalytics   |Ninguna          |
 
|Nombre de tabla de informe            |Nombre de tabla de origen            |Procesamiento       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Tipo cambiado" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration (Minute)", Int64.Type}, {"Average Call Duration (Second)", type number}, {"Date", type date}})|

|Sección Informe                                |Campos usados                         |Filtros aplicados       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Nombre del agente                                    |Nombre del agente                            |Ninguna                  |
|Nombre de cola de llamadas                               |Nombre de cola de llamadas                       |Ninguna                  |
|#Calls por agente                               |Nombre del agente<br>Recuento de llamadas<br>Fecha      |Ninguna                  |
|Distribución por agente y cola de llamadas          |Nombre del agente<br>Recuento de llamadas<br>Duración de la llamada (minutos)<br>Nombre de cola de llamadas |Ninguna                      |
|Inferior izquierda                                   |Nombre del agente<br>Duración media de la llamada (segundo)<br>Recuento de llamadas<br>Duración de la llamada (minuto)<br>Nombre de cola de llamadas | Ninguna |
|Duración media de la llamada (segundos) por nombre del agente |Nombre del agente<br>Duración media de la llamada (segundo)<br>Recuento de llamadas<br>Duración de la llamada (minuto)<br>Nombre de cola de llamadas | Ninguna |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>descripción de campos CQD de fAgentTimelineAnalytics

|Nombre                                    |Tipo de datos                |Descripción                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nombre del agente                              |Texto                     |UPN de usuario<br>Si el nombre de usuario **completo user@microsoft.com** , este valor será: **usuario** |
|Duración media de la llamada (segundo)          |Número decimal           |Resumir: Suma<br>Duración media de las llamadas en cola de llamadas en segundos |
|Recuento de llamadas                              |Número entero             |Resumir: Suma<br>Número de llamadas que ha manipulado el agente                    |
|Duración de la llamada (minuto)                  |Número entero             |Resumir: Suma<br>Duración total de las llamadas en cola de llamadas en minutos  |
|Nombre de cola de llamadas                         |Texto                     |Nombre de la cuenta de recursos adjunta a cola de llamadas<br><br>Si el nombre completo de la cuenta de **recursos cq_test@microsoft.com** , este valor será: **cq_test** |
|Fecha                                    |Fecha                     |                                                    |


> [!NOTE]
> 1) Este informe muestra los recuentos de llamadas desde la perspectiva de los agentes y, por lo tanto, el total de llamadas de este informe suele ser mayor que el número total de llamadas en el informe análisis de cola de llamadas **en la** nube. Cada llamada de la cola puede presentarse a uno o más agentes al menos una vez antes de que se le conteste. Cada llamada de cola de llamadas que se presenta a un agente se cuenta en este informe, incluso si el agente no la ha respondido. La diferencia en el recuento de llamadas entre estos dos informes es más pronunciada con la  opción de enrutamiento del operador, que llama a todos los agentes para cada llamada. 
> 2) Cuando una llamada llega por primera vez a la primera cola de llamadas, si el número de llamadas que ya están en espera  en esa cola supera el límite de administración de desbordamiento de llamadas y si la opción redirigir envía llamadas a una segunda cola de llamadas, los agentes de la segunda cola de llamadas se mostrarán como en la primera cola de llamadas de este informe. 

## <a name="known-issues"></a>Problemas conocidos

- La cola de llamadas y los operadores automáticos se muestran mediante el id. de la cuenta de recursos en lugar de los nombres de cola de llamadas o operadores automáticos.  Para mostrar todo el tráfico de un operador automático o una cola de llamadas, debe seleccionar todas las cuentas de recursos asignadas al operador automático o a la cola de llamadas.

- Solo 28 días de historial están disponibles en el panel, ya que los datos de cola de llamadas o operador automático se consideran datos personales y están sujetos a directivas de retención de privacidad de datos.

- En algunos escenarios, el recuento de llamadas contestadas por el agente en el informe de escala de tiempo del agente de cola de llamadas en la nube puede ser diferente del número de llamadas que se muestran en el historial de llamadas de Teams cliente. El Teams de llamadas del cliente es correcto. El soporte técnico está investigando, pero no hay tiempo estimado para reparar disponible en este momento.

- <sup>1 El origen</sup> **de llamadas** entrantes en los gráficos de operador automático y cola de llamadas muestra el origen final del tramo de llamada en lugar del origen inicial del tramo de llamada. Por ejemplo, si un operador automático recibe una llamada externa y transfiere la llamada a otro operador automático o cola de llamadas,  el origen de llamadas entrantes se notifica como Interno.
