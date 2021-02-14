---
title: Usar plantillas de Teams en el centro de administración
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
description: Aprenda a usar las plantillas de Teams para crear espacios de colaboración con canales para distintos temas mediante plantillas preinstaladas.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ad35b874f3f11a7e71d61c63cb90a1945c7cc85
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662655"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>Introducción a las plantillas de Teams en el centro de administración

**Las plantillas personalizadas aún no son compatibles con los clientes educativos.**

> [!NOTE]
> Actualmente, las plantillas de Teams no admiten la creación de canales privados. La creación de canales privados no se incluye en las definiciones de plantillas.

Las plantillas de Teams son definiciones predefinidas de la estructura de un equipo diseñadas en torno a una necesidad empresarial o un proyecto. Use plantillas predefinidas o cree su propia plantilla. Las plantillas de Teams le permiten crear rápidamente espacios de colaboración enriquecidos con canales para distintos temas y preinstalar aplicaciones para extraer contenido y servicios fundamentales. Las plantillas de Teams proporcionan una estructura de equipo predefinida que puede ayudarle a crear fácilmente equipos coherentes en toda su organización. Actualmente puede crear un equipo a partir de una plantilla en Teams o mediante [Microsoft Graph.](get-started-with-teams-templates.md)

En este artículo se describen las propiedades que se pueden definir en las plantillas, qué tipos de plantillas base son y cómo puede usar algunas solicitudes de ejemplos para crear un equipo a partir de una plantilla.

Este artículo es para usted si es responsable de planear, implementar y administrar varios equipos en toda la organización.

## <a name="teams-template-capabilities"></a>Capacidades de las plantillas de Teams

La mayoría de las propiedades de un equipo se incluyen y se admiten con plantillas. Pero hay algunas propiedades y características que actualmente no son compatibles. La tabla siguiente proporciona un resumen rápido de lo que se incluye y lo que no se incluye en las plantillas de Teams.

| **Propiedades de equipo admitidas por plantillas de Teams** | **Las propiedades del equipo aún no son compatibles con las plantillas de Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla base | Membresía de equipo |
| Nombre del equipo | Imagen del equipo |
| Descripción del equipo | Configuración de canales |
| Visibilidad del equipo (pública o privada) | Conectores |
| Configuración del equipo (por ejemplo, menciones de miembros, invitados o @) | Archivos y contenido |
| Canal de Autofavorite | |
| Aplicación instalada | |
| Pestañas ancladas | |

> [!NOTE]
> Agregaremos más funcionalidades de plantillas en futuras versiones de Microsoft Teams, así que vuelva a comprobar la información más actualizada sobre las propiedades compatibles.

## <a name="what-are-base-template-types"></a>Qué son los tipos de plantillas base

Los tipos de plantillas base son plantillas especiales que Microsoft ha creado para sectores específicos. Estas plantillas base suelen contener aplicaciones de propiedad que no están disponibles en la tienda de aplicaciones.

Una vez definido un tipo de plantilla base, puede extender o invalidar estas plantillas especiales con propiedades adicionales que quiera especificar. Algunos tipos de plantilla base contienen propiedades que no se pueden anular.

> [!NOTE]
> Las plantillas base predefinidas que se proporcionan en Microsoft Teams se pueden duplicar, pero no editar.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adoptar Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canales: <ul><li>General</li> <li>Anuncios</li> <li>Esquina de campeones</li> <li>Formularios de equipo</li></ul> Aplicaciones: <ul><li>Wiki</li>  <li>Calendario</li> |
| Administrar un proyecto |`com.microsoft.teams.template.ManageAProject`| Canales: <ul><li>General</li> <li>Anuncios</li> <li>Recursos</li> <li>Planeación</li></ul> Aplicaciones:<ul><li>Wiki</li><li>OneNote</li><li>Planner</li><li>Listas</li>  </ul> |
| Administrar un evento|`com.microsoft.teams.template.ManageAnEvent` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Budget</li> <li>Contenido</li><li>Logística</li> <li>Planeación</li> <li> Marketing y relaciones públicas</li></ul> Aplicaciones:<ul><li>Wiki</li><li>Sitio web</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Incorporar empleados|`com.microsoft.teams.template.OnboardEmployees` | Canales: <ul><li>General</li> <li>Anuncios</li> <li>Chat de empleado</li> <li>Aprendizaje</li></ul>Aplicaciones:<ul><li>Wiki</li><li>Comunidades</li><li>Planner</li></ul>|
|Organizar el servicio de ayuda| `com.microsoft.teams.template.OrganizeHelpDesk`|Canales:<ul><li>General</li><li>Anuncios</li><li>Preguntas más frecuentes</li></ul>Aplicaciones:<ul><li>Wiki</li><li>OneNote</li><li>Planner </li><li>Elogiar</li></ul> |
| Colaborar en la atención al paciente| `healthcareWard`| Canales:<ul><li>General</li><li>Anuncios</li><li>Garabatos</li><li>Redondear</li><li>Empleados</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas  </li></ul>|
| Colaborar en eventos o crisis globales |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canales: <ul><li>General<li>Anuncios</li><li>Noticias internacionales</li><li>Continuidad empresarial</li><li>Trabajo remoto</li><li>Comunicación interna</li><li>Comms externos</li><li>Solicitud de aprobaciones</li><li>Quejas de clientes</li><li>Kudos</li><li>Actualización ejecutiva</li></ul>Aplicaciones: <ul><li>Elogiar</li><li>Wiki</li><li>Sitio web</li><li>Planner</li></ul>|
|Colaborar en una rama de bancos| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canales: <ul><li>General<li>Anuncios</li><li>Garabatos</li><li>Reuniones de clientes</li><li>Solicitud de aprobación </li><li>Entrenador</li><li>Desarrollo de aptitudes</li><li>Procesamiento del préstamo</li><li>Quejas de clientes</li><li>Kudos</li><li>Cosas divertidas</li><li>Cumplimiento</li></ul>Aplicaciones:<ul><li>Elogiar </li></ul>|
|Coordinar respuesta a incidentes| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canales: <ul><li>General<li>Anuncios</li><li>Logística</li><li>Planeación</li><li>Recuperación</li><li>Urgente</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital| `healthcareHospital` |Canales: <ul><li>General</li><li>Anuncios</li><li>Cumplimiento</li><li>Descúyal</li><li>Recursos humanos</li><li>Clínica</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas  </li></ul>|
|Organizar una tienda| `retailStore` |Canales: <ul><li>General<li>Mayús handoff</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Planner</li></ul>|
|Calidad y seguridad |`com.microsoft.teams.template.QualitySafety`|Canales: <ul><li>General<li>Anuncios</li><li>Línea 1</li><li>Línea 2</li><li>Línea 3</li><li>Seguridad</li><li>Aprendizaje</li><li>Mantenimiento</li><li>Cosas divertidas</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Planner</li></ul>|
|Comercio al por menor: colaboración del administrador| `retailManagerCollaboration` |Canales: <ul><li>General<li>Operations</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Planner</li></ul>|
||||

Para obtener más información sobre las categorías de plantilla, vea las siguientes categorías:

- [Plantillas financieras](financial-teams-templates-in-the-admin-console.md)
- [Plantillas generales](general-teams-templates-in-the-admin-console.md)
- [Plantillas gubernamentales](government-teams-templates-in-the-admin-console.md)
- [Plantillas sanitarias](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Plantillas de fabricación](manufacturing-teams-templates-in-the-admin-console.md)
- [Plantillas comerciales](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Límites de tamaño de plantilla

Las plantillas se limitan a un número específico de canales, fichas y aplicaciones.

 > [!Note]
 > Puede agregar más canales, fichas y aplicaciones al equipo después de crearlos a partir de una plantilla.

|Característica | Límite|
|-|-|
|Canales por plantilla | 15 |
|Pestañas por canal en una plantilla | 20 |
|Aplicaciones por plantilla | 50|
|||

Consulte [los límites y las especificaciones de Teams](limits-specifications-teams.md) para obtener más información.

## <a name="related-topics"></a>Temas relacionados

- [Crear una plantilla de equipo personalizada](create-a-team-template.md)
- [Crear una plantilla de equipo a partir de una plantilla de equipo existente](create-template-from-existing-template.md)
- [Crear una plantilla de un equipo existente](create-template-from-existing-team.md)
