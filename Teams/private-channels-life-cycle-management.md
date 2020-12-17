---
title: Administrar el ciclo de vida de los canales privados en Microsoft Teams
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
description: Obtenga más información sobre cómo administrar el ciclo de vida de los canales privados de su organización.
ms.openlocfilehash: 336d97071c30bca145d26f4c853d5bb30265721f
ms.sourcegitcommit: 68dffc3aca46992448bc2be0689bfd352e016316
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49601665"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Administrar el ciclo de vida de los canales privados en Microsoft Teams

Aquí encontrará las instrucciones para administrar el ciclo de vida de los [canales privados](private-channels.md) de su organización.

> [!IMPORTANT]
> Si está usando los pasos de PowerShell de este artículo para administrar canales privados, debe instalar y usar el módulo versión preliminar pública PowerShell de Teams desde la [Galería de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). Consulte [Instalar PowerShell para Microsoft Teams](teams-powershell-install.md) para seguir los pasos de instalación del módulo.  El último módulo de PowerShell para Teams de disponibilidad general no admite la administración de canales privados.

## <a name="set-whether-team-members-can-create-private-channels"></a>Configurar si los propietarios y miembros pueden crear canales privados

Los propietarios del equipo pueden activar o desactivar la posibilidad de que los miembros puedan crear canales privados en la configuración del equipo. Para ello, en la pestaña **Configuración** del equipo, se puede activar o desactivar el **permitir que los miembros puedan crear canales privados**.

Como administrador, puede usar la API de Graph para controlar si los miembros pueden crear canales privados en un equipo específico. Por ejemplo:

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Configurar si los usuarios de la organización pueden crear canales privados

Como administrador, puede establecer directivas mediante el Centro de administración de Microsoft Teams o PowerShell para controlar qué usuarios de su organización pueden crear canales privados.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Use directivas para controlar qué usuarios de su organización pueden crear canales privados. Para obtener más información, consulte [Administrar directivas de equipos en Teams](teams-policies.md).

### <a name="using-powershell"></a>Con PowerShell

Use **CsTeamsChannelsPolicy** para controlar qué usuarios de su organización pueden crear canales privados. Configure el parámetro **AllowPrivateChannelCreation** como **verdadero** para permitir a los usuarios que se asignen en la directiva puedan crear canales privados. Configura el parámetro como **falso** para desactivar el que puedan crear canales privados los usuarios que se asignen en la directiva.

Para obtener más información, consulte [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Crear un canal privado en nombre de un propietario del equipo

Como administrador, puede usar PowerShell o la API de Graph para crear un canal privado en nombre de un propietario del equipo. Por ejemplo, quizá quiera hacerlo si su organización pretende centralizar la creación de canales privados.

### <a name="using-powershell"></a>Con PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Con la API de Graph

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

Como administrador, puede usar PowerShell o los comandos de la API de Graph para consultar estas direcciones URL.

### <a name="using-powershell"></a>Con PowerShell

1. Instale y conéctese a la [consola de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con su cuenta de administrador.
2. Ejecute lo siguiente, donde &lt;group_id&gt; es el ID de Grupo del equipo. (Puede encontrar fácilmente el ID del Grupo en el enlace del equipo.)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Con la API de Graph

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

Como administrador, puede usar el Centro de administración de Microsoft Teams, PowerShell o la API de Graph para llevar a cabo estas acciones.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Para obtener más información sobre cómo administrar los miembros del equipo con el Centro de administración de Microsoft Teams, consulte [Administrar equipos en el Centro de administración de Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="using-powershell"></a>Con PowerShell

1. Ejecute lo siguiente, donde &lt;group_id&gt; es el ID de grupo del equipo y &lt;channel_name&gt; es el nombre del canal.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. Ascender a un miembro al rol de administrador

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Con la API de Graph

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

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Usar la API de Microsoft Graph para trabajar con Microsoft Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Enumerar canales](https://docs.microsoft.com/graph/api/channel-list)
    - [Crear un canal](https://docs.microsoft.com/graph/api/channel-post)
    - [Agregar un miembro al canal](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Actualizar un miembro del canal](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Quitar un miembro del canal](https://docs.microsoft.com/graph/api/conversationmember-delete)
