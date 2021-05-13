---
title: Usar la API Teams de envío de aplicaciones para enviar y aprobar las aplicaciones personalizadas
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
description: Obtenga información sobre cómo aprobar las aplicaciones personalizadas que se envían con Teams API de envío de aplicaciones en Microsoft Teams.
ms.openlocfilehash: e544fdc12e17fc8917a2d3b9ce01dfc5985261de
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337797"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Publicar una aplicación personalizada enviada a través de la API Teams de envío de aplicaciones

## <a name="overview"></a>Información general

> [!NOTE]
> Cuando publica una aplicación Teams personalizada, está disponible para los usuarios en la tienda de aplicaciones de su organización. Hay dos formas de publicar una aplicación personalizada y la forma en que se usa depende de cómo obtenga la aplicación. **Este artículo se centra en cómo** aprobar y publicar una aplicación personalizada que un desarrollador envía a través de la API Teams de envío de aplicaciones. El otro método, cargar una aplicación personalizada, se usa cuando un desarrollador le envía un paquete de aplicación .zip formato. Para obtener más información sobre ese método, vea <a href="/microsoftteams/upload-custom-apps" target="_blank">Publicar una aplicación personalizada cargando un paquete de aplicación.</a> El widget aprobar aplicación no está disponible en GCC inquilinos. 

> [!IMPORTANT]
> Este método no está disponible actualmente para GCC entornos. Debe usar el método *de carga de una aplicación* personalizada.

En este artículo se proporcionan instrucciones de un extremo a otro sobre cómo llevar la aplicación Teams desde el desarrollo hasta la implementación hasta la detección. Encontrará información general sobre las experiencias conectadas que Teams proporciona en todo el ciclo de vida de la aplicación para simplificar cómo desarrollar, implementar y administrar aplicaciones personalizadas en la tienda de aplicaciones de su organización.

Abarcaremos cada paso del ciclo de vida, incluida la manera en que los desarrolladores pueden usar la API de envío de aplicaciones de Teams para enviar aplicaciones personalizadas directamente al Centro de administración de Microsoft Teams para que pueda revisarlas y aprobarlas, cómo establecer directivas para administrar aplicaciones para los usuarios de su organización y cómo los usuarios las descubren en Teams.

![Información general sobre la aplicación desde el desarrollo hasta la implementación](media/custom-app-lifecycle.png)

Esta guía se centra en los Teams de la aplicación y está destinada a administradores y profesionales de TI. Para obtener información sobre cómo Teams aplicaciones, consulte la Teams <a href="/microsoftteams/platform" target="_blank">de desarrolladores.</a>

## <a name="develop"></a>Desarrollar

### <a name="create-the-app"></a>Crear la aplicación

La Microsoft Teams de desarrolladores facilita a los desarrolladores integrar sus propias aplicaciones y servicios para mejorar la productividad, tomar decisiones más rápidamente y crear colaboración en torno al contenido y flujos de trabajo existentes. Las aplicaciones integradas en la plataforma Teams son puentes entre el cliente Teams y sus servicios y flujos de trabajo, lo que las lleva directamente al contexto de su plataforma de colaboración. Para obtener más información, vaya a la <a href="/microsoftteams/platform" target="_blank">Teams de desarrolladores.</a>

### <a name="submit-the-app"></a>Enviar la aplicación

Cuando la aplicación esté lista para su uso en producción, el desarrollador puede enviar la aplicación mediante la API de envío de aplicaciones de Teams Graph, que se puede llamar desde una <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">API,</a>un entorno de desarrollo integrado (IDE) como Visual Studio Code o una plataforma como Power Apps y Power Virtual Agents. Al hacerlo, la aplicación <a href="/microsoftteams/manage-apps" target="_blank"></a> está disponible en la página Administrar aplicaciones del Centro de administración de Microsoft Teams, donde usted, el administrador, puede revisarla y aprobarla.esto

La API de envío de aplicaciones de Teams, integrada en <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph,</a>permite que su organización se desarrolle en la plataforma de su elección y automatiza el proceso de envío a aprobación para aplicaciones personalizadas en Teams.

Este es un ejemplo de la apariencia de este paso de envío de aplicaciones en Visual Studio Code:

![enviar una aplicación en Visual Studio Code](media/custom-app-lifecycle-submit-app.png)

Tenga en cuenta que esto todavía no publica la aplicación en la tienda de aplicaciones de su organización. Este paso envía la aplicación al centro de administración de Microsoft Teams donde puede aprobarla para su publicación en la tienda de aplicaciones de su organización.

Para obtener más información sobre cómo usar la API Graph enviar aplicaciones, vea <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">aquí</a>.

## <a name="validate"></a>Validar

La página Administrar <a href="/microsoftteams/manage-apps" target="_blank">aplicaciones</a> del centro de administración de Microsoft Teams (en el panel de navegación izquierdo, vaya a **Teams aplicaciones** Administrar aplicaciones), le ofrece una vista de todas las aplicaciones Teams de su  >  organización. El **widget De aprobación** pendiente en la parte superior de la página le permite saber cuándo se envía una aplicación personalizada para su aprobación.

En la tabla, una aplicación recién  enviada muestra automáticamente un estado de publicación de **Enviado** y **estado** de **Bloqueado.** Puede ordenar la **columna Estado de publicación** en orden descendente para buscar rápidamente la aplicación.

![estado de publicación ](media/custom-app-lifecycle-validate-app.png)

Haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación. En la **pestaña** Acerca de, puede ver detalles sobre la aplicación, como la descripción, el estado, el enviador y el id. de la aplicación.

![página de detalles de la aplicación para una aplicación enviada](media/custom-app-lifecycle-app-details.png)

Para obtener más información sobre cómo usar la API Graph para comprobar el estado **de publicación,** vea <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">aquí</a>.

## <a name="publish"></a>Publicar

Cuando esté listo para que la aplicación esté disponible para los usuarios, publique la aplicación.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. Haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, en el cuadro Estado **de publicación,** seleccione **Publicar**.

    Después de publicar la aplicación, el  estado De  **publicación** cambia a Publicado y el Estado cambia automáticamente a **Permitido.**

## <a name="set-up-and-manage"></a>Configurar y administrar

### <a name="control-access-to-the-app"></a>Controlar el acceso a la aplicación

De forma predeterminada, todos los usuarios de su organización pueden acceder a la aplicación en la tienda de aplicaciones de su organización. Para restringir y controlar quién tiene permiso para usar la aplicación, puede crear y asignar una directiva de permisos de aplicación. Para obtener más información, consulte <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Administrar configuración y directivas de aplicación personalizadas en Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anclar e instalar la aplicación para que los usuarios lo descubran

De forma predeterminada, para que los usuarios encuentren la aplicación que tienen que ir a la tienda de aplicaciones de su organización y examinarla o buscarla. Para que sea más fácil para los usuarios acceder a la aplicación, puede anclar la aplicación a la barra de aplicaciones en Teams. Para ello, cree una directiva de configuración de la aplicación y asígnela a los usuarios. Para obtener más información, consulte <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Administrar las directivas de configuración de aplicaciones en Teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Buscar en el registro de auditoría Teams eventos de la aplicación

Puede buscar en el registro de auditoría para ver Teams de aplicaciones de su organización. Para obtener más información sobre cómo buscar en el registro de auditoría y ver una lista de las actividades de Teams que se registran en el registro de auditoría, vea Buscar eventos en el registro de auditoría en <a href="/microsoftteams/audit-log-events" target="_blank">Teams</a>.

Para que pueda buscar en el registro de auditoría, primero debe activar la característica de auditoría en el <a href="https://protection.office.com" target="_blank">Centro de seguridad y cumplimiento</a>. Para obtener más información, consulte <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Activar o desactivar la búsqueda de registros de auditoría</a>. Tenga en cuenta que los datos de auditoría solo están disponibles desde el momento en que activó la característica de auditoría.

## <a name="discover-and-adopt"></a>Descubrir y adoptar

Los usuarios que tengan permisos para la aplicación pueden encontrarla en la tienda de aplicaciones de su organización. Vaya a **Nombre de la organización *integrado*** en la página Aplicaciones para buscar las aplicaciones personalizadas de su organización.

![Página aplicaciones que muestra la aplicación publicada ](media/custom-app-lifecycle-discovery.png)

Si creó y asignó una directiva de configuración de aplicaciones, la aplicación se ancla a la barra de aplicaciones en Teams para facilitar el acceso a los usuarios a los que se les asignó la directiva.

## <a name="update"></a>Actualización

Para actualizar una aplicación, los desarrolladores deben seguir los pasos de la [sección](#develop) Desarrollar.

Cuando el desarrollador envíe una actualización a una aplicación personalizada publicada, se le notificará en el **widget** De aprobación pendiente de la <a href="/microsoftteams/manage-apps" target="_blank">página</a> Administrar aplicaciones. En la tabla, **el estado de publicación** de la aplicación se establecerá en Actualizar **enviado.**

![Página Administrar aplicaciones que muestra las solicitudes pendientes y el estado de la aplicación ](media/custom-app-lifecycle-update-submitted.png)

Para revisar y publicar una actualización de la aplicación:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. Haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, **seleccione Actualizar disponible** para revisar los detalles de la actualización.

    ![página de detalles de la aplicación](media/custom-app-lifecycle-update-app.png)
3. Cuando esté listo, seleccione **Publicar** para publicar la actualización. Al hacerlo, se reemplaza la aplicación existente, se actualiza el número de versión y se cambia el **estado De publicación** a **Publicado.** Todas las directivas de permisos de la aplicación y las directivas de configuración de la aplicación siguen siendo obligatorias para la aplicación actualizada.

    Si rechaza la actualización, la versión anterior de la aplicación permanecerá publicada.

Tenga en cuenta lo siguiente:

- Cuando se aprueba una aplicación, cualquiera puede enviar una actualización a la aplicación. Esto significa que otros desarrolladores, incluido el desarrollador que envió originalmente la aplicación, pueden enviar una actualización a la aplicación.
- Cuando un desarrollador envía una aplicación y la solicitud está pendiente, solo ese mismo desarrollador puede enviar una actualización a la aplicación. Otros desarrolladores pueden enviar una actualización solo después de aprobar la aplicación.

Para obtener más información sobre el uso de la API Graph para actualizar aplicaciones, vea <a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">aquí</a>.

## <a name="related-topics"></a>Temas relacionados

- [Publicar una aplicación personalizada cargando un paquete de aplicación](upload-custom-apps.md)
- [Administrar las aplicaciones en el centro Microsoft Teams administración](manage-apps.md)
- [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
- [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)
- <a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">API Graph Microsoft para Teams aplicaciones</a>