---
title: Presencia de usuario en los equipos
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rakayala
description: Los administradores de información deben conocer acerca de la presencia en los equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1934a602d89240c89ffb4f7410192d19a7dd2e61
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533029"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="5356f-103">Presencia de usuario en los equipos</span><span class="sxs-lookup"><span data-stu-id="5356f-103">User Presence in Teams</span></span>

<span data-ttu-id="5356f-104">Presencia forma parte de un perfil de usuario en Microsoft Teams (y a lo largo de Office 365) – e indica la disponibilidad actual y el estado a otros usuarios de la organización del usuario.</span><span class="sxs-lookup"><span data-stu-id="5356f-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="5356f-105">De forma predeterminada, cualquier persona de su organización con los equipos puede ver si otros usuarios están disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="5356f-105">By default, anyone in your organization using Teams can see whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="5356f-106">Estados de presencia en los equipos</span><span class="sxs-lookup"><span data-stu-id="5356f-106">Presence states in Teams</span></span>

<span data-ttu-id="5356f-107">Los Estados de presencia de usuario disponibles en los equipos son:</span><span class="sxs-lookup"><span data-stu-id="5356f-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="5356f-108">Configurada por el usuario</span><span class="sxs-lookup"><span data-stu-id="5356f-108">User configured</span></span>|<span data-ttu-id="5356f-109">Aplicación configurado</span><span class="sxs-lookup"><span data-stu-id="5356f-109">App configured</span></span>|
|:--- |:---|
| ![Presencia disponible](media/Presence_Available.png) <span data-ttu-id="5356f-111">Disponible</span><span class="sxs-lookup"><span data-stu-id="5356f-111">Available</span></span>|![Presencia disponible](media/Presence_Available.png) <span data-ttu-id="5356f-113">Disponible</span><span class="sxs-lookup"><span data-stu-id="5356f-113">Available</span></span>|
|| ![oof disponible](media/Presence_Available_OOF.png) <span data-ttu-id="5356f-115">Está disponible, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="5356f-115">Available, Out of Office</span></span> |
|  ![No disponible](media/Presence_Busy.png) <span data-ttu-id="5356f-117">No disponible</span><span class="sxs-lookup"><span data-stu-id="5356f-117">Busy</span></span> |  ![No disponible](media/Presence_Busy.png) <span data-ttu-id="5356f-119">No disponible</span><span class="sxs-lookup"><span data-stu-id="5356f-119">Busy</span></span>  |
|| ![No disponible](media/Presence_Busy.png) <span data-ttu-id="5356f-121">En una llamada</span><span class="sxs-lookup"><span data-stu-id="5356f-121">In a call</span></span>|
|| ![No disponible](media/Presence_Busy.png) <span data-ttu-id="5356f-123">En una reunión</span><span class="sxs-lookup"><span data-stu-id="5356f-123">In a meeting</span></span> |
|| ![oof ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="5356f-125">En una llamada, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="5356f-125">In a call, out of office</span></span>|
|  ![No molestar](media/Presence_DND.png) <span data-ttu-id="5356f-127">No molestar</span><span class="sxs-lookup"><span data-stu-id="5356f-127">Do not disturb</span></span> ||
|| ![No molestar](media/Presence_DND.png) <span data-ttu-id="5356f-129">Presentación</span><span class="sxs-lookup"><span data-stu-id="5356f-129">Presenting</span></span>|
| ![estado ausente](media/Presence_Away.png) <span data-ttu-id="5356f-131">Estado ausente</span><span class="sxs-lookup"><span data-stu-id="5356f-131">Away</span></span>| ![estado ausente](media/Presence_Away.png) <span data-ttu-id="5356f-133">Estado ausente</span><span class="sxs-lookup"><span data-stu-id="5356f-133">Away</span></span>|
|| <span data-ttu-id="5356f-134">![ausente](media/Presence_Away.png) como ausente último visto *tiempo*</span><span class="sxs-lookup"><span data-stu-id="5356f-134">![away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![estado ausente](media/Presence_Away.png) <span data-ttu-id="5356f-136">Enseguida regreso</span><span class="sxs-lookup"><span data-stu-id="5356f-136">Be right back</span></span>| |
|| ![estado ausente](media/Presence_Away.png)  <span data-ttu-id="5356f-138">Día libre</span><span class="sxs-lookup"><span data-stu-id="5356f-138">Off Work</span></span>|
|| ![Sin conexión](media/Presence_Offline.png) <span data-ttu-id="5356f-140">Sin conexión</span><span class="sxs-lookup"><span data-stu-id="5356f-140">Offline</span></span> |
|| ![desconocido](media/Presence_Unknown.png) <span data-ttu-id="5356f-142">Estado desconocido</span><span class="sxs-lookup"><span data-stu-id="5356f-142">Status unknown</span></span>|
||![bloqueado](media/Presence_Blocked.png) <span data-ttu-id="5356f-144">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="5356f-144">Blocked</span></span> |
|| ![Fuera de la oficina](media/Presence_OOF.png) <span data-ttu-id="5356f-146">Fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="5356f-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="5356f-147">Los usuarios pueden establecer manualmente su estado de presencia actual a algunas de las opciones y obtiene refleja su estado a todos los demás usuarios.</span><span class="sxs-lookup"><span data-stu-id="5356f-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="5356f-148">Detalles de la presencia de usuario adicionales también se actualizan automáticamente en función de la actividad del usuario (por ejemplo, disponible o ausente), Estados del calendario de Outlook (como en una reunión) o Estados de la aplicación de los equipos (en una llamada, presentar), los Estados de las que se aplica sangría en la lista.</span><span class="sxs-lookup"><span data-stu-id="5356f-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="5356f-149">No hay un tiempo de espera de inactividad de 15 minutos, después del cual se restablecerá el estado de presencia actual de los usuarios a ausente.</span><span class="sxs-lookup"><span data-stu-id="5356f-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="5356f-150">Los usuarios pueden especificar quién puede interrumpir a través de (póngase en contacto con ellos reemplazar una opción de configuración no molestar).</span><span class="sxs-lookup"><span data-stu-id="5356f-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="5356f-151">Estas opciones están disponibles en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5356f-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="5356f-152">Los equipos no es Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="5356f-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="5356f-153">La siguiente configuración de administración en Skype para la empresa es diferente en los equipos:</span><span class="sxs-lookup"><span data-stu-id="5356f-153">The following Admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="5356f-154">Uso compartido de presencia siempre está habilitado en los equipos de los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="5356f-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="5356f-155">Configuración de privacidad (decidir quién puede ver la presencia) no está disponible en los equipos.</span><span class="sxs-lookup"><span data-stu-id="5356f-155">Privacy (deciding who can see Presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="5356f-156">Uso compartido con todos los usuarios (incluidos los servicios federados) de presencia siempre está habilitado para los usuarios en los equipos.</span><span class="sxs-lookup"><span data-stu-id="5356f-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="5356f-157">Está visible en su lista de contactos (si tuvieran uno en SfB) **conversaciones > contactos** o en **llamadas > contactos**.</span><span class="sxs-lookup"><span data-stu-id="5356f-157">Their contact list (if they had one in SfB) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="5356f-158">Características de cliente no molestar e innovadora siempre están habilitadas para los usuarios en los equipos.</span><span class="sxs-lookup"><span data-stu-id="5356f-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="5356f-159">Calendario (incluye OOF & otra información de calendario) integración siempre está habilitada para los usuarios de los equipos si integrado con Outlook.</span><span class="sxs-lookup"><span data-stu-id="5356f-159">Calendar (includes OOF & other calendar info) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="5356f-160">El indicador de *Ausente desde* (si está en un entorno dual con Skype para la empresa) o *visto por última vez* siempre está habilitado para los usuarios en los equipos.</span><span class="sxs-lookup"><span data-stu-id="5356f-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>
- <span data-ttu-id="5356f-161">Establecer un estado de presencia personalizados no está habilitado para los usuarios en los equipos.</span><span class="sxs-lookup"><span data-stu-id="5356f-161">Setting a custom presence status is not enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="5356f-162">La capacidad de una administración de equipos para personalizar estas opciones no se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="5356f-162">The ability of a Teams Admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="5356f-163">Coexistencia con Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="5356f-163">Coexistence with Skype for Business</span></span>

<span data-ttu-id="5356f-164">Para obtener información detallada sobre el funcionamiento de presencia de los equipos cuando coexisten con Skype para la empresa, vea [coexistencia con Skype para la empresa](coexistence-chat-calls-presence.md) .</span><span class="sxs-lookup"><span data-stu-id="5356f-164">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 