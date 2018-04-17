---
title: Implementar voz en la nube
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/10/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Guía práctica para implementar características de voz en la nube en Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4828cb7c27c53387e0efae800167cef1b53dd4b6
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="13ccf-103">Implementar voz en la nube</span><span class="sxs-lookup"><span data-stu-id="13ccf-103">Cloud voice deployment</span></span>

<span data-ttu-id="13ccf-104">Teams de Microsoft, el concentrador para el trabajo en equipo y comunicaciones en Office 365, ahora ofrece conferencias de Audio y sistema de teléfono llamando a los planes de capacidades para satisfacer los requerimientos empresariales adicionales extendiendo la reunión de equipos y llamar la experiencia para incluir partes externas que se conectan a través de la red telefónica pública conmutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="13ccf-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>
 
<span data-ttu-id="13ccf-105">Esta página se irá actualizando conforme se vayan publicando características de voz en la nube adicionales en Teams.</span><span class="sxs-lookup"><span data-stu-id="13ccf-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="13ccf-106">Audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13ccf-106">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="13ccf-107">Audioconferencia en Office 365 permite a los participantes unirse a las reuniones desde cualquier teléfono.</span><span class="sxs-lookup"><span data-stu-id="13ccf-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="13ccf-108">Esto es lo que conseguirá con [Audioconferencia](https://go.microsoft.com/fwlink/?linkid=858992) en Office 365.</span><span class="sxs-lookup"><span data-stu-id="13ccf-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="13ccf-109">Sistema telefónico con planes de llamada en los equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="13ccf-109">Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="13ccf-110">Sistema telefónico es una funcionalidad de Office 365 que permite administrar el enrutamiento de llamadas, las directivas y el aprovisionamiento de usuarios.</span><span class="sxs-lookup"><span data-stu-id="13ccf-110">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="13ccf-111">Aquí se incluye el sistema de administración de llamadas, el enrutamiento de llamadas y el control de llamadas.</span><span class="sxs-lookup"><span data-stu-id="13ccf-111">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="13ccf-112">Planes de llamada de Office 365 es un servicio complementario para la función Sistema telefónico que se proporciona a través de Microsoft Teams y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="13ccf-112">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="13ccf-113">Planes de llamada proporcionan el número de las personas de su empresa con un teléfono principal y les permite hacer y recibir llamadas de teléfono fuera de la organización sobre la RTC.</span><span class="sxs-lookup"><span data-stu-id="13ccf-113">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="13ccf-114">Para obtener más información, consulte [Esto es lo que conseguirá con Sistema telefónico en Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) y [¿Qué son los Planes de llamada en Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span><span class="sxs-lookup"><span data-stu-id="13ccf-114">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>


## <a name="practical-guidance-for-audio-conferencing-and-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="13ccf-115">Guía práctica para conferencias de Audio y sistema de teléfono con llamar a planes de Teams de Microsoft</span><span class="sxs-lookup"><span data-stu-id="13ccf-115">Practical guidance for Audio Conferencing and Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="13ccf-116">Esta práctica guía está organizada mediante el marco de viaje de cliente de Office 365 FastTrack y sus tres fases&mdash;Envision, a bordo y el valor de la unidad.</span><span class="sxs-lookup"><span data-stu-id="13ccf-116">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="13ccf-117">Que está diseñada para ayudarle a planear, entregar y operar una exitosa conferencia de Audio o sistema de teléfono con una llamada a los planes de implementación.</span><span class="sxs-lookup"><span data-stu-id="13ccf-117">It's intended to help you plan, deliver, and operate a successful Audio Conferencing or Phone System with Calling Plans implementation.</span></span>

|<span data-ttu-id="13ccf-118">Enfoque</span><span class="sxs-lookup"><span data-stu-id="13ccf-118">Envision</span></span>  |<span data-ttu-id="13ccf-119">Incorporación</span><span class="sxs-lookup"><span data-stu-id="13ccf-119">Onboard</span></span>  |<span data-ttu-id="13ccf-120">Nuevos valores</span><span class="sxs-lookup"><span data-stu-id="13ccf-120">Drive Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="13ccf-121">Definir mi éxito</span><span class="sxs-lookup"><span data-stu-id="13ccf-121">Define my success</span></span> <br> <span data-ttu-id="13ccf-122">Tomar decisiones de mi servicio</span><span class="sxs-lookup"><span data-stu-id="13ccf-122">Make my service decisions</span></span> <br> <span data-ttu-id="13ccf-123">Evaluar mi entorno</span><span class="sxs-lookup"><span data-stu-id="13ccf-123">Evaluate my environment</span></span> <br> <span data-ttu-id="13ccf-124">Plan de administración del servicio</span><span class="sxs-lookup"><span data-stu-id="13ccf-124">Plan my service management</span></span> <br> <span data-ttu-id="13ccf-125">Planear la experiencia de los usuarios</span><span class="sxs-lookup"><span data-stu-id="13ccf-125">Plan my users' experience</span></span> <br> <span data-ttu-id="13ccf-126">Documentar el plan de éxito</span><span class="sxs-lookup"><span data-stu-id="13ccf-126">Document my success plan</span></span>    | <span data-ttu-id="13ccf-127">Preparar mi servicio</span><span class="sxs-lookup"><span data-stu-id="13ccf-127">Prepare my service</span></span> <br> <span data-ttu-id="13ccf-128">Preparar Mis usuarios</span><span class="sxs-lookup"><span data-stu-id="13ccf-128">Prepare my users</span></span> <br> <span data-ttu-id="13ccf-129">Implementar mi servicio</span><span class="sxs-lookup"><span data-stu-id="13ccf-129">Deploy my service</span></span>  <br> <br> <br> <br>     | <span data-ttu-id="13ccf-130">Operar mi servicio</span><span class="sxs-lookup"><span data-stu-id="13ccf-130">Operate my service</span></span> <br> <span data-ttu-id="13ccf-131">Mejorar mi servicio</span><span class="sxs-lookup"><span data-stu-id="13ccf-131">Enhance my service</span></span> <br> <br> <br> <br> <br>      |

<span data-ttu-id="13ccf-132">El contenido se presenta de forma ordenada y está diseñado para guiarle a través de un viaje de implementación end-to-end de principio a fin.</span><span class="sxs-lookup"><span data-stu-id="13ccf-132">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="13ccf-133">Si está implementando ya activamente, aún le animamos a hacer referencia a las áreas de contenido aplicables.</span><span class="sxs-lookup"><span data-stu-id="13ccf-133">If you're already actively deploying, we still encourage you to reference the applicable content areas.</span></span>



> [!TIP]
> <span data-ttu-id="13ccf-134">En esta práctica guía, continuamos ofreciendo un ejemplo que se genera para cada actividad y la clave de la conversación.</span><span class="sxs-lookup"><span data-stu-id="13ccf-134">In this practical guidance, we're providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="13ccf-135">Los ejemplos en este documento se incluyen dentro de llamadas de punta, y sirven como una plantilla que se puede reutilizar.</span><span class="sxs-lookup"><span data-stu-id="13ccf-135">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="13ccf-136">La frase "Por añadir" indica que falta por completar con información como parte del proceso de planificación.</span><span class="sxs-lookup"><span data-stu-id="13ccf-136">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>