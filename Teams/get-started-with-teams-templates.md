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
description: Obtenga información sobre cómo usar las plantillas de Teams en Microsoft Graph para crear espacios de colaboración con canales para diferentes temas y Preinstalar aplicaciones para proporcionar contenido y servicios.
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
> Las plantillas de Teams actualmente no admiten la creación de canales privados. La creación de canales privados no se incluye en las definiciones de plantilla.

Las plantillas de Teams son definiciones preconstruidas de una estructura de equipo diseñada según una necesidad o un proyecto empresarial. Puede [crear su propia plantilla en la consola de administración](get-started-with-teams-templates-in-the-admin-console.md). Con Microsoft Graph, se usan las plantillas predefinidas. Puede usar las plantillas de Teams para crear rápidamente espacios de colaboración enriquecidos con canales para diferentes temas y para preinstalar aplicaciones para extraer contenido y servicios de misión crítica. Las plantillas de Teams proporcionan una estructura de equipo predefinida que le puede ayudar a crear fácilmente equipos coherentes en toda la organización.

En este artículo, explicaremos las propiedades que se pueden definir en plantillas, qué son los tipos de plantilla base y cómo puede usar algunas solicitudes de ejemplos para crear un equipo a partir de una plantilla.

Este artículo le interesa si:

- Responsable de planear, implementar y administrar varios equipos en la organización<br>
- Un desarrollador que desea crear mediante programación un equipo con canales y aplicaciones predefinidos

## <a name="teams-template-capabilities"></a>Capacidades de las plantillas de Teams

La mayoría de las propiedades de un equipo están incluidas y son compatibles con las plantillas. Sin embargo, hay algunas propiedades y características que actualmente no se admiten. En la tabla siguiente se proporciona un resumen rápido de lo que se incluye y lo que no se incluye en las plantillas de Teams.

| **Propiedades del equipo admitidas por las plantillas de Teams** | **Las propiedades del equipo aún no son compatibles con las plantillas de Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla base | Membresía de equipo |
| Nombre del equipo | Imagen de equipo |
| Descripción del equipo | Configuración del canal |
| Visibilidad del equipo (pública o privada) | Conectores |
| Configuración del equipo (por ejemplo, miembro, invitado, @ menciones) | Archivos y contenido |
| Canal de favoritos automático | |
| Aplicación instalada | |
| Pestañas ancladas | |

> [!NOTE]
> Agregaremos más capacidades de plantilla en versiones futuras de Microsoft Teams, así que vuelva a consultar la información más actualizada sobre las propiedades admitidas.

## <a name="what-are-base-template-types"></a>Qué son los tipos de plantilla base

Los tipos de plantillas base son plantillas especiales que Microsoft creó para sectores específicos. Estas plantillas básicas a menudo contienen aplicaciones propias que no están disponibles en la tienda. Además, las plantillas básicas a menudo contienen propiedades de equipo que aún no se admiten individualmente en las plantillas de Teams. Aprenda a usar las [plantillas de equipo en Microsoft Graph](get-started-with-teams-templates.md).

Una vez que se define un tipo de plantilla base, puede extender o invalidar estas plantillas especiales con propiedades adicionales que le gustaría especificar. Algunos tipos de plantillas base contienen propiedades que no se pueden reemplazar.

De forma predeterminada, la plantilla base se establece en **estándar** , que no contiene ninguna aplicación de propiedad adicional ni propiedades especiales. A continuación se muestra la lista actual de tipos de plantillas base disponibles.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | No hay más aplicaciones ni propiedades |
| Educativo<br>Equipo de clase | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Phone<ul><li>Bloc de notas de clase de OneNote (anclado a la pestaña **General** ) </li><li>Aplicación tareas (anclada a la pestaña **General** )</li></ul> Propiedades del equipo:<ul><li>Visibilidad del equipo establecida en **HiddenMembership** (no se puede reemplazar)</li></ul> |
| Educativo<br>Equipo del personal | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Phone<ul><li>Bloc de notas para docentes de OneNote (anclado a la pestaña **General** )</li></ul> |
|Educativo<br>Equipo de PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Phone<ul><li>Bloc de notas PLC de OneNote (anclado a la pestaña **General** )</ul></li>|
| Anuales<br>Tienda | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canales<ul><li>Transición de turno</li><li>Aprendiendo</li></ul>Propiedades del equipo<ul><li>Visibilidad de equipo establecida como pública</li></ul>Permisos de miembro<ul><li>Evitar que los miembros creen, actualicen o quiten canales</li><li>Evitar que los miembros agreguen o quiten aplicaciones</li><li>Evitar que los miembros creen, actualicen o quiten conectores</li></ul> |
| Anuales<br>Colaboración de administrador | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canales<ul><li>Aprendiendo</li><li>Operations</li></ul>Propiedades del equipo:<ul><li>Visibilidad del equipo establecida en privado</li></ul>Permisos de miembro:<ul><li>Evitar que los miembros creen, actualicen o quiten canales</li><li>Evitar que los miembros agreguen o quiten aplicaciones</li><li>Evitar que los miembros creen, actualicen o quiten conectores</li></ul>|
| Healthcare<br>Hacia |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canales <ul><li>Anuncios\*</li><li>Huddles\*</li><li>Hacia</li><li>Personal\*</li><li>Aprendizaje\*</li></ul>\*Canales favoritos automáticos |
|Healthcare<br>Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canales<ul><li>Anuncios\*</li><li>Cumplimiento\*</li><li>Private</li><li>Recursos humanos</li></li><li>Pertenecie</li></ul>\*Canal de favoritos automáticos|
|||


Use las siguientes plantillas para crear equipos tanto en el cliente de Teams como en Microsoft Graph.


| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adopción de Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Canales <ul><li>General</li> <li>Anuncios</li> <li>La esquina de los campeones</li> <li>Formularios de equipo</li></ul> Phone <ul><li>Wiki</li>  <li>Calendario</li> |
| Administrar un proyecto |`com.microsoft.teams.template.`<br>`ManageAProject`| Canales <ul><li>General</li> <li>Anuncios</li> <li>Recursos</li> <li>Planeación</li></ul> Phone<ul><li>Wiki</li><li>OneNote</li></ul> |
| Administrar un evento|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Canales <ul><li>General</li> <li>Anuncios</li> <li>Budget</li> <li>Contenido</li><li>Logística</li> <li>Planeación</li> <li> Marketing y PR</li></ul> Phone<ul><li>Wiki</li><li>Página</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Empleados de la placa|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Canales <ul><li>General</li> <li>Anuncios</li> <li>Chat de empleados</li> <li>Aprendizaje</li></ul>Phone<ul><li>Wiki</li><li>Comunitarios</li></ul>|
|Organizar el Departamento de soporte técnico| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Canales<ul><li>General</li><li>Anuncios</li><li>Preguntas más frecuentes</li></ul>Phone<ul><li>Wiki</li><li>OneNote</li></ul> |
| Colaborar en el cuidado del paciente| `healthcareWard `| Canales<ul><li>General</li><li>Anuncios</li><li>Huddles</li><li>Hacia</li><li>Personal</li><li>Aprendizaje</li></ul> Phone <ul><li>Wiki</li>|
| Colaborar en crisis global o evento |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Canales <ul><li>General<li>Anuncios</li><li>Noticias mundiales</li><li>Continuidad empresarial</li><li>Trabajo remoto</li><li>Comunicaciones internas</li><li>Comunicaciones externas</li><li>Quejas de los clientes</li><li>Kudos</li><li>Actualización Ejecutiva</li></ul>Phone <ul><li>Elogio</li><li>Wiki</li><li>Página</li></ul>|
|Colaborar dentro de una sucursal bancaria| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Canales <ul><li>General<li>Anuncios</li><li>Huddles</li><li>Reuniones de clientes</li><li>Tren</li><li>Desarrollo de competencias</li><li>Procesamiento de préstamos</li><li>Quejas de los clientes</li><li>Kudos</li><li>Cosas divertidas</li><li>Cumplimiento</li></ul>|
|Coordinar la respuesta a incidentes| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Canales <ul><li>General<li>Anuncios</li><li>Logística</li><li>Planeación</li><li>Recuperar</li><li>Urgente</li></ul> Phone <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital| `healthcareHospita`cuenta |Canales <ul><li>General<li>Anuncios</li><li>Cumplimiento</li><li>Private</li><li>Recursos humanos</li><li>Pertenecie</li></ul> Phone <ul><li>Wiki</li></ul>|
|Organizar un almacén| `retailStore` |Canales <ul><li>General<li>Transición de turno</li><li>Aprendiendo</li></ul> Phone <ul><li>Wiki</li></ul>|
|Calidad y seguridad |`com.microsoft.teams.`<br>`template.QualitySafety`|Canales <ul><li>General<li>Anuncios</li><li>Línea 1</li><li>Línea 2</li><li>Línea 3</li><li>Opera</li><li>Aprendizaje</li><li>Mantenimiento</li><li>Cosas divertidas</li></ul> Phone <ul><li>Wiki</li></ul>|
|Colaboración minorista-Gerente| `retailManagerCollaboration` |Canales <ul><li>General<li>Operations</li><li>Aprendiendo</li></ul> Phone <ul><li>Wiki</li></ul>|
||||

Para obtener más información, vea [Introducción a las plantillas de Teams en el centro de administración](get-started-with-teams-templates-in-the-admin-console.md) .

## <a name="related-topics"></a>Temas relacionados

- [Introducción a las plantillas de Teams en la consola de administración](get-started-with-teams-templates-in-the-admin-console.md)
- [Crear equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en versión preliminar)
- [Nuevo: equipo](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formación de administradores para Microsoft Teams](itadmin-readiness.md)