---
title: Responder al operador automático y llamar a la cola de llamadas directamente desde Teams
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Describe los operadores automáticos de la nube y las colas de llamadas, y explica cómo puede responder a estas llamadas en Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a508aeb6c5e1359c9b3432834f2f0f3d141aea2d
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516800"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="5e1e5-103">Responder al operador automático y llamar a la cola de llamadas directamente desde Teams</span><span class="sxs-lookup"><span data-stu-id="5e1e5-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="5e1e5-104">Los usuarios de Teams pueden recibir y responder llamadas de los operadores automáticos de la nube y de las colas de llamadas directamente desde el cliente de su equipo.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="5e1e5-105">Para los usuarios de Teams, la característica de operador automático ahora está disponible generalmente y la función cola de llamadas está en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="5e1e5-106">¿Qué son los operadores automáticos y las colas de llamadas?</span><span class="sxs-lookup"><span data-stu-id="5e1e5-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="5e1e5-107">Los operadores automáticos de la nube proporcionan una serie de mensajes de voz o un archivo de audio que escuchan las personas que llaman en lugar de un operador humano cuando llaman a una organización.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-107">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="5e1e5-108">Un operador automático permite que los autores de llamadas se muevan por el sistema de menús, llamen y localicen a usuarios utilizando el teclado del teléfono (DTMF) o su propia voz gracias al reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="5e1e5-109">Las colas de llamadas en nube incluyen saludos que se usan cuando un usuario llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de buscar el siguiente agente de llamada disponible para controlar la llamada mientras las personas que llaman son escuchando música en espera.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-109">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="5e1e5-110">Puede crear una o varias colas de llamadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="5e1e5-111">Control de una llamada de cola de llamadas o de operador automático</span><span class="sxs-lookup"><span data-stu-id="5e1e5-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="5e1e5-112">Los usuarios podrán diferenciar las llamadas entrantes de un operador automático o de una cola de llamadas antes de responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="5e1e5-113">Junto con el nombre o el número de la persona que llama, cada llamada incluirá información sobre la persona que llama intentando llegar, lo que proporciona a los usuarios un contexto mejor para dirigir la llamada.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="5e1e5-114">La ilustración siguiente muestra cómo un usuario verá una llamada entrante de un operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Captura de pantalla de una notificación de llamada entrante](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="5e1e5-116">Una vez que se responde a un operador automático o a una llamada de cola de llamadas, el usuario puede procesar la llamada como cualquier otra llamada &#x2014; que pueden agregar o realizar una conferencia en otro usuario o transferir la llamada a otra persona.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="5e1e5-117">Además, las llamadas de operador automático se desviarán en función de la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="5e1e5-118">Las llamadas a la cola de llamadas no se desvían en función de la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="5e1e5-119">Esto garantiza que los autores de llamadas permanezcan en la cola hasta que un agente pueda contestar la llamada y que la persona que llama no se desvíe de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="5e1e5-120">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="5e1e5-120">Supported clients</span></span>

<span data-ttu-id="5e1e5-121">La compatibilidad con el operador automático y las llamadas a la cola de llamadas está disponible en los siguientes clientes:</span><span class="sxs-lookup"><span data-stu-id="5e1e5-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="5e1e5-122">Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="5e1e5-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="5e1e5-123">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="5e1e5-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="5e1e5-124">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="5e1e5-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="5e1e5-125">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="5e1e5-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="5e1e5-126">Configurar el operador automático y la cola de llamadas para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e1e5-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="5e1e5-127">Para recibir llamadas de operador automático y cola de llamadas en Microsoft Teams, necesita configurar la Directiva de interoperabilidad y la actualización de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="5e1e5-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="5e1e5-128">Revise la [migración y la interoperabilidad de las organizaciones que usan Teams conjuntamente con Skype empresarial](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="5e1e5-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="5e1e5-129">Si no tiene configurado el operador automático o la cola de llamadas y desea hacerlo, consulte [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md) y [crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="5e1e5-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5e1e5-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5e1e5-130">Related topics</span></span>

-   [<span data-ttu-id="5e1e5-131">Qué es el sistema telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="5e1e5-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="5e1e5-132">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="5e1e5-132">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-   [<span data-ttu-id="5e1e5-133">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="5e1e5-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="5e1e5-134">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="5e1e5-134">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

