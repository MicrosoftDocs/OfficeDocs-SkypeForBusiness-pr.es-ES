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
description: Obtenga información sobre cómo recuperar Microsoft Teams datos del registro de auditoría en el Centro de cumplimiento de Microsoft 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 027d3691a5e5c501beb69448a4d4060de4a7fad9
ms.sourcegitcommit: e023c3023f49e196315e176ce346f0dc5825fa56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53275679"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Buscar eventos en el registro de auditoría en Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

El registro de auditoría puede ayudarle a investigar actividades específicas en Microsoft 365 servicios. Para Microsoft Teams, estas son algunas de las actividades que se auditan:

- Creación de equipos
- Eliminación de equipos
- Agregación de canales
- Cambios en la configuración

Para obtener una lista completa de Teams actividades [](#teams-activities) que se auditan, vea Teams actividades y turnos en Teams actividades [(en versión preliminar).](#shifts-in-teams-activities)

> [!NOTE]
> Los eventos de auditoría de canales privados también se registran tal y como están para equipos y canales estándar.

## <a name="turn-on-auditing-in-teams"></a>Activar la auditoría en Microsoft Teams

Antes de poder ver los datos de auditoría, primero debe activar la auditoría en el Centro de [& cumplimiento.](https://protection.office.com) Para obtener ayuda con la activación de la auditoría, lea Activar o desactivar la búsqueda del [registro de auditoría.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)

> [!IMPORTANT]
> Los datos de auditoría solo están disponibles desde el punto en que ha activado la auditoría.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperar datos de Microsoft Teams del registro de auditoría

1. Para recuperar los registros de auditoría, vaya al [Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=855775). En **Buscar,** seleccione **Búsqueda de registro de auditoría.**

2. Use **Buscar** para filtrar por las actividades, las fechas y los usuarios que desee auditar.

3. Exporte los resultados a Excel para continuar el análisis.

> [!IMPORTANT]
> Los datos de auditoría solo están visibles en el registro de auditoría si la auditoría está activada.

La duración del tiempo que un registro de auditoría se conserva y se puede buscar en el registro de auditoría depende de su suscripción Microsoft 365 o Office 365 y, específicamente, del tipo de licencia que se asigna a los usuarios. Para obtener más información, vea la descripción del [servicio & centro de cumplimiento.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="tips-for-searching-the-audit-log"></a>Sugerencias para buscar en el registro de auditoría

Estas son sugerencias para buscar Teams actividades en el registro de auditoría.

![Captura de pantalla de la página de búsqueda del registro de auditoría](media/audit-log-search-page.png)

- Puede seleccionar actividades específicas para buscar haciendo clic en el nombre de la actividad. También puede buscar todas las actividades de un grupo (como Actividades de archivo y **carpetas)** haciendo clic en el nombre del grupo. Si se selecciona una actividad, puede hacer clic en ella para cancelar la selección. También puede usar el cuadro de búsqueda para mostrar las actividades que contienen la palabra clave que escribe.

  ![Captura de pantalla de la búsqueda del registro de auditoría](media/audit-log-search.png)

- Para mostrar los eventos de las actividades que se ejecutan con cmdlets, seleccione **Mostrar resultados para todas** las actividades de la **lista** Actividades. Si conoce el nombre de la operación para estas actividades, busque todas las actividades y, después, filtre los resultados escribiendo el nombre de la operación en el cuadro de la columna **Actividad.** Para obtener más información, vea [Paso 3: Filtrar los resultados de la búsqueda.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance?view=o365-worldwide#step-3-filter-the-search-results)

- Para borrar los criterios de búsqueda actuales, haga clic en **Borrar**. El intervalo de fechas vuelve al valor predeterminado de los últimos siete días. También puede hacer clic en **Borrar todo para mostrar los resultados** de todas las actividades para cancelar todas las actividades seleccionadas.

- Si se encuentran 5.000 resultados, es probable que suponga que hay más de 5 000 eventos que cumplen los criterios de búsqueda. Puede refinar los criterios de búsqueda y volver a ejecutar la búsqueda para devolver menos resultados, o puede exportar todos los resultados de búsqueda seleccionando Exportar resultados  >  **Descargar todos los resultados.**

Consulte este [vídeo para](https://www.youtube.com/embed/UBxaRySAxyE) usar la búsqueda de registros de audio. Únase a Ansuman Acharya, un administrador de programas para Teams, ya que muestra cómo realizar una búsqueda de registro de auditoría para Teams.

## <a name="use-cloud-app-security-to-set-activity-policies"></a>Usar Cloud App Security para establecer directivas de actividad

Con [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) integración, puede [](/cloud-app-security/user-activity-policies) establecer directivas de actividad para exigir una amplia gama de procesos automatizados con las API del proveedor de aplicaciones. Estas directivas le permiten supervisar actividades específicas realizadas por varios usuarios o seguir tasas inesperadamente altas de un determinado tipo de actividad.

Después de establecer una directiva de detección de actividad, comienza a generar alertas. Las alertas solo se generan en las actividades que se producen después de crear la directiva. Estos son algunos escenarios de ejemplo para cómo puede usar directivas de actividad en Cloud App Security para supervisar Teams actividades.

### <a name="external-user-scenario"></a>Escenario de usuario externo

Un escenario en el que puede que desee estar atento, desde una perspectiva empresarial, es la adición de usuarios externos a su entorno Teams empresa. Si los usuarios externos están habilitados, supervisar su presencia es una buena idea.  Puede usar [Cloud App Security](/cloud-app-security/what-is-cloud-app-security) identificar amenazas potenciales.

![Captura de pantalla de una lista de eventos desencadenados por eliminaciones masivas](media/TeamsExternalUserAddPolicy.png)

La captura de pantalla de esta directiva para supervisar la adición de usuarios externos le permite nombrar la directiva, establecer la gravedad según las necesidades de su empresa, establecerla como (en este caso) una sola actividad y, a continuación, establecer los parámetros que supervisarán específicamente solo la adición de usuarios no internos y limitar esta actividad a Teams.

Los resultados de esta directiva se pueden ver en el registro de actividades:

![Captura de pantalla de una lista de eventos desencadenados por eliminaciones masivas](media/TeamsExternalUserList.png)

Aquí puede revisar coincidencias con la directiva que ha establecido y realizar los ajustes necesarios, o exportar los resultados para usarlos en otro lugar.

### <a name="mass-delete-scenario"></a>Escenario de eliminación masiva

Como se mencionó anteriormente, puede supervisar escenarios de eliminación. Es posible crear una directiva que supervise la eliminación masiva de Teams sitios. En este ejemplo, se configura una directiva basada en alertas para detectar la eliminación masiva de equipos en un intervalo de 30 minutos.

![Captura de pantalla de la página de creación de directivas que muestra la configuración de una directiva para la detección masiva de eliminación de equipos](media/TeamsMassDeletePolicy.png)

Como se muestra en la captura de pantalla, puede establecer muchos parámetros diferentes para esta directiva para supervisar las eliminaciones de Teams, incluida la gravedad, la acción única o repetida, y los parámetros que limitan esto Teams la eliminación del sitio. Esto se puede hacer independientemente de una plantilla, o es posible que tenga una plantilla creada para basar esta directiva en, dependiendo de las necesidades de la organización.

Después de establecer una directiva que funcione para su empresa, puede revisar los resultados del registro de actividades a medida que se desencadenan los eventos:

![Captura de pantalla de una lista de eventos desencadenados por eliminaciones masivas](media/TeamsMassDeleteList.png)

Puede filtrar hacia abajo hasta la directiva que haya establecido para ver los resultados de esa directiva. Si los resultados que está obteniendo en el registro de actividades no son satisfactorios (tal vez está viendo una gran cantidad de resultados, o nada en absoluto), esto puede ayudarle a ajustar la consulta para que sea más relevante para lo que necesita que haga.

### <a name="alert-and-governance-scenario"></a>Escenario de alerta y gobierno

Puede establecer alertas y enviar correos electrónicos a administradores y otros usuarios cuando se desencadene una directiva de actividad. Puede establecer acciones de gobierno automatizadas como suspender un usuario o hacer que un usuario vuelva a iniciar sesión de forma automatizada. En este ejemplo se muestra cómo se puede suspender una cuenta de usuario cuando se desencadena una directiva de actividad y se determina que un usuario eliminó dos o más equipos en 30 minutos.

![Captura de pantalla de alertas y acciones de gobierno para una directiva de actividad](media/audit-log-governance.png)

## <a name="use-cloud-app-security-to-set-anomaly-detection-policies"></a>Usar Cloud App Security para establecer directivas de detección de anomalías

[](/cloud-app-security/anomaly-detection-policy) Las directivas de detección de anomalías en Cloud App Security proporcionan análisis de comportamiento de usuarios y entidades (UEBA) y aprendizaje automático (ML) de forma que pueda ejecutar inmediatamente la detección avanzada de amenazas en todo el entorno de la nube. Como están habilitadas automáticamente, las nuevas directivas de detección de anomalías proporcionan resultados inmediatos al proporcionar detecciones inmediatas, dirigidas a numerosas anomalías conductuales entre los usuarios y los equipos y dispositivos conectados a su red. Además, las nuevas directivas exponen más datos del motor de detección de Cloud App Security, para ayudarle a acelerar el proceso de investigación y contener amenazas en curso.

Estamos trabajando para integrar Teams eventos en directivas de detección de anomalías. Por ahora, puede configurar directivas de detección de anomalías para otros productos Office y realizar acciones en los usuarios que coincidan con dichas directivas.

## <a name="teams-activities"></a>Teams actividades

Esta es una lista de todos los eventos que se registran para las actividades de usuario y administrador en Teams en el registro Microsoft 365 auditoría. La tabla incluye el nombre descriptivo que  se muestra en la columna Actividades y el nombre de la operación correspondiente que aparece en la información detallada de un registro de auditoría y en el archivo CSV al exportar los resultados de la búsqueda.

|Nombre descriptivo  |Operación |Descripción |
|:---------|:---------|:---------|
|Bot agregado al equipo   |BotAddedToTeam        |Un usuario agrega un bot a un equipo.        |
|Agregación de canales   |Canal agregado         |Un usuario agrega un canal a un equipo.         |
|Conector agregado  |Conector agregado          |Un usuario agrega un conector a un canal.        |
|Miembros agregados    |Miembro agregado         |El propietario de un equipo agrega miembros a un equipo, canal o chat grupal.         |
|Pestaña Agregado    |Pestaña Agregada         |Un usuario agrega una pestaña a un canal.        |
|Configuración del canal cambiada    |ChannelSettingChanged         |La operación ChannelSettingChanged se registra cuando un miembro del equipo realiza las siguientes actividades. Para cada una de estas actividades, se muestra una descripción de la configuración  que se ha cambiado (se muestra entre paréntesis en la columna Elemento en los resultados de búsqueda del registro de auditoría. <ul><li>Cambia el nombre de un canal de grupo (**nombre del canal**)</li><li>Cambiar la descripción de un canal de grupo (**Descripción del canal**)</li> </ul>      |
|Configuración de la organización cambiada   |TeamsTenantSettingChanged         |La operación TeamsTenantSettingChanged se registra cuando un administrador global realiza las siguientes actividades en el Centro de administración de Microsoft 365. Estas actividades afectan a la configuración de Teams organización. Para obtener más información, vea [Administrar Teams configuración de su organización.](enable-features-office-365.md) <br>Para cada una de estas actividades, se muestra una descripción de la configuración  que se modificó (se muestra entre paréntesis) en la columna Elemento en los resultados de la búsqueda del registro de auditoría.<ul><li>Habilita o deshabilita Teams para la organización (**Microsoft Teams**).</li><li>Habilita o deshabilita la interoperabilidad entre Microsoft Teams y Skype Empresarial para la organización **(Skype Empresarial interoperabilidad).**</li><li>Habilita o deshabilita la vista organigrama en Microsoft Teams **(vista Organigrama).**</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo programe reuniones privadas **(programación de reuniones privadas).**</li><li>Habilita o deshabilita la capacidad de los miembros del equipo para programar reuniones del canal **(programación de reuniones del canal).**</li><li>Habilita o deshabilita las videollamadas en Teams reuniones **(Vídeo para Skype reuniones).**</li><li>Habilita o deshabilita el uso compartido de pantalla en Microsoft Teams reuniones de la organización (uso compartido de pantalla **para Skype reuniones).**</li><li>Habilita o deshabilita esa capacidad para agregar imágenes animadas (denominadas Giphys) a Teams conversaciones **(imágenes animadas).**</li><li>Cambia la configuración de clasificación de contenido de la organización (**Clasificación de contenido**). La clasificación de contenido restringe el tipo de imagen animada que se puede mostrar en las conversaciones.</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo agreguen imágenes personalizables (denominadas memes personalizados) desde Internet a las conversaciones del equipo (imágenes personalizables **desde Internet).**</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo agreguen imágenes editables (denominadas adhesivos) a las conversaciones del equipo **(imágenes editables).**</li><li>Habilita o deshabilita esa capacidad para que los miembros del equipo usen bots en Microsoft Teams chats y canales **(bots** para toda la organización).</li><li>Habilita bots específicos para Microsoft Teams. Esto no incluye el T-Bot, que es Teams bot de ayuda que está disponible cuando los bots están habilitados para la organización **(bots individuales).**</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo agreguen extensiones o pestañas **(extensiones o pestañas).**</li><li>Habilita o deshabilita la carga lateral de bots propietarios para Microsoft Teams **(carga lateral de bots).**</li><li>Habilita o deshabilita la capacidad de los usuarios para enviar mensajes de correo electrónico a un canal Microsoft Teams **(correo electrónico del canal).**</li></ul>|
|Rol cambiado de los miembros del equipo    |MemberRoleChanged         |El propietario de un equipo cambia el rol de los miembros de un equipo. Los siguientes valores indican el tipo de rol asignado al usuario. <br><br>**1:** indica el rol de miembro.<br>**2:** indica el rol propietario.<br>**3:** indica el rol de invitado.<br><br>La propiedad Miembros también incluye el nombre de su organización y la dirección de correo electrónico del miembro.        |
|Configuración de equipo cambiada    |TeamSettingChanged        |La operación TeamSettingChanged se registra cuando un propietario del equipo realiza las siguientes actividades. Para cada una de estas actividades, se muestra una descripción de la configuración  que se modificó (se muestra entre paréntesis) en la columna Elemento en los resultados de la búsqueda del registro de auditoría.<ul><li>Cambia el tipo de acceso de un equipo. Teams puede establecerse como privada o pública **(tipo de acceso de equipo).** Cuando un equipo es privado (la configuración predeterminada), los usuarios solo pueden acceder al equipo por invitación. Cuando un equipo es público, es reconocible por cualquier persona.</li><li>Cambia la clasificación de información de un equipo **(clasificación de equipo).** Por ejemplo, los datos de grupo se pueden clasificar como impacto empresarial alto, impacto empresarial medio o bajo impacto empresarial.</li><li>Cambia el nombre de un equipo **(nombre del equipo).**</li><li>Cambia la descripción del equipo **(descripción del equipo).**</li><li>Cambios realizados en la configuración del equipo. Para acceder a esta configuración, el propietario del equipo puede hacer clic con el botón derecho en un equipo, seleccionar Administrar equipo **y,** a continuación, hacer clic **en Configuración** pestaña. Para estas actividades, el nombre de la configuración  que se modificó se muestra en la columna Elemento en los resultados de búsqueda del registro de auditoría.</li></ul>         |
|Crear un chat <sup>1</sup>|   ChatCreado|    Se Teams un chat de Teams usuario.|
|Equipo creado    |TeamCreated         |Un usuario crea un equipo.         |
|Se eliminaron todas las aplicaciones de la organización|DeletedAllOrganizationApps           |Eliminó todas las aplicaciones de la organización del catálogo.     |
|Aplicación eliminada |AppDeletedFromCatalog           |Se ha eliminado una aplicación del catálogo.     |
|Canal eliminado     |ChannelDeleted         |Un usuario elimina un canal de un equipo.         |
|Equipo eliminado  |TeamDeleted            |El propietario de un equipo elimina un equipo.      |
|Editó un mensaje con un vínculo url en Teams     |MessageEditedHasLink         |Un usuario edita un mensaje y agrega un vínculo url a él en Teams.         |
|Mensajes exportados <sup>1</sup> |   MensajesExportados |Se exportaron mensajes de chat o canal|.
|Chats obtenidos <sup>1</sup> |ChatRetrieved  |Se Microsoft Teams un chat de Microsoft Teams.|
|Capturar todo el contenido hospedado de un mensaje<sup>1</sup>    |MessageHostedContentsListed    |Se ha recuperado todo el contenido hospedado en un mensaje, como imágenes o fragmentos de código.|
|Aplicación instalada |AppInstalled         |Se instaló una aplicación.   |
|Acción realizada en la tarjeta|PerformedCardAction|Un usuario realizó acciones en una tarjeta adaptable dentro de un chat. Los bots suelen usar las tarjetas adaptables para permitir la visualización enriquecida de información e interacción en chats. <br/><br/>**Nota:** Solo las acciones de entrada en línea en una tarjeta adaptable dentro de un chat estarán disponibles en el registro de auditoría. Por ejemplo, cuando un usuario envía una respuesta de sondeo en una conversación de canal en una tarjeta adaptable generada por un bot de sondeo. Las acciones de usuario como "Ver resultado", que abrirá un cuadro de diálogo, o las acciones de usuario dentro de los cuadros de diálogo no estarán disponibles en el registro de auditoría.|
|Publicado un nuevo mensaje <sup>1</sup>  |MensajeSent Un nuevo mensaje se publicó en un chat o canal.|
|Aplicación publicada |AppPublishedToCatalog           |Se ha agregado una aplicación al catálogo.     |
|Leer un mensaje <sup>1</sup>    |MessageRead    |Se ha recuperado un mensaje de un chat o canal.|
|Leer contenido hospedado de un mensaje <sup>1</sup>  |MessageHostedContentRead   |Se ha recuperado el contenido hospedado en un mensaje, como una imagen o un fragmento de código.|
|Bot quitado del equipo   |BotRemovedFromTeam         |Un usuario quita un bot de un equipo.       |
|Conector quitado     |ConnectorRemoved         |Un usuario quita un conector de un canal.         |
|Miembros eliminados    |MemberRemoved        |El propietario de un equipo quita los miembros de un equipo, canal o chat grupal.         |
|Pestaña Quitado    |TabRemoved         |Un usuario quita una pestaña de un canal.         |
|Mensajes recuperados <sup>1</sup>    |MensajesListed |Se recuperaron los mensajes de un chat o canal.|
|Se ha enviado un mensaje con un vínculo url en Teams |MessageCreatedHasLink|Un usuario envía un mensaje que contiene un vínculo url en Teams.|
|Notificación de cambio enviada para la creación <sup>de mensajes 1</sup> |MessageCreatedNotification |Se envió una notificación de cambio para notificar un mensaje nuevo a una aplicación de escucha suscrita.|
|Notificación de cambio enviada para la eliminación <sup>de mensajes 1</sup> |MessageDeletedNotification |Se envió una notificación de cambio para notificar a una aplicación de escucha suscrita de un mensaje eliminado.|
|Notificación de cambio enviada para la actualización <sup>de mensajes 1</sup>   |MessageUpdatedNotification |Se envió una notificación de cambio para notificar un mensaje actualizado a una aplicación de escucha suscrita.|
|Suscribirse a las notificaciones de cambio de mensajes <sup>1</sup>    |SubscribedToMessages   |Una aplicación de escucha creó una suscripción para recibir notificaciones de cambio de mensajes.|
|Aplicación desinstalada |AppUninstalled           |Se ha desinstalado una aplicación.     |
|Aplicación actualizada |AppUpdatedInCatalog           |Se actualizó una aplicación en el catálogo.     |
|Actualizado un chat <sup>1</sup>    |ChatUpdated    |Se ha Teams un chat de Teams.|
|Se ha actualizado un mensaje <sup>1</sup> |MessageUpdated |Se actualizó un mensaje de un chat o canal.|
|Conector actualizado    |ConnectorUpdated         |Un usuario modificó un conector en un canal.         |
|Pestaña Actualizada   |TabUpdated         |Un usuario modificó una pestaña en un canal.         |
|Aplicación actualizada |AppUpgraded           |Una aplicación se actualizó a su versión más reciente del catálogo.     |
|El usuario ha iniciado sesión en Teams     |TeamsSessionStarted         |Un usuario inicia sesión en un Microsoft Teams usuario. Este evento no captura las actividades de actualización de tokens.         |
||||

> [!NOTE]
> <sup>1</sup> Un registro de auditoría para este evento solo se registra cuando la operación se realiza llamando a una API Graph Microsoft. Si la operación se realiza en el Teams, no se registrará un registro de auditoría

## <a name="shifts-in-teams-activities"></a>Turnos en Teams actividades

**(en la versión preliminar)**

Si su organización usa la aplicación Turnos en Teams, puede buscar en el registro de auditoría actividades relacionadas con la aplicación Turnos. Esta es una lista de todos los eventos que se registran para las actividades de Turnos en Teams en el Microsoft 365 registro de auditoría.

|Nombre descriptivo  |Operación  |Descripción  |
|---------|---------|---------|
|Grupo de programación agregado |ScheduleGroupAdded          |Un usuario agrega correctamente un nuevo grupo de programación a la programación.|
|Grupo de programación editado     |ScheduleGroupEdited         |Un usuario edita correctamente un grupo de programación.          |
|Grupo de programación eliminado         |ScheduleGroupDeleted              |Un usuario elimina correctamente un grupo de programación de la programación.|
|Retirar la programación |ScheduleWithdrawn              |Un usuario retira correctamente una programación publicada.|
|Turno agregado      |Mayús Agregado          |Un usuario agrega correctamente un turno.           |
|Turno editado       |MayúsEdited       |Un usuario edita correctamente un turno.        |
|Turno eliminado          |MayúsDeleted          | Un usuario elimina correctamente un turno.               |
|Tiempo añadido de descanso      |TimeOffAdded          |Un usuario agrega correctamente el tiempo libre en la programación.          |
|Tiempo libre editado         |TimeOffEdited           |Un usuario edita correctamente los permisos.          |
|Tiempo de espera eliminado     |TimeOffDeleted              |Un usuario elimina correctamente el tiempo libre.           |
|Se ha agregado el turno de apertura     |OpenShift Agregado          |Un usuario agrega correctamente un turno abierto a un grupo de programación.          |
|Turno abierto editado    |OpenShiftEdited          |Un usuario edita correctamente un turno abierto en un grupo de programación.          |
|Turno abierto eliminado      |OpenShiftDeleted          |Un usuario elimina correctamente un turno abierto de un grupo de programación.         |
|Programación compartida     |ScheduleShared                  |Un usuario compartió correctamente una programación de grupo para un intervalo de fechas.          |
|Reloj en el que se usa reloj de hora         |ClockedIn          |Un usuario puede usar el reloj de hora correctamente.          |
|Reloj de salida con reloj de tiempo      |ClockedOut          |Un usuario se desahora correctamente con el reloj de hora.          |
|Interrupción iniciada con reloj de hora      |BreakStarted          |Un usuario inicia correctamente un salto durante una sesión activa del reloj de hora.          |
|Interrupción finalizada con reloj de hora    |BreakEnded          |Un usuario termina correctamente un salto durante una sesión activa del reloj de hora.          |
|Entrada de reloj de hora agregada     |TimeClockEntryAdded          |Un usuario agrega correctamente una nueva entrada manual del reloj de tiempo en la hoja de horas.          |
|Entrada de reloj de hora editada     | TimeClockEntryEdited             |Un usuario edita correctamente una entrada de reloj de hora en hoja de horas.          |
|Entrada de reloj de hora eliminada    |TimeClockEntryDeleted              |Un usuario elimina correctamente una entrada de reloj de hora en hoja de horas.          |
|Solicitud de turno agregada         |Solicitud agregada              |Un usuario agregó una solicitud de turno.          |
|Respuesta a la solicitud de turno     |RequestRespondedTo                  |Un usuario respondió a una solicitud de turno.          |
|Solicitud de turno cancelada         |RequestCancelled               |Un usuario ha cancelado una solicitud de turno.          |
|Configuración de programación cambiada      |ScheduleSettingChanged          |Un usuario cambia una configuración en la configuración de Turnos.         |
|Integración de fuerza laboral agregada      |WorkforceIntegrationAdded                  | La aplicación Turnos está integrada con un sistema de terceros.         |
|Mensaje de turno desactivado aceptado         |OffShiftDialogAccepted          |Un usuario reconoce el mensaje de turno libre para acceder a Teams horas de turno.           |

## <a name="office-365-management-activity-api"></a>Office 365 API de actividad de administración

Puede usar la API Office 365 actividad de administración para recuperar información sobre Teams eventos. Para obtener más información sobre el esquema api de actividad de administración para Teams, [vea Teams esquema](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).

## <a name="attribution-in-teams-audit-logs"></a>Atribución en Teams registros de auditoría

Los cambios de pertenencia a Teams (como usuarios agregados o eliminados) realizados a través de Azure Active Directory (Azure AD), un portal de administración de Microsoft 365 o la API Graph grupos de Microsoft 365 aparecerán en los mensajes de auditoría de Teams y en el canal General con una atribución a un propietario existente del equipo y no al iniciador real de la acción. En estos escenarios, consulte Azure AD [o Microsoft 365 de auditoría](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) del grupo para ver la información relevante.

## <a name="related-topics"></a>Temas relacionados

- [Busque el registro de auditoría en el Centro de cumplimiento de Microsoft 365](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
