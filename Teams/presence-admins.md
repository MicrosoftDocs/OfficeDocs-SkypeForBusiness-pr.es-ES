---
title: La presencia del usuario en Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Información para administradores sobre la presencia en Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 054c3a639cc5857fb25a7e211a272868477dcb61
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573222"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="2224d-103">La presencia del usuario en Teams</span><span class="sxs-lookup"><span data-stu-id="2224d-103">User presence in Teams</span></span>

<span data-ttu-id="2224d-104">La presencia es parte de un perfil de usuario de Microsoft Teams (y de toda la 365 de Office) que indica la disponibilidad y el estado actuales del usuario a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="2224d-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="2224d-105">De forma predeterminada, cualquier persona de la organización que use Teams puede ver (en casi tiempo real) si hay otros usuarios disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="2224d-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2224d-106">Si desinstala el cliente de Skype Empresarial después de mover un usuario al modo **Teams solo**, la presencia dejará de funcionar en Outlook y en otras aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="2224d-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="2224d-107">La presencia funciona bien en Teams.</span><span class="sxs-lookup"><span data-stu-id="2224d-107">Presence works fine in Teams.</span></span> <span data-ttu-id="2224d-108">Solución: para ver la presencia en Outlook (y en otras aplicaciones de Office), debe estar instalado Skype empresarial, incluso si está ejecutando Teams en modo de **solo Teams** .</span><span class="sxs-lookup"><span data-stu-id="2224d-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="2224d-109">Microsoft es consciente de este problema y está buscando una solución. </span><span class="sxs-lookup"><span data-stu-id="2224d-109">Microsoft is aware of this problem and is working on a fix.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="2224d-110">Estados de presencia en Teams</span><span class="sxs-lookup"><span data-stu-id="2224d-110">Presence states in Teams</span></span>

<span data-ttu-id="2224d-111">Los Estados de presencia de usuario disponibles en Teams son:</span><span class="sxs-lookup"><span data-stu-id="2224d-111">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="2224d-112">Usuario configurado</span><span class="sxs-lookup"><span data-stu-id="2224d-112">User configured</span></span>|<span data-ttu-id="2224d-113">Aplicación configurada</span><span class="sxs-lookup"><span data-stu-id="2224d-113">App configured</span></span>|
|:--- |:---|
| ![Marca de verificación verde sólido, indica la presencia disponible](media/Presence_Available.png) <span data-ttu-id="2224d-115">Disponible</span><span class="sxs-lookup"><span data-stu-id="2224d-115">Available</span></span>|![Marca de verificación verde sólido, indica la presencia disponible](media/Presence_Available.png) <span data-ttu-id="2224d-117">Disponible</span><span class="sxs-lookup"><span data-stu-id="2224d-117">Available</span></span>|
|| ![Abrir la marca de verificación verde, indica el OOF disponible](media/Presence_Available_OOF.png) <span data-ttu-id="2224d-119">Disponible, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="2224d-119">Available, Out of Office</span></span> |
|  ![Círculo rojo sólido, indica ocupado](media/Presence_Busy.png) <span data-ttu-id="2224d-121">Ocupado</span><span class="sxs-lookup"><span data-stu-id="2224d-121">Busy</span></span> |  ![Círculo rojo sólido, indica ocupado](media/Presence_Busy.png) <span data-ttu-id="2224d-123">Ocupado</span><span class="sxs-lookup"><span data-stu-id="2224d-123">Busy</span></span>  |
|| ![Círculo rojo sólido, indica ocupado en una llamada](media/Presence_Busy.png) <span data-ttu-id="2224d-125">En una llamada</span><span class="sxs-lookup"><span data-stu-id="2224d-125">In a call</span></span>|
|| ![Círculo rojo sólido, indica ocupado en una reunión](media/Presence_Busy.png) <span data-ttu-id="2224d-127">En una reunión</span><span class="sxs-lookup"><span data-stu-id="2224d-127">In a meeting</span></span> |
|| ![Abrir un círculo rojo, indica ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="2224d-129">En una llamada, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="2224d-129">In a call, out of office</span></span>|
|  ![Círculo rojo con línea blanca, indica que no molestar](media/Presence_DND.png) <span data-ttu-id="2224d-131">No molestar</span><span class="sxs-lookup"><span data-stu-id="2224d-131">Do not disturb</span></span> ||
|| ![Un círculo rojo con línea blanca indica la presentación](media/Presence_DND.png) <span data-ttu-id="2224d-133">Moderado</span><span class="sxs-lookup"><span data-stu-id="2224d-133">Presenting</span></span>|
|| ![Un círculo rojo con línea blanca indica el foco](media/Presence_DND.png) <span data-ttu-id="2224d-135">Énfasis</span><span class="sxs-lookup"><span data-stu-id="2224d-135">Focusing</span></span>|
| ![Icono de reloj amarillo, indica ausente](media/Presence_Away.png) <span data-ttu-id="2224d-137">Desaparece</span><span class="sxs-lookup"><span data-stu-id="2224d-137">Away</span></span>| ![Icono de reloj amarillo, indica ausente](media/Presence_Away.png) <span data-ttu-id="2224d-139">Desaparece</span><span class="sxs-lookup"><span data-stu-id="2224d-139">Away</span></span>|
|| <span data-ttu-id="2224d-140">![Icono de reloj amarillo, que](media/Presence_Away.png) indica que está fuera de la última *hora* de vista</span><span class="sxs-lookup"><span data-stu-id="2224d-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icono amarillo de reloj, indica que está ausente, volver a la derecha](media/Presence_Away.png) <span data-ttu-id="2224d-142">Enseguida regreso</span><span class="sxs-lookup"><span data-stu-id="2224d-142">Be right back</span></span>| |
|| ![Icono de reloj amarillo, indica que no hay trabajo](media/Presence_Away.png)  <span data-ttu-id="2224d-144">Descuento en el trabajo</span><span class="sxs-lookup"><span data-stu-id="2224d-144">Off Work</span></span>|
|| ![Círculo gris con x, indica sin conexión](media/Presence_Offline.png) <span data-ttu-id="2224d-146">Línea</span><span class="sxs-lookup"><span data-stu-id="2224d-146">Offline</span></span> |
|| ![Abrir un círculo gris, indica el estado desconocido](media/Presence_Unknown.png) <span data-ttu-id="2224d-148">Estado desconocido</span><span class="sxs-lookup"><span data-stu-id="2224d-148">Status unknown</span></span>|
||![Círculo rojo abierto con línea diagonal, indica bloqueado](media/Presence_Blocked.png) <span data-ttu-id="2224d-150">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="2224d-150">Blocked</span></span> |
|| ![Círculo púrpura con flecha, indica fuera de la oficina](media/Presence_OOF.png) <span data-ttu-id="2224d-152">Fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="2224d-152">Out of Office</span></span>|
|||
 
<span data-ttu-id="2224d-153">Los usuarios pueden establecer manualmente el estado de presencia actual en algunas opciones, y su estado se reflejará a todos los demás usuarios.</span><span class="sxs-lookup"><span data-stu-id="2224d-153">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="2224d-154">También se actualizan automáticamente más detalles de presencia de usuario.</span><span class="sxs-lookup"><span data-stu-id="2224d-154">More user presence details are also automatically updated.</span></span> <span data-ttu-id="2224d-155">Los cambios se basan en la actividad del usuario (disponible, ausente), Estados del calendario de Outlook (en una reunión) o Estados de la aplicación de Teams (en una llamada, presentando), para Estados que tienen sangría en la lista.</span><span class="sxs-lookup"><span data-stu-id="2224d-155">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="2224d-156">Hay un tiempo de espera de 15 minutos de inactividad, después de que el estado de presencia actual se restablezca a ausente.</span><span class="sxs-lookup"><span data-stu-id="2224d-156">There is a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="2224d-157">Los usuarios pueden especificar quién puede romperse (es decir, póngase en contacto con él a pesar de un estado no molestar).</span><span class="sxs-lookup"><span data-stu-id="2224d-157">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="2224d-158">Esta configuración está disponible en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="2224d-158">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="2224d-159">Configuración de administración de equipos comparada con Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="2224d-159">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="2224d-160">La siguiente configuración de administración de Skype empresarial es diferente en Teams:</span><span class="sxs-lookup"><span data-stu-id="2224d-160">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="2224d-161">En Teams, el uso compartido de presencia siempre está habilitado para los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="2224d-161">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="2224d-162">La configuración de privacidad (donde se define quién puede ver la presencia) no está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="2224d-162">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="2224d-163">El uso compartido de presencia con todos los usuarios (incluidos los servicios federados) siempre está habilitado para los usuarios en Teams.</span><span class="sxs-lookup"><span data-stu-id="2224d-163">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="2224d-164">Su lista de contactos (si tenía una en Skype empresarial) está visible en **conversación > contactos** o en **llamadas > contactos**.</span><span class="sxs-lookup"><span data-stu-id="2224d-164">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="2224d-165">Las características de cliente no molestar y de avance siempre están habilitadas para los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="2224d-165">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="2224d-166">La integración de calendario (incluye fuera de oficina y otra información de calendario) siempre está habilitada para los usuarios cuando se integran Teams con Outlook.</span><span class="sxs-lookup"><span data-stu-id="2224d-166">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="2224d-167">El *último* indicador, visto o *ausente, ya* está habilitado para los usuarios de Teams si la organización también usa Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="2224d-167">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="2224d-168">La capacidad de un administrador de equipos para personalizar esta configuración no es compatible actualmente.</span><span class="sxs-lookup"><span data-stu-id="2224d-168">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="2224d-169">Coexistencia con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="2224d-169">Coexistence with Skype for Business</span></span>

<span data-ttu-id="2224d-170">Vea [coexistencia con Skype empresarial](coexistence-chat-calls-presence.md) para obtener información sobre cómo funciona la presencia de Teams cuando su organización también usa Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="2224d-170">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
