---
title: Introducción a las plantillas de equipos
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: Obtenga información sobre cómo usar las plantillas de equipos para crear un equipo con los canales de predefinidos.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801467"
---
# <a name="get-started-with-teams-templates"></a>Introducción a las plantillas de equipos 

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
| Nombre del equipo | Imagen del equipo |
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

De forma predeterminada, la plantilla base se establece en **estándar** que no contiene propiedades especiales ni aplicaciones adicionales de su propiedad. A continuación está disponible la lista actual de tipos de plantillas de base.

| Tipo de plantilla de base | baseTemplateId | Aplicaciones propietario de plantilla de base y las propiedades especiales |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | No hay aplicaciones adicionales y propiedades |
| Educación- <br>Clase equipo<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | Aplicaciones:<ul><li>Bloc de notas de OneNote clase (anclado a la ficha **General** ) </li><li>Aplicación de las asignaciones (anclado a la ficha **General** )</li></ul> Propiedades de equipo:<ul><li>Visibilidad de equipo se establece en **HiddenMembership** (no se puede reemplazar)</li></ul> |
| Educación-<br>Personal de grupo<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | Aplicaciones:<ul><li>Bloc de notas de OneNote personal (anclado a la ficha **General** )</li></ul> |
|Educación-<br>Equipo PLC |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | Aplicaciones:<ul><li>Bloc de notas de OneNote PLC (anclado a la ficha **General** )</ul></li>|
|||

Publicación de <sup>1</sup> de octubre de 2018 las últimas

> [!NOTE]
> Agregaremos más plantilla base de tipos de en futuras versiones de Microsoft Teams, por lo que verificación atrás para la información más actualizada sobre admite propiedades.

## <a name="examples"></a>Ejemplos 

Puede empezar a usar una plantilla para crear un equipo mediante el uso de la [API de Microsoft Graph](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

### <a name="create-a-team-from-a-template"></a>Crear un equipo a partir de una plantilla

#### <a name="requests"></a>Solicitudes

**Solicitud para crear un equipo con la plantilla de base estándar**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

**Para crear un equipo con un canal extra y no permitir a los miembros de eliminar los canales de solicitudes**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

**Solicitud para crear un equipo con todas las propiedades compatibles**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a>Obtener el estado

#### <a name="request"></a>Solicitud

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a>Respuesta

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a>Temas relacionados

- [Crear equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en la vista previa)
- [Nuevo equipo](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formación de administradores para Microsoft Teams](itadmin-readiness.md)