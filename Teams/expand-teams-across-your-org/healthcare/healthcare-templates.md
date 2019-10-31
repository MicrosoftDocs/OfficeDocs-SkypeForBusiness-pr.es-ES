---
title: Introducción a las plantillas para las organizaciones sanitarias de Teams
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Introducción a las plantillas para las organizaciones sanitarias de Teams
ms.openlocfilehash: e19c0403f259f400e784faf928738d36df66d618
ms.sourcegitcommit: ced9b584eeceff7ca0109cba5823c7c3ddbd092e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "37886443"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Introducción a las plantillas para las organizaciones sanitarias de Teams

Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.

Para las organizaciones de cuidado de la salud, las plantillas pueden ser especialmente eficaces, puesto que proporcionan una estructura para que los usuarios se orienten con la mejor manera de aprovechar Teams. Las plantillas también permiten a los administradores implementar equipos coherentes en sus organizaciones. Este artículo le interesa si es responsable de planear, implementar y administrar varios equipos en la organización de la salud.

Actualmente ofrecemos dos plantillas de atención médica de primera parte que puede aprovechar para diversas situaciones. Para obtener más información sobre las plantillas de equipo en general, consulte [Introducción a las plantillas](../../get-started-with-teams-templates.md)de Teams.

## <a name="ward-template"></a>Plantilla en adelante

La plantilla en adelante está pensada para la comunicación y la colaboración dentro de un interior, un conjunto Pod o un departamento. La plantilla se puede usar para facilitar la administración de pacientes, así como las necesidades operacionales de un mismo. Por ejemplo, los anuncios en adelante se pueden publicar en el canal de *anuncios* y los turnos se pueden administrar en el *personal*. Si está buscando simplificar sus operaciones en el exterior, esta plantilla es para usted.

|Tipo de plantilla base |baseTemplateId |Canales de plantillas de línea base|
|:--- |:---|:---|
|Atención médica en adelante | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Anuncios\* <br> Huddles\* <br> Hacia\* <br> Personal\* <br> Instrui\* |
|     | |         |

\*Con favoritos automáticos

## <a name="hospital-template"></a>Plantilla de hospital

La plantilla del hospital está pensada para la comunicación y la colaboración entre varios departamentos, pods y otros departamentos dentro de un hospital. En esta plantilla se incluyen varios canales operativos, entre los que se incluyen *anuncios*, personalización de la *asistencia*y *farmacia*, pero también ofrecemos una secuencia de comandos a continuación que extiende la plantilla con una variedad de departamentos adicionales o canales de especialización especializada que puede Agregar, eliminar o editar a su gusto. Por ejemplo, si tiene un departamento de *Endocrinology* , pero no necesita un canal para *Ophthalmology*, la secuencia de comandos puede adaptarse para incluir un canal de *Endocrinology* y quitar el canal *Ophthalmology* . Le recomendamos que estos canales de especialidad o modelos en el exterior no se hayan preferido de forma automática para evitar la saturación de las notificaciones. Por lo general, los usuarios tienen los canales que encuentran relevantes.

|Tipo de plantilla base |baseTemplateId |Canales de plantillas de línea base|
|:--- |:---|:---|
|Asistencia sanitaria-Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Anuncios\* <br> Respeto\* <br> Private <br> Recursos humanos <br> Pertenecie |
| | |  |

\*Con favoritos automáticos 

## <a name="care-coordination-template"></a>Plantilla de coordinación de cuidados

La plantilla de coordinación de cuidados está pensada para facilitar la comunicación dentro de un equipo de atención al paciente, con algunos ejemplos como interdisciplinarios y equipos multidisciplinarios. Nuestra aplicación de pacientes de propiedad está precargada en esta plantilla y se coloca en el canal general. Con la aplicación de pacientes, puede ajustar listas de pacientes y sus valores asociados y vitales, lo que hace que sea útil para el redondeo y los escenarios de administración de pacientes. 

|Tipo de plantilla base |baseTemplateId |Canales de plantillas de línea base|
|:--- |:---|:---|
|Asistencia sanitaria: coordinación de cuidados | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareCareCoordination')`   | Revisión posterior al tratamiento\* <br> Programación\* <br> Instrui\* |
| | |  |

\*Con favoritos automáticos 

## <a name="how-to-use-first-party-templates"></a>Cómo usar las plantillas de primera fiesta

Para usar estas plantillas, simplemente cambie la propiedad ' template@odata.bind ' en el cuerpo de la solicitud de ' Standard ' a la TemplateIDs anterior.  Para obtener más información sobre cómo implementar las plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Los canales de la plantilla se crearán automáticamente en la ficha General.

### <a name="example-hospital-template-extension-script"></a>Ejemplo: script de extensión de plantilla de hospital

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
              "displayName": "Women’s Health",
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
