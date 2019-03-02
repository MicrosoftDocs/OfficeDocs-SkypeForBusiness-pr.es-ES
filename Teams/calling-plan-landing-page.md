---
title: Planes de llamada en los equipos de Microsoft
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Llamar a la página de inicio del Plan
appliesto:
- Microsoft Teams
ms.openlocfilehash: cce239825389e11cfbc627d518e7d1e459fa77d3
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351501"
---
# <a name="phone-system-with-calling-plans"></a><span data-ttu-id="ea4e0-103">Sistema telefónico con Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="ea4e0-103">Phone System with Calling Plans</span></span> 

<span data-ttu-id="ea4e0-104">Se ha completado la [Introducción](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="ea4e0-105">Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="ea4e0-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="ea4e0-106">Es posible que haya implementado [conferencia & de las reuniones](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="ea4e0-107">Ahora está listo para agregar las cargas de trabajo de voz de la nube y ha decidido usar el sistema telefónico de Microsoft con el Plan para llamar a para conectarse a la red telefónica pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="ea4e0-108">En este artículo se describe la implementación las decisiones principales para llamar a los planes, así como consideraciones adicionales que es posible que desea configurar, en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="ea4e0-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="ea4e0-109">También debe leer [En la nube de voz en los equipos de Microsoft](cloud-voice-landing-page.md) para obtener más información acerca de las ofertas de voz de la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ea4e0-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="ea4e0-110">Encontrará más información acerca de los planes de llamada</span><span class="sxs-lookup"><span data-stu-id="ea4e0-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="ea4e0-111">Los artículos siguientes proporcionan más información sobre la implementación y uso de llamar a los planes de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="ea4e0-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="ea4e0-112">Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="ea4e0-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="ea4e0-113">Planes de llamadas para Office 365</span><span class="sxs-lookup"><span data-stu-id="ea4e0-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="ea4e0-114">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="ea4e0-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="ea4e0-115">Decisiones de implementación principales</span><span class="sxs-lookup"><span data-stu-id="ea4e0-115">Core deployment decisions</span></span>

<span data-ttu-id="ea4e0-116">Para usar Microsoft como su operador de telefonía, debe obtener licencias de llamar a planear y asignarlos a los usuarios del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="ea4e0-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="ea4e0-117">Hay dos tipos de planes de llamada disponibles:</span><span class="sxs-lookup"><span data-stu-id="ea4e0-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="ea4e0-118">Planes de llamada nacionales</span><span class="sxs-lookup"><span data-stu-id="ea4e0-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="ea4e0-119">Planes de llamada nacional e internacional</span><span class="sxs-lookup"><span data-stu-id="ea4e0-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="ea4e0-120">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ea4e0-120">Ask yourself</span></span>|<span data-ttu-id="ea4e0-121">Acción</span><span class="sxs-lookup"><span data-stu-id="ea4e0-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="ea4e0-122">¿Son planes de llamada disponibles en Mi área?</span><span class="sxs-lookup"><span data-stu-id="ea4e0-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="ea4e0-123">¿Las ubicaciones de usuario tendrá planeación de llamar al servicio?</span><span class="sxs-lookup"><span data-stu-id="ea4e0-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="ea4e0-124">Para obtener más información, vea [disponibilidad de país y región para las conferencias de Audio y planes de llamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="ea4e0-125">¿Mis usuarios necesitan llamadas internacionales?</span><span class="sxs-lookup"><span data-stu-id="ea4e0-125">Do my users need international calling?</span></span> | <span data-ttu-id="ea4e0-126">Para obtener más información, vea [Llamar a planes de Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="ea4e0-127">¿Mis usuarios tienen una llamada a los planes de licencias?</span><span class="sxs-lookup"><span data-stu-id="ea4e0-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="ea4e0-128">Para comprar y asignar licencias, vea [paso 2: comprar y asignar licencias](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="ea4e0-129">¿Mis usuarios tienen un directo hacia dentro de marcado de número de teléfono (DID)?</span><span class="sxs-lookup"><span data-stu-id="ea4e0-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="ea4e0-130">Para obtener los números de teléfono, vea [paso 3: obtener los números de teléfono](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="ea4e0-131">Transferir números de teléfono a Office 365</span><span class="sxs-lookup"><span data-stu-id="ea4e0-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="ea4e0-132">Es fácil transferir sus números de teléfono de su proveedor de servicios actual a los equipos.</span><span class="sxs-lookup"><span data-stu-id="ea4e0-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="ea4e0-133">Después de que el puerto sus números de teléfono a los equipos, Microsoft se convertirán en su proveedor de servicios y bill correspondiente a los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="ea4e0-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="ea4e0-134">Para obtener más información, vea [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="ea4e0-135">Números de teléfono y ubicaciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="ea4e0-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="ea4e0-136">Con una llamada a los planes en Office 365, todos los usuarios de su organización necesita tener un único marcado entrante directo (DID) número de teléfono y una dirección de emergencia validada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ea4e0-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="ea4e0-137">También puede especificar una ubicación de emergencia dentro de la dirección de emergencia (por ejemplo, un número de oficina o número de piso).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="ea4e0-138">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ea4e0-138">Ask yourself</span></span>|<span data-ttu-id="ea4e0-139">Acción</span><span class="sxs-lookup"><span data-stu-id="ea4e0-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="ea4e0-140">¿El nivel de detalle quiero la información de dirección y ubicación de emergencia a ser?</span><span class="sxs-lookup"><span data-stu-id="ea4e0-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="ea4e0-141">Para obtener más información, vea [¿Cuáles son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="ea4e0-142">Identidad de llamada</span><span class="sxs-lookup"><span data-stu-id="ea4e0-142">Calling identity</span></span>

<span data-ttu-id="ea4e0-143">De forma predeterminada, todas las llamadas salientes utilizan el número de teléfono asignado como llamada identidad (identificador de autor de la llamada).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="ea4e0-144">El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.</span><span class="sxs-lookup"><span data-stu-id="ea4e0-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="ea4e0-145">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ea4e0-145">Ask yourself</span></span>|<span data-ttu-id="ea4e0-146">Acción</span><span class="sxs-lookup"><span data-stu-id="ea4e0-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="ea4e0-147">¿Desea enmascarar o deshabilitar el identificador de autor de la llamada?</span><span class="sxs-lookup"><span data-stu-id="ea4e0-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="ea4e0-148">Para cambiar o bloquear el identificador de autor de la llamada, vea [establecer el identificador de autor de la llamada de un usuario](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="ea4e0-148">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||




