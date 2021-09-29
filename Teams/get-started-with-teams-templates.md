---
title: Introducción a las plantillas de equipo con Microsoft Graph
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
description: Obtenga información sobre las plantillas de equipo que solo están disponibles con Microsoft Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e570faff4ec7138457f7cd52e101a0a3632d64d2
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991119"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Introducción a las plantillas de equipo con Microsoft Graph

> [!NOTE]
> Actualmente, las plantillas de equipo no admiten la creación de canales privados. La creación de canales privados no se incluye en las definiciones de plantilla.

Una plantilla de equipo en Microsoft Teams es una definición de la estructura de un equipo diseñada en torno a una necesidad empresarial o un proyecto. Con las plantillas de equipo, puede crear espacios de colaboración enriquecidos de forma rápida y sencilla con configuraciones predefinidas, canales y aplicaciones. Las plantillas de equipo pueden ayudarle a implementar equipos coherentes en toda la organización.

Con Microsoft Graph, usa las plantillas de equipo predefinidas que se incluyen con Teams para crear equipos. En este artículo, aprenderá sobre las propiedades que se pueden definir en las plantillas y las plantillas que solo están disponibles con Microsoft Graph.

Este artículo es para usted si:

- Responsable de planear, implementar y administrar varios equipos en toda la organización<br>
- Un desarrollador que quiera crear mediante programación un equipo con canales y aplicaciones predefinidos

## <a name="team-template-capabilities"></a>Capacidades de plantilla de equipo

La mayoría de las propiedades de un equipo se incluyen y son compatibles con las plantillas. Pero hay algunas propiedades y características que no son compatibles actualmente. Este es un resumen rápido de lo que se incluye y lo que no se incluye en las plantillas de equipo.

| **Propiedades de equipo compatibles con plantillas de equipo** | **Las propiedades del equipo aún no son compatibles con las plantillas de equipo** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla | Membresía de equipo |
| Nombre del equipo | Imagen del equipo |
| Descripción del equipo | Configuración del canal |
| Visibilidad del equipo (público o privado) | Conectores |
| Configuración del equipo (por ejemplo, miembro, invitado, @ menciones) | Archivos y contenido |
| Canal auto-favorito | |
| Aplicación instalada | |
| Pestañas ancladas | |

> [!NOTE]
> Agregaremos más capacidades de plantilla en futuras versiones de Microsoft Teams, así que vuelva a comprobar la información más actualizada sobre las propiedades compatibles.

## <a name="pre-built-templates"></a>Plantillas predefinidas

Las plantillas de equipo predefinidas son plantillas que hemos creado para sectores específicos. Estas son las plantillas predefinidas que solo están disponibles con Microsoft Graph.

| Tipo de plantilla | TemplateId | Propiedades que vienen con esta plantilla |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | No hay aplicaciones ni propiedades adicionales |
| Educación -<br>Equipo de clase | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Aplicaciones:<ul><li>OneNote Bloc de notas de clase (anclado a la **pestaña General)** </li><li>Aplicación Tareas (anclada a la **pestaña General)**</li></ul> Propiedades del equipo:<ul><li>Visibilidad del equipo establecida en **HiddenMembership** (no se puede invalidar)</li></ul> |
| Educación -<br>Equipo de docentes | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Aplicaciones:<ul><li>OneNote Bloc de notas para docentes (anclado a la **pestaña General)**</li></ul> |
|Educación -<br>Equipo de PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Aplicaciones:<ul><li>OneNote Bloc de notas plc (anclado a la **pestaña General)**</ul></li>|

> [!NOTE]
> Para obtener una lista de plantillas predefinidas que puede usar en el cliente de Teams y con Microsoft Graph, vea Introducción a las plantillas de grupo en el Centro de administración de [Teams.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las plantillas de grupo en el centro Teams administración](get-started-with-teams-templates-in-the-admin-console.md)
- [Crear un equipo](/graph/api/team-post?view=graph-rest-beta) (en vista previa)
- [Nuevo equipo](/powershell/module/teams/New-Team?view=teams-ps)
