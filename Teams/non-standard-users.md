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
description: Obtenga información sobre el comportamiento de las aplicaciones de Microsoft Teams para los usuarios no estándar.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66754565737929ec9d34125ca421c7e3eed9fe65
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278550"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="85a50-103">Comportamiento de las aplicaciones de Microsoft Teams para usuarios no estándar</span><span class="sxs-lookup"><span data-stu-id="85a50-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="85a50-104">En este artículo se describe cómo se comportan las aplicaciones de Teams cuando los usuarios invitados, externos (federados) y anónimos están presentes en un contexto de Teams.</span><span class="sxs-lookup"><span data-stu-id="85a50-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="85a50-105">Un **usuario invitado** es alguien que no es un empleado, un estudiante o un miembro de su organización.</span><span class="sxs-lookup"><span data-stu-id="85a50-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="85a50-106">Tampoco tiene una cuenta profesional o educativa con su organización.</span><span class="sxs-lookup"><span data-stu-id="85a50-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="85a50-107">Un **usuario externo (federado) pertenece** a otro dominio y no tiene acceso a los equipos ni a los recursos del equipo de su organización.</span><span class="sxs-lookup"><span data-stu-id="85a50-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

>[!Note]
> <span data-ttu-id="85a50-108">Para ver una comparación más detallada entre los usuarios invitados y los externos, vea la comunicación [con usuarios de otras organizaciones.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)</span><span class="sxs-lookup"><span data-stu-id="85a50-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations).</span></span>

- <span data-ttu-id="85a50-109">Un **usuario anónimo es** un concepto en las reuniones de Teams en las que el usuario se ha unido a la reunión a través de un vínculo.</span><span class="sxs-lookup"><span data-stu-id="85a50-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="85a50-110">El usuario no ha iniciado sesión con su cuenta de Microsoft o de la organización.</span><span class="sxs-lookup"><span data-stu-id="85a50-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="85a50-111">Acceso de usuario invitado</span><span class="sxs-lookup"><span data-stu-id="85a50-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="85a50-112">Instalar, actualizar y eliminar para usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="85a50-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="85a50-113">Los invitados no pueden instalar, actualizar o eliminar aplicaciones en un contexto compartido, como un chat, un canal o una reunión.</span><span class="sxs-lookup"><span data-stu-id="85a50-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="85a50-114">Pueden instalar, actualizar o eliminar aplicaciones en su ámbito personal mediante extensiones de mensajes y vínculos directos.</span><span class="sxs-lookup"><span data-stu-id="85a50-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="85a50-115">Los invitados no tienen acceso a la tienda de aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="85a50-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="85a50-116">Comportamiento y directiva de uso para usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="85a50-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="85a50-117">Los invitados pueden usar una aplicación si la aplicación fue instalada por un usuario nativo.</span><span class="sxs-lookup"><span data-stu-id="85a50-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="85a50-118">Los bots pueden enviar mensajes de forma proactiva a los usuarios invitados, pero los invitados no pueden interactuar con el bot.</span><span class="sxs-lookup"><span data-stu-id="85a50-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="85a50-119">Los invitados no pueden enviar un mensaje al bot 1:1, @ mencionar al bot ni interactuar con tarjetas adaptables que se comunican con el bot.</span><span class="sxs-lookup"><span data-stu-id="85a50-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="85a50-120">Los invitados se ajustarán a las directivas de permisos globales y de toda la organización establecidas para el inquilino host de cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="85a50-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="85a50-121">Es decir, si se bloquea una aplicación para toda la organización host, los invitados tampoco podrán usar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="85a50-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="85a50-122">Las directivas de configuración no se aplican a los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="85a50-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="85a50-123">Esto significa que la aplicación anclada por el administrador de la directiva predeterminada no afecta a los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="85a50-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="85a50-124">Acceso de usuarios externos (federados)</span><span class="sxs-lookup"><span data-stu-id="85a50-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="85a50-125">Instalar, actualizar y eliminar usuarios externos</span><span class="sxs-lookup"><span data-stu-id="85a50-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="85a50-126">Los usuarios externos no pueden instalar, actualizar o eliminar aplicaciones en ningún contexto, como un chat, un canal o una reunión personal.</span><span class="sxs-lookup"><span data-stu-id="85a50-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="85a50-127">No tienen acceso a la tienda de aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="85a50-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="85a50-128">Comportamiento y directiva de uso para usuarios externos</span><span class="sxs-lookup"><span data-stu-id="85a50-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="85a50-129">Los usuarios externos no pueden usar ninguna aplicación de Teams y, cuando se agrega un usuario externo a un contexto con los usuarios nativos, todos los usuarios (nativos y externos) ya no pueden usar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="85a50-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="85a50-130">Las directivas de aplicación no afectan a los usuarios externos, ya que no pueden usar las aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="85a50-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="85a50-131">Acceso anónimo en reuniones</span><span class="sxs-lookup"><span data-stu-id="85a50-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="85a50-132">Instalar, actualizar y eliminar para usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="85a50-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="85a50-133">Los usuarios anónimos no pueden instalar, actualizar ni eliminar aplicaciones en reuniones.</span><span class="sxs-lookup"><span data-stu-id="85a50-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="85a50-134">Comportamiento y directiva de uso para usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="85a50-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="85a50-135">Los usuarios anónimos no pueden usar aplicaciones directamente en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="85a50-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="85a50-136">Los usuarios nativos pueden seguir usando las aplicaciones de reuniones si hay usuarios anónimos presentes.</span><span class="sxs-lookup"><span data-stu-id="85a50-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="85a50-137">Si una aplicación envía una tarjeta adaptable en el chat, los usuarios anónimos pueden interactuar con la tarjeta.</span><span class="sxs-lookup"><span data-stu-id="85a50-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span>

<span data-ttu-id="85a50-138">Los usuarios anónimos heredarán la directiva de permisos predeterminada global a nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="85a50-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="85a50-139">Este control permite a los usuarios anónimos interactuar con aplicaciones en reuniones de Teams si la directiva de permisos a nivel de usuario ha habilitado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="85a50-139">This control allows anonymous users to interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="85a50-140">Los usuarios anónimos solo pueden interactuar con aplicaciones que ya están disponibles en una reunión y que no pueden adquirir ni administrar estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="85a50-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
