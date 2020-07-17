---
title: Voz en la nube de Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: Obtenga más información sobre la característica de voz en la nube y comprenda las decisiones de implementación necesarias a las que se enfrentará.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8106e5ef30b71ec82e9b1ae42f785b7a73b170a5
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158648"
---
# <a name="voice---phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="fa5d8-103">Opciones de conectividad RTC y sistema telefónico de voz</span><span class="sxs-lookup"><span data-stu-id="fa5d8-103">Voice - Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="fa5d8-104">Ha completado la [Introducción](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="fa5d8-105">Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="fa5d8-106">Es posible que haya implementado [reuniones & conferencias](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="fa5d8-107">Ahora ya puede agregar capacidades de voz para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-107">Now you're ready to add voice capabilities for your users.</span></span> 

<span data-ttu-id="fa5d8-108">La voz proporciona capacidades de intercambio privado (PBX) y opciones para conectarse a la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-108">Voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="fa5d8-109">Este artículo le ayudará a decidir si necesita cambiar cualquiera de la configuración predeterminada de voz, en función del perfil y los requisitos empresariales de su organización, y luego le guiará por los cambios.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-109">This article helps you decide whether you need to change any of the default voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="fa5d8-110">La configuración se dividirá en dos grupos, empezando por el conjunto básico de [cambios que es más probable que se realicen](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="fa5d8-111">El segundo grupo incluye las [opciones adicionales](#additional-deployment-decisions) que puede que quiera configurar, según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="fa5d8-112">Recomendamos que todas las organizaciones prosigan las decisiones básicas y, a continuación, si su organización tiene requisitos adicionales, revise el siguiente material.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-voice"></a><span data-ttu-id="fa5d8-113">Más información sobre la voz</span><span class="sxs-lookup"><span data-stu-id="fa5d8-113">Learn more about voice</span></span>

<span data-ttu-id="fa5d8-114">Los artículos siguientes proporcionan más información sobre la implementación y el uso de las características de voz en Teams:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-114">The following articles provide more information about deploying and using voice features in Teams:</span></span>

- [<span data-ttu-id="fa5d8-115">Sistema telefónico en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="fa5d8-115">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="fa5d8-116">Sistema telefónico con Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="fa5d8-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="fa5d8-117">Enrutamiento directo del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="fa5d8-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="fa5d8-118">Soluciones de telefonía de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa5d8-118">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="fa5d8-119">Vea la siguiente sesión para obtener más información sobre el sistema telefónico: [Introducción al sistema telefónico en Microsoft Teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="fa5d8-119">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="fa5d8-120">Decisiones de implementación principales</span><span class="sxs-lookup"><span data-stu-id="fa5d8-120">Core deployment decisions</span></span>

<span data-ttu-id="fa5d8-121">Estas son las opciones que la mayoría de organizaciones cambia (si la configuración predeterminada de Teams no sirve para la organización).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-121">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="fa5d8-122">Sistema telefónico (Office 365)</span><span class="sxs-lookup"><span data-stu-id="fa5d8-122">Phone System (Office 365)</span></span>

<span data-ttu-id="fa5d8-123">Sistema telefónico es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de la central de conmutación (PBX) en la nube de Microsoft 365 o de Office 365.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-123">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud.</span></span> <span data-ttu-id="fa5d8-124">El sistema telefónico le permite reemplazar el sistema de central de conmutación (PBX) existente por un conjunto de características que se proporcionan directamente desde Microsoft 365 u Office 365 y están estrechamente integradas en la experiencia de productividad de nube de la empresa.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-124">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Microsoft 365 or Office 365 and tightly integrated into the company's cloud productivity experience.</span></span>


|<span data-ttu-id="fa5d8-125">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-125">Ask yourself</span></span>|<span data-ttu-id="fa5d8-126">Acción</span><span class="sxs-lookup"><span data-stu-id="fa5d8-126">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="fa5d8-127">¿En qué ubicaciones de usuario o oficinas implementaré el sistema telefónico?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-127">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="fa5d8-128">Para obtener más información sobre el sistema telefónico, consulte [Qué es el sistema telefónico en Microsoft 365 u Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-128">For more information about Phone System, see [What is Phone System in Microsoft 365 or Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="fa5d8-129">Conexión a la red de telefonía pública conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="fa5d8-129">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="fa5d8-130">Para conectar el sistema telefónico a la red de telefonía pública conmutada (RTC) para que los usuarios puedan hacer llamadas telefónicas en todo el mundo, tienes opciones basadas en las necesidades de tu empresa.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-130">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="fa5d8-131">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-131">Ask yourself the following:</span></span>


|<span data-ttu-id="fa5d8-132">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-132">Ask yourself</span></span>|<span data-ttu-id="fa5d8-133">Acción</span><span class="sxs-lookup"><span data-stu-id="fa5d8-133">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="fa5d8-134">¿Quiero usar el plan de llamadas de Microsoft como mi operador de telefonía?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-134">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="fa5d8-135">Para obtener más información, consulta [sistema telefónico con planes de llamadas](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-135">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="fa5d8-136">¿Debo usar mi propio operador de telefonía?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-136">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="fa5d8-137">Para obtener más información, consulte [sistema telefónico con enrutamiento directo](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-137">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="fa5d8-138">Decisiones de implementación adicionales</span><span class="sxs-lookup"><span data-stu-id="fa5d8-138">Additional deployment decisions</span></span>

<span data-ttu-id="fa5d8-139">Es posible que desee cambiar la configuración de lo siguiente, en función de las necesidades y la configuración de su organización:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-139">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="fa5d8-140">Correo de voz</span><span class="sxs-lookup"><span data-stu-id="fa5d8-140">Voicemail</span></span>
- <span data-ttu-id="fa5d8-141">Identidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="fa5d8-141">Calling identity</span></span>
- <span data-ttu-id="fa5d8-142">Números de teléfono de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa5d8-142">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="fa5d8-143">Planes de marcado</span><span class="sxs-lookup"><span data-stu-id="fa5d8-143">Dial plans</span></span>
- <span data-ttu-id="fa5d8-144">Colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="fa5d8-144">Call queues</span></span>
- <span data-ttu-id="fa5d8-145">Operadores automáticos</span><span class="sxs-lookup"><span data-stu-id="fa5d8-145">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="fa5d8-146">Correo de voz</span><span class="sxs-lookup"><span data-stu-id="fa5d8-146">Voicemail</span></span>

<span data-ttu-id="fa5d8-147">El buzón de voz de nube, basado en los servicios de buzón de voz de Azure, admite depósitos de buzón de voz solo y no admite sistemas de correo electrónico de terceros.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-147">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn't support third-party email systems.</span></span> <span data-ttu-id="fa5d8-148">El buzón de voz de nube incluye la transcripción del buzón de voz, que está habilitada para todos los usuarios de su organización de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-148">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="fa5d8-149">Las necesidades de su empresa pueden requerir que deshabilite la transcripción del buzón de voz para usuarios específicos o para todos los miembros de la organización.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-149">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="fa5d8-150">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-150">Ask yourself</span></span>|<span data-ttu-id="fa5d8-151">Acción</span><span class="sxs-lookup"><span data-stu-id="fa5d8-151">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="fa5d8-152">¿Quiero habilitar el buzón de voz de nube?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-152">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="fa5d8-153">Para los procedimientos de configuración de buzón de voz, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-153">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="fa5d8-154">¿Quiero habilitar la transcripción del buzón de voz para algunos o todos los usuarios?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-154">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="fa5d8-155">Para desactivar la transcripción del buzón de voz, consulte [configurar directivas de buzón de voz en su organización](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-155">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="fa5d8-156">Identidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="fa5d8-156">Calling identity</span></span>

<span data-ttu-id="fa5d8-157">De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificación de llamada).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-157">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="fa5d8-158">El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-158">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="fa5d8-159">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-159">Ask yourself</span></span>|<span data-ttu-id="fa5d8-160">Acción</span><span class="sxs-lookup"><span data-stu-id="fa5d8-160">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="fa5d8-161">¿Quiero enmascarar o deshabilitar la identificación de llamadas?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-161">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="fa5d8-162">Para cambiar o bloquear la identificación de llamadas, vea [establecer la identificación de llamadas de un usuario](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-162">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="fa5d8-163">Números de teléfono de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa5d8-163">Phone numbers from Microsoft</span></span>

<span data-ttu-id="fa5d8-164">Microsoft tiene dos tipos de números telefónicos disponibles: números de *suscriptor* (usuario), que se pueden asignar a los usuarios de su organización, y números de *servicio* , disponibles como números de servicio de pago y gratuitos, que tienen mayor capacidad de llamadas simultáneas que los números de suscriptor y que se pueden asignar a servicios como audioconferencias, operadores automáticos o colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-164">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="fa5d8-165">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-165">Ask yourself</span></span>|<span data-ttu-id="fa5d8-166">Acción</span><span class="sxs-lookup"><span data-stu-id="fa5d8-166">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="fa5d8-167">¿Qué ubicaciones de usuario necesitan números de teléfono nuevos de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-167">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="fa5d8-168">Para obtener información sobre cómo obtener números de teléfono, vea [administrar números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) y [obtener números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-168">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="fa5d8-169">¿Qué tipo de número de teléfono (suscriptor o servicio) necesito?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-169">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="fa5d8-170">Para elegir el tipo de número de teléfono que necesita, vea [diferentes tipos de números de teléfono para los planes de llamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-170">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="fa5d8-171">¿Cómo Porto números de teléfono existentes a teams?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-171">How do I port existing phone numbers to Teams?</span></span>|<span data-ttu-id="fa5d8-172">Para obtener más información, consulte [transferir números de teléfono a Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-172">For more information, see [Transfer phone numbers to Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="fa5d8-173">Planes de marcado</span><span class="sxs-lookup"><span data-stu-id="fa5d8-173">Dial plans</span></span>

<span data-ttu-id="fa5d8-174">Un plan de marcado de la característica del sistema telefónico de Microsoft 365 u Office 365 es un conjunto de reglas de normalización que traducen números de teléfono marcados a un formato alternativo (por lo general, formato E. 164) para la autorización de llamadas y el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-174">A dial plan in the Phone System feature of Microsoft 365 or Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="fa5d8-175">Para obtener más información acerca de los planes de marcado, vea [¿Qué son los planes de marcado?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-175">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="fa5d8-176">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-176">Ask yourself</span></span>|<span data-ttu-id="fa5d8-177">Acción</span><span class="sxs-lookup"><span data-stu-id="fa5d8-177">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="fa5d8-178">¿Mi organización necesita un plan de marcado personalizado?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-178">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="fa5d8-179">Para determinar si necesita un plan de marcado personalizado, consulte [planear planes de marcado de inquilino](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="fa5d8-179">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="fa5d8-180">¿Qué usuarios necesitan un plan de marcado personalizado y qué plan de marcado del espacio empresarial se va a asignar a cada usuario?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-180">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="fa5d8-181">Para agregar usuarios a un plan de marcado personalizado en PowerShell, vea [crear y administrar planes de marcado](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-181">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="fa5d8-182">Colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="fa5d8-182">Call queues</span></span>

<span data-ttu-id="fa5d8-183">Las colas de llamadas en nube incluyen saludos que se usan cuando un usuario llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la posibilidad de buscar el siguiente agente de llamada disponible para controlar la llamada mientras las personas que llaman escuchan música en espera.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-183">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="fa5d8-184">Puede crear una o varias colas de llamadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-184">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="fa5d8-185">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-185">Ask yourself</span></span>|<span data-ttu-id="fa5d8-186">Acción</span><span class="sxs-lookup"><span data-stu-id="fa5d8-186">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="fa5d8-187">¿Mi organización necesita colas de llamadas?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-187">Does my organization need call queues?</span></span> | <span data-ttu-id="fa5d8-188">Para obtener más información, consulte [crear una cola de llamadas en la nube](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) y [configurar el sistema telefónico](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-188">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="fa5d8-189">Operadores automáticos</span><span class="sxs-lookup"><span data-stu-id="fa5d8-189">Auto attendants</span></span>

<span data-ttu-id="fa5d8-190">Los operadores automáticos de la nube se pueden usar para crear un sistema de menús para la organización que permita a los autores de llamadas externos e internos desplazarse por un sistema de menús para ubicar y realizar llamadas a usuarios o departamentos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="fa5d8-190">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="fa5d8-191">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-191">Ask yourself</span></span>|<span data-ttu-id="fa5d8-192">Acción</span><span class="sxs-lookup"><span data-stu-id="fa5d8-192">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="fa5d8-193">¿Mi organización necesita operadores automáticos?</span><span class="sxs-lookup"><span data-stu-id="fa5d8-193">Does my organization need auto attendants?</span></span> | <span data-ttu-id="fa5d8-194">Para obtener más información, vea [Qué son los operadores automáticos de la nube](what-are-phone-system-auto-attendants.md) y [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="fa5d8-194">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="fa5d8-195">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="fa5d8-195">Devices</span></span>

<span data-ttu-id="fa5d8-196">Para obtener más información sobre los dispositivos compatibles, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa5d8-196">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="fa5d8-197">Administrar sus dispositivos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa5d8-197">Manage your devices in Microsoft Teams</span></span>](devices/device-management.md)
- [<span data-ttu-id="fa5d8-198">Teléfonos IP</span><span class="sxs-lookup"><span data-stu-id="fa5d8-198">IP Phones</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="fa5d8-199">Dispositivos de audio y vídeo USB</span><span class="sxs-lookup"><span data-stu-id="fa5d8-199">USB audio and video devices</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="fa5d8-200">Comunicaciones inteligentes para dispositivos</span><span class="sxs-lookup"><span data-stu-id="fa5d8-200">Intelligent communications for devices</span></span>](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


