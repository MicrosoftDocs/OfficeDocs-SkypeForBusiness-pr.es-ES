---
title: Exportar contenido con las Microsoft Teams Exportar API
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: En este artículo, aprenderá a exportar contenido Teams mediante las Microsoft Teams Exportar API.
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
ms.openlocfilehash: f2e7ccaac78cd7e96581dc1d9371fc9eef096265
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717981"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="e3ee0-103">Exportar contenido con las Microsoft Teams Exportar API</span><span class="sxs-lookup"><span data-stu-id="e3ee0-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="e3ee0-104">Teams Las API de exportación le permiten exportar 1:1, chat grupal, chats de reunión y canales de mensajes desde Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-104">Teams Export APIs allow you to export 1:1, group chat, meeting chats, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="e3ee0-105">Si su organización necesita exportar Microsoft Teams mensajes, puede extraerlos con Teams Exportar API.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="e3ee0-106">*Mensaje de chat* representa un mensaje de chat individual dentro de [un canal](/graph/api/resources/channel?view=graph-rest-beta) o [chat.](/graph/api/resources/chat?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="e3ee0-106">*Chat Message* represents an individual chat message within a [channel](/graph/api/resources/channel?view=graph-rest-beta) or [chat](/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="e3ee0-107">El mensaje de chat puede ser un mensaje de chat raíz o parte de un hilo de respuesta definido por la **propiedad replyToId** del mensaje de chat.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="e3ee0-108">A continuación se muestran algunos ejemplos sobre cómo puede usar estas API de exportación:</span><span class="sxs-lookup"><span data-stu-id="e3ee0-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="e3ee0-109">**Ejemplo 1:** Si ha habilitado Microsoft Teams en su organización y desea exportar todos los mensajes de Microsoft Teams a la fecha mediante programación pasando el intervalo de fechas para un usuario o equipo determinado.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="e3ee0-110">**Ejemplo 2:** Si desea exportar todos los mensajes de usuario o equipo a diario mediante programación, proporcione un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="e3ee0-111">Las API de exportación pueden recuperar todos los mensajes creados o actualizados durante el intervalo de fechas determinado.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="e3ee0-112">¿Qué es compatible con las Teams Exportar API?</span><span class="sxs-lookup"><span data-stu-id="e3ee0-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="e3ee0-113">Exportación en masa de un mensaje **de Teams:** las API de exportación de Teams admiten hasta 200 RPS por aplicación por inquilino y 600 RPS para una aplicación, con estos límites, debería poder exportar en masa Teams mensajes.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="e3ee0-114">**Contexto de la** aplicación: para llamar a Microsoft Graph, la aplicación debe adquirir un token de acceso desde el Plataforma de identidad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="e3ee0-115">El token de acceso contiene información sobre la aplicación y los permisos que tiene para los recursos y API disponibles a través de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="e3ee0-116">Para obtener un token de acceso, la aplicación debe estar registrada con el Plataforma de identidad de Microsoft y ser autorizada por un usuario o un administrador para obtener acceso a los recursos Graph Microsoft que necesita.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="e3ee0-117">Si ya está familiarizado con la integración de una aplicación [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) con el Plataforma de identidad de Microsoft para obtener tokens, consulte la sección Pasos siguientes para obtener información y muestras específicas de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="e3ee0-118">**Entorno híbrido:** Las API de exportación admiten los mensajes enviados por los usuarios que se aprovisionan en entorno híbrido (Exchange local y Teams).</span><span class="sxs-lookup"><span data-stu-id="e3ee0-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="e3ee0-119">Los mensajes que envíen los usuarios que estén configurados para entorno híbrido serán accesibles con Las API de exportación.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="e3ee0-120">**Mensajes eliminados por el usuario:** Se puede acceder a los mensajes eliminados por los usuarios del cliente Teams mediante API de exportación hasta 21 días desde el momento de la eliminación.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-120">**User Deleted Messages:** Messages that are deleted by users from the Teams client can be accessed using export APIs up to 21 days from the time of deletion.</span></span>
- <span data-ttu-id="e3ee0-121">**Datos adjuntos de mensajes:** Las API de exportación incluyen los vínculos a los datos adjuntos que se envían como parte de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="e3ee0-122">Con Exportar API puede recuperar los archivos adjuntos en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="e3ee0-123">**Propiedades del mensaje de chat:** Consulte la lista completa de propiedades que Teams la compatibilidad de las API de exportación [aquí.](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)</span><span class="sxs-lookup"><span data-stu-id="e3ee0-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="e3ee0-124">Cómo obtener acceso a Teams Exportar API</span><span class="sxs-lookup"><span data-stu-id="e3ee0-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="e3ee0-125">**Ejemplo 1** es una consulta sencilla para recuperar todos los mensajes de un usuario o equipo sin filtros:</span><span class="sxs-lookup"><span data-stu-id="e3ee0-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- <span data-ttu-id="e3ee0-126">**Ejemplo 2** es una consulta de ejemplo para recuperar todos los mensajes de un usuario o equipo especificando filtros de fecha y 50 mensajes principales:</span><span class="sxs-lookup"><span data-stu-id="e3ee0-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
><span data-ttu-id="e3ee0-127">La API devuelve respuesta con el vínculo de página siguiente en caso de varios resultados.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="e3ee0-128">Para obtener el siguiente conjunto de resultados, simplemente llame a OBTENER en la dirección URL desde @odata.nextlink.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="e3ee0-129">Si @odata.nextlink no está presente o es nulo, se recuperarán todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="e3ee0-130">Requisitos previos para obtener Teams exportar API</span><span class="sxs-lookup"><span data-stu-id="e3ee0-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="e3ee0-131">Teams Las API de exportación están actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="e3ee0-132">Solo estará disponible para usuarios e inquilinos que tengan las [licencias necesarias](/graph/teams-licenses) para las API.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-132">It will only be available to users and tenants that have the [required licenses](/graph/teams-licenses) for APIs.</span></span> <span data-ttu-id="e3ee0-133">En el futuro, Microsoft puede requerir que usted o sus clientes paguen tarifas adicionales en función de la cantidad de datos a los que se accede a través de la API.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="e3ee0-134">Microsoft Teams Las API de Microsoft Graph acceso a datos confidenciales se consideran API protegidas.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="e3ee0-135">Las API de exportación requieren que tenga una validación adicional, más allá de los permisos y el consentimiento, antes de poder usarlas.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="e3ee0-136">Para solicitar acceso a estas API protegidas, complete el [formulario de solicitud.](https://aka.ms/teamsgraph/requestaccess)</span><span class="sxs-lookup"><span data-stu-id="e3ee0-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="e3ee0-137">Las aplicaciones que se ejecutan sin un usuario que ha iniciado sesión usan los permisos de aplicación; los permisos de la aplicación solo pueden ser consentidos por un administrador.</span><span class="sxs-lookup"><span data-stu-id="e3ee0-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="e3ee0-138">Se necesitan los siguientes permisos:</span><span class="sxs-lookup"><span data-stu-id="e3ee0-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="e3ee0-139">*Chat.Read.All:* permite el acceso a todos los mensajes de chat de reunión, chat de grupo y 1:1</span><span class="sxs-lookup"><span data-stu-id="e3ee0-139">*Chat.Read.All*: enables access to all 1:1, Group chat, and meeting chat messages</span></span> 
    - <span data-ttu-id="e3ee0-140">*ChannelMessage.Read.All:* permite el acceso a todos los mensajes del canal</span><span class="sxs-lookup"><span data-stu-id="e3ee0-140">*ChannelMessage.Read.All*: enables access to all channel messages</span></span>  
    - <span data-ttu-id="e3ee0-141">*User.Read.All:* permite el acceso a la lista de usuarios de un espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="e3ee0-141">*User.Read.All*: enables access to the list of users for a tenant</span></span>

## <a name="json-representation"></a><span data-ttu-id="e3ee0-142">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="e3ee0-142">JSON representation</span></span>

<span data-ttu-id="e3ee0-143">El ejemplo siguiente es una representación JSON del recurso:</span><span class="sxs-lookup"><span data-stu-id="e3ee0-143">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="e3ee0-144">Espacio de nombres: microsoft.graph</span><span class="sxs-lookup"><span data-stu-id="e3ee0-144">Namespace: microsoft.graph</span></span>

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

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
><span data-ttu-id="e3ee0-145">Para obtener más información sobre el recurso chatMessage, vea el artículo tipo [de recurso chatMessage.](/graph/api/resources/chatmessage)</span><span class="sxs-lookup"><span data-stu-id="e3ee0-145">For more details on chatMessage resource, see the [chatMessage resource type](/graph/api/resources/chatmessage) article.</span></span>