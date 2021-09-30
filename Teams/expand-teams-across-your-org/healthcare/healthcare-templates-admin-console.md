---
title: Usar plantillas de equipo de atención sanitaria
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Obtenga información sobre cómo administrar y usar las plantillas de equipo sanitario en el Centro de administración de Teams y con Microsoft Graph para crear equipos de forma rápida y sencilla para su organización sanitaria.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5345f5e9886bbcb9e4a2274d21d2aabb0be373c6
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007810"
---
# <a name="use-healthcare-team-templates"></a>Usar plantillas de equipo de atención sanitaria

Las plantillas de equipo de Microsoft Teams le permiten crear equipos de forma rápida y sencilla al proporcionar una estructura predefinida de equipos de configuración, canales y aplicaciones preinstaladas.

En el caso de las organizaciones sanitarias, las plantillas de equipo pueden ser especialmente eficaces, ya que le ayudan a implementar rápidamente equipos coherentes en toda la organización. Las plantillas también ayudan al personal a orientarse con la forma de usar Teams de forma eficaz.

Teams incluye plantillas diseñadas específicamente para organizaciones sanitarias. Use estas plantillas predefinidas para crear rápidamente equipos para que el personal se comunique y colabore en la atención a los pacientes o en las necesidades operativas. En este artículo, le presentamos cada una de estas plantillas y le recomendamos que las use.

La forma de administrar y trabajar con plantillas de equipo depende de si es administrador o desarrollador.

|Si está: | A continuación, usted: |
| ---- | --------- |
| Un administrador o un profesional de TI |[Administrador de plantillas de equipo en el Centro de administración de Teams](#manage-team-templates-in-the-teams-admin-center). Vea las plantillas de equipo y aplique directivas de plantillas para controlar cuales puede usar su personal en Teams para crear equipos. |
| Un desarrollador | [Usar Microsoft Graph](#use-team-templates-with-microsoft-graph) para crear equipos a partir de plantillas de equipo. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Administrar plantillas de equipo en el Centro de administración de Teams

Como un administrador, puede administrar plantillas de equipo en el Centro de administración de Microsoft Teams. Aquí puede ver los detalles acerca de cada plantilla. También puede [crear y asignar directivas de plantillas](../../templates-policies.md) al personal para controlar qué plantillas ven en Teams para [crear equipos](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c). 

Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams en el Centro de administración](../../get-started-with-teams-templates-in-the-admin-console.md).

Actualmente ofrecemos las siguientes plantillas de equipo de atención sanitaria pregeneradas. Para verlos, en el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Teams** > **plantillas de equipo**.
### <a name="patient-care"></a>Cuidado del paciente

 Esta plantilla está pensada para la comunicación y la colaboración dentro de una sala, un pod o un departamento. Puede usar esta plantilla para facilitar la administración de pacientes y las necesidades operativas de una sala. Por ejemplo, publique anuncios de sala en el canal *Anuncios* y administre los turnos en el canal de llamadas de *Personal*.

| Tipo de plantilla |TemplateId| Propiedades que vienen con esta plantilla |
| ------------------ |---|----------------------------------------------------- |
| Cuidado del paciente |`healthcareWard` | Canales:<ul><li>General</li><li>Anuncios<ul><li>Boletines&sup1;</li></ul></li><li>Huddles<ul><li>Listas (lista de pacientes)&sup1;</li></ul></li><li>Rondas<ul><li>Inspección&sup1;</li></ul></li><li>Personal</li><li>Aprendizaje</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Listas</li><li>Tareas</li><li>Aprobaciones</li><li>Turnos</li><li>Boletines</li><li>Inspección</li></ul>|
||||

&sup1; Aplicación agregada al canal como una pestaña.
### <a name="hospital"></a>Hospital

Esta plantilla está pensada para la comunicación y la colaboración entre varios salas, pods y departamentos dentro de un hospital. Esta plantilla incluye un conjunto de canales para las operaciones hospitalarias y se puede ampliar para una mayor personalización.

| Tipo de plantilla |TemplateId | Propiedades que vienen con esta plantilla |
| ------------------|-- |----------------------------------------------------- |
|Hospital|`healthcareHospital`|Canales: <ul><li>General<ul><li>Listas&sup1;</li></ul></li><li>Anuncios<ul><li>Boletines&sup1;</li></ul></li><li>Cumplimiento</li><ul><li>Inspección&sup1;</li></ul></li><li>Custodia</li><li>Recursos humanos<ul><li>Ideas&sup1;</li></ul></li><li>Farmacia</li></ul> Aplicaciones: <ul><li>Wiki</li><li>Tareas</li><li>Listas</li><li>Aprobaciones</li><li>Turnos</li><li>Boletines</li><li>Inspección</li><li>Ideas</li></ul>|
||||

&sup1; Aplicación agregada al canal como una pestaña.
## <a name="use-team-templates-with-microsoft-graph"></a>Uso de plantillas de equipo con Microsoft Graph

Los desarrolladores pueden usar Microsoft Graph para crear equipos a partir de plantillas de equipo predefinidas. Para obtener más información sobre el uso de plantillas de equipo con Microsoft Graph, vea [Introducción a las plantillas de equipo mediante Microsoft Graph](../../get-started-with-teams-templates.md), [información general de la API de Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0)y [tipo de recurso teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Estas son las plantillas de equipo de atención sanitaria predefinidas.
### <a name="ward"></a>Sala

La plantilla de sala está pensada para la comunicación y la colaboración dentro de una sala, un pod o un departamento. La plantilla se puede usar para facilitar la administración de pacientes y las necesidades operativas de una sala. Por ejemplo, los anuncios de salas pueden publicarse en el canal *Anuncios* y los turnos pueden publicarse en el canal *Personal*. Si quiere simplificar sus operaciones de sala, esta plantilla es la adecuada.

|Tipo de Plantilla |TemplateId |Canales de plantilla|
|:--- |:---|:---|
|Atención sanitaria: Sala | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | General<br>Anuncios&sup2; <br> Huddles&sup2; <br> Redondeos&amp;2; <br> Personal&sup2; <br> Aprendizaje&2; |
|     | |         |

&sup2; Canales con favoritos automáticos

### <a name="hospital"></a>Hospital

La plantilla de hospital está pensada para la comunicación y la colaboración entre varias salas, pods y departamentos dentro de un hospital. Esta plantilla incluye varios canales operativos como *Anuncios*, *de custodios* y *Farmacia*. También proporcionamos un script que puede usar para ampliar la plantilla con departamentos adicionales o canales especializados. Puede editarlo para adaptarlo a sus necesidades.

Por ejemplo, si tiene un departamento de *Endocrinología*, pero no necesita un canal para *Oftalmología*, el script puede adaptarse para incluir un canal de *Endocrinología* y quitar el canal de *Oftalmología*. Para evitar la saturación de notificaciones, recomendamos que estos canales de especialidades o basados en salas no se marquen como favoritos automáticamente. Los usuarios suelen marcar como favoritos los canales que encuentran relevantes.

|Tipo de plantilla |TemplateId |Canales de plantilla|
|:--- |:---|:---|
|Atención sanitaria: Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | General<br>Anuncios&sup2; <br> Cumplimiento&sup2; <br> Custodia <br> Recursos humanos <br> Farmacia |
| | |  |

&sup2; Canales con favoritos automáticos

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Cómo usar las plantillas de equipo con Microsoft Graph

Para usar estas plantillas, cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "standard" a TemplateIds anterior. Para obtener más información sobre cómo implementar plantillas de equipo, consulte el artículo de Microsoft Graph sobre cómo [crear un equipo](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Los canales de la plantilla se crearán automáticamente en la pestaña **General**.

#### <a name="example-hospital-template-extension-script"></a>Ejemplo: script de extensión de plantilla hospitalaria

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

### <a name="related-articles"></a>Artículos relacionados

[Introducción a las plantillas de equipo en el centro de administración de Teams](../../get-started-with-teams-templates-in-the-admin-console.md)

[Introducción a las plantillas de equipo con Microsoft Graph](../../get-started-with-teams-templates.md)

[Introducción a Teams para organizaciones sanitarias](teams-in-hc.md)