---
title: Teams de aplicaciones para usuarios no estándar
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo las aplicaciones Microsoft Teams se comportan para los usuarios no estándar.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: c27a73928e0740eb325c269fd5ac625fa4c43086
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628929"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="709fc-103">Microsoft Teams de aplicaciones para usuarios no estándar</span><span class="sxs-lookup"><span data-stu-id="709fc-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="709fc-104">En este artículo se describe cómo se comportan las aplicaciones de Teams cuando los usuarios invitados, externos (federados) y anónimos están presentes en Teams contexto.</span><span class="sxs-lookup"><span data-stu-id="709fc-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="709fc-105">Un **usuario invitado** es alguien que no es empleado, estudiante o miembro de su organización.</span><span class="sxs-lookup"><span data-stu-id="709fc-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="709fc-106">Tampoco tiene una cuenta profesional o educativa con su organización.</span><span class="sxs-lookup"><span data-stu-id="709fc-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="709fc-107">Un **usuario externo (federado)** pertenece a otro dominio y no tiene acceso a los equipos ni a los recursos del equipo de su organización.</span><span class="sxs-lookup"><span data-stu-id="709fc-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="709fc-108">Para obtener una comparación más detallada de los usuarios invitados frente a los externos, vea [Comunicarse con usuarios de otras organizaciones.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="709fc-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="709fc-109">Un **usuario anónimo** es un concepto en Teams reuniones en las que el usuario se ha unido a la reunión a través de un vínculo.</span><span class="sxs-lookup"><span data-stu-id="709fc-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="709fc-110">El usuario no ha iniciado sesión con su cuenta de Microsoft u organización.</span><span class="sxs-lookup"><span data-stu-id="709fc-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="709fc-111">Usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="709fc-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="709fc-112">Instalar, actualizar y eliminar para usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="709fc-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="709fc-113">Los invitados no pueden instalar, actualizar o eliminar aplicaciones en un contexto compartido, como un chat, un canal o una reunión, pero pueden hacerlo en su ámbito personal mediante extensiones de mensajes y vínculos directos.</span><span class="sxs-lookup"><span data-stu-id="709fc-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="709fc-114">Los invitados no tienen acceso a la tienda de aplicaciones Teams desde la aplicación de escritorio Teams, pero pueden acceder a ella con un vínculo directo.</span><span class="sxs-lookup"><span data-stu-id="709fc-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="709fc-115">Comportamiento y directiva de uso para usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="709fc-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="709fc-116">Los invitados pueden usar una aplicación si la aplicación la instaló un usuario nativo.</span><span class="sxs-lookup"><span data-stu-id="709fc-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="709fc-117">Bots instalados en un canal</span><span class="sxs-lookup"><span data-stu-id="709fc-117">Bots installed to a channel</span></span>

<span data-ttu-id="709fc-118">Los bots pueden enviar mensajes de forma proactiva a los usuarios invitados, pero los invitados no pueden interactuar con el bot.</span><span class="sxs-lookup"><span data-stu-id="709fc-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="709fc-119">Los invitados no pueden enviar mensajes al bot uno a uno, mencionar el bot o interactuar con tarjetas adaptables que se comunican con el bot.</span><span class="sxs-lookup"><span data-stu-id="709fc-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="709fc-120">Bots personales instalados con directivas</span><span class="sxs-lookup"><span data-stu-id="709fc-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="709fc-121">Los invitados se ajustarán a las directivas de permisos globales y de toda la organización establecidas para el inquilino del host para cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="709fc-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="709fc-122">Si una aplicación está bloqueada para toda la organización host, los invitados tampoco pueden usar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="709fc-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="709fc-123">Los bots incluidos en la directiva de configuración predeterminada global de la aplicación también se instalarán para los invitados.</span><span class="sxs-lookup"><span data-stu-id="709fc-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="709fc-124">Una vez instalado un bot, los bots pueden comunicarse proactivamente con los invitados y los invitados pueden comunicarse de nuevo con los bots.</span><span class="sxs-lookup"><span data-stu-id="709fc-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="709fc-125">No puede quitar un invitado de la directiva de configuración de aplicaciones predeterminada global.</span><span class="sxs-lookup"><span data-stu-id="709fc-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="709fc-126">Para evitar que los invitados accedan a bots, puede crear más directivas de configuración de aplicaciones, asignarlas a usuarios internos e instalar bots con las directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="709fc-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="709fc-127">Usuarios externos (federados)</span><span class="sxs-lookup"><span data-stu-id="709fc-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="709fc-128">Instalar, actualizar y eliminar para usuarios externos</span><span class="sxs-lookup"><span data-stu-id="709fc-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="709fc-129">Los usuarios externos no pueden instalar, actualizar ni eliminar aplicaciones en ningún contexto, como un chat, un canal o una reunión personal.</span><span class="sxs-lookup"><span data-stu-id="709fc-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="709fc-130">No tienen acceso a la tienda Teams aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="709fc-130">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="709fc-131">Comportamiento de uso y directiva para usuarios externos</span><span class="sxs-lookup"><span data-stu-id="709fc-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="709fc-132">Los usuarios externos no pueden usar ninguna aplicación Teams y, cuando se agrega un usuario externo a un contexto con usuarios nativos, todos los usuarios , nativos y externos, ya no pueden usar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="709fc-132">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>
- <span data-ttu-id="709fc-133">Las directivas de aplicaciones no afectan a los usuarios externos, ya que no pueden usar Teams aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="709fc-133">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="709fc-134">Usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="709fc-134">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="709fc-135">Instalar, actualizar y eliminar para usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="709fc-135">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="709fc-136">Los usuarios anónimos no pueden instalar, actualizar ni eliminar aplicaciones en reuniones.</span><span class="sxs-lookup"><span data-stu-id="709fc-136">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="709fc-137">Comportamiento y directiva de uso para usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="709fc-137">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="709fc-138">Los usuarios anónimos no pueden usar directamente las aplicaciones en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="709fc-138">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="709fc-139">Los usuarios nativos pueden seguir usando las aplicaciones de reuniones si hay usuarios anónimos presentes.</span><span class="sxs-lookup"><span data-stu-id="709fc-139">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="709fc-140">Si una aplicación envía una tarjeta adaptable en el chat, los usuarios anónimos pueden interactuar con la tarjeta.</span><span class="sxs-lookup"><span data-stu-id="709fc-140">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="709fc-141">Para obtener más información, lea [Permitir que usuarios anónimos se unan a reuniones.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="709fc-141">For more information, read [Allow anonymous users to join meetings](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="709fc-142">Los usuarios anónimos heredarán la directiva de permisos predeterminada global a nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="709fc-142">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="709fc-143">Pueden interactuar con las aplicaciones en Teams reuniones si la directiva de permisos de nivel de usuario ha habilitado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="709fc-143">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="709fc-144">Los usuarios anónimos solo pueden interactuar con aplicaciones que ya están disponibles en una reunión y que no pueden adquirir ni administrar estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="709fc-144">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
