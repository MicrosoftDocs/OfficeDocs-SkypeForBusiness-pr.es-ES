---
title: Administrar la aplicación listas para su organización
author: LanaChin
ms.author: v-lanac
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo administrar la aplicación listas en Teams para los usuarios de su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7e237ffd041c2207516b714147d555b3a1b9043
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138404"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación listas para su organización en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview-of-lists"></a>Información general de listas

La aplicación listas de Microsoft Teams ayuda a los usuarios de la organización a realizar un seguimiento de la información, organizar el trabajo y administrar los flujos de trabajo. Con las listas, los usuarios pueden realizar un seguimiento de los datos, como problemas, activos, rutinas, contactos, inventarios, incidentes, préstamos, pacientes y más, con vistas, reglas y alertas personalizables para mantener sincronizados a todos los miembros del equipo.

En Teams, los usuarios tienen acceso a las listas como una ficha en un canal. Haga clic **+** para abrir la galería de pestañas y agregar una nueva instancia de la pestaña de la aplicación listas a un canal para comenzar. 

![Captura de pantalla de la aplicación listas en la galería de pestañas](media/lists-tab.png)

Los usuarios pueden crear listas nuevas o anclar listas existentes desde el mismo equipo o desde otro sitio de SharePoint al que tengan acceso. Las listas nuevas se pueden crear desde cero, desde las plantillas integradas, en función de la estructura de una lista existente o mediante la importación de datos desde un libro de Excel. La aplicación listas está disponible en Teams Desktop, en la web y en clientes móviles.

![Captura de pantalla de cómo crear una lista en la aplicación listas](media/lists-create-list.png)

## <a name="templates"></a>Plantillas

Las plantillas de listas se adaptan a escenarios comunes de seguimiento de información para los usuarios. Cada plantilla incluye una estructura de lista, diseños de formulario y opciones de formato predefinidos en una vista de lista y un nivel de vista de detalles para ayudar a los usuarios a empezar rápidamente. Después de seleccionar una plantilla, los usuarios obtienen una vista previa del aspecto que tendrá la lista, junto con algunos datos de ejemplo. Estos son algunos ejemplos de cómo los equipos de su organización pueden usar las plantillas predefinidas en las listas:

- Realice un seguimiento de los problemas y póngalos en cierre con la plantilla Issue Tracker.
- Organice todos los detalles de los eventos con la plantilla itinerario de eventos.
- Use la plantilla de pacientes para registrar las necesidades y el estado de los pacientes para que los equipos de atención médica de su organización de cuidado de la salud puedan monitorear y coordinar el cuidado.
- Realizar un seguimiento del estado de las solicitudes de préstamos con la plantilla préstamos.

## <a name="example-scenario"></a>Escenario de ejemplo

Una oficina de correos local es responsable de ordenar y entregar el correo en su distrito. Cada mañana, la oficina de correos tiene un Huddle de equipo para revisar los objetivos diarios, compartir anuncios y discutir incidentes conocidos.

Después de la Huddle, los transportistas de correo retoman su correo y comienzan su camino de entrega. Las incidencias pueden producirse a través de una ruta, por ejemplo, un accidente de un vehículo, un problema relacionado con el perro o un impago de la no Rest social. Cuando los transportistas de correo encuentran un incidente, usan Teams en sus dispositivos móviles para registrar los detalles del incidente, que se controlan en una lista en el canal del equipo. Todos los miembros del equipo, incluidas las compañías de correo en el campo, pueden ver esta información y mantenerse informados.

Antes de pasar a los equipos, los transportistas de correo tuvieron que volver a la oficina de correos para completar un formulario de copia impresa para informar de un incidente que se introdujo en una hoja de cálculo de Excel. Teams proporciona a los operadores de correo un teléfono móvil, experiencia donde pueden usar listas para denunciar incidentes en el campo a medida que se producen, compartir los detalles de los incidentes con los miembros del equipo, conversar sobre ellos en el canal e impulsar incidentes a la resolución.

## <a name="what-you-need-to-know-about-lists"></a>Lo que debe saber sobre las listas

### <a name="lists-is-available-in-every-team-and-channel"></a>Lists está disponible en todos los equipos y canales

Lists está preinstalado para todos los usuarios de Teams y está disponible directamente en la galería de pestañas de todos los equipos y canales. Esto significa que los usuarios no tienen que ir a la tienda de aplicaciones de Teams para instalarlo.

### <a name="lists-and-sharepoint"></a>Listas y SharePoint

Los datos de la lista se almacenan en el sitio de grupo de SharePoint Online. Para obtener más información acerca de cómo SharePoint Online interactúa con Teams, vea [Cómo SharePoint Online y OneDrive para la empresa interactúan con Teams](SharePoint-OneDrive-interact.md).

Los permisos establecidos en SharePoint se aplican a las listas creadas en la aplicación listas. De forma predeterminada, lists hereda permisos del sitio al que pertenecen. Estos permisos rigen los tipos de acciones que los usuarios pueden hacer, por ejemplo, si pueden crear o editar listas. Para obtener más información, vea [niveles de permisos en SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) y [permisos de usuario y niveles de permisos en SharePoint Server](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels).

En algunos escenarios, es posible que desee restringir qué acciones pueden hacer los usuarios en las listas. Por ejemplo, una persona de un equipo modifica una vista de lista, que la cambia para todos los miembros del equipo, y quiere permitir que solo el propietario del equipo o determinados miembros del equipo editen las vistas de la lista. Para obtener más información, consulte [personalizar permisos para una lista o biblioteca de SharePoint](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).

> [!NOTE]
> En este momento, los permisos de propietario y miembro de un equipo no se vinculan de ninguna manera a los permisos del sitio de grupo que rigen el comportamiento de las listas o de la aplicación listas. Sin embargo, en función de los comentarios y el uso de los clientes, esto se tendrá en cuenta para una futura iteración del producto.  

### <a name="limitations"></a>Algunas

Con las listas, los usuarios obtienen una experiencia de escritorio, Web y móvil. Es importante saber que los usuarios no pueden crear listas nuevas ni anclar listas existentes usando listas en el cliente móvil de Teams. Para ver o editar una lista en el cliente móvil de Teams, primero debe crear una lista o agregarla con las listas en el escritorio de Teams o el cliente web.

Los invitados de [canales privados](private-channels.md) no pueden crear o eliminar una lista ni iniciar una nueva conversación sobre un elemento de lista. Pueden agregar elementos de lista a las listas existentes y responder a una conversación existente sobre un elemento de lista. Tenga en cuenta que estas limitaciones solo se aplican a los canales privados.

### <a name="lists-and-the-sharepoint-app"></a>Listas y la aplicación de SharePoint

Si los usuarios de la organización crearon listas mediante la aplicación de SharePoint, esas listas se moverán automáticamente a las listas sin que el usuario tenga que realizar ninguna acción. Para obtener la mejor y más detallada lista de integración de Teams, use la aplicación lists y ancle las listas existentes.

## <a name="set-up-lists"></a>Configurar listas

### <a name="enable-or-disable-lists-in-your-organization"></a>Habilitar o deshabilitar listas de su organización

Lists está habilitado de forma predeterminada para todos los usuarios de Teams de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) del centro de administración de Microsoft Teams.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps** .
2. Realice una de las siguientes acciones:

    - Para desactivar las listas de su organización, busque la aplicación listas, selecciónela y, a continuación, haga clic en **bloquear**.
    - Para activar las listas de su organización, busque la aplicación listas, selecciónela y, a continuación, haga clic en **permitir**.

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar listas para usuarios específicos de su organización

Para permitir o bloquear a determinados usuarios de su organización el uso de listas, asegúrese de que listas está activada para su organización en la página [Administrar aplicaciones](manage-apps.md) y, después, cree una directiva de permisos de aplicaciones personalizada y asígnela a esos usuarios. Para obtener más información, vea [Administrar directivas de permisos de aplicaciones en Teams](teams-app-permission-policies.md).

## <a name="search-the-audit-log-for-list-events"></a>Buscar eventos de lista en el registro de auditoría

Las listas se habilitan con auditoría de nivel empresarial para que pueda buscar listas y eventos de elementos de lista en el registro de auditoría del centro de cumplimiento de seguridad &. Para obtener más información, vea [Buscar en el registro de auditoría del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

Para obtener una lista de los eventos de auditoría relevantes para la aplicación listas de Teams, consulte actividades de la [lista de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).

Antes de poder buscar en el registro de auditoría, primero debe activar la auditoría en el [centro de cumplimiento de & de seguridad](https://protection.office.com). Tenga en cuenta que los datos de auditoría solo están disponibles desde el punto en el que activó la auditoría.

## <a name="power-automate-power-apps-and-graph-api"></a>Automatización de Power, Power apps y Graph

Lists es compatible con [Power Automate](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint) para flujos de trabajo y [Power apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) para formularios de lista. Los programadores pueden usar la [API de listas](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) para conectar los datos de lista como un origen a través de Microsoft Graph.

## <a name="give-feedback-or-report-an-issue"></a>Enviar comentarios o informar de un problema
  
Para enviarnos comentarios o informar de un problema, haga clic en **ayuda** cerca de la parte inferior del navegación de la izquierda en Teams y, a continuación, seleccione **informar de un problema**. Seleccione **listas**y, a continuación, escriba sus comentarios o detalles sobre el problema que está experimentando.
