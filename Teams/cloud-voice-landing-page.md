---
title: Voz en la nube de Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Página de inicio a la implementación de voz en la nube en los equipos
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47c534eba93c6f5af21a75fa20b5015fac00c674
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914615"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="bb6a0-103">Voz en la nube de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bb6a0-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="bb6a0-104">Ha completado la [Introducción](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="bb6a0-105">Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="bb6a0-106">Es posible que haya implementado [conferencia & de las reuniones](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="bb6a0-107">Ahora está listo para agregar funciones de voz en la nube para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="bb6a0-108">En la nube voz proporciona capacidades de conmutación (PBX) y opciones para la conexión a la red telefónica pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="bb6a0-109">En este artículo le ayudará a decidir si necesita cambiar cualquiera de las opciones de voz de forma predeterminada en la nube, según el perfil de su organización y los requisitos empresariales, a continuación, le guiará a través de cada cambio.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="bb6a0-110">Nos hemos dividir en dos grupos, empezando con el conjunto principal de [los cambios que es más probable que realizar](#core-deployment-decisions)la configuración.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="bb6a0-111">El segundo grupo incluye las [opciones adicionales](#additional-deployment-decisions) que puede que quiera configurar, según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="bb6a0-112">Se recomienda que todas las organizaciones funcionan a través de las decisiones principales y, a continuación, si su organización tiene requisitos adicionales, revisión la siguiente (en inglés).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="bb6a0-113">Encontrará más información acerca de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="bb6a0-113">Learn more about cloud voice</span></span>

<span data-ttu-id="bb6a0-114">Los artículos siguientes proporcionan más información sobre la implementación y uso de las características de voz de la nube en los equipos:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="bb6a0-115">Sistema telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="bb6a0-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="bb6a0-116">Sistema telefónico con planes de llamada</span><span class="sxs-lookup"><span data-stu-id="bb6a0-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="bb6a0-117">Enrutamiento directo del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="bb6a0-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="bb6a0-118">Implementación de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="bb6a0-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="bb6a0-119">Soluciones de telefonía de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bb6a0-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="bb6a0-120">Vea la sesión siguiente para obtener más información sobre el sistema telefónico: [Introducción al sistema de teléfono en los equipos de Microsoft](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="bb6a0-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="bb6a0-121">Decisiones de implementación principales</span><span class="sxs-lookup"><span data-stu-id="bb6a0-121">Core deployment decisions</span></span>

<span data-ttu-id="bb6a0-122">Estas son las opciones que la mayoría de organizaciones cambia (si la configuración predeterminada de Teams no sirve para la organización).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="bb6a0-123">Sistema telefónico (Office 365)</span><span class="sxs-lookup"><span data-stu-id="bb6a0-123">Phone System (Office 365)</span></span>

<span data-ttu-id="bb6a0-124">Sistema telefónico es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de conmutación (PBX) en la nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="bb6a0-125">Sistema telefónico permite reemplazar el sistema de conmutación (PBX) existente con un conjunto de características que se entregan directamente desde Office 365 y estrechamente integrados en la experiencia de productividad de la compañía en la nube.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="bb6a0-126">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-126">Ask yourself</span></span>|<span data-ttu-id="bb6a0-127">Acción</span><span class="sxs-lookup"><span data-stu-id="bb6a0-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="bb6a0-128">¿En qué oficinas o ubicaciones de usuario se implementar sistema telefónico?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="bb6a0-129">Para obtener más información acerca del sistema de teléfono, vea [¿Qué es el sistema telefónico en Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="bb6a0-130">Conexión pública conmutada red telefónica (RTC)</span><span class="sxs-lookup"><span data-stu-id="bb6a0-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="bb6a0-131">Para conectar el sistema telefónico a la red telefónica pública conmutada (RTC) para que los usuarios pueden realizar llamadas telefónicas todo el mundo, dispone de opciones en función de sus necesidades empresariales.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="bb6a0-132">Hágase lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-132">Ask yourself the following:</span></span>


|<span data-ttu-id="bb6a0-133">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-133">Ask yourself</span></span>|<span data-ttu-id="bb6a0-134">Acción</span><span class="sxs-lookup"><span data-stu-id="bb6a0-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="bb6a0-135">¿Desea que se utilizará al llamar a planeación de Microsoft como mi portadora de telefonía?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="bb6a0-136">Para obtener más información, vea [Sistema de teléfono con planes de llamada](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="bb6a0-137">¿Es necesario usar mi propia portadora de telefonía?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="bb6a0-138">Para obtener más información, vea [Sistema de teléfono con el enrutamiento directo](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="bb6a0-139">Decisiones de implementación adicionales</span><span class="sxs-lookup"><span data-stu-id="bb6a0-139">Additional deployment decisions</span></span>

<span data-ttu-id="bb6a0-140">Es posible que desee cambiar la configuración de los siguientes valores, en función de las necesidades de su organización y la configuración:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="bb6a0-141">Correo de voz</span><span class="sxs-lookup"><span data-stu-id="bb6a0-141">Voicemail</span></span>
- <span data-ttu-id="bb6a0-142">Identidad de llamada</span><span class="sxs-lookup"><span data-stu-id="bb6a0-142">Calling identity</span></span>
- <span data-ttu-id="bb6a0-143">Números de teléfono de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bb6a0-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="bb6a0-144">Planes de marcado</span><span class="sxs-lookup"><span data-stu-id="bb6a0-144">Dial plans</span></span>
- <span data-ttu-id="bb6a0-145">Colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="bb6a0-145">Call queues</span></span>
- <span data-ttu-id="bb6a0-146">Operadores automáticos</span><span class="sxs-lookup"><span data-stu-id="bb6a0-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="bb6a0-147">Correo de voz</span><span class="sxs-lookup"><span data-stu-id="bb6a0-147">Voicemail</span></span>

<span data-ttu-id="bb6a0-148">Correo de voz en la nube, con tecnología de servicios de correo de voz de Azure, es compatible con depósitos de correo de voz a los buzones de Exchange y no es compatible con sistemas de correo electrónico de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="bb6a0-149">Correo de voz en la nube incluye transcripción de correo de voz, que está habilitado para todos los usuarios de la organización de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="bb6a0-150">Las necesidades de negocio pueden requerir que deshabilite la transcripción de correo de voz para usuarios específicos o todos los usuarios en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="bb6a0-151">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-151">Ask yourself</span></span>|<span data-ttu-id="bb6a0-152">Acción</span><span class="sxs-lookup"><span data-stu-id="bb6a0-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bb6a0-153">¿Desea habilitar el correo de voz en la nube?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="bb6a0-154">Para los procedimientos de configuración de correo de voz, vea [Configurar el correo de voz en la nube](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="bb6a0-155">¿Desea habilitar la transcripción de correo de voz para todos o algunos de Mis usuarios?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="bb6a0-156">Para desactivar la transcripción de correo de voz, consulte [configuración de directivas de correo de voz en su organización](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="bb6a0-157">Identidad de llamada</span><span class="sxs-lookup"><span data-stu-id="bb6a0-157">Calling identity</span></span>

<span data-ttu-id="bb6a0-158">De forma predeterminada, todas las llamadas salientes utilizan el número de teléfono asignado como llamada identidad (identificador de autor de la llamada).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="bb6a0-159">El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="bb6a0-160">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-160">Ask yourself</span></span>|<span data-ttu-id="bb6a0-161">Acción</span><span class="sxs-lookup"><span data-stu-id="bb6a0-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="bb6a0-162">¿Desea enmascarar o deshabilitar el identificador de autor de la llamada?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="bb6a0-163">Para cambiar o bloquear el identificador de autor de la llamada, vea [establecer el identificador de autor de la llamada de un usuario](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-163">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="bb6a0-164">Números de teléfono de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bb6a0-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="bb6a0-165">Microsoft tiene dos tipos de números de teléfono disponibles: números de *suscriptor* (usuario), que se pueden asignar a los usuarios de su organización y números de *servicio* , disponibles como números de pago y los números de un servicio gratuito, que tienen mayor llamadas simultáneas capacidad de números de suscriptor y se pueden asignar a servicios, como conferencias de Audio, operadores automáticos o colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="bb6a0-166">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-166">Ask yourself</span></span>|<span data-ttu-id="bb6a0-167">Acción</span><span class="sxs-lookup"><span data-stu-id="bb6a0-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="bb6a0-168">¿Qué ubicaciones de usuario necesitan nuevos números de teléfono de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="bb6a0-169">Para obtener información acerca de cómo obtener los números de teléfono, vea [administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) y [los números de teléfono de introducción para los usuarios](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span> 
| <span data-ttu-id="bb6a0-170">¿Qué tipo de número de teléfono (suscriptor o servicio) es necesario?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="bb6a0-171">Para ayudarle a elegir el tipo de número de teléfono que necesita, vea [distintos tipos de números de teléfono utilizados para llamar a los planes](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="bb6a0-172">¿Cómo puerto existente los números de teléfono a Office 365?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="bb6a0-173">Para obtener más información, vea [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="bb6a0-174">Planes de marcado</span><span class="sxs-lookup"><span data-stu-id="bb6a0-174">Dial plans</span></span>

<span data-ttu-id="bb6a0-175">Un plan de marcado de la característica de sistema telefónico de Office 365 es un conjunto de reglas de normalización que traducir marca números de teléfono en un formato alternativo (normalmente, el formato E.164) para la autorización de llamadas y el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="bb6a0-176">Para obtener más información acerca de los planes de marcado, vea [¿Qué son los planes de marcado?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="bb6a0-177">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-177">Ask yourself</span></span>|<span data-ttu-id="bb6a0-178">Acción</span><span class="sxs-lookup"><span data-stu-id="bb6a0-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bb6a0-179">¿Mi organización necesita un plan de marcado personalizado?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="bb6a0-180">Para ayudar a determinar si necesita un plan de marcado personalizado, consulte [Planning for inquilino planes de marcado](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="bb6a0-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="bb6a0-181">¿Qué usuarios necesitan un plan de marcado personalizado y qué plan de marcado del espacio empresarial se va a asignar a cada usuario?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="bb6a0-182">Para agregar usuarios a un plan de marcado personalizado en PowerShell, vea [crear y administrar planes de marcado](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="bb6a0-183">Colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="bb6a0-183">Call queues</span></span>

<span data-ttu-id="bb6a0-184">Colas de llamada de nube incluyen el saludo que se usa cuando alguien llama a un número de teléfono para su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de búsqueda para el siguiente agente de llamada disponibles controlar la llamada mientras las personas que son de llamada escucha música en espera.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-184">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="bb6a0-185">Puede crear una o varias colas de llamadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="bb6a0-186">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-186">Ask yourself</span></span>|<span data-ttu-id="bb6a0-187">Acción</span><span class="sxs-lookup"><span data-stu-id="bb6a0-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bb6a0-188">¿Mi organización necesitan llamar a colas?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-188">Does my organization need call queues?</span></span> | <span data-ttu-id="bb6a0-189">Para obtener más información, vea [crear una cola de llamada en la nube](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) y la [Configuración del sistema de teléfono](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="bb6a0-190">Operadores automáticos</span><span class="sxs-lookup"><span data-stu-id="bb6a0-190">Auto attendants</span></span>

<span data-ttu-id="bb6a0-191">Operadores automáticos en la nube se pueden usar para crear un sistema de menús para la organización que permite externo y mover los autores de llamadas internas a través de un sistema de menús para localizar y colocar o transferir las llamadas a los usuarios de la compañía o los departamentos de la organización.</span><span class="sxs-lookup"><span data-stu-id="bb6a0-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="bb6a0-192">Pregúntese lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-192">Ask yourself</span></span>|<span data-ttu-id="bb6a0-193">Acción</span><span class="sxs-lookup"><span data-stu-id="bb6a0-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bb6a0-194">¿Necesita mi organización automáticos?</span><span class="sxs-lookup"><span data-stu-id="bb6a0-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="bb6a0-195">Para obtener más información, vea [¿Cuáles son los operadores automáticos de la nube](what-are-phone-system-auto-attendants.md) y [configurar un operador automático de la nube](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="bb6a0-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> |

### <a name="devices"></a><span data-ttu-id="bb6a0-196">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="bb6a0-196">Devices</span></span>

<span data-ttu-id="bb6a0-197">Para obtener más información sobre los dispositivos admitidos, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb6a0-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="bb6a0-198">Administrar sus dispositivos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bb6a0-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="bb6a0-199">Teléfonos IP</span><span class="sxs-lookup"><span data-stu-id="bb6a0-199">IP Phones</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="bb6a0-200">Dispositivos de audio y vídeo USB</span><span class="sxs-lookup"><span data-stu-id="bb6a0-200">USB audio and video devices</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="bb6a0-201">Comunicaciones inteligentes para dispositivos</span><span class="sxs-lookup"><span data-stu-id="bb6a0-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


