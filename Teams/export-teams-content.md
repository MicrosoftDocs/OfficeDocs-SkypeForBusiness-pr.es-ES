---
title: Exportar contenido con las API de exportación de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: En este artículo, obtendrá información sobre cómo exportar contenido de Teams mediante las API de exportación de Microsoft Teams.
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
ms.openlocfilehash: 026b7f238b059b4e310fa2216b482c68f2528780
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650983"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="c41ed-103">Exportar contenido con las API de exportación de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c41ed-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="c41ed-104">Las API de exportación de equipos le permiten exportar 1:1 y mensajes de chat grupal de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c41ed-104">Teams Export APIs allow you to export 1:1 and group chat messages from Microsoft Teams.</span></span> <span data-ttu-id="c41ed-105">Si su organización necesita exportar mensajes de Microsoft Teams, puede extraerlos con las API de exportación de Teams.</span><span class="sxs-lookup"><span data-stu-id="c41ed-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="c41ed-106">El *mensaje de chat* representa un mensaje de chat individual dentro de un [canal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) o un [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="c41ed-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="c41ed-107">El mensaje de chat puede ser un mensaje de chat raíz o parte de un subproceso de respuesta definido por la propiedad **replyToId** en el mensaje de la conversación.</span><span class="sxs-lookup"><span data-stu-id="c41ed-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="c41ed-108">A continuación se muestran algunos ejemplos de uso de estas API de exportación:</span><span class="sxs-lookup"><span data-stu-id="c41ed-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="c41ed-109">**Ejemplo 1**: Si ha habilitado Microsoft Teams en su organización y desea exportar todos los mensajes de Microsoft Teams a Date mediante programación, pase el intervalo de fechas para un usuario dado.</span><span class="sxs-lookup"><span data-stu-id="c41ed-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user.</span></span>
- <span data-ttu-id="c41ed-110">**Ejemplo 2**: Si desea exportar mediante programación todos los mensajes de usuario a diario proporcionando un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="c41ed-110">**Example 2**: If you want to programmatically export all user messages daily by providing a date range.</span></span> <span data-ttu-id="c41ed-111">Las API de exportación pueden recuperar todos los mensajes creados o actualizados durante el intervalo de fechas dado.</span><span class="sxs-lookup"><span data-stu-id="c41ed-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="c41ed-112">¿Qué es compatible con las API de exportación de Teams?</span><span class="sxs-lookup"><span data-stu-id="c41ed-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="c41ed-113">**Exportación en masa del mensaje de Teams:** Las API de exportación de equipos admiten hasta 200 RPS por aplicación por espacio empresarial y 600 RPS para una aplicación, con estos límites debe poder exportar en bloque los mensajes de Teams.</span><span class="sxs-lookup"><span data-stu-id="c41ed-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="c41ed-114">**Contexto**de la aplicación: para llamar a Microsoft Graph, la aplicación debe adquirir un token de acceso de la plataforma de identidades de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c41ed-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="c41ed-115">El token de acceso contiene información sobre la aplicación y los permisos que tiene para los recursos y las API disponibles a través de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="c41ed-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="c41ed-116">Para obtener un token de acceso, la aplicación debe registrarse en la plataforma de identidad de Microsoft y su autorización es autorizada por un usuario o un administrador para acceder a los recursos de Microsoft Graph que necesita.</span><span class="sxs-lookup"><span data-stu-id="c41ed-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="c41ed-117">Si ya está familiarizado con la integración de una aplicación con la plataforma de identidades de Microsoft para obtener tokens, consulte la sección [pasos siguientes](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) para obtener información y ejemplos específicos de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="c41ed-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="c41ed-118">**Entorno híbrido:** Las API de exportación son compatibles con los usuarios que se aprovisionan en un entorno híbrido (Exchange local y Teams).</span><span class="sxs-lookup"><span data-stu-id="c41ed-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="c41ed-119">Los mensajes que envíen los usuarios que estén configurados para un entorno híbrido serán accesibles con las API de exportación.</span><span class="sxs-lookup"><span data-stu-id="c41ed-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="c41ed-120">**Mensajes eliminados por el usuario:** Se puede acceder a los mensajes eliminados por el usuario del cliente de Teams mediante el uso de API de exportación hasta 30 días desde el momento de la eliminación.</span><span class="sxs-lookup"><span data-stu-id="c41ed-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="c41ed-121">**Datos adjuntos de mensaje:** Las API de exportación incluyen los vínculos a los datos adjuntos que se envían como parte de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c41ed-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="c41ed-122">Con las API de exportación, puedes recuperar los archivos adjuntos en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c41ed-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="c41ed-123">**Propiedades del mensaje de la conversación:** Consulte la lista completa de propiedades que los equipos de exportación de API admiten [aquí](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span><span class="sxs-lookup"><span data-stu-id="c41ed-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="c41ed-124">Cómo obtener acceso a las API de exportación de Teams</span><span class="sxs-lookup"><span data-stu-id="c41ed-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="c41ed-125">El **ejemplo 1** es una consulta sencilla para recuperar todos los mensajes de un usuario sin ningún filtro:</span><span class="sxs-lookup"><span data-stu-id="c41ed-125">**Example 1** is a simple query to retrieve all the messages of a user without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- <span data-ttu-id="c41ed-126">El **ejemplo 2** es una consulta de ejemplo para recuperar todos los mensajes de un usuario mediante la especificación de filtros de fecha y hora y los mensajes más importantes de 50:</span><span class="sxs-lookup"><span data-stu-id="c41ed-126">**Example 2** is a sample query to retrieve all the messages of a user by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
><span data-ttu-id="c41ed-127">La API devuelve la respuesta con el vínculo de página siguiente en caso de varios resultados.</span><span class="sxs-lookup"><span data-stu-id="c41ed-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="c41ed-128">Para obtener el siguiente conjunto de resultados, simplemente llama a GET en la dirección URL desde @odata. NEXTLINK.</span><span class="sxs-lookup"><span data-stu-id="c41ed-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="c41ed-129">Si @odata. NEXTLINK no está presente o null, se recuperarán todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c41ed-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="c41ed-130">Requisitos previos para acceder a las API de exportación de Teams</span><span class="sxs-lookup"><span data-stu-id="c41ed-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="c41ed-131">Las API de exportación de Teams se encuentran en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="c41ed-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="c41ed-132">Solo estará disponible para los usuarios y los inquilinos que tengan las [licencias necesarias](https://aka.ms/teams-changenotification-licenses) para las API.</span><span class="sxs-lookup"><span data-stu-id="c41ed-132">It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs.</span></span> <span data-ttu-id="c41ed-133">En el futuro, Microsoft puede requerir que usted o sus clientes paguen cargos adicionales en función de la cantidad de datos a los que se obtiene acceso a través de la API.</span><span class="sxs-lookup"><span data-stu-id="c41ed-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="c41ed-134">Las API de Microsoft Teams de Microsoft Graph que tienen acceso a datos confidenciales se consideran API protegidas.</span><span class="sxs-lookup"><span data-stu-id="c41ed-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="c41ed-135">Las API de exportación requieren una validación adicional, además de los permisos y el consentimiento, antes de que puedas usarlas.</span><span class="sxs-lookup"><span data-stu-id="c41ed-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="c41ed-136">Para solicitar acceso a estas API protegidas, completa el [formulario de solicitud](https://aka.ms/teamsgraph/requestaccess).</span><span class="sxs-lookup"><span data-stu-id="c41ed-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="c41ed-137">Los permisos de aplicación se usan en las aplicaciones que se ejecutan sin un usuario que ha iniciado sesión; los permisos de la aplicación solo los puede enviar un administrador.</span><span class="sxs-lookup"><span data-stu-id="c41ed-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="c41ed-138">Se necesitan los siguientes permisos:</span><span class="sxs-lookup"><span data-stu-id="c41ed-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="c41ed-139">*Chat. Read. All*: permite el acceso a todos los mensajes de 1:1 y chat grupal</span><span class="sxs-lookup"><span data-stu-id="c41ed-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="c41ed-140">*User. Read. All*: permite el acceso a la lista de usuarios de un inquilino.</span><span class="sxs-lookup"><span data-stu-id="c41ed-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="c41ed-141">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="c41ed-141">JSON representation</span></span>

<span data-ttu-id="c41ed-142">El ejemplo siguiente es una representación JSON del recurso:</span><span class="sxs-lookup"><span data-stu-id="c41ed-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="c41ed-143">Espacio de nombres: Microsoft. Graph</span><span class="sxs-lookup"><span data-stu-id="c41ed-143">Namespace: microsoft.graph</span></span>

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
                    "id": "0de69e5e-2da8-4cf2-821f-5e6585b2c65b",
                    "displayName": "User Name",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "19:0de69e5e-2da8-4cf2-821f-5e6585b2c65b_5c64e248-3269-4268-a36e-0f80314e9c39@unq.gbl.spaces"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
><span data-ttu-id="c41ed-144">Para obtener más información sobre el recurso chatMessage, vea el artículo sobre el [tipo de recurso chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .</span><span class="sxs-lookup"><span data-stu-id="c41ed-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
