---
title: Administrar los canales privados en Microsoft Teams con Graph API
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo administrar canales privados en su organización con Graph API.
ms.openlocfilehash: e97d808bd9f544ef611b0b5e4b0456d302b4013d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117748"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Administrar el ciclo de vida de los canales privados en Microsoft Teams

Aquí encontrará las instrucciones que necesita para administrar el uso de la API de Graph para administrar los canales privados de [Teams](./private-channels.md) en su organización.

## <a name="set-whether-team-members-can-create-private-channels"></a>Configurar si los propietarios y miembros pueden crear canales privados

Como administrador, puede usar la API de Graph para controlar si los miembros pueden crear canales privados en un equipo específico. Por ejemplo:

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Crear un canal privado en nombre de un propietario del equipo

Como administrador, puede usar la API de Graph para crear un canal privado en nombre de un propietario del equipo. Por ejemplo, quizá quiera hacerlo si su organización pretende centralizar la creación de canales privados.

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a>Obtenga una lista de todos los mensajes del canal privado

Quizá quiera obtener una lista de todos los mensajes y las respuestas de un canal privado para poder archivarlos y hacer una auditoría.  Aquí se muestra cómo usar la API de Graph para hacerlo.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Encuentre las direcciones URL de SharePoint para todos los canales privados en un equipo

Tanto si quieres hacer una exhibición de documentos electrónicos o archivos de una suspensión por litigio en un canal privado o quieres diseñar una aplicación personalizada que ubique los archivos en ciertos canales privados, querrás una manera de consultar las únicas colecciones de sitios SharePoint que se han creado para cada canal privado.

Como administrador, puede usar comandos de API de Graph para consultar estas direcciones URL.

Puede probar estos comandos a través del [Explorador de Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Use lo siguiente para obtener la lista de los identificadores de los canales privados para enviarlos al equipo, donde <group_id> es el ID del grupo del equipo. Lo necesitará en las siguientes llamadas. (Puede encontrar fácilmente el ID del grupo en el enlace del equipo.)

    **Solicitud**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Respuesta**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
    
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

2. Para cada canal privado del que quiera obtener la dirección URL de SharePoint, haga la siguiente solicitud, donde &lt;channel_id&gt; es el ID del canal.

    **Solicitud**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Respuesta**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
      
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Lista y actualización de roles de los propietarios y los miembros de un canal privado

Quizá quiera extraer una lista de los propietarios y los miembros de un canal privado para decidir si necesita ascender a ciertos miembros de un canal privado al rol de propietario. Esto puede ocurrir cuando tienes propietarios de canales privados que han dejado la organización y el canal privado requiere ayuda administrativa para reclamar la propiedad del mismo.

Como administrador, puede usar la API de Graph para realizar estas acciones.

Puede probar estos comandos a través del [Explorador de Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Use lo siguiente, donde &lt;group_id&gt; es el ID de grupo del equipo y &lt;channel_id&gt; es el ID del canal.

    **Solicitud**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **Respuesta**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams({group_id}')/channels('{channel_id}')/members",
          "@odata.count": 2,
          "value": [
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
                  "id": "id-value",
                  "roles": [],
                  "displayName": "display-name-value",
                  "userId": "userId-value",
                  "email": "email-value"
              },
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
              "id": "id-value",
              "roles": ["owner"],
              "displayName": "display-name-value",
              "userId": "userId-value",
              "email": "email-value"
              }
          ]
    }
    ```    
2. Use lo siguiente para ascender un miembro a propietario, donde &lt;group_id&gt;, &lt;channel_id&gt; e &lt;id&gt; se obtienen de llamadas anteriores. Tenga en cuanta que &lt;id&gt; y &lt;userId&gt; que se obtienen de llamadas anteriores no son los mismos y no son intercambiables. Asegúrese de que usa el &lt;id&gt;.

    **Solicitud**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Respuesta**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>Temas relacionados

[Usar la API de Microsoft Graph para trabajar con Microsoft Teams](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[Enumerar canales](/graph/api/channel-list)

[Crear un canal](/graph/api/channel-post)

[Agregar un miembro al canal](/graph/api/conversationmember-add)

[Actualizar un miembro del canal](/graph/api/conversationmember-update)

[Quitar un miembro del canal](/graph/api/conversationmember-delete)