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
ms.openlocfilehash: 50ab15d188f2f8a198f59446a0bd5fd8015d0c74
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656033"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="d5a65-103">Microsoft Teams de aplicaciones para usuarios no estándar</span><span class="sxs-lookup"><span data-stu-id="d5a65-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="d5a65-104">En este artículo se describe cómo se comportan las aplicaciones de Teams cuando los usuarios invitados, externos (federados) y anónimos están presentes en Teams contexto.</span><span class="sxs-lookup"><span data-stu-id="d5a65-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="d5a65-105">Un **usuario invitado** es alguien que no es empleado, estudiante o miembro de su organización.</span><span class="sxs-lookup"><span data-stu-id="d5a65-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="d5a65-106">Tampoco tiene una cuenta profesional o educativa con su organización.</span><span class="sxs-lookup"><span data-stu-id="d5a65-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="d5a65-107">Un **usuario externo (federado)** pertenece a otro dominio y no tiene acceso a los equipos ni a los recursos del equipo de su organización.</span><span class="sxs-lookup"><span data-stu-id="d5a65-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="d5a65-108">Para obtener una comparación más detallada de los usuarios invitados frente a los externos, vea [Comunicarse con usuarios de otras organizaciones.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="d5a65-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="d5a65-109">Un **usuario anónimo** es un concepto en Teams reuniones en las que el usuario se ha unido a la reunión a través de un vínculo.</span><span class="sxs-lookup"><span data-stu-id="d5a65-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="d5a65-110">El usuario no ha iniciado sesión con su cuenta de Microsoft u organización.</span><span class="sxs-lookup"><span data-stu-id="d5a65-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="d5a65-111">Usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="d5a65-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="d5a65-112">Instalar, actualizar y eliminar para usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="d5a65-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="d5a65-113">Los invitados no pueden instalar, actualizar o eliminar aplicaciones en un contexto compartido, como un chat, un canal o una reunión, pero pueden hacerlo en su ámbito personal mediante extensiones de mensajes y vínculos directos.</span><span class="sxs-lookup"><span data-stu-id="d5a65-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="d5a65-114">Los invitados no tienen acceso a la tienda de aplicaciones Teams desde la aplicación de escritorio Teams, pero pueden acceder a ella con un vínculo directo.</span><span class="sxs-lookup"><span data-stu-id="d5a65-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="d5a65-115">Comportamiento y directiva de uso para usuarios invitados</span><span class="sxs-lookup"><span data-stu-id="d5a65-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="d5a65-116">Los invitados pueden usar una aplicación si la aplicación la instaló un usuario nativo.</span><span class="sxs-lookup"><span data-stu-id="d5a65-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="d5a65-117">Bots instalados en un canal</span><span class="sxs-lookup"><span data-stu-id="d5a65-117">Bots installed to a channel</span></span>

<span data-ttu-id="d5a65-118">Los bots pueden enviar mensajes de forma proactiva a los usuarios invitados, pero los invitados no pueden interactuar con el bot.</span><span class="sxs-lookup"><span data-stu-id="d5a65-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="d5a65-119">Los invitados no pueden enviar mensajes al bot uno a uno, mencionar el bot o interactuar con tarjetas adaptables que se comunican con el bot.</span><span class="sxs-lookup"><span data-stu-id="d5a65-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="d5a65-120">Bots personales instalados con directivas</span><span class="sxs-lookup"><span data-stu-id="d5a65-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="d5a65-121">Los invitados se ajustarán a las directivas de permisos globales y de toda la organización establecidas para el inquilino del host para cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5a65-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="d5a65-122">Si una aplicación está bloqueada para toda la organización host, los invitados tampoco pueden usar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5a65-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="d5a65-123">Los bots incluidos en la directiva de configuración predeterminada global de la aplicación también se instalarán para los invitados.</span><span class="sxs-lookup"><span data-stu-id="d5a65-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="d5a65-124">Una vez instalado un bot, los bots pueden comunicarse proactivamente con los invitados y los invitados pueden comunicarse de nuevo con los bots.</span><span class="sxs-lookup"><span data-stu-id="d5a65-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="d5a65-125">No puede quitar un invitado de la directiva de configuración de aplicaciones predeterminada global.</span><span class="sxs-lookup"><span data-stu-id="d5a65-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="d5a65-126">Para evitar que los invitados accedan a bots, puede crear más directivas de configuración de aplicaciones, asignarlas a usuarios internos e instalar bots con las directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d5a65-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="d5a65-127">Usuarios externos (federados)</span><span class="sxs-lookup"><span data-stu-id="d5a65-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="d5a65-128">Instalar, actualizar y eliminar para usuarios externos</span><span class="sxs-lookup"><span data-stu-id="d5a65-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="d5a65-129">Los usuarios externos no pueden instalar, actualizar ni eliminar aplicaciones en ningún contexto, como un chat, un canal o una reunión personal.</span><span class="sxs-lookup"><span data-stu-id="d5a65-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="d5a65-130">No tienen acceso a la tienda Teams aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d5a65-130">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="d5a65-131">Comportamiento de uso y directiva para usuarios externos</span><span class="sxs-lookup"><span data-stu-id="d5a65-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="d5a65-132">Las personas de otras organizaciones se adhieren a la directiva de permisos de usuario predeterminada de la organización de hospedaje y a la configuración de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="d5a65-132">People from other organizations adhere to the hosting organization's default user permission policy and org-wide settings.</span></span>
- <span data-ttu-id="d5a65-133">Los usuarios de la organización de hospedaje pueden agregar aplicaciones en chats de reunión con personas de otras organizaciones.</span><span class="sxs-lookup"><span data-stu-id="d5a65-133">Users in the hosting organization can add apps in meeting chats with people from other organizations.</span></span> <span data-ttu-id="d5a65-134">Los usuarios de otras organizaciones no pueden agregar aplicaciones en chats de reunión, pero pueden interactuar con bots y pestañas una vez agregados al chat.</span><span class="sxs-lookup"><span data-stu-id="d5a65-134">People from other organizations cannot add apps in meeting chats but can interact with bots and tabs once added to the chat.</span></span>
- <span data-ttu-id="d5a65-135">Después de instalar un bot en un chat, puede comunicarse proactivamente con personas de otras organizaciones en ese chat y esas personas pueden comunicarse con el bot.</span><span class="sxs-lookup"><span data-stu-id="d5a65-135">After a bot is installed in a chat, it can proactively communicate with people from other organizations in that chat and those people can communicate with bot.</span></span>
- <span data-ttu-id="d5a65-136">Se aplican las directivas de datos de la organización de hospedaje, así como las prácticas de uso compartido de datos de las aplicaciones de terceros compartidas por la organización de ese usuario.</span><span class="sxs-lookup"><span data-stu-id="d5a65-136">The data policies of the hosting organization, as well as the data sharing practices of any third-party apps shared by that user's organization, are applied.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="d5a65-137">Usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="d5a65-137">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="d5a65-138">Instalar, actualizar y eliminar para usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="d5a65-138">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="d5a65-139">Los usuarios anónimos no pueden instalar, actualizar ni eliminar aplicaciones en reuniones.</span><span class="sxs-lookup"><span data-stu-id="d5a65-139">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="d5a65-140">Comportamiento y directiva de uso para usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="d5a65-140">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="d5a65-141">Los usuarios anónimos no pueden usar directamente las aplicaciones en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="d5a65-141">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="d5a65-142">Los usuarios nativos pueden seguir usando las aplicaciones de reuniones si hay usuarios anónimos presentes.</span><span class="sxs-lookup"><span data-stu-id="d5a65-142">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="d5a65-143">Si una aplicación envía una tarjeta adaptable en el chat, los usuarios anónimos pueden interactuar con la tarjeta.</span><span class="sxs-lookup"><span data-stu-id="d5a65-143">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="d5a65-144">Para obtener más información, lea [Permitir que usuarios anónimos se unan a reuniones.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="d5a65-144">For more information, read [Allow anonymous users to join meetings](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="d5a65-145">Los usuarios anónimos heredarán la directiva de permisos predeterminada global a nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="d5a65-145">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="d5a65-146">Pueden interactuar con las aplicaciones en Teams reuniones si la directiva de permisos de nivel de usuario ha habilitado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5a65-146">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="d5a65-147">Los usuarios anónimos solo pueden interactuar con aplicaciones que ya están disponibles en una reunión y que no pueden adquirir ni administrar estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d5a65-147">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
