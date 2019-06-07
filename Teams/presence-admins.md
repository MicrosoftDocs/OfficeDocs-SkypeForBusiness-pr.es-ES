---
title: Presencia de usuario en Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Los administradores de la información deben comprender la presencia en Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30b50972dd53300905f580c51a410d699ebb1bff
ms.sourcegitcommit: 21a5550e3c0feafaa57dbcdc428ed13eedd276b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2019
ms.locfileid: "34748446"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="366a3-103">Presencia de usuario en Teams</span><span class="sxs-lookup"><span data-stu-id="366a3-103">User presence in Teams</span></span>

<span data-ttu-id="366a3-104">La presencia es parte del perfil de un usuario en Microsoft Teams (y en todo el Office 365), e indica la disponibilidad y el estado actuales del usuario a otros usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="366a3-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="366a3-105">De forma predeterminada, cualquier persona de la organización que use Teams puede ver casi el tiempo casi real, tanto si otros usuarios están disponibles en línea como si no.</span><span class="sxs-lookup"><span data-stu-id="366a3-105">By default, anyone in your organization using Teams can see - in nearly real time - whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="366a3-106">Estados de presencia en Teams</span><span class="sxs-lookup"><span data-stu-id="366a3-106">Presence states in Teams</span></span>

<span data-ttu-id="366a3-107">Los Estados de presencia de usuario disponibles en Teams son:</span><span class="sxs-lookup"><span data-stu-id="366a3-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="366a3-108">Usuario configurado</span><span class="sxs-lookup"><span data-stu-id="366a3-108">User configured</span></span>|<span data-ttu-id="366a3-109">Aplicación configurada</span><span class="sxs-lookup"><span data-stu-id="366a3-109">App configured</span></span>|
|:--- |:---|
| ![Marca CHEK verde sólido, que indica presencia disponible](media/Presence_Available.png) <span data-ttu-id="366a3-111">Disponible</span><span class="sxs-lookup"><span data-stu-id="366a3-111">Available</span></span>|![Marca CHEK verde sólido, que indica presencia disponible](media/Presence_Available.png) <span data-ttu-id="366a3-113">Disponible</span><span class="sxs-lookup"><span data-stu-id="366a3-113">Available</span></span>|
|| ![Marca de CHEK verde abierto, que indica el OOF disponible](media/Presence_Available_OOF.png) <span data-ttu-id="366a3-115">Disponible, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="366a3-115">Available, Out of Office</span></span> |
|  ![Círculo rojo sólido, que indica que está ocupado](media/Presence_Busy.png) <span data-ttu-id="366a3-117">Ocupado</span><span class="sxs-lookup"><span data-stu-id="366a3-117">Busy</span></span> |  ![Círculo rojo sólido, que indica que está ocupado](media/Presence_Busy.png) <span data-ttu-id="366a3-119">Ocupado</span><span class="sxs-lookup"><span data-stu-id="366a3-119">Busy</span></span>  |
|| ![Círculo rojo sólido, que indica que está ocupado en una llamada](media/Presence_Busy.png) <span data-ttu-id="366a3-121">En una llamada</span><span class="sxs-lookup"><span data-stu-id="366a3-121">In a call</span></span>|
|| ![Círculo rojo sólido, que indica que está ocupado en una reunión](media/Presence_Busy.png) <span data-ttu-id="366a3-123">En una reunión</span><span class="sxs-lookup"><span data-stu-id="366a3-123">In a meeting</span></span> |
|| ![Abrir un círculo rojo, que indica un OOF ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="366a3-125">En una llamada, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="366a3-125">In a call, out of office</span></span>|
|  ![Círculo rojo con línea blanca, que indica que no molestar](media/Presence_DND.png) <span data-ttu-id="366a3-127">No molestar</span><span class="sxs-lookup"><span data-stu-id="366a3-127">Do not disturb</span></span> ||
|| ![Círculo rojo con línea blanca, que indica la presentación](media/Presence_DND.png) <span data-ttu-id="366a3-129">Moderado</span><span class="sxs-lookup"><span data-stu-id="366a3-129">Presenting</span></span>|
| ![Icono de reloj amarillo, que indica que está ausente](media/Presence_Away.png) <span data-ttu-id="366a3-131">Desaparece</span><span class="sxs-lookup"><span data-stu-id="366a3-131">Away</span></span>| ![Icono de reloj amarillo, que indica que está ausente](media/Presence_Away.png) <span data-ttu-id="366a3-133">Desaparece</span><span class="sxs-lookup"><span data-stu-id="366a3-133">Away</span></span>|
|| <span data-ttu-id="366a3-134">![Icono de reloj amarillo, que](media/Presence_Away.png) indica que se está alejando la *hora* de última vista</span><span class="sxs-lookup"><span data-stu-id="366a3-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icono de reloj amarillo, que indica que está ausente, volver al final](media/Presence_Away.png) <span data-ttu-id="366a3-136">Enseguida regreso</span><span class="sxs-lookup"><span data-stu-id="366a3-136">Be right back</span></span>| |
|| ![Icono de reloj amarillo, que indica que está ausente, trabajo](media/Presence_Away.png)  <span data-ttu-id="366a3-138">Descuento en el trabajo</span><span class="sxs-lookup"><span data-stu-id="366a3-138">Off Work</span></span>|
|| ![Círculo gris con x, que indica que no tiene conexión](media/Presence_Offline.png) <span data-ttu-id="366a3-140">Línea</span><span class="sxs-lookup"><span data-stu-id="366a3-140">Offline</span></span> |
|| ![Abrir un círculo gris, que indica el estado desconocido](media/Presence_Unknown.png) <span data-ttu-id="366a3-142">Estado desconocido</span><span class="sxs-lookup"><span data-stu-id="366a3-142">Status unknown</span></span>|
||![Círculo rojo abierto con línea diagonal, que indica que está bloqueado](media/Presence_Blocked.png) <span data-ttu-id="366a3-144">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="366a3-144">Blocked</span></span> |
|| ![Círculo púrpura con flecha, que indica fuera de la oficina](media/Presence_OOF.png) <span data-ttu-id="366a3-146">Fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="366a3-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="366a3-147">Los usuarios pueden establecer manualmente el estado de presencia actual en algunas opciones, y su estado se reflejará a todos los demás usuarios.</span><span class="sxs-lookup"><span data-stu-id="366a3-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="366a3-148">Los detalles de presencia de usuario adicionales también se actualizan automáticamente en función de la actividad del usuario (como disponible o ausente), los Estados del calendario de Outlook (como en una reunión) o los Estados de la aplicación de Teams (en una llamada, presentar), para los Estados que tienen sangría en la lista.</span><span class="sxs-lookup"><span data-stu-id="366a3-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="366a3-149">Hay un tiempo de espera de 15 minutos de inactividad, después del cual el estado de presencia actual de los usuarios se restablecerá a ausente.</span><span class="sxs-lookup"><span data-stu-id="366a3-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="366a3-150">Los usuarios pueden especificar quién puede interrumpir (póngase en contacto con ellos invalidando la configuración de no molestar).</span><span class="sxs-lookup"><span data-stu-id="366a3-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="366a3-151">Esta configuración está disponible en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="366a3-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="366a3-152">Teams no es Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="366a3-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="366a3-153">La siguiente configuración de administrador en Skype empresarial es diferente en Teams:</span><span class="sxs-lookup"><span data-stu-id="366a3-153">The following admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="366a3-154">El uso compartido de presencia siempre está habilitado en Teams para los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="366a3-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="366a3-155">La configuración de privacidad (decidir quién puede ver la presencia) no está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="366a3-155">Privacy (deciding who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="366a3-156">El uso compartido de presencia con todos los usuarios (incluidos los servicios federados) siempre está habilitado para los usuarios en Teams.</span><span class="sxs-lookup"><span data-stu-id="366a3-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="366a3-157">Su lista de contactos (si tenía una en Skype empresarial) está visible en **conversación > contactos** o en **llamadas > contactos**.</span><span class="sxs-lookup"><span data-stu-id="366a3-157">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="366a3-158">Las características de cliente no molestar y de avance siempre están habilitadas para los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="366a3-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="366a3-159">La integración de calendario (incluye fuera de oficina y otra información de calendario) siempre está habilitada para los usuarios de Teams si están integrados con Outlook.</span><span class="sxs-lookup"><span data-stu-id="366a3-159">Calendar (includes out of office and other calendar information) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="366a3-160">La *última fecha* de presentación o de *ausencia* (si en un entorno dual con Skype empresarial) está siempre habilitada para los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="366a3-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="366a3-161">La capacidad de un administrador de equipos para personalizar esta configuración no es compatible actualmente.</span><span class="sxs-lookup"><span data-stu-id="366a3-161">The ability of a Teams admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="366a3-162">Coexistencia con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="366a3-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="366a3-163">Vea [coexistencia con Skype empresarial](coexistence-chat-calls-presence.md) para obtener más información sobre cómo funciona la presencia de equipos cuando coexisten con Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="366a3-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
