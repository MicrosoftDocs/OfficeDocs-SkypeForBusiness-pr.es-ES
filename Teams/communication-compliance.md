---
title: Cumplimiento de la comunicación con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Aprender sobre el cumplimiento de las comunicaciones, parte de la solución de riesgos de Insider, desde la perspectiva de Microsoft Teams (esta es parte de la funcionalidad de cumplimiento de comunicaciones de M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328259"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Cumplimiento de la comunicación con Microsoft Teams

El cumplimiento de la comunicación es una solución de riesgo de Insider en Microsoft 365 que ayuda a minimizar los riesgos de comunicación ayudándole a detectar, capturar y actuar en los mensajes inapropiados de su organización.

Para Microsoft Teams, el cumplimiento de la comunicación ayuda a identificar los [siguientes tipos](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) de contenido inadecuado en canales de equipos o en 1:1 y chats grupales:

- Lenguaje ofensivo, irreverente y de acoso
- Imágenes de adultos, racy y Gory
- Uso compartido de información confidencial

Para obtener más información sobre el cumplimiento de las comunicaciones y sobre cómo configurar directivas para su organización, consulte [cumplimiento de la comunicación en Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Cómo usar el cumplimiento de la comunicación en Microsoft Teams

El cumplimiento de las comunicaciones y Microsoft Teams están estrechamente integrados y pueden ayudar a minimizar los riesgos de comunicación de su organización. Una vez que haya configurado las primeras directivas de cumplimiento de comunicaciones, puede administrar activamente los mensajes y el contenido inapropiados de Microsoft teams que se marcan automáticamente en las alertas.

### <a name="getting-started"></a>Introducción

Introducción a la comunicación el cumplimiento en Microsoft Teams comienza a [planear](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) y crear directivas predefinidas o personalizadas para identificar actividades de usuario inadecuadas en los canales de Teams o en 1:1 y grupos. Tenga en cuenta que tendrá que [configurar](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) algunos permisos y los requisitos previos básicos como parte del proceso de configuración.

Los administradores de equipos pueden configurar directivas de cumplimiento de comunicaciones en los siguientes niveles:

- **Nivel de usuario**: las directivas de este nivel se aplican a un usuario individual de Teams o se pueden aplicar a todos los usuarios de su organización. Estas directivas cubren los mensajes que estos usuarios pueden enviar en 1:1 o chats grupales. Las comunicaciones por chat de los usuarios se supervisan automáticamente en todos los equipos de Microsoft en los que los usuarios son miembros.
- **Nivel de Teams**: las directivas de este nivel se aplican a un canal de equipo de Microsoft. Estas directivas cubren los mensajes enviados solo en el canal de Teams.

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Actuar sobre mensajes inapropiados en Microsoft Teams

Una vez que haya configurado las directivas y haya recibido alertas de cumplimiento para las comunicaciones de los mensajes de Microsoft Teams, es el momento de que los revisores de cumplimiento de normas de su organización tomen medidas en estos mensajes. Los revisores pueden ayudar a proteger su organización revisando las alertas de cumplimiento de comunicaciones y eliminando los mensajes marcados de la vista en Microsoft Teams.

![Quitar un mensaje de Teams](./media/communication-compliance-remove-teams-message.png)

Los mensajes y el contenido quitados se reemplazan por notificaciones para visores que explican que el mensaje o contenido se ha quitado y qué directiva es aplicable a la eliminación. El remitente del mensaje o contenido eliminado también recibe la notificación del estado de eliminación y se proporciona con el contenido del mensaje original para el contexto relacionado con su eliminación. El remitente también puede ver la condición de la Directiva específica que se aplica a la eliminación del mensaje.

Ejemplo de sugerencia de directiva visto por el remitente:

![Sugerencia de directiva para el remitente](./media/communication-compliance-warning-1.png)

Ejemplo de notificación de condición de la Directiva visto por el remitente:

![Información de condición de la Directiva para el remitente](./media/communication-compliance-warning-2.png)

Ejemplo de sugerencia de directiva visto por el destinatario:

![Sugerencia de directiva para el destinatario](./media/communication-compliance-warning-3.png)
