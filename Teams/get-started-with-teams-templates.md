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
- m365-frontline
description: Obtenga información sobre las plantillas de equipo que solo están disponibles con Microsoft Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4251aa0293665b6fd41c66e352ca9c595378259
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397241"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Introducción a las plantillas de equipo con Microsoft Graph

> [!NOTE]
> Las plantillas de equipo actualmente no admiten la creación de canales privados. La creación de canales privados no se incluye en las definiciones de plantilla.

Una plantilla de equipo en Microsoft Teams es una definición de la estructura de un equipo diseñada en torno a una necesidad empresarial o un proyecto. Con las plantillas de equipo, puede crear espacios de colaboración enriquecidos de forma rápida y sencilla con configuraciones predefinidas, canales y aplicaciones. Las plantillas de equipo pueden ayudarle a implementar equipos coherentes en toda la organización.

Con Microsoft Graph, puede [crear sus propias plantillas](/graph/api/resources/teamtemplate?view=graph-rest-beta) o usar las plantillas de equipo predefinidas que se incluyen en Teams para crear equipos. En este artículo, obtendrá información sobre las propiedades que se pueden definir en las plantillas y las plantillas predefinidas que solo están disponibles con Microsoft Graph.

Este artículo es para usted si es:

- Responsable de planear, implementar y administrar varios equipos en toda la organización<br>
- Un desarrollador que desea crear mediante programación un equipo con canales y aplicaciones predefinidos

## <a name="team-template-capabilities"></a>Capacidades de plantillas de equipo

La mayoría de las propiedades de un equipo se incluyen y son compatibles con las plantillas. Pero hay algunas propiedades y características que no son compatibles actualmente. Este es un resumen rápido de lo que se incluye y lo que no se incluye en las plantillas de equipo.

| **Propiedades de equipo admitidas por plantillas de equipo** | **Las propiedades de equipo aún no son compatibles con las plantillas de equipo** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla | Membresía de equipo |
| Nombre del equipo | Imagen del equipo |
| Descripción del equipo | Configuración de canal |
| Visibilidad del equipo (pública o privada) | Conectores |
| Configuración del equipo (por ejemplo, miembro, invitado, @ menciones) | Archivos y contenido |
| Canal favorito automático | |
| Aplicación instalada | |
| Pestañas ancladas | |

> [!NOTE]
> Agregaremos más funcionalidades de plantilla en futuras versiones de Microsoft Teams, así que vuelva a comprobar la información más actualizada sobre las propiedades compatibles.

## <a name="pre-built-templates"></a>Plantillas predefinidas

Las plantillas de equipo predefinidas son plantillas que hemos creado para sectores específicos. Estas son las plantillas predefinidas que solo están disponibles con Microsoft Graph.

| Tipo de plantilla | TemplateId | Propiedades que vienen con esta plantilla |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | No hay aplicaciones y propiedades adicionales |
| Educación -<br>Equipo de clase | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Aplicaciones:<ul><li>Bloc de notas de clase de OneNote (anclado a la pestaña **General** ) </li><li>Aplicación Tareas (anclada a la pestaña **General** )</li></ul> Propiedades del equipo:<ul><li>Visibilidad del equipo establecida en **HiddenMembership** (no se puede anular)</li></ul> |
| Educación -<br>Equipo de personal | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Aplicaciones:<ul><li>Bloc de notas para docentes de OneNote (anclado a la pestaña **General** )</li></ul> |
|Educación -<br>Equipo de PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Aplicaciones:<ul><li>Bloc de notas de PLC de OneNote (anclado a la pestaña **General** )</ul></li>|

> [!NOTE]
> Para obtener una lista de plantillas predefinidas que puede usar en el cliente de Teams y en Microsoft Graph, consulte [Introducción a las plantillas de equipo en el Centro de administración de Teams](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las plantillas de equipo en el centro de administración de Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Crear un equipo](/graph/api/team-post?view=graph-rest-beta) (en versión preliminar)
- [Nuevo equipo](/powershell/module/teams/New-Team?view=teams-ps)
