---
title: Datos de diagnóstico móvil necesarios para Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Una lista de propiedades y eventos móviles para los controles de directiva para Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d040a6e592ead9f29dcc7f23efe069b041ccf07
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901947"
---
# <a name="required-mobile-diagnostic-data-for-microsoft-teams"></a>Datos de diagnóstico móvil necesarios para Microsoft Teams

El artículo siguiente contiene una lista de eventos de Microsoft Teams Mobile y listas de propiedades que recopila cada evento.

Para más información sobre los datos de diagnóstico, incluido cómo controlar los datos de diagnóstico que se envían a Microsoft, vea [Datos de diagnóstico enviados desde la aplicación de Microsoft Teams a Microsoft](policy-control-overview.md#diagnostic-data-sent-from-the-teams-app-to-microsoft). Para ver los datos de diagnóstico que se envían a Microsoft, puede usar el [Visor de datos de diagnóstico](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).

## <a name="events"></a>Eventos

> [!NOTE]
> Hay propiedades comunes para todos los eventos que se muestran a continuación, con el fin de revisarlos, vea [Propiedades que se envían con todos los eventos](#properties-sent-with-all-events).

### <a name="panelaction"></a>PanelAction

> [!NOTE]
> Para obtener información sobre las propiedades de los eventos PanelAction, consulte[propiedades que se envían con eventos de PanelAction](#properties-sent-with-panelaction-events).

- **accessibilityUserConfiguration** - Cuando un usuario activa una característica de accesibilidad.
- **acknowledgeSettingChange** : Reconoce una actualización en el cuadro de diálogo hemos actualizado la configuración de la notificación. Se trata de una métrica de éxito de características que se usa para confirmar las notificaciones de actualización y para determinar la confiabilidad global de las notificaciones.
- **actionComposeMenu**
  - Uso de la extensión de crear mensajes.
  - Uso de la extensión de acción de mensaje.
- **active_session_banner_dismissed** : Se ha descartado la pancarta que comparte el aviso activo.
- **activityChatClicked** - Se desencadena cuando se selecciona el chat no activo en la pestaña **Actividad** o se muestra una vista dividida.
- **activityContextMenu** - Acciones de desbordamiento en la fuente de actividades.
- **activityFeedClick** - Se puntea en un elemento de la fuente de actividades y se navega a un bot de chat.
- **activityFeedLongPress** - Captura gestos de presión larga en elementos de fuente.
- **activityFeedSwipe** - Captura los gestos de deslizamiento de los elementos de fuente.
- **activityFilterClick** - Captura el uso del filtro de actividad.
- **activityFilterOptionsClick** - Captura el uso del filtro de actividad.
- **activityFilterOptionsClicked** - Captura el uso del filtro de actividad.
- **activityLiveChatClicked** - Se desencadena cuando se selecciona chat en Live Meeting en la pestaña **Actividad**.
- **activityLiveDetailsClicked** - Se desencadena cuando se selecciona **Detalles** en una reunión de Live Meeting en la pestaña **Actividad**.
- **activityTabClicked** - Te ayuda a determinar si:
  - Se muestra la pestaña **Actividad**.
  - Teams captura un evento de la pestaña **Actividad**.
- **activityTypeDropdown** - Captura el uso del filtro de actividad para cambiar entre **Mi actividad** y **Fuentes**.
- **addChannel**: agregar un canal. Este elemento proporciona datos correctos en torno a la creación satisfactoria de un canal.
- **addMember** - Activó el botón **Invitar personas** está seleccionado en el menú **Más**.
- **addMembers** - Agregar miembros a un equipo o un canal privado.
- **addToCalendar** - Seleccione el botón **agregar al calendario** para eventos de calendario que faltan en el calendario privado.
- **addToList** - Un contacto se agrega a una lista de contactos.
- **addToMeeting** - Seleccione el botón **Agregar a la reunión** en la lista de participantes de una reunión (para los participantes que forman parte del chat).
- **addUserAsContact** - Se puede agregar un contacto al seleccionar el icono **Agregar contacto** desde la tarjeta de perfil del contacto.
- **admitAll** - Es el número de veces que se selecciona el botón **Admitir todos** en la sección introductoria.
- **admitParticipant** - El número de veces que alguien ha sido admitido en una reunión desde la lista de participantes de la reunión.
- **alertsNavAlert** - Pulsar en un elemento de la fuente.
- **Android: NULL** - Activar o desactivar el bot de un chat. Esto está mejorando la telemetría existente en torno a los chats, solo agrega información de la aplicación.
- **anonymousMeetingJoin** - **Unirse a una reunión** está seleccionada en una página de proporcionar nombre participar anónimamente o **Aceptar** es pulsado en el cuadro de diálogo nombre.
- **anonymousMeetingJoinWelcome** - **unirse como** de invitado está seleccionada en una página de aterrizaje unirse a una reunión anónima.
- **anonymousMeetingPostMeetingChat** - El número de vistas de usuario de chat en la pantalla finalizar llamada.
- **anonymousMeetingPostMeetingRejoin** - Es el número de veces que un usuario anónimo intenta volver a unirse a una reunión.
- **anonymousMeetingSignIn** - Es el número de veces que un usuario se ha desplazado para iniciar sesión desde la pantalla de entrada Nombre.
- **anonymousMeetingSignInWelcome** - **Iniciar sesión y unirse** se ha seleccionado en una página de destino unirse a una reunión anónimamente.
- **anonymousMeetingToggleMuted** - Número de veces que se ha seleccionado el botón de alternancia de silencio.
- **anonymousMeetingToggleVideo** - El número de veces que se ha seleccionado el botón de alternancia de vídeo.
- **appKilled** - La aplicación ha finalizado.
- **approveTimeOffRequest** - Cuando un administrador de Trabajador de primera línea (FLW) aprueba una solicitud de tiempo libre de un Trabajador de primera línea.
- **assigneeChange** - Se desencadena cuando se agrega una nueva asignación a un elemento de tarea.
- **assignmentPickerClicked** - El botón **Asignar a** está seleccionado, abriendo la página selector de la persona asignada.
- **assignmentRemoved**: Se desencadena cuando se quita un elemento al que se ha asignado una tarea al seleccionar la **x** (que es la única manera de quitar una persona asignada).
- **attachmentAdded** - Confirma que los datos adjuntos de una tarea se han agregado correctamente.
- **attachmentDeleted** - Confirma que los datos adjuntos de una tarea se ha eliminado correctamente.
- **attachmentUpdated** - Confirma que un archivo adjunto en una tarea se ha actualizado correctamente.
- **audioOnlyLowBatteryBanner** - La opción **Solo audio** está seleccionada debido a un indicador de batería baja.
- **audioOnlyPoorNetworkBanner** - La opción **Vídeo apagado** está seleccionada debido a un indicador de conexión deficiente.
- **audioUserDoubleTap** - Pulse dos veces en un participante de audio.
- **autoReconnectCallmebackCallDrop** - El número de veces que se seleccionó el botón **Callmeback** en la pantalla finalizar llamada.
- **autoReconnectDialIn**
  - Se selecciona el botón **Marcar para acceder** en la UFD reconectar.
  - El número de veces que se seleccionó el botón **Marcar para acceder** mientras se está realizando una conexión.
- **autoReconnectDialInonCallDrop** - El botón **Marcar para acceder** se encuentra seleccionado en la UFD llamada desconectada.
- **autoReconnectDialOut** - El botón **Llamarme** se ha seleccionado en la UFD reconectar.
- **autoReconnectRejoinonCallDrop** - El número de veces que se seleccionó el botón **Volver a unirse** o **Volver a marcar** en la pantalla finalizar llamada.
- **backFromCallMePSTN** - El flujo numérico RTC Llamarme, no está completo.
- **backToPhotoShare** - Regresar a la cámara.
- **backToStageFromWhiteboard** - Volver a una pantalla de llamadas desde una pizarra.
- **backToWhiteboardFromStage** : va a una pizarra desde una pantalla de llamadas.
- **blockAnonymous** - Cuando:
  - Permite que la configuración de llamada bloquee las llamadas sin ID. de llamada de la configuración.
  - Deshabilita la configuración de llamada para bloquear las llamadas sin el identificador de llamada de la configuración.
  - Permite que la configuración de llamada bloquee las llamadas sin el identificador de llamada de la hoja de acciones.
  - Deshabilita la configuración de llamada para bloquear las llamadas sin el identificador de llamada de la hoja de acciones.
- **blockCaller** - Bloquear:
  - Un número y un contacto desde la nueva hoja de acciones de las llamadas de iOS.
  - Un contacto y un número de la tarjeta de contacto.
  - Números de la configuración.
- **blockChat** bloquear un bot de chat. Esto mejora la telemetría actual en torno a los chats y solo agrega información de la aplicación.
- **botClickCardAction** - Uso de la tarjeta de conexión.
- **brbFormOpened** - El usuario solicitó enviar comentarios.
- **brbFormSubmit** - El usuario envió comentarios.
- **breakStartEndClicked** - En la pantalla del reloj, se selecciona el botón **Inicio** o **Finalizar descanso**.
- **breakStartEndTriggered** - Registrar un usuario opta por usar Iniciar o Finalizar descanso.
- **bucketSelected** - Confirma que un depósito se ha seleccionado correctamente.
- **bucketUnselected** - Confirma que se ha desactivado correctamente un depósito.
- **bucketPickerClicked** - Confirma que el selector de depósito se inició correctamente.
- **BYOELiveEventJoin** - Al evento en directo BYOE (difundir su propio evento) se une un usuario.
- **calendarLiveChatClicked** - Chat de Live Meeting en la pestaña **Programación**.
- **calendarMeetingJoin** - **Botón** Unirse a la reunión seleccionado en un calendario.
- **calendarTab**: seleccionar la pestaña **Reuniones** en el raíl inferior. Es útil para comprender el uso del calendario y compararlo con otras aplicaciones en el raíl inferior, o bien para determinar si se produjo un error al procesar el envío del calendario después de seleccionar una opción en la barra inferior.
- **calendarTabClicked** - En las circunstancias que se muestran a continuación, se mostrará el uso del calendario y le permitirá comparar con otras aplicaciones de la barra de exploración en el riel inferior. Se puede usar para determinar si se produjo un error cuando:
  - Se muestra la pestaña **Programación**.
  - La pestaña **Reuniones** está seleccionada en el riel inferior.
- **calendarUpcomingChatClicked** - Use el chat desde una próxima reunión en la pestaña **Programación**.
- **callAccepted** - Llamada aceptada.
- **callAcceptedSFB** - Llamada aceptada.
- **callAppPreference** : Está seleccionada la aplicación preferida para llamadas.
- **callControlsManualDismisslos** - Los controles de llamada se descartan manualmente.
- **callControlsManualInvoke** - Los controles de llamada se llaman manualmente.
- **callHistoryItemExpand** - Elemento de historial de llamadas expandido.
- **callHistoryTab** - La pestaña **CallHistory** se selecciona en Llamadas.
- **callInProgressShown** - Se muestra una notificación de **_Llamada en curso_*.
- **callMePSTNConnected** - **Llamarme** se ha realizado correctamente.
- **callOrMeetUpAddParticipants** - Se desencadena cuando:
  - El botón Agregar participante es pulsado en una pantalla de llamadas 1:1.
  - Seleccione Person (VoIP) en Agregar participantes.
  - Seleccione RTC en Agregar participantes.
  - Agregue personas en una reunión privada en directo.
  - Seleccione RTC en una reunión privada en directo.
  - Seleccione Contacto empresarial en una reunión privada en directo.
  - Seleccionar el contacto del dispositivo en una reunión privada en directo.
  - Agregue participantes en una reunión privada en directo.
  - Agregue personas en una reunión de canal en directo.
  - Seleccione RTC en una reunión de canal en directo.
  - Seleccione miembro del equipo en una reunión con un canal en directo.
  - Seleccione contactos del dispositivo en una reunión de canal en directo.
  - Agregue participantes en una reunión con un canal en directo.
- **callOrMeetUpAddParticipantsDone** - Un usuario termina la adición de su participante.
- **callOrMeetUpAddRoom** - Se desencadena cuando:
  - **Agregar sala** se ha seleccionado en la lista de participantes.
  - Se selecciona un resultado de búsqueda en agregar sala.
  - **Descartar** está seleccionada para Cerca.
  - **Habilitar BT** o **Ubicación** está seleccionada para Cerca.
  - Se ha seleccionado un resultado de sala cercana en agregar sala.
  - Se ha seleccionado un resultado de sala sugerido en agregar sala.
  - **Hecho** se ha seleccionado en agregar sala.
- **callOrMeetUpAudioOffSwitch** - Mueva el switch de **Desactivar audio** mientras se encuentre en el modo de conectar compañía en una llamada en directa o Meetup.
- **callOrMeetUpAutoReconnect** - Un pobre rendimiento de la red provoca que el dispositivo de un usuario entre en modo de Autoreconnect.
- **callOrMeetUpCallAccepted** - Se desencadena cuando:
  - Se acepta una llamada.
  - Se aceptan llamadas RTC.
- **callOrMeetUpCallEnded** - Se desencadena cuando:
  - Se pulsa un botón **Finalizar llamada**.
  - Se pulsa un botón de **Llamada finalizada** mientras está en callOrMeetupLive.
  - Se pulsa un botón de **Llamada finalizada** mientras está en la pantalla de bloqueo.
  - Se pulsa un botón de **Llamada finalizada** mientras está en la notificación.
  - Se pulsa un botón de **Llamada finalizada** mientras está en inApp.
  - Se pulsa un botón de **Llamada finalizada** mientras está en callKit.
  - Se pulsa un botón de **Llamada finalizada** para RTC.
- **callOrMeetUpChatWithParticipants** - Alternacia de chat mientras está en una llamada o reunión en directo.
- **callOrMeetUpDeviceAudioSwitch** - Se desencadena cuando:
  - Cambiar el origen de audio al orador.
  - Cambiar el origen de audio al dispositivo.
  - Cambiar el origen de audio a Bluetooth.
  - Cambiar el origen de audio a audio apagado.
  - Cambiar de orador mientras está en una llamada o reunión en directo.
  - Cambiar del altavoz al audio apagado mientras se encuentre en Live Meeting o en una llamada.
  - Activa el botón de **Audio apagado** mientras se encuentre en el modo de Conectar compañía en llamada o encuentra en directo.
  - Cambiar de audio de dispositivo mientras está en RTC.
- **callOrMeetUpEnterDriveMode** - Cambia manualmente al modo En coche desde el menú **...**.
- **callOrMeetupExitDriveMode** - se ha pulsado el botón de **Salir del modo En coche**.
- **callOrMeetUpHold** - Se desencadena cuando:
  - El botón **Retener** es pulsado mientras está en una llamada o reunión en directo.
  - Llamada en espera en RTC.
- **callOrMeetUpIncomingVideoSwitch** - Desactivar IncomingVideo mientras se encuentren en una llamada o reunión en directo.
- **callOrMeetUpInvitedParticipants** - Se desencadena cuando:
  - Se hace clic en **Ver todos** en la parte inferior de un grupo de participantes **Otros invitados** durante una reunión en directo privada.
  - Se hace clic en **Ver todos** en la parte inferior de un grupo de participantes **Otros invitados** durante una reunión de canal en directo.
- **callOrMeetUpJoinedParticipants** - Se desencadena cuando:
  - Se hace clic en **Ver todos** en la parte inferior de un grupo de participantes **En la reunión** durante una reunión en directo privada.
  - Se hace clic en **Ver todos** en la parte inferior de un grupo de participantes **En la reunión** durante una reunión de canal en directo.
- **callOrMeetUpLobbyParticipants** - Se desencadena cuando:
  - Se hace clic en **Ver todos** en la parte inferior de un grupo de participantes **Sala de espera** durante una reunión en directo privada.
  - Se hace clic en **Ver todos** en la parte inferior de un grupo de participantes **Sala de espera** durante una reunión de canal en directo.
- **callOrMeetUpMicrophoneSwitch** - Se desencadena cuando:
  - Se cambia el micrófono a activado.
  - Se cambia el micrófono a desactivado.
  - El botón del **Micrófono** está seleccionado mientras se encuentre en una reunión o en una llamada en directo.
  - Interruptor del Micrófono mientras está en RTC.
- **callOrMeetUpMuteParticipant** - Un participante remoto está silenciado.
- **callOrMeetUpMuteParticipants** - Silenciar a todos los participantes mientras se encuentren en una llamada o reunión en directo.
- **callOrMeetUpParticipants** - Los participantes se activan durante una llamada o reunión en directo.
- **callOrMeetUpRemoteMuteUFD** - Ha estado silenciada UFD.
- **callOrMeetUpResume** Se desencadena cuando:
  - El botón de **Retomar** está seleccionada mientras se encuentra en una reunión o en una llamada en directo.
  - Llame a resume en RTC.
- **callOrMeetUpSearchParticipants** - Se desencadena cuando:
  - Se hace clic en **Buscar** en los participantes de la reunión durante una reunión en directo privada.
  - Se hace clic en **Buscar** después de ver el grupo participante **Sala de espera** durante la reunión privada.
  - Se hace clic en **Buscar** después de ver el grupo participante **En la reunión** durante la reunión privada.
  - Se hace clic en **Buscar** después de ver el grupo participante **Otros invitados** durante la reunión privada.
  - Se hace clic en **Buscar** en participantes de la reunión durante una reunión de canal en directo.
  - Se hace clic en **Buscar** después de ver el grupo participante **Sala de espera** durante una reunión del canal activo.
  - Se hace clic en **Buscar** después de ver el grupo participante **En la reunión** durante una reunión del canal activo.
  - Se hace clic en **Buscar** después de ver el grupo participante **Otros invitados** durante una reunión del canal activo.
- **callOrMeetUpVideoSwitch** - Se desencadena cuando:
  - Se cambia el vídeo a activado.
  - Se cambia el vídeo a desactivado.
  - El botón de vídeo fue seleccionado mientras se encontraba en una llamada o reunión en directo.
- **callPark** - Se desencadena cuando:
  - La **Llamada de estacionamiento** está seleccionada en el menú **...**.
  - El botón **Recuperar** está seleccionado.
  - **Recogida** está seleccionada en el cuadro de diálogo recuperar.
  - **Cancelar** está seleccionada en el cuadro de diálogo recuperar.
- **callPreferenceSetting**- Configuración de la aplicación de preferencias de llamada.
- **callsTabNewCall** - **Llamada nueva** está seleccionada en la pestaña **Llamadas**.
- **callTransfer** - Se ha iniciado una transferencia de llamada.
- **callVoicemailTab** - La pestaña **Correo de voz** está seleccionada en llamadas.
- Se ha seleccionado el cuadro de diálogo de permisos de cámara **cameraPermissionCancel** - **Cancelar**.
- En el cuadro de diálogo de permisos de cámara se navega por **cameraPermissionGoToSettings** - **Settings**.
- **cancelEditMeeting** - Seleccione el botón **Cerrar** mientras se encuentre en la página programador de reuniones, después de seleccionar **Editar reunión**. Este registro se registra cuando un usuario abandona la selección de edición de la reunión.
- En el cuadro de diálogo de confirmación, **cancelFileShare** - **Cancelar** está seleccionado.
- En el cuadro de diálogo cargar se ha seleccionado **cancelFileUpload** - **x**.
- **cancelMeeting** - Seleccione **Cancelar evento** en la página detalles de la reunión. Se usa para obtener datos agregados del número de reuniones canceladas.
- **cancelNavigationToLink** - Se ha elegido Cancelar navegación.
- **cancelRequestToJoinTeam** - Solicitud de cancelar unirse a un equipo.
- **cancelRequestToJoinTeamError** - Hay un error con una solicitud de cancelar unirse a un equipo.
- **cancelNewMeeting** - Para registrar selecciones abandonadas de Crear reuniones y verificar lo que las provocó cuando:
  - Se selecciona el botón **Cerrar** mientras se encuentra en la página programador de reuniones.
  - Se selecciona el botón **Cerrar** mientras se encuentra en la página programador de reuniones después de seleccionar **Editar reunión**.
- **cardView - No hay AS asignada** Vista de tarjeta y representación de la tarjeta. Las tarjetas son construcciones clave de la plataforma y la medida del uso y el patrón es necesaria para entender el uso de la plataforma y mantener un vistazo a los posibles problemas en el lado del cliente. Este elemento es necesario para medir cualquier error en la Unión a un equipo.
- **castPpt** - El evento se activa cuando:
  - Se ha seleccionado una opción de PowerPoint.
  - Se selecciona un archivo de PowerPoint concreto.
  - La carpeta equipos y canales está seleccionada en la página del selector de archivos.
  - Selecciona una carpeta de OneDrive en la página del selector de archivos.
  - Detiene la sesión de conversión.
  - Pulsa en el PiP multitarea.
  - Selecciona una opción de presentación de la vista de archivo.
- **castScreen** - Hace referencia a:
  - Toque en la opción de pantalla compartir.
  - Detener la sesión de uso compartido de la pantalla.
  - Selección de la opción de presentación desde la vista de archivo.
- **center_on_team_clicked** - Un usuario centra satisfactoriamente el mapa en los grupos.
- **channelFollow** - Activar las notificaciones para un canal.
- **channelUnfollow** - Desactiva las notificaciones para un canal.
- **channelsActiveSetting** - La configuración de la notificación **Avisarme cuando esté activo en el escritorio** está cambiada.
- **chatCreation** - Creación de chat con éxito.
- **changeIsActiveSetting** - Cambia notificación basada en la actividad de escritorio.
- **canal** - botón de nuevo mensaje o cuadro de texto en chat.
- **channelDetails** - Información de navegación del canal para cuando:
  - Se ha seleccionado un encabezado de canal.
  - Se navega hasta la página Detalles del canal.
- **channelFollow/channelUnfollow** - Seguir o no seguir un canal.
- **channelNav** - Navegando a un canal desde cualquier lugar.
- **channelNavTab** - Proporciona datos correctos y de detectabilidad para los archivos de en equipos cuando:
  - La pestaña **Archivos** está seleccionada en canal.
  - Hay una respuesta de tarjeta de conector.
- **channelNotificationSettings** - Se desencadena cuando:
  - Se selecciona el cuadro de diálogo **Nueva configuración de notificaciones**.
  - El botón configuración de notificación de canal está seleccionado en la vista canal.
  - Se ha seleccionado una configuración de notificación de canal.
- **channelSelected** - Confirma que se ha seleccionado satisfactoriamente un canal para un nuevo plan.
- **channelSendMessage** - Se desencadena cuando:
  - Se enviará un mensaje de canal.
  - Un bot es @mentioned en un cuadro de redacción.
- **channelTabOverflow** - Selecciona la pestaña **Más** en un canal.
- **Chat** - Se refiere a lo siguiente:
  - Un botón de mensaje nuevo o un cuadro de texto en el chat.
  - 1:1 chat seleccionado en un elemento callHistory.
  - Una selección de chat de 1:1 de la lista de llamadas.
- **Chat - no hay AS asignado** - Ver el chat no leído o editar la lista de chat, específicamente:
  - Seleccionar el botón **Completado** al agregar un usuario a un chat.
  - Se selecciona un filtro de la lista de chats para filtrar por no leídos.
- **chatAddChat** - Agregar un botón de charlar a un miembro punteado (esto será el mismo para 1:1 chat y un chat de grupo).
- **chatAllowJoinViaLink** - Activa o desactiva las funciones de enlace de Unión en la página Detalles del chat.
- **chatAvatarEdit** - Realiza un seguimiento de cuántos grupos cambian de la página Detalles del chat.
- **chatAvatarEditCamera** - Se desencadena cuando un usuario edita el Avatar desde una fuente de cámara activa.
- **chatAvatarEditGallery** - Se desencadena cuando un usuario edita el avatar de la galería del teléfono.
- **chatAvatarEditView** - Se desencadena cuando un usuario ve la imagen de Avatar existente.
- **chatListNavConversations** - Cuando un usuario puntea en un elemento de lista de chat.
- **chatCancelAudioCall** - Cancele un cuadro de diálogo llamada de audio de grupo-confirmar.
- **chatCancelVideoCall** - Cancele una llamada de vídeo grupal al cuadro de diálogo de confirmación.
- **chatCM_CopyText** - Pulse **Copiar texto** en un menú contextual de charla.
- **chatCM_DeleteMessage** - Pulse **Eliminar mensaje** en un menú contextual de charla.
- **chatCM_edit** - Pulse **Editar** en un menú contextual de chat.
- **chatCM_Forward** - Pulse **Reenviar** en un menú contextual de chat.
- **chatCM_markUnread** - Tocar **Marcar como no leído** en un menú contextual de chat.
- **chatCM_save** - Pulse **Guardar** en un menú contextual de chat.
- **chatCM_SeenBy** - Pulse en **Visto** en una opción de menú contextual. Confirmaciones de lectura, como leído por (readby).
- **chatContactsEnter** - Se ingresa la pestaña de **Contactos de chat**.
- **chatDetails** - Proporciona datos correctos y de detectabilidad para una página de detalles del chat cuando:
  - Se ha seleccionado un encabezado de chat.
  - Se navega hasta una página de detalles de charla.
- **chatRecentEnter** - Se inserta la ficha **Chat reciente**.
- **chatSendMessage** - Envía un mensaje de chat.
- **chatShareLink** Realiza un seguimiento del número de usuarios que envían un vínculo invitar al grupo.
- **chatStartAudioCall** - Se desencadena cuando:
  - Se ha punteado el botón de llamada de audio 1:1.
  - Pulsa el botón **Audio** en un resultado de búsqueda.
  - Pulsa el botón **Iniciar llamada** situado en la parte derecha.
  - 1:1 llamada de audio pulsada desde un elemento callHistory.
  - 1:1 llamada de audio pulsada desde un elemento de correo de voz.
  - Realizar una llamada de audio grupal - Confirmar diálogo.
- **chatStartAudioCallOnBehalfOf** - Delegado inicia una llamada desde la hoja de acciones como jefe.
- **chatStartAudioCallOnBehalfOfMyself** - Delegado inicia una llamada de la hoja de acciones como Yo mismo.
- **chatStartAudioCallSFB** - Se ha pulsado el botón de llamada de audio 1:1.
- **chatStartVideoCall** - Se desencadena cuando:
  - Se pulsa el botón de llamada de video 1:1.
  - Se pulsa el botón vídeo en los resultados de búsqueda.
  - Se pulsa la llamada de vídeo 1:1 desde el elemento callHistory.
  - Realice una llamada de vídeo al grupo - Confirmar el diálogo.
- **chatStartVideoCallSFB** - se ha pulsado el botón de llamada de vídeo 1:1.
- **chatWithMeetingParticipants** - Selecciona la pestaña **Chat** en la página Detalles de la reunión.
- **checkListAddClicked** - **Agregar un elemento** está seleccionado en la vista de detalles de la tarea para la sección lista de comprobación.
- **checkListItemAdded** - Se crea un elemento de la lista de comprobación para una tarea.
- **checkListItemDeleted** - Se elimina un elemento de la lista de comprobación de una tarea.
- **checkListItemUpdated** - Se actualiza un elemento de lista de comprobación para una tarea.
- **channelPickerClicked** - Confirma que el selector de canales se inició correctamente.
- **checklistSeeAllClicked** - Cuando se selecciona el botón **Ver todos** dentro de los detalles de la tarea para ver todos los elementos de la lista de comprobación.
- **chicletExpand** - Entender cómo se muestran las tarjetas en la vista previa en móviles y en el comportamiento de cierre de la versión preliminar.
- **clearFilter** - Cuando se borran todos los filtros mientras se ve una TaskList.
- **clickPhotoOfficeLens** - Seleccionar **Realizar foto** : inicie una cámara (solo Android).
- **clockInEntryTeamSelectionShown** - Un usuario selecciona un equipo para el reloj de hora sin hora de entrada.
- **clockInOutClicked** - En la pantalla de registro, el **registro de hora de entrada** o **registro de hora de salida** está seleccionado.
- **clockInOutTriggered** - Registrar la hora de entrada o de salida de un usuario. Esto no se activará hasta que haya comprobado la ubicación, presuponiendo que la ubicación es necesaria.
- **closedBannerMessage** - Se desencadena cuando se cierra el mensaje de banner de una notificación.
- **closeLobbyBanner** - El número de veces que se cierra la notificación del vestíbulo, por medio de su botón **Cerrar**.
- **commentAdded** - Confirma que se ha agregado un comentario a una tarea.
- **commentsClicked** - Confirma que la vista comentarios se inició correctamente.
- **commentUpdated** - Confirma que un comentario se ha actualizado correctamente en una tarea.
- **companionBannerJoin** - Selecciona **Unirse** en el banner de nivel superior.
- **companionDismiss** - Descarta el banner complementario.
- **companionDismissProximity** - Descarta el banner complementario.
- **companionJoin** - Unirse como opción complementaria está seleccionada en la hoja.
- **companionJoinProximity** - Unido a través del banner complementario.
- **completeVaultFRE**: el usuario completa el proceso de generación de una clave maestra, que se usa para cifrar los datos de la caja fuerte.
- **completionStateChange** - Desencadenado cuando se activa la alternancia de filtro completada o no completada en la vista filtro de la lista de tareas.
- **composeExpandComposer** - el botón **Formato** es pulsado.
- **composeFilePick** - Se ha iniciado el selector de archivo nativo.
- **composeImagePicker** - El botón de **Imagen** es pulsado.
- **composeLocation** - El botón de **Ubicación** fue pulsado durante la redacción.
- **composeMention** - @mención.
- **composeOpenEmoticonPicker** - Se pulsó el Selector de emoticonos.
- **composeOpenFunPicker** - Se pulsó el selector diversión.
- **composeParticipantAdded** - Cuando se agrega un participante a la aplicación Turnos.
- **composeSearchResult** - Selección de resultados de la extensión de mensaje, lo que puede resultar útil para comprender la relevancia del resultado de búsqueda de la aplicación. También mejora el envío de mensajes de telemetría con datos de la aplicación.
- **composeSelectExtension** - Pulse en una aplicación yo.
- **composeSendSmartRespondly**: se hace clic en un elemento de respuesta inteligente.
- **composeSendMessage** - Mejora el envío de mensajes de telemetría con datos de la aplicación.
- **confirmAudioOn** - Un usuario confirma que quieren audio.
- **confirmFileShare** - **Compartir** está seleccionado en el diálogo de confirmación.
- **consultTransfer** - Se desencadena cuando:
  - Selecciona **Transferir** > **consulta en primer lugar**
  - Destino de transferencia establecido en Persona
  - Destino de transferencia establecido en Número de teléfono.
- **consultTransferCall** - Se desencadena cuando:
  - Se inicia una llamada consultar.
  - Confirm está seleccionada en el cuadro de diálogo confirmar transferencia.
  - Cancelar está seleccionado en el cuadro de diálogo confirmar transferencia.
  - Se selecciona el botón **Transferencia de banner**.
  - Se selecciona el botón **Reanudar banner**.
- **consultTransferChat** se desencadena cuando:
  - Se ha iniciado un chat de consulta.
  - Confirm está seleccionada en el cuadro de diálogo confirmar transferencia.
  - Confirmaciones está seleccionada en el cuadro de diálogo confirmar transferencia.
  - Se selecciona un botón de **Transferencia de banner** o **Reanudar banner**.
- **consumeVoiceMessage** - Mensaje de voz reproducido.
- **ContactCard_SeeMoreOOF** - Ver más de un mensaje largo de OOF.
- **contactOrganizer** - Se selecciona **Organizador de contactos**.
- **conversación, pestañas** - Pestaña seleccionada.
- **copyLink** - Copiar un vínculo a una publicación de canal.
- **contactActivity** - Cuando se selecciona el botón para ver la actividad de un usuario desde la tarjeta de contacto.
- **conversación** - Cuando un usuario navega hasta las pestañas de **Chat** o **Publicaciones**.
- **cortanaClose** - Cuando un usuario descarta el lienzo de Cortana.
- **cortanaEduCategorySelect** - Cuando un usuario hace clic en un elemento de categoría de sugerencias de educación.
- **cortanaEduOpen** - Cuando se muestra la página Educación en el lienzo de Cortana.
- **cortanaInvoke** - Cuando Cortana empieza a escuchar.
- **cortanaKWSSwitchToggle** - Cuando un usuario pulsa en el conmutador de KWS en la página de configuración de Cortana.
- **cortanaMicPermissionButtonClick** - Cuando un usuario concede o rechaza los permisos de micrófono en el lienzo de Cortana.
- **cortanaOpen** - Cuando un usuario abre el lienzo de Cortana.
- **cortanaOptionsOpen** - Cuando el usuario pulsa el botón de opciones en el lienzo de Cortana.
- **cortanaSafetyFirstActions** - Cuando el usuario acepta la primera declaración de seguridad.
- **cortanaSafetyFirstLaunch** - Cuando el usuario abre Cortana por primera vez después de que finalice la FRE.
- **cortanaSettingsOpen** - Cuando un usuario abre la página de configuración de Cortana haciendo clic en el botón de configuración de Cortana en el lienzo de Cortana.
- **cortanaStopResponding** - Cuando un usuario hace clic en el botón Cancelar en el lienzo de Cortana.
- **cortanaUserSettingsLaunch** - Cuando el usuario abre la configuración de Cortana en la configuración de Teams.
- **cortanaVoiceSelect** - Cuando un usuario selecciona la fuente de voz de Cortana en la página de configuración de Cortana.
- **createChannel** - Proporciona datos correctos en torno a la creación correcta o descartar la creación de un nuevo canal cuando:
  - El botón **Completado** está seleccionado en la página **Crear canal**.
  - Se selecciona el botón **Cancelar** en la página **Crear canal**.
- **createComposeExtension** - Crear uso de la extensión de mensaje o uso de acciones.
- **createConversationClicked** - Cuando se crea una conversación con otros trabajadores.
- **createDefaultPlannerPlan** - Se crea automáticamente una lista compartida cuando cualquier usuario del grupo Abra la aplicación tareas por primera vez, comprueba la lista automática creada con el servicio de Microsoft Planner. Confirma que la lista de tareas compartida predeterminada se crea correctamente en Planner la primera vez que un usuario intenta crear una lista de tareas compartida.
- **createOrJoinTeam**- Se selecciona el botón **+** para crear un equipo o unirse a él.
- **createPersonalPlan** : Se crea una lista personal, lista de comprobaciones creada con el servicio ToDo. Confirma que se crea una nueva lista de tareas personales en ToDo.
- **createPersonalSubtask** - Confirma que se ha creado correctamente una subtarea personal.
- **createPersonalTask** - Confirma que una tarea personal se ha creado correctamente.
- **createPlan** - Confirma que se ha creado una lista de tareas compartida satisfactoriamente. Confirma que un plan compartido se ha creado correctamente mediante el nivel intermedio.
- **createPlannerPlan** - Se crea una lista compartida, lista de comprobaciones creada con el servicio de Planner. Confirma que se crea una nueva lista de tareas compartida en Planner.
- **createPlannerTask** - Comprueba una llamada al servicio de Microsoft Planner. Confirma que una tarea se ha creado correctamente en una lista de tareas compartida.
- **createShiftClicked** - Cuando un administrador selecciona **Crear un turno**.
- **createShiftOrTimeOffClicked** - Desencadenada si selecciona **Crear un turno** o **Tiempo libre**.
- **createTask**: se usa para cuando se produce un error en la acción de crear, comprueba que se ha llamado al servicio de Planner. Confirma un error en la operación de crear tarea.
- **createTaskList** - Cuando un usuario navega a la vista crear plan desde la vista Inicio.
- **createTeam** - Proporciona datos correctos en torno a la creación o descartar correctamente para la creación de nuevos equipos cuando:
  - El botón **Completado** está seleccionado en la página **Crear equipo**.
  - Se selecciona el botón **Cancelar** en la página **Crear equipo**.
- **createTeam, createChannel** - Esto ofrece datos correctos en torno a la adición satisfactoria de miembros en un equipo y la creación satisfactoria de un nuevo equipo cuando:
  - El botón **Omitir** está seleccionado en la página **Agregar miembros** (primero comprobar el existente).
  - El botón **Completado** está seleccionado en la página **Agregar miembros** (Compruebe primero el existente).
  - Muestra confirmación de creación de canal o de equipo.
- **crossCloudDialogCancel** -  Se selecciona **Cancelar** para un cuadro de diálogo entre nubes.
- **crossCloudDialogJoin** - **Unirse como Invitado** está seleccionada para un cuadro de diálogo para varias nubes.
- **dashboardNav** - Un usuario navega a un mosaico en el panel de chat.
- **dateChanged** - Los usuarios modificaron una fecha de turno.
- **datePickerLaunch** - Confirma que el selector de fecha se ha iniciado correctamente.
- **dayClicked** - Seleccione la vista día cuando el usuario vea sus turnos.
- **daySaved** - Un usuario guarda la disponibilidad del día, guarda un día de turnos.
- **declineTimeOffRequest** - Cuando un usuario declina la solicitud de tiempo libre de trabajo. Es una función clave para el tiempo libre, para que el administrador rechace la solicitud.
- **deleteClicked** - Cuando se selecciona **Eliminar** en detalles de la tarea, lo cual muestra el cuadro de diálogo de confirmación.
- **deleteContact** - Un usuario elimina un contacto privado existente.
- **deleteMeeting** - Seleccione el botón **Eliminar** en la página Detalles de la reunión.
- **deletePersonalTask** - Confirma que una tarea personal se ha eliminado correctamente.
- **deletePersonalSubtask** - Confirma que una subtarea personal se ha eliminado correctamente.
- **deletePersonalVaultItem**: solicitudes de usuarios para eliminar su caja fuerte personal.
- **deletePlannerTask** - Confirma que la operación de eliminación de una tarea compartida se completó correctamente.
- **deleteShift** - Eliminación de turno.
- **duration_picker_dismissed** - Cuando el selector de la duración se descarta.
- **deleteTask** - Comprueba con el servicio Microsoft Planner si una acción de eliminación se ha realizado correctamente o no. Comprueba que la tarea de eliminación ha fallado, es decir, que la eliminación de una tarea no se ha realizado correctamente.
- **deleteVoicemail** - Eliminar el elemento de correo de voz pulsado.
- **demotedToAttendee** - Un usuario degrada un moderador - Botón **Cambiar** en el cuadro de diálogo.
- **denyParticipant** - Número de veces que un usuario niega una entrada de la lista.
- **descriptionChanged** - Confirma que una tarea compartida Descripción ha cambiado correctamente.
- **descriptionClicked** - Cuando un usuario selecciona **Ver descripción** de detalles de la tarea.
- **detailsTabClicked** - Se selecciona la pestaña **Detalles** del en la reunión.
- **deviceAddressBookSync** - Se activa cuando la sincronización de la libreta de direcciones está activada desde la página Configuración.
- **deviceAddressBookUnsync** - Se activa cuando se desactiva la sincronización de la libreta de direcciones en la página Configuración.
- **dialen** - Un usuario elige marcar en una reunión (distintas ubicaciones).
- **dialInBadNetworkBanner** -  Se ha seleccionado **Marcar para acceder** para un banner de conexión deficiente.
- **dialInBadNetworkBannerCancel** - **Marcar para acceder** es cancelado en el cuadro de diálogo nativo.
- **dialInBadNetworkBannerConfirm** - Se confirma el **Marcar para acceder** en el cuadro de diálogo nativo.
- **dialInCall** - **Llamada** está seleccionada en la ventana emergente **Marcar para acceder**.
- **dialInCancel** - **Cancelar** está seleccionada en la ventana emergente **Marcar para acceder**.
- **dialOutCall** : Se desencadena cuando un usuario:
  - Se une en el modo En coche.
  - Selecciona **Llamada** en el menú emergente **Llamarme**.
- **dialOutCallAAD** - Cuando se selecciona cualquier número de **Mis números** en la hoja de acciones
- **dialOutCallRecent** - Cuando se selecciona cualquier número de números recientes anteriores en la hoja de acciones.
- **dialOutCancel** - **Cancelar** está seleccionada en el menú emergente **Llamarme**.
- **dialOutDialog** - **Nuevo número** está seleccionado en la hoja de acciones.
- **dialOutFailRetry** - **Reintento** está seleccionado en un banner de error.
- **Teclado marcado** - Se selecciona el botón **Teclado de marcación** de la lista de llamadas.
- **directShare** - Compartió un vínculo de invitación a una aplicación nativa de SMS o correo electrónico.
- **disableCategory** - Deshabilita un tipo de notificación o deshabilita las notificaciones de llamadas entrantes.
- **deshabilitar** - **Omitir notificaciones** está seleccionado en la experiencia de primera ejecución (FRE). Esto proporciona datos clave para el éxito para omitir la notificación en el flujo del FRE.
- **disableQuietDays** - Días silenciosos deshabilitados. Característica de telemetría de éxito para los días no molestas.
- **disableQuietHours** - Horas silenciadas deshabilitadas.
- **discoverTeams** - Navegar hasta Examinar y unirse a la página Teams.
- **Dismiss_earlycancelledCQF** - Se descarta el formulario de llamada CQF Early Canceled.
- **Dismiss_ratemycallCQF** - Se descarta la tasa de CQF mi formulario de llamada.
- **Dismiss_ratemyliveeventCQF** - Se descarta la tasa de CQF mi formulario evento en directo.
- **dismissBadNetworkBanner** - **Descartar** está seleccionada para un banner de conexión deficiente.
- **dismissFlyout** - El botón **Descartar** está activado.
- **dismissModality** - Se saldrá del selector de modalidad sin compartirlo.
- **dismissModalityPicker**- El botón **Selector de modalidad** está seleccionado.
- **dismissReadReceiptsNotice** - **Recibido** se encuentra seleccionada en un aviso de características.
- **dismissStartRecording** - Descarta un error al iniciar la grabación.
- **dismissStopRecording** - Descarta un error al detener la grabación.
- **dismissUseWifiForVideoBanner** - Se desencadena cuando un usuario descarta un banner:
  - Indica al usuario que el vídeo de participante remoto está bloqueado y que los usuarios tienen que cambiar a WiFi para verlo.
  - Esto indica al usuario que los usuarios tienen que cambiar a WiFi para compartir vídeo.
- **DLPDelete** - Un usuario eliminó un mensaje bloqueado.
- **DLPEdit** - Un usuario ha editado un mensaje bloqueado.
- **DLPOverride** - Un usuario anuló un mensaje bloqueado.
- **DLPOverrideReport** - Un usuario notificó un falso positivo y anuló el mensaje.
- **DLPReport** - Un usuario notificó un falso positivo.
- **DLPResolve** - Un usuario intentó resolver un mensaje DLP.
- **DLPSeeOriginal** - Un usuario ha pulsado para ver un mensaje original.
- **downloadFile** - Ayuda a:
  - Determine si se ha iniciado una operación de descarga.
  - Determine si se ha descargado un archivo correctamente.
- **dragDatePickerHandle**
- **dtmfPSTNCall** - Botón DTMF en teclado marcado fue pulsado.
- **dueDateChanged** - Se desencadena cuando un usuario asigna una DueDate a una tarea.
- **dueDatePickerClicked** - Se desencadena cuando se selecciona el botón **Fecha de vencimiento** en detalles de la tarea, abriendo la página del selector DueDate.
- **dueDateSelected** - Se desencadena cuando un usuario aplica un filtro de DueDate al ver una TaskList.
- **dueDateUnselected** - Se desencadena cuando un usuario no aplica un filtro al duedate mientras visualiza un TaskList.
- **edit** -  Botón **Editar** en un mensaje de chat..
- **editChannel** - Un usuario selecciona un botón para editar un canal de su propiedad o de administración.
- **editContact** - Un usuario edita un contacto privado existente, puede hacerlo yendo a la tarjeta de contacto.
- **editMeetingResponse** - Edita la respuesta a la reunión desde la página de detalles de la reunión.
- **editNavigation** - **Reordenar** está seleccionada en el menú **Más** para editar el orden de las aplicaciones de barra inferior.
- **editRsvpMeetingOptions** - Seleccione **RSVP** para cambiar de la selección anterior.
- **editShiftClicked** - Edite un turno.
- **editSmartReply**: se hace clic en un elemento de respuesta inteligente.
- **editTeam** - Un usuario pulsa un botón para editar un equipo del que es propietario o administrar.
- **editTeam, editChannel** - Relacionada con el éxito agregado de miembros en un equipo y la creación satisfactoria de un equipo existente cuando:
  - Se selecciona el botón **Cancelar** en la página **Agregar miembros** (equipo o canal existente).
  - El botón **Completado** está seleccionado en la página **agregar miembros** (equipo o canal existente).
- **emergencyCall** - Se estableció Llamada de emergencia en plan de llamadas.
- **emergencyCallDirectRouting** - Llamada de emergencia colocada en enrutamiento directo.
- **emergencyCallLocationPolicyBased** - DialEmergency con teclado marcado.
- **emergencycallSecurityDeskNotify** - Llamada de emergencia, informada por el centro de seguridad.
- **enableCategory** - Relacionada con la configuración de notificaciones al activar:
  - Un tipo de notificación
  - Notificaciones de llamadas entrantes
- **habilitado** - Relacionada con la habilitación de la notificación en el flujo de la experiencia de primera ejecución (FRE):
  - **Habilitar las notificaciones** está seleccionada en la experiencia de primera ejecución (FRE).
  - Habilitar está activado en un aviso.
- **habilitar o deshabilitar** - Permisos de llamada o permisos de contacto (solo para Android).
- **habilitado, notNow** - Solicitud de permiso de notificación **aceptar** botón, notificación de primera ejecución (FRE) Permiso de notificaciones (iOS). Esto captura el número de usuarios que han habilitado la característica de notificación y proporciona información.
- **enablediOSPrompt** - En realidad, un usuario habilita las notificaciones en la solicitud de permisos de notificaciones de iOS. Esto ofrece información sobre los usuarios que realmente permiten las notificaciones en iOS desde la solicitud de permisos de notificación.
- **enabledQuietDays** - Días de no molestar habilitados.
- **enableLocationPermission** - Cuando un usuario habilita los permisos de ubicación para la característica ubicación de uso compartido.
- **enableQuietDays** - Un usuario habilita Días de no molestar.
- **enableQuietHours** - Horas silenciadas habilitadas.
- **endEditing** - Botón **Guardar** presionado.
- **endFileShare** - **Volver** está seleccionada en un cuadro de diálogo de uso compartido de archivos.
- **endMyShift** - Número de dispositivos en el modo compartido o el número de veces que se ha cerrado la sesión.
- **endPhotoShare** - **x** de la foto compartida.
- **entryPointClicked** - Seleccionar **Solicitudes** en la pestaña **Programación**. Las solicitudes son para cuando un trabajador de primera línea (FLW) solicite la hora del turno, etc.
- **endPSTNCallSelected** - Un usuario finaliza una llamada de contenido y RTC.
- **endPSTNCallShown** - Se pide al usuario que termine una llamada de contenido o RTC.
- **endVideoShare** - **x** del recurso compartido de vídeo.
- **errorShown** - Se muestra un error.
- **expand/collapse** - La sección de contactos de dispositivo y contactos de la empresa.
- **expandCollapseSection** : Pulse en un encabezado de sección para expandir o contraer una sección.
- **Se esperaba: atMention-Android: chatSendMessage-iOS: sendMsg** - @mención de un bot en un cuadro de redacción.
- **Expected: botClickCardAction - Android: showCard - iOS: missing**: tocar en los botones de tarjeta. Las tarjetas son construcciones clave de la plataforma y la medida del uso y el patrón es necesaria para entender el uso de la plataforma y echar un vistazo a los posibles problemas en el lado del cliente.
- **Se esperaba: chatSendMessage-iOS: composeSendMessage** - Pulse en **responder** y responder a un bot de chat en un canal.
- **Se esperaba: composeSendMessage-Android: replyChannel-iOS: no se encuentra** - Pulse en **responder** y responder a un chat de robots en un canal.
- **Se esperaba: messageLike - Android: reactLike_CM** como un mensaje de un bot.
- **Se esperaba: messageUnread-Android: markAsLastUnread** - Opciones del menú contextual de mensajes para un mensaje de un bot.
- **federatedUpgradeNewChat** - Chat heredado se actualiza a nativo.
- **archivos** - Realiza un seguimiento de si la lista de archivos se completa correctamente en la pestaña archivos de chat y canales.
- **fileSelected** - Se ha seleccionado una presentación de PowerPoint.
- **fileThumbnailPreviewDownloaded** - Ayuda a identificar si una miniatura se representó correctamente para un archivo.
- **fileThumbnailPreviewFromCache** - Captura en caso de que las miniaturas se muestren correctamente en la caché y ayuda a identificar si la miniatura se representó correctamente para un archivo.
- **fileThumbnailPreviewNotAvailable** - Ayuda a identificar si la miniatura se representó correctamente para un archivo.
- **fillFrameVideo** - Rellenar marco desde la hoja de acciones.
- **firstTimeSignedIn** Evento de inicio de sesión y suscripción activado por:
  - Inicio de sesión correcto.
  - El primer inicio de sesión se realizó correctamente.
  - Un usuario ve los errores de inicio de sesión.
  - Registrar la telemetría de las directivas de MAM/MDM implementadas el primer inicio de sesión.
  - Instalación de la aplicación de registro parámetros de referencia después de iniciar sesión correctamente por primera vez.
- **fitToFrameVideo** - Ajustar al marco de la hoja de acciones.
- **flipCamera** - Voltear cámara.
- **forcedUpdateAccept** - Un usuario acepta actualizar la versión de la aplicación en el cuadro de diálogo Force Update.
- **forcedUpdateExit** - Un usuario cierra la aplicación en lugar de actualizar la versión de la aplicación en el cuadro de diálogo Force Update.
- **forcedUpdatePrompt** - Se usa en situaciones en las que los usuarios de versiones anteriores, que es posible que no tengan las últimas correcciones de seguridad y privacidad, deben ponerse en contacto con usted.
- **formattingBold** - Un usuario selecciona el formato de negrita.
- **formattingHighlight** - Un usuario selecciona resaltar formato.
- **formattingImportant** - Un usuario selecciona importancia.
- **formattingItatlics** - Un usuario selecciona cursiva.
- **formattingTextColor** - Un usuario selecciona formato de color del texto.
- **formattingUnderline** - Un usuario selecciona el subrayado.
- **Enciclopedia-no como asignada** - Registra la telemetría sobre las directivas de MAM/MDM en el inicio de la aplicación. Telemetría para la integración de Intune para MAM y MDM. Ofrece datos correctos sobre errores durante la experiencia de primera ejecución (FRE).
- **freActionClicked** - **Comenzar**, **Intentarlo más tarde** o **Cerrar** (GPS) en la experiencia de primera ejecución (enciclopedia).
- **freDone** - Se ha completado la experiencia de primera ejecución (FRE).
- **freTriggered** - Un usuario ve el reloj de la hora en la experiencia de primera ejecución (enciclopedia).
- **funSearchQueryEntered** - Fue ingresada una búsqueda en Giphy Datos de éxito de la característica de datos adjuntos de giphy en Teams.
- **funSelectItem** - Giphy la imagen elegida. Datos de éxito de la característica de datos adjuntos de giphy en Teams.
- **galleryImage** - Imagen cargada - Galería.
- **get_directions_clicked** - Se ha seleccionado el botón **Obtener instrucciones**.
- **giphyUserDisabled**: el usuario elige rechazar los términos o las condiciones de Giphy.
- **giphyUserEnisabled**: el usuario elige aceptar los términos o las condiciones de Giphy.
- **goToNotificationSettings** - Vaya a la página Configuración de notificaciones de **hemos actualizado la configuración de notificaciones** cuadro de diálogo.
- **GPSPromptClicked**: **Permitir** o **No permitir** está seleccionada en un símbolo del sistema operativo. Permite o no GPS.
- **group_map_closed** - Un usuario abre la vista de mapa desde el chat.
- **group_map_open** - El usuario cierra la vista del mapa.
- **groupCallJoin** - Un usuario se une a una llamada de grupo.
- **groupClicked** - Realiza un seguimiento de la hora a la que un usuario selecciona el grupo Shift.
- **guideMe** - Los usuarios seleccionan un banner que les informa sobre las notificaciones de bloqueo de las aplicaciones 3P y ofrece instrucciones de solución de problemas.
- **hamburgerMenu**: navegar al menú Hamburguesa. El menú Hamburguesa contiene acciones importantes, como el cambio de cuenta, la configuración de notificaciones, la configuración de datos y la configuración del perfil.
- **handoffComplete** - En este dispositivo se entrega una reunión o llamada
- **handoffJoin** La opción de entrega de la reunión está seleccionada en la hoja de acciones.
- **hardwareAudioOff** - Desactivar el audio por medio de los botones físicos.
- **hardwareAudioOn** - Activar el audio por medio de los botones físicos.
- **ocultar** - Ocultar el chat.
- **hideChannel** - Oculta un canal de la lista equipos y canales.
- **imagen** - imagen.
- **immediateCallForward** - Se configura el destino de reenvío de llamada inmediata, o bien se permite el desvío de llamadas inmediata (llamar a mí está deshabilitado).
- **importanceToggleClicked** - Se desencadena cuando el campo **!** se activa dentro de los detalles del elemento de tarea.
- **importantMessage_select** - Un usuario selecciona un mensaje importante en el menú contextual de prioridad.
- **importantMessageSend** - Un usuario envía un mensaje importante.
- **inCallDialOut** - Un usuario selecciona el botón **Devolver llamada** desde más opciones en la llamada en curso.
- **initiatePhotoShare** - Iniciar el compartir foto.
- **initiateVideoShare** - Inicia el uso compartido de vídeo.
- **Install** - Instalar o Evento de instalar.
- **installReferrer** - Instalar la aplicación de grabación parámetros de referencia después de la primera instalación.
- **invisionWhiteboardClicked** - la pizarra Invision está seleccionada:
  - La pestaña de **Archivos de canal**.
  - La pestaña de la reunión de **los archivos de chat** pestaña.
- **inviteFreemium**- Pulse el botón **+** en la pantalla Invitar.
- **inviteGuest** - Pulse el botón **+** en la pantalla Invitar.
- **joinFromDeeplinkInTeams** - Un usuario se ha unido a través de un vínculo profundo en la aplicación Teams.
- **joinFromDeeplinkOutsideTeams** - Un usuario se ha unido a través de un vínculo profundo desde fuera de la aplicación equipos.
- **joinFromJoinLauncher** - Un usuario se ha unido desde un iniciador de participación en reuniones.
- **joinFromNudge** - Un usuario se ha unido desde una sugerencia de productividad.
- **joinFromStore** - Un usuario se ha unido después de descargar la aplicación de la tienda de aplicaciones.
- **joinMeeting** - Detecta el éxito o error al unirse a las reuniones desde el calendario en los siguientes casos:
  - Unirse a la reunión a través de marcar para acceder.
  - Unirse a la reunión a través de Llamarme de vuelta.
  - Únase al contenido de la reunión.
  - Seleccione el botón **Unirse a la reunión** en la vista Agenda.
- **joinOptionsEdu** - Un usuario de EDU selecciona opciones para unirse a una reunión programada y se muestran las opciones correctas.
- **joinTeam** - Se presiona el botón **Unirse**.
- **joinViaCode** - Un usuario se une a la reunión a través de un código.
- **labelPickerClicked** - Confirma que el selector de etiqueta se inició correctamente.
- **labelSelected** - Confirma que una etiqueta se ha seleccionado correctamente.
- **labelUnselected** - Confirma que una etiqueta se ha desactivado correctamente.
- **launchLinksGallery** - Cuando un usuario entra en la galería de vínculos desde el panel.
- **launchSlideshow**: el usuario inicia el visor de imagen a pantalla completa de presentaciones con diapositivas entre una de las tres posibles ubicaciones de característica de la aplicación. 
- **La fuente de inicio, como directa, vínculo, appShortcut** -inicia directamente o a través de un vínculo (grabación de la administración de aplicaciones móviles (MAM) o la telemetría de la administración de dispositivos móviles (MDM) en el inicio de la aplicación para recopilar datos para usuarios activos).
- **leaveChat** - Confirma que se deja el chat.
- **legacyChatLink** - Se selecciona un vínculo a un chat heredado.
- **link** - Un usuario ha iniciado el canje de un vínculo de invitación entrando a la aplicación de Teams.
- **likeAppDismiss** - Cuando se pregunta si un usuario le gusta la aplicación o no se descarta sin respuesta.
- **likeAppNo** - Cuando aparece el mensaje en el que se pregunta si el usuario le gusta la aplicación recibe la respuesta no.
- **likeAppYes** - Cuando aparece el mensaje en el que se pregunta si el usuario le gusta la aplicación recibe una respuesta de sí.
- **likeMsg** - Seleccionar **Me gusta**.
- **linkPreviewCancel** - Entienda el comportamiento del cierre de la versión preliminar.
- **listUserClicked** - Cuando un usuario selecciona un usuario mientras trabaja ahora.
- **liveCaptions** - Los títulos en directo están activados o desactivados.
- **liveEventAdditonalLink** - Se ha seleccionado un vínculo adicional.
- **liveEventInfo** - Se selecciona el botón **Info**.
- **liveEventJoin** - Un usuario se une a un evento en directo.
- **liveEventLeave** - Se presiona el botón **Salir**.
- **liveEventPresenterJoin** - Un evento en directo se une por un moderador.
- **liveEventPresenterJoinAsAttendee** - Un moderador de eventos dinámicos Unido como asistente.
- **liveEventQnA** Se selecciona el icono de **Q&A**.
- **liveEventYammer** - Se selecciona el icono de **Yammer**.
- **liveMeetingPushNotificationClicked** - La notificación de inserción está seleccionada.
- **liveMeetingToastClicked** - Se ha seleccionado la notificación del sistema en la aplicación.
- **live_location_in_chats_from_profile_clicked** - en la vista perfil está seleccionado **Ubicación en directo**.
- **lobbyPickAudio** - Número de veces que un usuario cambia la salida de audio del vestíbulo.
- **lobbyToggleMuted** - Número de veces que un usuario ha activado o desactivado el micrófono de la sala de espera.
- **lobbyToggleVideo** - Número de veces que el vídeo está activado o desactivado por el usuario en la sala de espera.
- **logOutClicked** - Cuando un usuario cierra la sesión.
- **location_active_tracking** - El dispositivo de un usuario se cambia a un seguimiento activo.
- **locationCard** - Seleccione una tarjeta de ubicación.
- **location_family_sync** - Se muestran los miembros de un grupo de familias que se crearon en la aplicación de la familia MSA. Confirma que se muestran todos los miembros de la familia que pueden conceder permiso.
- **location_data_use_privacy_denied** - El usuario ha denegado la aceptación de los términos de privacidad.
- **location_group_map_sync** - Se abre vista de mapa.
- **location_map_load carga de vista del mapa** -Carga de vista de mapa.
- **location_map_markers_load**: cargar vista del mapa. Confirma que los marcadores de ubicación para todos los usuarios que comparten activamente se muestran correctamente en la vista del mapa.
- **location_message_send** - Un usuario inicia una sesión para compartir la ubicación.
- **location_data_use_privacy_denied** - Un usuario descarta o selecciona **Ahora no** en un elemento emergente que explica el uso de los datos de ubicación por TFL.
- **location_data_use_privacy_granted** - Un usuario selecciona **Permitir** en el menú emergente en el que se explica el uso de los datos de ubicación por TFL.
- **location_settings_open** - Un usuario abre la configuración de ubicación.
- **location_sharing_start** - Los usuarios comparten su ubicación en un chat.
- **location_sharing_stop** - Un usuario deja de compartir su ubicación en directo en un chat.
- **loginFailed** - El usuario no puede iniciar sesión.
- **loginSuccess** - El usuario pudo iniciar sesión.
- **logoutVault**: el usuario cierra sesión en la aplicación y en la caja fuerte. 
- **manageBlockedNumbers**: acceda a números bloqueados mediante la Configuración.
- **manageVaultKey**: el usuario cambia la opción para administrar la clave de su caja fuerte (MSA o autoseguimiento)
- **manualSend Se**: se envía un mensaje manualmente.
- **mapAppPicker** - Cuando un usuario selecciona la aplicación de mapas que quiere usar al pulsar en una tarjeta de ubicación.
- **markAsRead** - Marcar como leído.
- **markAsUnread** - Marcar como no leído.
- **markChannelRead** - Un usuario marca un canal leído.
- **messageBookmarkMessage** - Se guarda la tarjeta del conector. Usa la telemetría existente con datos específicos de la aplicación. O guardar un mensaje de bot.
- **markAsLastUnread** - Menú contextual de la tarjeta del conector.
- **maskCallerId** - Un usuario habilita o deshabilita la configuración de llamada para enmascarar la identificación de quien llama.
- **meetingAttachmentFileClick** - Se hace clic en un elemento de datos adjuntos de una reunión.
- **meetingAttachmentFileOpciones** - Se hace clic en las opciones de un elemento de datos adjuntos de una reunión.
- **meetingAttachmentSeeMoreClick** - Se hace clic en el botón Ver más de los datos adjuntos de una reunión.
- **meetingDetailCalendarList** - Página de detalles de la reunión seleccionada en calendarList o seleccione la pestaña **Detalles** en la página Detalles de la reunión.
- **meetingDetailChatWithParticipants** - Charle con los participantes de la página de Detalles de la reunión.
- **meetingDetailDeleteMeetingforSelf** - Eliminar una reunión de la página de detalles de la reunión para uno mismo.
- **meetingDetailJoin** - Se selecciona el botón **Unirse a la reunión** en la página Detalles de la reunión.
- **meetingDetailParticipants** - Ver todos los participantes de la página de detalles de la reunión.
- **meetingDetailScheduledMeeting** - Página de detalles de la reunión seleccionada en el objeto reunión programada (**...**), o bien seleccione la pestaña **Detalles** de una reunión programada.
- **meetingDetailSearchParticipants** Se seleccionó **Buscar** en los participantes de la reunión en la programación de reuniones.
- **meetingInsightFileClick** - Se hace clic en un elemento de archivo relacionado con la reunión.
- **meetingInsightFileLocatorClick** - Se hace clic en el botón de sugerencia de localizador de contenido relacionado con la reunión.
- **meetingInsightFileOptions** - Se hace clic en las opciones de un elemento de archivo relacionado con la reunión.
- **meetingInsightSeeMoreClick** - Se hace clic en el botón Ver más del contenido relacionado con la reunión.
- **meetingJoinLeave** : Permanece pulsado -> **x** es pulsado después de pulsar el botón **Unirse**.
- **meetingJoinNow** - **Unirse ahora al** VOIP seleccionada.
- **meetingJoinNowWithCallMe** - Un usuario se une a una reunión con **Llamarme**.
- **meetingJoinNowWithPSTN** - Un usuario se une a una reunión con marcar para acceder.
- **meetingLeaveChat** - Abandonar el chat.
- **meetingMuteChat** - Silenciar chat.
- **meetingNotesCreatedInChatLink** - El Chicklet creado de las **Notas de la reunión** se ha seleccionado en un chat de reunión privada o en un chat de reunión de canal. 
- **meetingNotesMentionCharLink** - Se selecciona el vínculo de la @mención en chat privado de reuniones.
- **meetingNotesMentionChatLink** - Se selecciona el vínculo @mención en el chat de reuniones del canal.
- **meetingNotesTabEntryPoint** - La pestaña **Notas de la reunión** está seleccionada en reunión privada o en un canal.
- **meetingNotificationSettingsAccepted** - La opción de configuración de notificaciones se cambió a Únicamente aceptadas.
- **meetingNotificationSettingsAll** - La opción de configuración de notificaciones se cambió a Todos.
- **meetingNotificationSettingsNone** - La opción de configuración de notificaciones se cambió a Ninguna.
- **messagePriority_select** - Un punto de entrada de prioridad de mensaje está seleccionado.
- **messageSeeOriginal** - Un usuario revierte el mensaje convertido al original.
- **meetingSeeParticipantsChatDetails** - Ver a todos los participantes.
- **memberListLoadMore** - Desplácese hacia abajo para cargar más.
- **messagedEditMessage** - Un usuario edita un mensaje.
- **messageShareMessage** - Compartir un mensaje.
- **messageTranslate** - Un usuario traduce un mensaje.
- **messageUnabletoEdit** - Un usuario no puede editar un mensaje.
- **meetingUserAnonB2B** - B2B anónimo se incorporó a la reunión.
- **meetingUserAnonB2C** - B2C anónimo se incorporó a la reunión.
- **meetingUserDialIn** - RTC (marcar para acceder) el usuario se unió a la reunión.
- **meetingUserDialOut** - PSTN llama a un usuario posterior unido a la reunión.
- **meetingUserFederated** - Un usuario federado se ha unido a la reunión.
- **meetingUserFreemium** - Un usuario freemium se ha unido a la reunión.
- **meetingUserGuest** - Un usuario invitado se ha unido a la reunión.
- **meetingUserTenant** - Un usuario de cuenta empresarial se ha unido a la reunión.
- **memeGenerated**: se genera un meme a partir de la entrada con imagen y datos de texto de un usuario. 
- **messageCopyMessage** - Copiar mensaje.
- **messageDelete** - Eliminar mensaje.
- **messageEditMessage** : Editar mensaje.
- **messageForwardMessage** - Un usuario selecciona un punto de entrada hacia adelante en el menú contextual del mensaje.
- **messageLike/messageUnlike** - Message me gusta o No me gusta.
- **messageMuteSender** - Silenciar o reactivar el audio del remitente.
- **messageLike** - Tarjeta de conectores me gusta. Usa la telemetría existente con datos específicos de la aplicación.
- **messageScheduledMeeting** - Objeto de reunión en el canal seleccionado (no solo los programados).
- **messageTriggered** - Es cuando se activa una notificación para un mensaje.
- **micPermissionCancel** - **Cancelar** está seleccionada en el cuadro de diálogo Permission MIC.
- **micPermissionGoToSettings** - Un usuario se desplaza a la configuración del cuadro de diálogo de permisos del MIC.
- **MicrosoftWhiteboardClicked** - Se selecciona Microsoft pizarra en la pestaña **Archivos de canal** o en la pestaña **Archivos de conversación de reuniones**.
- **moreOptionsClicked** - Se desencadena cuando el menú contextual **...** en la parte superior derecha se encuentra seleccionado en la pantalla del editor de elementos de tarea.
- **moveTaskClicked** - Opción en más lista de opciones del elemento de tarea.
- **multiCallEndFromUFD** - Número de veces que un usuario termina la llamada en espera en un escenario de varias llamadas.
- **multiCallResumeFromUFD** - El número de veces que un usuario selecciona para reanudar la llamada en espera.
- **multiCallSwitch** - Número de veces que un usuario selecciona una opción para cambiar la llamada y se muestra una lista de las llamadas en espera.
- **multipleAccounts** - Número de cuentas de un usuario.
- **multipleTenants** - Número de inquilinos por cuenta.
- **mute** - Silenciar el chat.
- **muteOnWhiteboard** - Un usuario se silencia o se silencia en la pantalla de la pizarra.
- **muteParticipant** - Silenciar al participante (ir a la hoja de acciones).
- **my_location_button_clicked** - El usuario centra el mapa en su ubicación al seleccionar el botón **Mi ubicación**.
- **my_location_clicked** - Un usuario centra el mapa en su ubicación al seleccionar el **punto azul** en el mapa.
- **myShiftPickerClicked**: solo se registra si la solicitud enviada es un cambio o una oferta. Se selecciona el selector **Mi turno**.
- **nameGroupChat** - Nombre de chat de grupo.
- **nativeTimeClockBreak** - Un descanso en el tiempo.
- **nativeChatLink** - Se ha seleccionado un vínculo a un chat nativo.
- **navActivity** - Vaya a la página fuentes de actividades.

- **navBookmark** - Un usuario navega a la pestaña o aplicación **Guardada** en la barra inferior o en la bandeja de la aplicación.
- **navCalendar** - Mide si un usuario navega a un calendario.
- **navCallingSettings** - Un usuario se desplaza a la configuración de llamadas.
- **navCalls** - La pestaña **Llamadas** es pulsada.
- **navCamera** - Un usuario navega a la pestaña o la aplicación **Cámara** en la barra inferior o en la bandeja de la aplicación.
- **navChat** - Un usuario navega a la pestaña o a la aplicación **Chat** en la barra inferior o en la bandeja de la aplicación.
- **navContacts** - Un usuario navega hasta la pestaña o aplicación **Contactos** o **Personas** en la barra inferior o en la bandeja de la aplicación.
- **navDashboardTab** - Un usuario navega a la pestaña **Panel** dentro de una conversación.
- **navDynamics365** - Se desencadena cuando se abre la aplicación Dynamics365.
- **navFiles** - Está seleccionada la aplicación de archivos, realiza un seguimiento de si un usuario puede iniciar la aplicación archivos en la bandeja de aplicaciones (iOS).
- **navFilesTab** - Está seleccionada la aplicación de archivos, realiza un seguimiento de si un usuario puede iniciar la aplicación archivos en la barra de navegación inferior (iOS).
- **navMeetings** - Se ha pulsado la pestaña **Calendario**.
- **navNotes** - Se desencadena cuando se abre la aplicación de Notas.
- **navOrganization** - Se desencadena cuando se abre la aplicación de la organización.
- **navOrgChart** - Se desencadena cuando se abre la aplicación de OrgChart.
- **navPeople** - El evento se activa cuando se abre la aplicación contactos.
- **navPeopleSettings** - Se desencadena cuando navega a la categoría **personas** en el menú configuración.
- **navPersonalFiles** - Está seleccionada la aplicación de archivos, realiza un seguimiento de si un usuario puede iniciar la aplicación archivos en la barra de navegación inferior (Android).
- **navPhotoTab** - Pestaña **Foto**.
- **navSaved** - Un usuario navega a la pestaña o aplicación **Guardado** en la barra inferior o en la bandeja de la aplicación.
- **navSelectPlan** - Cuando un usuario selecciona un plan compartido para navegar en la vista Inicio.
- **navSelectPersonalList** - Cuando un usuario selecciona un plan personal para navegar en la vista Inicio.
- **navSelectSmartList** - Cuando un usuario selecciona un plan inteligente al que navegar desde la vista Inicio.
- **navTasks** - Se desencadena cuando se abre la aplicación de tareas.
- **navTeams** - Pulse **Ver todos**.
- **navVideocamera** - Un usuario navega a la pestaña o la aplicación **Cámara** en la barra inferior o en la bandeja de la aplicación.
- **navVideoTab** - En la pestaña **Video**.
- **navVoicemail** - Un usuario navega a la página de correo de voz.
- **navWalkieTalkie** un usuario ha abierto la aplicación talkie de walkie.
- **navWiki** : se desencadena cuando se abre la aplicación wiki.
- **newChat** - Un usuario crea un chat.
- **newCall** - Pulsa el botón **Nueva llamada**.
- **newCallDialPad** - Pulsa el botón **teclado marcado** en la pestaña.
- **newCallPeople** - Pulsa el botón **Personas** en la pestaña.
- **noBGActivityDetected** - Supera el umbral de errores de actividad en segundo plano.
- **notBlockedDevice** - Un usuario no llega al umbral de errores de actividad en segundo plano en un plazo de 30 días.
- **notNow** - **No por el momento** está seleccionada en aviso.
- **notNowUpdate** -UpdateDefer.
- **notificationNavChannelConversation** - Iniciar la aplicación con una notificación para una conversación de canal.
- **notificationNavChannelThreadConversation** - Iniciar la aplicación con una notificación para un mensaje específico en una conversación del canal.
- **notificationSettingTurnedOff** - Desactiva las notificaciones de inserción de la aplicación Android de equipos.
- **notificationNavPreCall** - Un usuario recibe una notificación de la reunión empieza que la desplaza a la pantalla de pre-llamada en la selección.
- **ocvFeedback** - Relativo al rendimiento del formulario de comentarios de OCV.
- **ocvFormCancelled** - Un evento enviado cuando el formulario de comentarios OCV se cancela y el usuario vuelve a la aplicación.
- **ocvFormOpened** -Un evento enviado cuando se abre el formulario OCV.
- **ocvFormSubmit** - Un evento enviado cuando el usuario hace clic en Submit en el OCV formulario de comentarios.
- **offerRecipientClicked** - Solo se registra si la solicitud se ha enviado una oferta. El usuario escribe el selector de miembros del equipo para ofrecer un turno. La oferta significa ofrecer un cambio de hora.
- **offerSwapShiftFromL1** - Tipo de cambio que un usuario intenta ofrecer o cambiar desde una lista de turnos. iOS es una **SwipedRight** y una acción de Android es **LongPressed**.
- **offerSwapShiftFromL1Triggered** - Un usuario le ofrece cambiar un turno por otro usuario.
- **officeLens** - Se desencadena cuando la aplicación inicia la característica officeLens Camera, ya sea cuando:
  - Un usuario intenta adjuntar una foto al mensaje
  - Un usuario intenta tomar una foto y cargarla directamente en la galería.
- **officeLens o cameraImage** - Cámara seleccionada - cámara estándar u Office lens.
- **onBackClicked** - Cuando la flecha atrás está seleccionada para navegar atrás en una página.
- **oneNote** - cuando un usuario abre la aplicación de OneNote.
- **open** - Pulsar administración de notificaciones.
- **abrir editar** - Wiki uso de la telemetría: el usuario selecciona para editar el wiki.
- **openApp** - Abra una aplicación personal.
- **openAppDrawer** - se ha seleccionado **Más** en la barra inferior para abrir el cajón de aplicaciones.
- **openEditMeetingForm** - Se selecciona el botón **Editar** en la página Detalles de la reunión.
- **openFile** - Ayuda a:
  - Identificar un archivo pudo abrirse correctamente en el chat.
  - Identificar que se pudo abrir un archivo desde una lista de archivos.
  - Comprobar si se pueden abrir archivos desde una lista de OneDrive.
  - Identificar los archivos abiertos se pueden abrir desde una lista de canales.
  - Determinar si se pueden abrir archivos desde chats grupales.
  - Determinar si se puede abrir un archivo correctamente desde la aplicación archivos.
  - Determinar si se puede abrir un archivo de mensaje desde el Chicklet correctamente.
  - Determinar si los archivos de la lista recientes pueden abrirse correctamente.
  - Determinar si se puede abrir un archivo de la lista de archivos correctamente.
  - Determinar si se puede abrir un archivo desde un archivo de mensajes Chicklet.
  - Determinar si se pueden abrir archivos correctamente desde una lista de archivos.
- **openInAppClicked** - Opción dentro del elemento de tarea más lista de opciones, solo disponible para tareas personales.
- **opensCalendarView** - Pulse en **Turnos abiertos** en la apertura de la pestaña **Programación**.
- **openContactCard** - Un usuario pulsa en el icono de **Contacto** o en un contacto de la aplicación contactos para iniciar la tarjeta de perfil del contacto.
- **openContactCard_ReactionSummary** - Desplácese hasta tarjeta de contacto en la página Resumen de la reacción.
- **openFileInApp** - Le ayuda a identificar si los usuarios han optado por abrir archivos por fuera de Teams en oposición a por dentro de Teams.
- **openHamburgerMenu** - Se selecciona el icono **hamburguesa** (superior izquierda) para abrir el menú lateral para tener acceso a configuración, presencia y conmutador de inquilino.
- **openInStream** - Abra un vídeo en secuencia.
- **openMeetingDetails** - Abra la página Detalles de la reunión o la página de detalles de la reunión en una reunión en particular.
- **openModalityPicker** - X = ChatsAndChannels para chats y canales.
- **openNewMeetingForm** - Confirma que una subtarea personal se ha actualizado correctamente.
- **openNewMeetingForm** - Abra el programador mientras configura una nueva reunión.
- **openPhotoLibrary** - Seleccione una biblioteca de fotografías.
- **openQuietDays** - Vaya a la página días de no molestar.
- **openQuietHours** - Vaya a la página de horas de no molestar.
- **openReactionHoverBubble** - Presione el botón **agregar respuesta** en la página Resumen de la reacción.
- **openReactionSummary** - Invocar al Consumer de reacción.
- **openSettingsSetUpInstructions** Abrir la **Configuración** de instrucciones.
- **penSharedLink** - Cuando un usuario abre un enlace desde el mosaico de enlaces del panel o la galería de enlaces.
- **openShiftsClicked** - Cuántos usuarios han pulsado el icono **Calendario**.
- **orgChart - No hay AS asignado** - Telemetría de uso básico para organigrama.
- **pageEntered** - Un usuario ha introducido una página.
- **parental_consent_grant** - Un usuario concede permiso a un leve en su MSFamily para usar la característica de ubicación dinámica de TFL.
- **parental_consent_remove** - Un usuario revoca el permiso para un leve en su MSFamily a usar la característica ubicación dinámica de TFL.
- **pauseVoicemail** - **Pausa** es pulsado en un elemento de correo de voz.
- **peoplePickerInvoked** - El selector de personas se usa en siete lugares de equipos móviles, entre los que se incluyen (entre otros):
  - Nuevo selector de chat.
  - Reenvía un mensaje.
  - Agregar un participante a una reunión.
- **personalAppNavBotChat** - Desplácese hasta el bot en la aplicación personal.
- **personalAppNavTab** - Vaya a las pestañas de la aplicación personal.
- **photoLibraryPicker** - **Abrir la biblioteca fotográfica** es pulsada dentro del selector de imágenes.
- **pickGalleryPhoto** - Elija una foto de la galería.
- **pickParticipantChatDetails** - Elija un usuario de la lista.
- **pickRecentPhoto** - Selecciona una imagen reciente para compartir.
- **pinChannel** - Ancla un canal para mostrarlo por sobre la lista de equipos y canales.
- **pinSelf** - Anclar a mi mismo desde la hoja de acciones.
- **el pinUs** - Anclar un usuario de la hoja de acciones.
- **place_created** - El usuario creó un lugar compartido.
- **place_deleted** - El usuario eliminó un lugar compartido.
- **place_edited** - El usuario editó un lugar compartido.
- **reproducir** - Reproducir la grabación.
- **playVoicemail** - **Reproducir** es pulsado en el elemento de correo de voz.
- **plusButtonClicked** - Selecciona el botón **Más** (**+**).
- **pptNextSlide** - Siguiente diapositiva como moderador o en vista privada.
- **pptPreviousSlide** - Diapositiva anterior como moderador o en vista privada.
- **pptReturnToPresenter** - Vaya a la diapositiva **En directo** (en la que está activada el moderador y todos los demás usuarios).
- **pptStopPresenting** - Detener la presentación.
- **pptTakeControl** - Tomar control.
- **preJoinAddRoom** - El botón **Agregar una sala** está seleccionada en la lista desplegable predefinida, **Unirse** está seleccionada en el escenario **Agregar una sala**.
- **preJoinAudioOff** - Se selecciona el botón **audio desactivado** en la lista desplegable predefinida.
- **preJoinAutoAddRoom** - **Unirse ahora** está seleccionado cuando una sala está cerca.
- **preJoinBack** - Los botones **Atrás** o **Cerrar** están seleccionados.
- **preJoinDenied** - Un usuario no puede unirse a una reunión.
- **preJoinDeviceAudio** - **Unirse con audio de dispositivo** está seleccionado en lista desplegable.
- **preJoinDialIn** - El botón **Marcar para acceder** se ha seleccionado en la lista desplegable pre-unirse.
- **preJoinDialInCall** - Un usuario confirma la solicitud de **marcar para acceder** al pre-unirse.
- **preJoinDialInCancel** - Un usuario cancela la **marcar para acceder** en pre-unirse
- **preJoinDialOut** - El botón **Llamarme de vuelta** se ha seleccionado en la lista desplegable predefinida.
- **preJoinDialOutCall** - Un usuario confirma la solicitud de **llamarme de nuevo** al pre-unirse.
- **preJoinDialOutCancel** - Un usuario cancela la solicitud de **llamarme de nuevo** al pre-unirse..
- **preJoinPSTNOptions** - Un usuario selecciona una lista desplegable para otras opciones de combinación.
- **priorityChange** - Se desencadena cuando se aplica el filtro prioridad cuando se visualiza una lista de tareas.
- **priorityPickerClicked** - Se desencadena cuando un usuario se desplaza al selector de filtro de prioridad desde la pantalla de filtro de la lista de tareas.
- **privateMeetingJoin** -  El botón **Unirse a una reunión** se ha pulsado en un chat privado.
- **processInBG** - Procesar la notificación entrante en segundo plano (Android).
- **processInFG** - Procesar la notificación entrante en primer plano (Android).
- **progressItemClicked** - Confirma que un usuario ha abierto satisfactoriamente el selector de progreso para una tarea.
- **promotedToPresenter** - El usuario promueve un asistente, **botón cambiar** en el cuadro de diálogo.
- **provideFeedbackDismiss** - Descarta el mensaje que le pregunta si el usuario desea enviar comentarios sobre por qué no me gusta la aplicación.
- **provideFeedbackNo** - Responder no a la solicitud que pregunta si el usuario desea enviar comentarios sobre el motivo por el que no le gusta la aplicación.
- **provideFeedbackYes** - Responder sí a la solicitud que pregunta si el usuario desea enviar comentarios sobre el motivo por el que no le gusta la aplicación..
- **provideRatingDismiss** - Descartar el mensaje que pregunta si el usuario desea evaluar nuestra aplicación en la tienda de aplicaciones después de decir que le gusta la aplicación.
- **provideRatingNo** - Responder no a la solicitud que pregunta si el usuario desea evaluar nuestra aplicación en la tienda de aplicaciones después de decir que le gusta la aplicación.
- **provideRatingYes** - Responder sí a la solicitud que pregunta si el usuario desea evaluar nuestra aplicación en la tienda de aplicaciones después de decir que le gusta la aplicación.
- **proximityPermissionDismissed** Se descarta el banner de permisos.
- **proximityPermissionGranted** - El permiso se muestra en la ventana emergente.
- **proximityPermissionViewed** - Se pulsa el banner de permisos.
- **pushNotification** - Los eventos desencadenantes:
  - Iniciar por notificación.
  - Servicio de notificaciones de inserción
  - Se pulsa en la notificación de inserción de reconexión.
  - **Error al conectar** la notificación de inserción es pulsada.
- **quickNotificationAction** - Cuando un usuario interactúa con una de las respuestas de acción rápida en una notificación (como la capacidad de enviar un mensaje directamente desde la notificación de inserción).
- **quickSelectImagePicker** - Selección rápida.
- **quickStartLiveEventJoin** - Inicio rápido evento en directo es unido por un usuario.
- **quietHoursValues** - Captura el estado de las horas de silencio al navegar el botón atrás.
- **quotedReplySent** - Un usuario ha enviado un mensaje de respuesta con el tipo de contexto.
- **reactAngry_CM** - Reaccionar con enfadado desde el menú contextual.
- **reactAngry_HB** - Reaccionar con enfadado desde la burbuja flotante.
- **reactHeart_CM** - Reaccionar con el corazón de el menú contextual.
- **reactHeart_HB** - Reaccionar con el corazón desde la burbuja flotante.
- **reactLaugh_CM** - Reaccionar con risas desde el menú contextual.
- **reactLaugh_HB** - Reaccionar con risas desde la burbuja flotante.
- **reactLike_CM** - Reaccionar con Me gusta en el menú contextual o como un mensaje de bot.
- **reactLike_doubleTap** - Reacciona con un Me gusta desde la doble pulsación.
- **reactLike_HB** - Reaccionar con like desde la burbuja flotante.
- **reactSad_CM** - Reaccionar con triste en el menú contextual.
- **reactSad_HB** - Reaccionar con triste desde la burbuja de flotante.
- **reactSurprised_CM** - Reaccionar con sorpresa en el menú contextual.
- **reactSurprised_HB** - Reaccionar con la sorpresa en la burbuja flotante.
- **reactRemoved_HB** - Cuando un usuario retira la reacción de la experiencia de la página de resumen de la reacción.
- **readReceipts** - Característica habilitada por el usuario.
- **redeemInvite** - En el canje de la aplicación.
- **redeemLinkInAppStart** - El usuario ha iniciado el canje de un vínculo de invitación desde la aplicación de Teams.
- **refreshCalendarList** - Tire hacia abajo para actualizar la vista Agenda.
- **refreshLinksGallery** - Cuando un usuario desliza el dedo hacia abajo para actualizar la galería de vínculos.
- **removeAssignee** - Confirma que una tarea asignada se elimina de la vista selector de la asignación (en lugar de *assignmentRemoved* que se activa al seleccionar **x** fuera de la vista del selector de asignaciones).
- **removeMeeting** - Seleccione **Quitar del calendario** de la página de detalles de la reunión de la reunión cancelada.
- **removeParticipantFromEditMeeting** - Quitar un participante después de seleccionar **Editar reunión** de la reunión en la página Detalles de la reunión.
- **removeParticipantFromNewMeeting** - Quitar un participante de la página del programador mientras se configura una nueva reunión.
- **removeReplyObject** - Un usuario ha quitado un objeto de respuesta de redacción.
- **removeUser** - Confirma que un encargado se elimina de la vista del selector de asignaciones (en lugar de *assignmentRemoved* el que se activa al seleccionar **x** fuera de la vista del selector de asignaciones).
- **removeUser_CM** - Cuando un usuario quita una persona a través de la lista de participantes de charla.
- **removeUserConfirm** - Un usuario confirmó un diálogo quitar usuario.
- **removeUserContextMenu** - Un usuario ha quitado un participante mediante el menú contextual.
- **removeUserSwipe** - Un usuario ha quitado un participante mediante un deslizamiento.
- **reorderChannelItem** - Un usuario reordena canales anclados.
- **reportAbuseConfirmation** - Cuando un usuario selecciona el botón **Completado** en la pantalla de confirmación.
- **reportAbuseOpen** El número de veces que la **informar de un problema** botón está seleccionada en el menú contextual.
- **reportAbuseSend** - Cuando un usuario selecciona el botón **Informar**, la telemetría debe almacenar el tipo de informe seleccionado.
- **replyChain** - Se ha seleccionado el botón o cuadro de texto **Nuevo mensaje** en la cadena de respuesta (hilo).
- **replyChannel** - Se ha seleccionado el botón **Responder** en canales.
- **replyNavigation** - El objeto respuesta se ha seleccionado para navegar a la publicación de referencia.
- **replySendMessage** - Enviar respuesta de canal.
- **replyViaMsgOptions** - El usuario inició la respuesta mediante el menú contextual.
- **replyViaSwipe** - El usuario inició la respuesta mediante el dedo.
- **requestActedOn** - Se desencadena cuando un administrador actúa sobre las solicitudes de los turnos abiertos.
- **requestActionClicked** - Cuando un usuario solicita una acción, por ejemplo, cuando se selecciona la solicitud para un turno (ya sea una vista de administrador de trabajador de primera línea (FLW) o un trabajador de primera línea.
- **requestDetailsClicked** - Cuando se selecciona la solicitud para un turno (ya sea una vista de administrador de los trabajadores de primera línea (FLW) o un trabajador de primera línea).
- **requestJoinTeam** - El botón de **solicitud** está presionado.
- **requestSent** - Inicia sesión si se ha enviado una solicitud.
- **requestToJoinTeam** - Solicitud de unirse al equipo (público o privado).
- **requestToJoinTeamError** - Error con la solicitud de combinación.
- **requestTypeClicked** - Determinar el tipo de solicitud que las personas seleccionan en el selector solicitudes.
- **resetLocalVault**: el usuario restablece y borra todos los datos de caja fuerte del dispositivo.
- **resolveIssue** - **Resolve** está seleccionada en el control flotante solucionador de problemas de notificaciones para ir a la aplicación bloqueador.
- **responseClicked** - Un usuario selecciona una página de respuesta.
- **retryButtonClicked** - El botón **Reintentar** está seleccionado.
- **returnToMessage** - Se selecciona el botón **Regresar** para volver al mensaje.
- **runningLate** - El usuario va con retraso.
- **safeLink** - El vínculo se ha verificado como seguro.
- **saveEditMeeting** - Seleccione el botón **Guardar** mientras se encuentre en la página programador de reuniones después de actualizar una reunión.
- **saveNewMeeting** - Seleccione el botón **Guardar** mientras se encuentre en la página programador de reuniones. Para registrar reuniones guardadas correctamente y el porcentaje de reuniones que no se pudieron crear debido a un error del lado del cliente o del servicio.
- **savePlanClicked** - El desencadenador **Crear** se ha seleccionado en el nuevo creador del plan de la apertura predeterminada de la aplicación.
- **scenarioChannelDashboard** - El usuario navega a un icono en el panel.
- **scenarioDashboardNav** - El usuario navega a la pestaña del panel en una conversación (pestaña del mismo nivel que la del chat).
- **scheduledMeetingJoin** - Se selecciona el botón **Unirse a la reunión** en el objeto reunión programada.
- **scrollCalendarList** - Mide el desplazamiento en el calendario.
- **scrollDatePicker** - Se desplaza por el control selector de fecha del calendario.
- **searchAbandoned** - Determina si se ha abandonado la búsqueda.
- **searchCancelled** - Determina si:
  - La búsqueda se ha realizado correctamente o si el usuario ha abandonado la búsqueda.
  - Una consulta de búsqueda se ha realizado correctamente.
- **searchContacts** - Buscar en la lista de llamadas.
- **searchInitiated** - Determina si se puede desencadenar la búsqueda y el origen del desencadenador de búsqueda.
- **searchMeetingParticipants** - Buscar participantes para agregarlos en el formulario del programador. Para distinguir entre el número de citas creadas frente al número de reuniones creadas.
- **searchResultsClicked** - Determina:
  - Si se pueden encontrar resultados relevantes correctamente.
  - Si los resultados de búsqueda provienen de la ficha todas en lugar de un dominio individual.
- **searchTabClicked** - Determina:
  - Información del dominio del resultado de la búsqueda: contactos, chat, mensajes y archivos.
  - Si los resultados relevantes se detectan correctamente.
- **seeAllMeetingParticipants** - Seleccione **Ver todos los** de la página Detalles de la reunión o ver todos los participantes. Registra los datos de usuario en el embudo de calendario, donde los detalles de la reunión del calendario desempeñan un papel importante, esto permite validar selecciones de acceso telefónico, reuniones de equipo, RSVP, etc.
- **seeMeetingDescription** - Abra la página Detalles de la reunión o seleccione **Ver más** en la descripción de la reunión de la página Detalles de la reunión. Los datos se registran en el embudo de calendario, donde los detalles de la reunión del calendario desempeñan un papel importante, ya que le ayuda a validar las selecciones de las aplicaciones de acceso telefónico, reuniones de equipo, RSVP, etc.
- **seeRsvpMeetingOptions** - Selecciona el **Organizador de notificaciones** desde el menú emergente RSVP, o bien seleccione opciones **RSVP** en la página Detalles de la reunión.
- **selectActivityType** - Captura seleccionar gestos en un elemento de la fuente.
- **selectCalendarDate** - Selecciona una fecha específica en el control selector de fecha del calendario.
- **selectDevice** - Seleccionar un dispositivo concreto en la aplicación de muestra.
- **selectGeneralSetting** - Vaya a configuración general.
- **selección** - Se ha seleccionado el contacto con el dispositivo o el contacto empresarial.
- **selectMeetingChicklet** | Reunión.
- **selectMeetingRsvpOption** - Seleccione el botón **RSVP** para elegir una opción.
- **selectMeetingRsvpOptions** - Seleccione el botón **RSVP** para elegir una opción.
- **selectPersonalList** - Confirma que el usuario ha navegado correctamente a una lista de tareas personales pulsando en ella.
- **selectPlannerList** - Confirma que el usuario ha navegado correctamente a una lista de tareas compartida pulsando en ella.
- **selectSettingOption** - Va a la pestaña **Configuración** en el menú hamburguesa.
- **selectTheme** - Habilitar tema oscuro.
- **selectUser** - Confirma que un encargado se ha seleccionado correctamente para una tarea.
- **selfLongPress** - Largo.
- **Send_earlycancelledCQF** - Un usuario envía comentarios sobre CQF formulario de llamada cancelado anticipadamente.
- **send_map_pin_clicked** - Un usuario envía una ubicación estática.
- **Send_ratemycallCQF** - Un usuario envía comentarios sobre CQF tasa mi formulario de llamada.
- **Send_ratemyliveeventCQF** - Un usuario envía un Comentario en CQF tasa mi formulario de evento en directo.
- **sendForward** - Un usuario confirma que se envíe un mensaje reenviado desde el selector de reenvío.
- **sendImage** - Enviar imagen.
- **sendLocation** - Ubicación de envío.
- **sendMsg** - Seleccione **Enviar** en respuesta.
- **sendRequestBulkClicked** - Se registra una vez para cada envío de solicitud en masa.
- **sendRequestClicked** - Se selecciona **Enviar solicitud de cambio de turno**
- **sendVoiceMessage** -  El botón **Grabar** es liberado.
- **Setting/Dismiss** - Configuración de los contactos del dispositivo.
- **settingsNavReadReceiptNotice** - El usuario se ha pasado a la configuración desde la notificación de características.
- **settingsOpened** - Se desencadena cuando la zona horaria del dispositivo del usuario no coincide con la zona horaria del equipo y el usuario se desplaza a la configuración.
- **setupPinVault**: el usuario guarda un elemento anclado de caja fuerte para su cuenta. 
- **shareCharmCompleted** - El usuario ha terminado de compartir un vínculo de invitación mediante el acceso para compartir de la aplicación.
- **shareCharmOpened** - El usuario ha empezado a compartir un vínculo de invitación mediante el acceso para compartir de la aplicación. 
- **shareFile** - Se desencadena cuando **Compartir archivo** está seleccionada. También le ayuda a comprobar si:
  - El usuario pudo iniciar la operación de compartir el archivo.
  - El usuario puede compartir un archivo correctamente.
- **shareHistory** - Seleccionó el selector de historial de uso compartido.
- **shareInto** - Un usuario comparte información de otra aplicación en Teams.
- **sharePlanToChat** - Una lista compartida se comparte manualmente desde la aplicación tareas en el chat grupal como Chicklet, compruebe Chicklet enviado a través del servicio de mensajería back-end.
- **sharePPTFromChannels** - **equipos y canales** está seleccionado.
- **sharePPTFromOneDrive** - **OneDrive** está seleccionada.
- **shareRecording** - Compartir una grabación.
- **shareScreen** - Iniciar o detener un recurso compartido de pantalla.
- **shareShift** - La información que se proporciona al compartir un turno.
- **shareShiftsClicked** - Detalles de un turno abierto.
- **shareTray** - **Compartir...** está seleccionado en la hoja de acciones.
- **shiftAssigneeClicked** - La vista de calendario turnos que muestra los detalles de los turnos concretos.
- **shiftDetails** - Permite ver los detalles de un turno.
- **shiftDetailsCalendar** - El usuario va a los detalles del turno.
- **shiftDetailsMyShifts** - Pulse en **Calendario** en la pestaña **Programaciones**.
- **shiftDetailsTodaysCoworkers** - En la pantalla reloj, se selecciona el botón **Inicio** o **Finalizar descanso**.
- **shortCircuitContactCount** - El número de contactos de cortocircuito coinciden con la libreta de direcciones que se ha recibido de una recopilación de contactos.
- **showBanner** - El número de veces que se muestra el **WiFi conectado, no hay ninguna pantalla** de Internet.
- **showCard**: tocar en los botones de tarjeta. Las tarjetas son construcciones clave de la plataforma y la medida del uso y el patrón es necesaria para entender el uso de la plataforma y echar un vistazo a los posibles problemas en el lado del cliente.
- **shownReadReceiptNotice** - La notificación de características que se muestra a los usuarios con opciones de configuración.
- **signIn** - **Inicio de sesión** está seleccionada en la Página principal, o bien, el botón **Inicio de sesión** está pulsado.
- **signUp** - **Crear una cuenta gratuita** o **Registrarse gratuitamente** están seleccionadas.
- **simultaneousCallForward** - Se desencadena cuando:
  - Se configuró el destino de reenvío de llamada simultánea.
  - El desvío de llamadas simultánea está habilitado (Llamadas márcame y También llamar están habilitadas).
- **skipVerificationForLink** - El usuario decidió omitir la comprobación.
- **smartReply**: se hace clic en el botón de alternancia de respuesta inteligente.
- **SMSSendMessage** - El usuario envía un mensaje SMS.
- **sortChanged** - Se desencadena cuando el usuario cambia el criterio de ordenación mientras ve un TaskList.
- **startEditing** -  El botón **Edición** está seleccionado.
- **startPresentPhoto** - Empezar a presentar foto.
- **startPresentVideo** - Empieza a presentar vídeo.
- **startPSTNCall** - Desencadenado debido a:
  - Resultado RTC en la búsqueda global (contactos).
  - Llamada RTC colocada desde el dispositivo contactCard.
  - Llamada RTC colocada en callList.
  - DialPSTN número por medio del teclado de marcado.
- **startRecording** - Inicia la grabación.
- **startVoicemailCall** - Está seleccionado **Cambiar el saludo del correo de voz**.
- **static_place_selected** - Un usuario arrastra un mapa para seleccionar un sitio estático.
- **statusCheckBoxClicked** - Desencadenador cuando el elemento de tarea se completa o no se completa.
- **statusMsgCancel** - Un usuario cancela el cambio al mensaje de estado.
- **statusMsgExpiry** - Un usuario establece el tiempo de expiración.
- **statusMsgSet** - Un usuario establece un nuevo mensaje de estado.
- **statusPageViaContactCard** - Un usuario escribe el estado de la experiencia de redacción mediante tarjeta de contacto.
- **statusPageViaHamburger** - Un usuario ingresa el estado de la experiencia a través del menú hamburguesa.
- **stop_location_sharing_logout** - Un usuario cierra sesión en la aplicación.
- **stopMeetingButton** - El número de veces que un usuario abandona la sala sin ser admitido en la reunión.
- **stopPresentPhoto** - Dejar de presentar la foto.
- **stopPresentVideo** - Dejar de presentar vídeo.
- **stopRecording** - Detener la grabación.
- **structuredMeetingsBannerDismiss** - Un usuario descarta el banner que les informa sobre su rol de reunión.
- **stuckOnConnectingDialInSelected** - **Marcar desde acceso** está seleccionado en el cajón.
- **stuckOnConnectingRetrySelected** - **Reintentar** está seleccionada en el cajón.
- **stuckOnConnectingShownDismissed** - Un usuario ha descartado el cajón.
- **suggested_place_selected** - Un usuario comparte una ubicación estática al seleccionar un lugar sugerido.
- **switchTeamAction** - Un usuario cambia de equipo en el horario de reloj. Se debe activar después de que el usuario seleccione el equipo al que quiere cambiar.
- **switchTeamsDialogTriggered** - Un usuario ve la pestaña **Cambios**.
- **tabActionCopyLink** - Cómo detectan y usan el vínculo de copia de pestañas en dispositivos móviles.
- **tabActionMoreOptions** Comprende el uso de puntos suspensivos (**...**) en una pestaña.
- **tabActionOpenInBrowser**: uso de abrir en el explorador. Esto es necesario para comprender si los usuarios prefieren abrir una pestaña fuera de Teams.
- **tabActionOpenInBrowserFromTab**: comprender el uso de Abrir en el explorador desde una pestaña para más opciones: detectabilidad y uso.
- **tabActionOpenInTeams**: uso Abrir en. Esta es una forma clave de comprender si la pestaña se puede establecer como Abrir en Teams.
- **tabActionRemove** - Comprende cómo se detecta la opción de eliminación y el uso de la característica.
- **tabActionRename** - Entienda cómo se cambia el nombre reconocible y el uso de la característica.
- **tabActionSetting, Android - Fix** - Cómo los usuarios detectan y usan la configuración de pestañas en dispositivos móviles.
- **table** - Seleccione una tabla.
- **tabListMoreOptions** - Comprende el uso de las opciones Más, de una pestaña.
- **tabOpen** - Registra éxitos en las pestañas de apertura o si hay problemas en la forma en que se abren las pestañas.
- **tabViewed** - Solo se registra si la solicitud que se envía es un cambio, para entradas en el selector de **Cambios de Teams**.
- **takePhoto** - Toma una foto.
- **takePhotoPicker** - **Tomar foto** está seleccionado dentro del selector de imágenes.
- **tapChicletExpand** - Cómo se pueden obtener vistas previas de las tarjetas en móviles.
- **tapDatePickerHandle** - Expande el control selector de fecha del calendario.
- **tapSettings** - El número de usuarios que vuelven a configurar las aplicaciones en dispositivos móviles.
- **tasksAppLaunchAdaptiveCard** - La aplicación tareas se abre desde una adaptivecard en un chat grupal, comprueba el inicio de la aplicación a través de la dirección URL del servicio IC3.
- **tasksAppLaunchComposeExtension** - La aplicación tareas se abre desde la extensión de redacción en un chat grupal, comprueba el inicio de la aplicación a través del servicio MT.
- **tasksAppLaunchDashboard** -la aplicación Tareas se abre desde el icono de panel o un plan específico, compruebe el inicio de la aplicación mediante el servicio MT.
- **tasksAppLaunchDashboardSeeAll** - La aplicación Tareas se abre desde el botón del panel **Ver todos**, comprueba el inicio de la aplicación a través del servicio MT.
- **tasksAppLaunchDefault** - La aplicación tareas se abre desde el alimentador inferior y comprueba el inicio de la aplicación a través del servicio MT.
- **tabCalendarClicked** - Un usuario ha elegido un equipo del selector de equipo.
- **teamChannelChanged**: se desencadena cuando un usuario selecciona y se desplaza a un plan a partir de una lista de planes. Solo se envía a appInsights, no a Aria.
- **teamCreate** - Un usuario selecciona la opción para crear un nuevo equipo.
- **teamEdit** - Un usuario edita un aspecto de un equipo del que es propietario o administra.
- **teamNav** - Ver las opciones de menú de un equipo.
- **teamsDeviceCallResumed** - Un usuario con un periférico conectado a Bluetooth (acoplamiento por teléfono móvil) reactiva una llamada en espera.
- **teamSelectedClicked** - Cuando un usuario selecciona **Equipo seleccionado** para un registro de horas trabajadas.
- **teamShiftPickerClicked** - Cuando un usuario agrega una nueva entrada de salto. El evento se registra cuando el usuario guarda los cambios.
- **tenantSwitch**: sobre conmutación de espacio empresarial. La métrica de éxito de la característica para MTMA (múltiples cuentas y varios espacios empresariales ), le ayuda a identificar y corregir los problemas de manera proactiva y a proporcionar una experiencia de conmutación suave.
- **tenantSwitchUnsupportedError**: error de espacio empresarial no admitido (cuando un usuario ve el error). La métrica de éxito de la característica para MTMA (múltiples cuentas y varios espacios empresariales), permiten la telemetría en torno a errores de la cuenta o el cambio de espacio empresarial, de modo que podemos identificar y corregir los problemas de manera proactiva y proporcionar una experiencia de conmutación suave.
- **timeClockClicked** - Un usuario selecciona el botón **Reloj** en la pestaña Mis turnos.
- **timeOffReasonClicked** - Determinar si se cita el motivo del uso del horario.
- **timesheetAddClicked** - Cuando un usuario agrega una nota a sus ediciones de ruptura. El evento se registra cuando el usuario guarda los cambios.
 **timesheetBreakAdded** - Agregar una nueva entrada de reloj. El evento se registra una vez que se guardan los cambios.
- **timesheetBreakEdited** - Cuando un usuario confirma su registro de horas trabajadas. El evento se registra cuando el usuario llega a la confirmación en la moda.
- **timesheetBreakNoteAdded** - Cuando un usuario elimina su parte de horas. El evento se registra cuando el usuario confirma la eliminación en la moda.
- **timesheetClockAdded** - Cuando un usuario selecciona Editar para un registro de horas trabajadas.
- **timesheetClockEdited** - Cuando un usuario selecciona Guardar en un registro  de horas trabajadas editado.
- **timesheetConfirmed** - Cuando un usuario agrega una nota a las modificaciones de su parte de horas. El evento se registra cuando el usuario guarda los cambios.
- **timesheetDeleted** - Si un usuario tiene o no tiene un recordatorio de turno establecido y la cantidad de minutos previos a un turno en la que un usuario quiere ser alertado.
- **timesheetEditClicked** - Telemetría de configuración de usuario.
- **timesheetEditSaved** - Un usuario pulsa en un registro de horas trabajadas desde el perfil de un usuario para abrir el registro de horas del usuario.
- **timesheetNoteAdded** - Para ver una solicitud de hora de aprobación aprobada.
- **titleChanged** - Se desencadena cuando cambia el título de un elemento de tarea. el desencadenador de cada carácter cambia.
- **toast** - Está seleccionado la notificación del sistema dentro de la aplicación.
- **toggleChannelsInChat** - Activa o desactiva la característica. Indicadores de éxito de la característica para charlas unificadas y experiencia de canal.
- **toggleClicked** - Está activada la opción de alternancia.
- **transferNow** - Se desencadena cuando:
  - Un usuario selecciona **Transfer** > **Transferir ahora**.
  - El destino de transferencia se configura para un usuario.
  - El destino de transferencia está establecido en un número de teléfono.
- **translateFailed** - Error de traducción (excepto sin conexión). Presentar métricas de éxito para la función de traducción de mensajes.
- **trigger_created** - El usuario creó una geovalla.
- **trigger_deleted** - El usuario eliminó una geovalla.
- **unansweredCallForward** - Se ha establecido un destino de reenvío de llamada sin responder. También permite el desvío de llamadas no respondidas (Llámame está habilitado y Si no hay respuesta está habilitado).
- **unblockCaller** - Desbloquear:
  - Un contacto o un número de la hoja de acciones.
  - Un contacto o un número de una tarjeta de contacto.
  - Número de la configuración.
- **unblockChat** - Desbloquea un bot de chat.
- **unpinChannel** - Desanclar un canal.
- **unpinSelf** - Desanclarse de la hoja de acciones.
- **unpinUser** - Desanclar un usuario de la hoja de acciones.
- **unsafeLink** - Se determinó que un vínculo no es seguro.
- **updatePersonalTask** - Confirma que una tarea personal se ha actualizado correctamente.
- **updatePlaybackSpeedVoicemail** - Se cambia el valor de la velocidad de reproducción del correo de voz.
- **updateTask** - Se ha producido un error en la acción de confirmar tareas de actualización.
- **updateTaskState**: confirma que se ha actualizado el estado de la tarea. Acción.
- **actualización** - Seleccione el botón **actualizar** en el menú **Más**.
- **uploadFile** - Un usuario selecciona **Cargar desde el dispositivo**.
- **uploadSelectedFile** - Activado en estas circunstancias:
  - Carga de archivos en el canal correctamente.
  - Cargar archivos en chat correctamente.
  - Cargue los archivos en la ventana de respuesta.
  - Cargar archivos correctamente en el chat grupal.
  - Uso de escenario principal.
  - El inicio del escenario de carga en el canal.
  - El escenario de inicio de la carga en el chat.
  - El comienzo de la situación de carga en el canal.
  - Cargue un archivo en la pestaña **Archivos** correctamente.
  - Si se actúa durante la carga del archivo
  - Si un archivo seleccionado se carga correctamente.
- **uploadSelectFile** - Seleccionar un archivo correctamente; Seleccione correctamente el botón **Cargar archivo**.
- **urgentMessageSelect** - Selecciona un mensaje urgente en el menú contextual de prioridad.
- **urgentMessageSend** - Envía un mensaje urgente.
- **URL** - URL.
- **urlPreview** - versión preliminar de URL.
- **urlPreviewAdd** - Agregar versión preliminar de URL.
- **urlPreviewOpen** - Versión preliminar de URL abierta.
- **urlPreviewRemove** - Previsualización de URL eliminada.
- **userConfiguration** - Para ver una solicitud de tiempo libre pendiente.
- **userJoinedViaShareLink** - Un usuario se ha unido a una reunión desde un vínculo.
- **userLongPress** - Mantener presionado un participante.
- **userProfileOpened** - Un usuario selecciona un icono de **Usuario** para abrir un perfil de usuario.
- userTimesheetOpened ** - Un usuario selecciona un parte de horas en el perfil de un usuario para abrir el parte de horas de esa persona.
- **useWifiForAudioDialog** - Un usuario selecciona **Aceptar** mientras el sistema se lo solicita, mientras un administrador bloqueó las llamadas de audio y vídeo en la red móvil.
- **useWifiForVideoDialog** - Se desencadena cuando:
  - **Aceptar** se selecciona mientras el sistema se lo solicita, mientras que un administrador ha bloqueado las llamadas de vídeo en celulares.
  - Intentando habilitar el vídeo en la reunión y un administrador lo ha bloqueado en la red celular.
  - **Aceptar** se selecciona mientras el sistema se lo solicita, mientras que un administrador ha bloqueado el vídeo en las reuniones de la red celular.
- **videoUserDoubleTap** - Pulse dos veces en un participante de vídeo.
- **viewChannelMembers** - Ver la lista de miembros del canal.
- **viewContactCard** - ContactCard seleccionado desde:
  - Un elemento callHistory.
  - Un elemento de correo de voz.
  - Una lista de llamadas.
- **viewed** - Un usuario ha visto una página.
- **viewFullAllDayMeetingList** - La vista de agenda en dispositivos móviles.
- **viewLobbyFromBanner** - El número de veces que un usuario selecciona **Ver sala de espera** en un banner de notificación.
- **viewMeetingDetails** - Seleccione el menú **...** en la página Detalles de la reunión. Que conciernen al uso del menú **Más** en los calendarios de dispositivos móviles.
- **viewMeetingOccurrence** - Abre los detalles de la reunión de una instancia de una reunión periódica. Telemetría para registrar datos de usuario a través del embudo del calendario, donde los detalles de la reunión del calendario juegan un papel importante, que ayuda a validar selecciones de marcado, reuniones de equipos, confirmaciones de asistencia, etc.
- **viewMeetingSeries** - Para registrar la representación satisfactoria de una serie de reuniones en los siguientes casos:
  - Al pasar de una instancia a la página de detalles de la reunión de la serie.
  - Al seleccionar **Ver serie** de la página detalles de la reunión.
- **viewOrgChart** - Telemetría de uso básico para un gráfico de organización.
- **viewRequests** - Se presiona el botón **ver solicitudes**.
- **voiceDataCollectionOptOut** - Un usuario se da de baja de la grabación desde el móvil haciendo clic en el banner.
- **correo de voz: no hay AS asignado** - Un orador pulsa en un elemento de correo de voz.
- **whiteboardUsed** - Un usuario anota en una pizarra (cualquiera de las acciones que se muestran en ella).
- **wiki - No hay AS asignado** - Telemetría de uso de wiki.
- **poorNetworkBanner**: se muestra el banner de red deficiente.
- **badNetworkBanner**: se muestra el banner mala conexión de red.

### <a name="panelview"></a>PanelView

> [!NOTE]
> Para obtener información sobre las propiedades de los eventos Panelview, consulte[Propiedades que se envían con los eventos panelview](#properties-sent-with-panelview-events).

- **fileDeleteFailed**: se desencadena cuando se produce un error en la operación de eliminación de archivos.
- **fileDeleteSuccess**: se desencadena cuando una operación de eliminación de archivos concluye con éxito.
- **filePreview**: se desencadena en los escenarios siguientes:
  - Cuando se pulsa la opción compartir en la pantalla de vista previa de archivo.
  - Cuando se copia la opción compartir en la pantalla de vista previa de archivo.
  - Cuando se descarga la opción compartir en la pantalla de vista previa de archivo.
  - Cuando se carga correctamente una vista previa de archivo.
- **file**: se desencadena en los escenarios siguientes:
  - Cuando se muestra una vista previa de un archivo en la aplicación de Teams.
  - Cuando la opción de carga de archivos está pulsada en la pantalla archivos de OneDrive.
  - Cuando la opción "Copiar link" se pulsa en la pantalla de vista previa de archivo.
  - Cuando se descarta la pantalla de uso compartido de archivos.
  - Cuando se abre el menú de opciones de archivos o cuando se pulsa una de las opciones de ese menú.
  - Cuando se abre la pantalla de archivos "en una llamada".
  - Cuando se pulsa un archivo para abrirlo.
- **filesChannel**: se desencadena cuando se abre la pantalla de archivos de canal.
- **fileSources** : se desencadena cuando se abre el menú de opciones de archivos o cuando se pulsa una de las opciones de ese menú.
- **filesPersonal**: se desencadena cuando un lote de archivos se carga en OneDrive o en la pantalla de archivos recientes.
- **fileUploadDeleteTriggered**: se desencadena cuando se eliminan los datos adjuntos de un archivo o se separan del área de mensaje.
- **fileUploadFailed**: se desencadena cuando se produce un error en la operación de carga de archivos.
- **fileUploadIndividualNotification**: se desencadena cuando cambia el contenido de la notificación de carga de archivo o cuando se interactúa con la notificación. Las interacciones pueden incluir gestos como deslizar el dedo para descartar la notificación o pulsar la notificación, etc.
- **fileUploadSuccess**: se desencadena cuando se resuelve un error en la operación de carga de archivos.
- **fileUploadSummaryNotification**: se desencadena cuando cambia el contenido del resumen de carga de archivo o cuando se interactúa con la notificación. Las interacciones pueden incluir gestos como deslizar el dedo para descartar la notificación o pulsar la notificación, etc.
- **meetingFiles**: se desencadena cuando se abre la pantalla archivos de reunión.
- **meetNowActionSheet**: se activa cuando el usuario crea una reunión Reunirse ahora.
- **navPersonalFiles**: se desencadena cuando se realiza la navegación a la pantalla de archivos.

### <a name="scenario"></a>Escenario

> [!NOTE]
> Para obtener información sobre las propiedades de los eventos PanelAction, vea [Propiedades que se envían con eventos de escenario](#properties-sent-with-scenario-events).

- **app_incremental_sync_launch**: confirma si el recuento de píldoras se actualiza correctamente para el lanzamiento en frío.
- **app_incremental_sync_resume**: confirma si el recuento de píldoras se actualiza correctamente para el lanzamiento en caliente o tibio.
- **app_start_cold**: para supervisar el lanzamiento de aplicaciones en frío (solo para Android).
- **app_start_hot**: para supervisar el lanzamiento de aplicaciones en caliente (solo para Android).
- **app_start_warm**: para supervisar el lanzamiento de aplicaciones en tibio (solo para Android).
- **chat_add_giphy**: confirma si la acción de representación gif de Giphy se ha hecho correctamente o con errores.
- **cortanaError** - Para supervisar el error de Cortana que se produce.
- **cortanaView** - Para supervisar la aparición del lienzo de Cortana.
- **cortanaRestart** - Para supervisar el reinicio de Cortana.
- **cortanaSetNewConversation** - Para supervisar el establecimiento de una nueva conversación de Cortana.
- **cortanaSpeechRecognization** - Para supervisar la latencia de reconocimiento de voz de Cortana.
- **cortanaStart** - Para supervisar el inicio de backend de Cortana.
- **cortanaStartListening** - Para supervisar cuándo Cortana empieza a escuchar.
- **cortanaStopListening** - Para supervisar cuándo Cortana deja de escuchar.
- **cortanaThinking** - Para supervisar el cambio de estado de Cortana a pensando (esperando por la respuesta del servicio).
- **cortanaTokenRefresh** - Para supervisar la actualización del token de Cortana en primer plano.
- **cortanaWarmingUp** Para supervisar el inicio de preparación de Cortana (Cortana está abierta, pero el token sigue capturando).
- **cortana_admin_policy_refresh** - Para supervisar la actualización de la directiva de administración de Cortana.
- **cortana_background_token_refresh** - Para supervisar la actualización del token de Cortana.
- **cortana_initialization** - Para supervisar los pasos de inicialización de Cortana.
- **cortana_sdk_events** - Para supervisar los eventos relacionados con la activación de Cortana.
- **cortana_skill_action_execution** - Para supervisar la ejecución de acciones de Cortana.
- **cortana_skill_action_delay** - Confirma el inicio de la acción de retraso.
- **cortana_watchdog** - Para supervisar el proceso de recuperación de watchdog de Cortana.
- **create_default_plan_and_nav_to_view** - Confirma la creación correcta de una lista de tareas compartida predeterminada y el tiempo que tardó un usuario en posicionar la vista posterior resultante en la acción.
- **create_personal_plan_and_nav_to_view** - Confirma la creación correcta de una lista de tareas personales y el tiempo que tardó un usuario en encontrarse en la vista posterior resultante de la acción.
- **create_personal_task** - Confirma la creación correcta de un elemento de tarea personal.
- **create_planner_plan_and_nav_to_view** - Confirma la creación satisfactoria de la lista de tareas compartida y la duración que tardó un usuario en la vista resultante de la acción.
- **create_planner_task** - Confirma la creación satisfactoria de un elemento de tarea compartida.
- **forwardExistingAmsObject** Confirma si la acción de reenvío multimedia se ha hecho correctamente o con errores.
- **delete_personal_plan** - Confirma la eliminación correcta de una lista de tareas personales.
- **delete_personal_task** - Confirma que un elemento de tarea personal se elimina correctamente.
- **delete_planner_plan** - Confirma que la eliminación de la lista de tareas compartida se haya realizado correctamente.
- **delete_planner_task** - Confirma que un elemento de tarea compartida se elimina correctamente.
- **get_sender_sub_scenario** - Obtenga el subescenario Sender en la actividad.
- **load_chat_plans_list** - Confirma la recuperación exitosa de los planes del planificador para la vista del plan de un chat.
- **load_home_page** - Confirma la recopilación satisfactoria de listas de tareas personales y compartidas para la vista principal.
- **load_personal_task_list** - Confirma la búsqueda exitosa de las tareas de una lista de tareas en la vista de lista de tareas.
- **load_shared_task_list** - Confirma la búsqueda exitosa de las tareas de una lista de tareas compartida en la vista de lista de tareas.
- **load_smart_task_list** - Confirma la recopilación satisfactoria de las tareas inteligentes de una lista de tareas para la vista de lista de tareas.
- **meetingAttachmentRender** - Confirma la representación de datos adjuntos de reunión.
- **meetingInsightFetch** - Confirma la captura de contenido relacionado con la reunión.
- **meetingInsightLocatorRender** - Confirma la representación de la sugerencia de localizador de contenido relacionado con la reunión.
- **meetingInsightRender** - Confirma la representación del contenido relacionado con la reunión.
- **meetingInsightVisible** - Confirma la visibilidad del contenido relacionado con la reunión.
- **open_image** Confirma si la representación de imágenes a pantalla completa se ha representado correctamente o con errores.
- **rename_personal_plan** - Confirma que el cambio de nombre de una lista de tareas personales se ha realizado correctamente.
- **rename_planner_plan** - Confirma que el cambio de nombre de una lista de tareas compartida se ha realizado correctamente.
- **save_image** Confirma si la imagen guarda la acción correctamente o con errores.
- **share_image** Confirma si la imagen comparte la acción correctamente o con errores.
- **smart_reply_enabled**: confirma que la respuesta inteligente está habilitada para el usuario actual.
- **smart_reply_received** : confirma que se recibe una sugerencia de respuesta inteligente.
- **tenantSwitchUnsupportedError**: confirma que la respuesta inteligente no se puede mostrar para el usuario actual.
- **park_call_for_hold_v2**: confirma si poner la llamada en espera con el estacionamiento de llamadas se realizó con o sin éxito.
- **unpark_call_for_hold_v2**: confirma si continuar la llamada sin el estacionamiento de llamadas se realizó con o sin éxito. 
- **update_planner_task_and_nav_to_view** - Confirma la correcta actualización de un elemento de tarea compartida y cuánto tiempo tardó un usuario en llegar a la vista resultante después de la acción.
- **update_planner_task_and_nav_to_view**: confirma la correcta actualización de un elemento de tarea personal y cuánto tiempo tardó un usuario en llegar a la vista resultante después 
- **updatePlannerTask**: confirma que un usuario ha actualizado correctamente una tarea en una lista de tareas compartida.
- **upload_images** Confirma si la imagen carga la acción correctamente o con errores.
- **upload_voice_messages** Confirma si el mensaje de voz carga la acción correctamente o con errores.
- **voiceMessageUpload** Confirma si el mensaje de voz carga la acción correctamente o con errores.
- **cancel_channel_meeting** confirma si la cancelación de una reunión de canal se hizo correctamente o no.
- **cancel_meeting** confirma si la cancelación de una reunión se hizo correctamente o no.
- **cancel_private_meeting** confirma si la cancelación de una reunión privada se hizo correctamente o no.
- **edit_channel_meeting** confirma si la edición de una reunión de canal se hizo correctamente o no.
- **edit_meeting** confirma si la operación de edición de una reunión se hizo correctamente o no.
- **server_fetch_agenda_view** confirma si la sincronización de eventos de calendario mediante la API de nivel medio se hizo correctamente o no.
- **server_fetch_date_picker_view** confirma si la sincronización de eventos de calendario mediante la API de REST de Outlook se hizo correctamente o no.
- **server_fetch_agenda_view_group** confirma si la sincronización de eventos de calendario mediante la API de nivel medio para el grupo TFL se hizo correctamente o no.
- **server_fetch_date_picker_view_incremental** confirma si la sincronización incremental de eventos de calendario mediante la API de REST de Outlook se hizo correctamente o no.
- **meeting_details** confirma si la sincronización de detalles de la reunión se hizo correctamente o no.
- **show_meeting_participants** confirma si la lista de participantes de la reunión se hizo correctamente o no.
- **search** Confirma que la sesión de búsqueda completa se ha realizado correctamente o ha fallado.

## <a name="property-lists"></a>Listas de propiedades

### <a name="properties-sent-with-all-events"></a>Propiedades enviadas con todos los eventos

| Nombre de la propiedad                    | Descripción                                                          |
|----------------------------------|----------------------------------------------------------------------|
| EventInfo_Time                   | Hora de generación de evento                                                |
| EventInfo_Name                   | Nombre del evento - Se usa para diferenciar entre los tipos de evento               |
| EventInfo_BaseType/Name          | Tipo de evento - Se usa para diferenciar entre los tipos de eventos en un evento.   |
| EventInfo_Source                 | Origen de la generación del evento                                       |
| AppInfo_Language                 | Idioma de la aplicación                                                         |
| AppInfo_ETag                     | ID de experimento asignado a un usuario                                     |
| DeviceInfo_OsBuild               | Versión de compilación del SO                                              |
| UserInfo_Mri                     | Escriba un identificador de usuario                                                       |
| Session_RunId                    | Tipo de un identificador de sesión                                                 |
| DeviceInfo_DetailModel           | Modelo del dispositivo.                                                  |
| UserInfo_TimeZone                | Zona horaria del usuario                                                |
| DeviceInfo_OsName                | Nombre de SO del dispositivo                                                       |
| DeviceInfo_NetworkProvider       | Proveedor de red de dispositivos                                              |
| DeviceInfo_Model                 | Modelo del dispositivo                                                         |
| DeviceInfo_NetworkType           | Información de la red del dispositivo                                                  |
| UserInfo_Language                | Idioma de usuario: parecido al idioma de la aplicación                              |
| client_ring/UserInfo_Ring        | El anillo del usuario le ayuda a publicar características para los primeros usuarios.           |
| UserInfo_Id                      | Id. de usuario                                                              |
| UserInfo_TenantId                | ID. del espacio empresarial                                                            |
| EventInfo_SdkVersion             | Versión del SDK usada para generar el evento                               |
| DeviceInfo_Id                    | ID de dispositivo proporcionada por el sistema operativo del dispositivo                                      |
| eventpriority                    | Prioridad de un evento                                                 |
| DeviceInfo_Make                  | Fabricante del dispositivo                                                  |
| AppInfo_Version                  | Versión de la aplicación                                                   |
| DeviceInfo_OsVersion             | Versión del sistema operativo del dispositivo                                                    |
| Session_Id/SessionId             | Identificador de la sesión de la solicitud                                            |
| Session_Environment              | Entorno de sesión                                                  |
| isNetworkIssue                   | Captura información si hubo un problema de red mientras se atiende la solicitud |
| UserRole                         | Rol de usuario en un espacio empresarial                                                |
| Tenant_Model                     | Captura si se trata de una cuenta gratuita o empresarial.          |
| licenseType/UserInfo_LicenseType | Tipo de licencia asignada al usuario                                    |
| UserLocale                       | Configuración regional en la que se está teniendo acceso a la aplicación                                |
| Intune_sdkVersion                | Versión del SDK de Intune                                            |
| Intune_sdkBundleVersion          | Versión detallada del SDK de Intune                                   |
| AppInfo_Environment              | Entorno en el que se está teniendo acceso a la aplicación                         |

### <a name="properties-sent-with-panelaction-events"></a>Propiedades enviadas con eventos panelaction

| Nombre de la propiedad         | Descripción                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | URL del recurso al que tiene acceso la acción del usuario                  |
| Panel_Url             | URL del panel entregado al usuario                             |
| Action_Gesture        | Tipo de gesto que realiza el usuario en la aplicación                       |
| Action_ScenarioType   | Agrupación de características que está relacionada con la métrica empresarial de la característica       |
| Panel_Type            | Tipo de panel al que obtuvo acceso el usuario.                                    |
| Action_Outcome        | Resultado de la acción efectuada por el usuario                            |
| Team_Id               | Identificación del equipo en el que el usuario ha realizado la acción           |
| Module_Type           | Tipo de módulo que ha alojado la acción del usuario                        |
| Module_Name           | Nombre del módulo que ha alojado la acción del usuario                        |
| Module_Summary        | Resumen del módulo que ha alojado la acción del usuario                      |
| Thread_Id             | Identificador de la conversación al que obtuvo acceso el usuario.                         |
| Panel_PreviousUrl     | URL del panel anterior                                          |
| Panel_Region          | Región donde se hospeda el panel en la aplicación                       |
| Panel_LaunchMethod    | Método mediante el que se inició el panel                        |
| Panel_PreviousType    | Tipo del panel anterior                                         |
| Thread_Type           | Tipo de hilo al que tiene acceso el usuario.                                    |
| Module_State          | Estado del módulo al que tiene acceso el usuario.                               |
| Action_Scenario       | Característica en un grupo de características que está relacionada con el sistema métrico de la empresa |
| Panel_LaunchSource    | Información de origen del panel que se inició                  |
| Tab_Type              | Tipo de la pestaña a la que obtiene acceso el usuario.                                   |
| Team_Type             | Tipo de equipo al que tiene acceso el usuario.                                      |

### <a name="properties-sent-with-panelview-events"></a>Propiedades enviadas con eventos PanelView

| Panel_Url          | URL del panel entregado al usuario                   |
|--------------------|----------------------------------------------------------|
| Panel_Type         | Tipo de panel al que obtuvo acceso el usuario.                          |
| Team_Id            | Identificación del equipo en el que el usuario ha realizado la acción |
| Thread_Id          | Identificador de la conversación al que obtuvo acceso el usuario.               |
| Panel_PreviousUrl  | URL del panel anterior                                |
| Panel_Region       | Región donde se hospeda el panel en la aplicación             |
| Panel_LaunchMethod | Método mediante el que se inició el panel              |
| Panel_PreviousType | Tipo del panel anterior                               |
| Thread_Type        | Tipo de hilo al que tiene acceso el usuario.                          |
| Panel_LaunchSource | Información de origen del panel que se inició        |
| Tab_Type           | Tipo de la pestaña a la que obtiene acceso el usuario.                         |
| Team_Type          | Tipo de equipo al que tiene acceso el usuario.                            |

### <a name="properties-sent-with-scenario-events"></a>Propiedades enviadas con eventos de escenario

| Nombre de la propiedad        | Descripción |
|----------------------|-------------|
| Scenario_Status      | Estado de un escenario: abandonar/aceptar/ERROR |
| Scenario_Step        | Cuando un escenario contiene varios pasos con puntos de error diferentes, esta propiedad captura detalles sobre el paso |
| Scenario_StatusCode  | Registros de propiedad código de estado del escenario basado en el éxito o error de escenario |

### <a name="properties-sent-with-trace-events"></a>Propiedades enviadas con eventos de seguimiento

| Nombre de la propiedad | Descripción                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| Trace_message | Contiene una cadena de error y detalles sobre los motivos por los que puede haberse producido un error. |
