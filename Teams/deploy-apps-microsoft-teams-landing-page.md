---
title: Información sobre las aplicaciones de Microsoft Teams
ms.reviewer: ''
description: Obtenga información sobre las aplicaciones, los bots y los conectores, y sobre cómo decidir qué implementar en Microsoft Teams según el perfil y los requisitos empresariales de su organización.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 02/10/2021
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
ms.openlocfilehash: b6fd5ef344550cf85420faef1748c34f6e87e88b
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556531"
---
# <a name="about-apps-in-microsoft-teams"></a>Acerca de las aplicaciones de Microsoft Teams

Las aplicaciones le permiten buscar contenido de sus servicios favoritos y compartirlo en Teams. Permiten realizar tareas como anclar servicios en la parte superior de un canal, automatizar las notificaciones mediante bots o compartir y asignar tareas. Para obtener más información sobre el uso de aplicaciones, lea [Información general sobre las aplicaciones para los usuarios finales](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

Los diferentes tipos de aplicaciones que los usuarios finales pueden usar en Teams son aplicaciones creadas por Microsoft, aplicaciones de terceros certificadas y aplicaciones personalizadas creadas por su propia organización.

## <a name="use-microsoft-provided-apps"></a>Usar aplicaciones proporcionadas por Microsoft

Teams incluye un conjunto de aplicaciones integradas, como Listas, Tareas, Elogiar, Aprobaciones y más. Le recomendamos que incluya aplicaciones destacadas de Teams, como Planner, en la implementación inicial de Teams. Agregue otras aplicaciones a medida que impulsa la adopción de Teams. Algunas funciones predeterminadas, como la transmisión de actividades, el chat, el calendario y las llamadas están disponibles de forma predeterminada y también están ancladas para facilitar el acceso a los usuarios finales.

## <a name="use-third-party-apps"></a>Aplicaciones de terceros

Además de las aplicaciones proporcionadas por Microsoft, puede usar aplicaciones de terceros validadas por Microsoft. Microsoft trabaja con partners desarrolladores de Microsoft 365 a fin de proporcionar la información necesaria para acelerar la toma de decisiones acerca del uso de aplicaciones de Microsoft Teams. Para más información, consulte [Seguridad y cumplimiento de aplicaciones de Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps).

## <a name="use-open-source-sample-apps-provided-by-microsoft"></a>Usar aplicaciones de ejemplo de código abierto proporcionadas por Microsoft

También puede usar [plantillas de Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json), aplicaciones listas para producción en Microsoft Teams que están impulsadas por la comunidad, son de código abierto y están disponibles en GitHub.

## <a name="create-custom-apps"></a>Crear aplicaciones personalizadas

Puede crear rápidamente soluciones personalizadas de poco código si usa la integración de Teams con [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions). También puede crear su propia aplicación personalizada para adaptarla a sus necesidades empresariales. Para más información, consulte [Crear aplicaciones para Microsoft Teams](/microsoftteams/platform/overview).  

## <a name="apps-deployment-decisions"></a>Decisiones de implementación de aplicaciones

Teams proporciona una experiencia de colaboración excelente para su organización y la configuración predeterminada parece funcionar para la mayoría de organizaciones. Este artículo le ayudará a decidir si cambiar alguna opción de la configuración predeterminada, en función del perfil y los requisitos empresariales de su organización, después, le guiará con cada cambio. Hemos dividido las opciones en dos grupos, comenzando por el conjunto principal de [cambios que es más probable que realice](#core-deployment-decisions). El segundo grupo incluye la [configuración adicional](#additional-deployment-decisions) que puede que quiera configurar según las necesidades de su organización.

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las opciones de aplicaciones que la mayoría de organizaciones cambian (si la configuración predeterminada de Teams no funciona).

### <a name="app-availability-settings"></a>Configuración de disponibilidad de aplicaciones

Teams ofrece una serie de aplicaciones proporcionadas por Microsoft y aplicaciones de terceros para interactuar con los usuarios, ayudar en la productividad e integrar los servicios empresariales usados frecuentemente en Teams.
Obtener aplicaciones desde la Tienda Teams. De forma predeterminada, todas las aplicaciones, incluidas las aplicaciones personalizadas que ha enviado a través del [proceso de aprobación de Teams Store](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), están activadas para todos los usuarios. Por ejemplo, los usuarios pueden usar la aplicación de Planner para crear y administrar tareas de equipo en Teams.

De forma predeterminada, todas las aplicaciones proporcionadas por Microsoft, así como las personalizadas y las de terceros, están disponibles y puede activarlas o desactivarlas individualmente. Hay configuraciones de toda la organización que le permiten activar o desactivar todas las aplicaciones personalizadas o de terceros para toda la organización.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Va a cambiar la configuración predeterminada de las aplicaciones de Teams? | Para obtener más información sobre las directivas y configuraciones que puede usar para administrar las aplicaciones de su organización, consulte [Configuración de administración de aplicaciones en Microsoft Teams](admin-settings.md).|

### <a name="app-permissions-and-other-considerations"></a>Permisos de aplicación y otras consideraciones

Los usuarios tienen que dar su consentimiento a las aplicaciones y el administrador o profesional de TI las administra mediante directivas. Sin embargo, los permisos y el perfil de riesgo de la aplicación se definen en la misma aplicación.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|<br>¿A qué aplicaciones deseo permitir el acceso? ¿A cuáles no quiero permitir el acceso?  | <ul><li>Vea [Consideraciones y permisos de las aplicaciones de Microsoft Teams](app-permissions.md) para ver una serie de aspectos que debe considerar al permitir el acceso a una aplicación, bot, pestaña o conector.</li><li>Para obtener más información sobre cómo hacer que una aplicación esté disponible para los usuarios de su organización, consulte [administrar sus aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md).</li></ul>|

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
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

## <a name="additional-deployment-decisions"></a>Decisiones de implementación adicionales

Puede cambiar esta configuración en función de las necesidades y la configuración de su organización.

### <a name="activity-reports"></a>Informes de actividad

Puede usar los informes de actividad para ver cómo los usuarios de su organización usan Teams. Por ejemplo, si algunos aún no utilizan Teams, puede que no sepan cómo empezar o no entiendan cómo pueden usar Teams para ser más productivos y mejorar la colaboración. Su organización puede usar los informes de actividad para decidir dónde debe dar prioridad a los esfuerzos de aprendizaje y comunicación. Para ver los informes de actividad, debe ser un administrador global de Microsoft 365 u Office 365, administrador de servicios de Teams o administrador de Skype Empresarial.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| <br>¿Quién necesita ver los informes de actividad? ¿Tienen los permisos adecuados para poder verlos? |<ul><li>Si no quiere asignar un rol de administrador a un usuario, puede [asignar el rol de Lector de informes](teams-activity-reports.md#reports-reader-role).</li><li>Vea [Roles y permisos](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) y [Ver y asignar roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para obtener información sobre cómo asignar roles de administrador en Azure Active Directory.</li></ul> |

### <a name="app-templates"></a>Plantillas de aplicaciones

Las plantillas de aplicaciones son aplicaciones listas para producción en Microsoft que están controladas por la comunidad, son de código abierto y están disponibles en GitHub. Cada aplicación contiene instrucciones detalladas de implementación e instalación para su organización. Es una aplicación lista para usarse: puede instalar y empezar a usarse inmediatamente.

El código fuente completo también está disponible, para que pueda explorarlo en detalle, o bien puede bifurcar el código y modificarlo para satisfacer sus necesidades específicas.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| ¿Quiero instalar alguna plantilla de aplicación de Teams, como IceBreaker? |Para obtener más información, vea [Plantillas de aplicación para Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json).|
