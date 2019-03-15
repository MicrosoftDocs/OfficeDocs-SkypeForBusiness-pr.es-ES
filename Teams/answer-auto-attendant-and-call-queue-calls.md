---
title: Responder al operador automático y llamar a la cola de llamadas directamente desde Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Describe los operadores automáticos de sistema telefónico y colas de llamadas y se explica cómo puede responder a estas llamadas en los equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 900fe698654a760c9863583da0b3cd161625844d
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569442"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="18349-103">Responder al operador automático y llamar a la cola de llamadas directamente desde Teams</span><span class="sxs-lookup"><span data-stu-id="18349-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="18349-104">Los usuarios de los equipos pueden recibir y responda a llamadas de Skype para profesionales Online operador automático y las colas de llamadas directamente desde su cliente de los equipos.</span><span class="sxs-lookup"><span data-stu-id="18349-104">Teams users can receive and answer calls from Skype for Business Online auto attendant and call queues directly from their Teams client.</span></span> <span data-ttu-id="18349-105">Para los usuarios de los equipos, la característica de operador automático está ahora disponible por lo general y la funcionalidad de cola de llamadas está en vista previa.</span><span class="sxs-lookup"><span data-stu-id="18349-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="18349-106">¿Cuáles son automáticos y colas de llamadas?</span><span class="sxs-lookup"><span data-stu-id="18349-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="18349-107">Operadores automáticos de teléfono del sistema proporcionan una serie de mensajes de voz o un archivo de audio que escuchen los autores de llamadas en lugar de un operador humano cuando llaman a una organización.</span><span class="sxs-lookup"><span data-stu-id="18349-107">Phone System auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="18349-108">Un operador automático permite que los autores de llamadas se muevan por el sistema de menús, llamen y localicen a usuarios utilizando el teclado del teléfono (DTMF) o su propia voz gracias al reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="18349-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="18349-109">Llamada de teléfono del sistema colas incluyen el saludo que se usa cuando alguien llama a un número de teléfono para su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de búsqueda para el siguiente agente de llamada disponibles controlar la llamada mientras las personas que llamada se escuchan música en espera.</span><span class="sxs-lookup"><span data-stu-id="18349-109">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="18349-110">Puede crear una o varias colas de llamadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="18349-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="18349-111">Controlar una llamada de cola de llamada o de operador automático</span><span class="sxs-lookup"><span data-stu-id="18349-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="18349-112">Los usuarios podrán diferenciar las llamadas entrantes de una cola de llamada o de operador automático antes de que responda a la llamada.</span><span class="sxs-lookup"><span data-stu-id="18349-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="18349-113">Junto con el nombre o el número del autor de la llamada, cada llamada incluirá información acerca de la que el autor de la llamada estaba intentando alcanzar, dar a los usuarios un mejor contexto para hacer frente a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="18349-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="18349-114">En la siguiente ilustración se muestra cómo aparecerá una llamada recibida de una cola de llamada o de operador automático a un usuario.</span><span class="sxs-lookup"><span data-stu-id="18349-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Notificación de llamada entrante](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="18349-116">Una vez que se responde a una llamada de cola de llamada o de operador automático, el usuario puede procesar la llamada al igual que cualquier otro & de llamada #x 2014; pueden agregar o conferencia en otro usuario o transferir la llamada a otra persona.</span><span class="sxs-lookup"><span data-stu-id="18349-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="18349-117">Además, las llamadas de operador automático se desviarán según la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="18349-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="18349-118">Cola de llamadas no se transfieren en función de la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="18349-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="18349-119">Esto es para asegurarse de que los autores de llamadas permanecen en la cola hasta que un agente puede responder a la llamada y el autor de la llamada no se reenvía de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="18349-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="18349-120">Clientes admitidos</span><span class="sxs-lookup"><span data-stu-id="18349-120">Supported clients</span></span>

<span data-ttu-id="18349-121">Compatibilidad para las llamadas de cola de operador y llamada automático está disponible en los siguientes clientes:</span><span class="sxs-lookup"><span data-stu-id="18349-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="18349-122">Cliente de Microsoft Teams para Windows (versiones de 32 y 64 bits)</span><span class="sxs-lookup"><span data-stu-id="18349-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="18349-123">Cliente de Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="18349-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="18349-124">Aplicación Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="18349-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="18349-125">Aplicación Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="18349-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="18349-126">Configurar la auto attendant y llamada de cola compatibilidad con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18349-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="18349-127">Para recibir el operador automático y llamar a las llamadas de cola en Microsoft Teams, debe configurar la directiva de interoperabilidad y actualización de directiva.</span><span class="sxs-lookup"><span data-stu-id="18349-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="18349-128">Revise la [migración y la interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="18349-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="18349-129">Si no dispone de operador automático o cola de llamadas configurado y desea hacerlo, vea [configurar un operador automático de sistema telefónico](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) y [crear una cola de llamadas de sistema telefónico](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span><span class="sxs-lookup"><span data-stu-id="18349-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Phone System auto attendant](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) and [Create a Phone System call queue](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span></span>

## <a name="related-topics"></a><span data-ttu-id="18349-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="18349-130">Related topics</span></span>

-   [<span data-ttu-id="18349-131">¿Qué es el sistema telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="18349-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="18349-132">Crear una cola de llamadas para el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="18349-132">Create a Phone System call queue</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [<span data-ttu-id="18349-133">¿Qué son los operadores automáticos del Sistema telefónico?</span><span class="sxs-lookup"><span data-stu-id="18349-133">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="18349-134">Configurar un operador automático para el sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="18349-134">Set up a Phone System auto attendant</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

