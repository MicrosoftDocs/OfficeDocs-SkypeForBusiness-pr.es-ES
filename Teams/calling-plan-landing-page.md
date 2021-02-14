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
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Determine qué plan de llamadas de sistema telefónico de Microsoft servirá mejor a su organización en Cloud Voice en Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71fe92646a3a2976e9a4d393e54ea56a7669b400
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031856"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="50458-103">¿Qué plan de llamada es adecuado para usted?</span><span class="sxs-lookup"><span data-stu-id="50458-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="50458-104">Ha completado la [introducción.](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="50458-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="50458-105">Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="50458-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="50458-106">Es posible que haya implementado [Reuniones & conferencia.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="50458-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="50458-107">Ahora ya está listo para agregar cargas de trabajo de voz en la nube y ha decidido usar Microsoft Phone System con plan de llamadas para conectarse a la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="50458-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="50458-108">En este artículo se describen las decisiones de implementación básicas para planes de llamadas, así como consideraciones adicionales que puede que quiera configurar según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="50458-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="50458-109">También debe leer [Cloud Voice en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="50458-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="50458-110">Más información sobre planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="50458-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="50458-111">En los artículos siguientes se proporciona más información sobre la implementación y el uso de planes de llamadas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="50458-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="50458-112">Sistema telefónico en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="50458-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="50458-113">Planes de llamadas para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="50458-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="50458-114">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="50458-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="50458-115">Decisiones de implementación principales</span><span class="sxs-lookup"><span data-stu-id="50458-115">Core deployment decisions</span></span>

<span data-ttu-id="50458-116">Para usar Microsoft como su operador de telefonía, debe obtener licencias del plan de llamadas y asignarlas a los usuarios de su sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="50458-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="50458-117">Hay dos tipos de planes de llamadas disponibles:</span><span class="sxs-lookup"><span data-stu-id="50458-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="50458-118">Planes de llamadas nacionales</span><span class="sxs-lookup"><span data-stu-id="50458-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="50458-119">Planes de llamadas nacionales e internacionales</span><span class="sxs-lookup"><span data-stu-id="50458-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="50458-120">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50458-120">Ask yourself</span></span>|<span data-ttu-id="50458-121">Acción</span><span class="sxs-lookup"><span data-stu-id="50458-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="50458-122">¿Los planes de llamadas están disponibles en mi área?</span><span class="sxs-lookup"><span data-stu-id="50458-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="50458-123">¿Qué ubicaciones de usuario tendrán servicio Plan de llamadas?</span><span class="sxs-lookup"><span data-stu-id="50458-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="50458-124">Para obtener más información, consulte Disponibilidad del país y la región para planes de [audioconferencia y llamadas.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="50458-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="50458-125">¿Mis usuarios necesitan llamadas internacionales?</span><span class="sxs-lookup"><span data-stu-id="50458-125">Do my users need international calling?</span></span> | <span data-ttu-id="50458-126">Para obtener más información, [consulte Planes de llamadas para Microsoft 365 u Office 365.](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="50458-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="50458-127">¿Tienen mis usuarios licencias de planes de llamadas?</span><span class="sxs-lookup"><span data-stu-id="50458-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="50458-128">Para comprar y asignar licencias, vea [el paso 2: Comprar y asignar licencias.](set-up-calling-plans.md#step-2-buy-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="50458-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="50458-129">¿Tienen mis usuarios un número de teléfono de marcado directo (DID)?</span><span class="sxs-lookup"><span data-stu-id="50458-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="50458-130">Para obtener números de teléfono, vea [el paso 3: Obtener números de teléfono.](set-up-calling-plans.md#step-3-get-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="50458-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="50458-131">Transferir números de teléfono a Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="50458-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="50458-132">Es fácil transferir sus números de teléfono desde su proveedor de servicios actual a Teams.</span><span class="sxs-lookup"><span data-stu-id="50458-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="50458-133">Después de realizar la portabilidad de sus números de teléfono a Teams, Microsoft se convertirá en su proveedor de servicios y le facturará por esos números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="50458-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="50458-134">Para obtener más información, consulte [Transferir números de teléfono a Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="50458-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="50458-135">Números de teléfono y ubicaciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="50458-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="50458-136">Con los planes de llamadas en Microsoft 365 u Office 365, cada usuario de su organización debe tener un número de teléfono de marcado directo (DID) único y una dirección de emergencia validada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="50458-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="50458-137">También puede especificar una ubicación de emergencia dentro de la dirección de emergencia (por ejemplo, un número de oficina o un número de planta).</span><span class="sxs-lookup"><span data-stu-id="50458-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="50458-138">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50458-138">Ask yourself</span></span>|<span data-ttu-id="50458-139">Acción</span><span class="sxs-lookup"><span data-stu-id="50458-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="50458-140">¿En qué medida quiero que esté la dirección de emergencia y la información de ubicación?</span><span class="sxs-lookup"><span data-stu-id="50458-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="50458-141">Para obtener más información, vea [¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="50458-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="50458-142">Identidad de llamada</span><span class="sxs-lookup"><span data-stu-id="50458-142">Calling identity</span></span>

<span data-ttu-id="50458-143">De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificador de llamada).</span><span class="sxs-lookup"><span data-stu-id="50458-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="50458-144">El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.</span><span class="sxs-lookup"><span data-stu-id="50458-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="50458-145">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50458-145">Ask yourself</span></span>|<span data-ttu-id="50458-146">Acción</span><span class="sxs-lookup"><span data-stu-id="50458-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="50458-147">¿Quiero enmascarar o deshabilitar la identificación de llamadas?</span><span class="sxs-lookup"><span data-stu-id="50458-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="50458-148">Para cambiar o bloquear el identificador de llamada, vea [Establecer el identificador de llamada de un usuario.](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="50458-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




