---
title: Cumplimiento de comunicaciones con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Información sobre el cumplimiento de las comunicaciones, parte del conjunto de soluciones de riesgo de Insider, desde la perspectiva de Microsoft Teams (esto forma parte de la funcionalidad de cumplimiento de comunicaciones M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf032669edc7255571e2501774ac0d0ee0df47d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121538"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Cumplimiento de comunicaciones con Microsoft Teams

El cumplimiento de las comunicaciones es una solución de riesgo de Insider en Microsoft 365 que ayuda a minimizar los riesgos de comunicación al ayudarle a detectar, capturar y actuar en mensajes inadecuados en su organización.

Para Microsoft Teams, el [](/microsoft-365/compliance/communication-compliance-feature-reference) cumplimiento de las comunicaciones ayuda a identificar los siguientes tipos de contenido inadecuado en los canales de Teams o en chats grupales y 1:1:

- Lenguaje ofensivo, profano y acosante
- Imágenes de adultos, radas y peludos
- Uso compartido de información confidencial

Para obtener más información sobre el cumplimiento de las comunicaciones y cómo configurar directivas para su organización, vea Cumplimiento de comunicaciones [en Microsoft 365.](/microsoft-365/compliance/communication-compliance)

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Cómo usar el cumplimiento de comunicaciones en Microsoft Teams

El cumplimiento de las comunicaciones y Microsoft Teams están estrechamente integrados y pueden ayudar a minimizar los riesgos de comunicación en su organización. Después de configurar las primeras directivas de cumplimiento de comunicaciones, puede administrar activamente los mensajes y el contenido inadecuados de Microsoft Teams que se marcan automáticamente en las alertas.

### <a name="getting-started"></a>Introducción

Introducción al cumplimiento de comunicaciones [](/microsoft-365/compliance/communication-compliance-plan) en Microsoft Teams comienza con la planificación y creación de directivas predefinidas o personalizadas para identificar actividades de usuario inadecuadas en los canales de Teams o en 1:1 y grupos. Tenga en cuenta que necesitará [](/microsoft-365/compliance/communication-compliance-configure) configurar algunos permisos y requisitos previos básicos como parte del proceso de configuración.

Los administradores de Teams pueden configurar directivas de cumplimiento de comunicaciones en los siguientes niveles:

- **Nivel de usuario:** las directivas de este nivel se aplican a un usuario individual de Teams o se pueden aplicar a todos los usuarios de Teams de su organización. Estas directivas cubren los mensajes que estos usuarios pueden enviar en chats grupales o 1:1. Las comunicaciones de chat para los usuarios se supervisan automáticamente en todos los Microsoft Teams en los que los usuarios son miembros.
- **Nivel de Teams:** las directivas de este nivel se aplican a un canal de Microsoft Team. Estas directivas abarcan solo los mensajes enviados en el canal de Teams.

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Actuar sobre mensajes inadecuados en Microsoft Teams

Después de configurar las directivas y haber recibido alertas de cumplimiento de comunicaciones para los mensajes de Microsoft Teams, es el momento de que los revisores de cumplimiento de su organización tomen medidas en estos mensajes. Los revisores pueden ayudar a proteger su organización revisando las alertas de cumplimiento de comunicaciones y quitando los mensajes marcados de la vista en Microsoft Teams.

![Quitar un mensaje en Teams](./media/communication-compliance-remove-teams-message.png)

Los mensajes y el contenido eliminados se reemplazan por notificaciones para los visores que explican que el mensaje o el contenido se ha quitado y qué directiva se aplica a la eliminación. Al remitente del mensaje o contenido quitado también se le notifica el estado de eliminación y se le proporciona el contenido original del mensaje para el contexto relacionado con su eliminación. El remitente también puede ver la condición de directiva específica que se aplica a la eliminación del mensaje.

Ejemplo de sugerencia de directiva que ve el remitente:

![Sugerencia de directiva para remitente](./media/communication-compliance-warning-1.png)

Ejemplo de notificación de condición de directiva que ha visto el remitente:

![Información de condición de directiva para el remitente](./media/communication-compliance-warning-2.png)

Ejemplo de sugerencia de directiva que ve el destinatario:

![Sugerencia de directiva para el destinatario](./media/communication-compliance-warning-3.png)