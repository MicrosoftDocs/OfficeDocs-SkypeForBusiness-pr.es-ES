---
title: Información sobre las aplicaciones de Microsoft Teams
ms.reviewer: ''
description: Obtenga información sobre las aplicaciones, los bots y los conectores, y sobre cómo decidir qué implementar en Microsoft Teams según el perfil y los requisitos empresariales de su organización.
ms.topic: conceptual
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 10/01/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: 1ff0095ef804f7e58dcbc81c45639228b0264da4
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784205"
---
# <a name="understand-microsoft-teams-apps"></a>Comprender las aplicaciones de terceros en Microsoft Teams

Las aplicaciones de Teams ayudan a los usuarios a unir las herramientas y los servicios de su lugar de trabajo y a colaborar con otros usuarios. Algunos ejemplos son los usuarios finales que usan un calendario anclado en Teams para colaborar rápidamente con otros usuarios, una aplicación con la funcionalidad de bots que informa a los usuarios de la calidad de un servicio web en un canal de Teams, y una aplicación para compartir y asignar tareas a varios usuarios finales en un canal. Las aplicaciones de Microsoft Teams son aplicaciones SaaS basadas en web que no necesitan implementarse localmente.

Como administrador, puede establecer un proceso de gobierno de aplicaciones que equilibre requisitos amplios de los usuarios finales junto con las directivas de TI, los estándares y los perfiles de riesgo de su organización.

Nuestro extenso [catálogo](https://appsource.microsoft.com/marketplace/apps?product=office%3Bteams&page=1) de aplicaciones validadas y seguras de Teams proporciona a los usuarios finales acceso a las herramientas y servicios que su organización necesita a diario. El Centro de administración de Teams proporciona a los administradores controles y configuraciones de nivel empresarial para gobernar las aplicaciones. Puede controlar la disponibilidad de las aplicaciones para cada usuario en los distintos contextos, como reuniones, chats y canales.

Este artículo le ayudará a comprender los tipos de aplicaciones y desde dónde acceden los usuarios a esas aplicaciones. Para obtener más información sobre el uso de aplicaciones, lea [Información general sobre las aplicaciones para los usuarios finales](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

Los diferentes tipos de aplicaciones que los usuarios finales pueden usar en Teams son:

* [Aplicaciones principales que forman parte de Teams](#core-apps).
* Otras [aplicaciones creadas por Microsoft](#apps-created-by-microsoft).
* [Aplicaciones de terceros](#third-party-apps-created-by-independent-app-developers) creadas por partners (validadas por Microsoft).
* [Aplicaciones personalizadas](#custom-apps-created-within-an-organization-for-internal-use) creadas por tu propia organización.

## <a name="core-apps"></a>Aplicaciones principales

Algunas funcionalidades de Teams, como la fuente de actividades, los equipos, el chat, el calendario, las llamadas, los archivos y las tareas (inquilinos de educación) están disponibles y ancladas de forma predeterminada para facilitar el acceso a los usuarios finales. Para los trabajadores de primera línea, solo están disponibles y anclados la actividad, los turnos, el chat y las llamadas. Como administrador, puede modificar el comportamiento predeterminado mediante la [directiva de configuración](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Las aplicaciones principales son las aplicaciones ancladas en Teams de forma predeterminada." lightbox="media/core-apps-pinned2.png":::

## <a name="apps-created-by-microsoft"></a>Aplicaciones creadas por Microsoft

Microsoft proporciona muchas aplicaciones para mejorar la productividad y la colaboración. Usted y los usuarios finales pueden encontrar estas aplicaciones si buscan a Microsoft como Editor en el Centro de administración de Teams o como Proveedor en la tienda de Teams.

Teams incluye un conjunto de aplicaciones integradas, como Listas, Tareas, Elogiar, Aprobaciones y más. Recomendamos que se incluyan aplicaciones destacadas de Teams, como Planner, en la implementación inicial de Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Captura de pantalla que muestra una lista de aplicaciones de Microsoft en el Centro de administración de Teams." lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-created-by-independent-app-developers"></a>Aplicaciones de terceros creadas por desarrolladores de aplicaciones independientes

Además de las aplicaciones proporcionadas por Microsoft, puede usar aplicaciones de terceros. Microsoft valida rigurosamente la funcionalidad y la seguridad de todas estas aplicaciones. Elaborar pruebas manuales y automatizadas se ejecutan antes de hacer que estas aplicaciones estén disponibles en la tienda de Teams y muchas pruebas continúan con una cadencia regular incluso después de que las aplicaciones se publiquen en directo. Para comprender las ventajas de la validación de aplicaciones, consulte [validación de aplicaciones de terceros](overview-of-app-validation.md). Algunas de las aplicaciones se suscriben al [programa de cumplimiento de Microsoft](overview-of-app-certification.md) para pasar por varios niveles de comprobaciones adicionales más allá de la validación.

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Captura de pantalla de un ejemplo de aplicaciones de terceros en la tienda de Teams.":::

## <a name="custom-apps-created-within-an-organization-for-internal-use"></a>Aplicaciones personalizadas creadas dentro de una organización para uso interno

Las aplicaciones creadas por los desarrolladores de su organización se denominan aplicaciones personalizadas (o aplicaciones de línea de negocio). Su organización puede encargar la creación de aplicaciones personalizadas para los requisitos específicos de la organización. Tiene el control para permitir o bloquear dichas aplicaciones para toda la organización o para usuarios específicos. Los desarrolladores de su organización pueden crear rápidamente soluciones personalizadas de bajo código mediante la integración de Teams con [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Después de que un administrador permita el uso de aplicaciones personalizadas, los usuarios finales pueden encontrarlas seleccionando **Creado para su organización** en el panel de navegación izquierdo de la Tienda Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Captura de pantalla de aplicaciones personalizadas en la tienda de Teams en la aplicación de escritorio de Teams." lightbox="media/built-for-your-org2.png":::

Para obtener más información, consulta [Comprender y administrar aplicaciones personalizadas y de instalación de prueba](custom-app-overview.md).

## <a name="about-app-templates"></a>Información de plantillas de aplicación

Con los métodos de desarrollo de aplicaciones, Microsoft crea y proporciona aplicaciones de muestra funcionales y listas para producción. Colectivamente, estas aplicaciones se denominan plantillas de aplicaciones para Teams y se proporcionan a:

* Ilustra algunos casos de uso de colaboración en Teams.
* Muestra los procedimientos recomendados y métodos de desarrollo de aplicaciones.
* Proporciona aplicaciones de código abierto que los desarrolladores pueden ampliar para crear sus propias aplicaciones.

Los desarrolladores de la organización personalizan las plantillas de aplicación con cambios sencillos en el código fuente proporcionado. Usted proporciona estas aplicaciones como aplicaciones personalizadas para los usuarios finales, para satisfacer las necesidades de la organización.

Para obtener más información, consulte [Plantillas de aplicación de Microsoft Teams](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="understand-app-capabilities"></a>Comprender las funcionalidades de la aplicación

Para proporcionar experiencias enriquecidas que permitan a los usuarios finales trabajar dentro de Teams, los desarrolladores de aplicaciones aprovechan las siguientes funcionalidades de la aplicación. Las extensiones de mensajería permiten a los usuarios interactuar con el cliente de Teams del servicio web. Buscan o inician acciones en un sistema externo. Puede enviar el resultado de la interacción al cliente de Teams como una tarjeta con formato enriquecido. Las aplicaciones de extensibilidad de reuniones integran las aplicaciones de un desarrollador dentro de las reuniones y ofrecen una experiencia dentro de las reuniones con capacidad de respuesta.

Un bot también se conoce como bot de chat o bot de conversación. Es una aplicación que ejecuta tareas repetitivas y simples. Una interacción de bot puede ser una pregunta y una respuesta rápidas, o puede ser una conversación compleja que proporcione acceso a servicios o ayuda. Los usuarios pueden chatear con un bot uno a uno o en un canal. Por ejemplo, puede usar la aplicación Polly para crear encuestas rápidas, obtener comentarios y realizar una comprobación de pulsos.

Las pestañas son páginas web compatibles con Teams ancladas en la parte superior de un canal o un chat. Las pestañas le permiten interactuar con contenido y servicios con una experiencia similar a la web. Puede agregar pestañas como parte de un canal dentro de un equipo, chat de grupo o aplicación personal para un usuario individual.

Los webhooks y conectores proporcionan contenido y actualizaciones de servicios que los usuarios finales usan con frecuencia (como Jira Cloud y Bitbucket) directamente en una conversación de canal. Las aplicaciones que usan esta funcionalidad pueden comunicarse con aplicaciones externas y pueden enviar o recibir notificaciones y mensajes de un servicio externo.

Las extensiones de mensajería son accesos directos para insertar contenido de la aplicación o para actuar en un mensaje sin que los usuarios finales tengan que salir de la conversación. Las extensiones de mensajería pueden tener comandos de búsqueda para que los usuarios finales encuentren rápidamente contenido externo y lo inserten en un mensaje o comandos de acción.

Para ver casos de uso comunes asignados a las capacidades de Teams, consulte [Asignar los casos de uso a las capacidades de la aplicación Teams](/microsoftteams/platform/concepts/design/map-use-cases).

<!--- TBD: Admins do many considerations and decisions around app adoption and app governance. These are to be covered in a separate article. Commenting the below content for now as part of this article revamp.

## Apps deployment decisions

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

## Core deployment decisions

These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).

### App availability settings

Teams provides many apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.
Get apps from the Teams Store. By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users. For example, users can use the Planner app to build and manage team tasks in Teams.

By default, all Microsoft-provided, third-party, and custom apps are available, and you can turn individual apps on or off. There are org-wide settings that let you turn all third-party and/or custom apps on or off for your entire organization.

| Ask yourself | Action |
|--------------|--------|
|Will you change the default Teams apps settings? | For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### App permissions and other considerations

Apps are consented to by users and managed by the admin or IT pro through policies. However, app permissions and risk profile are defined in the app itself.

| Ask yourself | Action |
|--------------|--------|
|<br>Which apps do I want to allow access to? Which ones do I not want to allow access to?  | <ul><li>See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</li><li>See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</li></ul>|

--->

<!--- TBD: Rewrite this to talk about bots and tabs as a capability of apps. Admins do not govern bots, tabs, etc. Admins only govern apps that contain capabilities such as connectors, bots, etc. This writeup gives an impression that admins manage apps + bots + tabs + connectors, etc.

### Bots for private chats and channels

Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat. Teams supports bots in private chats and channels. Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom bots in my organization?|For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### Built-in and custom tabs

Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services. Add tabs to help users access and manage the data they need or use the most. In channels, the Conversations and Files tabs are created by default. In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default. In addition to these built-in tabs, you can design and add custom tabs. To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](/microsoftteams/platform/tabs/what-are-tabs).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

<!--- TBD: Activity reports is not part of app overview. Commenting for now. To be reused in a different article later.

### Activity reports

You can use activity reports to see how users in your organization are using Teams. For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative. Your organization can use the activity reports to decide where to prioritize training and communication efforts. To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.

| Ask yourself | Action |
|--------------|--------|
| Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->

## <a name="related-article"></a>Artículo relacionado

* [Obtenga más información sobre las plantillas de aplicaciones para Teams](/microsoftteams/platform/samples/app-templates).
