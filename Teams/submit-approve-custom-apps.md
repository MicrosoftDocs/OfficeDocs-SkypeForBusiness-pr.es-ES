---
title: Usar la API de envío de aplicaciones de Teams para enviar y aprobar sus aplicaciones personalizadas
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/19/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información sobre cómo aprobar las aplicaciones personalizadas que se envían con la API de envío de aplicaciones de Teams en Microsoft Teams.
ms.openlocfilehash: 83a4896fbd849cf55020854fd617da003d589cb0
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131269"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>Publicar una aplicación personalizada enviada con la API de envío de aplicaciones de Teams

Este artículo proporciona una guía de principio a fin para llevar su aplicación de Teams desde el desarrollo pasando por la implementación hasta su descubrimiento. Obtendrá información general sobre las experiencias conectadas que Teams proporciona en todo el ciclo de vida de la aplicación para simplificar la forma de desarrollar, implementar y administrar aplicaciones personalizadas en la tienda de aplicaciones de su organización.

Trataremos cada paso del ciclo de vida, incluido cómo los desarrolladores pueden usar la API de envío de aplicaciones de Teams para enviar aplicaciones personalizadas directamente al Centro de administración de Microsoft Teams para que las revise y apruebe, cómo establecer directivas para administrar aplicaciones para los usuarios de su organización y cómo los usuarios las descubren en Teams.

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="Información general sobre la aplicación, desde el desarrollo hasta la implementación.":::

Esta guía se centra en los aspectos de Teams de la aplicación y está destinada a administradores y profesionales de TI. Para obtener información sobre el desarrollo de aplicaciones de Teams, consulte la [documentación del desarrollador de Teams](/microsoftteams/platform).

> [!NOTE]
> Al publicar una aplicación de Teams personalizada, está disponible para los usuarios de la tienda de aplicaciones de su organización. Hay dos formas de publicar una aplicación personalizada y la manera en que se usan depende de cómo se obtiene la aplicación. Este artículo se centra en cómo aprobar y publicar una aplicación personalizada que envía un desarrollador a través de la API de envío de aplicaciones de Teams. El otro método, cargar una aplicación personalizada, se usa cuando un desarrollador le envía un paquete de aplicación en .zip formato. Para obtener más información sobre ese método, vea [Publicar una aplicación personalizada cargando un paquete de aplicación](/microsoftteams/upload-custom-apps). El widget aprobar aplicación no está disponible en los inquilinos de GCC.

> [!IMPORTANT]
> Este método no está disponible en entornos GCC. [Cargue una aplicación personalizada](upload-custom-apps.md) para publicarla en entornos GCC.

## <a name="develop"></a>Desarrollar

### <a name="create-the-app"></a>Crear la aplicación

La plataforma para desarrolladores de Microsoft Teams facilita a los desarrolladores la integración de sus propias aplicaciones y servicios para mejorar la productividad, tomar decisiones más rápidamente y crear colaboración en torno al contenido y los flujos de trabajo existentes. Las aplicaciones creadas en la plataforma Teams son puentes entre el cliente de Teams y sus servicios y flujos de trabajo, lo que las lleva directamente al contexto de su plataforma de colaboración. Para obtener más información, vaya a la [documentación para desarrolladores de Teams](/microsoftteams/platform).

### <a name="submit-the-app"></a>Enviar la aplicación

Cuando la aplicación esté lista para usarse en producción, el desarrollador puede enviar la aplicación mediante la API de envío de aplicaciones de Teams, a la que se puede llamar desde [Graph API](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), un entorno de desarrollo integrado (IDE) como Visual Studio Code o una plataforma como Power Apps y Power Virtual Agents. Esto hace que la aplicación esté disponible en la página [Administrar aplicaciones](/microsoftteams/manage-apps) del Centro de administración de Teams, donde puede revisarla y aprobarla.

La API de envío de aplicaciones de Teams, [creada en Microsoft Graph](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), permite a su organización desarrollarse en la plataforma de su elección y automatizar el proceso de envío a aprobación para aplicaciones personalizadas en Teams.

Este es un ejemplo del aspecto que tiene este paso de envío de aplicaciones en Visual Studio Code:

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="Captura de pantalla del envío de aplicaciones en Visual Studio Code.":::

Tenga en cuenta que esto aún no publica la aplicación en la tienda de aplicaciones de su organización. Este paso envía la aplicación al Centro de administración de Teams, donde puede aprobarla para su publicación en la tienda de aplicaciones de su organización.

Para obtener más información sobre el uso de la Graph API para enviar aplicaciones, consulta [aquí](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true).

## <a name="notify"></a>Notificar

Puedes activar las notificaciones para saber cuándo los desarrolladores envían una nueva solicitud para su revisión y aprobación. También recibirás notificaciones cuando los desarrolladores envíen actualizaciones de aplicaciones. Para habilitar las notificaciones de envío de aplicaciones en el Centro de administración de Teams, vaya a **Notificaciones & alertas** > **[Reglas](https://admin.teams.microsoft.com/notifications/rules)** >  de **envíos** de aplicaciones y active la regla cambiando el estado a **Activo**. Esta configuración está desactivada de forma predeterminada. Debe ser administrador global o administrador de Teams para activar esta configuración.

Después de activar esta configuración, recibirá notificaciones en el equipo **de alertas y notificaciones de Administración** en un nuevo canal denominado **Envíos de aplicaciones**. Como alternativa, puede elegir un equipo y un canal existentes para recibir notificaciones a un canal y equipo especificados. Para ello, siga estos pasos:

1. En la regla **de envíos de** aplicaciones, selecciona la casilla **Alerta de canal** en **Acciones**.
1. Elija el botón **Seleccionar canal** .
1. Busque un equipo para agregar.
1. Busque un canal para agregar.
1. Seleccione **Aplicar**.

   :::image type="content" source="media/channel-alert.png" alt-text="Casilla de notificación de alerta de canal personalizado." lightbox="media/channel-alert.png":::

> [!NOTE]
> Seleccione la casilla **Alerta de canal predeterminada** para recibir notificaciones al equipo **de Administración alertas y notificaciones** en el canal **Envíos de aplicaciones**.

:::image type="content" source="media/default-channel-alert.png" alt-text="Casilla de notificación de alerta de canal predeterminada." lightbox="media/default-channel-alert.png":::

También puede configurar notificaciones en un webhook externo especificando una dirección URL de webhook pública después de seleccionar la casilla **webhook** . Se enviará una carga de notificación JSON a la dirección URL del webhook.

:::image type="content" source="media/app-submission-notification.png" alt-text="Notificación de envío de aplicaciones." lightbox="media/app-submission-notification.png":::

Después de configurar la regla de envíos de aplicaciones, puede revisar las tarjetas de notificación en el canal especificado para ver los detalles de la aplicación y seleccionar **Ver detalles** para abrir aplicaciones en el Centro de administración de Teams.

## <a name="validate"></a>Validar

La página [Administrar aplicaciones](/microsoftteams/manage-apps) en el Centro de administración de Teams (en el panel de navegación izquierdo, ir a [**Aplicaciones** >  de Teams **Administrar aplicaciones**](https://admin.teams.microsoft.com/manage-apps)), le ofrece una vista de todas las aplicaciones de Teams para su organización. El widget **Aprobación pendiente** en la parte superior de la página le permite saber cuándo se envía una aplicación personalizada para su aprobación.

En la tabla, una aplicación recién enviada muestra automáticamente el **estado Publicación** de **Enviado** y **Estado** de **Bloqueado**. Puede ordenar la columna **Estado de publicación** en orden descendente para encontrar rápidamente la aplicación.

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="Estado de publicación." lightbox="media/custom-app-lifecycle-validate-app.png":::

Haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación. En la pestaña **Acerca de** , puede ver detalles sobre la aplicación, como la descripción, el estado, el enviador y el id. de la aplicación.

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="Página de detalles de la aplicación para una aplicación enviada." lightbox="media/custom-app-lifecycle-app-details.png":::

Para obtener más información sobre el uso de la Graph API para comprobar el **estado de publicación**, consulte [aquí](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true).

## <a name="publish"></a>Publicar

Cuando esté listo para que la aplicación esté disponible para los usuarios, publique la aplicación.

1. Inicie sesión en el Centro de administración de Teams y vaya a Aplicaciones  > **de Teams****[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Selecciona el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, en el cuadro **Estado de publicación** , selecciona **Publicar**.

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="Botón Publicar en la página de detalles de la aplicación.":::

Después de publicar la aplicación, el **estado publicación** cambia a **Publicado** y el **Estado** cambia a **Permitido**.

## <a name="set-up-and-manage"></a>Configurar y administrar

### <a name="control-access-to-the-app"></a>Controlar el acceso a la aplicación

De forma predeterminada, todos los usuarios de su organización pueden acceder a la aplicación en la tienda de aplicaciones de su organización. Para restringir y controlar quién tiene permiso para usar la aplicación, puede crear y asignar una directiva de permisos de aplicación. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anclar e instalar la aplicación para que los usuarios la descubran

De forma predeterminada, para que los usuarios encuentren la aplicación, tienen que ir a la tienda de aplicaciones de su organización y explorar o buscarla. Para que sea más fácil para los usuarios acceder a la aplicación, puede anclar la aplicación a la barra de aplicaciones de Teams. Para ello, cree una directiva de configuración de aplicaciones y asígnela a los usuarios. Para obtener más información, consulte [Administrar las directivas de configuración de aplicaciones en Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Buscar eventos de aplicaciones de Teams en el registro de auditoría

Puede buscar en el registro de auditoría para ver la actividad de aplicaciones de Teams en su organización. Para obtener más información sobre cómo buscar el registro de auditoría y ver una lista de las actividades de Teams que se registran en el registro de auditoría, vea [Buscar eventos en Teams en el registro de auditoría](audit-log-events.md).

Para que pueda buscar en el registro de auditoría, primero debe activar la característica de auditoría en el [Centro de seguridad y cumplimiento](https://sip.protection.office.com/). Para obtener más información, consulte [Activar o desactivar la búsqueda de registros de auditoría](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true). Tenga en cuenta que los datos de auditoría solo están disponibles desde el momento en que activó la característica de auditoría.

## <a name="discover-and-adopt"></a>Descubrir y adoptar

Los usuarios que tienen permisos para la aplicación pueden encontrarla en la tienda de aplicaciones de su organización. Vaya a **Creado para *Nombre de su organización*** en la página Aplicaciones para buscar las aplicaciones personalizadas de su organización.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Página de aplicaciones que muestra la aplicación publicada." lightbox="media/custom-app-lifecycle-discovery.png":::

Si ha creado y asignado una directiva de configuración de aplicaciones, la aplicación se ancla a la barra de aplicaciones de Teams para facilitar el acceso a los usuarios a los que se asignó la directiva.

## <a name="update"></a>Actualización

Para actualizar una aplicación, los desarrolladores deben seguir los pasos de la sección [Desarrollar](#develop) .

Cuando el desarrollador envíe una actualización a una aplicación personalizada publicada, recibirás una notificación en el widget **Aprobación pendiente** de la página [Administrar aplicaciones](/microsoftteams/manage-apps) . En la tabla, el **estado Publicación** de la aplicación se establecerá en **Actualización enviada**. También se te notificará en el equipo **de Administración alertas y notificaciones** en el canal **de envío** de aplicaciones si activaste las notificaciones de envío de aplicaciones. La tarjeta de notificación tendrá un vínculo que le llevará directamente a la aplicación en el Centro de administración de Teams. Para obtener más información sobre cómo activar las notificaciones de envío de aplicaciones, consulta [Notificar](#notify).

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="Página Administrar aplicaciones que muestra las solicitudes pendientes y el estado de la aplicación." lightbox="media/custom-app-lifecycle-update-submitted.png":::

Para revisar y publicar una actualización de la aplicación:

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
1. Haz clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, selecciona **Actualizar disponible** para revisar los detalles de la actualización.

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="Página de detalles de la aplicación." lightbox="media/custom-app-lifecycle-update-app.png":::

1. Cuando esté listo, seleccione **Publicar** para publicar la actualización. Al hacerlo, se reemplaza la aplicación existente, se actualiza el número de versión y se cambia el **estado de publicación** a **Publicado**. Se siguen aplicando todas las directivas de permisos y de configuración de aplicaciones para la aplicación actualizada.

    Si rechaza la actualización, la versión anterior de la aplicación permanece publicada.

Tenga en cuenta lo siguiente:

* Cuando se aprueba una aplicación, cualquiera de ellas puede enviar una actualización a la aplicación. Esto significa que otros desarrolladores, incluido el desarrollador que envió originalmente la aplicación, pueden enviar una actualización a la aplicación.
* Cuando un desarrollador envía una aplicación y la solicitud está pendiente, solo ese mismo desarrollador puede enviar una actualización a la aplicación. Otros desarrolladores pueden enviar una actualización solo después de la aprobación de la aplicación.

Para obtener más información sobre el uso de la Graph API para actualizar aplicaciones, consulta [aquí](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true).

## <a name="related-articles"></a>Artículos relacionados

* [Publicar una aplicación personalizada cargando un paquete de aplicación](upload-custom-apps.md)
* [Administrar aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
* [Administrar directivas y configuraciones de aplicaciones personalizadas](teams-custom-app-policies-and-settings.md)
* [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
* [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)
* [Supervisión y alertas de Teams](alerts/teams-admin-alerts.md)
* [Microsoft Graph API para aplicaciones de Teams](alerts/teams-admin-alerts.md)
