---
title: Uso del informe de Power BI del CQD para ver el Operador automático & histórico de la cola de llamadas
ms.author: colongma
author: clyvr
manager: roykuntz
ms.reviewer: mikedav, siunies, gageames
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar el informe de Power BI del panel de calidad de llamadas para ver el Operador automático y el histórico de colas de llamadas.
ms.openlocfilehash: 16f8682e8f1bc444e2694a0586ff21cf442288cd
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130431"
---
# <a name="what-are-the-requirements"></a>¿Cuáles son los requisitos? 
Debe tener instalado Power BI Desktop. Puede instalarlo desde Microsoft [Windows Store.](https://aka.ms/pbidesktopstore)

Puede usar la versión gratuita de Power BI Desktop. La versión mínima compatible es 2.85.681.0 (septiembre de 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Permisos para obtener acceso a la canalización del CQD
La cuenta que use para ver el informe histórico de AA & CQ Analytics debe tener permisos para tener acceso a la canalización de datos del CQD. Consulte el rol de [acceso del CQD](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) para obtener más información.

## <a name="installation"></a>Instalación 
En los pasos siguientes se supone que ya ha instalado Power BI Desktop en el equipo y que su cuenta tiene los permisos necesarios para obtener acceso a la canalización de datos del CQD.

Realice estos pasos:
- Descargue la plantilla de informes históricos Operador automático & del [CQD Teams](https://aka.ms/TAPAACQAnalytics) y guárdela en un directorio de su equipo.

- Haga doble clic en la plantilla y se iniciará Power BI Desktop.

- Se le pedirá que seleccione la región de canalización de datos del CQD. Seleccione la región donde se encuentra su inquilino.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas en el Centro de administración de Teams":::

 - Puede ver la región con el cmdlet de PS de Skype Empresarial Online (Get-CsTenant). Salida ServiceInstance. 
 La región se mostrará después de /como en este ejemplo: 
 
   microsoftcommunicationsonline/noam-4a-s7 donde la región es noam.
   
 - El informe se iniciará con datos de ejemplo.
 
 - Para ver sus propios datos, haga clic **en Actualizar** en la pestaña Inicio, en Consultas en Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas en el Centro de administración de Teams":::

- A continuación, se le pedirá que inicie sesión. Seleccione **Cuenta de la** organización y, a continuación, seleccione Iniciar **sesión.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas en el Centro de administración de Teams":::

- Seleccione **Conectar y** vea la actualización de datos.

## <a name="data-latency-any-aa--cq-analytics"></a>Latencia de datos: análisis de AA & CQ
Los datos estarán disponibles en la canalización de datos del CQD en un plazo de 30 minutos.

Tendrá que actualizar los datos para ver los nuevos datos de análisis. 

## <a name="customization"></a>Personalización 
Puede personalizar ciertos aspectos de visualización de los informes, como agregar o quitar campos que se mostrarán en las distintas visualizaciones, cambiar el tipo de gráfico, etc.

No puede agregar campos de datos adicionales distintos a los proporcionados en el informe.

### <a name="change-color-schema"></a>Cambiar esquema de color 
En los pasos siguientes se supone que ya ha completado los pasos de instalación.

Realice estos pasos:
- Seleccione **la pestaña Vista** en la cinta de opciones.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas en el Centro de administración de Teams":::

- Seleccione el esquema de color de la lista desplegable.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas en el Centro de administración de Teams":::


## <a name="cqd-fields-description"></a>Descripción de los campos del CQD

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Operador automático identidad                 |cadena                   |Nombre de la cuenta de recursos adjunta a AA<br>Ejemplo: aa_test@microsoft.com|
|Operador automático de inicio en cadena         |datetime                 |Hora de inicio de cadena AA                    |
|Operador automático búsqueda en el directorio  |cadena                   |Último método de búsqueda de la libreta de direcciones        |
|Operador automático acción de transferencia          |cadena                   |Tipo de destino de transferencia de llamadas<br>Valores posibles:<br>§ desconocido : no se ha especificado el tipo de entidad<br>§ usuario - entidad de usuario<br>§ orgaa - Entidad Operador automático organización<br>§ hunt_group - entidad Cola de llamadas<br>§ aplicación - entidad de aplicación de voz<br>§ external_pstn - entidad RTC externa<br>§ shared_voicemail - entidad de correo de voz compartido|
|Operador automático de llamada              |cadena                   |Resultado de la llamada:<br>§ desconocido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|Operador automático de llamadas                |cadena                   |Encapsula los diferentes estados de la llamada Operador automático llamada<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ anuncio|
|Está Operador automático implicado              |Boolean                  |Se indica si AA participa en la llamada |
|Operador automático de acciones del autor de la llamada      |int                      |Recuento de acciones usadas por el autor de la llamada         |
|Operador automático segundos de duración en cadena   |int                      |Duración de la llamada en AA                 |
|Resultado de llamadas en cola de llamadas                  |String                   |Estado final de la llamada en cola de llamadas<br>valores posibles:<br>§ error<br>§ rechazado<br>§ desbordado<br>§ falló<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Acción de estado final de la cola de llamadas           |String                   |Acción final de la cola de llamadas<br>valores posibles:<br>§ reenvío<br>§ desconectar<br>§ correo de voz<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ otros|
|Identidad de la cola de llamadas                     |String                   |Nombre de la cuenta de recursos adjuntada al CQ<br>Ejemplo: aa_test@microsoft.com|
|La cola de llamadas es modo de conferencia           |Boolean                  |Establecer en 1 si el modo de conferencia está habilitado en el CQ |
|Tipo de destino de cola de llamadas                  |String                   |Tipo de destino de redireccionamiento de llamadas esperado     |
|Transferida desde la identidad de la cola de llamadas    |Boolean                  |Nombre de la cuenta de recurso adjuntada al CQ desde la que se ha transferido esta llamada<br>Ejemplo: aa_test@microsoft.com|
|Agente de cola de llamadas que decide participar en Count           |int                      |Número de agentes disponibles para esta cola en el momento de la llamada |
|Call Queue Agent Count                  |int                      |Recuento de agentes asignados a esta cola en el momento de la llamada |
|¿Está involucrada la cola de llamadas?                  |Boolean                  |Si la cola de llamadas participa en esta llamada es igual a 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensiones del modelo de datos de PowerBI

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nombre AA                                   |cadena                   |Operador automático de recursos (Id. de cuenta de recurso) |
|AACallFlow                              |cadena                   |Encapsula los diferentes estados de la llamada Operador automático llamada<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>anuncio |
|AACallResult                            |cadena                   |Resultado de Operador automático llamada:<br>§ desconocido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – error de configuración AA<br>§ service_terminated – errores internos de AA<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |cadena                   |Duración de Operador automático llamada en segundos  |
|AACount                                 |cadena                   |N.º Operador automático participar en la llamada         |
|AADirectorySearchMethod                 |cadena                   |Método de búsqueda usado en la llamada:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |cadena                   |Hora de llamada en UTC                            |
|AATransferAction                        |cadena                   |Receptor de llamada:<br>§ desconocido : no se ha especificado el tipo de entidad<br>§ usuario - entidad de usuario<br>§ AA: entidad Operador automático organización<br>§ CQ : entidad Cola de llamadas<br>§ aplicación - entidad de aplicación de voz<br>§ external_pstn - entidad RTC externa<br>§ shared_voicemail - entidad de correo de voz compartido      |
|PSTNMinutes                             |int                      |Uso total de minutos                          |
|Resultado de llamadas en cola de llamadas                  |cadena                   |Estado final de la llamada en cola de llamadas<br>valores posibles:<br>§ error<br>§ rechazado<br>§ desbordado<br>§ falló<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identidad de la cola de llamadas                     |cadena                   |Nombre de la cuenta de recursos adjuntada al CQ     |
|Tipo de destino de cola de llamadas                  |cadena                   |Tipo de destino de redirección de llamadas esperado:<br>§ Usuario<br>§ Extremo de aplicación<br>§ Otros     |
|Resultado de llamadas en cola de llamadas                  |cadena                   |Estado final de la llamada en cola de llamadas<br>valores posibles:<br>§ error<br>§ rechazado<br>§ desbordado<br>§ falló<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Acción de estado final de la cola de llamadas           |cadena                   |Acción final de la cola de llamadas<br>valores posibles:<br>§ reenvío<br>§ desconectar<br>§ correo de voz<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ otros             |
|Nombre del agente                              |cadena                   |UPN de usuario               |


### <a name="measures"></a>Medidas

|Nombre                                      |Tipo                       |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |N.º de acción seleccionada por el usuario en AA durante la llamada  |
|PSTNMinutes                             |int                      |Uso total de minutos                                  |
|TotalCallCount                          |int                      |N.º de llamadas                                          |
|Duración de llamada media(segundos)         |int                      |Duración total de llamadas en cola de llamadas en segundos     |


### <a name="power-bi-graph-description-auto-attendant"></a>Descripción del gráfico Power BI Operador automático

|Nombre                                      |Descripción                            |
|:---------------------------------------|:--------------------------------------|
|Origen de llamadas entrantes                    |Distribución de llamadas por origen de llamadas interno/externo      |
|Totales de métodos de búsqueda en directorios          |Distribución de la llamada por tipo de búsqueda                         |
|Acción del autor de la llamada                           |Distribución de la llamada por receptor de llamada                       |
|Resultado de la llamada                             |Distribución de la llamada por estado de llamada final                    |
|Recuento de acciones del autor de la llamada                     |Distribución de la llamada por acción de número usada durante la llamada  |


### <a name="call-queue"></a>Cola de llamadas

|Nombre                                      |Descripción                            |
|:---------------------------------------|:--------------------------------------|
|Origen de llamadas entrantes                    |Distribución de llamadas por origen de llamadas interno/externo         |
|Volumen de llamadas                             |Distribución de llamadas por colas de llamadas                            |
|Resultado del autor de la llamada                           |Distribución de llamadas por resultado de llamada                            |
|Acción total de llamada Timeout/Overflow      |Distribución de llamadas NO reenviadas (abandonados) por resultado de llamada   |
|Totales de destino de transferencia o reenvío          |Distribución de llamadas desviadas por resultado de llamada                  |
|Relación de llamadas abandonado                   |Relación de éxito con el recuento de llamadas abandonado                    |
|Duración media de la sesión (segundos)        |Duración de la llamada en segundos agrupadas por llamadas abandonados o con éxito   |



### <a name="agent-timeline"></a>Escala de tiempo del agente

|Nombre                                                      |Descripción                            |
|:-------------------------------------------------------|:--------------------------------------|
|# llamadas por agente                                        |Distribución de llamadas por cola de llamadas y agente                 |
|Duración total de la llamada (segundos) según el agente y la cola de llamadas   |Duración total (segundos) de llamada por agente y cola de llamadas     |
|Duración media de la llamada (segundos) por nombre del agente            |Duración media (segundos) de llamada por agente                  |



## <a name="known-issues"></a>Problemas conocidos
- Actualmente, la cola de llamadas y el operador automático muestran el Id. de cuentas de recursos en lugar de los nombres de la cola de llamadas y de los operadores automáticos.  Para mostrar todo el tráfico de un operador automático o de la cola de llamadas, debe seleccionar todas las cuentas de recursos asignadas al operador automático o a la cola de llamadas.

- Actualmente, solo 28 días de historial está disponible en el panel, ya que los datos de la cola de llamadas y del operador automático se consideran información de identificación del usuario final y está sujeto a las directivas de retención de privacidad de datos.
