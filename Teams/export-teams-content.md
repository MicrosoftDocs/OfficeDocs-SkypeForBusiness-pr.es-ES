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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84f53b5c75c9e99e3a3bfc2877c096b32fe3b9c0
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082870"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar contenido con las Microsoft Teams Exportar API

Teams Las API de exportación le permiten exportar 1:1, chat grupal, chats de reunión y canales de mensajes desde Microsoft Teams. Si su organización necesita exportar Microsoft Teams mensajes, puede extraerlos con Teams Exportar API. *Mensaje de chat* representa un mensaje de chat individual dentro de [un canal](/graph/api/resources/channel?view=graph-rest-beta) o [chat.](/graph/api/resources/chat?view=graph-rest-beta) El mensaje de chat puede ser un mensaje de chat raíz o parte de un hilo de respuesta definido por la **propiedad replyToId** del mensaje de chat.

A continuación se muestran algunos ejemplos sobre cómo puede usar estas API de exportación:

- **Ejemplo 1:** Si ha habilitado Microsoft Teams en su organización y desea exportar todos los mensajes de Microsoft Teams a la fecha mediante programación pasando el intervalo de fechas para un usuario o equipo determinado.
- **Ejemplo 2:** Si desea exportar todos los mensajes de usuario o equipo a diario mediante programación, proporcione un intervalo de fechas. Las API de exportación pueden recuperar todos los mensajes creados o actualizados durante el intervalo de fechas determinado.

## <a name="what-is-supported-by-the-teams-export-apis"></a>¿Qué es compatible con las Teams Exportar API?

- Exportación en masa de un mensaje **de Teams:** las API de exportación de Teams admiten hasta 200 RPS por aplicación por inquilino y 600 RPS para una aplicación, con estos límites, debería poder exportar en masa Teams mensajes.
- **Contexto de la** aplicación: para llamar a Microsoft Graph, la aplicación debe adquirir un token de acceso desde el Plataforma de identidad de Microsoft. El token de acceso contiene información sobre la aplicación y los permisos que tiene para los recursos y API disponibles a través de Microsoft Graph. Para obtener un token de acceso, la aplicación debe estar registrada con el Plataforma de identidad de Microsoft y ser autorizada por un usuario o un administrador para obtener acceso a los recursos Graph Microsoft que necesita.

    Si ya está familiarizado con la integración de una aplicación [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) con el Plataforma de identidad de Microsoft para obtener tokens, consulte la sección Pasos siguientes para obtener información y muestras específicas de Microsoft Graph.
- **Entorno híbrido:** Las API de exportación admiten los mensajes enviados por los usuarios que se aprovisionan en entorno híbrido (Exchange local y Teams). Los mensajes que envíen los usuarios que estén configurados para entorno híbrido serán accesibles con Las API de exportación.
- **Mensajes eliminados por el usuario:** Se puede acceder a los mensajes eliminados por los usuarios del cliente Teams mediante API de exportación hasta 21 días desde el momento de la eliminación.
- **Datos adjuntos de mensajes:** Las API de exportación incluyen los vínculos a los datos adjuntos que se envían como parte de los mensajes. Con Exportar API puede recuperar los archivos adjuntos en los mensajes.
- **Propiedades del mensaje de chat:** Consulte la lista completa de propiedades que Teams la compatibilidad de las API de exportación [aquí.](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

>[!NOTE]
>Las API de exportación no *admiten reacciones.*

## <a name="how-to-access-teams-export-apis"></a>Cómo obtener acceso a Teams Exportar API

- **Ejemplo 1** es una consulta sencilla para recuperar todos los mensajes de un usuario o equipo sin filtros:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
    ```

- **Ejemplo 2** es una consulta de ejemplo para recuperar todos los mensajes de un usuario o equipo especificando filtros de fecha y 50 mensajes principales:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>La API devuelve respuesta con el vínculo de página siguiente en caso de varios resultados. Para obtener el siguiente conjunto de resultados, simplemente llame a OBTENER en la dirección URL desde @odata.nextlink. Si @odata.nextlink no está presente o es nulo, se recuperarán todos los mensajes.

## <a name="prerequisites-to-access-teams-export-apis"></a>Requisitos previos para obtener Teams exportar API 

- Microsoft Teams Las API de Microsoft Graph acceso a datos confidenciales se consideran API protegidas. Las API de exportación requieren que tenga una validación adicional, más allá de los permisos y el consentimiento, antes de poder usarlas. Para solicitar acceso a estas API protegidas, complete el [formulario de solicitud.](https://aka.ms/teamsgraph/requestaccess)
- Las aplicaciones que se ejecutan sin un usuario que ha iniciado sesión usan los permisos de aplicación; los permisos de la aplicación solo pueden ser consentidos por un administrador. Se necesitan los siguientes permisos:

    - *Chat.Read.All:* permite el acceso a todos los mensajes de chat de reunión, chat de grupo y 1:1 
    - *ChannelMessage.Read.All:* permite el acceso a todos los mensajes del canal  
    - *User.Read.All:* permite el acceso a la lista de usuarios de un espacio empresarial

## <a name="license-requirements-for-teams-export-apis"></a>Requisitos de licencia Teams Exportar API

La API de exportación admite escenarios de seguridad y cumplimiento (S+C) y de uso general a través de un parámetro de consulta de modelo. Los escenarios de S+C (modelo A) incluyen capacidad de seed y requieren una suscripción E5 y los escenarios de uso general (modelo B) están disponibles para todas las suscripciones y solo son de consumo. Para obtener más información sobre las tarifas de consumo y capacidad de seeded, vea Requisitos de licencia y pago para [Microsoft Graph Teams API.](/graph/teams-licenses)

### <a name="scmodel-a-scenarios"></a>Escenarios de S+C/Model A

Restringido a las aplicaciones que realizan funciones de seguridad y/o cumplimiento, los usuarios deben tener licencias E5 específicas para usar esta funcionalidad y recibir capacidad de semilla. La capacidad seeded es por usuario y se calcula por mes y se agrega en el nivel de inquilino. Para el uso más allá de la capacidad de la semilla, los propietarios de aplicaciones se facturan por consumo de API. El modelo A solo puede obtener acceso a los mensajes de los usuarios con una licencia E5 asignada.

### <a name="general-usagemodel-b-scenarios"></a>Uso general/Escenarios del modelo B

Disponible para todos los escenarios relacionados que no sean de S+C, no hay requisitos de licencia ni capacidad de semilla. Cuando los contadores de consumo estén disponibles, los propietarios de las aplicaciones se cobrarán por todas las llamadas mensuales de la API. 

### <a name="evaluation-mode-default"></a>Modo de evaluación (predeterminado)

Ninguna declaración de modelo permite el acceso a las API con uso limitado por cada aplicación solicitante con fines de evaluación. 

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