---
title: Introducción a las plantillas de equipo en el centro de administración de Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
description: Obtenga más información sobre las plantillas de equipo y cómo administrarlas en el Centro de administración de Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 063f84ffc0b34c99ff937c4a5496d5df3be2ddf5
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778990"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Introducción a las plantillas de equipo en el centro de administración de Teams

**La capacidad de crear plantillas personalizadas aún no es compatible con los clientes de educación.**

> [!NOTE]
> - Los canales privados y compartidos no se admiten actualmente en las plantillas de equipo. La creación de canales privados y compartidos no se incluye en las definiciones de plantillas.
>
> - Las etiquetas de confidencialidad no se admiten en las plantillas de equipo en entornos GCC. La opción de etiqueta de confidencialidad del flujo Crear equipo a partir de plantilla no se aplicará al equipo.

## <a name="overview"></a>Información general

Una plantilla de equipo en Microsoft Teams es una definición de la estructura de un equipo diseñada en torno a una necesidad empresarial o un proyecto. Como administrador, puede usar plantillas para implementar fácilmente equipos coherentes en toda la organización. Con las plantillas, los usuarios pueden crear rápidamente espacios de colaboración enriquecidos con configuraciones predefinidas, canales y aplicaciones.

Puede administrar plantillas de equipo en el Centro de administración de Microsoft Teams o con PowerShell. Puede usar las plantillas predefinidas que proporcionamos y también puede [crear sus propias plantillas personalizadas](#create-your-own-team-templates). También puede [aplicar directivas de plantilla](#apply-team-template-policies) para controlar qué plantillas están disponibles para los usuarios en Teams.

En este artículo se ofrece información general sobre cómo trabajar con plantillas de equipo en el Centro de administración de Teams. Obtendrá información sobre las propiedades compatibles con las plantillas, las plantillas predefinidas que proporcionamos, los límites de tamaño de las plantillas, cómo crear y administrar plantillas y mucho más.

> [!NOTE]
> Los usuarios pueden [crear equipos a partir de plantillas de equipo predefinidas o personalizadas](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) en la aplicación Teams. Los desarrolladores también pueden crear equipos mediante programación a partir de plantillas de equipo predefinidas o personalizadas con Microsoft Graph. Para obtener más información, consulte [Introducción a las plantillas de equipo con Microsoft Graph](get-started-with-teams-templates.md).

## <a name="team-template-capabilities"></a>Capacidades de plantillas de equipo

La mayoría de las propiedades de un equipo se incluyen y son compatibles con las plantillas de equipo. Pero hay algunas propiedades y características que no son compatibles actualmente. Este es un resumen de lo que se incluye y lo que no se incluye en las plantillas de equipo.

| **Propiedades de equipo admitidas por plantillas de equipo** | **Las propiedades de equipo aún no son compatibles con las plantillas de equipo** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla | Membresía de equipo |
| Nombre del equipo | Imagen del equipo |
| Descripción del equipo | Configuración de canal |
| Visibilidad del equipo (pública o privada) | Conectores |
| Configuración del equipo (por ejemplo, miembro, invitado, @ menciones) | Archivos y contenido |
| Canal Autofavorite | |
| Aplicación instalada | |
| Pestañas ancladas | |

> [!NOTE]
> Agregaremos más funcionalidades de plantilla en futuras versiones de Microsoft Teams, así que vuelva a comprobar la información más actualizada sobre las propiedades compatibles.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Plantillas de equipo predefinidas en el Centro de administración de Teams

Estas son las plantillas de equipo predefinidas que están disponibles en el Centro de administración de Teams. Las plantillas predefinidas son plantillas que hemos creado para sectores específicos. Para ver estas plantillas, en el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Plantillas de equipo de** **Teams** > .

Puede duplicar plantillas predefinidas, pero no editarlas. Si desea cambiar las propiedades de una plantilla predefinida, puede crear una plantilla nueva a partir de una existente y, a continuación, agregar o quitar las propiedades que desee. Tenga en cuenta que algunas propiedades de algunas plantillas no se pueden cambiar.

> [!NOTE]
> Un asterisco (*) indica que la plantilla es una *plantilla conectada a Microsoft 365*. Cuando los usuarios crean un equipo con la plantilla, la plantilla de SharePoint conectada se aplica al sitio y al equipo. Los componentes de SharePoint, como páginas, listas e integraciones de Power Platform, se agregan y anclan automáticamente como pestañas al canal General del equipo. Los usuarios pueden editar estas páginas y listas directamente desde Teams.
>
> Para obtener más información sobre las plantillas de SharePoint, vea [Aplicar y personalizar plantillas de sitio de SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

>[!div class="mx-tdBreakAll"]
>| Tipo de plantilla | TemplateId | Propiedades que vienen con esta plantilla |
>| ------------------ | -------------- | ----------------------------------------------------- |
>|Administrar un proyecto* |`com.microsoft.teams.template.ManageAProject`| Canales: <ul><li>General</li> <li>Anuncios</li> <li>Recursos</li> <li>Planeación</li></ul> Aplicaciones:<ul><li>Aprobaciones</li><li>Boletines</li><li>Listas<ul><li>Seguimiento de proyectos</li><li>Seguimiento de problemas</li></ul></li><li>Hitos</li><li>OneNote</li><li>Power Automate</li><li>Páginas de SharePoint<ul><li>Nuestro sitio</li></ul></li><li>Tareas por Planner y To Do</li><li>Wiki</li></ul> |
|Administrar un evento*|`com.microsoft.teams.template.ManageAnEvent` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Budget</li> <li>Contenido</li><li>Logística</li> <li>Planeación</li> <li> Marketing y RELACIONES PÚBLICAS</li></ul> Aplicaciones:<ul><li>Aprobaciones</li><li>Boletines</li> <li>Ideas para empleados</li><li>Listas<ul><li>Programador de contenido</li></ul></li><li>Hitos</li> <li>OneNote</li> <li>Power Automate</li> <li>Páginas de SharePoint<ul><li>Nuestro sitio</li><li>Acerca de nuestro evento</li></ul><li>Tareas por Planner y To Do</li><li>Wiki</li> |
|Empleados a bordo*|`com.microsoft.teams.template.OnboardEmployees` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Chat de empleados</li> <li>Aprendizaje</li></ul>Aplicaciones:<ul><li>Boletines</li><li>Ideas para empleados</li><li>Listas<ul><li>Lista de comprobación de incorporación</li></ul></li><li>Hitos</li><li>Power Automate</li> <li>Páginas de SharePoint<ul><li>Introducción</li><li>Aprendizaje</li></ul><li>Tareas por Planner y To Do</li><li>Viva Engage</li><li>Wiki</li></ul>|
|Adoptar Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canales: <ul><li>General</li> <li>Anuncios</li> <li>Rincón de campeones</li> <li>Formularios de equipo</li><li>Calendario</li></ul> Aplicaciones: <ul><li>Boletines</li>  <li>Calendario del canal</li> <li>Hitos</li><li>Wiki</li></ul>|
|Organizar el servicio de asistencia*| `com.microsoft.teams.template.OrganizeHelpDesk`|Canales:<ul><li>General</li><li>Anuncios</li><li>Preguntas más frecuentes</li></ul>Aplicaciones:<ul><li>Informes de problemas</li><li>Listas<ul><li>Dispositivos</li><li>Entradas</li></ul></li><li>OneNote</li><li>Power Automate</li><li>Páginas de SharePoint<ul><li>Nuestro sitio</li><li>Preguntas frecuentes</li></ul></li><li>Tareas por Planner y To Do</li><li>Wiki</li></ul> |
|Respuesta a incidentes| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canales: <ul><li>General<li>Anuncios</li><li>Logística</li><li>Planeación</li><li>Recuperación</li><li>Urgente</li></ul> Aplicaciones: <ul><li>Aprobaciones</li><li>Boletines</li><li>Excel</li><li>Inspección</li><li>Hitos</li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint</li><li>Tareas por Planner y To Do</li><li>Wiki</li></ul>|
|Crisis Communications* |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canales: <ul><li>General<li>Anuncios</li><li>Executive Update</li><li>Planeación</li><li>Logística</li></ul>Aplicaciones: <ul><li>Aprobaciones</li><li>Informes de problemas</li><li>Listas<ul><li>Programador de contenido</li><li>Plan de proyecto</li></ul></li><li>OneNote</li><li>Power Automate</li><li>Páginas de SharePoint<ul><li>Nuestro sitio</li><li>Última actualización</li></ul><li>Tareas por Planner y To Do</li>|
|Administrar una Store*| `com.microsoft.teams.template.retailStore` |Canales: <ul><li>General<li>Desplazar la entrega</li><li>Store Readiness</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Aprobaciones</li><li>Inspección</li><li>Listas<ul><li>Lista de inventario</li></ul></li><li>Páginas de SharePoint<ul><li>Nuestra tienda</li></ul></li><li>Turnos</li><li>Tareas por Planner y To Do</li><li>Wiki</li></ul>|
|Sucursal bancaria| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canales: <ul><li>General<li>Anuncios</li><li>Reuniones</li><li>Reuniones de clientes</li><li>Solicitud de aprobaciones </li><li>Asesoramiento</li><li>Desarrollo de habilidades</li><li>Procesamiento de préstamos</li><li>Quejas de clientes</li><li>Elogios</li><li>Cosas divertidas</li><li>Cumplimiento</li></ul>Aplicaciones:<ul><li>Aprobaciones</li><li>Boletines</li><li>Calendario del canal</li><li>Ideas para empleados</li><li>Informes de problemas</li><li>Elogiar</li><li>Turnos</li><li>Wiki</li></ul>|
|Atención al paciente| `com.microsoft.teams.template.healthcareWard`| Canales:<ul><li>General</li><li>Anuncios</li><li>Reuniones</li><li>Rondas</li><li>Personal</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Aprobaciones</li><li>Boletines</li><li>Inspección</li><li>Listas</li><li>Turnos</li><li>Tareas por Planner y To Do</li><li>Wiki</li></ul>|
|Hospital| `com.microsoft.teams.template.healthcareHospital` |Canales: <ul><li>General</li><li>Anuncios</li><li>Cumplimiento</li><li>Custodia</li><li>Recursos humanos</li><li>Farmacia</li></ul> Aplicaciones: <ul><li>Aprobaciones</li><li>Boletines</li><li>Ideas para empleados</li><li>Inspección</li><li>Listas</li><li>Turnos</li><li>Tareas por Planner y To Do</li><li>Wiki</li></ul>|
|Calidad y seguridad |`com.microsoft.teams.template.QualitySafety`|Canales: <ul><li>General</li><li>Liderazgo</li><li>Mantenimiento</li><li>Línea de producción 1</li><li>Línea de producción 2</li><li>Línea de producción 3</li><li>Salud y seguridad</li><li>Aprendizaje</li><li>Cosas divertidas</li></ul> Aplicaciones: <ul><li>Aprobaciones</li><li>Inspección</li><li>Informes de problemas</li><li>Turnos</li> <li>Tareas por Planner y To Do</li> <li>Wiki</li> </ul>|
|Venta al por menor para administradores*| `com.microsoft.teams.template.retailManagerCollaboration` |Canales: <ul><li>General<li>Operaciones</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Aprobaciones</li><li>Inspección</li><li>Páginas de SharePoint<ul><li>Nuestra tienda</li></ul></li><li>Tareas por Planner y To Do</li><li>Wiki</li></ul>|
|Administrar voluntarios| `com.microsoft.teams.template.ManageVolunteers` |Canales: <ul><li>General<li>Anuncios</li><li>Informes</li><li>Administración de voluntarios</li><li>Oportunidades de participación</li><li>Incorporación de voluntarios</li></ul> Aplicaciones: <ul><li>OneNote</li><li>Power Apps</li><li>Power BI</li><li>SharePoint</li><li>Tareas por Planner y To Do</li><li>Sitio web</li><li>YouTube</li></ul>|
|Colaboración en primera línea| `com.microsoft.teams.template.Frontline` |Canales: <ul><li>General<li>Anuncios</li><li>Desplazar la entrega</li><li>Operaciones</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Aprobaciones</li><li>Informes de problemas</li><li>Listas</li><li>Elogiar</li><li>Turnos</li><li>Tareas por Planner y To Do</li></ul>|

### <a name="team-templates-by-category-and-industry"></a>Plantillas de equipo por categoría e industria

Para obtener más información sobre cómo usar las plantillas predefinidas en su sector, vea:

- [Plantillas de equipo generales](general-teams-templates-in-the-admin-console.md)
- [Plantillas de equipo financiero](financial-teams-templates-in-the-admin-console.md)
- [Plantillas de equipo de administración pública](government-teams-templates-in-the-admin-console.md)
- [Plantillas de equipo de atención sanitaria](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Fabricación de plantillas de equipo](manufacturing-teams-templates-in-the-admin-console.md)
- [Plantillas de equipo para ONG](team-templates-nonprofit.md)
- [Plantillas de equipo comerciales](get-started-with-retail-teams-templates.md)

## <a name="team-template-size-limits"></a>Límites de tamaño de las plantillas de equipo

Las plantillas están limitadas a un número específico de canales, pestañas y aplicaciones.

 > [!Note]
 > Puede agregar más canales, pestañas y aplicaciones al equipo después de crearlo a partir de una plantilla.

|Característica | Límite|
|-|-|
|Canales por plantilla | 15 |
|Pestañas por canal en una plantilla | 20 |
|Aplicaciones por plantilla | 50|

Para obtener más información, consulte [Límites y especificaciones de Teams](limits-specifications-teams.md).

## <a name="manage-team-templates"></a>Administrar plantillas de equipo

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Administrar plantillas de equipo en el Centro de administración de Teams

#### <a name="view-team-templates"></a>Ver plantillas de equipo

Para ver las plantillas de equipo, en el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Plantillas de equipo de** **Teams** > . Seleccione una plantilla para ver más detalles, incluidos los canales y las aplicaciones que contiene.

#### <a name="create-your-own-team-templates"></a>Crear sus propias plantillas de equipo

Puede crear sus propias plantillas personalizadas desde cero, a partir de un equipo existente y a partir de una plantilla existente. Para más información, vea:

- [Crear una plantilla de equipo personalizada](create-a-team-template.md)
- [Crear una plantilla a partir de un equipo existente](create-template-from-existing-team.md)
- [Crear una plantilla de equipo a partir de una plantilla de equipo existente](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Aplicar directivas de plantilla de equipo

Para controlar las plantillas que los usuarios ven en Teams para [crear equipos](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b), puede establecer directivas de plantillas y asignarlas a usuarios y grupos de su organización. Para obtener más información, consulte [Administrar plantillas de equipo en el Centro de administración de Teams](templates-policies.md).

### <a name="manage-team-templates-using-powershell"></a>Administrar plantillas de equipo con PowerShell

Use los siguientes cmdlets para administrar las plantillas en PowerShell.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate)

## <a name="related-articles"></a>Artículos relacionados

- [Crear un equipo a partir de una plantilla](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introducción a las plantillas de equipo con Microsoft Graph](get-started-with-teams-templates.md)
- [Clonar un equipo](/graph/api/team-clone)
- [Información general sobre la integración de Teams y SharePoint](/sharepoint/teams-connected-sites)
