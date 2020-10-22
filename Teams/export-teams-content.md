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
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar contenido con las API de exportación de Microsoft Teams

Las API de exportación de equipos le permiten exportar 1:1 y mensajes de chat grupal de Microsoft Teams. Si su organización necesita exportar mensajes de Microsoft Teams, puede extraerlos con las API de exportación de Teams. El *mensaje de chat* representa un mensaje de chat individual dentro de un [canal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) o un [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta). El mensaje de chat puede ser un mensaje de chat raíz o parte de un subproceso de respuesta definido por la propiedad **replyToId** en el mensaje de la conversación.

A continuación se muestran algunos ejemplos de uso de estas API de exportación:

- **Ejemplo 1**: Si ha habilitado Microsoft Teams en su organización y desea exportar todos los mensajes de Microsoft Teams a Date mediante programación, pase el intervalo de fechas para un usuario dado.
- **Ejemplo 2**: Si desea exportar mediante programación todos los mensajes de usuario a diario proporcionando un intervalo de fechas. Las API de exportación pueden recuperar todos los mensajes creados o actualizados durante el intervalo de fechas dado.

## <a name="what-is-supported-by-the-teams-export-apis"></a>¿Qué es compatible con las API de exportación de Teams?

- **Exportación en masa del mensaje de Teams:** Las API de exportación de equipos admiten hasta 200 RPS por aplicación por espacio empresarial y 600 RPS para una aplicación, con estos límites debe poder exportar en bloque los mensajes de Teams.
- **Contexto**de la aplicación: para llamar a Microsoft Graph, la aplicación debe adquirir un token de acceso de la plataforma de identidades de Microsoft. El token de acceso contiene información sobre la aplicación y los permisos que tiene para los recursos y las API disponibles a través de Microsoft Graph. Para obtener un token de acceso, la aplicación debe registrarse en la plataforma de identidad de Microsoft y su autorización es autorizada por un usuario o un administrador para acceder a los recursos de Microsoft Graph que necesita.

    Si ya está familiarizado con la integración de una aplicación con la plataforma de identidades de Microsoft para obtener tokens, consulte la sección [pasos siguientes](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) para obtener información y ejemplos específicos de Microsoft Graph.
- **Entorno híbrido:** Las API de exportación son compatibles con los usuarios que se aprovisionan en un entorno híbrido (Exchange local y Teams). Los mensajes que envíen los usuarios que estén configurados para un entorno híbrido serán accesibles con las API de exportación.
- **Mensajes eliminados por el usuario:** Se puede acceder a los mensajes eliminados por el usuario del cliente de Teams mediante el uso de API de exportación hasta 30 días desde el momento de la eliminación.
- **Datos adjuntos de mensaje:** Las API de exportación incluyen los vínculos a los datos adjuntos que se envían como parte de los mensajes. Con las API de exportación, puedes recuperar los archivos adjuntos en los mensajes.
- **Propiedades del mensaje de la conversación:** Consulte la lista completa de propiedades que los equipos de exportación de API admiten [aquí](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).

## <a name="how-to-access-teams-export-apis"></a>Cómo obtener acceso a las API de exportación de Teams

- El **ejemplo 1** es una consulta sencilla para recuperar todos los mensajes de un usuario sin ningún filtro:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- El **ejemplo 2** es una consulta de ejemplo para recuperar todos los mensajes de un usuario mediante la especificación de filtros de fecha y hora y los mensajes más importantes de 50:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
>La API devuelve la respuesta con el vínculo de página siguiente en caso de varios resultados. Para obtener el siguiente conjunto de resultados, simplemente llama a GET en la dirección URL desde @odata. NEXTLINK. Si @odata. NEXTLINK no está presente o null, se recuperarán todos los mensajes.

## <a name="prerequisites-to-access-teams-export-apis"></a>Requisitos previos para acceder a las API de exportación de Teams 

- Las API de exportación de Teams se encuentran en versión preliminar. Solo estará disponible para los usuarios y los inquilinos que tengan las [licencias necesarias](https://aka.ms/teams-changenotification-licenses) para las API. En el futuro, Microsoft puede requerir que usted o sus clientes paguen cargos adicionales en función de la cantidad de datos a los que se obtiene acceso a través de la API.
- Las API de Microsoft Teams de Microsoft Graph que tienen acceso a datos confidenciales se consideran API protegidas. Las API de exportación requieren una validación adicional, además de los permisos y el consentimiento, antes de que puedas usarlas. Para solicitar acceso a estas API protegidas, completa el [formulario de solicitud](https://aka.ms/teamsgraph/requestaccess).
- Los permisos de aplicación se usan en las aplicaciones que se ejecutan sin un usuario que ha iniciado sesión; los permisos de la aplicación solo los puede enviar un administrador. Se necesitan los siguientes permisos:

    - *Chat. Read. All*: permite el acceso a todos los mensajes de 1:1 y chat grupal 
    - *User. Read. All*: permite el acceso a la lista de usuarios de un inquilino. 

## <a name="json-representation"></a>Representación JSON

El ejemplo siguiente es una representación JSON del recurso:

Espacio de nombres: Microsoft. Graph

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
>Para obtener más información sobre el recurso chatMessage, vea el artículo sobre el [tipo de recurso chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .
