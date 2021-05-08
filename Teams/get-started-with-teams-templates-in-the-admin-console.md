---
title: Usar Teams en el Centro de administración
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar Teams para crear espacios de colaboración con canales para diferentes temas con plantillas preinstaladas.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56577639e62c954d430d2745f5b105e97f5c56ff
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264900"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>Introducción a las Teams en el Centro de administración

**La capacidad de crear plantillas personalizadas aún no es compatible con los clientes de EDU.**

> [!NOTE]
> Actualmente, los canales privados y las etiquetas de confidencialidad no son compatibles Teams plantillas. La creación de canales privados no se incluye en las definiciones de plantilla. La opción de etiqueta de confidencialidad **en Crear equipo a partir** del flujo de plantillas no se aplicará al equipo.

Teams plantillas son definiciones predefinidas de la estructura de un equipo diseñadas en torno a una necesidad empresarial o un proyecto. Use plantillas predefinidas o cree su propia plantilla. Teams plantillas le permiten crear rápidamente espacios de colaboración enriquecidos con canales para diferentes temas y preinstalar aplicaciones para extraer contenido y servicios de misión crítica. Teams plantillas proporcionan una estructura de equipo predefinida que puede ayudarle a crear fácilmente equipos coherentes en toda la organización. Actualmente puede crear un equipo a partir de una plantilla en Teams o con [Microsoft Graph](get-started-with-teams-templates.md).

En este artículo se describen las siguientes características:

- Las propiedades que se pueden definir en plantillas.
- Los tipos de plantilla base.
- Cómo puede usar algunas solicitudes de ejemplos para crear un equipo a partir de una plantilla.

Este artículo es para usted si es responsable de planear, implementar y administrar varios equipos en toda la organización

## <a name="teams-template-capabilities"></a>Teams de plantilla

La mayoría de las propiedades de un equipo se incluyen y son compatibles con las plantillas. Pero hay algunas propiedades y características que no son compatibles actualmente. En la tabla siguiente se proporciona un resumen rápido de lo que se incluye y lo que no se incluye en Teams plantillas.

| **Propiedades de equipo compatibles con Teams plantillas** | **Las propiedades de equipo aún no son compatibles Teams plantillas** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla base | Membresía de equipo |
| Nombre del equipo | Imagen del equipo |
| Descripción del equipo | Configuración del canal |
| Visibilidad del equipo (público o privado) | Conectores |
| Configuración del equipo (por ejemplo, miembro, invitado, @ menciones) | Archivos y contenido |
| Canal de autofavorite | |
| Aplicación instalada | |
| Pestañas ancladas | |

> [!NOTE]
> Agregaremos más capacidades de plantilla en futuras versiones de Microsoft Teams, así que vuelva a comprobar la información más actualizada sobre las propiedades compatibles.

## <a name="what-are-base-template-types"></a>Qué son los tipos de plantilla base

Los tipos de plantilla base son plantillas especiales que Microsoft creó para sectores específicos. Estas plantillas base a menudo contienen aplicaciones de propiedad que no están disponibles en la tienda de aplicaciones.

Una vez definido un tipo de plantilla base, puede ampliar o invalidar estas plantillas especiales con más propiedades que le gustaría especificar. Algunos tipos de plantilla base contienen propiedades que no se pueden invalidar.

> [!NOTE]
> Las plantillas base predefinidas que se proporcionan en Microsoft Teams se pueden duplicar pero no editar.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adoptar Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canales: <ul><li>General</li> <li>Anuncios</li> <li>Esquina Campeones</li> <li>Formularios de equipo</li></ul> Aplicaciones: <ul><li>Wiki</li>  <li>Calendario</li> |
| Administrar un proyecto |`com.microsoft.teams.template.ManageAProject`| Canales: <ul><li>General</li> <li>Anuncios</li> <li>Recursos</li> <li>Planeación</li></ul> Aplicaciones:<ul><li>Wiki</li><li>OneNote</li><li>Planner</li><li>Listas</li>  </ul> |
| Administrar un evento|`com.microsoft.teams.template.ManageAnEvent` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Budget</li> <li>Contenido</li><li>Logística</li> <li>Planeación</li> <li> Marketing y relaciones públicas</li></ul> Aplicaciones:<ul><li>Wiki</li><li>Sitio web</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li> <li>Ideas de empleados</li> <li>Issue Reporter</li></ul> |
|Incorporar empleados|`com.microsoft.teams.template.OnboardEmployees` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Chat de empleados</li> <li>Aprendizaje</li></ul>Aplicaciones:<ul><li>Wiki</li><li>Comunidades</li><li>Planner</li><li>Ideas de empleados</li></ul>|
|Organizar el servicio de ayuda| `com.microsoft.teams.template.OrganizeHelpDesk`|Canales:<ul><li>General</li><li>Anuncios</li><li>Preguntas más frecuentes</li></ul>Aplicaciones:<ul><li>Wiki</li><li>OneNote</li><li>Planner </li><li>Elogio</li><li>Issue Reporter</li></ul> |
| Atención al paciente| `healthcareWard`| Canales:<ul><li>General</li><li>Anuncios</li><li>Reuniones</li><li>Rondas</li><li>Personal</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas  </li><li>Aprobaciones</li></ul>|
| Colaborar en eventos o crisis globales |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canales: <ul><li>General<li>Anuncios</li><li>Noticias del mundo</li><li>Continuidad empresarial</li><li>Trabajo remoto</li><li>Comunicación interna</li><li>Comms externos</li><li>Solicitud de aprobaciones</li><li>Quejas de clientes</li><li>Kudos</li><li>Actualización ejecutiva</li></ul>Aplicaciones: <ul><li>Elogio</li><li>Wiki</li><li>Sitio web</li><li>Planner</li><li>Issue Reporter</li></ul>|
|Sucursal bancaria| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canales: <ul><li>General<li>Anuncios</li><li>Reuniones</li><li>Reuniones de clientes</li><li>Solicitud de aprobaciones </li><li>Coaching</li><li>Desarrollo de aptitudes</li><li>Procesamiento de préstamo</li><li>Quejas de clientes</li><li>Kudos</li><li>Cosas divertidas</li><li>Cumplimiento</li></ul>Aplicaciones:<ul><li>Elogio </li><li>Issue Reporter</li></ul>|
|Respuesta a incidentes| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canales: <ul><li>General<li>Anuncios</li><li>Logística</li><li>Planeación</li><li>Recuperación</li><li>Urgente</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li> <li>Aprobaciones</li> <li>Inspección</li> </ul>|
|Hospital| `healthcareHospital` |Canales: <ul><li>General</li><li>Anuncios</li><li>Cumplimiento</li><li>Custodia</li><li>Recursos humanos</li><li>Farmacia</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas  </li></ul>|
|Organizar una tienda| `retailStore` |Canales: <ul><li>General<li>Cambio de turno</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Planner</li></ul>|
|Calidad y seguridad |`com.microsoft.teams.template.QualitySafety`|Canales: <ul><li>General<li>Anuncios</li><li>Línea 1</li><li>Línea 2</li><li>Línea 3</li><li>Seguridad</li><li>Aprendizaje</li><li>Mantenimiento</li><li>Cosas divertidas</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Planner</li> <li>Issue Reporter</li> <li>Inspección</li> </ul>|
|Retail para administradores| `retailManagerCollaboration` |Canales: <ul><li>General<li>Operaciones</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Planner</li></ul>|
||||

Para obtener más información sobre las categorías de plantilla, vea las siguientes categorías:

- [Plantillas financieras](financial-teams-templates-in-the-admin-console.md)
- [Plantillas generales](general-teams-templates-in-the-admin-console.md)
- [Plantillas de gobierno](government-teams-templates-in-the-admin-console.md)
- [Plantillas de atención sanitaria](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Plantillas de fabricación](manufacturing-teams-templates-in-the-admin-console.md)
- [Plantillas de retail](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Límites de tamaño de plantilla

Las plantillas están limitadas a un número específico de canales, pestañas y aplicaciones.

 > [!Note]
 > Puede agregar más canales, pestañas y aplicaciones al equipo después de crearlo a partir de una plantilla.

|Característica | Límite|
|-|-|
|Canales por plantilla | 15 |
|Fichas por canal en una plantilla | 20 |
|Aplicaciones por plantilla | 50|
|||

Vea [Límites y especificaciones de Teams](limits-specifications-teams.md) para obtener más información.

## <a name="manage-templates-in-powershell"></a>Administrar plantillas en PowerShell

Use los siguientes cmdlts para administrar las plantillas en PowerShell.

- [Get-CsTeamTemplate](https://docs.microsoft.com/powershell/module/teams/get-csteamtemplate?view=teams-ps) 
- [Get-CsTeamTemplateList](https://docs.microsoft.com/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](https://docs.microsoft.com/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](https://docs.microsoft.com/powershell/module/teams/remove-csteamtemplate?view=teams-ps) 
- [Update-CsTeamTemplate](https://docs.microsoft.com/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-topics"></a>Temas relacionados

- [Crear una plantilla de equipo personalizada](create-a-team-template.md)
- [Crear una plantilla de equipo a partir de una plantilla de equipo existente](create-template-from-existing-template.md)
- [Crear una plantilla a partir de un equipo existente](create-template-from-existing-team.md)
