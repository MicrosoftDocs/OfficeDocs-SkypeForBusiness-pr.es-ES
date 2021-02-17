---
title: Crear un equipo con las plantillas sanitarias de Teams
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
description: Use plantillas de Microsoft Teams en el centro de administración o con Microsoft Graph para crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260312"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Crear un equipo con las plantillas sanitarias de Teams

Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.

Para las organizaciones sanitarias, las plantillas pueden ser especialmente eficaces, ya que proporcionan una estructura para que los usuarios se orienten sobre cómo usar Teams de manera eficaz. Las plantillas también permiten a los administradores implementar equipos coherentes en todas sus organizaciones. Este artículo es para usted si es responsable de planear, implementar y administrar varios equipos en toda la organización sanitaria.

Elija un método para crear equipos con las plantillas sanitarias de Teams:

| Quién | Método para usar: |
| ---- | --------- |
| Administradores y profesionales de TI | [Use el centro de administración de Teams](#use-the-teams-templates-in-the-teams-admin-center) para crear equipos basados en las plantillas de Teams para la salud.|
| Desarrolladores e integradores de sistemas | [Use Microsoft Graph para crear](#use-the-teams-templates-with-the-microsoft-graph) equipos basados en las plantillas de Teams para el ámbito sanitario. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Usar las plantillas de Teams en el Centro de administración de Teams

Los administradores de Microsoft Teams pueden usar el Centro de administración de Teams para crear equipos con las plantillas de Teams. Actualmente, ofrecemos dos plantillas sanitarias de terceros que puede usar para una variedad de situaciones. Para obtener más información general sobre las plantillas de equipo, vea Introducción a [las plantillas de Teams en el Centro de administración.](../../get-started-with-teams-templates-in-the-admin-console.md)

### <a name="collaborate-on-patient-care"></a>Colaborar en la atención al paciente

 Simplifiice la comunicación y la colaboración sanitaria en un departamento, una podio o un departamento. La plantilla se puede usar para facilitar la administración del paciente y las necesidades operativas de un centro de atención.

| Tipo de plantilla base |baseTemplateId| Propiedades que vienen con esta plantilla base |
| ------------------ |---|----------------------------------------------------- |
| Colaborar en la atención al paciente |`healthcareWard` | Canales:<ul><li>General</li><li>Anuncios</li><li>Garabatos</li><li>Redondear</li><li>Empleados</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas</li></ul>|
||||

### <a name="hospital"></a>Hospital

Simplifiice la comunicación y la colaboración entre varios centros de investigación, podios y departamentos dentro de un hospital. Esta plantilla incluye un conjunto de canales base para operaciones hospitalarias y se puede ampliar para incluir especiales, ad hoc.

| Tipo de plantilla base |baseTemplateId | Propiedades que vienen con esta plantilla base |
| ------------------|-- |----------------------------------------------------- |
|Hospital|`healthcareHospital`|Canales: <ul><li>General</li><li>Anuncios</li><li>Cumplimiento</li><li>Descúyal</li><li>Recursos humanos</li><li>Clínica</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Usar las plantillas de Teams con Microsoft Graph

Los desarrolladores pueden usar Microsoft Graph para crear equipos con las plantillas de Teams. Actualmente, ofrecemos dos plantillas sanitarias de terceros que puede usar para una variedad de situaciones. Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams.](../../get-started-with-teams-templates.md) Además, para obtener información sobre las plantillas de Teams y Microsoft Graph, vea información general sobre [la API](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) de Microsoft Teams y [teamsTemplate tipo de recurso.](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)

### <a name="ward-template"></a>Plantilla de resalte

La plantilla del centro está pensada para la comunicación y la colaboración dentro de un departamento, una vaina o un departamento. La plantilla se puede usar para facilitar la administración del paciente, así como las necesidades operativas de un centro de atención. Por ejemplo, los anuncios del canal Anuncios se pueden publicar en el canal *Anuncios* y los turnos se pueden administrar en *Personal.* Si quiere simplificar las operaciones de sala, esta plantilla es la adecuada para usted.

|Tipo de plantilla base |baseTemplateId |Canales de plantilla de línea base|
|:--- |:---|:---|
|Salud - Centro de salud | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Anuncios\* <br> Garabatos\* <br> Redondear\* <br> Empleados\* <br> Aprendizaje\* |
|     | |         |

\* Favorito automático

### <a name="hospital-template"></a>Plantilla hospital

La plantilla hospitalaria está pensada para la comunicación y colaboración entre varios centros hospitalarios, podios y departamentos. Esta plantilla incluye varios canales de operaciones, entre los que se incluyen *Anuncios,* *Limpiezal* y *Química,* pero a continuación le proporcionamos un script que amplía la plantilla con una variedad de canales adicionales centrados en el departamento o centrados en la atención que puede agregar, eliminar o editar a su gusto. Por ejemplo, si tiene un departamento de endocrinology, pero no necesita un canal para *la ophology,* el script puede adaptarse para incluir un canal de *endocrinology* y eliminar el canal de *Ophphology.*  Se recomienda que estos canales especiales o modelo de canal no se agregó como favoritos automáticamente para evitar la saturación de notificaciones. Por lo general, los usuarios son favoritos de los canales que les sean relevantes.

|Tipo de plantilla base |baseTemplateId |Canales de plantilla de línea base|
|:--- |:---|:---|
|Salud - Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Anuncios\* <br> Cumplimiento\* <br> Descúyal <br> Recursos humanos <br> Clínica |
| | |  |

\* Favorito automático 

### <a name="how-to-use-first-party-templates"></a>Cómo usar plantillas de terceros

Para usar estas plantillas, simplemente cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "estándar" a los templateIDs anteriores.  Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Los canales de la plantilla se crearán automáticamente en la pestaña General.

#### <a name="example-hospital-template-extension-script"></a>Ejemplo: Script de extensión de plantilla hospitalaria

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
