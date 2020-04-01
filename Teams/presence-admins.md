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
ms.openlocfilehash: ea756b24a0292a35d4e47252383bfc954fcb8fa7
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096975"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="b4fb8-103">Presencia del usuario en Teams</span><span class="sxs-lookup"><span data-stu-id="b4fb8-103">User presence in Teams</span></span>

<span data-ttu-id="b4fb8-104">La presencia es parte de un perfil de usuario de Microsoft Teams (y de toda la 365 de Office) que indica la disponibilidad y el estado actuales del usuario a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-104">Presence is part of a user's profile in Microsoft Teams (and throughout Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="b4fb8-105">De forma predeterminada, cualquier persona de su organización que utilice Teams puede ver (casi en tiempo real) si otros usuarios están disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4fb8-106">Si desinstala el cliente de Skype Empresarial después de mover un usuario al modo **Teams solo**, la presencia dejará de funcionar en Outlook y en otras aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="b4fb8-107">La presencia funciona bien en Teams.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-107">Presence works fine in Teams.</span></span> <span data-ttu-id="b4fb8-108">Solución: Para ver la presencia en Outlook (y otras aplicaciones de Office), Skype Empresarial debe estar instalado, aunque esté ejecutando Teams en el modo **solo Teams**.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="b4fb8-109">Microsoft es consciente de este problema y está trabajando en una solución.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="b4fb8-110">La presencia de Teams en Outlook es compatible con la aplicación de escritorio Outlook 2013 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="b4fb8-111">Estados de presencia en Teams</span><span class="sxs-lookup"><span data-stu-id="b4fb8-111">Presence states in Teams</span></span>

|<span data-ttu-id="b4fb8-112">Configurado por el usuario</span><span class="sxs-lookup"><span data-stu-id="b4fb8-112">User configured</span></span>|<span data-ttu-id="b4fb8-113">Aplicación configurada</span><span class="sxs-lookup"><span data-stu-id="b4fb8-113">App configured</span></span>|
|:--- |:---|
| ![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) <span data-ttu-id="b4fb8-115">Disponible</span><span class="sxs-lookup"><span data-stu-id="b4fb8-115">Available</span></span>|![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) <span data-ttu-id="b4fb8-117">Disponible</span><span class="sxs-lookup"><span data-stu-id="b4fb8-117">Available</span></span>|
|| ![Marca de verificación verde sólida, indica Presencia Abierta marca de verificación verde, indica disponible oof](media/Presence_Available_OOF.png) <span data-ttu-id="b4fb8-119">Disponibles, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="b4fb8-119">Available, Out of Office</span></span> |
|  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="b4fb8-121">Ocupado</span><span class="sxs-lookup"><span data-stu-id="b4fb8-121">Busy</span></span> |  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="b4fb8-123">Ocupado</span><span class="sxs-lookup"><span data-stu-id="b4fb8-123">Busy</span></span>  |
|| ![Círculo rojo sólido, indica Ocupado en una llamada](media/Presence_Busy.png) <span data-ttu-id="b4fb8-125">En una llamada...</span><span class="sxs-lookup"><span data-stu-id="b4fb8-125">On a call</span></span>|
|| ![Círculo rojo sólido, indica Ocupado en una reunión](media/Presence_Busy.png) <span data-ttu-id="b4fb8-127">En una reunión</span><span class="sxs-lookup"><span data-stu-id="b4fb8-127">In a meeting</span></span> |
|| ![Círculo rojo abierto, indica Ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="b4fb8-129">En una llamada, fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="b4fb8-129">On a call, out of office</span></span>|
|  ![Círculo rojo con línea blanca, indica No molestar](media/Presence_DND.png) <span data-ttu-id="b4fb8-131">No molestar</span><span class="sxs-lookup"><span data-stu-id="b4fb8-131">Do not disturb</span></span> ||
|| ![Círculo rojo con línea blanca, indica Presentando](media/Presence_DND.png) <span data-ttu-id="b4fb8-133">Presentando</span><span class="sxs-lookup"><span data-stu-id="b4fb8-133">Presenting</span></span>|
|| ![Círculo rojo con línea blanca, indica Modo enfoque](media/Presence_DND.png) <span data-ttu-id="b4fb8-135">Modo enfoque</span><span class="sxs-lookup"><span data-stu-id="b4fb8-135">Focusing</span></span>|
| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) <span data-ttu-id="b4fb8-137">Ausente</span><span class="sxs-lookup"><span data-stu-id="b4fb8-137">Away</span></span>| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) <span data-ttu-id="b4fb8-139">Ausente</span><span class="sxs-lookup"><span data-stu-id="b4fb8-139">Away</span></span>|
|| <span data-ttu-id="b4fb8-140">![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Última vez visto ausente*hora*</span><span class="sxs-lookup"><span data-stu-id="b4fb8-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icono del reloj amarillo, indica que está ausente, ahora vuelvo.](media/Presence_Away.png) <span data-ttu-id="b4fb8-142">Ahora vuelvo</span><span class="sxs-lookup"><span data-stu-id="b4fb8-142">Be right back</span></span>| |
|| ![Icono de reloj amarillo, indica que está ausente, fuera del trabajo](media/Presence_Away.png)  <span data-ttu-id="b4fb8-144">Fuera del trabajo</span><span class="sxs-lookup"><span data-stu-id="b4fb8-144">Off Work</span></span>|
|| ![Círculo gris con una x, indica que está Desconectado](media/Presence_Offline.png) <span data-ttu-id="b4fb8-146">Offline</span><span class="sxs-lookup"><span data-stu-id="b4fb8-146">Offline</span></span> |
|| ![Círculo gris abierto, indica estado desconocido](media/Presence_Unknown.png) <span data-ttu-id="b4fb8-148">Estado desconocido</span><span class="sxs-lookup"><span data-stu-id="b4fb8-148">Status unknown</span></span>|
||![Círculo rojo abierto con línea diagonal, indica que está bloqueado](media/Presence_Blocked.png) <span data-ttu-id="b4fb8-150">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="b4fb8-150">Blocked</span></span> |
|| ![Círculo púrpura con flecha, indica Fuera de la oficina](media/Presence_OOF.png) <span data-ttu-id="b4fb8-152">Fuera de la oficina</span><span class="sxs-lookup"><span data-stu-id="b4fb8-152">Out of Office</span></span>|
|||

<span data-ttu-id="b4fb8-153">Los Estados de presencia configurados por la aplicación se basan en la actividad del usuario (disponible, ausente), Estados del calendario de Outlook (en una reunión) o Estados de la aplicación de Teams (en una llamada, presentando).</span><span class="sxs-lookup"><span data-stu-id="b4fb8-153">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span>

<span data-ttu-id="b4fb8-154">El estado actual de presencia cambiará a ausente cuando bloquee el equipo o cuando entre en modo de suspensión o de espera.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-154">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="b4fb8-155">En dispositivos móviles, el estado de presencia cambiará a ausente cuando la aplicación de Teams esté en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-155">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="b4fb8-156">Los usuarios reciben todos los mensajes de chat que se les envían en los equipos, independientemente de su estado de presencia.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-156">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="b4fb8-157">Si un usuario está desconectado cuando alguien le envía un mensaje, el mensaje de chat aparece en Teams la próxima vez que el usuario se conecta.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-157">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="b4fb8-158">Si un usuario no molesta, el usuario aún recibirá mensajes instantáneos pero no se mostrarán las notificaciones de banner.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-158">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="b4fb8-159">Los usuarios reciben llamadas en todos los Estados de presencia excepto en no molestar, en el que las llamadas entrantes se dirigen al buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-159">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="b4fb8-160">Si el destinatario bloqueó la llamada, la llamada no será entregada y la persona que llama ve la presencia del destinatario como desconectada.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-160">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="b4fb8-161">Los usuarios pueden agregar a personas a su lista de acceso prioritario yendo a **Configuración** > **Privacidad** en Teams.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-161">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="b4fb8-162">Las personas con acceso prioritario pueden ponerse en contacto con el usuario incluso cuando el usuario está en no molestar.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-162">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="b4fb8-163">Configuración de administración en equipos en comparación con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b4fb8-163">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="b4fb8-164">La siguiente configuración de administración Skype Empresarial es diferente en Teams:</span><span class="sxs-lookup"><span data-stu-id="b4fb8-164">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="b4fb8-165">En Teams, el uso compartido de la presencia siempre está habilitado para los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-165">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="b4fb8-166">La configuración de privacidad (donde se define quién puede ver la presencia) no está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-166">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="b4fb8-167">Compartir la presencia con todo el mundo (incluidos los servicios Federados) siempre está habilitado para los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-167">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="b4fb8-168">Su lista de contactos (si tenía una en Skype Empresarial) está visible en**Chat > Contactos** o en **Llamadas > Contactos**.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-168">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="b4fb8-169">Las funciones de No molestar al cliente y Contacto siempre están habilitadas para los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-169">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="b4fb8-170">La integración del calendario (incluye información de fuera de la oficina y otra información de calendario) siempre está habilitada para los usuarios cuando Teams se integra con Outlook.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-170">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="b4fb8-171">El indicador *Último visto* o *Ausente desde* siempre está habilitado para los usuarios en Teams si la organización también usa Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-171">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="b4fb8-172">Actualmente no se admite la capacidad de un administrador de Teams para personalizar estos ajustes.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-172">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="b4fb8-173">Coexistencia con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b4fb8-173">Coexistence with Skype for Business</span></span>

<span data-ttu-id="b4fb8-174">Consulte[ Coexistencia con Skype Empresarial ](coexistence-chat-calls-presence.md)para obtener más información sobre cómo funciona la presencia en Teams cuando tu organización también usa Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b4fb8-174">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
