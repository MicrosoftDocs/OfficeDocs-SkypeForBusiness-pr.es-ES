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
description: Determine qué plan de llamadas de Microsoft Phone System servirá mejor a su organización en Voz en la nube en Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102736"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="f20b7-103">¿Qué plan de llamada es adecuado para usted?</span><span class="sxs-lookup"><span data-stu-id="f20b7-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="f20b7-104">Ha completado la [introducción.](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="f20b7-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="f20b7-105">Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="f20b7-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="f20b7-106">Puede que haya implementado Reuniones [& conferencias.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="f20b7-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="f20b7-107">Ahora ya está listo para agregar cargas de trabajo de voz en la nube y ha decidido usar Microsoft Phone System con plan de llamadas para conectarse a la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="f20b7-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="f20b7-108">En este artículo se describen las decisiones básicas de implementación de planes de llamadas, así como consideraciones adicionales que puede que desee configurar, en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="f20b7-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="f20b7-109">También debe leer Voz en [la nube en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f20b7-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="f20b7-110">Más información sobre planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="f20b7-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="f20b7-111">En los artículos siguientes se proporciona más información sobre la implementación y el uso de planes de llamadas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="f20b7-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="f20b7-112">Sistema telefónico en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="f20b7-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="f20b7-113">Planes de llamadas para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="f20b7-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="f20b7-114">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="f20b7-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="f20b7-115">Decisiones de implementación principales</span><span class="sxs-lookup"><span data-stu-id="f20b7-115">Core deployment decisions</span></span>

<span data-ttu-id="f20b7-116">Para usar Microsoft como operador de telefonía, debe obtener licencias del Plan de llamadas y asignarlas a los usuarios del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="f20b7-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="f20b7-117">Hay dos tipos de planes de llamadas disponibles:</span><span class="sxs-lookup"><span data-stu-id="f20b7-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="f20b7-118">Planes de llamadas nacionales</span><span class="sxs-lookup"><span data-stu-id="f20b7-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="f20b7-119">Planes de llamadas nacionales e internacionales</span><span class="sxs-lookup"><span data-stu-id="f20b7-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="f20b7-120">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f20b7-120">Ask yourself</span></span>|<span data-ttu-id="f20b7-121">Acción</span><span class="sxs-lookup"><span data-stu-id="f20b7-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="f20b7-122">¿Hay planes de llamadas disponibles en mi área?</span><span class="sxs-lookup"><span data-stu-id="f20b7-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="f20b7-123">¿Qué ubicaciones de usuario tendrán servicio plan de llamadas?</span><span class="sxs-lookup"><span data-stu-id="f20b7-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="f20b7-124">Para obtener más información, vea [Disponibilidad de país y región para planes de audioconferencias y llamadas.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="f20b7-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="f20b7-125">¿Mis usuarios necesitan llamadas internacionales?</span><span class="sxs-lookup"><span data-stu-id="f20b7-125">Do my users need international calling?</span></span> | <span data-ttu-id="f20b7-126">Para obtener más información, vea [Planes de llamadas para Microsoft 365 u Office 365.](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f20b7-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="f20b7-127">¿Mis usuarios tienen licencias de planes de llamadas?</span><span class="sxs-lookup"><span data-stu-id="f20b7-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="f20b7-128">Para comprar y asignar licencias, vea [Paso 2: Comprar y asignar licencias.](set-up-calling-plans.md#step-2-buy-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="f20b7-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="f20b7-129">¿Mis usuarios tienen cada uno un número de teléfono de marcado directo hacia adentro (DID)?</span><span class="sxs-lookup"><span data-stu-id="f20b7-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="f20b7-130">Para obtener números de teléfono, vea [Paso 3: Obtener números de teléfono.](set-up-calling-plans.md#step-3-get-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="f20b7-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="f20b7-131">Transferir números de teléfono a Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="f20b7-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="f20b7-132">Es fácil transferir los números de teléfono de su proveedor de servicios actual a Teams.</span><span class="sxs-lookup"><span data-stu-id="f20b7-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="f20b7-133">Después de portabilidad de los números de teléfono a Teams, Microsoft se convertirá en su proveedor de servicios y le facturará esos números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="f20b7-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="f20b7-134">Para obtener más información, vea [Transferir números de teléfono a Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f20b7-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="f20b7-135">Números de teléfono y ubicaciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="f20b7-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="f20b7-136">Con planes de llamadas en Microsoft 365 u Office 365, todos los usuarios de su organización deben tener un número de teléfono de llamada directa (DID) único y una dirección de emergencia validada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f20b7-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="f20b7-137">También puede especificar una ubicación de emergencia dentro de la dirección de emergencia (por ejemplo, un número de oficina o un número de planta).</span><span class="sxs-lookup"><span data-stu-id="f20b7-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="f20b7-138">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f20b7-138">Ask yourself</span></span>|<span data-ttu-id="f20b7-139">Acción</span><span class="sxs-lookup"><span data-stu-id="f20b7-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="f20b7-140">¿Qué detalle deseo que tenga la dirección de emergencia y la información de ubicación?</span><span class="sxs-lookup"><span data-stu-id="f20b7-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="f20b7-141">Para obtener más información, vea ¿Qué son las [ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="f20b7-141">For more information, see [What are emergency locations, addresses, and call routing?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="f20b7-142">Identidad de llamada</span><span class="sxs-lookup"><span data-stu-id="f20b7-142">Calling identity</span></span>

<span data-ttu-id="f20b7-143">De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificador de llamada).</span><span class="sxs-lookup"><span data-stu-id="f20b7-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="f20b7-144">El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.</span><span class="sxs-lookup"><span data-stu-id="f20b7-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="f20b7-145">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f20b7-145">Ask yourself</span></span>|<span data-ttu-id="f20b7-146">Acción</span><span class="sxs-lookup"><span data-stu-id="f20b7-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="f20b7-147">¿Quiero enmascarar o deshabilitar el identificador de llamada?</span><span class="sxs-lookup"><span data-stu-id="f20b7-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="f20b7-148">Para cambiar o bloquear el identificador de llamada, vea [Establecer el identificador de llamada de un usuario.](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="f20b7-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||