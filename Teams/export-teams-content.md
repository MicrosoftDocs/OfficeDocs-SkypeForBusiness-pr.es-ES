---
title: Exportar contenido con las API de exportación de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: En este artículo, aprenderá a exportar contenido de Teams con las API de exportación de Microsoft Teams.
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
ms.openlocfilehash: 013cd992619264f875841b1b6bb13aca3943d14e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092464"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar contenido con las API de exportación de Microsoft Teams

Las API de exportación de Teams le permiten exportar 1:1, chat grupal, chats de reunión y canales de mensajes de Microsoft Teams. Si su organización necesita exportar mensajes de Microsoft Teams, puede extraerlos con las API de exportación de Teams. *Mensaje de chat* representa un mensaje de chat individual dentro de [un canal](/graph/api/resources/channel?view=graph-rest-beta) o [chat.](/graph/api/resources/chat?view=graph-rest-beta) El mensaje de chat puede ser un mensaje de chat raíz o parte de un hilo de respuesta definido por la **propiedad replyToId** del mensaje de chat.

A continuación se muestran algunos ejemplos sobre cómo puede usar estas API de exportación:

- **Ejemplo 1:** Si ha habilitado Microsoft Teams en su organización y desea exportar todos los mensajes de Microsoft Teams a la fecha mediante programación pasando el intervalo de fechas para un usuario o equipo determinado.
- **Ejemplo 2:** Si desea exportar todos los mensajes de usuario o equipo a diario mediante programación, proporcione un intervalo de fechas. Las API de exportación pueden recuperar todos los mensajes creados o actualizados durante el intervalo de fechas determinado.

## <a name="what-is-supported-by-the-teams-export-apis"></a>¿Qué es compatible con las API de exportación de Teams?

- **Mensaje Exportar en masa de Teams:** Las API de exportación de Teams admiten hasta 200 RPS por aplicación por inquilino y 600 RPS para una aplicación, con estos límites debería poder exportar en masa los mensajes de Teams.
- **Contexto de la** aplicación: para llamar a Microsoft Graph, la aplicación debe adquirir un token de acceso desde la plataforma de identidad de Microsoft. El token de acceso contiene información sobre la aplicación y los permisos que tiene para los recursos y API disponibles a través de Microsoft Graph. Para obtener un token de acceso, la aplicación debe estar registrada en la plataforma de identidad de Microsoft y estar autorizada por un usuario o un administrador para obtener acceso a los recursos de Microsoft Graph que necesita.

    Si ya está familiarizado con la integración de una aplicación [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) con la plataforma de identidad de Microsoft para obtener tokens, vea la sección Pasos siguientes para obtener información y muestras específicas de Microsoft Graph.
- **Entorno híbrido:** Las API de exportación admiten los mensajes enviados por usuarios aprovisionados en entorno híbrido (Exchange local y Teams). Los mensajes que envíen los usuarios que estén configurados para entorno híbrido serán accesibles con Las API de exportación.
- **Mensajes eliminados por el usuario:** Se puede acceder a los mensajes eliminados por los usuarios desde el cliente de Teams mediante API de exportación hasta 21 días desde el momento de la eliminación.
- **Datos adjuntos de mensajes:** Las API de exportación incluyen los vínculos a los datos adjuntos que se envían como parte de los mensajes. Con Exportar API puede recuperar los archivos adjuntos en los mensajes.
- **Propiedades del mensaje de chat:** Consulte la lista completa de propiedades que admiten las API de exportación de Teams [aquí.](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Cómo obtener acceso a las API de exportación de Teams

- **Ejemplo 1** es una consulta sencilla para recuperar todos los mensajes de un usuario o equipo sin filtros:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- **Ejemplo 2** es una consulta de ejemplo para recuperar todos los mensajes de un usuario o equipo especificando filtros de fecha y 50 mensajes principales:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>La API devuelve respuesta con el vínculo de página siguiente en caso de varios resultados. Para obtener el siguiente conjunto de resultados, simplemente llame a OBTENER en la dirección URL desde @odata.nextlink. Si @odata.nextlink no está presente o es nulo, se recuperarán todos los mensajes.

## <a name="prerequisites-to-access-teams-export-apis"></a>Requisitos previos para obtener acceso a las API de exportación de Teams 

- Las API de exportación de Teams están actualmente en versión preliminar. Solo estará disponible para usuarios e inquilinos que tengan las [licencias necesarias](/graph/teams-licenses) para las API. En el futuro, Microsoft puede requerir que usted o sus clientes paguen tarifas adicionales en función de la cantidad de datos a los que se accede a través de la API.
- Las API de Microsoft Teams en Microsoft Graph que tienen acceso a datos confidenciales se consideran API protegidas. Las API de exportación requieren que tenga una validación adicional, más allá de los permisos y el consentimiento, antes de poder usarlas. Para solicitar acceso a estas API protegidas, complete el [formulario de solicitud.](https://aka.ms/teamsgraph/requestaccess)
- Las aplicaciones que se ejecutan sin un usuario que ha iniciado sesión usan los permisos de aplicación; los permisos de la aplicación solo pueden ser consentidos por un administrador. Se necesitan los siguientes permisos:

    - *Chat.Read.All:* permite el acceso a todos los mensajes de chat de grupo y 1:1 
    - *User.Read.All:* permite el acceso a la lista de usuarios de un espacio empresarial 

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
>Para obtener más información sobre el recurso chatMessage, vea el artículo tipo [de recurso chatMessage.](/graph/api/resources/chatmessage)