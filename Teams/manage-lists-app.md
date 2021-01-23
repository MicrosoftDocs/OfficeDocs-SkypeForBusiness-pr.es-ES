---
title: Administrar la aplicación Listas de su organización
author: cichur
ms.author: v-cichur
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenga información sobre cómo administrar la aplicación Listas en Teams para los usuarios de su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365initiative-lists
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: e0fb125ede9300395e045a0c5640abd075547562
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944615"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Listas de su organización en Microsoft Teams

## <a name="overview-of-lists"></a>Información general sobre listas

La aplicación Listas de Microsoft Teams ayuda a los usuarios de su organización a realizar un seguimiento de la información, organizar el trabajo y administrar los flujos de trabajo. Con Listas, los usuarios pueden realizar un seguimiento de datos como problemas, activos, rutinas, contactos, inventario, incidentes, mantenimiento, pacientes y mucho más, mediante vistas personalizables, reglas y alertas para mantener sincronizados a todos los miembros del equipo.

En Teams, los usuarios acceden a las listas como pestañas en un canal. Haga clic para abrir la galería de pestañas y agregar una nueva instancia de la pestaña **+** De listas a un canal para empezar.

![Aplicación Listas en la galería de pestañas](media/lists-tab.png)

Los usuarios pueden crear nuevas listas o anclar listas existentes desde el mismo equipo o desde otro sitio de SharePoint al que tengan acceso. Las listas nuevas se pueden crear desde cero, a partir de plantillas integradas, en función de la estructura de una lista existente o importando datos de un libro de Excel. La aplicación Listas está disponible en clientes móviles, web y de escritorio de Teams.

![cómo crear una lista en la aplicación Listas](media/lists-create-list.png)

## <a name="templates"></a>Plantillas

Las plantillas de listas están adaptadas a escenarios comunes de seguimiento de información para los usuarios. Cada plantilla incluye una estructura de lista predefinida, diseños de formulario y opciones de formato tanto en una vista de lista como en un nivel de vista de detalles para ayudar a los usuarios a comenzar rápidamente. Después de seleccionar una plantilla, los usuarios obtienen una vista previa del aspecto que tendrá la lista, junto con algunos datos de ejemplo. A continuación se muestran algunos ejemplos de cómo los equipos de su organización pueden usar las plantillas predefinidas en Listas:

- Realice un seguimiento de los problemas y tómelos para su cierre con la plantilla seguimiento de problemas.
- Organice todos los detalles del evento con la plantilla Itinerario del evento.
- Use la plantilla Pacientes para registrar las necesidades y el estado de los pacientes de los equipos de salud de su organización sanitaria para supervisar y coordinar la atención.
- Realice un seguimiento del estado de las aplicaciones de préstamo con la plantilla Descedido.

## <a name="example-scenario"></a>Escenario de ejemplo

Una oficina de correos local es la responsable de ordenar y entregar correo en su distrito. Cada mañana, la oficina de correos tiene un grupo de reunión para revisar los objetivos diarios, compartir anuncios y discutir incidentes conocidos.

Después de la reunión, los operadores de correo seleccionan su correo e inician su ruta de entrega. Los incidentes pueden ocurrir en una ruta, por ejemplo, un accidente de vehículo, un problema relacionado con un perro o un problema social. Cuando los operadores de correo se encuentran con un incidente, usan Teams en sus dispositivos móviles para registrar los detalles del incidente, que se marcan en una lista en el canal de equipo. Todos los miembros del equipo, incluidos los operadores de correo en el campo, pueden ver esta información y mantenerse informados.

Antes de pasar a Teams, los operadores de correo tenían que volver a la oficina de correos para completar un formulario de copia impresa para informar de un incidente que se escribió en una hoja de cálculo de Excel. Teams ofrece a los operadores de correo una experiencia móvil en primer lugar, donde pueden usar Listas para notificar incidentes en el campo a medida que se dan, compartir detalles de incidentes con los miembros del equipo, mantener conversaciones sobre ellos en el canal e impulsar las incidencias para que se resuelvan.

## <a name="what-you-need-to-know-about-lists"></a>Lo que debe saber sobre Listas

### <a name="lists-is-available-in-every-team-and-channel"></a>Las listas están disponibles en todos los equipos y canales

Las listas están preinstaladas para todos los usuarios de Teams y están disponibles directamente en la galería de pestañas de todos los equipos y canales. Esto significa que los usuarios no tienen que ir a la tienda de aplicaciones de Teams para instalarlo.

### <a name="lists-and-sharepoint"></a>Listas y SharePoint

Los datos de listas se almacenan en el sitio de grupo de SharePoint Online. Para obtener más información sobre cómo SharePoint Online interactúa con Teams, consulte Cómo [interactúan SharePoint Online y OneDrive para la Empresa con Teams.](SharePoint-OneDrive-interact.md)

Los permisos establecidos en SharePoint se aplican a listas creadas en la aplicación Listas. De forma predeterminada, las listas heredan los permisos del sitio al que pertenecen. Estos permisos rigen los tipos de acciones que los usuarios pueden realizar, como si pueden crear o editar listas. Para obtener más información, vea [Niveles de permisos en SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) y permisos de usuario y niveles de permisos en [SharePoint Server.](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)

En ciertos escenarios, es posible que desee restringir las acciones que los usuarios pueden realizar en las listas. Por ejemplo, una persona de un equipo edita una vista de lista, que cambia para todos los miembros del equipo, y solo desea permitir que el propietario del equipo o determinados miembros del equipo puedan editar vistas de lista. Para obtener más información, [vea Personalizar permisos para una lista o biblioteca de SharePoint.](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)

> [!NOTE]
> En este momento, los permisos de propietario y miembro de un equipo no están vinculados de ninguna manera a los permisos en el sitio de grupo que rigen el comportamiento de las listas o la aplicación Listas. Sin embargo, en función de los comentarios de los clientes y el uso, esto se considerará para una iteración futura del producto.  

### <a name="limitations"></a>Limitaciones

Con Lists, los usuarios obtienen una experiencia móvil, web y de escritorio. Es importante saber que los usuarios no pueden crear nuevas listas ni anclar listas existentes con Listas en el cliente móvil de Teams. Para ver o editar una lista en el cliente móvil de Teams, primero debe crear o agregar una lista con Listas en el cliente de escritorio o web de Teams.

Los invitados no pueden crear ni eliminar una lista. Pueden agregar elementos de lista a listas existentes, iniciar nuevas conversaciones sobre los elementos de lista y responder a conversaciones existentes sobre elementos de lista.

### <a name="lists-and-the-sharepoint-app"></a>Listas y la aplicación de SharePoint

Si los usuarios de su organización crearon listas con la aplicación de SharePoint, dichas listas se mueven automáticamente a Listas sin que sea necesaria ninguna acción del usuario. Para obtener la mejor experiencia de integración de listas y la más completa en Teams, use la aplicación Listas y anclar las listas existentes.

## <a name="set-up-lists"></a>Configurar listas

### <a name="enable-or-disable-lists-in-your-organization"></a>Habilitar o deshabilitar listas en su organización

Las listas están habilitadas de forma predeterminada para todos los usuarios de Teams en su organización. Puede desactivar o activar la aplicación en el [](manage-apps.md) nivel de la organización en la página Administrar aplicaciones del Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones**  >  **de** Teams.
2. Realice una de las siguientes acciones:

    - Para desactivar Listas para su organización, busque la aplicación Listas, selecciónelo y, a continuación, haga clic en **Bloquear.**
    - Para activar Listas para su organización, busque la aplicación Listas, selecciónelo y, a continuación, haga clic en **Permitir.**

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar Listas para usuarios específicos de su organización

Para permitir o impedir que determinados usuarios de la organización utilicen [](manage-apps.md) Listas, asegúrese de que Listas está activada para su organización en la página Administrar aplicaciones y, a continuación, cree una directiva de permisos de aplicación personalizada y asígnela a esos usuarios. Para obtener más información, consulte [Administrar directivas de permisos de aplicaciones en Teams.](teams-app-permission-policies.md)

## <a name="search-the-audit-log-for-list-events"></a>Buscar eventos de lista en el registro de auditoría

Las listas están habilitadas con auditoría de nivel empresarial para que pueda buscar listas y eventos de elementos de lista en el registro de auditoría del Centro de cumplimiento & seguridad. Para obtener más información, consulte Buscar en el registro de auditoría del Centro de cumplimiento [& seguridad.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

Para obtener una lista de eventos de auditoría relevantes para la aplicación Listas en Teams, vea actividades de [la lista de SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)

Antes de poder buscar en el registro de auditoría, primero tiene que activar la auditoría en el Centro de seguridad y [& cumplimiento.](https://protection.office.com) Tenga en cuenta que los datos de auditoría solo están disponibles desde el punto en el que ha activado la auditoría.

## <a name="power-automate-power-apps-and-graph-api"></a>Power Automate, Power Apps y API graph

Listas admite [Power Automate para](https://docs.microsoft.com/power-automate/flow-types) flujos de trabajo y Power Apps [para](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) formularios de lista. Los desarrolladores pueden usar [la API Listas](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) para conectar datos de lista como origen a través de Microsoft Graph.

## <a name="give-feedback-or-report-an-issue"></a>Enviar comentarios o informar de un problema
  
Para enviarnos comentarios o informar  de un problema, haga clic en Ayuda en la parte inferior del panel de navegación izquierdo de Teams y, a continuación, seleccione **Informar de un problema.** Selecciona **Listas** y, a continuación, escribe tus comentarios o detalles sobre el problema que estás experimentando.

## <a name="related-topics"></a>Temas relacionados

- [Enumera la documentación de ayuda](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
