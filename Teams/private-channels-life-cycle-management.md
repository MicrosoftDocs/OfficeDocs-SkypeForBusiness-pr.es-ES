---
title: Administrar los canales privados en Microsoft Teams con la API de Graph
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
description: Obtenga información sobre cómo administrar los canales privados de su organización con la API de Graph.
ms.openlocfilehash: 854e8721dac7d49e258db42845b84480955bfec7
ms.sourcegitcommit: 44bd56f67b1ad85ef8c21bb30d5b0d47e5a80339
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49772043"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="ed121-103">Administrar el ciclo de vida de los canales privados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed121-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="ed121-104">Aquí encontrará las instrucciones que necesita para administrar el uso de la API Graph para administrar los [canales privados](https://docs.microsoft.com/microsoftteams/private-channels) de los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="ed121-104">Here you'll find the guidance you need to manage use the Graph API to manage [Teams private channels](https://docs.microsoft.com/microsoftteams/private-channels) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="ed121-105">Configurar si los propietarios y miembros pueden crear canales privados</span><span class="sxs-lookup"><span data-stu-id="ed121-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="ed121-106">Como administrador, puede usar la API de Graph para controlar si los miembros pueden crear canales privados en un equipo específico.</span><span class="sxs-lookup"><span data-stu-id="ed121-106">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="ed121-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ed121-107">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="ed121-108">Crear un canal privado en nombre de un propietario del equipo</span><span class="sxs-lookup"><span data-stu-id="ed121-108">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="ed121-109">Como administrador, puede usar la API Graph para crear un canal privado en nombre de un propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="ed121-109">As an admin, you can use the Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="ed121-110">Por ejemplo, quizá quiera hacerlo si su organización pretende centralizar la creación de canales privados.</span><span class="sxs-lookup"><span data-stu-id="ed121-110">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="ed121-111">Obtenga una lista de todos los mensajes del canal privado</span><span class="sxs-lookup"><span data-stu-id="ed121-111">Get a list of all private channel messages</span></span>

<span data-ttu-id="ed121-112">Quizá quiera obtener una lista de todos los mensajes y las respuestas de un canal privado para poder archivarlos y hacer una auditoría.</span><span class="sxs-lookup"><span data-stu-id="ed121-112">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="ed121-113">Aquí se muestra cómo usar la API de Graph para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ed121-113">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="ed121-114">Encuentre las direcciones URL de SharePoint para todos los canales privados en un equipo</span><span class="sxs-lookup"><span data-stu-id="ed121-114">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="ed121-115">Tanto si quieres hacer una exhibición de documentos electrónicos o archivos de una suspensión por litigio en un canal privado o quieres diseñar una aplicación personalizada que ubique los archivos en ciertos canales privados, querrás una manera de consultar las únicas colecciones de sitios SharePoint que se han creado para cada canal privado.</span><span class="sxs-lookup"><span data-stu-id="ed121-115">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="ed121-116">Como administrador, puede usar los comandos de las API de Graph para consultar estas direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="ed121-116">As an admin, you can use Graph APIs commands to query these URLs.</span></span>

<span data-ttu-id="ed121-117">Puede probar estos comandos a través del [Explorador de Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="ed121-117">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="ed121-118">Use lo siguiente para obtener la lista de los identificadores de los canales privados para enviarlos al equipo, donde <group_id> es el ID del grupo del equipo.</span><span class="sxs-lookup"><span data-stu-id="ed121-118">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="ed121-119">Lo necesitará en las siguientes llamadas.</span><span class="sxs-lookup"><span data-stu-id="ed121-119">You'll need this in subsequent calls.</span></span> <span data-ttu-id="ed121-120">(Puede encontrar fácilmente el ID del grupo en el enlace del equipo.)</span><span class="sxs-lookup"><span data-stu-id="ed121-120">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="ed121-121">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="ed121-121">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="ed121-122">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="ed121-122">**Response**</span></span>

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

2. <span data-ttu-id="ed121-123">Para cada canal privado del que quiera obtener la dirección URL de SharePoint, haga la siguiente solicitud, donde &lt;channel_id&gt; es el ID del canal.</span><span class="sxs-lookup"><span data-stu-id="ed121-123">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="ed121-124">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="ed121-124">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="ed121-125">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="ed121-125">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="ed121-126">Lista y actualización de roles de los propietarios y los miembros de un canal privado</span><span class="sxs-lookup"><span data-stu-id="ed121-126">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="ed121-127">Quizá quiera extraer una lista de los propietarios y los miembros de un canal privado para decidir si necesita ascender a ciertos miembros de un canal privado al rol de propietario.</span><span class="sxs-lookup"><span data-stu-id="ed121-127">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="ed121-128">Esto puede ocurrir cuando tienes propietarios de canales privados que han dejado la organización y el canal privado requiere ayuda administrativa para reclamar la propiedad del mismo.</span><span class="sxs-lookup"><span data-stu-id="ed121-128">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="ed121-129">Como administrador, puede usar la API Graph para realizar estas acciones.</span><span class="sxs-lookup"><span data-stu-id="ed121-129">As an admin, you can use the Graph API to perform these actions.</span></span>

<span data-ttu-id="ed121-130">Puede probar estos comandos a través del [Explorador de Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="ed121-130">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="ed121-131">Use lo siguiente, donde &lt;group_id&gt; es el ID de grupo del equipo y &lt;channel_id&gt; es el ID del canal.</span><span class="sxs-lookup"><span data-stu-id="ed121-131">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="ed121-132">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="ed121-132">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="ed121-133">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="ed121-133">**Response**</span></span>

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
2. <span data-ttu-id="ed121-134">Use lo siguiente para ascender un miembro a propietario, donde &lt;group_id&gt;, &lt;channel_id&gt; e &lt;id&gt; se obtienen de llamadas anteriores.</span><span class="sxs-lookup"><span data-stu-id="ed121-134">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="ed121-135">Tenga en cuanta que &lt;id&gt; y &lt;userId&gt; que se obtienen de llamadas anteriores no son los mismos y no son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="ed121-135">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="ed121-136">Asegúrese de que usa el &lt;id&gt;.</span><span class="sxs-lookup"><span data-stu-id="ed121-136">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="ed121-137">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="ed121-137">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="ed121-138">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="ed121-138">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="ed121-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ed121-139">Related topics</span></span>

[<span data-ttu-id="ed121-140">Usar la API de Microsoft Graph para trabajar con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed121-140">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[<span data-ttu-id="ed121-141">Enumerar canales</span><span class="sxs-lookup"><span data-stu-id="ed121-141">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)

[<span data-ttu-id="ed121-142">Crear un canal</span><span class="sxs-lookup"><span data-stu-id="ed121-142">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)

[<span data-ttu-id="ed121-143">Agregar un miembro al canal</span><span class="sxs-lookup"><span data-stu-id="ed121-143">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)

[<span data-ttu-id="ed121-144">Actualizar un miembro del canal</span><span class="sxs-lookup"><span data-stu-id="ed121-144">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)

[<span data-ttu-id="ed121-145">Quitar un miembro del canal</span><span class="sxs-lookup"><span data-stu-id="ed121-145">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
