---
title: Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga más información sobre la experiencia de chat de equipos nativos para usuarios de acceso externo (federados) en Microsoft Teams, disponible entre usuarios externos donde los dos usuarios están en el modo de actualización de TeamsOnly.
ms.openlocfilehash: 0d6f7ed00482ee68233b4d93cc101e9c820a6f14
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832690"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams
======================================

Cuando un usuario de Microsoft Teams está conversando con un usuario externo (federado), la experiencia de chat se limita al texto. Sin embargo, si el inquilino de su equipo y el del usuario externo están en el modo de actualización de TeamsOnly, puede tener una "experiencia de chat de equipos nativos", que incluye formato enriquecido, @mentions y otras características de chat. En otras palabras, puede tener la misma experiencia de conversación enriquecida 1:1 con los usuarios externos que usted tiene con los usuarios de su organización. Los chats nativos con usuarios externos aún se limitan a chats de 1:1 (los usuarios externos no pueden realizar chats grupales).

La experiencia de chat nativa para usuarios externos se activa para todos los inquilinos de Teams, pero no todos los usuarios son elegibles. Para que se le ofrezca una experiencia de chat nativa, el remitente y el destinatario deben estar en un inquilino de teams que ejecute el modo de actualización TeamsOnly. Para obtener más información sobre las directivas de actualización, lea [configuración de la coexistencia y actualización de la configuración](setting-your-coexistence-and-upgrade-settings.md).

Para ver una lista de las funciones de los usuarios de acceso externo en Teams, consulte [comparar el acceso externo y](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)el de invitado.

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>¿Cómo puedo saber si estoy en una conversación nativa?

Si solo puedes intercambiar texto en tu conversación con un usuario externo, entonces estás en una conversación estándar de acceso externo (federado). Si tiene todas las demás funcionalidades de chat, incluidos formato, @mentions, emojis, etc., está en un chat de equipos nativos con su usuario externo. 

Teams comprueba periódicamente el modo de actualización para los usuarios externos y, cuando encuentra un usuario externo que ejecuta Teams en el modo de actualización de TeamsOnly, se le pedirá que cambie a un chat de equipos nativos y bloqueará la conversación original.

Al cambiar a un chat de equipos nativos, Teams no combina las dos conversaciones. En su lugar, verás ambos chats en tu fuente de chat. La nueva conversación de equipos nativos está activa, pero la antigua conversación de solo texto está bloqueada.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>¿Qué sucede si un usuario no está en el modo solo de equipo?

Si estabas en una conversación nativa de equipos con un usuario externo y después uno de usted se desconecta del modo de actualización de TeamsOnly, Teams bloquea la conversación de equipos nativos y le da un vínculo a un chat limitado de solo texto. No podrás continuar en la conversación nativa de equipos. Aún puedes leer la conversación de equipos nativos, pero no puedes continuar con ella.

Si Teams encuentra una conversación que solo es de texto con este usuario externo, la reactivará. De lo contrario, Teams crea un nuevo chat de solo texto.


## <a name="related-topics"></a>Temas relacionados

[Administrar el acceso externo en Teams](manage-external-access.md)
