---
title: Operador automático & informe histórico de la cola de llamadas
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: Obtenga información sobre cómo usar el informe de Power BI del panel de calidad de llamadas para ver los datos históricos de la cola de llamadas y el operador automático.
ms.openlocfilehash: 23d9f9db7668195bba4e964e8c5ac5607038f197
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085721"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Operador automático & informe histórico de la cola de llamadas

El operador automático de equipos del CQD & plantilla de Power BI para la cola de llamadas proporciona los tres informes siguientes:

- Operador automático: muestra análisis de llamadas entre los operadores automáticos.
- Cola de llamadas: muestra análisis para las llamadas que llegan a las colas de llamadas.
- Escala de tiempo del agente: muestra la vista de la escala de tiempo de los agentes que se activan en llamadas a colas de llamadas.

Estos informes usan datos del almacén de datos del [Panel de calidad de llamadas](CQD-Power-BI-query-templates.md) y permiten que las organizaciones notifiquen el número de llamadas que procesan los operadores automáticos y las colas de llamadas, así como el rendimiento del agente en las colas de llamadas.

## <a name="what-are-the-requirements"></a>¿Cuáles son los requisitos? 

Debe tener instalado Power BI Desktop. Puede instalarlo desde la [tienda de Microsoft Windows](https://aka.ms/pbidesktopstore).

Puede usar la versión gratuita de Power BI Desktop. La versión mínima compatible es 2.85.681.0 (2020 de septiembre).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Permisos para acceder a la canalización de CQD

La cuenta que use para ver el informe histórico de AA & analítica de CQ debe tener permisos de acceso a la canalización de datos del CQD. Para obtener más información, consulta la [función acceso del CQD](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) .

## <a name="installation"></a>Instalación 

En los pasos siguientes se da por supuesto que ya tiene instalado Power BI Desktop en el equipo y que la cuenta tiene los permisos necesarios para acceder a la canalización de datos CQD.

Siga estos pasos:
- Descargue las [plantillas de consulta de Power BI del CQD](https://www.microsoft.com/download/details.aspx?id=102291) y guarde el archivo zip en un directorio de su equipo.
- Haga doble clic en el archivo zip para abrirlo.
- Haga doble clic en el archivo de plantilla "CQ y AA Analytics 20201105. PBit" y Power BI Desktop debe iniciarse.
- Se le pedirá que seleccione la región de canalización de datos CQD. Seleccione la región donde se encuentra el inquilino.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de pantalla que selecciona la región de canalización datos CQD":::

 - Puede ver la región mediante el cmdlet de Skype empresarial online PS (get-CsTenant). Resultado de ServiceInstance. 
 La región se mostrará después de la/like en este ejemplo: microsoftcommunicationsonline/Noam-4A-S7 donde la región es Noam.
 - El informe se iniciará con datos de ejemplo.
 - Para ver sus propios datos, haga clic en **Actualizar** en la pestaña Inicio en consultas en Power BI Desktop.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de pantalla que selecciona la opción actualizar":::

- Se le pedirá que inicie sesión. Seleccione **cuenta** de la organización y, después, haga clic **en iniciar sesión**.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de pantalla que muestra inicio de sesión":::

- Seleccione **conectar** y vea la actualización de datos.

## <a name="data-latency-and-aa--cq-analytics"></a>Latencia de datos y análisis AA & CQ

Los datos estarán disponibles en la canalización de datos del CQD en un plazo de 30 minutos.

Tendrá que actualizar los datos para ver los nuevos datos de análisis. 

## <a name="customization"></a>Personalización 

Puede personalizar determinados aspectos de visualización de los informes, como agregar o quitar campos para mostrarlos en las diversas visualizaciones, cambiar el tipo de gráfico, etc.

No puede agregar campos de datos adicionales que no sean los proporcionados en el informe.

### <a name="change-color-schema"></a>Cambiar esquema de color 

En los pasos siguientes se supone que ya ha completado los pasos de instalación.

Siga estos pasos:
- Seleccione la **pestaña vista** en la cinta de opciones.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de pantalla que selecciona la pestaña vista para cambiar la combinación de colores":::

- Seleccione el esquema de color en la lista desplegable.

## <a name="cqd-fields-description"></a>Descripción de los campos CQD

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identidad de operador automático                 |tipo                   |Nombre de la cuenta de recursos adjunta a AA<br>Ejemplo: aa_test@microsoft.com|
|Hora de inicio de la cadena de operador automático         |datetime                 |Hora de inicio de la cadena de AA                    |
|Método de búsqueda de directorio de operador automático  |tipo                   |Último método de búsqueda de libretas de direcciones        |
|Acción de transferencia automática del operador          |tipo                   |Tipo de destino de transferencia de llamadas<br>valores posibles:<br>§ desconocido: no se especificó el tipo de entidad<br>§ usuario-entidad usuario<br>§ orgaa-entidad de operador automático organizacional<br>§ hunt_group: entidad de cola de llamadas<br>§ aplicación-entidad de la aplicación de voz<br>§ external_pstn entidad de RTC externa<br>§ shared_voicemail-entidad de buzón de voz compartido|
|Resultado de la llamada de operador automático              |tipo                   |Resultado de la llamada:<br>§ desconocido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|Flujo de llamadas de operador automático                |tipo                   |Encapsula los distintos Estados de una llamada de operador automático<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ anuncio|
|Es el operador automático implicado              |Boolean                  |Indica si el AA implicado en la llamada |
|Recuento de acciones de llamadas de operador automático      |int                      |Recuento de acciones utilizadas por el autor de la llamada         |
|Duración de la cadena de operador automático de segundos   |int                      |Duración de la llamada en AA                 |
|Resultado de la llamada a la cola de llamadas                  |String                   |Estado final de llamada de cola de llamadas<br>valores posibles:<br>§ error<br>§ rechazada<br>subdesbordamiento de §<br>§ falló<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Acción de estado final de cola de llamadas           |String                   |Acción final de cola de llamadas<br>valores posibles:<br>§ reenviar<br>§ Disconnect<br>§ buzón de voz<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ Other|
|Identidad de la cola de llamadas                     |String                   |Nombre de la cuenta de recursos adjuntada a CQ<br>Ejemplo: aa_test@microsoft.com|
|Cola de llamadas en modo de conferencia           |Boolean                  |Se establece en 1 si el modo de conferencia está habilitado en CQ |
|Tipo de destino de cola de llamadas                  |String                   |Tipo de destino de redirección de llamadas esperado     |
|Transferido desde la identidad de la cola de llamadas    |Boolean                  |Nombre de la cuenta de recursos vinculada a CQ desde la que se transfirió esta llamada<br>Ejemplo: aa_test@microsoft.com|
|Recuento de participación en el agente de cola de llamadas           |int                      |Recuento de agentes disponibles para esta cola en el momento de la llamada |
|Recuento de agentes de colas de llamadas                  |int                      |Recuento de agentes asignados a esta cola en el momento de la llamada |
|Es la cola de llamadas involucrada                  |Boolean                  |Si la cola de llamadas se relaciona con esta llamada es igual a 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensiones del modelo de datos de PowerBI

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nombre de AA                                   |tipo                   |Identificador de operador automático (identificador de cuenta de recursos) |
|AACallFlow                              |tipo                   |Encapsula los distintos Estados de una llamada de operador automático<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ anuncio |
|AACallResult                            |tipo                   |Resultado de la llamada de operador automático:<br>§ desconocido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined: error de configuración AA<br>§ service_terminated: errores internos de AA<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |tipo                   |Duración de la llamada de operador automático en segundos  |
|AACount                                 |tipo                   |número de operadores automáticos en una llamada         |
|AADirectorySearchMethod                 |tipo                   |Método de búsqueda usado en la llamada:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name<br>
|AAStartTime                             |tipo                   |Hora de la llamada en UTC      |
|AATransferAction                        |tipo                   |Destinatario de la llamada:<br>§ desconocido: no se especificó el tipo de entidad<br>§ usuario-entidad usuario<br>§ AA-entidad de operador automático organizacional<br>§ CQ: entidad de cola de llamadas<br>§ aplicación-entidad de la aplicación de voz<br>§ external_pstn entidad de RTC externa<br>§ shared_voicemail-entidad de buzón de voz compartido      |
|PSTNMinutes                             |int                      |Uso total de minutos                          |
|Resultado de la llamada a la cola de llamadas                  |tipo                   |Estado final de llamada de cola de llamadas<br>valores posibles:<br>§ error<br>§ rechazada<br>subdesbordamiento de §<br>§ falló<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identidad de la cola de llamadas                     |tipo                   |Nombre de la cuenta de recursos adjuntada a CQ     |
|Tipo de destino de cola de llamadas                  |tipo                   |Tipo de destino de redirección de llamadas esperado:<br>§ Usuario<br>§ Extremo de la aplicación<br>§ Other     |
|Resultado de la llamada a la cola de llamadas                  |tipo                   |Estado final de llamada de cola de llamadas<br>valores posibles:<br>§ error<br>§ rechazada<br>subdesbordamiento de §<br>§ falló<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference           |
|Acción de estado final de cola de llamadas           |tipo                   |Acción final de cola de llamadas<br>valores posibles:<br>§ reenviar<br>§ Disconnect<br>§ buzón de voz<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ Other             |
|Nombre del agente                              |tipo                   |UPN del usuario               |


### <a name="measures"></a>Relativas

|Nombre                                      |Tipo                       |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |n.º de acción seleccionada por el usuario en AA durante la llamada  |
|PSTNMinutes                             |int                      |Uso total de minutos                                  |
|TotalCallCount                          |int                      |número de llamadas                                          |
|Duración media de la llamada (segundos)         |int                      |Duración total de las llamadas a la cola de llamadas en segundos     |


### <a name="power-bi-graph-description-auto-attendant"></a>Operador automático de descripción de gráficos de Power BI

|Nombre                                      |Descripción                            |
|:---------------------------------------|:--------------------------------------|
|Origen de la llamada entrante                    |Distribución de la llamada por origen de llamada interna o externa      |
|Totales del método de búsqueda en el directorio          |Distribución de la llamada por tipo de búsqueda                         |
|Acción de llamador                           |Distribución de llamada por receptor de llamada                       |
|Resultado de la llamada                             |Distribución de la llamada por estado final de la llamada                    |
|Recuento de acciones de llamadas                     |Acción de distribución de llamada por número usada durante la llamada  |


### <a name="call-queue"></a>Cola de llamadas

|Nombre                                      |Descripción                            |
|:---------------------------------------|:--------------------------------------|
|Origen de la llamada entrante                    |Distribución de la llamada por origen de llamada interna o externa         |
|Volumen de llamadas                             |Distribución de las colas de llamadas de llamadas                            |
|Resultado de la llamada                           |Distribución de la llamada por el resultado de la llamada                            |
|Acción total de llamada de tiempo de espera/desbordamiento      |Distribución de llamada no desviada (abandonada) llamada por resultado de la llamada   |
|Totales de transferencia/reenvío          |Distribución de la llamada desviada por el resultado de la llamada                  |
|Proporción de llamadas abandonadas                   |Relación entre el recuento de llamadas con éxito a abandonado                    |
|Duración media de la sesión (segundos)        |Duración de la llamada en segundos agrupados por llamadas abandonadas o correctas   |



### <a name="agent-timeline"></a>Escala de tiempo del agente

|Nombre                                                      |Descripción                            |
|:-------------------------------------------------------|:--------------------------------------|
|# llamadas por agente                                        |Distribución de la llamada de la cola de llamadas y del agente                 |
|Duración total de las llamadas (segundos) por agente y cola de llamadas   |Duración total (segundos) de la llamada por agente y cola de llamadas     |
|Duración media de la llamada (segundos) por nombre de agente            |Duración media (segundos) de llamada por agente                  |



## <a name="known-issues"></a>Problemas conocidos

- Por el momento, la cola de llamadas y el operador automático muestran el identificador de cuentas de recursos en lugar de la cola de llamadas/nombres de operador automático.  Para mostrar todo el tráfico de un operador automático o de una cola de llamadas, debe seleccionar todas las cuentas de recursos asignadas al operador automático o a la cola de llamadas.
- Actualmente, solo los 28 días del historial están disponibles en el panel como la cola de llamadas o los datos de operador automático se consideran información de identificación del usuario final y están sujetos a las directivas de retención de privacidad de los datos.
