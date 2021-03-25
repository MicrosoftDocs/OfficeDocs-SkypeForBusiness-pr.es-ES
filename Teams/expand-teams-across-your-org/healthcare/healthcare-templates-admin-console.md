---
title: Crear un equipo con plantillas de Teams para la atención sanitaria
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Use plantillas de Microsoft Teams en el Centro de administración o con Microsoft Graph para crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13b85818101e1c3d42ae6dc715274ac23453e178
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117878"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Crear un equipo con plantillas de Teams para la atención sanitaria

Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla al proporcionar una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.

Para las organizaciones sanitarias, las plantillas pueden ser especialmente eficaces, ya que proporcionan una estructura para que los usuarios se orienten sobre cómo usar Teams de forma eficaz. Las plantillas también permiten a los administradores implementar equipos coherentes en todas las organizaciones. Este artículo les ayudará si es el responsable de planear, implementar y administrar varios equipos en toda la organización sanitaria.

Elija un método para crear equipos con las plantillas de Teams para la atención sanitaria:

| Quién | Método de uso: |
| ---- | --------- |
| Administradores y profesionales de TI | [Use el Centro de administración de Teams](#use-the-teams-templates-in-the-teams-admin-center) para crear equipos basados en las plantillas de Teams para la atención sanitaria.|
| Desarrolladores e integradores de sistemas | [Use Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) crear equipos basados en las plantillas de Teams para la atención sanitaria. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Usar las plantillas de Teams en el Centro de administración de Teams

Los administradores de Microsoft Teams pueden usar el Centro de administración de Teams para crear equipos con las plantillas de Teams. Actualmente ofrecemos dos plantillas propias para la atención sanitaria que puede usar en varias situaciones. Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams en el Centro de administración](../../get-started-with-teams-templates-in-the-admin-console.md).

### <a name="collaborate-on-patient-care"></a>Colaborar en la atención al paciente

 Simplifique la comunicación y la colaboración sanitaria en una sala, dispensario o departamento. La plantilla puede usarse para facilitar la gestión de los pacientes y las necesidades operativas de una sala.

| Tipo de plantilla base |baseTemplateId| Propiedades que vienen con esta plantilla base |
| ------------------ |---|----------------------------------------------------- |
| Colaborar en la atención al paciente |`healthcareWard` | Canales:<ul><li>General</li><li>Anuncios</li><li>Reuniones</li><li>Rondas</li><li>Personal</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas</li></ul>|
||||

### <a name="hospital"></a>Hospital

Simplifique la comunicación y la colaboración entre varias salas, dispensario y departamentos dentro de un hospital. Esta plantilla incluye un conjunto de canales base para operaciones en los hospitales y puede ampliarse para incluir especialidades, según necesario.

| Tipo de plantilla base |baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------|-- |----------------------------------------------------- |
|Hospital|`healthcareHospital`|Canales: <ul><li>General</li><li>Anuncios</li><li>Cumplimiento</li><li>Custodia</li><li>Recursos humanos</li><li>Farmacia</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Usar las plantillas de Teams con Microsoft Graph

Los desarrolladores pueden usar Microsoft Graph para crear equipos con las plantillas de Teams. Actualmente ofrecemos dos plantillas propias para la atención sanitaria que puede usar en varias situaciones. Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams](../../get-started-with-teams-templates.md). Para obtener información sobre las plantillas de Teams y Microsoft Graph, vea [Información general de la API de Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) y [Tipo de recurso teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="ward-template"></a>Plantilla de sala

La plantilla de sala está pensada para la comunicación y la colaboración dentro de una sala, dispensario o departamento. La plantilla puede usarse para facilitar la gestión de los pacientes, así como las necesidades operativas de una sala. Por ejemplo, los anuncios de salas pueden publicarse en el canal *Anuncios* y los turnos pueden publicarse en el canal *Personal*. Si quiere simplificar sus operaciones de sala, esta plantilla es la adecuada.

|Tipo de plantilla base |baseTemplateId |Canales de plantilla de línea base|
|:--- |:---|:---|
|Atención sanitaria: sala | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Anuncios\* <br> Reuniones\* <br> Rondas\* <br> Personal\* <br> Aprendizaje\* |
|     | |         |

\* Marcado automáticamente como favorito

### <a name="hospital-template"></a>Plantilla de hospital

La plantilla de hospital está pensada para la comunicación y la colaboración entre varias salas, dispensarios y departamentos dentro un hospital. En esta plantilla se incluyen varios canales operativos, como *Anuncios*, *Custodia* y *Farmacia*, pero también le proporcionamos un script a continuación que amplía la plantilla con departamentos adicionales o canales de especialidades que puede agregar, eliminar o editar a su gusto. Por ejemplo, si tiene un departamento de *Endocrinología*, pero no necesita un canal para *Oftalmología*, el script puede adaptarse para incluir un canal de *Endocrinología* y quitar el canal de *Oftalmología*. Para evitar la saturación de notificaciones, recomendamos que estos canales de especialidades o basados en salas no se marquen como favoritos automáticamente. Los usuarios suelen marcar como favoritos los canales que encuentran relevantes.

|Tipo de plantilla base |baseTemplateId |Canales de plantilla de línea base|
|:--- |:---|:---|
|atención sanitaria: hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Anuncios\* <br> Cumplimiento\* <br> Custodia <br> Recursos humanos <br> Farmacia |
| | |  |

\* Marcado automáticamente como favorito 

### <a name="how-to-use-first-party-templates"></a>Cómo usar plantillas de terceros

Para usar estas plantillas, simplemente cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "estándar" a los TemplateID anteriores.  Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Los canales de la plantilla se crearán automáticamente en la pestaña General.

#### <a name="example-hospital-template-extension-script"></a>Ejemplo: script de extensión de plantilla de hospital

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-topics"></a>Temas relacionados

[Introducción a las plantillas de Teams](../../get-started-with-teams-templates.md)

[Introducción a Teams para organizaciones sanitarias](teams-in-hc.md)