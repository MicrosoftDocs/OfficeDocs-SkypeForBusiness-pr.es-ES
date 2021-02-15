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
description: Obtenga información sobre la experiencia de chat nativa de Teams para los usuarios con acceso externo (federado) en Microsoft Teams, donde ambos usuarios se encuentran en el modo de actualización de TeamsOnly.
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055662"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams

Cuando un usuario de Microsoft Teams chatea con un usuario externo (federado), la experiencia de chat se limita a texto. Sin embargo, si tanto el usuario de Teams como la persona de otra organización se encuentra en el modo de actualización de TeamsOnly, puede tener una experiencia de chat "native-Teams", que incluye formato enriquecido, @mentions y otras características de chat. Es decir, puede tener la misma experiencia de chat de Teams completa con personas aptas en otras organizaciones que con los usuarios de su organización. Los chats nativos de Teams con personas de otras organizaciones se limitan solo a los chats entre dos personas.

La experiencia de chat nativa para personas de otras organizaciones está activada para todos los inquilinos de Teams, pero no todos los usuarios son aptos. Para que se le ofreca una experiencia de chat nativa, tanto el remitente como el receptor deben configurarse para el modo de actualización de TeamsOnly. Para obtener más información sobre las directivas de actualización, lea [Establecer la configuración de coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)

Para ver una lista de las funciones de los usuarios con acceso externo en Teams, vea [Comparar el acceso externo y el de invitado.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>¿Cómo puedo saber si estoy en un chat nativo?

Si solo puede intercambiar texto en el chat con personas de otras organizaciones, entonces se encuentra en un chat estándar de acceso externo (federado). Si tiene todas las demás funciones de chat, como formato, @mentions, emojis, etc., está en un chat nativo de Teams. 

Teams comprueba periódicamente el modo de actualización de las personas de otras organizaciones y, cuando encuentra un equipo que ejecuta Teams en el modo de actualización De Teams, le pedirá que cambie a un chat nativo de Teams y bloquee el chat original.

Cuando cambia a un chat nativo de Teams, Teams no combina las dos conversaciones. En su lugar, verá ambos chats en su fuente de chat. El nuevo chat de Teams nativo está activo, pero el chat antiguo de solo texto está bloqueado.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>¿Qué sucede si un usuario ya no está en el modo Solo equipos?

Si tiene un chat nativo de Teams con personas de otras organizaciones y luego uno de usted sale del modo de actualización TeamsOnly, Teams bloquea el chat nativo de Teams y le proporciona un vínculo para un chat limitado de solo texto. No podrá continuar en el chat nativo de Teams. Aún puede leer el chat nativo de Teams, pero no puede continuar la conversación allí.

Si Teams encuentra un chat antiguo de solo texto con esta persona, se reactivará ese chat. En caso contrario, Teams crea un nuevo chat de solo texto.


## <a name="related-topics"></a>Temas relacionados

[Administrar el acceso externo en Teams](manage-external-access.md)
