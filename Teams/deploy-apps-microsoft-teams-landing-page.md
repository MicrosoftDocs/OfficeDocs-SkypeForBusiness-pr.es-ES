---
title: Conectores, bots y aplicaciones en Microsoft Teams
ms.reviewer: ''
description: Use estos recursos de implementación para ayudarle a implementar las aplicaciones en Microsoft.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 535c34bd19a2f019d1b9dc07718cf20d5da2f98e
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826958"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a>Conectores, bots y aplicaciones en Microsoft Teams

Las aplicaciones le permiten buscar contenido de sus servicios favoritos y compartirlo directamente en Teams. Le ayudan a hacer cosas como anclar servicios al principio de un canal, chatear con bots o compartir y asignar tareas. Para aprender más cosas a este respecto, lea [Información general de aplicaciones en Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

Le recomendamos que incluya nuestras aplicaciones destacadas, como Planner, en la implementación inicial de Teams. Agregue otras aplicaciones, bots y conectores a medida que impulsa la adopción de Teams.

También tienes la opción de crear tus propias aplicaciones personalizadas. Consulte nuestra[ documentación para desarrolladores ](/microsoftteams/platform/overview)para obtener más información.

## <a name="apps-deployment-decisions"></a>Decisiones de implementación de aplicaciones

Teams proporciona una experiencia de colaboración excelente para su organización y la configuración predeterminada parece funcionar para la mayoría de organizaciones. Este artículo le ayudará a decidir si cambiar alguna opción de la configuración predeterminada, en función del perfil y los requisitos empresariales de su organización, después, le guiará con cada cambio. Hemos dividido las opciones en dos grupos, comenzando por el conjunto principal de [cambios que es más probable que realice](#core-deployment-decisions). El segundo grupo incluye las [opciones adicionales](#additional-deployment-decisions) que puede que quiera configurar, según las necesidades de su organización.

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las opciones de aplicaciones que la mayoría de organizaciones cambian (si la configuración predeterminada de Teams no funciona).

### <a name="app-availability-settings"></a>Configuración de disponibilidad de aplicaciones 

Teams ofrece una serie de aplicaciones proporcionadas por Microsoft y aplicaciones de terceros para interactuar con los usuarios, ayudar en la productividad e integrar los servicios empresariales usados frecuentemente en Teams. Obtener aplicaciones desde la Tienda Teams. De forma predeterminada, todas las aplicaciones, incluidas las aplicaciones personalizadas que ha enviado a través del [proceso de aprobación de Teams Store](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), están activadas para todos los usuarios. Por ejemplo, los usuarios pueden usar la aplicación de Planner para crear y administrar tareas de equipo en Teams.

De forma predeterminada, todas las aplicaciones proporcionadas por Microsoft, así como las personalizadas, están disponibles y puede activarlas o desactivarlas individualmente. Hay una configuración que abarca toda la organización que le permite activar o desactivar todas las aplicaciones personalizadas para toda la organización.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Va a cambiar la configuración predeterminada de las aplicaciones de Teams? | Para obtener más información sobre las directivas y configuraciones que puede usar para administrar las aplicaciones de su organización, consulte [Configuración de administración de aplicaciones en Microsoft Teams](admin-settings.md).|
|||

### <a name="app-permissions-and-other-considerations"></a>Permisos de aplicación y otras consideraciones

Los usuarios tienen que dar su consentimiento a las aplicaciones y el administrador o profesional de TI las administra mediante directivas. Sin embargo, en la mayoría de los casos, los permisos y el perfil de riesgo de la aplicación se definen en la misma. 

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|<br>¿A qué aplicaciones deseo permitir el acceso? ¿A cuáles no quiero permitir el acceso?  | <ul><li>Vea [Consideraciones y permisos de las aplicaciones de Microsoft Teams](app-permissions.md) para ver una serie de aspectos que debe considerar al permitir el acceso a una aplicación, bot, pestaña o conector.</li><li>Vea [Publicar aplicaciones en el catálogo de aplicaciones de inquilinos de Teams](tenant-apps-catalog-teams.md) para obtener información acerca de cómo hacer que una aplicación esté disponible para los usuarios de su organización.</li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a>Bots para conversaciones privadas y canales

Los bots son programas automatizados que responden a las consultas o dan actualizaciones y notificaciones sobre detalles que puedan resultar interesantes para los usuarios o sobre los que quieran mantenerse informados. Los bots permiten a los usuarios interactuar con los servicios de nube, como la administración de tareas, la programación y los sondeos, en un chat de Teams. Teams admite bots en los canales y conversaciones privadas. Los administradores pueden controlar si se permite el uso de bots en un inquilino de Office 365.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Me interesa permitir bots personalizados en mi inquilino de Office 365?|Para obtener más información sobre cómo agregar bots, vea [Agregar bots para chats privados y canales en Microsoft Teams](add-bots.md). Para obtener información sobre cómo activar o desactivar los bots personalizados, consulte [Configuración de administrador de aplicaciones en Microsoft Teams](admin-settings.md).|
|||

### <a name="built-in-and-custom-tabs"></a>Pestañas personalizadas e integradas

Los propietarios y los miembros del equipo pueden agregar pestañas adicionales a cada canal para integrar mejor sus servicios en la nube. Agregue pestañas para ayudar a los usuarios a acceder y administrar los datos que más necesitan o usan. En los canales, las pestañas de Conversaciones y Archivos se crean de forma predeterminada. En cada chat privado, las pestañas de Conversaciones, Archivos, Organización y Actividad se crean de forma predeterminada. Además de estas pestañas integradas, puede diseñar y agregar pestañas personalizadas. Para obtener información sobre cómo activar o desactivar las aplicaciones de Teams en su organización, lea [Configuración de administrador de aplicaciones en Teams](admin-settings.md).

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Me interesa permitir pestañas personalizadas en mi inquilino de Office 365?|Para obtener más información, vea [Usar fichas integradas y personalizadas en Teams](built-in-custom-tabs.md).|
|||

### <a name="office-365-and-custom-connectors"></a>Conectores de Office 365 y personalizados

Los conectores mantienen su equipo al día haciendo llegar contenido y actualizaciones de servicios que se usan con frecuencia directamente en un canal. Con los conectores, los usuarios de Teams pueden recibir actualizaciones de servicios populares como Twitter, Trello, Wunderlist, GitHub y Azure DevOps Services en sus chats de Teams.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Me interesa permitir que los usuarios creen conectores personalizados?|Para obtener más información, vea [Usar conectores de Office 365 y personalizados en Teams](office-365-custom-connectors.md).|
|||

## <a name="additional-deployment-decisions"></a>Decisiones de implementación adicionales

Puede que le interese cambiar esta configuración en función de las necesidades y la configuración de su organización.

### <a name="activity-reports"></a>Informes de actividad

Puede usar los informes de actividad para ver cómo los usuarios de su organización usan Teams. Por ejemplo, si algunos aún no utilizan Teams, puede que no sepan cómo empezar o no entiendan cómo pueden usar Teams para ser más productivos y mejorar la colaboración. Su organización puede usar los informes de actividad para decidir dónde debe dar prioridad a los esfuerzos de aprendizaje y comunicación. Para ver los informes de actividad, debe ser un administrador global de Office 365, administrador de servicios de Teams o administrador de Skype Empresarial.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| <br>¿Quién necesita ver los informes de actividad? ¿Tienen los permisos adecuados para poder verlos? |<ul><li>Si no quiere asignar un rol de administrador a un usuario, puede [asignar el rol de Lector de informes](teams-activity-reports.md#reports-reader-role).</li><li>Vea [Roles y permisos](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) y [Ver y asignar roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para obtener información sobre cómo asignar roles de administrador en Azure Active Directory.</li></ul> |
|||

### <a name="app-templates"></a>Plantillas de aplicaciones

Las plantillas de aplicaciones son aplicaciones listas para producción en Microsoft Teams que están controladas por la comunidad, son de código abierto y están disponibles en GitHub. Cada una contiene instrucciones detalladas sobre cómo implementar e instalar la aplicación para su organización, lo que proporciona una aplicación lista para usar que puede instalar y empezar a usar inmediatamente. El código fuente completo también está disponible, para que pueda explorarlo en detalle, o bien puede bifurcar el código y modificarlo para satisfacer sus necesidades específicas.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| ¿Quiero instalar alguna plantilla de aplicación de Teams, como IceBreaker? |Para obtener más información, vea [Plantillas de aplicación para Teams](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||


## <a name="next-steps"></a>Siguientes pasos
- [Impulsar la adopción](adopt-microsoft-teams-landing-page.md) de aplicaciones destacadas, como Planner.
- [Implementar reuniones y conferencias](deploy-meetings-microsoft-teams-landing-page.md)
- [Implementar voz en la nube](cloud-voice-landing-page.md)


