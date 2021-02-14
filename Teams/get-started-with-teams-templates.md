---
title: Introducción a las plantillas de Teams con Microsoft Graph
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Aprenda a usar plantillas de Teams en Microsoft Graph para crear espacios de colaboración con canales para distintos temas y preinstalar aplicaciones para proporcionar contenido y servicios.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 484b3ac3fd3545ce306dcb6e3d833bb523df5a86
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772201"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Introducción a las plantillas de Teams con Microsoft Graph

> [!NOTE]
> Actualmente, las plantillas de Teams no admiten la creación de canales privados. La creación de canales privados no se incluye en las definiciones de plantillas.

Las plantillas de Teams son definiciones predefinidas de la estructura de un equipo diseñadas en torno a una necesidad empresarial o un proyecto. Puede crear [su propia plantilla en la consola de administración.](get-started-with-teams-templates-in-the-admin-console.md) Con Microsoft Graph, puede usar las plantillas predefinidas. Puede usar plantillas de Teams para crear rápidamente espacios de colaboración enriquecidos con canales para distintos temas y preinstalar aplicaciones para agregar contenido y servicios fundamentales. Las plantillas de Teams proporcionan una estructura de equipo predefinida que puede ayudarle a crear fácilmente equipos coherentes en toda su organización.

En este artículo explicaremos las propiedades que se pueden definir en las plantillas, qué tipos de plantillas base son y cómo puede usar algunas solicitudes de ejemplo para crear un equipo a partir de una plantilla.

Este artículo es para usted si:

- Responsable de planear, implementar y administrar varios equipos en toda la organización<br>
- Un desarrollador que desea crear mediante programación un equipo con aplicaciones y canales predefinidos

## <a name="teams-template-capabilities"></a>Capacidades de las plantillas de Teams

La mayoría de las propiedades de un equipo se incluyen y se admiten con plantillas. Pero hay algunas propiedades y características que actualmente no son compatibles. La tabla siguiente proporciona un resumen rápido de lo que se incluye y lo que no se incluye en las plantillas de Teams.

| **Propiedades de equipo admitidas por plantillas de Teams** | **Las propiedades del equipo aún no son compatibles con las plantillas de Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla base | Membresía de equipo |
| Nombre del equipo | Imagen del equipo |
| Descripción del equipo | Configuración de canales |
| Visibilidad del equipo (pública o privada) | Conectores |
| Configuración del equipo (por ejemplo, menciones de miembros, invitados o @) | Archivos y contenido |
| Canal favorito automático | |
| Aplicación instalada | |
| Pestañas ancladas | |

> [!NOTE]
> Agregaremos más funcionalidades de plantillas en futuras versiones de Microsoft Teams, así que vuelva a comprobar la información más actualizada sobre las propiedades compatibles.

## <a name="what-are-base-template-types"></a>Qué son los tipos de plantillas base

Los tipos de plantillas base son plantillas especiales que Microsoft ha creado para sectores específicos. Estas plantillas base suelen contener aplicaciones de propiedad que no están disponibles en la tienda. Además, las plantillas base suelen contener propiedades de equipo que aún no se admiten individualmente en las plantillas de Teams. Obtenga información sobre cómo usar las [plantillas de equipo en Microsoft Graph.](get-started-with-teams-templates.md)

Una vez definido un tipo de plantilla base, puede extender o invalidar estas plantillas especiales con propiedades adicionales que quiera especificar. Algunos tipos de plantilla base contienen propiedades que no se pueden anular.

De forma predeterminada, la plantilla base está establecida en **Estándar,** que no contiene aplicaciones de propiedad adicionales ni propiedades especiales. A continuación se muestra la lista actual de tipos de plantillas base disponibles.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | No hay aplicaciones ni propiedades adicionales |
| Educación -<br>Equipo de clase | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Aplicaciones:<ul><li>Bloc de notas de clase de OneNote (anclado a la **pestaña General)** </li><li>Aplicación Tareas (anclada a la **pestaña General)**</li></ul> Propiedades del equipo:<ul><li>Visibilidad de equipo establecida **en Miembro Oculto** (no se puede anular)</li></ul> |
| Educación -<br>Equipo de docentes | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Aplicaciones:<ul><li>Bloc de notas para docentes de OneNote (anclado a la **pestaña General)**</li></ul> |
|Educación -<br>Equipo plc |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Aplicaciones:<ul><li>Bloc de notas PLC de OneNote (anclado a la **pestaña General)**</ul></li>|
| Venta al por menor:<br>Almacén | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canales:<ul><li>Mayús handoff</li><li>Aprendizaje</li></ul>Propiedades del equipo<ul><li>Visibilidad del equipo establecida en Público</li></ul>Permisos de miembros<ul><li>Impedir que los miembros creen, actualicen o quiten canales</li><li>Impedir que los miembros agreguen o quiten aplicaciones</li><li>Impedir que los miembros creen, actualicen o quiten conectores</li></ul> |
| Venta al por menor:<br>Colaboración del administrador | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canales:<ul><li>Aprendizaje</li><li>Operations</li></ul>Propiedades del equipo:<ul><li>Visibilidad del equipo establecida en Privado</li></ul>Permisos de miembros:<ul><li>Impedir que los miembros creen, actualicen o quiten canales</li><li>Impedir que los miembros agreguen o quiten aplicaciones</li><li>Impedir que los miembros creen, actualicen o quiten conectores</li></ul>|
| Salud -<br>Uno de los líderes |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canales: <ul><li>Anuncios\*</li><li>Garabatos\*</li><li>Redondear</li><li>Empleados\*</li><li>Aprendizaje\*</li></ul>\*Canales auto favoritos |
|Salud -<br>Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canales:<ul><li>Anuncios\*</li><li>Cumplimiento\*</li><li>Descúyal</li><li>Recursos humanos</li></li><li>Clínica</li></ul>\*Canal auto favoritos|
|||


Use las siguientes plantillas para crear equipos tanto en el cliente de Teams como en Microsoft Graph.


| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adoptar Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Canales: <ul><li>General</li> <li>Anuncios</li> <li>Esquina de campeones</li> <li>Formularios de equipo</li></ul> Aplicaciones: <ul><li>Wiki</li>  <li>Calendario</li> |
| Administrar un proyecto |`com.microsoft.teams.template.`<br>`ManageAProject`| Canales: <ul><li>General</li> <li>Anuncios</li> <li>Recursos</li> <li>Planeación</li></ul> Aplicaciones:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Administrar un evento|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Budget</li> <li>Contenido</li><li>Logística</li> <li>Planeación</li> <li> Marketing y relaciones públicas</li></ul> Aplicaciones:<ul><li>Wiki</li><li>Sitio web</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Incorporar empleados|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Chat de empleado</li> <li>Aprendizaje</li></ul>Aplicaciones:<ul><li>Wiki</li><li>Comunidades</li></ul>|
|Organizar el servicio de ayuda| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Canales:<ul><li>General</li><li>Anuncios</li><li>Preguntas más frecuentes</li></ul>Aplicaciones:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Colaborar en la atención al paciente| `healthcareWard `| Canales:<ul><li>General</li><li>Anuncios</li><li>Garabatos</li><li>Redondear</li><li>Empleados</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li>|
| Colaborar en eventos o crisis globales |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Canales: <ul><li>General<li>Anuncios</li><li>Noticias internacionales</li><li>Continuidad empresarial</li><li>Trabajo remoto</li><li>Comunicación interna</li><li>Comms externos</li><li>Quejas de clientes</li><li>Kudos</li><li>Actualización ejecutiva</li></ul>Aplicaciones: <ul><li>Elogiar</li><li>Wiki</li><li>Sitio web</li></ul>|
|Colaborar en una rama de bancos| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Canales: <ul><li>General<li>Anuncios</li><li>Garabatos</li><li>Reuniones de clientes</li><li>Entrenador</li><li>Desarrollo de aptitudes</li><li>Procesamiento del préstamo</li><li>Quejas de clientes</li><li>Kudos</li><li>Cosas divertidas</li><li>Cumplimiento</li></ul>|
|Coordinar la respuesta a incidentes| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Canales: <ul><li>General<li>Anuncios</li><li>Logística</li><li>Planeación</li><li>Recuperación</li><li>Urgente</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital| `healthcareHospita`l |Canales: <ul><li>General<li>Anuncios</li><li>Cumplimiento</li><li>Descúyal</li><li>Recursos humanos</li><li>Clínica</li></ul> Aplicaciones: <ul><li>Wiki</li></ul>|
|Organizar una tienda| `retailStore` |Canales: <ul><li>General<li>Mayús handoff</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li></ul>|
|Calidad y seguridad |`com.microsoft.teams.`<br>`template.QualitySafety`|Canales: <ul><li>General<li>Anuncios</li><li>Línea 1</li><li>Línea 2</li><li>Línea 3</li><li>Seguridad</li><li>Aprendizaje</li><li>Mantenimiento</li><li>Cosas divertidas</li></ul> Aplicaciones: <ul><li>Wiki</li></ul>|
|Comercio al por menor: colaboración del administrador| `retailManagerCollaboration` |Canales: <ul><li>General<li>Operations</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li></ul>|
||||

Vea [Introducción a las plantillas de Teams en el Centro de administración](get-started-with-teams-templates-in-the-admin-console.md) para obtener más información.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a las plantillas de Teams en la consola de administración](get-started-with-teams-templates-in-the-admin-console.md)
- [Crear un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en versión preliminar)
- [New-Team](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formación de administradores para Microsoft Teams](itadmin-readiness.md)