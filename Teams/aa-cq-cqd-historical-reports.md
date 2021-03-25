---
title: Operador automático & histórico de cola de llamadas
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
description: Obtenga información sobre cómo usar el informe Power BI del panel de calidad de llamadas para ver los datos históricos Operador automático y Cola de llamadas.
ms.openlocfilehash: d3c8bd7181bab9ee7c199aedbac8a6fcc4c78d75
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121548"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Operador automático & histórico de cola de llamadas

La plantilla de Power BI Operador automático & informe histórico de cola de llamadas de CQD Teams proporciona los siguientes tres informes:

- Operador automático: muestra análisis de las llamadas que llegan a los Operadores automáticos.
- Cola de llamadas: muestra análisis de las llamadas que llegan a las colas de llamadas.
- Escala de tiempo del agente: muestra una vista de escala de tiempo de los agentes que están activos en las llamadas de cola de llamadas.

Estos informes usan [](CQD-Power-BI-query-templates.md) datos del almacén de datos Panel de calidad de llamadas y permiten a las organizaciones informar sobre el número de llamadas que están procesando los operadores automáticos y las colas de llamadas, así como el rendimiento del agente en las colas de llamadas.

## <a name="what-are-the-requirements"></a>¿Cuáles son los requisitos? 

Debe tener Instalado Power BI Desktop. Puede instalarlo desde microsoft [Windows Store.](https://aka.ms/pbidesktopstore)

Puede usar la versión gratuita de Power BI Desktop. La versión mínima compatible es 2.85.681.0 (septiembre de 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Permisos para obtener acceso a la canalización de CQD

La cuenta que usa para ver el informe histórico de AA & CQ Analytics debe tener permisos para obtener acceso a la canalización de datos de CQD. Consulte el rol [de acceso CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para obtener más información.

## <a name="installation"></a>Instalación 

En los pasos siguientes se supone que ya ha instalado Power BI Desktop en el equipo y que su cuenta tiene los permisos necesarios para obtener acceso a la canalización de datos CQD.

Siga estos pasos:

- Descargue las plantillas de consulta de Power BI de [CQD](https://www.microsoft.com/download/details.aspx?id=102291) y guarde el archivo zip en un directorio del equipo.

- Haga doble clic en el archivo zip para abrirlo.

- Haga doble clic en el archivo de plantilla "CQ y AA combined Analytics 20201105.pbit" y power BI Desktop debería iniciarse.

- Se le pedirá que seleccione la región de canalización de datos CQD. Seleccione la región donde se encuentra el inquilino.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Captura de pantalla que selecciona la región de canalización de datos CQD":::

 - Puede ver la región con el cmdlet de PowerShell de Skype Empresarial Online (Get-CsTenant). Resultado de ServiceInstance. 
 La región se mostrará después del /me gusta en este ejemplo:

   microsoftcommunicationsonline/noam-4a-s7 donde la región es noam.
 
 - El informe se iniciará con datos de ejemplo.
 
 - Para ver sus propios datos, haga clic en **Actualizar** en la pestaña Inicio en Consultas en Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Captura de pantalla seleccionando la opción de actualización":::

- A continuación, se le pedirá que inicie sesión. Seleccione **Cuenta de la organización** y, a continuación, seleccione Iniciar **sesión.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Captura de pantalla que muestra inicio de sesión":::

- Seleccione **Conectar** y vea la actualización de datos.

## <a name="data-latency-and-aa--cq-analytics"></a>Latencia de datos y AA & análisis de CQ

Los datos estarán disponibles en la canalización de datos CQD en un plazo de 30 minutos.

Tendrá que actualizar los datos para ver los nuevos datos de análisis. 

## <a name="customization"></a>Personalización 

Puede personalizar determinados aspectos de visualización de los informes, como agregar o quitar campos que se mostrarán en las distintas visualizaciones, cambiar el tipo de gráfico, etc.

No puede agregar campos de datos adicionales distintos de los proporcionados en el informe.

### <a name="change-color-schema"></a>Cambiar esquema de color 

En los pasos siguientes se supone que ya ha completado los pasos de instalación.

Siga estos pasos:
- Seleccione **la pestaña Vista** en la cinta de opciones.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Captura de pantalla seleccionando la pestaña vista para cambiar la combinación de colores":::

- Seleccione el esquema de color de la lista desplegable.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Captura de pantalla que muestra varias combinación de colores":::

## <a name="cqd-fields-description"></a>Descripción de campos CQD

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Operador automático identidad                 |cadena                   |Nombre de la cuenta de recursos adjunta a AA<br>Ejemplo: aa_test@microsoft.com|
|Operador automático hora de inicio de cadena         |datetime                 |Hora de inicio de la cadena AA                    |
|Operador automático de búsqueda de directorios  |cadena                   |Método de búsqueda de la última libreta de direcciones        |
|Operador automático acción Transferir          |cadena                   |Tipo de destino de transferencia de llamadas<br>valores posibles:<br>§ desconocido: no se especificó el tipo de entidad<br>§ usuario: entidad de usuario<br>§ orgaa: entidad Operador automático organización<br>§ hunt_group : entidad Cola de llamadas<br>§ aplicación: entidad de aplicación de voz<br>§ external_pstn - entidad RTC externa<br>§ shared_voicemail: entidad de correo de voz compartido|
|Operador automático de llamada              |cadena                   |Resultado de la llamada:<br>§ desconocido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|Operador automático de llamadas                |cadena                   |Encapsula los distintos estados de Operador automático llamada<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>Anuncio de §|
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


### <a name="power-bi-data-model-dimensions"></a>Dimensiones del modelo de datos de Power BI

|Nombre                                    |Tipo de datos                |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nombre AA                                   |cadena                   |Operador automático (id. de cuenta de recurso) |
|AACallFlow                              |cadena                   |Encapsula los distintos estados de Operador automático llamada<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>Anuncio de § |
|AACallResult                            |cadena                   |Resultado de Operador automático llamada:<br>§ desconocido<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined: error de configuración de AA<br>§ service_terminated: errores internos de AA<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |cadena                   |Duración de Operador automático llamada en segundos  |
|AACount                                 |cadena                   |# de Operador automático participar en la llamada         |
|AADirectorySearchMethod                 |cadena                   |Método de búsqueda usado en la llamada:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name<br>
|AAStartTime                             |cadena                   |Hora de llamada en UTC      |
|AATransferAction                        |cadena                   |Receptor de llamada:<br>§ desconocido: no se especificó el tipo de entidad<br>§ usuario: entidad de usuario<br>§ AA: entidad Operador automático organización<br>§ CQ : entidad Cola de llamadas<br>§ aplicación: entidad de aplicación de voz<br>§ external_pstn - entidad RTC externa<br>§ shared_voicemail: entidad de correo de voz compartido      |
|RTCMinutes                             |int                      |Uso total de minutos                          |
|Resultado de la llamada en cola de llamadas                  |cadena                   |Estado final de la llamada de cola de llamadas<br>valores posibles:<br>Error de §<br>§ rechazado<br>§ desbordado<br>Error en el §<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identidad de cola de llamadas                     |cadena                   |Nombre de la cuenta de recursos adjunta a CQ     |
|Tipo de destino de cola de llamadas                  |cadena                   |Tipo de destino de redireccionamiento de llamadas esperado:<br>§ Usuario<br>§ Punto de conexión de aplicación<br>§ Otros     |
|Resultado de la llamada en cola de llamadas                  |cadena                   |Estado final de la llamada de cola de llamadas<br>valores posibles:<br>Error de §<br>§ rechazado<br>§ desbordado<br>Error en el §<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference           |
|Acción de estado final de la cola de llamadas           |cadena                   |Acción final de la cola de llamadas<br>valores posibles:<br>§ hacia delante<br>§ desconectar<br>§ correo de voz<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ otros             |
|Nombre del agente                              |cadena                   |UPN de usuario               |


### <a name="measures"></a>Medidas

|Nombre                                      |Tipo                       |Descripción                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |# de acción seleccionada por el usuario en AA durante la llamada  |
|RTCMinutes                             |int                      |Uso total de minutos                                  |
|TotalCallCount                          |int                      |# de llamadas                                          |
|Duración media de la llamada( segundos)         |int                      |Duración total de las llamadas en cola de llamadas en segundos     |


### <a name="power-bi-graph-description-auto-attendant"></a>Descripción de gráficos de Power BI Operador automático

|Nombre                                      |Descripción                            |
|:---------------------------------------|:--------------------------------------|
|Origen de llamadas entrantes                    |Distribución de llamadas por origen de llamada interno/externo<sup>1</sup>|
|Totales de métodos de búsqueda de directorios          |Distribución de llamadas por tipo de búsqueda                         |
|Acción de autor de llamadas                           |Distribución de llamadas por receptor de llamadas                       |
|Resultado de la llamada                             |Distribución de llamadas por estado de llamada final                    |
|Recuento de acciones de llamada                     |Distribución de la llamada por acción de número usada durante la llamada  |


### <a name="call-queue"></a>Cola de llamadas

|Nombre                                      |Descripción                            |
|:---------------------------------------|:--------------------------------------|
|Origen de llamadas entrantes                    |Distribución de llamadas por origen de llamada interno/externo<sup>1</sup>   |
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

- Cola de llamadas y operadores automáticos se muestran con el id. de la cuenta de recursos en lugar de los nombres de cola de llamadas o operadores automáticos.  Para mostrar todo el tráfico de un operador automático o cola de llamadas, debe seleccionar todas las cuentas de recursos asignadas al operador automático o a la cola de llamadas.

- Solo 28 días de historial está disponible en el panel, ya que los datos de cola de llamadas o operador automático se consideran información de identificación del usuario final y están sujetos a directivas de retención de privacidad de datos.

- <sup>1 Origen</sup> **de llamadas entrantes** en los gráficos operador automático y Cola de llamadas muestran el origen final del tramo de llamada en lugar del origen inicial del tramo de llamada. Por ejemplo, si un operador automático recibe una llamada externa y transfiere  la llamada a otro operador automático o cola de llamadas, el origen de llamadas entrantes se notifica como Interno.
