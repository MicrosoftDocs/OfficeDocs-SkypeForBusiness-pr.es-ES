---
title: Planes de llamadas en Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Página de aterrizaje de la planificación de llamadas
appliesto:
- Microsoft Teams
ms.openlocfilehash: d27169d5f65fb693ce49453f7e7c965f867198ad
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925591"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="cdd6f-103">¿Qué plan de llamada es adecuado para usted?</span><span class="sxs-lookup"><span data-stu-id="cdd6f-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="cdd6f-104">Has completado la [Introducción](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="cdd6f-105">Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="cdd6f-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="cdd6f-106">Es posible que haya implementado [reuniones & conferencias](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="cdd6f-107">Ahora está listo para agregar cargas de trabajo de voz de nube y ha decidido usar el sistema de teléfono de Microsoft con el plan de llamadas para conectarse a la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="cdd6f-108">En este artículo se describen las decisiones básicas de implementación para la llamada a planes, así como consideraciones adicionales que es posible que desee configurar en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="cdd6f-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="cdd6f-109">También debe leer [la voz de nube en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cdd6f-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="cdd6f-110">Más información sobre los planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="cdd6f-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="cdd6f-111">Los artículos siguientes proporcionan más información sobre la implementación y el uso de los planes de llamadas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="cdd6f-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="cdd6f-112">Sistema telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="cdd6f-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="cdd6f-113">Planes de llamadas para Office 365</span><span class="sxs-lookup"><span data-stu-id="cdd6f-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="cdd6f-114">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="cdd6f-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="cdd6f-115">Decisiones de implementación principales</span><span class="sxs-lookup"><span data-stu-id="cdd6f-115">Core deployment decisions</span></span>

<span data-ttu-id="cdd6f-116">Para usar Microsoft como su operador de telefonía, debe obtener las licencias del plan de llamadas y asignarlas a los usuarios del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="cdd6f-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="cdd6f-117">Existen dos tipos de planes de llamadas:</span><span class="sxs-lookup"><span data-stu-id="cdd6f-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="cdd6f-118">Planes de llamadas nacionales</span><span class="sxs-lookup"><span data-stu-id="cdd6f-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="cdd6f-119">Planes de llamadas nacionales e internacionales</span><span class="sxs-lookup"><span data-stu-id="cdd6f-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="cdd6f-120">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cdd6f-120">Ask yourself</span></span>|<span data-ttu-id="cdd6f-121">Acción</span><span class="sxs-lookup"><span data-stu-id="cdd6f-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="cdd6f-122">¿Están disponibles los planes de llamadas en mi área?</span><span class="sxs-lookup"><span data-stu-id="cdd6f-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="cdd6f-123">¿Qué ubicaciones de usuarios tendrán el servicio de plan de llamadas?</span><span class="sxs-lookup"><span data-stu-id="cdd6f-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="cdd6f-124">Para obtener más información, consulte [disponibilidad de países y regiones para las conferencias de audio y los planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="cdd6f-125">¿Los usuarios necesitan llamadas internacionales?</span><span class="sxs-lookup"><span data-stu-id="cdd6f-125">Do my users need international calling?</span></span> | <span data-ttu-id="cdd6f-126">Para obtener más información, consulte [planes de llamadas para Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="cdd6f-127">¿Tienen mis usuarios licencias de planes de llamadas?</span><span class="sxs-lookup"><span data-stu-id="cdd6f-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="cdd6f-128">Para comprar y asignar licencias, consulte el [paso 2: comprar y asignar licencias](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="cdd6f-129">¿Cada uno de mis usuarios tiene un número de teléfono de marcado directo?</span><span class="sxs-lookup"><span data-stu-id="cdd6f-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="cdd6f-130">Para obtener números de teléfono, consulte [paso 3: obtener números de teléfono](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="cdd6f-131">Transferir números de teléfono a Office 365</span><span class="sxs-lookup"><span data-stu-id="cdd6f-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="cdd6f-132">Es fácil transferir los números de teléfono de su proveedor de servicios actual a teams.</span><span class="sxs-lookup"><span data-stu-id="cdd6f-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="cdd6f-133">Después de trasladar los números de teléfono a Teams, Microsoft se convertirá en su proveedor de servicios y le facturará los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="cdd6f-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="cdd6f-134">Para obtener más información, consulte [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="cdd6f-135">Números de teléfono y ubicaciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="cdd6f-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="cdd6f-136">Con los planes de llamadas en Office 365, todos los usuarios de su organización necesitan tener un número de teléfono de marcado directo exclusivo y una dirección de emergencia validada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="cdd6f-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="cdd6f-137">También puedes especificar una ubicación de emergencia dentro de la dirección de emergencia (por ejemplo, un número de oficina o un número de piso).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="cdd6f-138">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cdd6f-138">Ask yourself</span></span>|<span data-ttu-id="cdd6f-139">Acción</span><span class="sxs-lookup"><span data-stu-id="cdd6f-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="cdd6f-140">¿Qué grado de detalle quiero que sea la dirección de emergencia y la información de ubicación?</span><span class="sxs-lookup"><span data-stu-id="cdd6f-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="cdd6f-141">Para obtener más información, vea [¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="cdd6f-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="cdd6f-142">Identidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="cdd6f-142">Calling identity</span></span>

<span data-ttu-id="cdd6f-143">De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificación de llamada).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="cdd6f-144">El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.</span><span class="sxs-lookup"><span data-stu-id="cdd6f-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="cdd6f-145">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cdd6f-145">Ask yourself</span></span>|<span data-ttu-id="cdd6f-146">Acción</span><span class="sxs-lookup"><span data-stu-id="cdd6f-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="cdd6f-147">¿Quiero enmascarar o deshabilitar la identificación de llamadas?</span><span class="sxs-lookup"><span data-stu-id="cdd6f-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="cdd6f-148">Para cambiar o bloquear la identificación de llamadas, vea [establecer la identificación de llamadas de un usuario](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="cdd6f-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




