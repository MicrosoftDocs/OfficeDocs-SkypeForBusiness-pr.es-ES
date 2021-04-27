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
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="a1c80-103">Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a1c80-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="a1c80-104">Cuando un usuario de Microsoft Teams chatea con un usuario externo (federado), la experiencia de chat se limita al texto.</span><span class="sxs-lookup"><span data-stu-id="a1c80-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="a1c80-105">Sin embargo, si tanto el usuario de Teams como la persona de otra organización están en el modo de actualización de TeamsOnly, puede tener una "experiencia de chat nativa de Teams", que incluye formato enriquecido, @mentions y otras características de chat.</span><span class="sxs-lookup"><span data-stu-id="a1c80-105">However, if both your Teams user and the person in another organization are in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="a1c80-106">Los chats de Native Teams con personas de otras organizaciones solo se limitan a chats de 1:1.</span><span class="sxs-lookup"><span data-stu-id="a1c80-106">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="a1c80-107">La experiencia de chat nativa para personas de otras organizaciones está activada para todos los inquilinos de Teams, pero no todas las personas son aptas.</span><span class="sxs-lookup"><span data-stu-id="a1c80-107">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="a1c80-108">Para ofrecer una experiencia de chat nativa, tanto el remitente como el receptor deben configurarse para el modo de actualización de TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="a1c80-108">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="a1c80-109">Para obtener más información sobre las directivas de actualización, lea [Establecer la configuración de coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a1c80-109">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="a1c80-110">Para ver una lista de las capacidades de los usuarios de acceso externo en Teams, vea [Comparar el acceso externo y el de invitado.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="a1c80-110">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="a1c80-111">¿Cómo puedo saber si estoy en un chat nativo?</span><span class="sxs-lookup"><span data-stu-id="a1c80-111">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="a1c80-112">Si solo puede intercambiar texto en el chat con personas de otras organizaciones, está en un chat estándar de acceso externo (federado).</span><span class="sxs-lookup"><span data-stu-id="a1c80-112">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="a1c80-113">Si tiene todas las demás funciones de chat, incluido el formato, @mentions, emojis, etc., entonces está en un chat nativo de Teams.</span><span class="sxs-lookup"><span data-stu-id="a1c80-113">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="a1c80-114">Teams comprueba periódicamente el modo de actualización para los usuarios de otras organizaciones y, cuando encuentre un equipo que ejecute Teams en el modo de actualización de TeamsOnly, le pedirá que cambie a un chat nativo de Teams y bloquee el chat original.</span><span class="sxs-lookup"><span data-stu-id="a1c80-114">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="a1c80-115">Al cambiar a un chat nativo de Teams, Teams no combina las dos conversaciones.</span><span class="sxs-lookup"><span data-stu-id="a1c80-115">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="a1c80-116">En su lugar, verá ambos chats en la fuente de chat.</span><span class="sxs-lookup"><span data-stu-id="a1c80-116">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="a1c80-117">El nuevo chat nativo de Teams está activo, pero el chat antiguo de solo texto está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="a1c80-117">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="a1c80-118">¿Qué sucede si un usuario ya no está en el modo Solo para Teams?</span><span class="sxs-lookup"><span data-stu-id="a1c80-118">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="a1c80-119">Si tenía un chat nativo de Teams con personas de otras organizaciones y, a continuación, uno de los usuarios se cambia del modo de actualización de TeamsOnly, Teams bloquea el chat nativo de Teams y le proporciona un vínculo para un chat limitado de solo texto.</span><span class="sxs-lookup"><span data-stu-id="a1c80-119">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="a1c80-120">No podrá continuar en el chat nativo de Teams.</span><span class="sxs-lookup"><span data-stu-id="a1c80-120">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="a1c80-121">Todavía puede leer el chat nativo de Teams, pero no puede continuar la conversación allí.</span><span class="sxs-lookup"><span data-stu-id="a1c80-121">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="a1c80-122">Si Teams encuentra un chat antiguo de solo texto con esta persona, reactivará ese chat.</span><span class="sxs-lookup"><span data-stu-id="a1c80-122">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="a1c80-123">En caso contrario, Teams crea un nuevo chat de solo texto.</span><span class="sxs-lookup"><span data-stu-id="a1c80-123">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a1c80-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a1c80-124">Related topics</span></span>

[<span data-ttu-id="a1c80-125">Administrar el acceso externo en Teams</span><span class="sxs-lookup"><span data-stu-id="a1c80-125">Manage external access in Teams</span></span>](manage-external-access.md)
