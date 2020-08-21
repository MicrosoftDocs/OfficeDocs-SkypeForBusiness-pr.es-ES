---
title: Usar la API de envío de aplicaciones de Teams para enviar y aprobar aplicaciones personalizadas
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo aprobar las aplicaciones personalizadas que se envían con la API de envío de aplicaciones de Teams en Microsoft Teams.
ms.openlocfilehash: bdd13dbe4db46110250ea380eebd0ea1d011a322
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824921"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Publicar una aplicación personalizada enviada a través de la API de envío de la aplicación de Teams

## <a name="overview"></a>Información general

> [!NOTE]
> Al publicar una aplicación de Teams personalizada, esta estará disponible para los usuarios de la tienda de aplicaciones de su organización. Hay dos formas de publicar una aplicación personalizada y la forma de usarla depende de cómo obtenga la aplicación. **Este artículo se centra en cómo aprobar y publicar una aplicación personalizada que envía un desarrollador a través de la API de envío de la aplicación de Teams**. El otro método, cargar una aplicación personalizada, se usa cuando un desarrollador le envía un paquete de la aplicación en formato. zip. Para obtener más información sobre ese método, vea <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">publicar una aplicación personalizada mediante la carga de un paquete de la aplicación</a>.
 
En este artículo se proporcionan instrucciones completas sobre cómo llevar la aplicación de su equipo de desarrollo a la implementación hasta su descubrimiento. Obtendrá información general de las experiencias conectadas que Teams proporciona en el ciclo de vida de la aplicación para simplificar el desarrollo, la implementación y la administración de aplicaciones personalizadas en la tienda de aplicaciones de su organización.

Cubriremos cada paso del ciclo de vida, incluido el modo en que los desarrolladores pueden usar la API de envío de aplicaciones de Teams para enviar aplicaciones personalizadas directamente al centro de administración de Microsoft Teams para que las revise y apruebe, cómo establecer directivas para administrar las aplicaciones de los usuarios de su organización y cómo las descubren los usuarios en Teams.

![Información general de la aplicación desde el desarrollo hasta la implementación](media/custom-app-lifecycle.png)

Esta guía se centra en los aspectos de los equipos de la aplicación y está pensado para administradores y profesionales de ti. Para obtener información sobre el desarrollo de aplicaciones de Teams, consulte la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentación para desarrolladores de Teams</a>.

## <a name="develop"></a>Desarrollar

### <a name="create-the-app"></a>Crear la aplicación

La plataforma de desarrollo de Microsoft Teams facilita la integración de sus propias aplicaciones y servicios para mejorar la productividad, tomar decisiones más rápido y crear colaboración sobre el contenido y los flujos de trabajo existentes. Las aplicaciones integradas en la plataforma de Teams son puentes entre el cliente de Teams y los servicios y flujos de trabajo, que se incluyen directamente en el contexto de la plataforma de colaboración. Para obtener más información, vaya a la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentación para desarrolladores de Teams</a>.

### <a name="submit-the-app"></a>Enviar la aplicación

Cuando la aplicación está lista para su uso en producción, el desarrollador puede enviar la aplicación mediante la API de envío de la aplicación de Teams, a la que se puede llamar desde la <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">API Graph</a>, un entorno de desarrollo integrado (IDE), como código de Visual Studio, o una plataforma como Power apps y Power virtual Agents. Esto hace que la aplicación esté disponible en la página <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Administrar aplicaciones</a> del centro de administración de Microsoft Teams, donde usted, el administrador, puede revisarla y aprobarla. 

La API de envío de la aplicación de Teams, <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">creada en Microsoft Graph</a>, permite a su organización desarrollar en la plataforma de su elección y automatiza el proceso de envío para la aprobación de aplicaciones personalizadas en Teams.

Este es un ejemplo del aspecto de este paso de envío de la aplicación en el código de Visual Studio:

![Captura de pantalla del envío de una aplicación en Visual Studio Code](media/custom-app-lifecycle-submit-app.png)

Tenga en cuenta que esto no publica aún la aplicación en la tienda de aplicaciones de su organización. Este paso envía la aplicación al centro de administración de Microsoft Teams, donde puede aprobarla para publicarla en la tienda de aplicaciones de su organización.

Para obtener más información sobre el uso de la API Graph para enviar aplicaciones, consulte <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">aquí</a>.

## <a name="validate"></a>Valide

La página <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> en el centro de administración de Microsoft Teams (en el navegación izquierdo, vaya a **aplicaciones de Teams**  >  **Manage apps**), le ofrece una vista de todas las aplicaciones de Teams para su organización. El widget **aprobación pendiente** en la parte superior de la página le permite saber cuándo se envía una aplicación personalizada para su aprobación.

En la tabla, una aplicación recién enviada muestra automáticamente un **Estado de publicación** de **enviado** y el **Estado** de **bloqueado**. Puede ordenar la columna **Estado de publicación** en orden descendente para buscar rápidamente la aplicación.

![Captura de pantalla de la página Administrar aplicaciones que muestra las solicitudes pendientes y el estado de la aplicación ](media/custom-app-lifecycle-validate-app.png)

Haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación. En la pestaña **acerca** de, puede ver los detalles de la aplicación, incluidos la descripción, el estado, el remitente y el identificador de la aplicación.

![Captura de pantalla de la página de detalles de la aplicación para una aplicación enviada](media/custom-app-lifecycle-app-details.png)

Para obtener más información sobre el uso de la API Graph para comprobar el estado de la **publicación**, consulte <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">aquí</a>.

## <a name="publish"></a>Publicar

Cuando esté listo para hacer que la aplicación esté disponible para los usuarios, publique la aplicación.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**.
2. Haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y luego, en el cuadro **Estado de publicación** , seleccione **publicar**.

    Después de publicar la aplicación, el **Estado de publicación** cambia a **publicado** y el **Estado** cambia automáticamente a **permitido**.

## <a name="set-up-and-manage"></a>Configurar y administrar

### <a name="control-access-to-the-app"></a>Controlar el acceso a la aplicación

De forma predeterminada, todos los usuarios de su organización pueden acceder a la aplicación en la tienda de aplicaciones de su organización. Para restringir y controlar quién tiene permiso para usar la aplicación, puede crear y asignar una directiva de permisos de aplicación. Para obtener más información, vea <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Administrar directivas de permisos de aplicaciones en Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anclar e instalar la aplicación para que los usuarios puedan descubrir

De forma predeterminada, para que los usuarios encuentren la aplicación, deben ir a la tienda de aplicaciones de su organización y examinarla o buscarla. Para facilitar a los usuarios el acceso a la aplicación, puede anclar la aplicación a la barra de aplicaciones de Teams. Para ello, cree una directiva de configuración de aplicaciones y asígnela a los usuarios. Para obtener más información, vea <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Administrar directivas de configuración de aplicaciones en Teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Buscar eventos de aplicaciones de Teams en el registro de auditoría

Puede buscar en el registro de auditoría para ver la actividad de las aplicaciones de Teams de su organización. Para obtener más información sobre cómo buscar en el registro de auditoría y ver una lista de las actividades de Teams registradas en el registro de auditoría, consulte <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">buscar eventos en el registro de auditoría de los equipos</a>.

Antes de poder buscar en el registro de auditoría, primero debe activar la auditoría en el <a href="https://protection.office.com" target="_blank">centro de cumplimiento de & de seguridad</a>. Para obtener más información, vea <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">activar o desactivar la búsqueda de registros de auditoría</a>. Tenga en cuenta que los datos de auditoría solo están disponibles desde el punto en el que activó la auditoría.

## <a name="discover-and-adopt"></a>Descubrir y aprobar

Los usuarios que tienen permisos para la aplicación pueden encontrarla en la tienda de aplicaciones de su organización. Vaya a **creado para *el nombre* ** de la organización en la página aplicaciones para buscar las aplicaciones personalizadas de su organización.

![Captura de pantalla de la página de aplicaciones que muestra la aplicación publicada ](media/custom-app-lifecycle-discovery.png)

Si creó y asignó una directiva de configuración de aplicaciones, la aplicación está anclada a la barra de aplicaciones de Teams para facilitar el acceso a los usuarios que se asignaron a la Directiva.

## <a name="update"></a>Actualización

Para actualizar una aplicación, los desarrolladores deben seguir los pasos de la sección [desarrollar](#develop) .

Cuando el desarrollador envía una actualización a una aplicación personalizada publicada, recibirá una notificación en el widget **aprobación pendiente** de la página <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> . En la tabla, el **Estado de publicación** de la aplicación se establecerá en **Actualizar enviado**.

![Captura de pantalla de la página Administrar aplicaciones que muestra las solicitudes pendientes y el estado de la aplicación ](media/custom-app-lifecycle-update-submitted.png)

Para revisar y publicar una actualización de la aplicación:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**.
2. Haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, seleccione **actualización disponible** para revisar los detalles de la actualización.

    ![Captura de pantalla de la página Administrar aplicaciones que muestra las solicitudes pendientes y el estado de la aplicación ](media/custom-app-lifecycle-update-app.png)
3. Cuando esté listo, seleccione **publicar** para publicar la actualización. Al hacerlo, se reemplaza la aplicación existente, se actualiza el número de versión y se cambia el **Estado de publicación** a **publicado**. Todas las directivas de permisos de aplicaciones y directivas de configuración de la aplicación siguen aplicándose para la aplicación actualizada.

    Si rechazas la actualización, la versión anterior de la aplicación permanece publicada.

Tenga en cuenta lo siguiente:

- Cuando se aprueba una aplicación, cualquier persona puede enviar una actualización a la aplicación. Esto significa que otros desarrolladores, incluido el desarrollador que originalmente envió la aplicación, pueden enviar una actualización a la aplicación.
- Cuando un desarrollador envía una aplicación y la solicitud está pendiente, solo el mismo desarrollador puede enviar una actualización a la aplicación. Otros desarrolladores pueden enviar una actualización solo después de que se apruebe la aplicación.

Para obtener más información sobre el uso de la API Graph para actualizar aplicaciones, vea <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">aquí</a>.

### <a name="update-experience-for-users"></a>Actualizar la experiencia de los usuarios

En la mayoría de los casos, después de publicar una actualización de la aplicación, la nueva versión aparece automáticamente para los usuarios. Sin embargo, hay algunas actualizaciones del <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">manifiesto de Microsoft Teams</a> que requieren la aceptación del usuario:

* Se ha agregado o eliminado un bot
* Ha cambiado la propiedad "botId" de un bot existente
* Ha cambiado la propiedad "isNotificationOnly" de un bot existente
* La propiedad "supportsFiles" del bot ha cambiado
* Se ha agregado o eliminado una extensión de mensajería
* Se agregó un nuevo conector
* Se ha agregado una nueva pestaña estática
* Se ha agregado una nueva pestaña configurable
* Las propiedades de "webApplicationInfo" han cambiado

![Captura de pantalla que muestra las aplicaciones que tienen una nueva versión disponible](media/manage-your-custom-apps-update1.png)

![Captura de pantalla de la opción de actualización de una aplicación](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Temas relacionados

- [Publicar una aplicación personalizada mediante la carga de un paquete de la aplicación](upload-custom-apps.md)
- [Administrar las aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
- [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)
- <a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">API de Microsoft Graph para aplicaciones de Teams</a>
