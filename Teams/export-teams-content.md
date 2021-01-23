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
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar contenido con las API de exportación de Microsoft Teams

Las API de exportación de Teams le permiten exportar mensajes 1:1, chats grupales y canales desde Microsoft Teams. Si su organización necesita exportar mensajes de Microsoft Teams, puede extraerlos mediante las API de exportación de Teams. *El mensaje de* chat representa un mensaje de chat individual dentro de [un canal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) o [chat.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta) El mensaje de chat puede ser un mensaje de chat raíz o parte de un hilo de respuesta definido por la propiedad **replyToId** en el mensaje de chat.

A continuación se muestran algunos ejemplos sobre cómo puede usar estas API de exportación:

- **Ejemplo 1:** Si ha habilitado Microsoft Teams en su organización y desea exportar todos los mensajes de Microsoft Teams a la fecha mediante programación pasando el intervalo de fechas de un usuario o equipo determinado.
- **Ejemplo 2:** Si desea exportar mediante programación todos los mensajes de usuario o equipo diariamente proporcionando un intervalo de fechas. Las API de exportación pueden recuperar todos los mensajes creados o actualizados durante el intervalo de fechas especificado.

## <a name="what-is-supported-by-the-teams-export-apis"></a>¿Qué se admite en las API de exportación de Teams?

- **Mensaje de exportación en masa de Teams:** Las API de exportación de Teams admiten hasta 200 RPS por aplicación por espacio empresarial y 600 RPS para una aplicación, con estos límites debería poder exportar mensajes de Teams en masa.
- **Contexto de la** aplicación: para llamar a Microsoft Graph, la aplicación debe adquirir un token de acceso de la plataforma de identidad de Microsoft. El token de acceso contiene información sobre la aplicación y los permisos que tiene para los recursos y las API disponibles a través de Microsoft Graph. Para obtener un token de acceso, la aplicación debe estar registrada con la plataforma de identidad de Microsoft y estar autorizada por un usuario o un administrador para obtener acceso a los recursos de Microsoft Graph que necesita.

    Si ya está familiarizado con la integración de una aplicación [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) con la plataforma de identidad de Microsoft para obtener tokens, consulte la sección Pasos siguientes para obtener información y ejemplos específicos de Microsoft Graph.
- **Entorno híbrido:** Export API support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams). Se podrá obtener acceso a todos los mensajes que envíen los usuarios configurados para el entorno híbrido mediante las API de exportación.
- **Mensajes eliminados por el usuario:** Se puede acceder a los mensajes eliminados por el usuario del cliente de Teams mediante las API de exportación hasta 30 días desde el momento de la eliminación.
- **Datos adjuntos de mensajes:** Las API de exportación incluyen los vínculos a los datos adjuntos que se envían como parte de los mensajes. Con exportar API, puede recuperar los archivos adjuntos en los mensajes.
- **Propiedades de los mensajes de chat:** Consulte aquí la lista completa de propiedades que admiten las API de exportación [de](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)Teams.

## <a name="how-to-access-teams-export-apis"></a>Cómo acceder a las API de exportación de Teams

- **El ejemplo 1** es una consulta sencilla para recuperar todos los mensajes de un usuario o equipo sin ningún filtro:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- **El ejemplo 2** es una consulta de ejemplo para recuperar todos los mensajes de un usuario o equipo especificando filtros de fecha y hora y los 50 mensajes superiores:

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
>Para obtener más información sobre el recurso chatMessage, vea el artículo sobre el [tipo de recurso chatMessage.](https://docs.microsoft.com/graph/api/resources/chatmessage)
