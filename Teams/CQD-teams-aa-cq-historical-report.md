---
title: Usar el informe Power BI CQD para ver Operador automático & histórico de cola de llamadas
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
description: Obtenga información sobre cómo usar el panel de calidad de Power BI para ver los datos históricos Operador automático y Cola de llamadas.
ms.openlocfilehash: 844ab5caee23cb504420925c9f13bc261d4d839cce19f7ae557d4637562a963e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331092"
---
# <a name="what-are-the-requirements"></a>¿Cuáles son los requisitos? 
Debe tener Power BI Desktop instalado. Puede instalarlo desde Microsoft [Windows Store.](https://aka.ms/pbidesktopstore)

Puede usar la versión gratuita de Power BI Desktop. La versión mínima compatible es 2.85.681.0 (septiembre de 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Permisos para obtener acceso a la canalización de CQD
La cuenta que usa para ver el informe histórico de AA & CQ Analytics debe tener permisos para obtener acceso a la canalización de datos de CQD. Consulte el rol [de acceso CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para obtener más información.

## <a name="installation"></a>Instalación 
Los pasos siguientes suponen que ya ha instalado Power BI Desktop en el equipo y que su cuenta tiene los permisos necesarios para obtener acceso a la canalización de datos CQD.

Siga estos pasos:
- Descargue la [plantilla CQD Teams Operador automático & informe](./aa-cq-cqd-historical-reports.md) histórico de cola de llamadas y guárdela en un directorio del equipo.

- Haga doble clic en la plantilla y Power BI Desktop iniciar.

- Se le pedirá que seleccione la región de canalización de datos CQD. Seleccione la región donde se encuentra el inquilino.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas Teams centro de administración":::

 - Puede ver la región con el cmdlet Skype Empresarial PS en línea (Get-CsTenant). Resultado de ServiceInstance. 
 La región se mostrará después del /me gusta en este ejemplo: 
 
   microsoftcommunicationsonline/noam-4a-s7 donde la región es noam.
   
 - El informe se iniciará con datos de ejemplo.
 
 - Para ver sus propios datos, haga clic en **Actualizar** en la pestaña Inicio en Consultas en Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas Teams centro de administración":::

- A continuación, se le pedirá que inicie sesión. Seleccione **Cuenta de la organización** y, a continuación, seleccione Iniciar **sesión.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas Teams centro de administración":::

- Seleccione **Conectar** y vea la actualización de datos.

## <a name="data-latency-any-aa--cq-analytics"></a>Latencia de datos Cualquier AA & análisis de CQ
Los datos estarán disponibles en la canalización de datos CQD en un plazo de 30 minutos.

Tendrá que actualizar los datos para ver los nuevos datos de análisis. 

## <a name="customization"></a>Personalización 
Puede personalizar determinados aspectos de visualización de los informes, como agregar o quitar campos que se mostrarán en las distintas visualizaciones, cambiar el tipo de gráfico, etc.

No puede agregar campos de datos adicionales distintos de los proporcionados en el informe.

### <a name="change-color-schema"></a>Cambiar esquema de color 
En los pasos siguientes se supone que ya ha completado los pasos de instalación.

Siga estos pasos:
- Seleccione **la pestaña Vista** en la cinta de opciones.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas Teams centro de administración":::

- Seleccione el esquema de color de la lista desplegable.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas Teams centro de administración":::


## <a name="cqd-fields-description"></a>Descripción de campos CQD

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Operador automático identidad                 |cadena                   |Nombre de la cuenta de recursos adjunta a AA<br>Ejemplo: aa_test@microsoft.com|
|Operador automático hora de inicio de cadena         |datetime                 |Hora de inicio de la cadena AA                    |
|Operador automático de búsqueda de directorios  |cadena                   |Método de búsqueda de la última libreta de direcciones        |
|Operador automático acción Transferir          |cadena                   |Tipo de destino de transferencia de llamadas<br>Valores posibles:<br>§ desconocido: no se especificó el tipo de entidad<br>§ usuario: entidad de usuario<br>§ orgaa: entidad Operador automático organización<br>§ hunt_group : entidad Cola de llamadas<br>§ aplicación: entidad de aplicación de voz<br>§ external_pstn - entidad RTC externa<br>§ shared_voicemail: entidad de correo de voz compartido|
|Operador automático de llamada              |cadena                   |Resultado de la llamada:<br>§ desconocido: la llamada no se pudo configurar o transferir y el servicio no ha recibido ningún motivo de error significativo <br>§ transferred_to_user: llamada transferida a un usuario a través de Marcado por nombre/extensión o opción de menú configurada <br>§ transferred_to_operator: la llamada se ha transferido a un operador configurado, por ejemplo, si AA está configurado con un operador para fuera del horario laboral <br>§ failover_to_operator- Reserva al operador cuando se produce un error en la transferencia o el reconocimiento de nombres no funciona después de tres intentos<br>§ user_terminated: el autor de la llamada ha finalizado la llamada <br>§ service_declined: la llamada rechazada por el servicio, esto podría ocurrir si el servicio no obtiene Operador automático configuración <br>§ service_terminated: el servicio back-end rescindió la llamada, posiblemente si se ha fallado una transferencia al destino y ningún operador está configurado como reserva. <br>§ failed_to_establish_media: error en el establecimiento multimedia entre la persona que llama y el servicio <br>§ terminated_no_operator: el reconocimiento de nombres falló después de tres intentos y no se configuró ningún operador <br>§ terminated_transfer_failed: error en la transferencia al destino y no se configura ningún operador <br>§ terminated_automatic_selection: si no se configura ninguna acción durante o fuera del horario laboral, la llamada finalizará de forma predeterminada <br>§ transferred_to_shared_voicemail: llamada transferida al correo de voz compartido si está configurada como destino <br>§ oaa_chain_too_long: cuando una cadena de Operador automático supera los cinco Operadores automáticos seguidos, la llamada finalizará para evitar posibles bucles de llamada <br>§ oaa_session_too_long: la llamada superó la duración máxima de la sesión permitido y ha superado el tiempo de espera. |
|Operador automático llamada Flow                |cadena                   |Encapsula los distintos estados de Operador automático llamada<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>Anuncio de §|
|Está Operador automático implicado              |Boolean                  |Se indica si AA participa en la llamada |
|Operador automático de acciones de llamada      |int                      |Recuento de acciones usadas por el autor de la llamada         |
|Operador automático duración de cadena segundos   |int                      |Duración de la llamada en AA                 |
|Resultado de la llamada en cola de llamadas                  |String                   |Estado final de la llamada de cola de llamadas<br>valores posibles:<br>Error de §<br>§ rechazado<br>§ desbordado<br>Error en el §<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Acción de estado final de la cola de llamadas           |String                   |Acción final de la cola de llamadas<br>valores posibles:<br>§ hacia delante<br>§ desconectar<br>§ correo de voz<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ otros|
|Identidad de cola de llamadas                     |String                   |Nombre de la cuenta de recursos adjunta a CQ<br>Ejemplo: aa_test@microsoft.com|
|Cola de llamadas es modo de conferencia           |Boolean                  |Establecer en 1 si el modo de conferencia está habilitado en CQ |
|Tipo de destino de cola de llamadas                  |String                   |Tipo de destino de redireccionamiento de llamadas esperado     |
|Transferido de la identidad de la cola de llamadas    |Boolean                  |Nombre de la cuenta de recursos adjunta a CQ desde la que se ha transferido esta llamada<br>Ejemplo: aa_test@microsoft.com|
|Agente de cola de llamadas opta por contar           |int                      |Recuento de agentes disponibles para esta cola en el momento de la llamada |
|Recuento de agentes de cola de llamadas                  |int                      |Recuento de agentes asignados a esta cola en el momento de la llamada |
|¿Está involucrada la cola de llamadas?                  |Boolean                  |Si la cola de llamadas está involucrada en esta llamada es igual a 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensiones del modelo de datos PowerBI

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nombre AA                                   |cadena                   |Operador automático (id. de cuenta de recurso) |
|AACallFlow                              |cadena                   |Encapsula los distintos estados de Operador automático llamada<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>anuncio |
|AACallResult                            |cadena                   |Resultado de Operador automático llamada:<br>§ desconocido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined: error de configuración de AA<br>§ service_terminated: errores internos de AA<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |cadena                   |Duración de Operador automático llamada en segundos  |
|AACount                                 |cadena                   |# de Operador automático participar en la llamada         |
|AADirectorySearchMethod                 |cadena                   |Método de búsqueda usado en la llamada:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |cadena                   |Hora de llamada en UTC                            |
|AATransferAction                        |cadena                   |Receptor de llamada:<br>§ desconocido: no se especificó el tipo de entidad<br>§ usuario: entidad de usuario<br>§ AA: entidad Operador automático organización<br>§ CQ : entidad Cola de llamadas<br>§ aplicación: entidad de aplicación de voz<br>§ external_pstn - entidad RTC externa<br>§ shared_voicemail: entidad de correo de voz compartido      |
|RTCMinutes                             |int                      |Uso total de minutos                          |
|Resultado de la llamada en cola de llamadas                  |cadena                   |Estado final de la llamada de cola de llamadas<br>valores posibles:<br>Error de §<br>§ rechazado<br>§ desbordado<br>Error en el §<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identidad de cola de llamadas                     |cadena                   |Nombre de la cuenta de recursos adjunta a CQ     |
|Tipo de destino de cola de llamadas                  |cadena                   |Tipo de destino de redireccionamiento de llamadas esperado:<br>§ Usuario<br>§ Punto de conexión de aplicación<br>§ Otros     |
|Resultado de la llamada en cola de llamadas                  |cadena                   |Estado final de la llamada de cola de llamadas<br>valores posibles:<br>Error de §<br>§ rechazado<br>§ desbordado<br>Error en el §<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Acción de estado final de la cola de llamadas           |cadena                   |Acción final de la cola de llamadas<br>valores posibles:<br>§ hacia delante<br>§ desconectar<br>§ correo de voz<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ otros             |
|Nombre del agente                              |cadena                   |UPN de usuario               |


### <a name="measures"></a>Medidas

|Nombre                                      |Tipo                       |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |# de acción seleccionada por el usuario en AA durante la llamada  |
|RTCMinutes                             |int                      |Uso total de minutos                                  |
|TotalCallCount                          |int                      |# de llamadas                                          |
|Duración media de la llamada( segundos)         |int                      |Duración total de las llamadas en cola de llamadas en segundos     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI de gráfico Operador automático

|Nombre                                      |Descripción                            |
|:---------------------------------------|:--------------------------------------|
|Origen de llamadas entrantes                    |Distribución de llamadas por origen de llamadas internos o externos      |
|Totales de métodos de búsqueda de directorios          |Distribución de llamadas por tipo de búsqueda                         |
|Acción de autor de llamadas                           |Distribución de llamadas por receptor de llamadas                       |
|Resultado de la llamada                             |Distribución de llamadas por estado de llamada final                    |
|Recuento de acciones de llamada                     |Distribución de la llamada por acción de número usada durante la llamada  |


### <a name="call-queue"></a>Cola de llamadas

|Nombre                                      |Descripción                            |
|:---------------------------------------|:--------------------------------------|
|Origen de llamadas entrantes                    |Distribución de llamadas por origen de llamadas internos o externos         |
|Volumen de llamadas                             |Distribución de las colas de llamadas por llamada                            |
|Resultado del autor de la llamada                           |Distribución del resultado de llamada por llamada                            |
|Acción total de llamada de tiempo de espera/desbordamiento      |Distribución de llamadas NO reenviadas (abandonados) por el resultado de la llamada   |
|Transferir o reenviar totales de destino          |Distribución de llamadas reenviadas por resultado de llamada                  |
|Relación de llamadas abandonadas                   |Relación de éxito a recuento de llamadas abandonado                    |
|Duración media de la sesión (segundos)        |Duración de la llamada en segundos agrupadas por llamadas desasistidos o correctas   |



### <a name="agent-timeline"></a>Escala de tiempo del agente

|Nombre                                                      |Descripción                            |
|:-------------------------------------------------------|:--------------------------------------|
|# llamadas por agente                                        |Distribución de llamadas por cola de llamadas y agente                 |
|Duración total de la llamada (segundos) por agente y Cola de llamadas   |Duración total (segundos) de llamada por agente y cola de llamadas     |
|Duración media de la llamada (segundos) por nombre del agente            |Duración media (segundos) de llamada por agente                  |



## <a name="known-issues"></a>Problemas conocidos
- Actualmente, la cola de llamadas y el operador automático muestran el id. de cuentas de recursos en lugar de los nombres de cola de llamadas o operadores automáticos.  Para mostrar todo el tráfico de un operador automático o cola de llamadas, debe seleccionar todas las cuentas de recursos asignadas al operador automático o a la cola de llamadas.

- Actualmente, solo 28 días de historial está disponible en el panel, ya que los datos de cola de llamadas o operador automático se consideran información de identificación del usuario final y están sujetos a directivas de retención de privacidad de datos.
