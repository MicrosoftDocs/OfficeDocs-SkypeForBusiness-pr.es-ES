---
title: Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre la experiencia de chat nativa de Teams para usuarios de acceso externo (federados) en Microsoft Teams, donde ambos usuarios están en el modo de actualización de TeamsOnly.
ms.openlocfilehash: a06532ab4cd1d1c5ffe3f30d2a6036b2c34c716f
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030120"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams

Cuando un usuario de Microsoft Teams chatea con un usuario externo (federado), la experiencia de chat se limita al texto. Sin embargo, si tanto el usuario de Teams como la persona de otra organización están en el modo de actualización de TeamsOnly, puede tener una "experiencia de chat nativa de Teams", que incluye formato enriquecido, @mentions y otras características de chat. Los chats de Native Teams con personas de otras organizaciones solo se limitan a chats de 1:1.

La experiencia de chat nativa para personas de otras organizaciones está activada para todos los inquilinos de Teams, pero no todas las personas son aptas. Para ofrecer una experiencia de chat nativa, tanto el remitente como el receptor deben configurarse para el modo de actualización de TeamsOnly. Para obtener más información sobre las directivas de actualización, lea [Establecer la configuración de coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)

Para ver una lista de las capacidades de los usuarios de acceso externo en Teams, vea [Comparar el acceso externo y el de invitado.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>¿Cómo puedo saber si estoy en un chat nativo?

Si solo puede intercambiar texto en el chat con personas de otras organizaciones, está en un chat estándar de acceso externo (federado). Si tiene todas las demás funciones de chat, incluido el formato, @mentions, emojis, etc., entonces está en un chat nativo de Teams. 

Teams comprueba periódicamente el modo de actualización para los usuarios de otras organizaciones y, cuando encuentre un equipo que ejecute Teams en el modo de actualización de TeamsOnly, le pedirá que cambie a un chat nativo de Teams y bloquee el chat original.

Al cambiar a un chat nativo de Teams, Teams no combina las dos conversaciones. En su lugar, verá ambos chats en la fuente de chat. El nuevo chat nativo de Teams está activo, pero el chat antiguo de solo texto está bloqueado.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>¿Qué sucede si un usuario ya no está en el modo Solo para Teams?

Si tenía un chat nativo de Teams con personas de otras organizaciones y, a continuación, uno de los usuarios se cambia del modo de actualización de TeamsOnly, Teams bloquea el chat nativo de Teams y le proporciona un vínculo para un chat limitado de solo texto. No podrá continuar en el chat nativo de Teams. Todavía puede leer el chat nativo de Teams, pero no puede continuar la conversación allí.

Si Teams encuentra un chat antiguo de solo texto con esta persona, reactivará ese chat. En caso contrario, Teams crea un nuevo chat de solo texto.


## <a name="related-topics"></a>Temas relacionados

[Administrar el acceso externo en Teams](manage-external-access.md)
