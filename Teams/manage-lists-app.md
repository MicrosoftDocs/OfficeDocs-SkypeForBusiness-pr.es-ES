---
title: Administrar la aplicación Lists para su organización
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
description: Obtenga más información sobre cómo administrar la aplicación Lists en Teams para los usuarios de su organización.
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
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944615"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Lists para su organización en Microsoft Teams

## <a name="overview-of-lists"></a>Información general de Lists

La aplicación Lists en Microsoft Teams ayuda a los usuarios de su organización a realizar un seguimiento de la información, organizar el trabajo y administrar los flujos de trabajo. Con Lists, los usuarios pueden realizar un seguimiento de datos como problemas, activos, rutinas, contactos, inventario, incidentes, préstamos, pacientes y mucho más con vistas personalizables, reglas y alertas para mantener a todos los miembros del equipo sincronizados.

En Teams, los usuarios acceden a Lists como una pestaña de un canal. Haga clic en **+** para abrir la galería de pestañas y agregar una nueva instancia de pestaña de la aplicación Lists a un canal para empezar.

![Aplicación Lists en la galería de pestañas](media/lists-tab.png)

Los usuarios pueden crear nuevas listas o anclar listas existentes desde el mismo equipo o desde un sitio de SharePoint al que tengan acceso. Las listas nuevas se pueden crear desde cero, a partir de plantillas integradas, en función de la estructura de una lista existente o importando datos de un libro de Excel. La aplicación Lists está disponible en clientes móviles, web y de escritorio de Teams.

![Cómo crear una lista en la aplicación Lists](media/lists-create-list.png)

## <a name="templates"></a>Plantillas

Las plantillas de Lists se adaptan a escenarios habituales de seguimiento de información para los usuarios. Cada plantilla incluye una estructura de lista predefinida, diseños de formulario y opciones de formato en una vista de lista y un nivel de vista de detalles para ayudar a los usuarios a empezar rápidamente. Después de seleccionar una plantilla, los usuarios obtienen una vista previa del aspecto que tendrá la lista, junto con algunos datos de ejemplo. Estos son algunos ejemplos de cómo los equipos de su organización pueden usar las plantillas predefinidas en Lists:

- Realice un seguimiento de los problemas y cierre los archivos con la plantilla Seguimiento de problemas.
- Organice todos los detalles del evento con la plantilla Itinerario del evento.
- Use la plantilla Pacientes para registrar las necesidades y el estado de los pacientes de los equipos de salud de su organización sanitaria para supervisar y coordinar la atención.
- Realice un seguimiento del estado de las aplicaciones de préstamo con la plantilla Préstamos.

## <a name="example-scenario"></a>Escenario de ejemplo

Una oficina de correos local es la responsable de ordenar y entregar el correo en su distrito. Cada mañana, la oficina de correos cuenta con un equipo que le ayudará a revisar los objetivos diarios, compartir anuncios y tratar los incidentes conocidos.

Después de juntarse, los carteros recogen su correo e inician la ruta de entrega. Los incidentes pueden producirse en una ruta, por ejemplo, un accidente de vehículo, un problema relacionado con un perro o una protesta social. Cuando los carteros se encuentran con un incidente, usan Teams en sus dispositivos móviles para registrar los detalles del incidente, que se marcan en una lista en el canal del equipo. Todos los miembros del equipo, incluidos los carteros sobre el terreno, pueden ver esta información y mantenerse informados.

Antes de cambiar a Teams, los carteros tenían que volver a la oficina de correos con el fin de completar un formulario de copia impresa para informar de un incidente que se había indicado en una hoja de cálculo de Excel. Teams ofrece a los carteros una experiencia móvil de primera mano en la que pueden usar Lists para informar sobre los incidentes sobre el terreno a medida que se produzcan, compartir detalles de incidentes con los miembros del equipo, mantener conversaciones sobre ellos en el canal e impulsar la resolución de incidentes.

## <a name="what-you-need-to-know-about-lists"></a>Todo lo que debe saber sobre Lists

### <a name="lists-is-available-in-every-team-and-channel"></a>Lists está disponible en todos los equipos y canales

La aplicación Lists viene preinstalada para todos los usuarios de Teams y está disponible directamente en la galería de pestañas de todos los equipos y canales. Esto quiere decir que los usuarios no tienen que ir a la tienda de aplicaciones de Teams para instalarla.

### <a name="lists-and-sharepoint"></a>Lists y SharePoint

Los datos de Lists se almacenan en el sitio de grupo de SharePoint Online. Para obtener más información sobre cómo interactúa SharePoint Online, vea [Cómo interactúan SharePoint Online y OneDrive para la Empresa con Teams](SharePoint-OneDrive-interact.md).

Los permisos establecidos en SharePoint se aplican a las listas creadas en la aplicación Lists. De forma predeterminada, las listas heredan los permisos del sitio al que pertenecen. Estos permisos rigen los tipos de acciones que los usuarios pueden realizar, por ejemplo, si pueden crear o editar listas. Para obtener más información, vea [Niveles de permisos en SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) y [Permisos de usuario y niveles de permisos en SharePoint Server](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels).

En determinados escenarios, puede que quiera limitar las acciones que los usuarios pueden realizar en las listas. Por ejemplo, una persona de un equipo edita una vista de lista, que la cambia para todos los miembros del equipo, y usted quiere permitir que solo el propietario o determinados miembros del equipo puedan editar las vistas de lista. Para obtener más información, vea [Personalizar los permisos de una lista o biblioteca de SharePoint](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).

> [!NOTE]
> En este momento, los permisos de propietario y miembro de un equipo no están vinculados de ninguna manera con los permisos en el sitio de grupo que rigen el comportamiento de las listas o de la aplicación Lists. Sin embargo, en vista de los comentarios y el uso de los clientes, esto se tendrá en consideración para una iteración futura del producto.  

### <a name="limitations"></a>Limitaciones

Con Lists, los usuarios obtienen una experiencia móvil, web y de escritorio. Es importante saber que los usuarios no pueden crear nuevas listas ni anclar listas existentes con Lists en el cliente móvil de Teams. Para ver o editar una lista en el cliente móvil de Teams, primero debe crearla o agregarla con Lists en el cliente web o de escritorio de Teams.

Los invitados no pueden crear ni eliminar una lista. Pueden agregar elementos de lista a listas existentes, iniciar conversaciones nuevas sobre elementos de lista y responder a conversaciones existentes sobre elementos de lista.

### <a name="lists-and-the-sharepoint-app"></a>Lists y la aplicación SharePoint

Si los usuarios de su organización crearon listas con la aplicación SharePoint, estas se moverán automáticamente a Lists sin que el usuario necesite realizar ninguna acción. Para obtener la mejor y más completa experiencia de integración de listas en Teams, use la aplicación Lists y ancle las listas que tenga.

## <a name="set-up-lists"></a>Configurar Lists

### <a name="enable-or-disable-lists-in-your-organization"></a>Deshabilitar o habilitar Lists en la organización

De forma predeterminada, Lists está habilitado para todos los usuarios de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) del centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. Realice una de las siguientes acciones:

    - Para desactivar Lists para su organización, busque la aplicación, selecciónela y después haga clic en **Bloquear**.
    - Para activar Lists para su organización, busque la aplicación, selecciónela y después haga clic en **Permitir**.

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar Lists para usuarios específicos de su organización

Para permitir o impedir que usuarios específicos de la organización puedan usar Lists, asegúrese de que la aplicación esté activada para su organización en la página [Administrar aplicaciones](manage-apps.md) y después cree una directiva de permisos de aplicación personalizada y asígnela a esos usuarios. Para obtener más información, vea [Administrar directivas de permisos de aplicaciones en Teams](teams-app-permission-policies.md).

## <a name="search-the-audit-log-for-list-events"></a>Buscar eventos en el registro de auditoría

Las listas están habilitadas con auditoría de nivel empresarial para que pueda buscar listas y eventos de elementos de lista en el registro de auditoría del Centro de seguridad y cumplimiento. Para obtener más información, vea [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

Para obtener una lista de eventos de auditoría relevantes para la aplicación Lists en Teams, vea [actividades de lista de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).

Para que pueda buscar en el registro de auditoría, primero debe activar la característica de auditoría en el [Centro de seguridad y cumplimiento](https://protection.office.com). Tenga en cuenta que los datos de auditoría solo están disponibles desde el momento en que activó la característica de auditoría.

## <a name="power-automate-power-apps-and-graph-api"></a>Power Automate, Power Apps y API de Graph

Lists admite [Power Automate](https://docs.microsoft.com/power-automate/flow-types) para flujos de trabajo y [Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) para formularios de lista. Los desarrolladores pueden usar la [API de Lists](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) para conectar datos de lista como origen a través de Microsoft Graph.

## <a name="give-feedback-or-report-an-issue"></a>Enviar comentarios o informar de un problema
  
Para enviarnos comentarios o informar de un problema, haga clic en **Ayuda** junto a la parte inferior del panel de navegación izquierdo de Teams y seleccione **Informar de un problema**. Seleccione **Lists** y después escriba sus comentarios o detalles sobre el problema que experimenta.

## <a name="related-topics"></a>Temas relacionados

- [Documentación de ayuda de Lists](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
