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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a administrar el ciclo de vida de los canales privados de su organización.
ms.openlocfilehash: 527e6421160eefa72b2a9c21e8e8f25303534320
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837330"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Administrar el ciclo de vida de canales privados en Microsoft Teams

Aquí encontrará las instrucciones que necesita para administrar el ciclo de vida de los [canales privados](private-channels.md) de su organización.

> [!IMPORTANT]
> Si está usando los pasos de PowerShell de este artículo para administrar canales privados, debe instalar y usar la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell. Para conocer los pasos para realizar esto, consulte [instalar el módulo de PowerShell más reciente de la galería de pruebas de PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery). La última versión disponible públicamente del módulo de PowerShell de Teams (actualmente [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) no admite la administración de canales privados.

## <a name="set-whether-team-members-can-create-private-channels"></a>Establecer si los miembros del equipo pueden crear canales privados

Los propietarios del equipo pueden desactivar o activar la posibilidad de que los miembros creen canales privados en la configuración del equipo. Para ello, en la pestaña **configuración** del equipo, desactive o desactive **permitir que los miembros creen canales privados**.

Como administrador, puede usar la API de Graph para controlar si los miembros pueden crear canales privados en determinados equipos. Este es un ejemplo.

```Graph API
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

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Usar la API Graph

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

## <a name="get-a-list-of-all-private-channel-messages"></a>Obtener una lista de todos los mensajes de canal privado

Es posible que desee obtener una lista de todos los mensajes y respuestas publicados en un canal privado para archivar y auditar.  A continuación se explica cómo usar la API de Graph para hacerlo.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Buscar direcciones URL de SharePoint para todos los canales privados de un equipo

Tanto si desea realizar una búsqueda de exhibición de sitios web o una retención legal en archivos de un canal privado o en crear una aplicación de línea de negocio que coloca los archivos en canales privados específicos, querrá una manera de consultar las colecciones de sitios de SharePoint exclusivas que se crean para cada canal privado.

Como administrador, puede usar los comandos de las API de PowerShell o Graph para consultar estas direcciones URL.

### <a name="using-powershell"></a>Usar PowerShell

1. Instale y conéctese al [Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con su cuenta de administrador.
2. Ejecute lo siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo. (Puede encontrar fácilmente el identificador de grupo en el vínculo al equipo).

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Usar la API Graph

Puede probar estos comandos en el [Explorador de gráficos](https://developer.microsoft.com/graph/graph-explorer).

1. Use el siguiente procedimiento para obtener la lista de identificadores de canal privado para un equipo determinado, donde <group_id> es el identificador de grupo del equipo. La necesitarás en llamadas posteriores. (Puede encontrar fácilmente el identificador de grupo en el vínculo al equipo).

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

2. Para cada canal privado para el que desee obtener la dirección URL de SharePoint, realice la siguiente solicitud &lt;,&gt; donde channel_id es el identificador de canal.

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Enumerar y actualizar los roles de propietarios y miembros en un canal privado

Es posible que desee enumerar los propietarios y miembros de un canal privado para decidir si necesita promover a un propietario a determinados miembros del canal privado. Esto puede ocurrir cuando tiene propietarios de canales privados que han abandonado la organización y el canal privado requiere ayuda del administrador para reclamar la propiedad del canal.

Como administrador, puede usar los comandos de las API de PowerShell o Graph para consultar estas direcciones URL.

### <a name="using-powershell"></a>Usar PowerShell

1. Instale y conéctese al [módulo de Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) con su cuenta de administrador.
2. Ejecute lo siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo y &lt;channel_id&gt; es el identificador de canal.

    **Solicitud**

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    **Respuesta**

    ```PowerShell
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

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Usar la API Graph

Puede probar estos comandos en el [Explorador de gráficos](https://developer.microsoft.com/graph/graph-explorer).

1. Use lo siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo y &lt;channel_id&gt; es el identificador de canal.

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
2.  Use el siguiente procedimiento para promocionar el miembro a propietario, &lt;donde&gt;group_id &lt;,&gt;channel_id e &lt;ID&gt; se devuelven desde la llamada anterior. Ten en &lt;cuenta&gt; que &lt;el&gt; identificador y el userId devueltos por la llamada anterior no son iguales y no son intercambiables. Asegúrate de usar &lt;el identificador&gt;.

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

## <a name="teams-powershell-module"></a>Módulo de PowerShell de Teams

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a>Instale el módulo de PowerShell más reciente de la galería de pruebas de PowerShell

La última versión disponible públicamente del módulo de PowerShell de Teams (actualmente [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) no admite la administración de canales privados. Siga estos pasos para instalar la última versión del módulo de PowerShell de Teams con compatibilidad de canal privado (actualmente 1.0.18) de la galería de pruebas de PowerShell.

> [!NOTE]
> No instale el módulo de Teams PowerShell desde la galería de pruebas de PowerShell en paralelo con una versión del módulo de la galería de PowerShell pública. Siga estos pasos para desinstalar primero el módulo de PowerShell de Teams de la galería de PowerShell pública y, a continuación, instale la última versión del módulo desde la galería de pruebas de PowerShell.

1. Cierre todas las sesiones de PowerShell existentes.
2. Inicie una nueva instancia del módulo de Windows PowerShell.
3. Ejecute lo siguiente para desinstalar el módulo de PowerShell de Teams de la galería pública de PowerShell:

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Cierre todas las sesiones de PowerShell existentes.
5. Inicie el módulo de Windows PowerShell de nuevo y, a continuación, ejecute lo siguiente para registrar la galería de pruebas de PowerShell como una fuente de confianza:

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Ejecute lo siguiente para instalar el módulo de PowerShell más reciente de la galería de pruebas de PowerShell:

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Ejecute lo siguiente para comprobar que se ha instalado correctamente la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Actualice a la última versión del módulo de PowerShell de Teams desde la galería de pruebas de PowerShell

Si ya ha instalado el módulo de Teams PowerShell desde la galería de pruebas de PowerShell, siga estos pasos para actualizar a la última versión.

1. Cierre todas las sesiones de PowerShell existentes.
2. Inicie una nueva instancia del módulo de Windows PowerShell.
3. Ejecute lo siguiente para actualizar la versión del módulo de PowerShell instalada actualmente desde la galería de pruebas de PowerShell:

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Ejecute lo siguiente para comprobar que se ha instalado correctamente la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Usar la API de Microsoft Graph para trabajar con equipos](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Lista de canales](https://docs.microsoft.com/graph/api/channel-list)
    - [Crear canal](https://docs.microsoft.com/graph/api/channel-post)
    - [Agregar miembro al canal](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Actualizar miembro en el canal](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Quitar miembro de un canal](https://docs.microsoft.com/graph/api/conversationmember-delete)
