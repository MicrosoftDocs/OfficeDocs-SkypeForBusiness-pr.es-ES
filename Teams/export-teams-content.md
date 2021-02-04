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
ms.openlocfilehash: 9c99bed1ef9a1862b469dd5214b8d829bde8479b
ms.sourcegitcommit: 15c45befbee35e69f9ec82493151cb82e61da4fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50096933"
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
- **Entorno híbrido:** Export API support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams). Se podrá obtener acceso a todos los mensajes que envíen los usuarios que estén configurados para el entorno híbrido mediante las API de exportación.
- **Mensajes eliminados por el usuario:** Se puede acceder a los mensajes eliminados por el usuario del cliente de Teams mediante las API de exportación hasta 30 días desde el momento de la eliminación.
- **Datos adjuntos de mensajes:** Las API de exportación incluyen los vínculos a los datos adjuntos que se envían como parte de los mensajes. Con exportar API, puede recuperar los archivos adjuntos en los mensajes.
- **Propiedades de los mensajes de chat:** Consulte aquí la lista completa de propiedades que admiten las API de exportación [de](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)Teams.

## <a name="how-to-access-teams-export-apis"></a>Cómo acceder a las API de exportación de Teams

- **El ejemplo 1** es una consulta sencilla para recuperar todos los mensajes de un usuario o equipo sin ningún filtro:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- **El ejemplo 2** es una consulta de ejemplo para recuperar todos los mensajes de un usuario o equipo especificando filtros de fecha y hora y los 50 mensajes superiores:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>La API devuelve la respuesta con el vínculo de la página siguiente en caso de obtener varios resultados. Para obtener el siguiente conjunto de resultados, simplemente llame a GET en la dirección URL @odata.nextlink. Si @odata.nextlink no está presente o es nulo, se recuperan todos los mensajes.

## <a name="prerequisites-to-access-teams-export-apis"></a>Requisitos previos para acceder a las API de exportación de Teams 

- Las API de exportación de Teams están actualmente en versión preliminar. Solo estará disponible para los usuarios e inquilinos que tengan las licencias [necesarias para](https://aka.ms/teams-changenotification-licenses) las API. En el futuro, Microsoft puede requerir que usted o sus clientes paguen tarifas adicionales en función de la cantidad de datos a los que se accede a través de la API.
- Las API de Microsoft Teams en Microsoft Graph que tienen acceso a datos confidenciales se consideran API protegidas. Las API de exportación requieren que tenga validación adicional, más allá de permisos y consentimiento, para poder usarlas. Para solicitar acceso a estas API protegidas, complete el formulario [de solicitud.](https://aka.ms/teamsgraph/requestaccess)
- Las aplicaciones que no tienen un usuario iniciado usan los permisos de aplicación; los permisos de la aplicación solo pueden ser consientes por un administrador. Son necesarios los siguientes permisos:

    - *Chat.Read.All*: permite el acceso a todos los mensajes de chat grupales y uno a uno 
    - *User.Read.All:* permite el acceso a la lista de usuarios de un inquilino. 

## <a name="json-representation"></a>Representación JSON

El ejemplo siguiente es una representación JSON del recurso:

Espacio de nombres: microsoft.graph

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
