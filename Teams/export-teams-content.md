---
title: Exportar contenido con las API de exportación de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: En este artículo, obtendrá información sobre cómo exportar contenido de Teams mediante las API de exportación de Microsoft Teams.
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
ms.openlocfilehash: ffbea482ac15d1362eabc720fe2c05a8b5954954
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562649"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar contenido con las API de exportación de Microsoft Teams

Las API de exportación de Teams le permiten exportar mensajes individuales, chats grupales, chats de reuniones y mensajes de canal de Microsoft Teams. Si su organización necesita exportar mensajes de Microsoft Teams, podrá extraerlos con las API de exportación de Teams. *Mensaje de* chat representa un mensaje de chat individual dentro de un [canal](/graph/api/resources/channel) o [chat](/graph/api/resources/chat). El mensaje de chat puede ser un mensaje de chat raíz o parte de una conversación de respuesta definida por la propiedad **replyToId** del mensaje de chat.

Estos son algunos ejemplos sobre cómo puede usar estas API de exportación:

- **Ejemplo 1**: Si ha habilitado Microsoft Teams en su organización y desea exportar todos los mensajes de Microsoft Teams a la fecha mediante programación pasando el intervalo de fechas para un usuario o equipo determinado.
- **Ejemplo 2**: Si desea exportar todos los mensajes de usuario o equipo a diario mediante programación proporcionando un intervalo de fechas. Las API de exportación pueden recuperar todos los mensajes creados o actualizados durante el intervalo de fechas especificado.

## <a name="what-is-supported-by-the-teams-export-apis"></a>¿Qué es compatible con las API de exportación de Teams?

- **Mensaje de exportación masiva de Teams:** Las API de exportación de Teams admiten hasta 200 RPS por aplicación por inquilino y 600 RPS para una aplicación, con estos límites debería poder exportar en masa mensajes de Teams.
- **Contexto de la aplicación**: para llamar a Microsoft Graph, la aplicación debe adquirir un token de acceso de la Plataforma de identidad de Microsoft. El token de acceso contiene información sobre la aplicación y los permisos que tiene para los recursos y API disponibles a través de Microsoft Graph. Para obtener un token de acceso, la aplicación debe estar registrada con el Plataforma de identidad de Microsoft y estar autorizada por un usuario o un administrador para obtener acceso a los recursos de Microsoft Graph que necesita.

    Si ya está familiarizado con la integración de una aplicación con la Plataforma de identidad de Microsoft para obtener tokens, consulte la sección [Pasos siguientes](/graph/auth/auth-concepts#next-steps) para obtener información y muestras específicas de Microsoft Graph.
- **Entorno híbrido:** Las API de exportación admiten los mensajes enviados por usuarios aprovisionados en un entorno híbrido (exchange local y teams). Los mensajes enviados por los usuarios configurados para un entorno híbrido serán accesibles mediante exportar API.
- **Mensajes eliminados por el usuario:** Se puede acceder a los mensajes eliminados por los usuarios del cliente de Teams mediante las API de exportación hasta 21 días a partir del momento de la eliminación.
- **Datos adjuntos de mensajes:** Las API de exportación incluyen los vínculos a los datos adjuntos que se envían como parte de los mensajes. Con Exportar API puede recuperar los archivos adjuntos en los mensajes.
- **Propiedades del mensaje de chat:** Consulte la lista completa de propiedades que admiten las API de exportación de Teams [aquí](/graph/api/resources/chatmessage#properties).

> [!NOTE]
> Las API de exportación no admiten *reacciones*.

## <a name="how-to-access-teams-export-apis"></a>Cómo acceder a las API de exportación de Teams

- **El ejemplo 1** es una consulta sencilla para recuperar todos los mensajes de un usuario o equipo sin filtros:

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
  ```

- **El ejemplo 2** es una consulta de ejemplo para recuperar todos los mensajes de un usuario o equipo especificando filtros de fecha y hora y los 50 mensajes principales:

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

> [!NOTE]
> La API devuelve la respuesta con el vínculo de página siguiente en caso de varios resultados. Para obtener el siguiente conjunto de resultados, simplemente llame a GET en la dirección URL desde @odata.nextlink. Si @odata.nextlink no está presente o es nulo, se recuperan todos los mensajes.

## <a name="prerequisites-to-access-teams-export-apis"></a>Requisitos previos para acceder a las API de exportación de Teams

- Las API de Microsoft Teams en Microsoft Graph que acceden a datos confidenciales se consideran API protegidas. Para poder usarlas, es necesario disponer de validación adicional, más allá de los permisos y el consentimiento. Para solicitar acceso a estas API protegidas, rellena el [formulario de solicitud](https://aka.ms/teamsgraph/requestaccess).
- Los permisos de aplicación los usan las aplicaciones que se ejecutan sin un usuario con sesión iniciada presente; permisos de aplicación solo puede ser consentido por un administrador. Son necesarios los siguientes permisos:
  - *Chat.Read.All*: permite el acceso a todos los mensajes de chat individuales, grupales y de reunión
  - *ChannelMessage.Read.All*: permite el acceso a todos los mensajes del canal
  - *User.Read.All*: permite el acceso a la lista de usuarios de un inquilino.

## <a name="license-requirements-for-teams-export-apis"></a>Requisitos de licencia para las API de exportación de Teams

La API de exportación admite seguridad y cumplimiento (S+C) y escenarios de uso general a través de un parámetro de consulta de modelo. Los escenarios de S+C (modelo A) incluyen capacidad de semillas y requieren una suscripción al plan E5 y los escenarios de uso general (modelo B) están disponibles para todas las suscripciones y solo son de consumo. Para obtener más información sobre la capacidad de semillas y las tarifas de consumo, consulte [Requisitos de licencias y pago para las API de Microsoft Graph Teams](/graph/teams-licenses).

### <a name="scmodel-a-scenarios"></a>Escenarios de S+C/Modelo A

Restringido a las aplicaciones que realizan funciones de seguridad o cumplimiento, los usuarios deben tener licencias E5 específicas para usar esta funcionalidad y recibir capacidad de semillas. La capacidad de semillas es por usuario y se calcula por mes y se agrega en el nivel de inquilino. Para el uso que supere la capacidad de semillas, se factura a los propietarios de aplicaciones el consumo de API. El modelo A solo puede tener acceso a los mensajes de los usuarios con una licencia E5 asignada.

### <a name="general-usagemodel-b-scenarios"></a>Escenarios generales de uso/modelo B

Disponible para todos los escenarios relacionados que no sean S+C, no hay requisitos de licencia ni capacidad de semillas. Cuando los contadores de consumo estén disponibles, se cobrará a los propietarios de las aplicaciones todas las llamadas mensuales a la API.

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

> [!NOTE]
> Para obtener más información sobre el recurso chatMessage, vea el artículo [tipo de recurso chatMessage](/graph/api/resources/chatmessage) .
