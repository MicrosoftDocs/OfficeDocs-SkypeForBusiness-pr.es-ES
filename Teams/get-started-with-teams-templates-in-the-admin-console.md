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
description: Obtenga más información sobre las plantillas de equipo y cómo administrarlas en el Centro de administración de Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bff3c2c63b94df4c1e19a748d3e9e9912574faa
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819361"
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
> Los usuarios pueden [crear equipos a partir de plantillas de equipo predefinidas o personalizadas](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) en la aplicación Teams. Los desarrolladores también pueden crear equipos mediante programación a partir de plantillas de equipo predefinidas con Microsoft Graph. Para obtener más información, consulte [Introducción a las plantillas de equipo con Microsoft Graph](get-started-with-teams-templates.md).

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

| Tipo de plantilla | TemplateId | Propiedades que vienen con esta plantilla |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adoptar Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canales: <ul><li>General</li> <li>Anuncios</li> <li>Rincón de campeones</li> <li>Formularios de equipo</li><li>Calendario</li></ul> Aplicaciones: <ul><li>Wiki</li>  <li>Calendario del canal</li> <li>Hitos</li><li>Boletines</li></ul>|
| Administrar un proyecto |`com.microsoft.teams.template.ManageAProject`| Canales: <ul><li>General</li> <li>Anuncios</li> <li>Recursos</li> <li>Planeación</li></ul> Aplicaciones:<ul><li>Wiki</li><li>OneNote</li><li>Tareas</li><li>Listas</li><li>Power Automate</li></ul> |
| Administrar un evento|`com.microsoft.teams.template.ManageAnEvent` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Budget</li> <li>Contenido</li><li>Logística</li> <li>Planeación</li> <li> Marketing y RELACIONES PÚBLICAS</li></ul> Aplicaciones:<ul><li>Wiki</li><li>Sitio web</li> <li>YouTube</li> <li>Tareas</li> <li>OneNote</li> <li>Ideas para empleados</li> <li>Informador del problema</li><li>Power Automate</li><li>Boletines</li><li>Hitos</li></ul> |
|Incorporar empleados|`com.microsoft.teams.template.OnboardEmployees` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Chat de empleados</li> <li>Aprendizaje</li></ul>Aplicaciones:<ul><li>Wiki</li><li>Comunidades</li><li>Tareas</li><li>Ideas para empleados</li><li>Power Automate</li><li>Boletines</li><li>Hitos</li></ul>|
|Organizar el servicio de asistencia| `com.microsoft.teams.template.OrganizeHelpDesk`|Canales:<ul><li>General</li><li>Anuncios</li><li>Preguntas más frecuentes</li></ul>Aplicaciones:<ul><li>Wiki</li><li>OneNote</li><li>Tareas </li><li>Elogiar</li><li>Informador del problema</li><li>Power Automate</li><li>Boletines</li></ul> |
| Cuidado del paciente| `com.microsoft.teams.template.healthcareWard`| Canales:<ul><li>General</li><li>Anuncios</li><li>Reuniones</li><li>Rondas</li><li>Personal</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas  </li><li>Aprobaciones</li><li>Boletines</li><li>Inspección</li></ul>|
| Comunicación de crisis |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canales: <ul><li>General<li>Anuncios</li><li>Noticias mundiales</li><li>Comms internos</li><li>Comunicaciones externas</li><li>Solicitud de aprobaciones</li><li>Escalaciones de clientes</li><li>Actualización ejecutiva</li><li>Planeación</li><li>Logística</li></ul>Aplicaciones: <ul><li>Sitio web</li><li>Tareas</li><li>Informador del problema</li><li>Aprobaciones</li><li>Boletines</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|Sucursal bancaria| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canales: <ul><li>General<li>Anuncios</li><li>Reuniones</li><li>Reuniones de clientes</li><li>Solicitud de aprobaciones </li><li>Asesoramiento</li><li>Desarrollo de aptitudes</li><li>Procesamiento de préstamos</li><li>Quejas de clientes</li><li>Elogios</li><li>Material divertido</li><li>Cumplimiento</li></ul>Aplicaciones:<ul><li>Elogiar </li><li>Informador del problema</li><li>Wiki</li><li>Calendario</li><li>Aprobaciones</li><li>Boletines</li><li>Ideas</li></ul>|
|Respuesta a incidentes| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canales: <ul><li>General<li>Anuncios</li><li>Logística</li><li>Planeación</li><li>Recuperación</li><li>Urgente</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Tareas</li> <li>Aprobaciones</li> <li>Inspección</li> <li>Power Automate</li><li>Boletines</li><li>Hitos</li></ul>|
|Hospital| `com.microsoft.teams.template.healthcareHospital` |Canales: <ul><li>General</li><li>Anuncios</li><li>Cumplimiento</li><li>Custodia</li><li>Recursos humanos</li><li>Farmacia</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas</li><li>Tareas</li><li>Aprobaciones</li><li>Turnos</li><li>Boletines</li><li>Inspección</li><li>Ideas</li></ul>|
|Organizar una tienda| `com.microsoft.teams.template.retailStore` |Canales: <ul><li>General<li>Cambio de turno</li><li>Preparación del almacén</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Tareas</li><li>Turnos</li><li>Inspección</li></ul>|
|Venta al por menor para administradores| `com.microsoft.teams.template.retailManagerCollaboration` |Canales: <ul><li>General<li>Operaciones</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Tareas</li><li>Inspección</li></ul>|
|Calidad y seguridad |`com.microsoft.teams.template.QualitySafety`|Canales: <ul><li>General<li>Anuncios</li><li>Liderazgo</li><li>Mantenimiento</li><li>Línea de producción 1</li><li>Línea de producción 2</li><li>Línea de producción 3</li><li>Salud y seguridad</li><li>Aprendizaje</li><li>Material divertido</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Tareas</li> <li>Informador del problema</li> <li>Inspección</li> </ul>|
|Administrar voluntarios| `com.microsoft.teams.template.ManageVolunteers` |Canales: <ul><li>General<li>Anuncios</li><li>Informes</li><li>Administración de voluntarios</li><li>Oportunidades de participación</li><li>Incorporación de voluntarios</li></ul> Aplicaciones: <ul><li>Sitio web</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Tareas</li><li>SharePoint</li><li>OneNote</li></ul>|
||||

### <a name="team-templates-by-category-and-industry"></a>Plantillas de equipo por categoría e industria

Para obtener más información sobre cómo usar las plantillas predefinidas en su sector, vea:

- [Plantillas de equipo financiero](financial-teams-templates-in-the-admin-console.md)
- [Plantillas de equipo generales](general-teams-templates-in-the-admin-console.md)
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
|||

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
