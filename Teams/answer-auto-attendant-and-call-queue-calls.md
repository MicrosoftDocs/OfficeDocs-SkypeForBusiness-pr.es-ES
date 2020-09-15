---
title: Contestar llamadas a la cola de llamadas y el operador automático
ms.reviewer: waseemh
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
ms.openlocfilehash: 95719bc95cc752888964a5f404e6f8050ebf3fa4
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766864"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="b93b7-103">Responder al operador automático y llamar a la cola de llamadas directamente desde Teams</span><span class="sxs-lookup"><span data-stu-id="b93b7-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="b93b7-104">Los usuarios de Teams pueden recibir y responder llamadas de los operadores automáticos de la nube y de las colas de llamadas directamente desde el cliente de su equipo.</span><span class="sxs-lookup"><span data-stu-id="b93b7-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="b93b7-105">¿Qué son los operadores automáticos y las colas de llamadas?</span><span class="sxs-lookup"><span data-stu-id="b93b7-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="b93b7-106">Los operadores automáticos de la nube proporcionan una serie de mensajes de voz o un archivo de audio que escuchan las personas que llaman en lugar de un operador humano cuando llaman a una organización.</span><span class="sxs-lookup"><span data-stu-id="b93b7-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="b93b7-107">Un operador automático permite que los autores de llamadas se muevan por el sistema de menús, llamen y localicen a usuarios utilizando el teclado del teléfono (DTMF) o su propia voz gracias al reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="b93b7-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="b93b7-108">Las colas de llamadas en nube incluyen saludos que se usan cuando un usuario llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la posibilidad de buscar el siguiente agente de llamada disponible para controlar la llamada mientras las personas que llaman escuchan música en espera.</span><span class="sxs-lookup"><span data-stu-id="b93b7-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="b93b7-109">Puede crear una o varias colas de llamadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="b93b7-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="b93b7-110">Control de una llamada de cola de llamadas o de operador automático</span><span class="sxs-lookup"><span data-stu-id="b93b7-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="b93b7-111">Los usuarios podrán diferenciar las llamadas entrantes de un operador automático o de una cola de llamadas antes de responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="b93b7-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="b93b7-112">Junto con el nombre o el número de la persona que llama, cada llamada incluirá información sobre la persona que llama intentando llegar, lo que proporciona a los usuarios un contexto mejor para dirigir la llamada.</span><span class="sxs-lookup"><span data-stu-id="b93b7-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="b93b7-113">La ilustración siguiente muestra cómo un usuario verá una llamada entrante de un operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b93b7-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Captura de pantalla de una notificación de llamada entrante](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="b93b7-115">Una vez que se responde a un operador automático o a una llamada de cola de llamadas, el usuario puede procesar la llamada como cualquier otra llamada &#x2014; que pueden agregar o realizar una conferencia en otro usuario o transferir la llamada a otra persona.</span><span class="sxs-lookup"><span data-stu-id="b93b7-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="b93b7-116">Además, las llamadas de operador automático se desviarán en función de la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="b93b7-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="b93b7-117">Las llamadas a la cola de llamadas no se desvían en función de la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="b93b7-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="b93b7-118">Esto garantiza que los autores de llamadas permanezcan en la cola hasta que un agente pueda contestar la llamada y que la persona que llama no se desvíe de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="b93b7-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="b93b7-119">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="b93b7-119">Supported clients</span></span>

<span data-ttu-id="b93b7-120">La compatibilidad con el operador automático y las llamadas a la cola de llamadas está disponible en los siguientes clientes:</span><span class="sxs-lookup"><span data-stu-id="b93b7-120">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="b93b7-121">Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="b93b7-121">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="b93b7-122">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="b93b7-122">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="b93b7-123">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="b93b7-123">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="b93b7-124">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="b93b7-124">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="b93b7-125">Configurar el operador automático y la cola de llamadas para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b93b7-125">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="b93b7-126">Para recibir llamadas de operador automático y cola de llamadas en Microsoft Teams, necesita configurar la Directiva de interoperabilidad y la actualización de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="b93b7-126">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="b93b7-127">Revise la [migración y la interoperabilidad de las organizaciones que usan Teams conjuntamente con Skype empresarial](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="b93b7-127">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="b93b7-128">Si no tiene configurado el operador automático o la cola de llamadas y desea hacerlo, consulte [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md) y [crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="b93b7-128">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="b93b7-129">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b93b7-129">Known Issues</span></span>

<span data-ttu-id="b93b7-130">Cuando un agente de cola de llamadas recibe una llamada en su dispositivo móvil, las llamadas pueden estar en espera si el dispositivo está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="b93b7-130">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="b93b7-131">El usuario primero debe desbloquear el dispositivo y luego responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="b93b7-131">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b93b7-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b93b7-132">Related topics</span></span>

-    [<span data-ttu-id="b93b7-133">Qué es el sistema telefónico en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="b93b7-133">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="b93b7-134">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="b93b7-134">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="b93b7-135">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="b93b7-135">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="b93b7-136">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="b93b7-136">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

