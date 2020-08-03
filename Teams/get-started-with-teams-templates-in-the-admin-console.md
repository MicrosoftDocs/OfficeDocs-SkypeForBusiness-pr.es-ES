---
title: Usar las plantillas de Teams en la consola de administración
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 26f26e869758c06762167731068033acb1707135
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506479"
---
# <a name="get-started-with-teams-templates-in-the-teams-admin-console"></a>Introducción a las plantillas de Teams en la consola de administración de Teams

[!INCLUDE [template](includes/preview-feature.md)]

> [!NOTE]
> Las plantillas de Teams actualmente no admiten la creación de canales privados. La creación de canales privados no se incluye en las definiciones de plantilla.

Las plantillas de Teams son definiciones preconstruidas de una estructura de equipo diseñada según una necesidad o un proyecto empresarial. Use plantillas predefinidas o cree su propia plantilla. Las plantillas de Teams le permiten crear rápidamente espacios de colaboración enriquecidos con canales para diferentes temas y Preinstalar aplicaciones para extraer contenido y servicios de misión crítica. Las plantillas de Teams proporcionan una estructura de equipo predefinida que le puede ayudar a crear fácilmente equipos coherentes en toda la organización. Por el momento, puede usar una plantilla en la consola de administración o con [Microsoft Graph](get-started-with-teams-templates.md).

En este artículo, explicaremos las propiedades que se pueden definir en plantillas, qué son los tipos de plantilla base y cómo puede usar algunas solicitudes de ejemplo para crear un equipo a partir de una plantilla.

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

Los tipos de plantillas base son plantillas especiales que Microsoft creó para sectores específicos. Estas plantillas básicas a menudo contienen aplicaciones propias que están disponibles en la tienda de aplicaciones.

Una vez que se define un tipo de plantilla base, puede extender o invalidar estas plantillas especiales con propiedades adicionales que le gustaría especificar. Pero algunos tipos de plantillas base contienen propiedades que no se pueden reemplazar.

> [!NOTE]
> Las plantillas básicas predefinidas proporcionadas en Microsoft Teams se pueden duplicar, pero no editar.


| Tipo de plantilla base | Propiedades que vienen con esta plantilla base |
| ------------------ |----------------------------------------------------- |
| Adopción de Office 365 |  Canales <ul><li>General</li> <li>Anuncios</li> <li>La esquina de los campeones</li> <li>Formularios de equipo</li></ul> Phone <ul><li>Wiki</li>  <li>Calendario</li> |
| Administrar un proyecto | Canales <ul><li>General</li> <li>Anuncios</li> <li>Recursos</li> <li>Planeación</li></ul> Phone<ul><li>Wiki</li><li>OneNote</li></ul> |
| Administrar un evento | Canales <ul><li>General</li> <li>Anuncios</li> <li>Budget</li> <li>Contenido</li><li>Logística</li> <li>Planeación</li> <li> Marketing y PR</li></ul> Phone<ul><li>Wiki</li><li>Página</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Empleados de la placa | Canales <ul><li>General</li> <li>Anuncios</li> <li>Chat de empleados</li> <li>Aprendizaje</li></ul>Phone<ul><li>Wiki</li><li>Comunitarios</li>|</ul>
|Organizar el Departamento de soporte técnico| Canales<ul><li>General</li><li>Anuncios</li><li>Preguntas más frecuentes</li></ul>Phone<ul><li>Wiki</li><li>OneNote</li></ul> |
| Colaborar en el cuidado del paciente | Canales<ul><li>General</li><li>Anuncios</li><li>Huddles</li><li>Hacia</li><li>Personal</li><li>Aprendizaje</li></ul> Phone <ul><li>Wiki</li>|
| Colaborar en crisis global o evento |Canales <ul><li>General<li>Anuncios</li><li>Noticias mundiales</li><li>Continuidad empresarial</li><li>Trabajo remoto</li><li>Comunicaciones internas</li><li>Comunicaciones externas</li><li>Quejas de los clientes</li><li>Kudos</li><li>Actualización Ejecutiva</li></ul>Phone <ul><li>Elogio</li><li>Wiki</li><li>Página</li></ul>|
|Colaborar dentro de una sucursal bancaria |Canales <ul><li>General<li>Anuncios</li><li>Huddles</li><li>Reuniones de clientes</li><li>Tren</li><li>Desarrollo de competencias</li><li>Procesamiento de préstamos</li><li>Quejas de los clientes</li><li>Kudos</li><li>Cosas divertidas</li><li>Cumplimiento</li></ul>|
|Coordinar la respuesta a incidentes |Canales <ul><li>General<li>Anuncios</li><li>Logística</li><li>Planeación</li><li>Recuperar</li><li>Urgente</li></ul> Phone <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital |Canales <ul><li>General<li>Anuncios</li><li>Cumplimiento</li><li>> de Private/Li<li>Recursos humanos</li><li>Pertenecie</li></ul> Phone <ul><li>Wiki</li></ul>|
|Organizar un almacén |Canales <ul><li>General<li>Transición de turno</li><li>Aprendiendo</li></ul> Phone <ul><li>Wiki</li></ul>|
|Calidad y seguridad |Canales <ul><li>General<li>Anuncios</li><li>Línea 1</li><li>Línea 2</li><li>Línea 3</li><li>Opera</li><li>Aprendizaje</li><li>Mantenimiento</li><li>Cosas divertidas</li></ul> Phone <ul><li>Wiki</li></ul>|
|Colaboración minorista-Gerente |Canales <ul><li>General<li>Operations</li><li>Aprendiendo</li></ul> Phone <ul><li>Wiki</li></ul>|
|||

## <a name="related-topics"></a>Temas relacionados

- [Crear una plantilla de equipo](create-a-team-template.md)
- [Crear un equipo a partir de una plantilla de equipo existente](modify-existing-team-template.md)
- [Crear una plantilla a partir de un equipo existente](create-team-from-existing-team.md)