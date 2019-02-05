---
title: Empezar a trabajar con plantillas de Microsoft los equipos sanitarios
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Empezar a trabajar con plantillas de Microsoft los equipos sanitarios
ms.openlocfilehash: 7d55d2d6a5f062bc5eb85b6bfc5227f7813c91ca
ms.sourcegitcommit: fddb1d6798e7a716ad87b0613f45a76deff6a043
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2019
ms.locfileid: "29735639"
---
# <a name="get-started-with-microsoft-teams-healthcare-templates"></a>Empezar a trabajar con plantillas de Microsoft los equipos sanitarios

Plantillas de Microsoft Teams permiten rápidamente y creación fácilmente los equipos, ya que proporciona una plantilla predefinida de configuración, canales y aplicaciones instaladas previamente.

Para las organizaciones de salud, plantillas pueden ser especialmente eficaces, ya que proporcionan la estructura para que los usuarios se convierten en orientación con cómo aprovechar al máximo los equipos de forma eficaz. Las plantillas también permiten a los administradores implementar equipos coherentes en sus organizaciones. En este artículo es para usted, si es responsable de la planeación, implementación y administración de varios equipos a través de su organización de salud.

Se actualmente oferta dos primera parte healthcare plantillas que puede aprovechar para una gran variedad de situaciones. Para obtener más información acerca del equipo plantillas en general, vea [Introducción a las plantillas de equipos](../get-started-with-teams-templates.md).

## <a name="ward-template"></a>Plantilla de distrito

La plantilla de distrito está pensada para la comunicación y la colaboración dentro de un distrito, caja o departamento. La plantilla se puede usar para facilitar la administración de pacientes, así como las necesidades operativas de un distrito. Por ejemplo, anuncios de distrito se pueden registrar en el canal de *anuncios* y turnos se pueden administrar en *personal*. Si busca para optimizar sus operaciones de distrito, esta plantilla es para usted.

|Tipo de plantilla de base |baseTemplateId |Canales de la plantilla de línea de base|
|:--- |:---|:---|
|Healthcare - distrito | https://<span></span>gráfico<span></span>.microsoft.com/beta/teamsTemplates/healthcareWardWide   | Anuncios\* <br> Luces de llamada\* <br> Material variado\* <br> Huddles\* <br>Redondea hacia arriba\* <br>Recursos de aprendizaje\* |
|     | |         |

\*Automático favoritos 

## <a name="hospital-template"></a>Plantilla de hospital

La plantilla de hospital está pensada para la comunicación y la colaboración entre varios departamentos dentro de un hospital, pods y salas de consulta. Incluidos en esta plantilla se varios canales operativos incluidos *anuncios*, *Custodial*y *farmacia*, pero también proporcionan una secuencia de comandos por debajo del cual extiende la plantilla con una gran variedad de departamento adicional o canales de centrado en especializados que se pueden agregar, eliminar de o editar a su gusto. Por ejemplo, si tiene un departamento de *Endocrinology* , pero no es necesario un canal para *Oftalmología*, puede adaptar la secuencia de comandos para incluir un canal *Endocrinology* y eliminar el canal de *Oftalmología* . Se recomienda que estos especializados o canales de modelar distrito no ser automático favoritos para evitar la saturación de notificación. Los usuarios normalmente favoritos cualquiera canales que consideren pertinentes.

|Tipo de plantilla de base |baseTemplateId |Canales de la plantilla de línea de base|
|:--- |:---|:---|
|Healthcare - Hospital | https://<span></span>gráfico<span></span>.microsoft.com/beta/teamsTemplates/healthcareWardWide   | Anuncios\* <br> Cumplimiento de normas\* <br> Material variado\* <br>Custodia<br>Servicios financieros<br>Recursos humanos <br>Laboratorio<br> Farmacia |
| | |  |

\*Automático favoritos 

## <a name="how-to-use-first-party-templates"></a>Cómo usar plantillas primera parte

Para usar estas plantillas, bastará con cambiar la propiedad 'template@odata.bind' en el cuerpo de la solicitud de 'estándar' para el TemplateIDs anterior.  Para obtener más información acerca de cómo implementar las plantillas de equipos, vea el [artículo sobre la creación de un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)de Microsoft Graph.

### <a name="example-hospital-template-extension-script"></a>Ejemplo: Secuencia de comandos de extensión de plantilla Hospital

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/healthcareHospitalWide",
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
