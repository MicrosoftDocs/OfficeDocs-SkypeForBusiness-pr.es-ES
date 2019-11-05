---
title: Administrar el ciclo de vida de canales privados en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a administrar el ciclo de vida de los canales privados de su organización.
ms.openlocfilehash: 5fe3f29559e62b6b6b11833304aa7bb13206fe6a
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2019
ms.locfileid: "37969418"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Administrar el ciclo de vida de canales privados en Microsoft Teams

Aquí encontrará las instrucciones que necesita para administrar el ciclo de vida de los [canales privados](private-channels.md) de su organización.

## <a name="set-whether-team-members-can-create-private-channels"></a>Establecer si los miembros del equipo pueden crear canales privados

Los propietarios del equipo pueden desactivar o activar la posibilidad de que los miembros creen canales privados en la configuración del equipo. Para ello, en la pestaña **configuración** del equipo, desactive o desactive **permitir que los miembros creen canales privados**.

Como administrador, puede usar la API de Graph para controlar si los miembros pueden crear canales privados en determinados equipos. Este es un ejemplo.

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Establecer si los usuarios de su organización pueden crear canales privados

Como administrador, puede establecer directivas con el centro de administración de Microsoft Teams o PowerShell para controlar los usuarios de su organización que pueden crear canales privados.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

Use directivas de Teams para establecer los usuarios de su organización que pueden crear canales privados. Para obtener más información, vea [Administrar directivas de Teams en Teams](teams-policies.md).

### <a name="using-powershell"></a>Usar PowerShell

Use **CsTeamsChannelsPolicy** para establecer qué usuarios de su organización pueden crear canales privados. Establezca el parámetro **AllowPrivateChannelCreation** en **true** para permitir a los usuarios a quienes les asignan la Directiva crear canales privados. Establecer el parámetro en **false** desactiva la capacidad de crear canales privados para los usuarios que tienen asignada la Directiva.

Para obtener más información, vea [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Crear un canal privado en nombre de un propietario del equipo

Como administrador, puede usar la API de PowerShell o Graph para crear un canal privado en nombre de un propietario del equipo. Por ejemplo, es posible que desee hacerlo si su organización desea centralizar la creación de canales privados.

### <a name="using-powershell"></a>Usar PowerShell

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Usar la API Graph

```
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a>Obtener una lista de todos los mensajes de canal privado

Es posible que desee obtener una lista de todos los mensajes y respuestas publicados en un canal privado para archivar y auditar.  A continuación se explica cómo usar la API de Graph para hacerlo.

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Buscar direcciones URL de SharePoint para todos los canales privados de un equipo

Tanto si desea realizar una búsqueda de exhibición de sitios web o una retención legal en archivos de un canal privado o en crear una aplicación de línea de negocio que coloca los archivos en canales privados específicos, querrá una manera de consultar las colecciones de sitios de SharePoint exclusivas que se crean para cada canal privado.

Como administrador, puede usar los comandos de las API de PowerShell o Graph para consultar estas direcciones URL.

### <a name="using-powershell"></a>Usar PowerShell

1. Instale y conéctese al [Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con su cuenta de administrador.
2. Ejecute lo siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo. (Puede encontrar fácilmente el identificador de grupo en el vínculo al equipo).

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Usar la API Graph

Puede probar estos comandos en el [Explorador de gráficos](https://developer.microsoft.com/graph/graph-explorer).

1. Use el siguiente procedimiento para obtener la lista de identificadores de canal privado para un equipo dado, donde <group_id> es el identificador de grupo del equipo. La necesitarás en llamadas posteriores. (Puede encontrar fácilmente el identificador de grupo en el vínculo al equipo).

    **Solicitud**

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Respuesta**

    ```
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

2. Para cada canal privado para el que desee obtener la dirección URL de SharePoint, realice la siguiente solicitud &lt;,&gt; donde channel_id es el identificador de canal.

    **Solicitud**

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Respuesta**

    ```
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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Enumerar y actualizar los roles de propietarios y miembros en un canal privado

Es posible que desee enumerar los propietarios y miembros de un canal privado para decidir si necesita promover a un propietario a determinados miembros del canal privado. Esto puede ocurrir cuando tiene propietarios de canales privados que han abandonado la organización y el canal privado requiere ayuda del administrador para reclamar la propiedad del canal.

Como administrador, puede usar los comandos de las API de PowerShell o Graph para consultar estas direcciones URL.

### <a name="using-powershell"></a>Usar PowerShell

1. Instale y conéctese al [módulo de Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) con su cuenta de administrador.
2. Ejecute lo siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo y &lt;channel_id&gt; es el identificador de canal.

    **Solicitud**

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    **Respuesta**

    ```
    HTTP/1.1 200 OK Content-type: application/json
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

3. Promociona un miembro a un propietario.

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Usar la API Graph

Puede probar estos comandos en el [Explorador de gráficos](https://developer.microsoft.com/graph/graph-explorer).

1. Use el siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo y &lt;channel_id&gt; es el identificador de canal.

    **Solicitud**

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **Respuesta**

    ```
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
2.  Use el siguiente procedimiento para promocionar el miembro a propietario, &lt;donde&gt;group_id &lt;,&gt;channel_id e &lt;ID&gt; se devuelven de la llamada anterior. Ten en &lt;cuenta&gt; que &lt;el&gt; identificador y el userId devueltos por la llamada anterior no son iguales y no son intercambiables. Asegúrate de usar &lt;el identificador&gt;.

    **Solicitud**

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Respuesta**

    ```
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

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Usar la API de Microsoft Graph para trabajar con equipos](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Lista de canales](https://docs.microsoft.com/graph/api/channel-list)
    - [Crear canal](https://docs.microsoft.com/graph/api/channel-post)
    - [Agregar miembro al canal](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Actualizar miembro en el canal](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Quitar miembro de un canal](https://docs.microsoft.com/graph/api/conversationmember-delete)