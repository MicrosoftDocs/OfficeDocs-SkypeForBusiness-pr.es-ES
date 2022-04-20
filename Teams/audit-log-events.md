---
title: Buscar eventos en el registro de auditoría en Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
description: Obtenga información sobre cómo recuperar Microsoft Teams datos del registro de auditoría en el portal de cumplimiento de Microsoft Purview.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 744a18f2a8f7f2ed406853ef7efbc9842d0096f5
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922641"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Buscar eventos en el registro de auditoría en Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

El registro de auditoría puede ayudarle a investigar actividades específicas en Microsoft 365 servicios. Para Microsoft Teams, estas son algunas de las actividades que se auditan:

- Creación de equipos
- Eliminación de equipos
- Agregación de canales
- Canal eliminado
- Configuración de canal cambiada

Para obtener una lista completa de las actividades de Teams que se auditan, consulte [Teams actividades](#teams-activities) y [Turnos en las actividades de Teams](#shifts-in-teams-activities).

> [!NOTE]
> Los eventos de auditoría de canales privados también se registran como para equipos y canales estándar.

## <a name="turn-on-auditing-in-teams"></a>Activar la auditoría en Microsoft Teams

Antes de poder ver los datos de auditoría, primero debe activar la auditoría en el portal de cumplimiento de Microsoft Purview. Para obtener más información, consulte [Activar o desactivar la auditoría](/microsoft-365/compliance/turn-audit-log-search-on-or-off).

> [!IMPORTANT]
> Los datos de auditoría solo están disponibles desde el punto en que se activó la auditoría.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperar datos de Microsoft Teams del registro de auditoría

1. Para recuperar registros de auditoría para actividades de Teams, vaya a <https://compliance.microsoft.com> y seleccione **Auditoría**.

2. En la página **Buscar** , filtre las actividades, las fechas y los usuarios que desea auditar.

3. Exporte los resultados a Excel para continuar el análisis.

Para obtener instrucciones detalladas, vea [Buscar el registro de auditoría en el Centro de cumplimiento](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

> [!IMPORTANT]
> Los datos de auditoría solo están visibles en el registro de auditoría si la auditoría está activada.

El período de tiempo que un registro de auditoría se conserva y se pueden buscar en el registro de auditoría depende de su Microsoft 365 o Office 365 suscripción, y específicamente del tipo de licencia que se asigna a los usuarios. Para obtener más información, consulte la [descripción del servicio centro de cumplimiento & seguridad](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Sugerencias para buscar el registro de auditoría

Aquí encontrará sugerencias para buscar actividades de Teams en el registro de auditoría.

:::image type="content" alt-text="Captura de pantalla de la página de búsqueda de registros de auditoría en el Centro de cumplimiento" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- Puede seleccionar actividades específicas para buscar haciendo clic en la casilla situada junto a una o más actividades. Si se selecciona una actividad, puede hacer clic en ella para cancelar la selección. También puede usar el cuadro de búsqueda para mostrar las actividades que contienen la palabra clave que escriba.

  ![Captura de pantalla de la lista desplegable de actividades en la página de búsqueda de registros de auditoría](media/audit-log-search.png)

- Para mostrar los eventos de las actividades ejecutadas con cmdlets, seleccione **Mostrar resultados para todas las actividades** en la lista **Actividades** . Si conoce el nombre de la operación para estas actividades, escríbala en el cuadro de búsqueda para mostrar la actividad y, a continuación, selecciónela.

- Para borrar los criterios de búsqueda actuales, haga clic en **Borrar todo**. El intervalo de fechas vuelve al valor predeterminado de los últimos siete días.

- Si se encuentran 5000 resultados, probablemente puede suponer que hay más de 5000 eventos que cumplen los criterios de búsqueda. Puede restringir los criterios de búsqueda y volver a ejecutar la búsqueda para devolver menos resultados, o bien puede exportar todos los resultados seleccionando **ExportarDescargar** >  todos los resultados. Para obtener instrucciones paso a paso para exportar registros de auditoría, vea [Exportar los resultados de búsqueda a un archivo](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file).

Consulte [este vídeo](https://www.youtube.com/embed/UBxaRySAxyE) para usar la búsqueda de registros de audio. Únase a Ansuman Acharya, un administrador de programas de Teams, como demuestra cómo realizar una búsqueda de registros de auditoría para Teams.

## <a name="teams-activities"></a>actividades de Teams

Esta es una lista de todos los eventos que se registran para las actividades administrativas y de usuario en Teams en el registro de auditoría Microsoft 365. La tabla incluye el nombre descriptivo que se muestra en la columna **Actividades** y el nombre de la operación correspondiente que aparece en la información detallada de un registro de auditoría y en el archivo CSV al exportar los resultados de búsqueda.

|Nombre descriptivo  |Operación |Descripción |
|:---------|:---------|:---------|
|Bot agregado al equipo   |BotAddedToTeam        |Un usuario agrega un bot a un equipo.        |
|Agregación de canales   |ChannelAdded         |Un usuario agrega un canal a un equipo.         |
|Conector agregado  |ConectorAgregar          |Un usuario agrega un conector a un canal.        |
|Se han agregado detalles sobre Teams reunión <sup>2</sup>|Detalle de la reunión|Teams agregado información sobre una reunión, incluida la hora de inicio, la hora de finalización y la dirección URL para unirse a la reunión.|
|Información agregada sobre los participantes <sup>de</sup> la reunión 2|MeetingParticipantDetail|Teams agregado información sobre los participantes de una reunión, incluido el id. de usuario de cada participante, la hora en que un participante se unió a la reunión y la hora en que un participante abandonó la reunión.|
|Miembros agregados    |MemberAdded         |El propietario de un equipo agrega miembros a un equipo, canal o chat grupal.         |
|Pestaña agregada    |TabAdded         |Un usuario agrega una pestaña a un canal.        |
|Configuración de canal cambiada    |ChannelSettingChanged         |La operación ChannelSettingChanged se registra cuando un miembro del equipo realiza las actividades siguientes. Para cada una de estas actividades, se muestra una descripción de la configuración que se modificó (entre paréntesis) en la columna **Elemento** de los resultados de búsqueda del registro de auditoría. <ul><li>Cambiar el nombre de un canal de equipo (**nombre del canal**)</li><li>Cambiar la descripción de un canal de equipo (**descripción del canal**)</li> </ul>      |
|Configuración de organización cambiada   |TeamsTenantSettingChanged         |La operación TeamsTenantSettingChanged se registra cuando un administrador global de la Centro de administración de Microsoft 365 realiza las actividades siguientes. Estas actividades afectan a la configuración de Teams de toda la organización. Para obtener más información, consulte [Administrar la configuración de Teams de su organización](enable-features-office-365.md). <br>Para cada una de estas actividades, se muestra una descripción de la configuración cambiada (entre paréntesis) en la columna **Elemento** de los resultados de búsqueda del registro de auditoría.<ul><li>Habilita o deshabilita Teams para la organización (**Microsoft Teams**).</li><li>Habilita o deshabilita la interoperabilidad entre Microsoft Teams y Skype Empresarial para la organización (**interoperabilidad Skype Empresarial**).</li><li>Habilita o deshabilita la vista de organigrama en Microsoft Teams clientes (**vista Organigrama**).</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo programen reuniones privadas (**programación de reuniones privadas**).</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo programen reuniones del canal (**programación de reuniones de canal**).</li><li>Habilita o deshabilita las videollamadas en Teams reuniones (**vídeo para reuniones de Skype**).</li><li>Habilita o deshabilita el uso compartido de la pantalla en Microsoft Teams reuniones para la organización (**Uso compartido de pantalla para reuniones de Skype**).</li><li>Habilita o deshabilita la posibilidad de agregar imágenes animadas (denominadas Giphys) a Teams conversaciones (**imágenes animadas**).</li><li>Cambia la configuración de la clasificación de contenido de la organización (**Clasificación de contenido**). La clasificación de contenido restringe el tipo de imagen animada que se puede mostrar en las conversaciones.</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo agreguen imágenes personalizables (denominadas memes personalizados) desde Internet a las conversaciones del equipo (**imágenes personalizables de Internet**).</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo agreguen imágenes editables (denominadas adhesivos) a las conversaciones del equipo (**imágenes editables**).</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo usen bots en Microsoft Teams chats y canales (**bots para toda la organización).**</li><li>Habilita bots específicos para Microsoft Teams. Esto no incluye T-Bot, que está Teams bot de ayuda que está disponible cuando los bots están habilitados para la organización (**bots individuales**).</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo agreguen extensiones o pestañas (**extensiones o pestañas**).</li><li>Habilita o deshabilita la carga de prueba de bots propietarios para Microsoft Teams (**carga lateral de bots**).</li><li>Habilita o deshabilita la posibilidad de que los usuarios envíen mensajes de correo electrónico a un canal de Microsoft Teams (**correo electrónico del canal**).</li></ul>|
|Rol cambiado de los miembros del equipo    |MemberRoleChanged         |El propietario de un equipo cambia el rol de los miembros de un equipo. Los siguientes valores indican el tipo de rol asignado al usuario. <br><br>**1** : indica el rol Miembro.<br>**2** : indica el rol Propietario.<br>**3** : indica el rol Invitado.<br><br>La propiedad Members también incluye el nombre de la organización y la dirección de correo electrónico del miembro.        |
|Configuración del equipo cambiada    |TeamSettingChanged        |La operación TeamSettingChanged se registra cuando un propietario del equipo realiza las actividades siguientes. Para cada una de estas actividades, se muestra una descripción de la configuración cambiada (entre paréntesis) en la columna **Elemento** de los resultados de búsqueda del registro de auditoría.<ul><li>Cambia el tipo de acceso de un equipo. Teams se pueden establecer como privados o públicos (**tipo de acceso de equipo**). Cuando un equipo es privado (la configuración predeterminada), los usuarios solo pueden acceder al equipo mediante invitación. Cuando un equipo es público, es reconocible por cualquier persona.</li><li>Cambia la clasificación de información de un equipo (**clasificación del equipo**). Por ejemplo, los datos del equipo se pueden clasificar como impacto empresarial alto, impacto empresarial medio o impacto empresarial bajo.</li><li>Cambia el nombre de un equipo (**nombre del equipo**).</li><li>Cambia la descripción del equipo (**descripción del equipo**).</li><li>Cambios realizados en la configuración del equipo. Para acceder a esta configuración, el propietario del equipo puede hacer clic con el botón derecho en un equipo, seleccionar **Administrar equipo** y, a continuación, hacer clic en la pestaña **Configuración**. Para estas actividades, se muestra el nombre de la configuración que se modificó en la columna **Elemento** de los resultados de búsqueda del registro de auditoría.</li></ul>         |
|Crear un chat <sup>1, </sup> <sup>2</sup>|    ChatCreado|    Se ha creado un chat Teams.|
|Equipo creado    |EquipoCreado         |Un usuario crea un equipo.         |
|Eliminar un mensaje  |MessageDeleted |Se eliminó un mensaje en un chat o canal.|
|Eliminar todas las aplicaciones de la organización|DeletedAllOrganizationApps           |Se han eliminado todas las aplicaciones de la organización del catálogo.     |
|Aplicación eliminada |AppDeletedFromCatalog           |Una aplicación se ha eliminado del catálogo.     |
|Canal eliminado     |ChannelDeleted         |Un usuario elimina un canal de un equipo.         |
|Equipo eliminado  |TeamDeleted            |El propietario de un equipo elimina un equipo.      |
|Editado un mensaje con un vínculo url en Teams     |MessageEditedHasLink         |Un usuario edita un mensaje y agrega un vínculo a la dirección URL en Teams.         |
|Mensajes exportados <sup>1, </sup> <sup>2</sup> |    Mensajesexportados |Se exportaron mensajes de canal o chat.|
|Error al validar la invitación al canal <sup>compartido3</sup> | ErrorValidación |Un usuario responde a una invitación a un canal compartido, pero la invitación no ha superado la validación. |
|Chat obtenido <sup>1, </sup> <sup>2</sup>   |ChatRecuperado  |Se ha recuperado un chat Microsoft Teams.|
|Captura de todo el contenido hospedado de un <sup>mensaje1, </sup> <sup>2</sup> |MessageHostedContentsListed    |Se ha recuperado todo el contenido hospedado de un mensaje, como imágenes o fragmentos de código.|
|Aplicación instalada |AppInstalled         |Se instaló una aplicación.   |
|Acción realizada en la tarjeta|PerformedCardAction|Un usuario tomó medidas en una tarjeta adaptable dentro de un chat. Los bots suelen usar tarjetas adaptables para permitir la visualización enriquecida de información e interacción en los chats. <br/><br/>**Nota:** Solo las acciones de entrada en línea en una tarjeta adaptable dentro de un chat estarán disponibles en el registro de auditoría. Por ejemplo, cuando un usuario envía una respuesta de sondeo en una conversación de canal en una tarjeta adaptable generada por un bot de sondeo. Las acciones de usuario, como "Ver resultado", que abrirá un cuadro de diálogo o las acciones de usuario dentro de los cuadros de diálogo, no estarán disponibles en el registro de auditoría.|
|Publicado un nuevo mensaje <sup>1, </sup> <sup>2</sup>   |Enviar mensajes|   Un nuevo mensaje se publicó en un chat o canal.|
|Aplicación publicada |AppPublishedToCatalog           |Se agregó una aplicación al catálogo.     |
|Leer un mensaje <sup>1, </sup> <sup>2</sup> |MessageRead    |Se ha recuperado un mensaje de un chat o canal.|
|Leer el contenido hospedado de un mensaje <sup>1, </sup> <sup>2</sup>   |MessageHostedContentRead   |Se recuperó el contenido hospedado en un mensaje, como una imagen o un fragmento de código.|
|Bot quitado del equipo   |BotRemovedFromTeam         |Un usuario quita un bot de un equipo.       |
|Conector quitado     |ConnectorRemoved         |Un usuario quita un conector de un canal.         |
|Miembros quitados    |MemberRemoved        |El propietario de un equipo quita miembros de un equipo, canal o chat grupal.         |
|Uso compartido quitado del canal <sup>de equipo3</sup> | TerminatedSharing |El propietario de un equipo o canal ha deshabilitado el uso compartido de un canal compartido. |
|Uso compartido restaurado del canal <sup>de equipo3</sup> | CompartirRetored | El propietario de un equipo o canal ha vuelto a habilitar el uso compartido para un canal compartido. |
|Pestaña quitada    |TabRemoved         |Un usuario quita una pestaña de un canal.         |
|Se ha respondido a la invitación para el canal <sup>compartido3</sup> | InvitadoReponded | Un usuario ha respondido a una invitación de canal compartido. |
|Respondieron a la respuesta del invitado al canal <sup>compartido3</sup> | ChannelOwnerResponded |El propietario de un canal respondió a una respuesta de un usuario que respondió a una invitación de canal compartido. |
|Mensajes recuperados <sup>1, </sup> <sup>2</sup> |Mensajes en la lista |Los mensajes de un chat o canal se recuperaron.|
|Enviar un mensaje con un vínculo de dirección URL en Teams |MessageCreatedHasLink|Un usuario envía un mensaje que contiene un vínculo url en Teams.|
|Notificación de cambio enviada para la creación <sup>de mensajes 1, </sup> <sup>2</sup>  |MessageCreatedNotification |Se ha enviado una notificación de cambio para notificar a una aplicación de escucha suscrita de un nuevo mensaje.|
|Notificación de cambio enviada para la eliminación <sup>de mensajes 1, </sup> <sup>2</sup>  |MessageDeletedNotification |Se ha enviado una notificación de cambio para notificar a una aplicación de escucha suscrita de un mensaje eliminado.|
|Notificación de cambio enviado para la actualización <sup>de mensajes 1, </sup> <sup>2</sup>    |MessageUpdatedNotification |Se ha enviado una notificación de cambio para notificar a una aplicación de escucha suscrita de un mensaje actualizado.|
|Invitación enviada para canal <sup>compartido3</sup> | InvitaciónEnvío |Un propietario o miembro del canal envía una invitación a un canal compartido. Las invitaciones a canales compartidos se pueden enviar a personas de fuera de la organización si la directiva de canal está configurada para compartir el canal con usuarios externos.  |
|Suscribirse a las notificaciones de cambio de mensaje <sup>1, </sup> <sup>2</sup> |SubscribedToMessages   |Una aplicación de escucha creó una suscripción para recibir notificaciones de cambio de mensajes.|
|Aplicación desinstalada |Aplicacióninstalada           |Se ha desinstalado una aplicación.     |
|Aplicación actualizada |AppUpdatedInCatalog           |Se ha actualizado una aplicación en el catálogo.     |
|Actualizado un chat <sup>1, </sup> <sup>2</sup> |ChatUpdated    |Se ha actualizado un chat Teams.|
|Actualizado un mensaje <sup>1, </sup> <sup>2</sup>  |MessageUpdated |Se ha actualizado un mensaje de un chat o canal.|
|Conector actualizado    |ConnectorUpdated         |Un usuario ha modificado un conector en un canal.         |
|Pestaña actualizada   |TabUpdated         |Un usuario ha modificado una pestaña en un canal.         |
|Aplicación actualizada |AppUpgraded           |Una aplicación se ha actualizado a su última versión en el catálogo.     |
|Usuario que ha iniciado sesión en Teams     |TeamsSessionStarted         |Un usuario inicia sesión en un cliente de Microsoft Teams. Este evento no captura actividades de actualización de token.         |
||||

> [!NOTE]
> <sup>1</sup> Un registro de auditoría para este evento solo se registra cuando la operación se realiza llamando a un Graph API de Microsoft. Si la operación se realiza en el cliente de Teams, no se registrará un registro de auditoría<br/><sup>2</sup> Este evento solo está disponible en Auditoría avanzada. Esto significa que los usuarios deben tener asignada la licencia adecuada antes de que estos eventos se registren en el registro de auditoría. Para obtener más información sobre las actividades solo disponibles en Auditoría avanzada, vea [Auditoría avanzada en Microsoft 365](/microsoft-365/compliance/advanced-audit#advanced-audit-events). Para conocer los requisitos de licencias de auditoría avanzada, consulte [Soluciones de auditoría en Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements). <br/> <sup>3</sup> Este evento se encuentra en versión preliminar pública.

## <a name="shifts-in-teams-activities"></a>Turnos en actividades de Teams

**(en la versión preliminar)**

Si su organización usa la aplicación Turnos en Teams, puede buscar actividades relacionadas con la aplicación Turnos en el registro de auditoría. Esta es una lista de todos los eventos que se registran para las actividades de Turnos en Teams en el registro de auditoría de Microsoft 365.

|Nombre descriptivo  |Operación  |Descripción  |
|---------|---------|---------|
|Grupo de programación agregado |ScheduleGroupAdded          |Un usuario agrega correctamente un nuevo grupo de programación a la programación.|
|Grupo de programación editado     |ScheduleGroupEdited         |Un usuario edita correctamente un grupo de programación.          |
|Grupo de programación eliminado         |ScheduleGroupDeleted              |Un usuario elimina correctamente un grupo de programación de la programación.|
|Programación retirada |ScheduleWithdrawn              |Un usuario retira correctamente una programación publicada.|
|Turno agregado      |MayúsAgregar          |Un usuario agrega correctamente un turno.           |
|Turno editado       |MayúsEdited       |Un usuario edita correctamente un turno.        |
|Turno eliminado          |MayúsEliminado          | Un usuario elimina correctamente un turno.               |
|Se ha agregado un permiso      |TimeOffAdded          |Un usuario agrega correctamente un permiso en la programación.          |
|Permisos editados         |TimeOffEdited           |Un usuario edita correctamente el permiso.          |
|Permisos eliminados     |TimeOffDeleted              |Un usuario elimina correctamente los permisos.           |
|Se ha agregado el turno abierto     |OpenShiftAdded          |Un usuario agrega correctamente un turno abierto a un grupo de programación.          |
|Turno abierto editado    |OpenShiftEdited          |Un usuario edita correctamente un turno abierto en un grupo de programación.          |
|Turno abierto eliminado      |OpenShiftDeleted          |Un usuario elimina correctamente un turno abierto de un grupo de programación.         |
|Programación compartida     |ScheduleShared                  |Un usuario ha compartido correctamente una programación de equipo para un intervalo de fechas.          |
|Con reloj de reloj sincronizado         |ClockedIn          |Un usuario marca correctamente el reloj con el reloj de hora.          |
|Reloj de salida con reloj de tiempo      |ClockedOut          |Un usuario cierra la reloj correctamente con reloj de hora.          |
|Inicio del descanso con reloj de tiempo      |BreakStarted          |Un usuario inicia correctamente un descanso durante una sesión de reloj de hora activa.          |
|Interrupción final con reloj de hora    |BreakEnded          |Un usuario finaliza correctamente un salto durante una sesión de reloj de hora activa.          |
|Entrada reloj de hora agregada     |TimeClockEntryAdded          |Un usuario agrega correctamente una nueva entrada manual de reloj de hora en la hoja de horas.          |
|Entrada reloj de hora editada     | TimeClockEntryEdited             |Un usuario edita correctamente una entrada de reloj de hora en la hoja de horas.          |
|Entrada de reloj de hora eliminada    |TimeClockEntryDeleted              |Un usuario elimina correctamente una entrada de reloj de hora en la hoja de horas.          |
|Solicitud de turno agregada         |RequestAdded              |Un usuario agregó una solicitud de turno.          |
|Se ha respondido a la solicitud de turno     |RequestRespondedTo                  |Un usuario ha respondido a una solicitud de turno.          |
|Solicitud de turno cancelada         |RequestCancelled               |Un usuario canceló una solicitud de turno.          |
|Configuración de programación cambiada      |ScheduleSettingChanged          |Un usuario cambia una configuración en la configuración de Turnos.         |
|Integración de la fuerza de trabajo agregada      |WorkforceIntegrationAdded                  | La aplicación Turnos está integrada con un sistema de terceros.         |
|Mensaje Desactivo de turno aceptado         |OffShiftDialogAccepted          |Un usuario reconoce el mensaje de cambio fuera de turno para acceder a Teams después de las horas del turno.           |

## <a name="office-365-management-activity-api"></a>API de actividad de administración de Office 365

Puede usar la API de actividad de administración de Office 365 para recuperar información sobre eventos de Teams. Para obtener más información sobre el esquema de la API de actividad de administración para Teams, vea [Teams esquema](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).

## <a name="attribution-in-teams-audit-logs"></a>Atribución en registros de auditoría de Teams

Los cambios de pertenencia a Teams (como los usuarios agregados o eliminados) realizados a través de Azure Active Directory (Azure AD), Microsoft 365 portal de administración o Grupos de Microsoft 365 Graph API aparecerán en Teams  auditar mensajes y en el canal General con una atribución a un propietario existente del equipo y no al iniciador real de la acción. En estos escenarios, consulte los registros de auditoría de Azure AD o [Microsoft 365 Grupo](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) para ver la información relevante.

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>Usar aplicaciones Defender for Cloud para establecer directivas de actividad

Con [la](/cloud-app-security/what-is-cloud-app-security) integración Microsoft Defender for Cloud Apps, puede establecer [directivas de actividad](/cloud-app-security/user-activity-policies) para exigir una amplia gama de procesos automatizados mediante las API del proveedor de la aplicación. Estas directivas le permiten supervisar actividades específicas realizadas por varios usuarios o seguir tasas inesperadamente altas de un determinado tipo de actividad.

Después de establecer una directiva de detección de actividad, comienza a generar alertas. Las alertas solo se generan en las actividades que se producen después de crear la directiva. Estos son algunos escenarios de ejemplo de cómo puede usar las directivas de actividad de las aplicaciones de Defender for Cloud para supervisar las actividades de Teams.

### <a name="external-user-scenario"></a>Escenario de usuario externo

Un escenario en el que es posible que desee estar pendiente, desde una perspectiva empresarial, es la adición de usuarios externos a su entorno de Teams. Si los usuarios externos están habilitados, supervisar su presencia es una buena idea.  Puedes usar [Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) para identificar posibles amenazas.

:::image type="content" alt-text="Directiva para supervisar la adición de usuarios externos." source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

La captura de pantalla de esta directiva para supervisar la adición de usuarios externos le permite asignar un nombre a la directiva, establecer la gravedad según las necesidades de su empresa, establecerla como (en este caso) una única actividad y, a continuación, establecer los parámetros que supervisarán específicamente solo la adición de usuarios no internos y limitar esta actividad a Teams.

Los resultados de esta directiva se pueden ver en el registro de actividades:

:::image type="content" alt-text="Eventos desencadenados por la directiva de usuarios externos." source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

Aquí puede revisar las coincidencias de la directiva que ha establecido y realizar los ajustes necesarios, o exportar los resultados para usarlos en otro lugar.

### <a name="mass-delete-scenario"></a>Escenario de eliminación masiva

Como se mencionó anteriormente, puede supervisar escenarios de eliminación. Es posible crear una directiva que supervise la eliminación masiva de sitios Teams. En este ejemplo, se configura una directiva basada en alertas para detectar la eliminación masiva de equipos en un intervalo de 30 minutos.

:::image type="content" alt-text="Directiva que muestra la configuración de una directiva para la detección de eliminación masiva de equipos." source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

Como se muestra en la captura de pantalla, puede establecer muchos parámetros diferentes para esta directiva para supervisar las eliminaciones de Teams, como la gravedad, una acción única o repetida, y los parámetros que lo limitan a Teams y eliminación del sitio. Esto se puede hacer independientemente de una plantilla, o puede que tenga una plantilla creada para basar esta directiva en, en función de sus necesidades de la organización.

Después de establecer una directiva que funcione para su empresa, puede revisar los resultados en el registro de actividades a medida que se desencadenan los eventos:

:::image type="content" alt-text="Eventos de captura de pantalla desencadenados por eliminaciones masivas." source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

Puede filtrar hacia abajo hasta la directiva que haya establecido para ver los resultados de esa directiva. Si los resultados que obtiene en el registro de actividades no son satisfactorios (es posible que esté viendo muchos resultados o nada en absoluto), esto puede ayudarle a ajustar la consulta para hacerla más relevante a lo que necesita hacer.

### <a name="alert-and-governance-scenario"></a>Escenario de alerta y gobernanza

Puede establecer alertas y enviar correos electrónicos a administradores y otros usuarios cuando se desencadena una directiva de actividad. Puede establecer acciones de gobierno automatizadas, como suspender a un usuario o hacer que un usuario inicie sesión de nuevo de forma automatizada. En este ejemplo se muestra cómo se puede suspender una cuenta de usuario cuando se activa una directiva de actividad y se determina que un usuario eliminó dos o más equipos en 30 minutos.

![Captura de pantalla de alertas y acciones de gobierno para una directiva de actividad.](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>Usar Defender for Cloud Apps para establecer directivas de detección de anomalías

[Las directivas de detección de anomalías](/cloud-app-security/anomaly-detection-policy) de Defender for Cloud Apps proporcionan análisis de comportamiento de entidades y usuarios predefinidos (UEBA) y aprendizaje automático (ML) para que pueda ejecutar inmediatamente la detección de amenazas avanzadas en su entorno de nube. Como se habilitan automáticamente, las nuevas directivas de detección de anomalías proporcionan resultados inmediatos al proporcionar detecciones inmediatas, que identifican numerosas anomalías conductuales entre los usuarios y las máquinas y dispositivos conectados a su red. Además, las nuevas directivas exponen más datos del motor de detección de aplicaciones Defender for Cloud, para ayudarle a acelerar el proceso de investigación y contener amenazas en curso.

Estamos trabajando para integrar eventos Teams en directivas de detección de anomalías. Por ahora, puede configurar directivas de detección de anomalías para otros productos Office y tomar medidas en los usuarios que coincidan con esas directivas.

## <a name="related-topics"></a>Temas relacionados

- [Buscar el registro de auditoría en el portal de cumplimiento de Microsoft Purview](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
