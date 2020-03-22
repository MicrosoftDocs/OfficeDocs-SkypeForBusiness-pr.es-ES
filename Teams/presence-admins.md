---
title: Presencia del usuario en Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Información para los Administradores sobre la Presencia en Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863201"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="6a8a1-103">Presencia del usuario en Teams</span><span class="sxs-lookup"><span data-stu-id="6a8a1-103">User presence in Teams</span></span>

<span data-ttu-id="6a8a1-104">La presencia es parte del perfil de un usuario en Microsoft Teams (y en todo Office 365) que indica a los demás usuarios la disponibilidad y el estado actual del usuario.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="6a8a1-105">De forma predeterminada, cualquier persona de su organización que utilice Teams puede ver (casi en tiempo real) si otros usuarios están disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a8a1-106">Si desinstala el cliente de Skype Empresarial después de mover un usuario al modo **Teams solo**, la presencia dejará de funcionar en Outlook y en otras aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="6a8a1-107">La presencia funciona bien en Teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-107">Presence works fine in Teams.</span></span> <span data-ttu-id="6a8a1-108">Solución: Para ver la presencia en Outlook (y otras aplicaciones de Office), Skype Empresarial debe estar instalado, aunque esté ejecutando Teams en el modo **solo Teams**.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="6a8a1-109">Microsoft es consciente de este problema y está trabajando en una solución.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="6a8a1-110">La presencia de Teams en Outlook es compatible con la aplicación de escritorio Outlook 2013 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="6a8a1-111">Estados de presencia en Teams</span><span class="sxs-lookup"><span data-stu-id="6a8a1-111">Presence states in Teams</span></span>

<span data-ttu-id="6a8a1-112">Los estados de presencia del usuario disponibles en Teams son:</span><span class="sxs-lookup"><span data-stu-id="6a8a1-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="6a8a1-113">Configurado por el usuario</span><span class="sxs-lookup"><span data-stu-id="6a8a1-113">User configured</span></span>|<span data-ttu-id="6a8a1-114">Aplicación configurada</span><span class="sxs-lookup"><span data-stu-id="6a8a1-114">App configured</span></span>|
|:--- |:---|
| ![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) <span data-ttu-id="6a8a1-116">Disponible</span><span class="sxs-lookup"><span data-stu-id="6a8a1-116">Available</span></span>|![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) <span data-ttu-id="6a8a1-118">Disponible</span><span class="sxs-lookup"><span data-stu-id="6a8a1-118">Available</span></span>|
|| ![Marca de verificación verde sólida, indica Presencia Abierta marca de verificación verde, indica disponible oof](media/Presence_Available_OOF.png) <span data-ttu-id="6a8a1-120">Disponibles, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="6a8a1-120">Available, Out of Office</span></span> |
|  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="6a8a1-122">Ocupado</span><span class="sxs-lookup"><span data-stu-id="6a8a1-122">Busy</span></span> |  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="6a8a1-124">Ocupado</span><span class="sxs-lookup"><span data-stu-id="6a8a1-124">Busy</span></span>  |
|| ![Círculo rojo sólido, indica Ocupado en una llamada](media/Presence_Busy.png) <span data-ttu-id="6a8a1-126">En una llamada...</span><span class="sxs-lookup"><span data-stu-id="6a8a1-126">On a call</span></span>|
|| ![Círculo rojo sólido, indica Ocupado en una reunión](media/Presence_Busy.png) <span data-ttu-id="6a8a1-128">En una reunión</span><span class="sxs-lookup"><span data-stu-id="6a8a1-128">In a meeting</span></span> |
|| ![Círculo rojo abierto, indica Ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="6a8a1-130">En una llamada, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="6a8a1-130">On a call, out of office</span></span>|
|  ![Círculo rojo con línea blanca, indica No molestar](media/Presence_DND.png) <span data-ttu-id="6a8a1-132">No molestar</span><span class="sxs-lookup"><span data-stu-id="6a8a1-132">Do not disturb</span></span> ||
|| ![Círculo rojo con línea blanca, indica Presentando](media/Presence_DND.png) <span data-ttu-id="6a8a1-134">Presentando</span><span class="sxs-lookup"><span data-stu-id="6a8a1-134">Presenting</span></span>|
|| ![Círculo rojo con línea blanca, indica Modo enfoque](media/Presence_DND.png) <span data-ttu-id="6a8a1-136">Modo enfoque</span><span class="sxs-lookup"><span data-stu-id="6a8a1-136">Focusing</span></span>|
| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) <span data-ttu-id="6a8a1-138">Ausente</span><span class="sxs-lookup"><span data-stu-id="6a8a1-138">Away</span></span>| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) <span data-ttu-id="6a8a1-140">Ausente</span><span class="sxs-lookup"><span data-stu-id="6a8a1-140">Away</span></span>|
|| <span data-ttu-id="6a8a1-141">![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Última vez visto ausente*hora*</span><span class="sxs-lookup"><span data-stu-id="6a8a1-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icono del reloj amarillo, indica que está ausente, ahora vuelvo.](media/Presence_Away.png) <span data-ttu-id="6a8a1-143">Ahora vuelvo</span><span class="sxs-lookup"><span data-stu-id="6a8a1-143">Be right back</span></span>| |
|| ![Icono de reloj amarillo, indica que está ausente, fuera del trabajo](media/Presence_Away.png)  <span data-ttu-id="6a8a1-145">Fuera del trabajo</span><span class="sxs-lookup"><span data-stu-id="6a8a1-145">Off Work</span></span>|
|| ![Círculo gris con una x, indica que está Desconectado](media/Presence_Offline.png) <span data-ttu-id="6a8a1-147">Offline</span><span class="sxs-lookup"><span data-stu-id="6a8a1-147">Offline</span></span> |
|| ![Círculo gris abierto, indica estado desconocido](media/Presence_Unknown.png) <span data-ttu-id="6a8a1-149">Estado desconocido</span><span class="sxs-lookup"><span data-stu-id="6a8a1-149">Status unknown</span></span>|
||![Círculo rojo abierto con línea diagonal, indica que está bloqueado](media/Presence_Blocked.png) <span data-ttu-id="6a8a1-151">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="6a8a1-151">Blocked</span></span> |
|| ![Círculo púrpura con flecha, indica Fuera de la oficina](media/Presence_OOF.png) <span data-ttu-id="6a8a1-153">Fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="6a8a1-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="6a8a1-154">Los usuarios pueden ajustar manualmente su estado de presencia actual a algunas opciones, y su estado se refleja a todos los demás usuarios.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="6a8a1-155">También se actualizan automáticamente más detalles de la presencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="6a8a1-156">Los cambios se basan en la actividad del usuario (Disponible, Ausente), los estados del calendario de Outlook (En una reunión), o los estados de las aplicaciones de Teams (En una llamada, Presentando), a los estados que están sangrados en la lista.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="6a8a1-157">Hay un tiempo límite de inactividad de 15 minutos, después del cual el estado de presencia actual se reajusta a Ausente.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="6a8a1-158">Los usuarios reciben todos los mensajes de chat que se les envían en los equipos, independientemente de su estado de presencia.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="6a8a1-159">Si un usuario está desconectado cuando alguien le envía un mensaje, el mensaje de chat aparece en Teams la próxima vez que el usuario se conecta.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="6a8a1-160">Si un usuario se encuentra en un estado de "No molestar", el usuario seguirá recibiendo mensajes de chat pero no se mostrará una notificación emergente.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="6a8a1-161">Los usuarios reciben llamadas en todos los estados de presencia excepto en los estados de "No molestar", en los que las llamadas entrantes son entregadas a su buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="6a8a1-162">Si el destinatario bloqueó la llamada, la llamada no será entregada y la persona que llama ve la presencia del destinatario como desconectada.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="6a8a1-163">Los usuarios pueden agregar a personas a su lista de acceso prioritario yendo a **Configuración** > **Privacidad** en Teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="6a8a1-164">Las personas que tienen acceso prioritario pueden ponerse en contacto con el usuario incluso cuando éste se encuentra en un estado de "No molestar".</span><span class="sxs-lookup"><span data-stu-id="6a8a1-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="6a8a1-165">Configuración de administración en equipos en comparación con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="6a8a1-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="6a8a1-166">La siguiente configuración de administración Skype Empresarial es diferente en Teams:</span><span class="sxs-lookup"><span data-stu-id="6a8a1-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="6a8a1-167">En Teams, el uso compartido de la presencia siempre está habilitado para los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="6a8a1-168">La configuración de privacidad (donde se define quién puede ver la presencia) no está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="6a8a1-169">Compartir la presencia con todo el mundo (incluidos los servicios Federados) siempre está habilitado para los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="6a8a1-170">Su lista de contactos (si tenía una en Skype Empresarial) está visible en**Chat > Contactos** o en **Llamadas > Contactos**.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="6a8a1-171">Las funciones de No molestar al cliente y Contacto siempre están habilitadas para los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="6a8a1-172">La integración del calendario (incluye información de fuera de la oficina y otra información de calendario) siempre está habilitada para los usuarios cuando Teams se integra con Outlook.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="6a8a1-173">El indicador *Último visto* o *Ausente desde* siempre está habilitado para los usuarios en Teams si la organización también usa Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="6a8a1-174">Actualmente no se admite la capacidad de un administrador de Teams para personalizar estos ajustes.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="6a8a1-175">Coexistencia con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="6a8a1-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="6a8a1-176">Consulte[ Coexistencia con Skype Empresarial ](coexistence-chat-calls-presence.md)para obtener más información sobre cómo funciona la presencia en Teams cuando tu organización también usa Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
