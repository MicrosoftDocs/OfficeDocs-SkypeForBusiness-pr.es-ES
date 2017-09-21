---
title: "Interacción entre Skype Empresarial y Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "Conozca cómo interaccionan Skype Empresarial y Microsoft Teams, desde los chats hasta las llamadas."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 02d11632a0a6b8f78504ab20ae3415a942e6c91f
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a><span data-ttu-id="ff767-103">Interacción entre Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff767-103">How Skype for Business and Microsoft Teams interact</span></span>
===================================================

<span data-ttu-id="ff767-104">Si su organización usa actualmente Skype Empresarial, es importante que comprenda cómo interaccionarán Skype Empresarial y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ff767-104">If your organization uses Skype for Business today, it is important to understand how Skype for Business and Microsoft Teams will interact.</span></span>

<span data-ttu-id="ff767-105">Cuando Microsoft Teams está disponible de manera general, la interoperabilidad básica entre Microsoft Teams y Skype Empresarial Online o Híbrido está disponible solo mediante mensajería instantánea de punto a punto (P2P).</span><span class="sxs-lookup"><span data-stu-id="ff767-105">At general availability of Microsoft Teams, basic interoperability between Microsoft Teams and Skype for Business Online or Hybrid is available peer to peer (P2P) instant messaging only.</span></span>

<span data-ttu-id="ff767-p101">El comportamiento predeterminado es que el cliente de Microsoft Teams iniciará sesión en los servicios back-end de Microsoft Teams y en los servicios de Skype Empresarial (enfoque de doble pila). El cliente de Microsoft Teams presentará solamente capacidades de MI para Skype Empresarial, así que al buscar un usuario de Microsoft Teams desde Skype Empresarial solo indicará el usuario como Solo MI. En el ejemplo de abajo, Alix Wilber ha iniciado sesión solamente en el cliente de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ff767-p101">The default behavior is that the Microsoft Teams client will sign into both the Microsoft Teams backend services and the Skype for Business services (a dual-stack approach). The Microsoft Teams client will only present IM capabilities to Skype for Business, so looking up a Microsoft Teams user from Skype for Business will only indicate the user as IM Only – shown in the example below, Alix Wilber is only signed into the Microsoft Teams client.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

<span data-ttu-id="ff767-108">En Microsoft Teams, los usuarios pueden buscar otros usuarios dentro de su organización que actualmente estén habilitados solo para Skype Empresarial y realizar sesiones de chat de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="ff767-108">From Microsoft Teams, users can search for other users within their organization who are currently only enabled for Skype for Business, and conduct instant messaging chat sessions.</span></span>

<span data-ttu-id="ff767-109">Los usuarios de Skype Empresarial pueden responder los mensajes instantáneos, que se recibirán en la ventana de chat de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ff767-109">Users on Skype for Business can reply to the instant messages, which will arrive in Microsoft Teams’ chat window.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

<span data-ttu-id="ff767-110">Los usuarios de Microsoft Teams, si están habilitados también para Skype Empresarial, pueden iniciar sesión en Microsoft Teams y Skype Empresarial simultáneamente con sus propios clientes respectivos.</span><span class="sxs-lookup"><span data-stu-id="ff767-110">Users on Microsoft Teams, if enabled for Skype for Business as well, can sign in to Microsoft Teams and Skype for Business using their own respective clients simultaneously.</span></span>

<span data-ttu-id="ff767-p102">Se atenderá el último punto de conexión activo, de modo que si el usuario usa activamente Microsoft Teams, todos los mensajes instantáneos enviados desde un usuario de Skype Empresarial se recibirán en la ventana de chat de Microsoft Teams. Si el usuario está usando actualmente Skype Empresarial para recibir o realizar llamadas o acaba de terminar una llamada con Skype Empresarial y no ha vuelto al cliente de Microsoft Teams, los mensajes instantáneos entrantes enviados por un usuario de Skype Empresarial llegarán al cliente de Skype Empresarial, ya que este será el punto de conexión más activo.</span><span class="sxs-lookup"><span data-stu-id="ff767-p102">The last active endpoint will be honored, so if the user is actively using Microsoft Teams, any instant messages sent from a Skype for Business user will arrive in the Microsoft Teams chat window. If the user is currently using Skype for Business to receive/make phone calls or just finished taking a call using Skype for Business, and have not returned to Microsoft Teams client, incoming instant messages sent from a Skype for Business user will arrive in Skype for Business client as this will be the most active endpoint.</span></span>

<span data-ttu-id="ff767-p103">Como Microsoft Teams solo admite actualmente interoperabilidad de mensajería instantánea de punto a punto (P2P) entre Skype Empresarial, cualquier llamada de audio o vídeo, o cualquier invitación para unirse a una reunión de Skype Empresarial (de cualquier tipo) desde otro usuario de Skype Empresarial llegará solo al cliente de Skype Empresarial. Esto ocurre también a la inversa: cualquier llamada de audio o vídeo, o cualquier invitación para unirse a una llamada en grupo (de cualquier tipo) desde el cliente de Microsoft Teams sólo llegará al cliente de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ff767-p103">As Microsoft Teams only currently supports peer-to-peer (P2P) instant messaging interop between Skype for Business, any audio/video calls or invitation to join a Skype for Business meetings, for any modalities, from other Skype for Business users will arrive on the Skype for Business client only. In the reverse, any audio/video calls or invitation to join group calling, for any modalities from Microsoft Teams client, will only arrive on the Microsoft Teams client.</span></span>

<span data-ttu-id="ff767-p104">Dado este comportamiento, los usuarios finales pueden usar cómodamente Microsoft Teams y Skype Empresarial a la vez, y controlar sus necesidades de comunicación específicas mediante la herramienta adecuada. Sin embargo, puede que sea necesario que el usuario final comprenda cómo funciona la interoperabilidad y cómo puede afectar a la experiencia del usuario final.</span><span class="sxs-lookup"><span data-stu-id="ff767-p104">With the above behavior, end users can comfortably use both Microsoft Teams and Skype for Business at the same time, and handle specific communications needs using the right tool. However, proper end user awareness may be required to understand how interoperability works and how it may impact end user experience.</span></span>


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br><span data-ttu-id="ff767-117">Nota</span><span class="sxs-lookup"><span data-stu-id="ff767-117">Note</span></span></br>      |<span data-ttu-id="ff767-118">Con la interoperabilidad de Skype Empresarial, los mensajes instantáneos que se reciben en Teams no se registrarán en el historial de conversaciones de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ff767-118">With Skype for Business interoperability, instant messages that arrive in Teams will not be recorded in Skype for Business conversation history.</span></span>         |

<span data-ttu-id="ff767-p105">Microsoft Teams ofrece a los usuarios la posibilidad de deshabilitar la interoperabilidad de Skype Empresarial desde la opción Notificaciones. Esta opción está controlada por el usuario, lo que permite a cada usuario decidir el comportamiento que prefiera.</span><span class="sxs-lookup"><span data-stu-id="ff767-p105">Microsoft Teams provides the ability for users to disable Skype for Business interoperability from within the Notification settings. This setting is user controlled, allowing each user to decide on the behavior they prefer.</span></span>
