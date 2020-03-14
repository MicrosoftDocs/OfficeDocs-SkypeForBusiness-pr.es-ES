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
ms.openlocfilehash: 317cded1be30beac8fefbb579d5f0c24258f2fa1
ms.sourcegitcommit: a4fd238de09366d6ed33d72c908faff812da11a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637207"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="42420-103">Administrar el ciclo de vida de canales privados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42420-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="42420-104">Aquí encontrará las instrucciones que necesita para administrar el ciclo de vida de los [canales privados](private-channels.md) de su organización.</span><span class="sxs-lookup"><span data-stu-id="42420-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42420-105">Si está usando los pasos de PowerShell de este artículo para administrar canales privados, debe instalar y usar la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42420-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="42420-106">Para conocer los pasos para realizar esto, consulte [instalar el módulo de PowerShell más reciente de la galería de pruebas de PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span><span class="sxs-lookup"><span data-stu-id="42420-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="42420-107">La última versión disponible públicamente del módulo de PowerShell de Teams (actualmente [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) no admite la administración de canales privados.</span><span class="sxs-lookup"><span data-stu-id="42420-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="42420-108">Establecer si los miembros del equipo pueden crear canales privados</span><span class="sxs-lookup"><span data-stu-id="42420-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="42420-109">Los propietarios del equipo pueden desactivar o activar la posibilidad de que los miembros creen canales privados en la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="42420-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="42420-110">Para ello, en la pestaña **configuración** del equipo, desactive o desactive **permitir que los miembros creen canales privados**.</span><span class="sxs-lookup"><span data-stu-id="42420-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="42420-111">Como administrador, puede usar la API de Graph para controlar si los miembros pueden crear canales privados en determinados equipos.</span><span class="sxs-lookup"><span data-stu-id="42420-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="42420-112">Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="42420-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="42420-113">Establecer si los usuarios de su organización pueden crear canales privados</span><span class="sxs-lookup"><span data-stu-id="42420-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="42420-114">Como administrador, puede establecer directivas con el centro de administración de Microsoft Teams o PowerShell para controlar los usuarios de su organización que pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="42420-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="42420-115">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42420-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="42420-116">Use directivas de Teams para establecer los usuarios de su organización que pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="42420-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="42420-117">Para obtener más información, vea [Administrar directivas de Teams en Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="42420-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="42420-118">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="42420-118">Using PowerShell</span></span>

<span data-ttu-id="42420-119">Use **CsTeamsChannelsPolicy** para establecer qué usuarios de su organización pueden crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="42420-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="42420-120">Establezca el parámetro **AllowPrivateChannelCreation** en **true** para permitir a los usuarios a quienes les asignan la Directiva crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="42420-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="42420-121">Establecer el parámetro en **false** desactiva la capacidad de crear canales privados para los usuarios que tienen asignada la Directiva.</span><span class="sxs-lookup"><span data-stu-id="42420-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="42420-122">Para obtener más información, vea [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="42420-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="42420-123">Crear un canal privado en nombre de un propietario del equipo</span><span class="sxs-lookup"><span data-stu-id="42420-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="42420-124">Como administrador, puede usar la API de PowerShell o Graph para crear un canal privado en nombre de un propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="42420-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="42420-125">Por ejemplo, es posible que desee hacerlo si su organización desea centralizar la creación de canales privados.</span><span class="sxs-lookup"><span data-stu-id="42420-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="42420-126">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="42420-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="42420-127">Usar la API Graph</span><span class="sxs-lookup"><span data-stu-id="42420-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="42420-128">Obtener una lista de todos los mensajes de canal privado</span><span class="sxs-lookup"><span data-stu-id="42420-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="42420-129">Es posible que desee obtener una lista de todos los mensajes y respuestas publicados en un canal privado para archivar y auditar.</span><span class="sxs-lookup"><span data-stu-id="42420-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="42420-130">A continuación se explica cómo usar la API de Graph para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="42420-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="42420-131">Buscar direcciones URL de SharePoint para todos los canales privados de un equipo</span><span class="sxs-lookup"><span data-stu-id="42420-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="42420-132">Tanto si desea realizar una búsqueda de exhibición de sitios web o una retención legal en archivos de un canal privado o en crear una aplicación de línea de negocio que coloca los archivos en canales privados específicos, querrá una manera de consultar las colecciones de sitios de SharePoint exclusivas que se crean para cada canal privado.</span><span class="sxs-lookup"><span data-stu-id="42420-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="42420-133">Como administrador, puede usar los comandos de las API de PowerShell o Graph para consultar estas direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="42420-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="42420-134">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="42420-134">Using PowerShell</span></span>

1. <span data-ttu-id="42420-135">Instale y conéctese al [Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con su cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="42420-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="42420-136">Ejecute lo siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo.</span><span class="sxs-lookup"><span data-stu-id="42420-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="42420-137">(Puede encontrar fácilmente el identificador de grupo en el vínculo al equipo).</span><span class="sxs-lookup"><span data-stu-id="42420-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="42420-138">Usar la API Graph</span><span class="sxs-lookup"><span data-stu-id="42420-138">Using Graph API</span></span>

<span data-ttu-id="42420-139">Puede probar estos comandos en el [Explorador de gráficos](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="42420-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="42420-140">Use el siguiente procedimiento para obtener la lista de identificadores de canal privado para un equipo determinado, donde <group_id> es el identificador de grupo del equipo.</span><span class="sxs-lookup"><span data-stu-id="42420-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="42420-141">La necesitarás en llamadas posteriores.</span><span class="sxs-lookup"><span data-stu-id="42420-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="42420-142">(Puede encontrar fácilmente el identificador de grupo en el vínculo al equipo).</span><span class="sxs-lookup"><span data-stu-id="42420-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="42420-143">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="42420-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="42420-144">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="42420-144">**Response**</span></span>

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

2. <span data-ttu-id="42420-145">Para cada canal privado para el que desee obtener la dirección URL de SharePoint, realice la siguiente solicitud &lt;,&gt; donde channel_id es el identificador de canal.</span><span class="sxs-lookup"><span data-stu-id="42420-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="42420-146">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="42420-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="42420-147">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="42420-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="42420-148">Enumerar y actualizar los roles de propietarios y miembros en un canal privado</span><span class="sxs-lookup"><span data-stu-id="42420-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="42420-149">Es posible que desee enumerar los propietarios y miembros de un canal privado para decidir si necesita promover a un propietario a determinados miembros del canal privado.</span><span class="sxs-lookup"><span data-stu-id="42420-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="42420-150">Esto puede ocurrir cuando tiene propietarios de canales privados que han abandonado la organización y el canal privado requiere ayuda del administrador para reclamar la propiedad del canal.</span><span class="sxs-lookup"><span data-stu-id="42420-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="42420-151">Como administrador, puede usar los comandos de las API de PowerShell o Graph para consultar estas direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="42420-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="42420-152">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="42420-152">Using PowerShell</span></span>

1. <span data-ttu-id="42420-153">Ejecute lo siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo y &lt;channel_name&gt; es el nombre de canal.</span><span class="sxs-lookup"><span data-stu-id="42420-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="42420-154">Promociona un miembro a un propietario.</span><span class="sxs-lookup"><span data-stu-id="42420-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="42420-155">Usar la API Graph</span><span class="sxs-lookup"><span data-stu-id="42420-155">Using Graph API</span></span>

<span data-ttu-id="42420-156">Puede probar estos comandos en el [Explorador de gráficos](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="42420-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="42420-157">Use lo siguiente, donde &lt;group_id&gt; es el identificador de grupo del equipo y &lt;channel_id&gt; es el identificador de canal.</span><span class="sxs-lookup"><span data-stu-id="42420-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="42420-158">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="42420-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="42420-159">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="42420-159">**Response**</span></span>

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
2.  <span data-ttu-id="42420-160">Use el siguiente procedimiento para promocionar el miembro a propietario, &lt;donde&gt;group_id &lt;,&gt;channel_id e &lt;ID&gt; se devuelven desde la llamada anterior.</span><span class="sxs-lookup"><span data-stu-id="42420-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="42420-161">Ten en &lt;cuenta&gt; que &lt;el&gt; identificador y el userId devueltos por la llamada anterior no son iguales y no son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="42420-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="42420-162">Asegúrate de usar &lt;el identificador&gt;.</span><span class="sxs-lookup"><span data-stu-id="42420-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="42420-163">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="42420-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="42420-164">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="42420-164">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="42420-165">Módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="42420-165">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="42420-166">Instale el módulo de PowerShell más reciente de la galería de pruebas de PowerShell</span><span class="sxs-lookup"><span data-stu-id="42420-166">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="42420-167">La última versión disponible públicamente del módulo de PowerShell de Teams (actualmente [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) no admite la administración de canales privados.</span><span class="sxs-lookup"><span data-stu-id="42420-167">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span> <span data-ttu-id="42420-168">Siga estos pasos para instalar la última versión del módulo de PowerShell de Teams con compatibilidad de canal privado (actualmente 1.0.18) de la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42420-168">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.18) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="42420-169">No instale el módulo de Teams PowerShell desde la galería de pruebas de PowerShell en paralelo con una versión del módulo de la galería de PowerShell pública.</span><span class="sxs-lookup"><span data-stu-id="42420-169">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="42420-170">Siga estos pasos para desinstalar primero el módulo de PowerShell de Teams de la galería de PowerShell pública y, a continuación, instale la última versión del módulo desde la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42420-170">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="42420-171">Cierre todas las sesiones de PowerShell existentes.</span><span class="sxs-lookup"><span data-stu-id="42420-171">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="42420-172">Inicie una nueva instancia del módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42420-172">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="42420-173">Ejecute lo siguiente para desinstalar el módulo de PowerShell de Teams de la galería pública de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="42420-173">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="42420-174">Cierre todas las sesiones de PowerShell existentes.</span><span class="sxs-lookup"><span data-stu-id="42420-174">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="42420-175">Inicie el módulo de Windows PowerShell de nuevo y, a continuación, ejecute lo siguiente para registrar la galería de pruebas de PowerShell como una fuente de confianza:</span><span class="sxs-lookup"><span data-stu-id="42420-175">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="42420-176">Ejecute lo siguiente para instalar el módulo de PowerShell más reciente de la galería de pruebas de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="42420-176">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="42420-177">Ejecute lo siguiente para comprobar que se ha instalado correctamente la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="42420-177">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="42420-178">Actualice a la última versión del módulo de PowerShell de Teams desde la galería de pruebas de PowerShell</span><span class="sxs-lookup"><span data-stu-id="42420-178">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="42420-179">Si ya ha instalado el módulo de Teams PowerShell desde la galería de pruebas de PowerShell, siga estos pasos para actualizar a la última versión.</span><span class="sxs-lookup"><span data-stu-id="42420-179">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="42420-180">Cierre todas las sesiones de PowerShell existentes.</span><span class="sxs-lookup"><span data-stu-id="42420-180">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="42420-181">Inicie una nueva instancia del módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42420-181">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="42420-182">Ejecute lo siguiente para actualizar la versión del módulo de PowerShell instalada actualmente desde la galería de pruebas de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="42420-182">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="42420-183">Ejecute lo siguiente para comprobar que se ha instalado correctamente la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="42420-183">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="42420-184">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="42420-184">Related topics</span></span>

- [<span data-ttu-id="42420-185">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="42420-185">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="42420-186">Usar la API de Microsoft Graph para trabajar con equipos</span><span class="sxs-lookup"><span data-stu-id="42420-186">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="42420-187">Lista de canales</span><span class="sxs-lookup"><span data-stu-id="42420-187">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="42420-188">Crear canal</span><span class="sxs-lookup"><span data-stu-id="42420-188">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="42420-189">Agregar miembro al canal</span><span class="sxs-lookup"><span data-stu-id="42420-189">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="42420-190">Actualizar miembro en el canal</span><span class="sxs-lookup"><span data-stu-id="42420-190">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="42420-191">Quitar miembro de un canal</span><span class="sxs-lookup"><span data-stu-id="42420-191">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
