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
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="b17a1-103">Experiencia de chat nativa para usuarios externos (federados) en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b17a1-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="b17a1-104">Cuando un usuario de Microsoft Teams chatea con un usuario externo (federado), la experiencia de chat se limita a texto.</span><span class="sxs-lookup"><span data-stu-id="b17a1-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="b17a1-105">Sin embargo, si tanto el usuario de Teams como la persona de otra organización se encuentra en el modo de actualización de TeamsOnly, puede tener una experiencia de chat "native-Teams", que incluye formato enriquecido, @mentions y otras características de chat.</span><span class="sxs-lookup"><span data-stu-id="b17a1-105">However, if both your Teams user and the person in another organization is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="b17a1-106">Es decir, puede tener la misma experiencia de chat de Teams completa con personas aptas en otras organizaciones que con los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="b17a1-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible people in other organizations as you'd have with users in your organization.</span></span> <span data-ttu-id="b17a1-107">Los chats nativos de Teams con personas de otras organizaciones solo se limitan a los chats uno a uno.</span><span class="sxs-lookup"><span data-stu-id="b17a1-107">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="b17a1-108">La experiencia de chat nativa para personas de otras organizaciones está activada para todos los inquilinos de Teams, pero no todos los usuarios son aptos.</span><span class="sxs-lookup"><span data-stu-id="b17a1-108">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="b17a1-109">Para que se le ofreca una experiencia de chat nativa, tanto el remitente como el receptor deben configurarse para el modo de actualización de TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="b17a1-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="b17a1-110">Para obtener más información sobre las directivas de actualización, lea [Establecer la configuración de coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b17a1-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="b17a1-111">Para ver una lista de las funciones de los usuarios con acceso externo en Teams, vea [Comparar el acceso externo y el de invitado.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="b17a1-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="b17a1-112">¿Cómo puedo saber si estoy en un chat nativo?</span><span class="sxs-lookup"><span data-stu-id="b17a1-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="b17a1-113">Si solo puede intercambiar texto en el chat con personas de otras organizaciones, entonces se encuentra en un chat estándar de acceso externo (federado).</span><span class="sxs-lookup"><span data-stu-id="b17a1-113">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="b17a1-114">Si tiene todas las demás funciones de chat, como formato, @mentions, emojis, etc., está en un chat nativo de Teams.</span><span class="sxs-lookup"><span data-stu-id="b17a1-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="b17a1-115">Teams comprueba periódicamente el modo de actualización de las personas de otras organizaciones y, cuando encuentra un equipo que ejecuta Teams en el modo de actualización De Teams, le pedirá que cambie a un chat nativo de Teams y bloquee el chat original.</span><span class="sxs-lookup"><span data-stu-id="b17a1-115">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="b17a1-116">Cuando cambia a un chat nativo de Teams, Teams no combina las dos conversaciones.</span><span class="sxs-lookup"><span data-stu-id="b17a1-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="b17a1-117">En su lugar, verá ambos chats en su fuente de chat.</span><span class="sxs-lookup"><span data-stu-id="b17a1-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="b17a1-118">El nuevo chat de Teams nativo está activo, pero el chat antiguo de solo texto está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="b17a1-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="b17a1-119">¿Qué sucede si un usuario ya no está en el modo Solo equipos?</span><span class="sxs-lookup"><span data-stu-id="b17a1-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="b17a1-120">Si tiene un chat nativo de Teams con personas de otras organizaciones y luego uno de usted sale del modo de actualización TeamsOnly, Teams bloquea el chat nativo de Teams y le proporciona un vínculo para un chat limitado de solo texto.</span><span class="sxs-lookup"><span data-stu-id="b17a1-120">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="b17a1-121">No podrá continuar en el chat nativo de Teams.</span><span class="sxs-lookup"><span data-stu-id="b17a1-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="b17a1-122">Aún puede leer el chat nativo de Teams, pero no puede continuar la conversación allí.</span><span class="sxs-lookup"><span data-stu-id="b17a1-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="b17a1-123">Si Teams encuentra un chat antiguo de solo texto con esta persona, se reactivará ese chat.</span><span class="sxs-lookup"><span data-stu-id="b17a1-123">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="b17a1-124">En caso contrario, Teams crea un nuevo chat de solo texto.</span><span class="sxs-lookup"><span data-stu-id="b17a1-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b17a1-125">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b17a1-125">Related topics</span></span>

[<span data-ttu-id="b17a1-126">Administrar el acceso externo en Teams</span><span class="sxs-lookup"><span data-stu-id="b17a1-126">Manage external access in Teams</span></span>](manage-external-access.md)
