---
title: Comportamiento de las aplicaciones de Teams para usuarios no estándar
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo se comportan las aplicaciones de Microsoft Teams para los usuarios no estándar.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc4f4f53262127355afa573b0fc2abec6b05e64
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607522"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="e3737-103">Comportamiento de las aplicaciones de Microsoft Teams para usuarios no estándar</span><span class="sxs-lookup"><span data-stu-id="e3737-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="e3737-104">En este artículo se describe cómo se comportan las aplicaciones de Teams cuando los usuarios invitados, externos (federados) y anónimos están presentes en un contexto de Teams.</span><span class="sxs-lookup"><span data-stu-id="e3737-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="e3737-105">Un **usuario invitado** es alguien que no es empleado, estudiante o miembro de su organización.</span><span class="sxs-lookup"><span data-stu-id="e3737-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="e3737-106">Tampoco tiene una cuenta profesional o educativa con su organización.</span><span class="sxs-lookup"><span data-stu-id="e3737-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="e3737-107">Un **usuario externo (federado)** pertenece a otro dominio y no tiene acceso a los equipos ni a los recursos del equipo de su organización.</span><span class="sxs-lookup"><span data-stu-id="e3737-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

>[!Note]
> <span data-ttu-id="e3737-108">Para obtener una comparación más detallada de los usuarios invitados frente a los externos, vea [Comunicarse con usuarios de otras organizaciones.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="e3737-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="e3737-109">Un **usuario anónimo es** un concepto en las reuniones de Teams en las que el usuario se ha unido a la reunión a través de un vínculo.</span><span class="sxs-lookup"><span data-stu-id="e3737-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="e3737-110">El usuario no ha iniciado sesión con su cuenta de Microsoft u organización.</span><span class="sxs-lookup"><span data-stu-id="e3737-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="e3737-111">Acceso de usuario invitado</span><span class="sxs-lookup"><span data-stu-id="e3737-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="e3737-112">Instalar, actualizar y eliminar para usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="e3737-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="e3737-113">Los invitados no pueden instalar, actualizar ni eliminar aplicaciones en un contexto compartido, como un chat, un canal o una reunión.</span><span class="sxs-lookup"><span data-stu-id="e3737-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="e3737-114">Pueden instalar, actualizar o eliminar aplicaciones a su ámbito personal mediante extensiones de mensajes y vínculos directos.</span><span class="sxs-lookup"><span data-stu-id="e3737-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="e3737-115">Los invitados no tienen acceso a la tienda de aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="e3737-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="e3737-116">Comportamiento y directiva de uso para usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="e3737-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="e3737-117">Los invitados pueden usar una aplicación si la aplicación la instaló un usuario nativo.</span><span class="sxs-lookup"><span data-stu-id="e3737-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="e3737-118">Los bots pueden enviar mensajes de forma proactiva a los usuarios invitados, pero los invitados no pueden interactuar con el bot.</span><span class="sxs-lookup"><span data-stu-id="e3737-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="e3737-119">Los invitados no pueden enviar mensajes al bot 1:1, @ mencionar el bot o interactuar con tarjetas adaptables que se comunican con el bot.</span><span class="sxs-lookup"><span data-stu-id="e3737-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="e3737-120">Los invitados se ajustarán a las directivas de permisos globales y de toda la organización establecidas para el inquilino del host para cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="e3737-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="e3737-121">En otras palabras, si una aplicación está bloqueada para toda la organización anfitriona, los invitados tampoco pueden usar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e3737-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="e3737-122">Las directivas de configuración no se aplican a los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="e3737-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="e3737-123">Esto significa que la aplicación anclada por el administrador de la directiva predeterminada no afecta a los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="e3737-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="e3737-124">Acceso de usuario externo (federado)</span><span class="sxs-lookup"><span data-stu-id="e3737-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="e3737-125">Instalar, actualizar y eliminar para usuarios externos</span><span class="sxs-lookup"><span data-stu-id="e3737-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="e3737-126">Los usuarios externos no pueden instalar, actualizar ni eliminar aplicaciones en ningún contexto, como un chat, un canal o una reunión personal.</span><span class="sxs-lookup"><span data-stu-id="e3737-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="e3737-127">No tienen acceso a la tienda de aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="e3737-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="e3737-128">Comportamiento de uso y directiva para usuarios externos</span><span class="sxs-lookup"><span data-stu-id="e3737-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="e3737-129">Los usuarios externos no pueden usar ninguna aplicación de Teams y, cuando se agrega un usuario externo a un contexto con usuarios nativos, todos los usuarios , nativos y externos, ya no pueden usar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e3737-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="e3737-130">Las directivas de aplicaciones no afectan a los usuarios externos, ya que no pueden usar las aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="e3737-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="e3737-131">Usuario anónimo en acceso a reuniones</span><span class="sxs-lookup"><span data-stu-id="e3737-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="e3737-132">Instalar, actualizar y eliminar para usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="e3737-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="e3737-133">Los usuarios anónimos no pueden instalar, actualizar ni eliminar aplicaciones en reuniones.</span><span class="sxs-lookup"><span data-stu-id="e3737-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="e3737-134">Comportamiento y directiva de uso para usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="e3737-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="e3737-135">Los usuarios anónimos no pueden usar directamente las aplicaciones en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="e3737-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="e3737-136">Los usuarios nativos pueden seguir usando las aplicaciones de reuniones si hay usuarios anónimos presentes.</span><span class="sxs-lookup"><span data-stu-id="e3737-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="e3737-137">Si una aplicación envía una tarjeta adaptable en el chat, los usuarios anónimos pueden interactuar con la tarjeta Para obtener más información, vea Permitir que usuarios anónimos se [unan a reuniones.](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="e3737-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card For more information, see [Allow anonymous users to join meetings](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="e3737-138">Los usuarios anónimos heredarán la directiva de permisos predeterminada global a nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="e3737-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="e3737-139">Pueden interactuar con aplicaciones en reuniones de Teams si la directiva de permisos de nivel de usuario ha habilitado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e3737-139">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="e3737-140">Los usuarios anónimos solo pueden interactuar con aplicaciones que ya están disponibles en una reunión y que no pueden adquirir ni administrar estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e3737-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
