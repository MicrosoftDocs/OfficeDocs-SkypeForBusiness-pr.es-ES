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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="6cfc7-103">Administrar el ciclo de vida de los canales privados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="6cfc7-104">Aquí encontrará las instrucciones para administrar el ciclo de vida de los [canales privados](private-channels.md) de su organización.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cfc7-105">Si está usando los pasos de PowerShell de este artículo para administrar canales privados, debe instalar y usar el módulo versión preliminar pública PowerShell de Teams desde la [Galería de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="6cfc7-106">Consulte [Instalar PowerShell para Microsoft Teams](teams-powershell-install.md) para seguir los pasos de instalación del módulo. </span><span class="sxs-lookup"><span data-stu-id="6cfc7-106">For steps on how to install the module, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span> <span data-ttu-id="6cfc7-107">El último módulo de PowerShell para Teams de disponibilidad general no admite la administración de canales privados.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-107">The latest General Availability Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="6cfc7-108">Configurar si los propietarios y miembros pueden crear canales privados</span><span class="sxs-lookup"><span data-stu-id="6cfc7-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="6cfc7-109">Los propietarios del equipo pueden activar o desactivar la posibilidad de que los miembros puedan crear canales privados en la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="6cfc7-110">Para ello, en la pestaña **Configuración** del equipo, se puede activar o desactivar el **permitir que los miembros puedan crear canales privados**.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="6cfc7-111">Como administrador, puede usar la API de Graph para controlar si los miembros pueden crear canales privados en un equipo específico.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="6cfc7-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6cfc7-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="6cfc7-113">Configurar si los usuarios de la organización pueden crear canales privados</span><span class="sxs-lookup"><span data-stu-id="6cfc7-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="6cfc7-114">Como administrador, puede establecer directivas mediante el Centro de administración de Microsoft Teams o PowerShell para controlar qué usuarios de su organización pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6cfc7-115">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6cfc7-116">Use directivas para controlar qué usuarios de su organización pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="6cfc7-117">Para obtener más información, consulte [Administrar directivas de equipos en Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6cfc7-118">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cfc7-118">Using PowerShell</span></span>

<span data-ttu-id="6cfc7-119">Use **CsTeamsChannelsPolicy** para controlar qué usuarios de su organización pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="6cfc7-120">Configure el parámetro **AllowPrivateChannelCreation** como **verdadero** para permitir a los usuarios que se asignen en la directiva puedan crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="6cfc7-121">Configura el parámetro como **falso** para desactivar el que puedan crear canales privados los usuarios que se asignen en la directiva.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="6cfc7-122">Para obtener más información, consulte [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="6cfc7-123">Crear un canal privado en nombre de un propietario del equipo</span><span class="sxs-lookup"><span data-stu-id="6cfc7-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="6cfc7-124">Como administrador, puede usar PowerShell o la API de Graph para crear un canal privado en nombre de un propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="6cfc7-125">Por ejemplo, quizá quiera hacerlo si su organización pretende centralizar la creación de canales privados.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6cfc7-126">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cfc7-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="6cfc7-127">Con la API de Graph</span><span class="sxs-lookup"><span data-stu-id="6cfc7-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="6cfc7-128">Obtenga una lista de todos los mensajes del canal privado</span><span class="sxs-lookup"><span data-stu-id="6cfc7-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="6cfc7-129">Quizá quiera obtener una lista de todos los mensajes y las respuestas de un canal privado para poder archivarlos y hacer una auditoría.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="6cfc7-130">Aquí se muestra cómo usar la API de Graph para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="6cfc7-131">Encuentre las direcciones URL de SharePoint para todos los canales privados en un equipo</span><span class="sxs-lookup"><span data-stu-id="6cfc7-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="6cfc7-132">Tanto si quieres hacer una exhibición de documentos electrónicos o archivos de una suspensión por litigio en un canal privado o quieres diseñar una aplicación personalizada que ubique los archivos en ciertos canales privados, querrás una manera de consultar las únicas colecciones de sitios SharePoint que se han creado para cada canal privado.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="6cfc7-133">Como administrador, puede usar PowerShell o los comandos de la API de Graph para consultar estas direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6cfc7-134">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cfc7-134">Using PowerShell</span></span>

1. <span data-ttu-id="6cfc7-135">Instale y conéctese a la [consola de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con su cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="6cfc7-136">Ejecute lo siguiente, donde &lt;group_id&gt; es el ID de Grupo del equipo.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="6cfc7-137">(Puede encontrar fácilmente el ID del Grupo en el enlace del equipo.)</span><span class="sxs-lookup"><span data-stu-id="6cfc7-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="6cfc7-138">Con la API de Graph</span><span class="sxs-lookup"><span data-stu-id="6cfc7-138">Using Graph API</span></span>

<span data-ttu-id="6cfc7-139">Puede probar estos comandos a través del [Explorador de Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="6cfc7-140">Use lo siguiente para obtener la lista de los identificadores de los canales privados para enviarlos al equipo, donde <group_id> es el ID del grupo del equipo.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="6cfc7-141">Lo necesitará en las siguientes llamadas.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="6cfc7-142">(Puede encontrar fácilmente el ID del grupo en el enlace del equipo.)</span><span class="sxs-lookup"><span data-stu-id="6cfc7-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="6cfc7-143">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="6cfc7-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="6cfc7-144">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="6cfc7-144">**Response**</span></span>

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

2. <span data-ttu-id="6cfc7-145">Para cada canal privado del que quiera obtener la dirección URL de SharePoint, haga la siguiente solicitud, donde &lt;channel_id&gt; es el ID del canal.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="6cfc7-146">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="6cfc7-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="6cfc7-147">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="6cfc7-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="6cfc7-148">Lista y actualización de roles de los propietarios y los miembros de un canal privado</span><span class="sxs-lookup"><span data-stu-id="6cfc7-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="6cfc7-149">Quizá quiera extraer una lista de los propietarios y los miembros de un canal privado para decidir si necesita ascender a ciertos miembros de un canal privado al rol de propietario.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="6cfc7-150">Esto puede ocurrir cuando tienes propietarios de canales privados que han dejado la organización y el canal privado requiere ayuda administrativa para reclamar la propiedad del mismo.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="6cfc7-151">Como administrador, puede usar el Centro de administración de Microsoft Teams, PowerShell o la API de Graph para llevar a cabo estas acciones.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-151">As an admin, you can use the Microsoft Teams admin center, PowerShell, or Graph API to perform these actions.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6cfc7-152">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-152">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6cfc7-153">Para obtener más información sobre cómo administrar los miembros del equipo con el Centro de administración de Microsoft Teams, consulte [Administrar equipos en el Centro de administración de Microsoft Teams](manage-teams-in-modern-portal.md).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-153">To learn how to manage team members using the Microsoft Teams admin center, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6cfc7-154">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cfc7-154">Using PowerShell</span></span>

1. <span data-ttu-id="6cfc7-155">Ejecute lo siguiente, donde &lt;group_id&gt; es el ID de grupo del equipo y &lt;channel_name&gt; es el nombre del canal.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-155">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="6cfc7-156">Ascender a un miembro al rol de administrador</span><span class="sxs-lookup"><span data-stu-id="6cfc7-156">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="6cfc7-157">Con la API de Graph</span><span class="sxs-lookup"><span data-stu-id="6cfc7-157">Using Graph API</span></span>

<span data-ttu-id="6cfc7-158">Puede probar estos comandos a través del [Explorador de Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-158">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="6cfc7-159">Use lo siguiente, donde &lt;group_id&gt; es el ID de grupo del equipo y &lt;channel_id&gt; es el ID del canal.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-159">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="6cfc7-160">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="6cfc7-160">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="6cfc7-161">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="6cfc7-161">**Response**</span></span>

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
2. <span data-ttu-id="6cfc7-162">Use lo siguiente para ascender un miembro a propietario, donde &lt;group_id&gt;, &lt;channel_id&gt; e &lt;id&gt; se obtienen de llamadas anteriores.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-162">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="6cfc7-163">Tenga en cuanta que &lt;id&gt; y &lt;userId&gt; que se obtienen de llamadas anteriores no son los mismos y no son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-163">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="6cfc7-164">Asegúrese de que usa el &lt;id&gt;.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-164">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="6cfc7-165">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="6cfc7-165">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="6cfc7-166">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="6cfc7-166">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="6cfc7-167">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6cfc7-167">Related topics</span></span>

- [<span data-ttu-id="6cfc7-168">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-168">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="6cfc7-169">Usar la API de Microsoft Graph para trabajar con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-169">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="6cfc7-170">Enumerar canales</span><span class="sxs-lookup"><span data-stu-id="6cfc7-170">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="6cfc7-171">Crear un canal</span><span class="sxs-lookup"><span data-stu-id="6cfc7-171">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="6cfc7-172">Agregar un miembro al canal</span><span class="sxs-lookup"><span data-stu-id="6cfc7-172">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="6cfc7-173">Actualizar un miembro del canal</span><span class="sxs-lookup"><span data-stu-id="6cfc7-173">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="6cfc7-174">Quitar un miembro del canal</span><span class="sxs-lookup"><span data-stu-id="6cfc7-174">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
