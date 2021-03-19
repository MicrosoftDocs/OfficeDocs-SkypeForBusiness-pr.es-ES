---
title: Responder llamadas de operador automático y cola de llamadas
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Describe los operadores automáticos de la nube y las colas de llamadas, y explica cómo puede responder a estas llamadas en Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cca068ab1194a48eb775550e4bf3f99826d82d2a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874670"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="29bcb-103">Responder al operador automático y llamar a la cola de llamadas directamente desde Teams</span><span class="sxs-lookup"><span data-stu-id="29bcb-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="29bcb-104">Los usuarios de Teams pueden recibir y responder llamadas de operadores automáticos de la nube y colas de llamadas directamente desde su cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="29bcb-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="29bcb-105">¿Qué son los operadores automáticos y las colas de llamadas?</span><span class="sxs-lookup"><span data-stu-id="29bcb-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="29bcb-106">Los operadores automáticos en la nube proporcionan una serie de mensajes de voz o un archivo de audio que los autores de llamadas escuchan en lugar de un operador humano cuando llaman a una organización.</span><span class="sxs-lookup"><span data-stu-id="29bcb-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="29bcb-107">Un operador automático permite que los autores de llamadas se muevan por el sistema de menús, llamen y localicen a usuarios utilizando el teclado del teléfono (DTMF) o su propia voz gracias al reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="29bcb-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="29bcb-108">Las colas de llamadas en la nube incluyen saludos que se usan cuando alguien llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de buscar el siguiente agente de llamada disponible para controlar la llamada mientras las personas que llaman escuchan música en espera.</span><span class="sxs-lookup"><span data-stu-id="29bcb-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="29bcb-109">Puede crear una o varias colas de llamadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="29bcb-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="29bcb-110">Administrar un operador automático o una llamada de cola de llamadas</span><span class="sxs-lookup"><span data-stu-id="29bcb-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="29bcb-111">Los usuarios podrán diferenciar las llamadas entrantes de un operador automático o una cola de llamadas antes de responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="29bcb-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="29bcb-112">Junto con el nombre o el número del autor de la llamada, cada llamada incluirá información sobre a quién estaba intentando contactar el autor de la llamada, lo que proporciona a los usuarios un contexto mejor para dirigirse al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="29bcb-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="29bcb-113">En la ilustración siguiente se muestra cómo se mostrará a un usuario una llamada entrante desde un operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="29bcb-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Captura de pantalla de una notificación de llamada entrante](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="29bcb-115">Una vez que se responde a un operador automático o llamada de cola de llamadas, el usuario puede procesar la llamada como cualquier otra llamada &#x2014; puede agregar o conferenciar en otro usuario o transferir la llamada a otra parte.</span><span class="sxs-lookup"><span data-stu-id="29bcb-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="29bcb-116">Además, las llamadas de operador automático se reenviarán en función de la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="29bcb-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="29bcb-117">Las llamadas de cola de llamadas no se reenvía en función de la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="29bcb-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="29bcb-118">Esto es para asegurarse de que los autores de llamadas permanezcan en la cola hasta que un agente pueda responder a la llamada y el autor de la llamada no se reenvía inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="29bcb-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

> <span data-ttu-id="29bcb-119">Los agentes no son notificados de las llamadas perdidas o mensajes de voz para las llamadas en cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="29bcb-119">Agents are not notified of any missed calls or voicemails for call queue calls.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="29bcb-120">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="29bcb-120">Supported clients</span></span>

<span data-ttu-id="29bcb-121">El soporte para llamadas automáticas y de cola de llamadas está disponible en los clientes siguientes:</span><span class="sxs-lookup"><span data-stu-id="29bcb-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="29bcb-122">Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="29bcb-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="29bcb-123">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="29bcb-123">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="29bcb-124">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="29bcb-124">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="29bcb-125">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="29bcb-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="29bcb-126">Configurar el operador automático y la cola de llamadas para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29bcb-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="29bcb-127">Para recibir llamadas de cola de llamadas y operadores automáticos en Microsoft Teams, debe configurar la directiva de interoperabilidad y la directiva de actualización.</span><span class="sxs-lookup"><span data-stu-id="29bcb-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="29bcb-128">Revise Migración [e interoperabilidad para organizaciones que usan Teams junto con Skype Empresarial.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="29bcb-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="29bcb-129">Si no tiene configurado el operador automático o la cola de [](create-a-phone-system-auto-attendant.md) llamadas y quiere hacerlo, vea Configurar un operador automático en la nube y Crear una cola de llamadas en la [nube.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="29bcb-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="29bcb-130">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="29bcb-130">Known Issues</span></span>

<span data-ttu-id="29bcb-131">Cuando un agente de la cola de llamadas recibe una llamada en su dispositivo móvil, las llamadas pueden estar en espera si el dispositivo está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="29bcb-131">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="29bcb-132">El usuario debe desbloquear el dispositivo primero y, a continuación, responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="29bcb-132">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="29bcb-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="29bcb-133">Related topics</span></span>

-    [<span data-ttu-id="29bcb-134">Qué es Sistema telefónico en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="29bcb-134">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="29bcb-135">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="29bcb-135">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="29bcb-136">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="29bcb-136">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="29bcb-137">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="29bcb-137">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

