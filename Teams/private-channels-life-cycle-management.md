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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="aef44-103">Administrar el ciclo de vida de canales privados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aef44-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="aef44-104">Aquí encontrará las instrucciones que necesita para administrar el ciclo de vida de los [canales privados](private-channels.md) de su organización.</span><span class="sxs-lookup"><span data-stu-id="aef44-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="aef44-105">Establecer si los miembros del equipo pueden crear canales privados</span><span class="sxs-lookup"><span data-stu-id="aef44-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="aef44-106">Los propietarios del equipo pueden desactivar o activar la posibilidad de que los miembros creen canales privados en la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="aef44-106">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="aef44-107">Para ello, en la pestaña **configuración** del equipo, desactive o desactive **permitir que los miembros creen canales privados**.</span><span class="sxs-lookup"><span data-stu-id="aef44-107">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="aef44-108">Como administrador, puede usar la API de Graph para controlar si los miembros pueden crear canales privados en determinados equipos.</span><span class="sxs-lookup"><span data-stu-id="aef44-108">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="aef44-109">Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aef44-109">Here's an example.</span></span>

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="aef44-110">Establecer si los usuarios de su organización pueden crear canales privados</span><span class="sxs-lookup"><span data-stu-id="aef44-110">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="aef44-111">Como administrador, puede establecer directivas con el centro de administración de Microsoft Teams o PowerShell para controlar los usuarios de su organización que pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="aef44-111">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="aef44-112">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aef44-112">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="aef44-113">Use directivas de Teams para establecer los usuarios de su organización que pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="aef44-113">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="aef44-114">Para obtener más información, vea [Administrar directivas de Teams en Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aef44-114">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="aef44-115">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="aef44-115">Using PowerShell</span></span>

<span data-ttu-id="aef44-116">Use **CsTeamsChannelsPolicy** para establecer qué usuarios de su organización pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="aef44-116">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="aef44-117">Establezca el parámetro **AllowPrivateChannelCreation** en **true** para permitir a los usuarios a quienes les asignan la Directiva crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="aef44-117">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="aef44-118">Establecer el parámetro en **false** desactiva la capacidad de crear canales privados para los usuarios que tienen asignada la Directiva.</span><span class="sxs-lookup"><span data-stu-id="aef44-118">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="aef44-119">Para obtener más información, vea [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="aef44-119">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="aef44-120">Crear un canal privado en nombre de un propietario del equipo</span><span class="sxs-lookup"><span data-stu-id="aef44-120">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="aef44-121">Como administrador, puede usar la API de PowerShell o Graph para crear un canal privado en nombre de un propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="aef44-121">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="aef44-122">Por ejemplo, es posible que desee hacerlo si su organización desea centralizar la creación de canales privados.</span><span class="sxs-lookup"><span data-stu-id="aef44-122">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="aef44-123">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="aef44-123">Using PowerShell</span></span>

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="aef44-124">Usar la API Graph</span><span class="sxs-lookup"><span data-stu-id="aef44-124">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="aef44-125">Obtener una lista de todos los mensajes de canal privado</span><span class="sxs-lookup"><span data-stu-id="aef44-125">Get a list of all private channel messages</span></span>

<span data-ttu-id="aef44-126">Es posible que desee obtener una lista de todos los mensajes y respuestas publicados en un canal privado para archivar y auditar.</span><span class="sxs-lookup"><span data-stu-id="aef44-126">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="aef44-127">A continuación se explica cómo usar la API de Graph para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="aef44-127">Here's how to use Graph API to do this.</span></span>

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="aef44-128">Buscar direcciones URL de SharePoint para todos los canales privados de un equipo</span><span class="sxs-lookup"><span data-stu-id="aef44-128">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="aef44-129">Tanto si desea realizar una búsqueda de exhibición de sitios web o una retención legal en archivos de un canal privado o en crear una aplicación de línea de negocio que coloca los archivos en canales privados específicos, querrá una manera de consultar las colecciones de sitios de SharePoint exclusivas que se crean para cada canal privado.</span><span class="sxs-lookup"><span data-stu-id="aef44-129">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="aef44-130">Como administrador, puede usar los comandos de las API de PowerShell o Graph para consultar estas direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="aef44-130">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="aef44-131">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="aef44-131">Using PowerShell</span></span>

1. <span data-ttu-id="aef44-132">Instale y conéctese al [Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con su cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="aef44-132">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="aef44-133">Ejecute lo siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo.</span><span class="sxs-lookup"><span data-stu-id="aef44-133">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="aef44-134">(Puede encontrar fácilmente el identificador de grupo en el vínculo al equipo).</span><span class="sxs-lookup"><span data-stu-id="aef44-134">(You can easily find the group Id in the link to the team.)</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="aef44-135">Usar la API Graph</span><span class="sxs-lookup"><span data-stu-id="aef44-135">Using Graph API</span></span>

<span data-ttu-id="aef44-136">Puede probar estos comandos en el [Explorador de gráficos](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="aef44-136">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="aef44-137">Use el siguiente procedimiento para obtener la lista de identificadores de canal privado para un equipo dado, donde <group_id> es el identificador de grupo del equipo.</span><span class="sxs-lookup"><span data-stu-id="aef44-137">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="aef44-138">La necesitarás en llamadas posteriores.</span><span class="sxs-lookup"><span data-stu-id="aef44-138">You'll need this in subsequent calls.</span></span> <span data-ttu-id="aef44-139">(Puede encontrar fácilmente el identificador de grupo en el vínculo al equipo).</span><span class="sxs-lookup"><span data-stu-id="aef44-139">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="aef44-140">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="aef44-140">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="aef44-141">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="aef44-141">**Response**</span></span>

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

2. <span data-ttu-id="aef44-142">Para cada canal privado para el que desee obtener la dirección URL de SharePoint, realice la siguiente solicitud &lt;,&gt; donde channel_id es el identificador de canal.</span><span class="sxs-lookup"><span data-stu-id="aef44-142">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="aef44-143">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="aef44-143">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="aef44-144">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="aef44-144">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="aef44-145">Enumerar y actualizar los roles de propietarios y miembros en un canal privado</span><span class="sxs-lookup"><span data-stu-id="aef44-145">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="aef44-146">Es posible que desee enumerar los propietarios y miembros de un canal privado para decidir si necesita promover a un propietario a determinados miembros del canal privado.</span><span class="sxs-lookup"><span data-stu-id="aef44-146">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="aef44-147">Esto puede ocurrir cuando tiene propietarios de canales privados que han abandonado la organización y el canal privado requiere ayuda del administrador para reclamar la propiedad del canal.</span><span class="sxs-lookup"><span data-stu-id="aef44-147">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="aef44-148">Como administrador, puede usar los comandos de las API de PowerShell o Graph para consultar estas direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="aef44-148">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="aef44-149">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="aef44-149">Using PowerShell</span></span>

1. <span data-ttu-id="aef44-150">Instale y conéctese al [módulo de Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) con su cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="aef44-150">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="aef44-151">Ejecute lo siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo y &lt;channel_id&gt; es el identificador de canal.</span><span class="sxs-lookup"><span data-stu-id="aef44-151">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="aef44-152">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="aef44-152">**Request**</span></span>

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="aef44-153">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="aef44-153">**Response**</span></span>

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

3. <span data-ttu-id="aef44-154">Promociona un miembro a un propietario.</span><span class="sxs-lookup"><span data-stu-id="aef44-154">Promote a member to an owner.</span></span>

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="aef44-155">Usar la API Graph</span><span class="sxs-lookup"><span data-stu-id="aef44-155">Using Graph API</span></span>

<span data-ttu-id="aef44-156">Puede probar estos comandos en el [Explorador de gráficos](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="aef44-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="aef44-157">Use el siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo y &lt;channel_id&gt; es el identificador de canal.</span><span class="sxs-lookup"><span data-stu-id="aef44-157">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="aef44-158">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="aef44-158">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="aef44-159">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="aef44-159">**Response**</span></span>

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
2.  <span data-ttu-id="aef44-160">Use el siguiente procedimiento para promocionar el miembro a propietario, &lt;donde&gt;group_id &lt;,&gt;channel_id e &lt;ID&gt; se devuelven de la llamada anterior.</span><span class="sxs-lookup"><span data-stu-id="aef44-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="aef44-161">Ten en &lt;cuenta&gt; que &lt;el&gt; identificador y el userId devueltos por la llamada anterior no son iguales y no son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="aef44-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="aef44-162">Asegúrate de usar &lt;el identificador&gt;.</span><span class="sxs-lookup"><span data-stu-id="aef44-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="aef44-163">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="aef44-163">**Request**</span></span>

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="aef44-164">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="aef44-164">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="aef44-165">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aef44-165">Related topics</span></span>

- [<span data-ttu-id="aef44-166">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="aef44-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="aef44-167">Usar la API de Microsoft Graph para trabajar con equipos</span><span class="sxs-lookup"><span data-stu-id="aef44-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="aef44-168">Lista de canales</span><span class="sxs-lookup"><span data-stu-id="aef44-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="aef44-169">Crear canal</span><span class="sxs-lookup"><span data-stu-id="aef44-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="aef44-170">Agregar miembro al canal</span><span class="sxs-lookup"><span data-stu-id="aef44-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="aef44-171">Actualizar miembro en el canal</span><span class="sxs-lookup"><span data-stu-id="aef44-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="aef44-172">Quitar miembro de un canal</span><span class="sxs-lookup"><span data-stu-id="aef44-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)