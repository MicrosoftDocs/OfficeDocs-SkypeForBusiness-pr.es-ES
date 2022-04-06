---
title: Información sobre las aplicaciones de Microsoft Teams
ms.reviewer: ''
description: Obtenga información sobre las aplicaciones, los bots y los conectores, y sobre cómo decidir qué implementar en Microsoft Teams según el perfil y los requisitos empresariales de su organización.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8579d7c2c49749058c174aa71430803dce63286
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2022
ms.locfileid: "64643024"
---
# <a name="about-apps-in-microsoft-teams"></a>Acerca de las aplicaciones de Microsoft Teams

Las aplicaciones son una forma excelente de reunir las herramientas y servicios de su lugar de trabajo y colaborar con otras personas. Las aplicaciones ayudan a los usuarios finales a ser más productivos, colaborativos y eficaces en sus tareas diarias. Las organizaciones usan aplicaciones para conectarse con sus clientes, proporcionar servicios y compartir información. Las aplicaciones permiten a los usuarios ser más eficaces Teams chats, reuniones y canales. Algunos ejemplos son los usuarios finales que usan un calendario anclado en Teams para colaborar rápidamente con otros usuarios, una aplicación con funcionalidad de bots que informa a los usuarios de QoS de un servicio web en un canal de Teams y una aplicación para compartir y asignar tareas a varios usuarios finales en un canal.

Nuestra amplia selección de aplicaciones validadas y seguras en la tienda proporciona a los usuarios finales acceso a las herramientas y servicios que su organización necesita cada día. Microsoft Teams son aplicaciones SaaS basadas en web que no es necesario implementar. Los usuarios finales pueden usar aplicaciones en Teams solo en función de los permisos proporcionados por usted. Como administrador, solo tiene que aprobar o bloquear el uso de cualquier aplicación para los usuarios de su organización. Controla la disponibilidad de aplicaciones para todos los usuarios en reuniones, chats y canales.

Para proporcionar a los usuarios finales las aplicaciones que necesitan, siga leyendo para comprender los tipos de aplicaciones y dónde los usuarios tienen acceso a esas aplicaciones. Para obtener más información sobre el uso de aplicaciones, lea [Información general sobre las aplicaciones para los usuarios finales](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

Los diferentes tipos de aplicaciones que los usuarios finales pueden usar en Teams son:

* [Aplicaciones principales que forman parte de Teams](#core-apps).
* [Otras aplicaciones creadas por Microsoft](#microsoft-provided-apps).
* [Aplicaciones de terceros de](#third-party-apps-validated-by-microsoft) partners (validadas por Microsoft).
* [Aplicaciones personalizadas](#custom-apps) creadas por su propia organización.

## <a name="core-apps"></a>Aplicaciones principales

Algunas funciones predeterminadas, como fuente de actividades, Teams canales, chat, calendario y llamadas están disponibles y ancladas de forma predeterminada para facilitar el acceso a los usuarios finales. Como administrador, puede modificar el comportamiento predeterminado mediante la [directiva de configuración](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Las aplicaciones principales son las aplicaciones ancladas en Teams de forma predeterminada." lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Aplicaciones proporcionadas por Microsoft

Microsoft proporciona muchas aplicaciones para mejorar la productividad y la colaboración. Usted y los usuarios finales pueden encontrar estas aplicaciones buscando Microsoft que aparece como el Publisher en el centro de administración o aparece como Proveedor en la tienda de grupo.

Teams incluye un conjunto de aplicaciones integradas, como Listas, Tareas, Elogiar, Aprobaciones y más. Le recomendamos que incluya aplicaciones destacadas de Teams, como Planner, en la implementación inicial de Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Aplicaciones de Microsoft en Teams de administración" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Aplicaciones de terceros validadas por Microsoft

Además de las aplicaciones proporcionadas por Microsoft, puede usar aplicaciones de terceros validadas por Microsoft. Microsoft valida la funcionalidad y la seguridad de estas aplicaciones antes de hacer que estas aplicaciones estén disponibles en Teams store.

<!--- TBD: Link to the new article later when it is created.
To understand the benefits of app validation, see [validation of third-party apps]().

--->

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Un ejemplo de aplicaciones de terceros en Teams tienda":::

<!--- TBD: Check the relevance of this link here.
For more information, see [Microsoft Teams App Security and Compliance](/microsoft-365-app-certification/teams/teams-apps).
--->

## <a name="custom-apps"></a>Aplicaciones personalizadas

Las aplicaciones creadas por desarrolladores de su organización se denominan aplicaciones personalizadas. El desarrollo de una aplicación de este tipo se encarga para requisitos específicos de su organización y tiene controles para permitir o no dichas aplicaciones. Los desarrolladores de su organización pueden crear rápidamente soluciones personalizadas de código bajo mediante Teams integración con [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Después de que un administrador permita el uso de aplicaciones personalizadas, los usuarios finales encontrarán dichas aplicaciones haciendo clic en Integrado para su organización en la navegación izquierda de Teams tienda.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Aplicaciones personalizadas en Teams en Teams de escritorio" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>Comprender la carga lateral de aplicaciones personalizadas

Al desarrollar aplicaciones personalizadas y antes de distribuir las aplicaciones a los usuarios finales, los desarrolladores prueban las aplicaciones agregándoles a la tienda para realizar pruebas por su cuenta o probar con un equipo en el que cargan la aplicación. Este método se denomina sideloading de aplicaciones y solo se aplica a aplicaciones personalizadas.

Los desarrolladores pueden descargar de forma lateral una aplicación para que esté disponible para los miembros de un equipo específico, normalmente para probar una aplicación en desarrollo. Esto no requiere la aprobación del administrador si se permite la carga lateral. Como administrador, puede no permitir la instalación lateral para cualquier desarrollador.

Si no permite la instalación lateral, los desarrolladores podrán probar sus aplicaciones en un espacio [empresarial de prueba](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Una vez completado el desarrollo de aplicaciones personalizadas, los desarrolladores solicitan a los administradores que distribuyan su aplicación personalizada a los usuarios finales. Para obtener más información, [vea cómo publicar una aplicación personalizada](/microsoftteams/upload-custom-apps). Como administrador, puede permitir o no permitir el uso de una aplicación personalizada para usuarios específicos.

### <a name="about-app-templates"></a>Acerca de las plantillas de aplicaciones

Las plantillas de aplicaciones para Teams son aplicaciones de ejemplo funcionales y listas para la producción creadas por Microsoft para ilustrar casos de uso populares, mostrar los procedimientos recomendados de desarrollo de aplicaciones y proporcionar aplicaciones de código abierto que los desarrolladores pueden ampliar para crear aplicaciones personalizadas. Los desarrolladores de la organización personalizan las plantillas de aplicación para las necesidades de su organización con cambios sencillos en el código disponible en GitHub. Como administrador, proporciona estas aplicaciones como aplicaciones personalizadas para los usuarios finales.

Para obtener más información, [vea Microsoft Teams de aplicaciones](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="understand-app-capabilities"></a>Comprender las capacidades de la aplicación

Las aplicaciones de mensajería incluyen contenido de una aplicación en un canal o chat. Las aplicaciones de extensibilidad de reuniones integran las aplicaciones de un desarrollador dentro de las reuniones y ofrecen una experiencia de reunión con capacidad de respuesta. Para proporcionar varias funciones, los desarrolladores de aplicaciones aprovechan las siguientes funcionalidades de la aplicación.

Los bots proporcionan respuestas, actualizaciones y asistencia. Puede chatear con esos usuarios uno a uno o dentro de un canal. Pueden ayudarle con la administración de tareas, la programación y mucho más. Por ejemplo, puede usar la aplicación Polly para crear encuestas rápidas, recibir comentarios y realizar una comprobación de pulsos.

Las pestañas ancladas en la parte superior de un canal le permiten interactuar con contenido y servicios con una experiencia de tipo web.
Los conectores proporcionan contenido y actualizaciones de los servicios que usa con frecuencia (como Jira Cloud y Bitbucket) directamente en una conversación de canal.

Las extensiones de mensajería son métodos abreviados de teclado para insertar contenido de la aplicación o para actuar en un mensaje sin que los usuarios finales tengan que salir de la conversación. Las extensiones de mensajería pueden tener comandos de búsqueda para que los usuarios finales puedan encontrar rápidamente contenido externo e insertarlo en un mensaje o comandos de acción.

Para ver casos de uso comunes asignados a Teams, vea Asignar los casos de uso a Teams [de la aplicación](/microsoftteams/platform/concepts/design/map-use-cases).

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
| <br>Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
