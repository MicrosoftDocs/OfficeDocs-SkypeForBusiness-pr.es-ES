---
title: Conectores, bots y aplicaciones en Microsoft Teams
ms.reviewer: ''
description: Obtenga información sobre las aplicaciones, los bots y los conectores, y sobre cómo decidir qué implementar en Microsoft Teams en función del perfil y los requisitos empresariales de su organización.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 02/10/2021
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3022b1d1fbeff9713741955a0b40fd553028de0e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094396"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a>Conectores, bots y aplicaciones en Microsoft Teams

Las aplicaciones le permiten buscar contenido de sus servicios favoritos y compartirlo en Teams. Le ayudan a hacer cosas como anclar servicios al principio de un canal, chatear con bots o compartir y asignar tareas. Para aprender más cosas a este respecto, lea [Información general de aplicaciones en Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0). 

Puede agregar aplicaciones a la implementación de Teams con las aplicaciones proporcionadas con Microsoft Teams, con aplicaciones y plantillas certificadas de terceros y creando sus propias aplicaciones personalizadas.

## <a name="use-microsoft-provided-apps"></a>Usar aplicaciones proporcionadas por Microsoft

Teams incluye un conjunto de aplicaciones integradas, como Listas, Tareas, Elogiar, Aprobaciones y más. Le recomendamos que incluya aplicaciones destacadas de Teams, como Planner, en la implementación inicial de Teams. Agregue otras aplicaciones, bots y conectores a medida que impulsa la adopción de Teams.

## <a name="use-third-party-apps"></a>Aplicaciones de terceros

Además de las aplicaciones proporcionadas por Microsoft, puede usar aplicaciones de terceros certificadas por Microsoft. Microsoft trabaja con partners desarrolladores de Microsoft 365 a fin de proporcionar la información necesaria para acelerar la toma de decisiones acerca del uso de aplicaciones y complementos de Microsoft Teams. Para más información, consulte [Seguridad y cumplimiento de aplicaciones de Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps).

## <a name="use-teams-templates"></a>Usar plantillas de Teams

También puede usar [plantillas de Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json), aplicaciones listas para producción en Microsoft Teams que están impulsadas por la comunidad, son de código abierto y están disponibles en GitHub.

## <a name="create-custom-apps"></a>Crear aplicaciones personalizadas

Puede crear rápidamente soluciones personalizadas de poco código si usa la integración de Teams con [Microsoft Power Platform](teams-power-platfom-integration.md). También puede crear su propia aplicación personalizada para adaptarla a sus necesidades empresariales. Para más información, consulte [Crear aplicaciones para Microsoft Teams](/microsoftteams/platform/overview).  


## <a name="apps-deployment-decisions"></a>Decisiones de implementación de aplicaciones

Teams proporciona una experiencia de colaboración excelente para su organización y la configuración predeterminada parece funcionar para la mayoría de organizaciones. Este artículo le ayudará a decidir si cambiar alguna opción de la configuración predeterminada, en función del perfil y los requisitos empresariales de su organización, después, le guiará con cada cambio. Hemos dividido las opciones en dos grupos, comenzando por el conjunto principal de [cambios que es más probable que realice](#core-deployment-decisions). El segundo grupo incluye la [configuración adicional](#additional-deployment-decisions) que puede que quiera configurar según las necesidades de su organización.

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las opciones de aplicaciones que la mayoría de organizaciones cambian (si la configuración predeterminada de Teams no funciona).

### <a name="app-availability-settings"></a>Configuración de disponibilidad de aplicaciones 

Teams ofrece una serie de aplicaciones proporcionadas por Microsoft y aplicaciones de terceros para interactuar con los usuarios, ayudar en la productividad e integrar los servicios empresariales usados frecuentemente en Teams. Obtener aplicaciones desde la Tienda Teams. De forma predeterminada, todas las aplicaciones, incluidas las aplicaciones personalizadas que ha enviado a través del [proceso de aprobación de Teams Store](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), están activadas para todos los usuarios. Por ejemplo, los usuarios pueden usar la aplicación de Planner para crear y administrar tareas de equipo en Teams.

De forma predeterminada, todas las aplicaciones proporcionadas por Microsoft, así como las personalizadas y las de terceros, están disponibles y puede activarlas o desactivarlas individualmente. Hay configuraciones de toda la organización que le permiten activar o desactivar todas las aplicaciones personalizadas o de terceros para toda la organización.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Va a cambiar la configuración predeterminada de las aplicaciones de Teams? | Para obtener más información sobre las directivas y configuraciones que puede usar para administrar las aplicaciones de su organización, consulte [Configuración de administración de aplicaciones en Microsoft Teams](admin-settings.md).|
|||

### <a name="app-permissions-and-other-considerations"></a>Permisos de aplicación y otras consideraciones

Los usuarios tienen que dar su consentimiento a las aplicaciones y el administrador o profesional de TI las administra mediante directivas. Sin embargo, en la mayoría de los casos, los permisos y el perfil de riesgo de la aplicación se definen en la misma. 

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|<br>¿A qué aplicaciones deseo permitir el acceso? ¿A cuáles no quiero permitir el acceso?  | <ul><li>Vea [Consideraciones y permisos de las aplicaciones de Microsoft Teams](app-permissions.md) para ver una serie de aspectos que debe considerar al permitir el acceso a una aplicación, bot, pestaña o conector.</li><li>Para obtener más información sobre cómo hacer que una aplicación esté disponible para los usuarios de su organización, consulte [administrar sus aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md).</li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a>Bots para conversaciones privadas y canales

Los bots son programas automatizados que responden a las consultas o dan actualizaciones y notificaciones sobre detalles que puedan resultar interesantes para los usuarios o sobre los que quieran mantenerse informados. Los bots permiten a los usuarios interactuar con los servicios de nube, como la administración de tareas, la programación y los sondeos, en un chat de Teams. Teams admite bots en los canales y conversaciones privadas. Los administradores pueden controlar si se permite el uso de bots en una organización con Microsoft 365 u Office 365.

| Pregúntese lo siguiente: | Action |
|--------------|--------|
|¿Me interesa permitir bots personalizados en mi organización?|Para obtener más información sobre cómo agregar bots, vea [Agregar bots para chats privados y canales en Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). Para obtener información sobre cómo activar o desactivar los bots personalizados, consulte [Configuración de administrador de aplicaciones en Microsoft Teams](admin-settings.md).|
|||

### <a name="built-in-and-custom-tabs"></a>Pestañas personalizadas e integradas

Los propietarios y los miembros del equipo pueden agregar pestañas adicionales a cada canal para integrar mejor sus servicios en la nube. Agregue pestañas para ayudar a los usuarios a acceder y administrar los datos que más necesitan o usan. En los canales, las pestañas de Conversaciones y Archivos se crean de forma predeterminada. En cada chat privado, las pestañas de Conversaciones, Archivos, Organización y Actividad se crean de forma predeterminada. Además de estas pestañas integradas, puede diseñar y agregar pestañas personalizadas. Para obtener información sobre cómo activar o desactivar las aplicaciones de Teams en su organización, lea [Configuración de administrador de aplicaciones en Teams](admin-settings.md).

| Pregúntese lo siguiente: | Action |
|--------------|--------|
|¿Me interesa permitir pestañas personalizadas en mi organización?|Para obtener más información, vea [Usar fichas integradas y personalizadas en Teams](built-in-custom-tabs.md).|
|||

### <a name="custom-connectors"></a>Conectores personalizados

Los conectores mantienen su equipo al día haciendo llegar contenido y actualizaciones de servicios que se usan con frecuencia directamente en un canal. Con los conectores, los usuarios de Teams pueden recibir actualizaciones de servicios populares como Twitter, Trello, Wunderlist, GitHub y Azure DevOps Services en sus chats de Teams.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Me interesa permitir que los usuarios creen conectores personalizados?|Para obtener más información, vea [Usar conectores personalizados en Teams](office-365-custom-connectors.md).|
|||

## <a name="additional-deployment-decisions"></a>Decisiones de implementación adicionales

Puede que le interese cambiar esta configuración en función de las necesidades y la configuración de su organización.

### <a name="activity-reports"></a>Informes de actividad

Puede usar los informes de actividad para ver cómo los usuarios de su organización usan Teams. Por ejemplo, si algunos aún no utilizan Teams, puede que no sepan cómo empezar o no entiendan cómo pueden usar Teams para ser más productivos y mejorar la colaboración. Su organización puede usar los informes de actividad para decidir dónde debe dar prioridad a los esfuerzos de aprendizaje y comunicación. Para ver los informes de actividad, debe ser un administrador global de Microsoft 365 u Office 365, administrador de servicios de Teams o administrador de Skype Empresarial.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| <br>¿Quién necesita ver los informes de actividad? ¿Tienen los permisos adecuados para poder verlos? |<ul><li>Si no quiere asignar un rol de administrador a un usuario, puede [asignar el rol de Lector de informes](teams-activity-reports.md#reports-reader-role).</li><li>Vea [Roles y permisos](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) y [Ver y asignar roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para obtener información sobre cómo asignar roles de administrador en Azure Active Directory.</li></ul> |
|||

### <a name="app-templates"></a>Plantillas de aplicaciones

Las plantillas de aplicaciones son aplicaciones listas para producción en Microsoft Teams que están controladas por la comunidad, son de código abierto y están disponibles en GitHub. Cada una contiene instrucciones detalladas sobre cómo implementar e instalar la aplicación para su organización, lo que proporciona una aplicación lista para usar que puede instalar y empezar a usar inmediatamente. El código fuente completo también está disponible, para que pueda explorarlo en detalle, o bien puede bifurcar el código y modificarlo para satisfacer sus necesidades específicas.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| ¿Quiero instalar alguna plantilla de aplicación de Teams, como IceBreaker? |Para obtener más información, vea [Plantillas de aplicación para Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json).|
|||