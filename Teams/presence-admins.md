---
title: Presencia del usuario en Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Obtenga información sobre los Estados de presencia en Teams, así como la configuración administrativa de la característica de presencia.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f14aeaf83862cbdd695eb6ec4646d8da81a0c5b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369215"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="54337-103">Presencia del usuario en Teams</span><span class="sxs-lookup"><span data-stu-id="54337-103">User presence in Teams</span></span>

<span data-ttu-id="54337-104">La presencia es parte del perfil de un usuario en Microsoft Teams (y en Microsoft 365 u Office 365) que indica la disponibilidad y el estado actuales del usuario a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="54337-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="54337-105">De forma predeterminada, cualquier persona de su organización que utilice Teams puede ver (casi en tiempo real) si otros usuarios están disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="54337-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="54337-106">La presencia de Teams en Outlook es compatible con la aplicación de escritorio Outlook 2013 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="54337-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="54337-107">Para obtener más información sobre los perfiles de usuario de Teams en diferentes plataformas, consulte [características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="54337-107">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="54337-108">Estados de presencia en Teams</span><span class="sxs-lookup"><span data-stu-id="54337-108">Presence states in Teams</span></span>

|<span data-ttu-id="54337-109">Configurado por el usuario</span><span class="sxs-lookup"><span data-stu-id="54337-109">User configured</span></span>|<span data-ttu-id="54337-110">Aplicación configurada</span><span class="sxs-lookup"><span data-stu-id="54337-110">App configured</span></span>|
|:--- |:---|
| ![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) <span data-ttu-id="54337-112">Disponible</span><span class="sxs-lookup"><span data-stu-id="54337-112">Available</span></span>|![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) <span data-ttu-id="54337-114">Disponible</span><span class="sxs-lookup"><span data-stu-id="54337-114">Available</span></span>|
|| ![Marca de verificación verde sólida, indica Presencia Abierta marca de verificación verde, indica disponible oof](media/Presence_Available_OOF.png) <span data-ttu-id="54337-116">Disponibles, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="54337-116">Available, Out of Office</span></span> |
|  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="54337-118">Ocupado</span><span class="sxs-lookup"><span data-stu-id="54337-118">Busy</span></span> |  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="54337-120">Ocupado</span><span class="sxs-lookup"><span data-stu-id="54337-120">Busy</span></span>  |
|| ![Círculo rojo sólido, indica Ocupado en una llamada](media/Presence_Busy.png) <span data-ttu-id="54337-122">En una llamada...</span><span class="sxs-lookup"><span data-stu-id="54337-122">On a call</span></span>|
|| ![Círculo rojo sólido, indica Ocupado en una reunión](media/Presence_Busy.png) <span data-ttu-id="54337-124">En una reunión</span><span class="sxs-lookup"><span data-stu-id="54337-124">In a meeting</span></span> |
|| ![Círculo rojo abierto, indica Ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="54337-126">En una llamada, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="54337-126">On a call, out of office</span></span>|
|  ![Círculo rojo con línea blanca, indica No molestar](media/Presence_DND.png) <span data-ttu-id="54337-128">No molestar</span><span class="sxs-lookup"><span data-stu-id="54337-128">Do not disturb</span></span> ||
|| ![Círculo rojo con línea blanca, indica Presentando](media/Presence_DND.png) <span data-ttu-id="54337-130">Presentando</span><span class="sxs-lookup"><span data-stu-id="54337-130">Presenting</span></span>|
|| ![Círculo rojo con línea blanca, indica Modo enfoque](media/Presence_DND.png) <span data-ttu-id="54337-132">Modo enfoque</span><span class="sxs-lookup"><span data-stu-id="54337-132">Focusing</span></span>|
| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) <span data-ttu-id="54337-134">Ausente</span><span class="sxs-lookup"><span data-stu-id="54337-134">Away</span></span>| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) <span data-ttu-id="54337-136">Ausente</span><span class="sxs-lookup"><span data-stu-id="54337-136">Away</span></span>|
|| <span data-ttu-id="54337-137">![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Última vez visto ausente*hora*</span><span class="sxs-lookup"><span data-stu-id="54337-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icono del reloj amarillo, indica que está ausente, ahora vuelvo.](media/Presence_Away.png) <span data-ttu-id="54337-139">Ahora vuelvo</span><span class="sxs-lookup"><span data-stu-id="54337-139">Be right back</span></span>| |
|![Círculo gris con una x, indica que está Desconectado](media/Presence_Offline.png) <span data-ttu-id="54337-141">Aparecer como desconectado</span><span class="sxs-lookup"><span data-stu-id="54337-141">Appear offline</span></span> | ![Círculo gris con una x, indica que está Desconectado](media/Presence_Offline.png) <span data-ttu-id="54337-143">Offline</span><span class="sxs-lookup"><span data-stu-id="54337-143">Offline</span></span>| |
|| ![Círculo gris abierto, indica estado desconocido](media/Presence_Unknown.png) <span data-ttu-id="54337-145">Estado desconocido</span><span class="sxs-lookup"><span data-stu-id="54337-145">Status unknown</span></span>|
|| ![Círculo púrpura con flecha, indica Fuera de la oficina](media/Presence_OOF.png) <span data-ttu-id="54337-147">Fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="54337-147">Out of Office</span></span>|
|||

<span data-ttu-id="54337-148">Los Estados de presencia configurados por la aplicación se basan en la actividad del usuario (disponible, ausente), Estados del calendario de Outlook (en una reunión) o Estados de la aplicación de Teams (en una llamada, presentando).</span><span class="sxs-lookup"><span data-stu-id="54337-148">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="54337-149">Tenga en cuenta que cuando se encuentra en el modo de enfoque basado en el calendario, el foco será el estado que verán los usuarios en Teams, pero se mostrarán como no molestar en otros productos.</span><span class="sxs-lookup"><span data-stu-id="54337-149">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams, but it will display as Do not disturb in other products.</span></span>

<span data-ttu-id="54337-150">El estado actual de presencia cambiará a ausente cuando bloquee el equipo o cuando el equipo entre en modo de inactividad o de suspensión.</span><span class="sxs-lookup"><span data-stu-id="54337-150">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="54337-151">En un dispositivo móvil, el estado de presencia cambiará a ausente cuando la aplicación de Teams esté en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="54337-151">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="54337-152">Los usuarios reciben todos los mensajes de chat que se les envían en los equipos, independientemente de su estado de presencia.</span><span class="sxs-lookup"><span data-stu-id="54337-152">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="54337-153">Si un usuario está desconectado cuando alguien le envía un mensaje, el mensaje de chat aparece en Teams la próxima vez que el usuario se conecta.</span><span class="sxs-lookup"><span data-stu-id="54337-153">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="54337-154">Si el estado de un usuario se establece en no molestar, el usuario seguirá recibiendo mensajes de chat, pero no se mostrarán las notificaciones de banner.</span><span class="sxs-lookup"><span data-stu-id="54337-154">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="54337-155">Los usuarios reciben llamadas en todos los Estados de presencia excepto en no molestar, en el que las llamadas entrantes se dirigen al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="54337-155">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="54337-156">Si el destinatario bloqueó la llamada, la llamada no será entregada y la persona que llama ve la presencia del destinatario como desconectada.</span><span class="sxs-lookup"><span data-stu-id="54337-156">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="54337-157">Los usuarios pueden agregar a personas a su lista de acceso prioritario yendo a **Configuración** > **Privacidad** en Teams.</span><span class="sxs-lookup"><span data-stu-id="54337-157">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="54337-158">Los usuarios con prioridad pueden ponerse en contacto con el usuario aunque el estado del usuario esté establecido en no molestar.</span><span class="sxs-lookup"><span data-stu-id="54337-158">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="54337-159">Expiración de Estados configurados por el usuario</span><span class="sxs-lookup"><span data-stu-id="54337-159">User configured states expiration</span></span>
<span data-ttu-id="54337-160">Cuando un usuario selecciona un estado de presencia específico, tiene prioridad sobre cualquier actualización de actividad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="54337-160">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="54337-161">Por ejemplo, si un usuario se establece como no molestar, su presencia permanecerá como no molestar aunque asista a una reunión o responda a una llamada.</span><span class="sxs-lookup"><span data-stu-id="54337-161">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="54337-162">Los Estados configurados por el usuario tienen una configuración de expiración predeterminada en Teams, para evitar que los usuarios muestren un estado que puede no ser relevante después de un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="54337-162">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="54337-163">Estado configurado por el usuario</span><span class="sxs-lookup"><span data-stu-id="54337-163">User configured state</span></span>|<span data-ttu-id="54337-164">Caducidad predeterminada</span><span class="sxs-lookup"><span data-stu-id="54337-164">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="54337-165">Ocupado</span><span class="sxs-lookup"><span data-stu-id="54337-165">Busy</span></span>|<span data-ttu-id="54337-166">1 día</span><span class="sxs-lookup"><span data-stu-id="54337-166">1 day</span></span>|
| <span data-ttu-id="54337-167">No molestar</span><span class="sxs-lookup"><span data-stu-id="54337-167">Do not disturb</span></span>|<span data-ttu-id="54337-168">1 día</span><span class="sxs-lookup"><span data-stu-id="54337-168">1 day</span></span>|
| <span data-ttu-id="54337-169">Ven</span><span class="sxs-lookup"><span data-stu-id="54337-169">Others</span></span>|<span data-ttu-id="54337-170">7 días</span><span class="sxs-lookup"><span data-stu-id="54337-170">7 days</span></span>|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="54337-171">Configuración de administración en equipos en comparación con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="54337-171">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="54337-172">La siguiente configuración de administración Skype Empresarial es diferente en Teams:</span><span class="sxs-lookup"><span data-stu-id="54337-172">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="54337-173">En Teams, el uso compartido de la presencia siempre está habilitado para los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="54337-173">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="54337-174">La configuración de privacidad (donde se define quién puede ver la presencia) no está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="54337-174">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="54337-175">Compartir la presencia con todo el mundo (incluidos los servicios Federados) siempre está habilitado para los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="54337-175">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="54337-176">Su lista de contactos (si tenía una en Skype Empresarial) está visible en**Chat > Contactos** o en **Llamadas > Contactos**.</span><span class="sxs-lookup"><span data-stu-id="54337-176">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="54337-177">Las funciones de No molestar al cliente y Contacto siempre están habilitadas para los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="54337-177">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="54337-178">La integración del calendario (incluye información de fuera de la oficina y otra información de calendario) siempre está habilitada para los usuarios cuando Teams se integra con Outlook.</span><span class="sxs-lookup"><span data-stu-id="54337-178">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="54337-179">El indicador *Último visto* o *Ausente desde* siempre está habilitado para los usuarios en Teams si la organización también usa Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="54337-179">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="54337-180">Actualmente no se admite la capacidad de un administrador de Teams para personalizar estos ajustes.</span><span class="sxs-lookup"><span data-stu-id="54337-180">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="54337-181">Coexistencia con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="54337-181">Coexistence with Skype for Business</span></span>

<span data-ttu-id="54337-182">Consulte[ Coexistencia con Skype Empresarial ](coexistence-chat-calls-presence.md)para obtener más información sobre cómo funciona la presencia en Teams cuando tu organización también usa Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="54337-182">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
