---
title: Usar la API de envío de aplicaciones de Teams para enviar y aprobar las aplicaciones personalizadas
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo aprobar las aplicaciones personalizadas que se envían mediante la API de envío de aplicaciones de Teams en Microsoft Teams.
ms.openlocfilehash: 0003bc218b425383ba117296ba847a637d76ac43
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145807"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Publicar una aplicación personalizada enviada a través de la API de envío de aplicaciones de Teams

## <a name="overview"></a>Información general

> [!NOTE]
> Cuando publica una aplicación personalizada de Teams, está disponible para los usuarios de la tienda de aplicaciones de su organización. Hay dos formas de publicar una aplicación personalizada y la forma en que se usa depende de cómo obtenga la aplicación. **Este artículo se centra en cómo aprobar** y publicar una aplicación personalizada que envía un desarrollador a través de la API de envío de aplicaciones de Teams. El otro método, cargar una aplicación personalizada, se usa cuando un desarrollador le envía un paquete de aplicación en formato .zip. Para obtener más información sobre ese método, vea <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Publicar una aplicación personalizada cargando un paquete de aplicación.</a> El widget aprobar aplicación no está disponible en los inquilinos de GCC. 

> [!IMPORTANT]
> Este método no está disponible actualmente para entornos GCC. Debe usar el método *de carga de una aplicación* personalizada.

En este artículo se proporciona una guía integral sobre cómo llevar la aplicación de Teams del desarrollo a la implementación y la detección. Verá información general sobre las experiencias conectadas que Teams proporciona a lo largo del ciclo de vida de la aplicación para simplificar la forma de desarrollar, implementar y administrar aplicaciones personalizadas en la tienda de aplicaciones de su organización.

Abarcaremos cada paso del ciclo de vida, incluido cómo los desarrolladores pueden usar la API de envío de aplicaciones de Teams para enviar aplicaciones personalizadas directamente al Centro de administración de Microsoft Teams para que lo revise y apruebe, cómo establecer directivas para administrar las aplicaciones para los usuarios de su organización y cómo los usuarios las descubrirán en Teams.

![Información general sobre la aplicación, desde el desarrollo hasta la implementación](media/custom-app-lifecycle.png)

Esta guía se centra en los aspectos de Teams de la aplicación y está destinada a administradores y profesionales de TI. Para obtener información sobre el desarrollo de aplicaciones de Teams, consulte la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentación para desarrolladores de Teams.</a>

## <a name="develop"></a>Desarrollar

### <a name="create-the-app"></a>Crear la aplicación

La plataforma para desarrolladores de Microsoft Teams permite a los desarrolladores integrar sus propias aplicaciones y servicios para mejorar la productividad, tomar decisiones más rápidamente y crear colaboración en torno al contenido y los flujos de trabajo existentes. Las aplicaciones creadas en la plataforma Teams son puentes entre el cliente de Teams y sus servicios y flujos de trabajo, lo que las lleva directamente al contexto de su plataforma de colaboración. Para obtener más información, vaya a la documentación <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">para desarrolladores de Teams.</a>

### <a name="submit-the-app"></a>Enviar la aplicación

Cuando la aplicación está lista para su uso en producción, el desarrollador puede enviar la aplicación mediante la API de envío de aplicaciones de Teams, a la que se puede llamar desde <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">graph API,</a>un entorno de desarrollo integrado (IDE) como Visual Studio Code, o una plataforma como Power Apps y Power Virtual Agents. Al hacerlo, la aplicación <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a> estará disponible en la página Administrar aplicaciones del Centro de administración de Microsoft Teams, donde usted, como administrador, puede revisarla y aprobarla. esto

La API de envío de aplicaciones de Teams, integrada en <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph,</a>permite a su organización desarrollarse en la plataforma de su elección y automatiza el proceso de envío a aprobación de aplicaciones personalizadas en Teams.

Este es un ejemplo del aspecto que tiene este paso de envío de aplicaciones en Visual Studio código:

![enviar una aplicación en el Visual Studio correo](media/custom-app-lifecycle-submit-app.png)

Tenga en cuenta que esto todavía no publica la aplicación en la tienda de aplicaciones de su organización. En este paso, la aplicación se envía al Centro de administración de Microsoft Teams, donde puede aprobarla para su publicación en la tienda de aplicaciones de su organización.

Para obtener más información sobre el uso de la API Graph para enviar aplicaciones, vea <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">aquí.</a>

## <a name="validate"></a>Validar

La <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">página Administrar</a> aplicaciones del Centro de administración de Microsoft Teams (en el panel de navegación izquierdo, vaya a Administrar aplicaciones de **Teams),** le ofrece una vista de todas las aplicaciones de  >  Teams de su organización. El **widget Aprobación** pendiente en la parte superior de la página le permite saber cuándo se envía una aplicación personalizada para su aprobación.

En la tabla, una aplicación que  acaba de enviar muestra automáticamente el estado De publicación de Enviado **y** **Estado de** **Bloqueado.** Puede ordenar la **columna de estado de** publicación en orden descendente para encontrar rápidamente la aplicación.

![estado de publicación ](media/custom-app-lifecycle-validate-app.png)

Haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación. En la **pestaña** Acerca de, puede ver detalles sobre la aplicación, como la descripción, el estado, el enviador y el id. de la aplicación.

![página de detalles de la aplicación para una aplicación enviada](media/custom-app-lifecycle-app-details.png)

Para obtener más información sobre el uso de la API de Graph para comprobar el estado **de publicación,** vea <a href="https://docs.microsoft.com/graph/api/appcatalogs-list-teamsapps?view=graph-rest-beta&tabs=http#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">aquí.</a>

## <a name="publish"></a>Publicar

Cuando esté listo para que la aplicación esté disponible para los usuarios, publique la aplicación.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones**  >  **de** Teams.
2. Haga clic en el nombre de la aplicación  para ir a la página de detalles de la aplicación y, a continuación, en el cuadro Estado de publicación, **seleccione Publicar.**

    Después de publicar la aplicación, el **estado de publicación** cambia a **Publicado** y **el** estado cambia automáticamente a **Permitido.**

## <a name="set-up-and-manage"></a>Configurar y administrar

### <a name="control-access-to-the-app"></a>Controlar el acceso a la aplicación

De forma predeterminada, todos los usuarios de su organización pueden acceder a la aplicación en la tienda de aplicaciones de su organización. Para restringir y controlar quién tiene permiso para usar la aplicación, puede crear y asignar una directiva de permisos de aplicación. Para obtener más información, consulte <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Administrar directivas de permisos de aplicaciones en Teams.</a>

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anclar e instalar la aplicación para que los usuarios puedan descubrir

De forma predeterminada, para que los usuarios puedan encontrar la aplicación, tienen que ir a la tienda de aplicaciones de su organización y examinarla o buscarla. Para que a los usuarios le sea más fácil acceder a ella, puede anclar la aplicación a la barra de la aplicación en Teams. Para ello, cree una directiva de configuración de la aplicación y asígnela a los usuarios. Para obtener más información, consulte <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Administrar directivas de configuración de aplicaciones en Teams.</a>

### <a name="search-the-audit-log-for-teams-app-events"></a>Buscar eventos de la aplicación Teams en el registro de auditoría

Puede buscar en el registro de auditoría para ver la actividad de las aplicaciones de Teams en su organización. Para obtener más información sobre cómo buscar en el registro de auditoría y ver una lista de las actividades de Teams que se registran en el registro de auditoría, vea Buscar eventos en el registro de auditoría <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">en Teams.</a>

Antes de poder buscar en el registro de auditoría, primero tiene que activar la auditoría en el Centro de seguridad & <a href="https://protection.office.com" target="_blank">cumplimiento.</a> Para obtener más información, vea Activar o desactivar la búsqueda <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">del registro de auditoría.</a> Tenga en cuenta que los datos de auditoría solo están disponibles desde el punto en el que ha activado la auditoría.

## <a name="discover-and-adopt"></a>Descubrir y adoptar

Los usuarios que tienen permisos para la aplicación pueden encontrarla en la tienda de aplicaciones de su organización. Vaya a **Creado para el nombre de *su*** organización en la página Aplicaciones para buscar las aplicaciones personalizadas de su organización.

![Página Aplicaciones que muestra la aplicación publicada ](media/custom-app-lifecycle-discovery.png)

Si creó y asignó una directiva de configuración de aplicaciones, la aplicación se ancla a la barra de aplicaciones de Teams para facilitar el acceso a los usuarios a los que se asignó la directiva.

## <a name="update"></a>Actualización

Para actualizar una aplicación, los desarrolladores deben seguir los pasos de la [sección](#develop) Desarrollar.

Cuando el desarrollador envíe una actualización a una aplicación personalizada publicada, se le notificará en el **widget** Aprobación pendiente de la <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">página Administrar</a> aplicaciones. En la tabla, el **estado de publicación** de la aplicación se establecerá en Actualizar **enviado.**

![Página Administrar aplicaciones que muestra las solicitudes pendientes y el estado de la aplicación ](media/custom-app-lifecycle-update-submitted.png)

Para revisar y publicar una actualización de la aplicación:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones**  >  **de** Teams.
2. Haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, seleccione **Actualizar disponible** para revisar los detalles de la actualización.

    ![página de detalles de la aplicación](media/custom-app-lifecycle-update-app.png)
3. Cuando esté listo, seleccione **Publicar para** publicar la actualización. Al hacerlo, se reemplaza la aplicación existente, se actualiza el número de versión y se cambia el **estado Publicación** **a Publicado.** Se siguen aplicando todas las directivas de permisos de aplicación y directivas de configuración de aplicaciones para la aplicación actualizada.

    Si rechaza la actualización, la versión anterior de la aplicación permanecerá publicada.

Tenga en cuenta lo siguiente:

- Cuando se aprueba una aplicación, cualquiera puede enviar una actualización a la aplicación. Esto significa que otros desarrolladores, incluido el desarrollador que envió originalmente la aplicación, pueden enviar una actualización a la aplicación.
- Cuando un desarrollador envía una aplicación y la solicitud está pendiente, solo ese mismo desarrollador puede enviar una actualización a la aplicación. Otros desarrolladores pueden enviar una actualización solo después de que se apruebe la aplicación.

Para obtener más información sobre el uso de la API graph para actualizar aplicaciones, vea <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">aquí.</a>

### <a name="update-experience-for-users"></a>Experiencia de actualización para los usuarios

En la mayoría de los casos, después de publicar una actualización de la aplicación, la nueva versión aparece automáticamente para los usuarios. Sin embargo, hay algunas actualizaciones en el manifiesto de <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> que requieren la aceptación del usuario para completar:

* Se agregó o se eliminó un bot
* La propiedad "botId" de un bot existente ha cambiado
* La propiedad "isNotificationOnly" de un bot existente ha cambiado
* La propiedad "supportsFiles" del bot ha cambiado
* Se agregó o se eliminó una extensión de mensajería
* Se agregó un conector nuevo
* Se ha agregado una nueva pestaña estática
* Se ha agregado una nueva pestaña configurable
* Propiedades de "webApplicationInfo" cambiadas

![nueva versión disponible](media/manage-your-custom-apps-update1.png)

![opción de actualización para una aplicación](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Temas relacionados

- [Publicar una aplicación personalizada cargando un paquete de aplicación](upload-custom-apps.md)
- [Administrar las aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
- [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)
- <a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">API de Microsoft Graph para aplicaciones de Teams</a>
