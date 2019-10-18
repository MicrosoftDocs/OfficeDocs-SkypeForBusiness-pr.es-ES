---
title: Introducción a las plantillas de Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/25/2019
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Aprenda a usar las plantillas de Teams para crear un equipo con canales predefinidos.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5832ccce69c9863e364f94c6e850f8d938ac162
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569569"
---
# <a name="get-started-with-teams-templates"></a>Introducción a las plantillas de Teams 

Las plantillas de Teams son definiciones preconstruidas de una estructura de equipo diseñada según una necesidad o un proyecto empresarial. Puede usar las plantillas de Teams para crear rápidamente espacios de colaboración enriquecidos con canales para diferentes temas y para preinstalar aplicaciones para extraer contenido y servicios de misión crítica. Las plantillas de Teams proporcionan una estructura de equipo predefinida que le puede ayudar a crear fácilmente equipos coherentes en toda la organización. 

En este artículo, explicaremos las propiedades que se pueden definir en plantillas, qué son los tipos de plantilla base y cómo puede usar algunas solicitudes de ejemplo para crear un equipo a partir de una plantilla.
 
Este artículo le interesa si:

- Responsable de planear, implementar y administrar varios equipos en la organización<br>
- Un desarrollador que desea crear mediante programación un equipo con canales y aplicaciones predefinidos 

## <a name="teams-template-capabilities"></a>Capacidades de las plantillas de Teams

La mayoría de las propiedades de un equipo están incluidas y son compatibles con las plantillas. Sin embargo, hay algunas propiedades y características que actualmente no se admiten. En la tabla siguiente se proporciona un resumen rápido de lo que se incluye y lo que no se incluye en las plantillas de Teams.

| **Propiedades del equipo admitidas por las plantillas de Teams** | **Las propiedades del equipo aún no son compatibles con las plantillas de Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla base | Pertenencia al equipo |
| Nombre del equipo | Imagen de equipo |
| Descripción del equipo | Configuración del canal |
| Visibilidad del equipo (pública o privada) | Los |
| Configuración del equipo (por ejemplo, miembro, invitado, @ menciones) | Archivos y contenido |
| Canal de favoritos automático | |
| Aplicación instalada | |
| Pestañas ancladas | | 

> [!NOTE]
> Agregaremos más capacidades de plantilla en versiones futuras de Microsoft Teams, así que vuelva a consultar la información más actualizada sobre las propiedades admitidas.

## <a name="what-are-base-template-types"></a>¿Qué son los tipos de plantilla básicos?

Los tipos de plantillas base son plantillas especiales que Microsoft creó para sectores específicos. Estas plantillas básicas a menudo contienen aplicaciones propias que no están disponibles en las propiedades del equipo y del almacén que aún no se admiten individualmente en las plantillas de Teams.

Una vez que se define un tipo de plantilla base, puede extender o invalidar estas plantillas especiales con propiedades adicionales que le gustaría especificar. Pero algunos tipos de plantillas base contienen propiedades que no se pueden reemplazar. 

De forma predeterminada, la plantilla base se establece en **estándar** , que no contiene ninguna aplicación de propiedad adicional ni propiedades especiales. A continuación se muestra la lista actual de tipos de plantillas base disponibles.

| Tipo de plantilla base | baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | No hay más aplicaciones ni propiedades |
| Educativo<br>Equipo de clase | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Phone<ul><li>Bloc de notas de clase de OneNote (anclado a la pestaña **General** ) </li><li>Aplicación tareas (anclada a la pestaña **General** )</li></ul> Propiedades del equipo:<ul><li>Visibilidad del equipo establecida en **HiddenMembership** (no se puede reemplazar)</li></ul> |
| Educativo<br>Equipo del personal | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Phone<ul><li>Bloc de notas para docentes de OneNote (anclado a la pestaña **General** )</li></ul> |
|Educativo<br>Equipo de PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Phone<ul><li>Bloc de notas PLC de OneNote (anclado a la pestaña **General** )</ul></li>|
| Anuales<br>Guarde | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canales<ul><li>Transición de turno</li><li>Aprendiendo</li></ul>Propiedades del equipo<ul><li>Visibilidad de equipo establecida como pública</li></ul>Permisos de miembro<ul><li>Evitar que los miembros creen, actualicen o quiten canales</li><li>Evitar que los miembros agreguen o quiten aplicaciones</li><li>Evitar que los miembros creen, actualicen o quiten conectores</li></ul> |
| Anuales<br>Colaboración de administrador | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canales<ul><li>Transición de turno</li><li>Aprendiendo</li></ul>Propiedades del equipo:<ul><li>Visibilidad del equipo establecida en privado</li></ul>Permisos de miembro:<ul><li>Evitar que los miembros creen, actualicen o quiten canales</li><li>Evitar que los miembros agreguen o quiten aplicaciones</li><li>Evitar que los miembros creen, actualicen o quiten conectores</li></ul>|
| Healthcare<br>Hacia |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canales <ul><li>Anuncios\*</li><li>Huddles\*</li><li>Hacia</li><li>Personal\*</li><li>Instrui\*</li></ul>\*Canales favoritos automáticos |
|Healthcare<br>Hospitales | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canales<ul><li>Anuncios\*</li><li>Respeto\*</li><li>Private</li><li>Recursos humanos</li></li><li>Pertenecie</li></ul>\*Canal de favoritos automáticos|
|||

> [!NOTE]
> Agregaremos más tipos de plantillas base en las futuras versiones de Microsoft Teams, así que vuelva a consultar la información más actualizada sobre las propiedades admitidas.


## <a name="related-topics"></a>Temas relacionados

- [Crear equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en versión preliminar)
- [Nuevo: equipo](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formación de administradores para Microsoft Teams](itadmin-readiness.md)
- [Introducción a las plantillas comerciales de Teams](get-started-with-retail-teams-templates.md)
- [Introducción a las plantillas para las organizaciones sanitarias de Teams](expand-teams-across-your-org/healthcare/healthcare-templates.md)
