---
title: Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 1274e71f5854e05049c8d766bd3456a0792b1032
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583849"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="a97e5-103">Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a97e5-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

<span data-ttu-id="a97e5-104">Cuando un usuario de Microsoft Teams está conversando con un usuario externo (federado), la experiencia de chat se limita al texto.</span><span class="sxs-lookup"><span data-stu-id="a97e5-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="a97e5-105">Sin embargo, si el usuario de su equipo y el usuario externo están en el modo de actualización de TeamsOnly, puede tener una "experiencia de chat de equipos nativos", que incluye formato enriquecido, @mentions y otras características de chat.</span><span class="sxs-lookup"><span data-stu-id="a97e5-105">However, if both your Teams user and the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="a97e5-106">En otras palabras, puede tener la misma experiencia de conversación enriquecida 1:1 con los usuarios externos que usted tiene con los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="a97e5-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="a97e5-107">Los chats nativos con usuarios externos aún se limitan a chats de 1:1 (los usuarios externos no pueden realizar chats grupales).</span><span class="sxs-lookup"><span data-stu-id="a97e5-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="a97e5-108">La experiencia de chat nativa para usuarios externos se activa para todos los inquilinos de Teams, pero no todos los usuarios son elegibles.</span><span class="sxs-lookup"><span data-stu-id="a97e5-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="a97e5-109">Para que se le ofrezca una experiencia de chat nativa, el remitente y el destinatario deben estar configurados para el modo de actualización TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="a97e5-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="a97e5-110">Para obtener más información sobre las directivas de actualización, lea [configuración de la coexistencia y actualización de la configuración](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a97e5-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="a97e5-111">Para ver una lista de las funciones de los usuarios de acceso externo en Teams, consulte [comparar el acceso externo y](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)el de invitado.</span><span class="sxs-lookup"><span data-stu-id="a97e5-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="a97e5-112">¿Cómo puedo saber si estoy en una conversación nativa?</span><span class="sxs-lookup"><span data-stu-id="a97e5-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="a97e5-113">Si solo puedes intercambiar texto en tu conversación con un usuario externo, entonces estás en una conversación estándar de acceso externo (federado).</span><span class="sxs-lookup"><span data-stu-id="a97e5-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="a97e5-114">Si tiene todas las demás funcionalidades de chat, incluidos formato, @mentions, emojis, etc., está en un chat de equipos nativos con su usuario externo.</span><span class="sxs-lookup"><span data-stu-id="a97e5-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="a97e5-115">Teams comprueba periódicamente el modo de actualización para los usuarios externos y, cuando encuentra un usuario externo que ejecuta Teams en el modo de actualización de TeamsOnly, se le pedirá que cambie a un chat de equipos nativos y bloqueará la conversación original.</span><span class="sxs-lookup"><span data-stu-id="a97e5-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="a97e5-116">Al cambiar a un chat de equipos nativos, Teams no combina las dos conversaciones.</span><span class="sxs-lookup"><span data-stu-id="a97e5-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="a97e5-117">En su lugar, verás ambos chats en tu fuente de chat.</span><span class="sxs-lookup"><span data-stu-id="a97e5-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="a97e5-118">La nueva conversación de equipos nativos está activa, pero la antigua conversación de solo texto está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="a97e5-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="a97e5-119">¿Qué sucede si un usuario no está en el modo solo de equipo?</span><span class="sxs-lookup"><span data-stu-id="a97e5-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="a97e5-120">Si estabas en una conversación nativa de equipos con un usuario externo y después uno de usted se desconecta del modo de actualización de TeamsOnly, Teams bloquea la conversación de equipos nativos y le da un vínculo a un chat limitado de solo texto.</span><span class="sxs-lookup"><span data-stu-id="a97e5-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="a97e5-121">No podrás continuar en la conversación nativa de equipos.</span><span class="sxs-lookup"><span data-stu-id="a97e5-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="a97e5-122">Aún puedes leer la conversación de equipos nativos, pero no puedes continuar con ella.</span><span class="sxs-lookup"><span data-stu-id="a97e5-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="a97e5-123">Si Teams encuentra una conversación que solo es de texto con este usuario externo, la reactivará.</span><span class="sxs-lookup"><span data-stu-id="a97e5-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="a97e5-124">De lo contrario, Teams crea un nuevo chat de solo texto.</span><span class="sxs-lookup"><span data-stu-id="a97e5-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a97e5-125">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a97e5-125">Related topics</span></span>

[<span data-ttu-id="a97e5-126">Administrar el acceso externo en Teams</span><span class="sxs-lookup"><span data-stu-id="a97e5-126">Manage external access in Teams</span></span>](manage-external-access.md)
