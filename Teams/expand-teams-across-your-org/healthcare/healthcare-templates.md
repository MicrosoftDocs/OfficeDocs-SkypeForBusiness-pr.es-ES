---
title: Plantillas para organizaciones sanitarias
author: serdarsoysal
ms.author: serdars
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
description: Use las plantillas de Microsoft Teams con Microsoft Graph para crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4c2e10efbff98150b120d1c026d4d810629333f2
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790412"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Introducción a las plantillas de Teams para organizaciones sanitarias

Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.

Para las organizaciones sanitarias, las plantillas pueden ser especialmente eficaces, ya que proporcionan una estructura para que los usuarios se orienten sobre cómo usar Teams de manera eficaz. Las plantillas también permiten a los administradores implementar equipos coherentes en todas sus organizaciones. Este artículo es para usted si es responsable de planear, implementar y administrar varios equipos en toda la organización sanitaria.

Actualmente, ofrecemos dos plantillas sanitarias de terceros que puede usar para una variedad de situaciones. Para obtener más información sobre las plantillas de equipo en general, vea Introducción [a las plantillas de Teams.](../../get-started-with-teams-templates.md)

## <a name="ward-template"></a>Plantilla de sala

La plantilla del centro está pensada para la comunicación y la colaboración dentro de un departamento, una vaina o un departamento. La plantilla se puede usar para facilitar la administración del paciente, así como las necesidades operativas de un centro de atención. Por ejemplo, los anuncios del canal Anuncios se pueden publicar en el canal *Anuncios* y los turnos se pueden administrar en *Personal.* Si quiere simplificar las operaciones de sala, esta plantilla es la adecuada para usted.

|Tipo de plantilla base |baseTemplateId |Canales de plantilla de línea base|
|:--- |:---|:---|
|Salud - Centro de salud | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Anuncios\* <br> Garabatos\* <br> Redondear\* <br> Empleados\* <br> Aprendizaje\* |
|     | |         |

\* Favorito automático

## <a name="hospital-template"></a>Plantilla hospital

La plantilla hospitalaria está pensada para la comunicación y colaboración entre varios centros hospitalarios, podios y departamentos. Esta plantilla incluye varios canales de operaciones, entre los que se incluyen *Anuncios,* *Limpiezal* y *Química,* pero a continuación le proporcionamos un script que amplía la plantilla con una variedad de canales adicionales centrados en el departamento o centrados en la atención que puede agregar, eliminar o editar a su gusto. Por ejemplo, si tiene un departamento de *endocrinology,* pero no necesita un canal para *Ophologymology,* el script puede adaptarse para incluir un canal de *endocrinology* y eliminar el canal de *Ophphology.* Recomendamos que estos canales especiales o modelo de canal no se agregó como favoritos automáticamente para evitar la saturación de notificaciones. Por lo general, los usuarios son favoritos de los canales que les sean relevantes.

|Tipo de plantilla base |baseTemplateId |Canales de plantilla de línea base|
|:--- |:---|:---|
|Salud - Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Anuncios\* <br> Cumplimiento\* <br> Descúyal <br> Recursos humanos <br> Clínica |
| | |  |

\* Favorito automático 

## <a name="how-to-use-first-party-templates"></a>Cómo usar plantillas de terceros

Para usar estas plantillas, simplemente cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "estándar" a los templateIDs anteriores.  Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Los canales de la plantilla se crearán automáticamente en la pestaña General.

### <a name="example-hospital-template-extension-script"></a>Ejemplo: Script de extensión de plantilla hospitalaria

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

## <a name="related-topics"></a>Temas relacionados

[Introducción a las plantillas de Teams](../../get-started-with-teams-templates.md)

[Introducción a Teams para organizaciones sanitarias](teams-in-hc.md)

[Introducción a las plantillas de Teams en la consola de administración](../../get-started-with-teams-templates-in-the-admin-console.md)
