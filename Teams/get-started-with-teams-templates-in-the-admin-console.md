---
title: Usar plantillas de Teams para crear un nuevo equipo
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
description: Aprenda a usar las plantillas de Teams para crear espacios de colaboración con canales para diferentes temas mediante las plantillas preinstaladas.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 618c1a2949dc00e1257e3fef56c41b3bf2be567c
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424660"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>Introducción a las plantillas de Teams en el centro de administración

[!INCLUDE [preview-feature](includes/preview-feature.md)]

**Las plantillas personalizadas aún no son compatibles con los clientes de EDU.**

> [!NOTE]
> Las plantillas de Teams actualmente no admiten la creación de canales privados. La creación de canales privados no se incluye en las definiciones de plantilla.

Las plantillas de Teams son definiciones preconstruidas de una estructura de equipo diseñada según una necesidad o un proyecto empresarial. Use plantillas predefinidas o cree su propia plantilla. Las plantillas de Teams le permiten crear rápidamente espacios de colaboración enriquecidos con canales para diferentes temas y Preinstalar aplicaciones para extraer contenido y servicios de misión crítica. Las plantillas de Teams proporcionan una estructura de equipo predefinida que le puede ayudar a crear fácilmente equipos coherentes en toda la organización. Por el momento, puede crear un equipo a partir de una plantilla en Teams o con [Microsoft Graph](get-started-with-teams-templates.md).

En este artículo se describen las propiedades que se pueden definir en plantillas, qué son los tipos de plantilla base y cómo puede usar algunas solicitudes de ejemplo para crear un equipo a partir de una plantilla.

Este artículo le interesa si es responsable de planear, implementar y administrar varios equipos en la organización.

## <a name="teams-template-capabilities"></a>Capacidades de las plantillas de Teams

La mayoría de las propiedades de un equipo están incluidas y son compatibles con las plantillas. Sin embargo, hay algunas propiedades y características que actualmente no se admiten. En la tabla siguiente se proporciona un resumen rápido de lo que se incluye y lo que no se incluye en las plantillas de Teams.

| **Propiedades del equipo admitidas por las plantillas de Teams** | **Las propiedades del equipo aún no son compatibles con las plantillas de Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla base | Membresía de equipo |
| Nombre del equipo | Imagen de equipo |
| Descripción del equipo | Configuración del canal |
| Visibilidad del equipo (pública o privada) | Conectores |
| Configuración del equipo (por ejemplo, miembro, invitado, @ menciones) | Archivos y contenido |
| Canal autofavorito | |
| Aplicación instalada | |
| Pestañas ancladas | |

> [!NOTE]
> Agregaremos más capacidades de plantilla en versiones futuras de Microsoft Teams, así que vuelva a consultar la información más actualizada sobre las propiedades admitidas.

## <a name="what-are-base-template-types"></a>Qué son los tipos de plantilla base

Los tipos de plantillas base son plantillas especiales que Microsoft creó para sectores específicos. Estas plantillas básicas a menudo contienen aplicaciones propias que no están disponibles en la tienda de aplicaciones.

Una vez que se define un tipo de plantilla base, puede extender o invalidar estas plantillas especiales con propiedades adicionales que le gustaría especificar. Algunos tipos de plantillas base contienen propiedades que no se pueden reemplazar.

> [!NOTE]
> Las plantillas básicas predefinidas proporcionadas en Microsoft Teams se pueden duplicar, pero no editar.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ |----|----------------------------------------------------- |
| Adopción de Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canales <ul><li>General</li> <li>Anuncios</li> <li>La esquina de los campeones</li> <li>Formularios de equipo</li></ul> Phone <ul><li>Wiki</li>  <li>Calendario</li> |
| Administrar un proyecto |`com.microsoft.teams.template.ManageAProject`| Canales <ul><li>General</li> <li>Anuncios</li> <li>Recursos</li> <li>Planeación</li></ul> Phone<ul><li>Wiki</li><li>OneNote</li></ul> |
| Administrar un evento|`com.microsoft.teams.template.ManageAnEvent` | Canales <ul><li>General</li> <li>Anuncios</li> <li>Budget</li> <li>Contenido</li><li>Logística</li> <li>Planeación</li> <li> Marketing y PR</li></ul> Phone<ul><li>Wiki</li><li>Página</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Empleados de la placa|`com.microsoft.teams.template.OnboardEmployees` | Canales <ul><li>General</li> <li>Anuncios</li> <li>Chat de empleados</li> <li>Aprendizaje</li></ul>Phone<ul><li>Wiki</li><li>Comunitarios</li></ul>|
|Organizar el Departamento de soporte técnico| `com.microsoft.teams.template.OrganizeHelpDesk`|Canales<ul><li>General</li><li>Anuncios</li><li>Preguntas más frecuentes</li></ul>Phone<ul><li>Wiki</li><li>OneNote</li></ul> |
| Colaborar en el cuidado del paciente| `healthcareWard `| Canales<ul><li>General</li><li>Anuncios</li><li>Huddles</li><li>Hacia</li><li>Personal</li><li>Aprendizaje</li></ul> Phone <ul><li>Wiki</li>|
| Colaborar en crisis global o evento |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canales <ul><li>General<li>Anuncios</li><li>Noticias mundiales</li><li>Continuidad empresarial</li><li>Trabajo remoto</li><li>Comunicaciones internas</li><li>Comunicaciones externas</li><li>Quejas de los clientes</li><li>Kudos</li><li>Actualización Ejecutiva</li></ul>Phone <ul><li>Elogio</li><li>Wiki</li><li>Página</li></ul>|
|Colaborar dentro de una sucursal bancaria| `com.microsoft.teams.template.CollaborateWithinABankBranch `|Canales <ul><li>General<li>Anuncios</li><li>Huddles</li><li>Reuniones de clientes</li><li>Tren</li><li>Desarrollo de competencias</li><li>Procesamiento de préstamos</li><li>Quejas de los clientes</li><li>Kudos</li><li>Cosas divertidas</li><li>Cumplimiento</li></ul>|
|Coordinar la respuesta a incidentes| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canales <ul><li>General<li>Anuncios</li><li>Logística</li><li>Planeación</li><li>Recuperar</li><li>Urgente</li></ul> Phone <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital| `healthcareHospita`cuenta |Canales <ul><li>General<li>Anuncios</li><li>Cumplimiento</li><li>Private</li><li>Recursos humanos</li><li>Pertenecie</li></ul> Phone <ul><li>Wiki</li></ul>|
|Organizar un almacén| `retailStore` |Canales <ul><li>General<li>Transición de turno</li><li>Aprendiendo</li></ul> Phone <ul><li>Wiki</li></ul>|
|Calidad y seguridad |`com.microsoft.teams.template.QualitySafety`|Canales <ul><li>General<li>Anuncios</li><li>Línea 1</li><li>Línea 2</li><li>Línea 3</li><li>Opera</li><li>Aprendizaje</li><li>Mantenimiento</li><li>Cosas divertidas</li></ul> Phone <ul><li>Wiki</li></ul>|
|Colaboración minorista-Gerente| `retailManagerCollaboration` |Canales <ul><li>General<li>Operations</li><li>Aprendiendo</li></ul> Phone <ul><li>Wiki</li></ul>|
||||

Para obtener más información acerca de las categorías de plantillas, vea las categorías siguientes:

- [Plantillas financieras](financial-teams-templates-in-the-admin-console.md)
- [Plantillas generales](general-teams-templates-in-the-admin-console.md)
- [Plantillas gubernamentales](government-teams-templates-in-the-admin-console.md)
- [Plantillas de asistencia sanitaria](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Plantillas de fabricación](manufacturing-teams-templates-in-the-admin-console.md)
- [Plantillas comerciales](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Límites de tamaño de plantilla

Las plantillas se limitan a un número específico de canales, pestañas y aplicaciones.

 > [!Note]
 > Puede agregar más canales, pestañas y aplicaciones al equipo después de que se haya creado a partir de una plantilla.

|Característica | Límite|
|-|-|
|Canales por plantilla | 4,5 |
|Pestañas por canal en una plantilla | veinte |
|Aplicaciones por plantilla | 50|
|||

Para obtener más información [, consulte límites y especificaciones de Teams](limits-specifications-teams.md) .

## <a name="related-topics"></a>Temas relacionados

- [Crear una plantilla de equipo personalizada](create-a-team-template.md)
- [Crear una plantilla de equipo a partir de una plantilla de equipo existente](create-template-from-existing-template.md)
- [Crear una plantilla a partir de un equipo existente](create-template-from-existing-team.md)
