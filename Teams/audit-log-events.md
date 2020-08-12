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
description: Obtenga información sobre cómo recuperar datos de Microsoft Teams del registro de auditoría.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64b2e2f28b33a3f0518dbf4f2f07a4be3053d342
ms.sourcegitcommit: 3814db70796888f15ea47d7810e1621a92992870
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "46634616"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Buscar eventos en el registro de auditoría en Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

El registro de auditoría puede ayudarle a investigar actividades específicas en los servicios de Microsoft 365. Para Microsoft Teams, estas son algunas de las actividades que se auditan:

- Creación de equipos
- Eliminación de equipos
- Agregación de canales
- Cambios en la configuración

Para obtener una lista completa de las actividades de teams que se auditan, consulte [actividades de Teams](#teams-activities) y [turnos en actividades de Teams (en versión preliminar)](#shifts-in-teams-activities).

> [!NOTE]
> Los eventos de auditoría de canales privados también se registran como si se trataran de equipos y canales estándar.

## <a name="turn-on-auditing-in-teams"></a>Activar la auditoría en Microsoft Teams

Para poder consultar los datos de auditoría, primero debe activar la auditoría en el [centro de cumplimiento de & de seguridad](https://protection.office.com). Para obtener ayuda con la activación de la auditoría, lea [activar o desactivar la búsqueda de registros de auditoría](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).

> [!IMPORTANT]
> Los datos de auditoría solo están disponibles desde el punto en el que activó la auditoría.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperar datos de Microsoft Teams del registro de auditoría

1. Para recuperar los registros de auditoría, vaya al [Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=855775). En **Buscar**, seleccione **búsqueda de registros de auditoría**.
2. Use **Buscar** para filtrar por las actividades, las fechas y los usuarios que desee auditar.
3. Exporte los resultados a Excel para continuar el análisis.

> [!IMPORTANT]
> Los datos de auditoría solo están visibles en el registro de auditoría si la auditoría está activada.

La cantidad de tiempo que un registro de auditoría se retiene y se puede buscar en el registro de auditoría depende de la suscripción a Microsoft 365 u Office 365, en concreto, el tipo de licencia que está asignada a los usuarios. Para obtener más información, consulte [Descripción del servicio del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Sugerencias para buscar en el registro de auditoría

Estas son algunas sugerencias para buscar actividades de Teams en el registro de auditoría.

![Captura de pantalla de la página de búsqueda de registro de auditoría](media/audit-log-search-page.png)

- Puede seleccionar actividades específicas para buscarlas haciendo clic en el nombre de la actividad. También puede hacer clic en el nombre del grupo para buscar todas las actividades de un grupo (como **actividades de archivos y carpetas**). Si una actividad está seleccionada, puede hacer clic en ella para cancelar la selección. También puede usar el cuadro de búsqueda para mostrar las actividades que contienen la palabra clave que escriba.<br>
    ![Captura de pantalla de búsqueda de registro de auditoría](media/audit-log-search.png)
- Para mostrar los eventos de actividades que se ejecutan con los cmdlets, seleccione **Mostrar resultados para todas las actividades** en la lista **actividades** . Si conoce el nombre de la operación de estas actividades, busque todas las actividades y, a continuación, filtre los resultados escribiendo el nombre de la operación en el cuadro de la columna **actividad** . Para obtener más información, consulte [paso 3: filtrar los resultados de la búsqueda](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance?view=o365-worldwide#step-3-filter-the-search-results).
- Para borrar los criterios de búsqueda actuales, haga clic en **Borrar**. El intervalo de fechas vuelve al valor predeterminado de los últimos siete días. También puede hacer clic en **Borrar todo para mostrar los resultados de todas las actividades** para cancelar todas las actividades seleccionadas.
- Si se encuentran resultados de 5.000, probablemente se dé por supuesto que hay más de 5.000 eventos que cumplen los criterios de búsqueda. Puede restringir los criterios de búsqueda y volver a ejecutar la búsqueda para que devuelva menos resultados, o bien puede exportar todos los resultados de la búsqueda seleccionando **exportar resultados**  >  **descargar todos los resultados**.

Consulte [este vídeo](https://www.youtube.com/embed/UBxaRySAxyE) para usar la búsqueda de registros de audio. Únase a Acharya, un jefe de programa de Teams, ya que muestra cómo realizar una búsqueda de registros de auditoría para equipos.

## <a name="use-cloud-app-security-to-set-activity-policies"></a>Usar Cloud App Security para establecer directivas de actividad

Con la integración de seguridad de la [aplicación en la nube de Microsoft](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) , puede configurar [directivas de actividades](https://docs.microsoft.com/cloud-app-security/user-activity-policies) para exigir una amplia variedad de procesos automatizados mediante las API del proveedor de aplicaciones. Estas directivas le permiten supervisar actividades específicas realizadas por varios usuarios o cumplir las tarifas inesperadas de un determinado tipo de actividad.

Después de establecer una directiva de detección de actividad, comienza a generar alertas. Las alertas solo se generan en las actividades que se producen después de crear la Directiva. Estos son algunos escenarios de ejemplo de cómo puede usar las directivas de actividad en Cloud App Security para supervisar las actividades de Teams.

### <a name="external-user-scenario"></a>Escenario de usuario externo

Un escenario que quizás desee mantener a la vista desde una perspectiva empresarial es la adición de usuarios externos a su entorno de equipos. Si los usuarios externos están habilitados, la supervisión de su presencia es una buena idea.  Puede usar [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para identificar amenazas potenciales.

![Captura de pantalla de una lista de eventos desencadenada por eliminaciones masivas](media/TeamsExternalUserAddPolicy.png)

La captura de pantalla de esta directiva para supervisar la adición de usuarios externos le permite asignar un nombre a la Directiva, establecer la gravedad según las necesidades de su empresa, establecerla como (en este caso) una sola actividad y, a continuación, establecer los parámetros que solo supervisarán específicamente la adición de usuarios no internos y limitarán esta actividad a teams.

Los resultados de esta Directiva se pueden ver en el registro de actividades:

![Captura de pantalla de una lista de eventos desencadenada por eliminaciones masivas](media/TeamsExternalUserList.png)

Aquí puede revisar las coincidencias con la Directiva que ha establecido, realizar los ajustes necesarios, o exportar los resultados para usarlos en otro lugar.

### <a name="mass-delete-scenario"></a>Escenario de eliminación masiva

Como se mencionó anteriormente, puede supervisar los escenarios de eliminación. Es posible crear una directiva que supervisará la eliminación masiva de sitios de Teams. En este ejemplo, se configura una directiva basada en alertas para detectar la eliminación masiva de Teams en un período de 30 minutos.

![Captura de pantalla de la página creación de directiva que muestra la configuración de una directiva para la detección masiva de la eliminación de equipos](media/TeamsMassDeletePolicy.png)

Como se muestra en la captura de pantalla, puede establecer muchos parámetros diferentes para que esta directiva supervise las eliminaciones de Teams, incluyendo la gravedad, una acción única o repetida, y los parámetros que limitan esta posibilidad a los equipos y la eliminación de sitios. Esto puede hacerse independientemente de una plantilla o puede tener una plantilla creada para basar esta Directiva, según las necesidades de la organización.

Una vez que haya establecido una directiva que funcione para su empresa, podrá revisar los resultados en el registro de actividades a medida que se activen los eventos:

![Captura de pantalla de una lista de eventos desencadenada por eliminaciones masivas](media/TeamsMassDeleteList.png)

Puede filtrar hasta la Directiva que haya establecido para ver los resultados de esa Directiva. Si los resultados que recibe en el registro de actividades no son satisfactorios (quizá haya un gran número de resultados o nada), esto puede ayudarle a ajustar la consulta para hacerla más relevante para lo que necesita.

### <a name="alert-and-governance-scenario"></a>Escenario de alertas y gobernanza

Puede establecer alertas y enviar correos electrónicos a administradores y a otros usuarios cuando se desencadena una directiva de actividad. Puede configurar acciones de gobierno automatizadas, como suspender un usuario o hacer que el usuario inicie sesión de nuevo de una manera automatizada. En este ejemplo se muestra cómo se puede suspender una cuenta de usuario cuando se desencadena una directiva de actividad y se determina que un usuario ha eliminado dos o más equipos en 30 minutos.

![Captura de pantalla de alertas y acciones de gobierno para una directiva de actividad](media/audit-log-governance.png)

## <a name="use-cloud-app-security-to-set-anomaly-detection-policies"></a>Usar Cloud App Security para establecer directivas de detección de anomalías

[Las directivas de detección de anomalías](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy) de seguridad de aplicaciones en la nube proporcionan análisis de comportamiento de entidad y de usuario (UEBA) y aprendizaje de máquina (ml) listos para usar, de modo que pueda ejecutar inmediatamente en todo el entorno de la nube. Debido a que se habilitan automáticamente, las nuevas políticas de detección de anomalías proporcionan resultados inmediatos proporcionando detecciones inmediatas, dirigidas a numerosas anomalías de comportamiento entre los usuarios y los equipos y dispositivos conectados a la red. Además, las nuevas directivas exponen más datos del motor de detección de seguridad de la aplicación en la nube para ayudarle a acelerar el proceso de investigación y a contener amenazas actuales.

Estamos trabajando para integrar eventos de Teams en directivas de detección de anomalías. Por el momento, puede configurar directivas de detección de anomalías para otros productos de Office y tomar medidas para los usuarios que coincidan con esas directivas.

## <a name="teams-activities"></a>Actividades de Teams

Esta es una lista de todos los eventos que se registran para las actividades de usuario y de administrador en Teams en el registro de auditoría de Microsoft 365. La tabla incluye el nombre descriptivo que se muestra en la columna **actividades** y el nombre de la operación correspondiente que aparece en la información detallada de un registro de auditoría y en el archivo CSV al exportar los resultados de la búsqueda.

|Nombre descriptivo  |Operación|Descripción |
|---------|---------|---------|
|Bot agregado al equipo   |BotAddedToTeam        |Un usuario agrega un bot a un equipo.        |
|Agregación de canales   |ChannelAdded         |Un usuario agrega un canal a un equipo.         |
|Conector agregado  |ConnectorAdded          |Un usuario agrega un conector a un canal.        |
|Miembros agregados    |MemberAdded         |El propietario de un equipo agrega miembros a un equipo, a un canal o a un chat grupal.         |
|Pestaña agregada    |TabAdded         |Un usuario agrega una ficha a un canal.        |
|Configuración de canal cambiada    |ChannelSettingChanged         |La operación ChannelSettingChanged se registra cuando un miembro del equipo realiza las siguientes actividades. Para cada una de estas actividades, se muestra una descripción de la opción de configuración que se ha cambiado (entre paréntesis, en la columna **elemento** de los resultados de la búsqueda de registros de auditoría. <ul><li>Cambia el nombre de un canal de equipo (**nombre de canal**)</li><li>Descripción de los cambios de un canal de equipo (**Descripción del canal**)</li> </ul>      |
|Configuración de organización cambiada   |TeamsTenantSettingChanged         |La operación TeamsTenantSettingChanged se registra cuando un administrador global realiza las siguientes actividades en el centro de administración de Microsoft 365. Estas actividades afectan a la configuración de Teams de toda la organización. Para obtener más información, vea [administrar la configuración de Teams para su organización](enable-features-office-365.md). <br>Para cada una de estas actividades, se muestra una descripción de la opción de configuración que se cambió (que se muestra entre paréntesis) en la columna **elemento** de los resultados de búsqueda de registro de auditoría.<ul><li>Habilita o deshabilita Teams para la organización (**Microsoft Teams**).</li><li>Habilita o deshabilita la interoperabilidad entre Microsoft Teams y Skype empresarial para la organización (**interoperabilidad de Skype**empresarial).</li><li>Habilita o deshabilita la vista de organigrama en clientes de Microsoft Teams (**vista de organigrama**).</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo programen reuniones privadas (**programación de reuniones privadas**).</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo programen reuniones de canal (**programación de reuniones de canal**).</li><li>Habilita o deshabilita las videollamadas en las reuniones de Teams (**vídeo para reuniones de Skype**).</li><li>Habilita o deshabilita la pantalla compartida en Microsoft Teams reuniones microsoftteams para la organización (**uso compartido de pantalla para reuniones de Skype**).</li><li>Habilita o deshabilita la posibilidad de agregar imágenes animadas (denominadas imágenes giphy) a las conversaciones de Teams (**imágenes animadas**).</li><li>Cambia la configuración de la clasificación de contenido de la organización (**clasificación de contenido**). La clasificación de contenido restringe el tipo de imagen animada que se puede mostrar en las conversaciones.</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo agreguen imágenes personalizables (denominadas memes personalizados) de Internet a las conversaciones del equipo (**imágenes personalizables de Internet**).</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo agreguen imágenes editables (denominadas adhesivos) a las conversaciones del equipo (**imágenes editables**).</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo usen bots en los chats y canales de Microsoft Teams (**bots en toda la organización)**.</li><li>Habilita bots específicos para Microsoft Teams. Esto no incluye a T-bot, que es el bot de ayuda de Microsoft teams que está disponible cuando se habilitan los bots para la organización (**bots individuales**).</li><li>Habilita o deshabilita la posibilidad de que los miembros del equipo agreguen extensiones o pestañas (**extensiones o pestañas**).</li><li>Habilita o deshabilita la carga de prueba de los bots de propiedad para Microsoft Teams (**carga de caras de bots**).</li><li>Habilita o deshabilita la posibilidad de que los usuarios envíen mensajes de correo electrónico a un canal de Microsoft Teams (**correo electrónico de canal**).</li></ul>|
|Se ha cambiado el rol de miembros en el equipo    |MemberRoleChanged         |Un propietario del equipo cambia el rol de los miembros de un equipo. Los siguientes valores indican el tipo de rol asignado al usuario. <br><br>**1** : indica el rol propietario.<br>**2** -indica el rol miembro.<br>**3** : indica el rol invitado.<br><br>La propiedad Members también incluye el nombre de la organización y la dirección de correo electrónico del miembro.        |
|Configuración de equipo cambiada    |TeamSettingChanged        |La operación TeamSettingChanged se registra cuando el propietario de un equipo realiza las siguientes actividades. Para cada una de estas actividades, se muestra una descripción de la opción de configuración que se cambió (que se muestra entre paréntesis) en la columna **elemento** de los resultados de búsqueda de registro de auditoría.<ul><li>Cambia el tipo de acceso de un equipo. Los equipos pueden establecerse como privados o públicos (**tipo de acceso de equipo**). Cuando un equipo es privado (configuración predeterminada), los usuarios solo pueden acceder al equipo mediante invitación. Cuando un equipo es público, lo puede detectar cualquier persona.</li><li>Cambia la clasificación de la información de un equipo (**clasificación de equipo**). Por ejemplo, los datos de equipo se pueden clasificar como alto impacto empresarial, impacto empresarial medio o impacto empresarial bajo.</li><li>Cambia el nombre de un equipo (**nombre del equipo**).</li><li>Cambia la descripción del equipo (**Descripción del equipo**).</li><li>Cambios realizados en la configuración del equipo. Para tener acceso a esta configuración, un propietario del equipo puede hacer clic con el botón secundario en un equipo, seleccionar **administrar equipo**y, a continuación, hacer clic en la pestaña **configuración** . Para estas actividades, el nombre de la opción de configuración que se cambió se muestra en la columna **elemento** de los resultados de búsqueda de registro de auditoría.</li></ul>         |
|Equipo creado    |TeamCreated         |Un usuario crea un equipo.         |
|Eliminadas todas las aplicaciones de la organización|DeletedAllOrganizationApps           |Se han eliminado todas las aplicaciones de la organización del catálogo.     |
|Aplicación eliminada |AppDeletedFromCatalog           |Se ha eliminado una aplicación del catálogo.     |
|Canal eliminado     |ChannelDeleted         |Un usuario elimina un canal de un equipo.         |
|Equipo eliminado  |TeamDeleted            |El propietario de un equipo elimina un equipo.      |
|Aplicación instalada |AppInstalled         |Se instaló una aplicación.   |
|Acción realizada en la tarjeta|PerformedCardAction|Un usuario tomó medidas en una tarjeta adaptativa dentro de una conversación. Los bots suelen usar tarjetas adaptables para permitir la visualización enriquecida de la información y la interacción en los chats. <br/><br/>**Nota:** Solo las acciones de entrada en línea en una tarjeta adaptable dentro de una conversación estarán disponibles en el registro de auditoría. Por ejemplo, cuando un usuario envía una respuesta de sondeo en una conversación de canal en una tarjeta adaptativa generada por un bot de sondeo. Las acciones del usuario, como "resultado de la vista", que abrirá un cuadro de diálogo, o las acciones de usuario dentro de los cuadros de diálogo no estarán disponibles en el registro de auditoría.|
|Aplicación publicada |AppPublishedToCatalog           |Se agregó una aplicación al catálogo.     |
|Bot quitado del equipo   |BotRemovedFromTeam         |Un usuario quita un bot de un equipo.       |
|Conector quitado     |ConnectorRemoved         |Un usuario quita un conector de un canal.         |
|Miembros quitados    |MemberRemoved        |El propietario de un equipo elimina los miembros de un equipo, un canal o un chat grupal.         |
|Pestaña quitada    |TabRemoved         |Un usuario quita una ficha de un canal.         |
|Aplicación desinstalada |AppUninstalled           |Se desinstaló una aplicación.     |
|Aplicación actualizada |AppUpdatedInCatalog           |Se actualizó una aplicación en el catálogo.     |
|Conector actualizado    |ConnectorUpdated         |Un usuario ha modificado un conector en un canal.         |
|Pestaña actualizado   |TabUpdated         |Un usuario ha modificado una pestaña en un canal.         |
|Aplicación actualizada |AppUpgraded           |Una aplicación se ha actualizado a su última versión en el catálogo.     |
|Usuario ha iniciado sesión en Teams     |TeamsSessionStarted         |Un usuario inicia sesión en un cliente de Microsoft Teams. Este evento no captura actividades de actualización de token.         |

## <a name="shifts-in-teams-activities"></a>Cambios en las actividades de Teams

**(en la versión preliminar)**

Si su organización usa la aplicación turnos en Teams, puede buscar en el registro de auditoría las actividades relacionadas con la aplicación turnos. Esta es una lista de todos los eventos que se han registrado para desplazar actividades en Teams en el registro de auditoría de Microsoft 365.

|Nombre descriptivo  |Operación  |Descripción  |
|---------|---------|---------|
|Grupo de programación agregado      |SchedulingGroupAdded          |Un usuario agrega correctamente un nuevo grupo de programación a la programación.          |
|Grupo de programación editado     |SchedulingGroupEdited         |Un usuario modifica correctamente un grupo de programación.          |
|Grupo de programación eliminado         |SchedulingGroupDeleted              |Un usuario elimina correctamente un grupo de programación de la programación.|
|Se ha agregado un turno      |ShiftAdded          |Un usuario agrega un turno correctamente.           |
|Turno modificado       |ShiftEdited       |Un usuario modifica correctamente un turno.        |
|Turno eliminado          |ShiftDeleted          | Un usuario elimina correctamente un turno.               |
|Se ha agregado un tiempo libre      |TimeOffAdded          |Un usuario agrega correctamente el tiempo libre en la programación.          |
|Hora de modificación         |TimeOffEdited           |Un usuario modifica correctamente la hora.          |
|Tiempo eliminado     |TimeOffDeleted              |Un usuario elimina correctamente el permiso.           |
|Se agregó el turno de apertura     |OpenShiftAdded          |Un usuario agrega correctamente un turno abierto a un grupo de programación.          |
|Turno abierto modificado    |OpenShiftEdited          |Un usuario modifica correctamente un turno abierto en un grupo de programación.          |
|Turno de apertura eliminado      |OpenShiftDeleted          |Un usuario elimina correctamente un turno abierto de un grupo de programación.         |
|Programación compartida     |ScheduleShared                  |Un usuario ha compartido correctamente una programación de equipo para un intervalo de fechas.          |
|Cronometrado con el reloj de tiempo         |ClockedIn          |Un usuario registra correctamente el reloj con el reloj de tiempo.          |
|Hora de salida con reloj de tiempo      |ClockedOut          |Un usuario registra correctamente el reloj de tiempo.          |
|Se inició la interrupción con el reloj de tiempo      |BreakStarted          |Un usuario inicia correctamente una interrupción durante una sesión de tiempo activa.          |
|Terminada la pausa con el reloj de tiempo    |BreakEnded          |Un usuario termina correctamente un salto durante una sesión de tiempo activa.          |
|Se ha agregado una entrada de reloj de tiempo     |TimeClockEntryAdded          |Un usuario agrega correctamente una nueva entrada de reloj de tiempo manual en la hoja de tiempo.          |
|Entrada de reloj de tiempo modificada     | TimeClockEntryEdited             |Un usuario modifica correctamente una entrada de reloj de tiempo en hoja de horas.          |
|Entrada de reloj de tiempo eliminada    |TimeClockEntryDeleted              |Un usuario elimina correctamente una entrada de reloj en la hoja de tiempo.          |
|Solicitud de turno agregada         |RequestAdded              |Un usuario ha agregado una solicitud de turno.          |
|Respuesta a una solicitud de turno     |RequestRespondedTo                  |Un usuario respondió a una solicitud de turno.          |
|Solicitud de turno cancelada         |RequestCanceled               |Un usuario canceló una solicitud de turno.          |
|Configuración de programación modificada      |ScheduleSettingChanged          |Un usuario cambia una configuración en la configuración de Mayús.         |
|Se ha agregado la integración de personal      |WorkforceIntegrationAdded                  | La aplicación de turnos está integrada en un sistema de terceros.         |
|Mensaje de turno aceptado         |OffShiftDialogAccepted          |Un usuario reconoce el mensaje de desplazarse para acceder a teams después de haber cambiado de horas.           |

## <a name="office-365-management-activity-api"></a>API de actividad de administración 365 de Office

Puede usar la API de actividad de administración de Office 365 para recuperar información sobre los eventos de Teams. Para obtener más información sobre el esquema API de administración de la actividad de los equipos, consulte [esquema de equipos](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).


## <a name="attribution-in-teams-audit-logs"></a>Atribución en los registros de auditoría de Teams

En la actualidad, existe un problema conocido con la atribución de los registros de auditoría de Teams y los mensajes de control: es posible que un propietario no se haya atribuido correctamente con la eliminación o adición de usuarios. Esto sucede cuando el cambio se produce fuera de Teams. En estos casos, le recomendamos que use los [registros de auditoría de Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="related-topics"></a>Temas relacionados

- [Buscar en el registro de auditoría del centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 
