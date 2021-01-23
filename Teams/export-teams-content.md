---
title: Exportar contenido con las API de exportación de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: En este artículo, aprenderá a exportar contenido de Teams mediante las API de exportación de Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4ea2d747d40c221d9e99b51fc7b15da8e2cdd12
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944605"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="26cea-103">Exportar contenido con las API de exportación de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="26cea-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="26cea-104">Las API de exportación de Teams le permiten exportar mensajes 1:1, chats grupales y canales desde Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="26cea-104">Teams Export APIs allow you to export 1:1, group chat, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="26cea-105">Si su organización necesita exportar mensajes de Microsoft Teams, puede extraerlos mediante las API de exportación de Teams.</span><span class="sxs-lookup"><span data-stu-id="26cea-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="26cea-106">*El mensaje de* chat representa un mensaje de chat individual dentro de [un canal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) o [chat.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="26cea-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="26cea-107">El mensaje de chat puede ser un mensaje de chat raíz o parte de un hilo de respuesta definido por la propiedad **replyToId** en el mensaje de chat.</span><span class="sxs-lookup"><span data-stu-id="26cea-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="26cea-108">A continuación se muestran algunos ejemplos sobre cómo puede usar estas API de exportación:</span><span class="sxs-lookup"><span data-stu-id="26cea-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="26cea-109">**Ejemplo 1:** Si ha habilitado Microsoft Teams en su organización y desea exportar todos los mensajes de Microsoft Teams a la fecha mediante programación pasando el intervalo de fechas de un usuario o equipo determinado.</span><span class="sxs-lookup"><span data-stu-id="26cea-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="26cea-110">**Ejemplo 2:** Si desea exportar mediante programación todos los mensajes de usuario o equipo diariamente proporcionando un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="26cea-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="26cea-111">Las API de exportación pueden recuperar todos los mensajes creados o actualizados durante el intervalo de fechas especificado.</span><span class="sxs-lookup"><span data-stu-id="26cea-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="26cea-112">¿Qué se admite en las API de exportación de Teams?</span><span class="sxs-lookup"><span data-stu-id="26cea-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="26cea-113">**Mensaje de exportación en masa de Teams:** Las API de exportación de Teams admiten hasta 200 RPS por aplicación por espacio empresarial y 600 RPS para una aplicación, con estos límites debería poder exportar mensajes de Teams en masa.</span><span class="sxs-lookup"><span data-stu-id="26cea-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="26cea-114">**Contexto de la** aplicación: para llamar a Microsoft Graph, la aplicación debe adquirir un token de acceso de la plataforma de identidad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26cea-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="26cea-115">El token de acceso contiene información sobre la aplicación y los permisos que tiene para los recursos y las API disponibles a través de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="26cea-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="26cea-116">Para obtener un token de acceso, la aplicación debe estar registrada con la plataforma de identidad de Microsoft y estar autorizada por un usuario o un administrador para obtener acceso a los recursos de Microsoft Graph que necesita.</span><span class="sxs-lookup"><span data-stu-id="26cea-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="26cea-117">Si ya está familiarizado con la integración de una aplicación [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) con la plataforma de identidad de Microsoft para obtener tokens, consulte la sección Pasos siguientes para obtener información y ejemplos específicos de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="26cea-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="26cea-118">**Entorno híbrido:** Export API support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span><span class="sxs-lookup"><span data-stu-id="26cea-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="26cea-119">Se podrá obtener acceso a todos los mensajes que envíen los usuarios configurados para el entorno híbrido mediante las API de exportación.</span><span class="sxs-lookup"><span data-stu-id="26cea-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="26cea-120">**Mensajes eliminados por el usuario:** Se puede acceder a los mensajes eliminados por el usuario del cliente de Teams mediante las API de exportación hasta 30 días desde el momento de la eliminación.</span><span class="sxs-lookup"><span data-stu-id="26cea-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="26cea-121">**Datos adjuntos de mensajes:** Las API de exportación incluyen los vínculos a los datos adjuntos que se envían como parte de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="26cea-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="26cea-122">Con exportar API, puede recuperar los archivos adjuntos en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="26cea-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="26cea-123">**Propiedades de los mensajes de chat:** Consulte aquí la lista completa de propiedades que admiten las API de exportación [de](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)Teams.</span><span class="sxs-lookup"><span data-stu-id="26cea-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="26cea-124">Cómo acceder a las API de exportación de Teams</span><span class="sxs-lookup"><span data-stu-id="26cea-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="26cea-125">**El ejemplo 1** es una consulta sencilla para recuperar todos los mensajes de un usuario o equipo sin ningún filtro:</span><span class="sxs-lookup"><span data-stu-id="26cea-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- <span data-ttu-id="26cea-126">**El ejemplo 2** es una consulta de ejemplo para recuperar todos los mensajes de un usuario o equipo especificando filtros de fecha y hora y los 50 mensajes superiores:</span><span class="sxs-lookup"><span data-stu-id="26cea-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>The API returns response with next page link in case of multiple results. For getting next set of results, simply call GET on the url from @odata.nextlink. If @odata.nextlink is not present or null then all messages are retrieved.

## Prerequisites to access Teams Export APIs 

- Teams Export APIs are currently in preview. It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs. In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.
- Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs. Export APIs require that you have additional validation, beyond permissions and consent, before you can use them. To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).
- Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator. The following permissions are needed:

    - *Chat.Read.All*: enables access to all 1:1 and Group chat messages 
    - *User.Read.All*: enables access to the list of users for a tenant 

## JSON representation

The following example is a JSON representation of the resource:

Namespace: microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
><span data-ttu-id="26cea-127">Para obtener más información sobre el recurso chatMessage, vea el artículo sobre el [tipo de recurso chatMessage.](https://docs.microsoft.com/graph/api/resources/chatmessage)</span><span class="sxs-lookup"><span data-stu-id="26cea-127">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
