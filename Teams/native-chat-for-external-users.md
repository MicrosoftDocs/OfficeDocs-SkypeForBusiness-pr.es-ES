---
title: Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre la experiencia de chat nativa de Teams para usuarios de acceso externo (federado) en Microsoft Teams, donde ambos usuarios se encuentran en el modo de actualización de TeamsOnly.
ms.openlocfilehash: 759ad4f03de099637df0e92a7a8925a7c18ae3fd
ms.sourcegitcommit: 8f26bf0ff88f1f6881de32914be00d5f0cc7396a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2023
ms.locfileid: "69740805"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams

Cuando un usuario de Microsoft Teams chatea con un usuario externo (federado), la experiencia de chat se limita al texto. Sin embargo, si tanto el usuario de Teams como la persona de otra organización están en el modo de actualización de TeamsOnly, puede tener una "experiencia de chat nativa de Teams", que incluye formato enriquecido, @mentions y otras características de chat.

La experiencia de chat nativa para los usuarios de otras organizaciones está activada para todos los inquilinos de Teams, pero no todas las personas son aptas. Para que se le ofrezca una experiencia de chat nativa, tanto el remitente como el receptor deben configurarse para El modo de actualización de TeamsOnly. Para obtener más información sobre las directivas de actualización, lea [Establecer la configuración de coexistencia y actualización](setting-your-coexistence-and-upgrade-settings.md).

Para ver una lista de las capacidades de los usuarios de acceso externo en Teams, consulte [Comparar el acceso externo y de invitado](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).

> [!NOTE]
> La experiencia de chat nativa no está disponible para entornos en la nube de Microsoft 365: Microsoft 365 WorldWide (incluido GCC) de GCC High, GCC High de/a DoD o WW de/a DoD.

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Cómo Saber si estoy en un chat nativo?

Si solo puede intercambiar texto en el chat con personas de otras organizaciones, entonces está en un chat estándar de acceso externo (federado). Si tiene otras funciones de chat, como formato, @mentions, emojis, etc., entonces se encuentra en un chat nativo de Teams. 

Teams comprueba periódicamente el modo de actualización de los usuarios de otras organizaciones y, cuando encuentra un equipo que ejecuta Teams en el modo de actualización de TeamsOnly, le pedirá que cambie a un chat nativo de Teams y bloquee el chat original.

Al cambiar a un chat nativo de Teams, Teams no combina las dos conversaciones. En su lugar, verá ambos chats en la fuente de chats. El nuevo chat nativo de Teams está activo, pero el chat antiguo de solo texto está bloqueado.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>¿Qué sucede si un usuario ya no está en el modo Solo teams?

Si estaba teniendo un chat nativo de Teams con personas de otras organizaciones y luego uno de ustedes sale del modo de actualización de TeamsOnly, Teams bloquea el chat nativo de Teams y le proporciona un vínculo para un chat limitado de solo texto. No podrá continuar en el chat nativo de Teams. Aún puede leer el chat nativo de Teams, pero no puede continuar la conversación allí.

Si Teams encuentra un chat antiguo de solo texto con esta persona, se reactivará ese chat. En caso contrario, Teams crea un nuevo chat de solo texto.


## <a name="related-topics"></a>Temas relacionados

[Administrar el acceso externo en Teams](manage-external-access.md)
