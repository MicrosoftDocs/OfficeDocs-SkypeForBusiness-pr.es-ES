---
title: Introducción a las plantillas de equipos
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 7850ad245eebee96b6852e7f0cc57a35adcca9f7
ms.sourcegitcommit: 8a56ed2107dfa378864576d1e137ab0086f5da08
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "23996263"
---
# <a name="get-started-with-teams-templates"></a>Introducción a las plantillas de equipos 

Plantillas de equipo son predefinidas definiciones de estructura de un equipo diseñado alrededor de un proyecto o necesidad empresarial. Puede usar las plantillas de equipo para crear rápidamente los espacios de colaboración con los canales para diferentes temas y preinstalación de aplicaciones que se van a extraer en servicios y contenido de misión crítica. Plantillas de equipo proporcionan una estructura de equipo predefinidos que puede ayudarle a crear fácilmente los equipos coherentes en toda la organización. 

En este artículo, se explican las propiedades que pueden definirse en plantillas, qué plantilla base son tipos, y cómo puede usar algunas solicitudes para crear un equipo a partir de una plantilla de ejemplo.
 
En este artículo es para usted si es:

• Responsable de la planeación, implementación y administración de varios equipos a través de su desarrollador de • una organización ¿está buscando para crear un equipo con predefinidos canales y aplicaciones mediante programación

## <a name="team-template-capabilities"></a>Capacidades de la plantilla de equipo

Mayoría de las propiedades en un equipo se incluyen y compatible con las plantillas. Sin embargo, hay algunas propiedades y características que actualmente no son compatibles. En la siguiente tabla proporciona un resumen rápido de lo que se incluye y qué no se incluye en las plantillas de equipos.

| **Propiedades de equipo compatibles con las plantillas de equipos** | **Propiedades de equipo aún no admitidas por las plantillas de equipos** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de plantilla de base | Miembros del equipo |
| Nombre del equipo | Imagen del equipo |
| Descripción de equipo | Configuración de canal (por ejemplo, auto-favorito y privacidad) |
| Visibilidad de equipo (pública o privada) | Conectores |
| Configuración del equipo (por ejemplo, miembro, invitado, @ menciones) | Los archivos y contenido |
| Canal de favorito de automático | |
| Aplicación instalada | |
| Fichas ancladas | | 

> [!NOTE]
> Se podrá ser agregar más capacidades de plantilla en futuras versiones de Microsoft Teams, por lo que vuelva a consultar para la información más actualizada sobre propiedades compatibles con.

## <a name="what-are-base-template-types"></a>¿Qué son los tipos de plantilla base?

Tipos de plantilla de base son plantillas especiales que Microsoft ha creado para sectores específicos. Estas plantillas bases a menudo contienen propietarias aplicaciones que no están disponibles en las propiedades de almacenamiento y de grupo que no se admite aún individualmente en las plantillas de equipos.

Una vez que se define un tipo de plantilla base, puede ampliar o reemplazar estas plantillas especiales con propiedades adicionales que le gustaría usar para especificar. Sin embargo, algunos tipos de plantilla base contienen las propiedades que no se puede reemplazar. 

De forma predeterminada, la plantilla base se establece en **estándar** que no contiene propiedades especiales ni aplicaciones adicionales de su propiedad. A continuación está disponible la lista actual de tipos de plantillas de base.

| Tipo de plantilla de base | baseTemplateId | Aplicaciones propietario de plantilla de base y las propiedades especiales |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | No hay aplicaciones adicionales y propiedades |
| Healthcare - coordinación de la atención | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | Aplicaciones:<br/> -Aplicación de los pacientes (anclado a la ficha **General** )<br/> <br/>Canales de entrada: <br/> -Anuncios<br/> -Diabetes<br/> -Cardiovascular<br/> -Diplomadas |
| Healthcare - proceso ponerse a trabajar | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | Canales de entrada:<br/> -Evitables muertes<br/> -Revisión de mortalidad <br/> -Impidiendo que se divide <br/> -Planes de sepsis |
| Educación - clase equipo<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | Aplicaciones:<br/> -Bloc de notas de OneNote clase (anclado a la ficha **General** ) <br/> -App asignaciones (anclado a la ficha **General** ) <br/><br/> Propiedades de equipo <br/> -Visibilidad equipo establecida en **HiddenMembership** (no se puede reemplazar) |
| Equipo de personal de educación -<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | Aplicaciones<br/> -Bloc de notas de OneNote personal (anclado a la ficha **General** ) |

Publicación de <sup>1</sup> de octubre de 2018 las últimas

> [!NOTE]
> Agregaremos más plantilla base de tipos de en futuras versiones de Microsoft Teams, por lo que verificación atrás para la información más actualizada sobre admite propiedades.

## <a name="examples"></a>Ejemplos 

Puede iniciar la creación de un equipo a través de la plantilla mediante la instalación de [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).

### <a name="create-a-team-from-a-template"></a>Crear un equipo a partir de una plantilla

#### <a name="requests"></a>Solicitudes

**Solicitud para crear un equipo con la plantilla de base estándar**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

**Para crear un equipo con un canal extra y no permitir a los miembros de eliminar los canales de solicitudes**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

**Solicitud para crear un equipo con todas las propiedades compatibles**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a>Respuesta

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
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

- [Crear equipo](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (en la vista previa)
- [Nuevo equipo](https://docs.microsoft.com/en-us/powershell/module/teams/New-Team?view=teams-ps)
- [Formación de administradores para Microsoft Teams](itadmin-readiness.md)