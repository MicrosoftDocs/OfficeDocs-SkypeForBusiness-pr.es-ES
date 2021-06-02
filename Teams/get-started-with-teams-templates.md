---
title: Introducción a las plantillas de equipo con Microsoft Graph
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
description: Obtenga información sobre cómo usar plantillas de equipo en Microsoft Graph crear espacios de colaboración con canales para diferentes temas y preinstalar aplicaciones para proporcionar contenido y servicios.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0208b8c6ad16cc42611768a25237a6e48bf60401
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717831"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Introducción a las plantillas de equipo con Microsoft Graph

> [!NOTE]
> Actualmente, las plantillas de equipo no admiten la creación de canales privados. La creación de canales privados no se incluye en las definiciones de plantilla.

Las plantillas de equipo son definiciones predefinidas de la estructura de un equipo diseñadas en torno a una necesidad empresarial o un proyecto. Puede crear [su propia plantilla en la consola de administración.](get-started-with-teams-templates-in-the-admin-console.md) Con Microsoft Graph, usa las plantillas predefinidas. Puede usar plantillas de equipo para crear rápidamente espacios de colaboración enriquecidos con canales para diferentes temas y preinstalar aplicaciones para extraer contenido y servicios de misión crítica. Las plantillas de equipo proporcionan una estructura de equipo predefinida que puede ayudarle a crear fácilmente equipos coherentes en toda la organización.

En este artículo, explicaremos las propiedades que se pueden definir en las plantillas, qué tipos de plantilla base son y cómo puede usar algunas solicitudes de ejemplos para crear un equipo a partir de una plantilla.

Este artículo es para usted si:

- Responsable de planear, implementar y administrar varios equipos en toda la organización<br>
- Un desarrollador que quiera crear mediante programación un equipo con canales y aplicaciones predefinidos

## <a name="team-template-capabilities"></a>Capacidades de plantilla de equipo

La mayoría de las propiedades de un equipo se incluyen y son compatibles con las plantillas. Pero hay algunas propiedades y características que no son compatibles actualmente. La tabla siguiente proporciona un resumen rápido de lo que se incluye y lo que no se incluye en las plantillas de equipo.

| **Propiedades de equipo compatibles con plantillas de equipo** | **Las propiedades del equipo aún no son compatibles con las plantillas de equipo** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla base | Membresía de equipo |
| Nombre del equipo | Imagen del equipo |
| Descripción del equipo | Configuración del canal |
| Visibilidad del equipo (público o privado) | Conectores |
| Configuración del equipo (por ejemplo, miembro, invitado, @ menciones) | Archivos y contenido |
| Canal auto-favorito | |
| Aplicación instalada | |
| Pestañas ancladas | |

> [!NOTE]
> Agregaremos más capacidades de plantilla en futuras versiones de Microsoft Teams, así que vuelva a comprobar la información más actualizada sobre las propiedades compatibles.

## <a name="what-are-base-template-types"></a>Qué son los tipos de plantilla base

Los tipos de plantilla base son plantillas especiales que Microsoft creó para sectores específicos. Estas plantillas base a menudo contienen aplicaciones de propiedad que no están disponibles en la tienda. Además, las plantillas base suelen contener propiedades de equipo que aún no se admiten individualmente en las plantillas de equipo. Obtenga información sobre cómo usar las plantillas [de equipo en Microsoft Graph](get-started-with-teams-templates.md).

Una vez definido un tipo de plantilla base, puede ampliar o invalidar estas plantillas especiales con propiedades adicionales que quiera especificar. Algunos tipos de plantilla base contienen propiedades que no se pueden invalidar.

De forma predeterminada, la plantilla base se establece en **Estándar,** que no contiene ninguna aplicación de propiedad adicional ni propiedades especiales. A continuación se muestra la lista actual de tipos de plantilla base disponibles.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | No hay aplicaciones ni propiedades adicionales |
| Educación -<br>Equipo de clase | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Aplicaciones:<ul><li>OneNote Bloc de notas de clase (anclado a la **pestaña General)** </li><li>Aplicación Tareas (anclada a la **pestaña General)**</li></ul> Propiedades del equipo:<ul><li>Visibilidad del equipo establecida en **HiddenMembership** (no se puede invalidar)</li></ul> |
| Educación -<br>Equipo de docentes | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Aplicaciones:<ul><li>OneNote Bloc de notas para docentes (anclado a la **pestaña General)**</li></ul> |
|Educación -<br>Equipo de PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Aplicaciones:<ul><li>OneNote Bloc de notas plc (anclado a la **pestaña General)**</ul></li>|
| Comercio minorista:<br>Tienda | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailStore')` | Canales:<ul><li>Cambio de turno</li><li>Aprendizaje</li></ul>Propiedades del equipo<ul><li>Visibilidad de equipo establecida en Público</li></ul>Permisos de miembro<ul><li>Impedir que los miembros creen, actualicen o quiten canales</li><li>Impedir que los miembros agreguen o quiten aplicaciones</li><li>Impedir que los miembros creen, actualicen o quiten conectores</li></ul> |
| Comercio minorista:<br>Colaboración del administrador | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailManagerCollaboration')` | Canales:<ul><li>Aprendizaje</li><li>Operaciones</li></ul>Propiedades del equipo:<ul><li>Visibilidad de equipo establecida en Privado</li></ul>Permisos de miembro:<ul><li>Impedir que los miembros creen, actualicen o quiten canales</li><li>Impedir que los miembros agreguen o quiten aplicaciones</li><li>Impedir que los miembros creen, actualicen o quiten conectores</li></ul>|
| Sanidad -<br>Sala |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareWard')` |Canales: <ul><li>Anuncios\*</li><li>Reuniones\*</li><li>Rondas</li><li>Personal\*</li><li>Aprendizaje\*</li></ul>\*Canales marcados como favoritos automáticamente |
|Sanidad -<br>Hospital | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareHospital')` |Canales:<ul><li>Anuncios\*</li><li>Cumplimiento\*</li><li>Custodia</li><li>Recursos humanos</li></li><li>Farmacia</li></ul>\*Canal auto-favorito|
|||


Use las siguientes plantillas para crear equipos tanto en el Teams cliente como en Microsoft Graph.


| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adoptar Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Canales: <ul><li>General</li> <li>Anuncios</li> <li>Esquina Campeones</li> <li>Formularios de equipo</li></ul> Aplicaciones: <ul><li>Wiki</li>  <li>Calendario</li> |
| Administrar un proyecto |`com.microsoft.teams.template.`<br>`ManageAProject`| Canales: <ul><li>General</li> <li>Anuncios</li> <li>Recursos</li> <li>Planeación</li></ul> Aplicaciones:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Administrar un evento|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Budget</li> <li>Contenido</li><li>Logística</li> <li>Planeación</li> <li> Marketing y relaciones públicas</li></ul> Aplicaciones:<ul><li>Wiki</li><li>Sitio web</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Incorporar empleados|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Chat de empleados</li> <li>Aprendizaje</li></ul>Aplicaciones:<ul><li>Wiki</li><li>Comunidades</li></ul>|
|Organizar el servicio de ayuda| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Canales:<ul><li>General</li><li>Anuncios</li><li>Preguntas más frecuentes</li></ul>Aplicaciones:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Colaborar en la atención al paciente| `healthcareWard `| Canales:<ul><li>General</li><li>Anuncios</li><li>Reuniones</li><li>Rondas</li><li>Personal</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li>|
| Colaborar en eventos o crisis globales |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Canales: <ul><li>General<li>Anuncios</li><li>Noticias del mundo</li><li>Continuidad empresarial</li><li>Trabajo remoto</li><li>Comunicación interna</li><li>Comms externos</li><li>Quejas de clientes</li><li>Kudos</li><li>Actualización ejecutiva</li></ul>Aplicaciones: <ul><li>Elogio</li><li>Wiki</li><li>Sitio web</li></ul>|
|Colaborar en una sucursal bancaria| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Canales: <ul><li>General<li>Anuncios</li><li>Reuniones</li><li>Reuniones de clientes</li><li>Coaching</li><li>Desarrollo de aptitudes</li><li>Procesamiento de préstamo</li><li>Quejas de clientes</li><li>Kudos</li><li>Cosas divertidas</li><li>Cumplimiento</li></ul>|
|Coordinar la respuesta a incidentes| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Canales: <ul><li>General<li>Anuncios</li><li>Logística</li><li>Planeación</li><li>Recuperación</li><li>Urgente</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital| `healthcareHospita`l |Canales: <ul><li>General<li>Anuncios</li><li>Cumplimiento</li><li>Custodia</li><li>Recursos humanos</li><li>Farmacia</li></ul> Aplicaciones: <ul><li>Wiki</li></ul>|
|Organizar una tienda| `retailStore` |Canales: <ul><li>General<li>Cambio de turno</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li></ul>|
|Calidad y seguridad |`com.microsoft.teams.`<br>`template.QualitySafety`|Canales: <ul><li>General<li>Anuncios</li><li>Línea 1</li><li>Línea 2</li><li>Línea 3</li><li>Seguridad</li><li>Aprendizaje</li><li>Mantenimiento</li><li>Cosas divertidas</li></ul> Aplicaciones: <ul><li>Wiki</li></ul>|
|Comercio al por menor: colaboración de administradores| `retailManagerCollaboration` |Canales: <ul><li>General<li>Operaciones</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li></ul>|
||||

Vea [Introducción a las plantillas de equipo en el Centro de administración](get-started-with-teams-templates-in-the-admin-console.md) para obtener más información.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a las plantillas de equipo en la consola de administración](get-started-with-teams-templates-in-the-admin-console.md)
- [Crear un equipo](/graph/api/team-post?view=graph-rest-beta) (en vista previa)
- [Nuevo equipo](/powershell/module/teams/New-Team?view=teams-ps)
- [Formación de administradores para Microsoft Teams](itadmin-readiness.md)
