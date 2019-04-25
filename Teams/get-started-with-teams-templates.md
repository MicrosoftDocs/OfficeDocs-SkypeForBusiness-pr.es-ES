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
- Teams_ITAdmin_Help
description: Obtenga información sobre cómo usar las plantillas de equipos para crear un equipo con los canales de predefinidos.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b620f163f1dc071bde8a0ed43bf7fe546a9bc04a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245596"
---
# <a name="get-started-with-teams-templates"></a>Introducción a las plantillas de Teams 

Las plantillas de equipos son predefinidas definiciones de estructura de un equipo diseñado alrededor de un proyecto o necesidad empresarial. Puede usar las plantillas de equipos para crear rápidamente los espacios de colaboración con los canales para diferentes temas y preinstalación de aplicaciones que se van a extraer en servicios y contenido de misión crítica. Las plantillas de equipos proporcionan una estructura de equipo predefinidos que puede ayudarle a crear fácilmente los equipos coherentes en toda la organización. 

En este artículo, se explican las propiedades que pueden definirse en plantillas, qué plantilla base son tipos, y cómo puede usar algunas solicitudes para crear un equipo a partir de una plantilla de ejemplo.
 
En este artículo es para usted si es:

- Responsable de la planeación, implementación y administración de varios equipos en toda la organización<br>
- Un programador que deseen crear mediante programación un equipo con aplicaciones y canales predefinidos 

## <a name="teams-template-capabilities"></a>Capacidades de la plantilla de los equipos

Mayoría de las propiedades en un equipo se incluyen y compatible con las plantillas. Sin embargo, hay algunas propiedades y características que no son compatibles actualmente. En la siguiente tabla proporciona un resumen rápido de lo que se incluye y qué no se incluye en las plantillas de equipos.

| **Propiedades de equipo compatibles con las plantillas de equipos** | **Propiedades de equipo aún no admitidas por las plantillas de equipos** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla de base | Miembros del equipo |
| Nombre de equipo | Imagen del equipo |
| Descripción de equipo | Opciones de canal |
| Visibilidad de equipo (pública o privada) | Conectores |
| Configuración del equipo (por ejemplo, miembro, invitado, @ menciones) | Los archivos y contenido |
| Canal de favorito de automático | |
| Aplicación instalada | |
| Fichas ancladas | | 

> [!NOTE]
> Se podrá ser agregar más capacidades de plantilla en futuras versiones de Microsoft Teams, por lo que vuelva a consultar para la información más actualizada sobre propiedades compatibles con.

## <a name="what-are-base-template-types"></a>¿Qué son los tipos de plantilla base?

Tipos de plantilla de base son plantillas especiales que Microsoft ha creado para sectores específicos. Estas plantillas bases a menudo contienen propietarias aplicaciones que no están disponibles en las propiedades de almacenamiento y del equipo que no son compatibles todavía individualmente en las plantillas de equipos.

Una vez que se define un tipo de plantilla base, puede ampliar o reemplazar estas plantillas especiales con propiedades adicionales que le gustaría usar para especificar. Pero algunos tipos de plantilla base contienen las propiedades que no se puede reemplazar. 

De forma predeterminada, la plantilla base se establece en **estándar** que no contiene propiedades especiales ni aplicaciones adicionales de su propiedad. A continuación está disponible la lista actual de tipos de plantilla de base.

| Tipo de plantilla de base | baseTemplateId | Propiedades que se incluyen con esta plantilla de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | No hay aplicaciones adicionales y propiedades |
| Educación-<br>Equipo de clase | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Aplicaciones:<ul><li>Bloc de notas de OneNote clase (anclado a la ficha **General** ) </li><li>Aplicación de las asignaciones (anclado a la ficha **General** )</li></ul> Propiedades de equipo:<ul><li>Visibilidad de equipo se establece en **HiddenMembership** (no se puede reemplazar)</li></ul> |
| Educación-<br>Equipo de personal | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Aplicaciones:<ul><li>Bloc de notas de OneNote personal (anclado a la ficha **General** )</li></ul> |
|Educación-<br>Equipo PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Aplicaciones:<ul><li>Bloc de notas de OneNote PLC (anclado a la ficha **General** )</ul></li>|
| Venta por menor-<br>Almacén | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canales de entrada:<ul><li>Entrega de MAYÚS</li><li>Recursos de aprendizaje</li></ul>Propiedades de equipo<ul><li>Visibilidad de equipo establecida en público</li></ul>Permisos de miembro<ul><li>Impedir que a los miembros de creación, actualización o eliminación de canales</li><li>Impedir que a los miembros de la adición o eliminación de aplicaciones</li><li>Impedir que a los miembros de creación, actualización o eliminación de los conectores</li></ul> |
| Venta por menor-<br>Colaboración de administrador | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canales de entrada:<ul><li>Entrega de MAYÚS</li><li>Recursos de aprendizaje</li></ul>Propiedades de equipo:<ul><li>Visibilidad de equipo establecida en privado</li></ul>Permisos de los miembros:<ul><li>Impedir que a los miembros de creación, actualización o eliminación de canales</li><li>Impedir que a los miembros de la adición o eliminación de aplicaciones</li><li>Impedir que a los miembros de creación, actualización o eliminación de los conectores</li></ul>|
| Healthcare-<br>Distrito |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canales de entrada: <ul><li>Anuncios\*</li><li>Huddles\*</li><li>Redondea hacia arriba</li><li>Personal\*</li><li>Recursos de aprendizaje\*</li></ul>\*Canales de automático favoritos |
|Healthcare-<br>Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canales de entrada:<ul><li>Anuncios\*</li><li>Cumplimiento de normas\*</li><li>Custodia</li><li>Recursos humanos</li></li><li>Farmacia</li></ul>\*Canal automático favoritos|
|||

> [!NOTE]
> Agregaremos más plantilla base de tipos de en futuras versiones de Microsoft Teams, por lo que verificación atrás para la información más actualizada sobre admite propiedades.


## <a name="related-topics"></a>Temas relacionados

- [Crear equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en la vista previa)
- [Nuevo equipo](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formación de administradores para Microsoft Teams](itadmin-readiness.md)
- [Introducción a las plantillas comerciales de Teams](get-started-with-retail-teams-templates.md)
- [Introducción a las plantillas para las organizaciones sanitarias de Teams](expand-teams-across-your-org/healthcare/healthcare-templates.md)
