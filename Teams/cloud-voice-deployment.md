---
title: Implementar voz en la nube
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: MyAdvisor
description: Guía práctica para implementar características de voz en la nube en Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6d8057fa2cba1f14ed00eebebdb522144eb283d
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458919"
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="4f9fc-103">Implementar voz en la nube</span><span class="sxs-lookup"><span data-stu-id="4f9fc-103">Cloud voice deployment</span></span>

<span data-ttu-id="4f9fc-104">Microsoft Teams, el concentrador de trabajo en equipo y comunicaciones en Office 365, ahora proporciona conferencias de Audio, el sistema telefónico con planes de llamada, y sistema telefónico directa capacidades de enrutamiento para cumplir los requisitos de negocio adicionales mediante la ampliación de la reunión de los equipos y experiencia de llamada para incluir usuarios externos conectados a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="4f9fc-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing, Phone System with Calling Plans, and Phone System Direct Routing capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>


> [!Tip] 
> <span data-ttu-id="4f9fc-105">Vea la sesión siguiente para obtener una introducción a los sistemas de telefonía: [Introducción al sistema de teléfono en los equipos de Microsoft](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="4f9fc-105">Watch the following session for an introduction to Phone Systems: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>
 
<span data-ttu-id="4f9fc-106">Actualizaremos esta página se lanzan las características de voz adicionales en la nube para los equipos a través del tiempo.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-106">We’ll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="4f9fc-107">Audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f9fc-107">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="4f9fc-108">Audioconferencia en Office 365 permite a los participantes unirse a las reuniones desde cualquier teléfono.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-108">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="4f9fc-109">Aquí es lo que se obtiene con las [Conferencias de Audio](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) en Office 365.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-109">Here’s what you get with [Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a><span data-ttu-id="4f9fc-110">Sistema telefónico al llamar a planes ("planes de llamada") en los equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4f9fc-110">Phone System with Calling Plans (“Calling Plans”) in Microsoft Teams</span></span>

<span data-ttu-id="4f9fc-111">Sistema telefónico es una funcionalidad de Office 365 que permite administrar el enrutamiento de llamadas, las directivas y el aprovisionamiento de usuarios.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-111">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="4f9fc-112">Aquí se incluye el sistema de administración de llamadas, el enrutamiento de llamadas y el control de llamadas.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-112">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="4f9fc-113">Planes de llamada es un servicio de complemento para la característica de sistema telefónico entregada a través de los equipos y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-113">Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="4f9fc-114">Planes de llamada requiere que el usuario en cuestión se hospedados en Skype para empresarial en línea para que funcionen en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-114">Calling Plans requires that the user in question be homed in Skype for Business Online to work in Microsoft Teams.</span></span> <span data-ttu-id="4f9fc-115">Planes de llamada proporcionan las personas de su empresa con un número de teléfono principal y les permite realizar y recibir llamadas de teléfono externos a su organización a través de la RTC.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-115">Calling Plans provide the people in your business with a primary phone number, and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="4f9fc-116">Para obtener más información, lea [aquí es lo que obtiene con el sistema telefónico en Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) y [¿Cuáles son los planes de llamada en Office 365?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="4f9fc-116">To learn more, read [Here’s what you get with Phone System in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) and [What are Calling Plans in Office 365?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)</span></span>


## <a name="phone-system-direct-routing-direct-routing"></a><span data-ttu-id="4f9fc-117">Sistema de teléfono directo enrutamiento ("enrutamiento directo")</span><span class="sxs-lookup"><span data-stu-id="4f9fc-117">Phone System Direct Routing (“Direct Routing”)</span></span>

<span data-ttu-id="4f9fc-118">Works de enrutamiento directas con la característica de sistema telefónico para dar a las personas de su organización la capacidad de realizar y recibir llamadas de teléfono fuera de la organización a través de la RTC, donde se proporciona conectividad RTC a través de los proveedores de servicios de terceros.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-118">Direct Routing works with the Phone System feature to give people in your organization the ability make and receive phone calls outside of the organization over the PSTN, where PSTN connectivity is provided via third-party service providers.</span></span>

<span data-ttu-id="4f9fc-119">Para obtener más información, lea la [Planeación de enrutamiento directo](direct-routing-plan.md) y [Configurar el enrutamiento directo](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="4f9fc-119">To learn more, read [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a><span data-ttu-id="4f9fc-120">Guía práctica para conferencias de Audio, planes de llamada y el enrutamiento directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f9fc-120">Practical guidance for Audio Conferencing, Calling Plans, and Direct Routing in Microsoft Teams</span></span>

<span data-ttu-id="4f9fc-121">Esta orientación práctica se organiza mediante el marco de viaje de atención al cliente de Office 365 FastTrack y sus tres fases&mdash;previsión, incorporación y el valor de unidad.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-121">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="4f9fc-122">Que está diseñada para ayudarle a planear, entregar y trabajar con una implementación correcta de conferencias de Audio, planes de llamada o enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-122">It’s intended to help you plan, deliver, and operate a successful Audio Conferencing, Calling Plans, or Direct Routing implementation.</span></span>

> [!div class="mx-tableFixed"]
> |<span data-ttu-id="4f9fc-123">Enfoque</span><span class="sxs-lookup"><span data-stu-id="4f9fc-123">Envision</span></span>  |<span data-ttu-id="4f9fc-124">Incorporación</span><span class="sxs-lookup"><span data-stu-id="4f9fc-124">Onboard</span></span>  |<span data-ttu-id="4f9fc-125">Nuevos valores</span><span class="sxs-lookup"><span data-stu-id="4f9fc-125">Drive Value</span></span>  |
> |---------|---------|---------|
> |[<span data-ttu-id="4f9fc-126">Definir mi éxito</span><span class="sxs-lookup"><span data-stu-id="4f9fc-126">Define my success</span></span>](1-envision-define-my-success-cloud-voice.md) <br> <span data-ttu-id="4f9fc-127">Mi las decisiones de servicio</span><span class="sxs-lookup"><span data-stu-id="4f9fc-127">Make my service decisions for</span></span> <br><span data-ttu-id="4f9fc-128">&nbsp;&nbsp;[Conferencias de audio](2-envision-make-my-service-decisions-audio-conferencing.md),</span><span class="sxs-lookup"><span data-stu-id="4f9fc-128">&nbsp;&nbsp;[Audio Conferencing](2-envision-make-my-service-decisions-audio-conferencing.md),</span></span><br><span data-ttu-id="4f9fc-129">&nbsp;&nbsp;[Planes de llamada](2-envision-make-my-service-decisions-phone-system.md)o [directa de enrutamiento](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="4f9fc-129">&nbsp;&nbsp;[Calling Plans](2-envision-make-my-service-decisions-phone-system.md), or [Direct Routing](2-envision-make-my-service-decisions-direct-routing.md)</span></span> <br> [<span data-ttu-id="4f9fc-130">Evaluar mi entorno</span><span class="sxs-lookup"><span data-stu-id="4f9fc-130">Evaluate my environment</span></span>](3-envision-evaluate-my-environment.md) <br> [<span data-ttu-id="4f9fc-131">Planeación de la administración del servicio de mi</span><span class="sxs-lookup"><span data-stu-id="4f9fc-131">Plan my service management</span></span>](4-envision-plan-my-service-management.md) <br> [<span data-ttu-id="4f9fc-132">Planeación de la experiencia de mi los usuarios</span><span class="sxs-lookup"><span data-stu-id="4f9fc-132">Plan my users’ experience</span></span>](5-envision-plan-my-users-experience.md) <br> [<span data-ttu-id="4f9fc-133">Mi plan de éxito de documentos</span><span class="sxs-lookup"><span data-stu-id="4f9fc-133">Document my success plan</span></span>](6-envision-document-my-success-plan.md)    | [<span data-ttu-id="4f9fc-134">Preparar mi servicio</span><span class="sxs-lookup"><span data-stu-id="4f9fc-134">Prepare my service</span></span>](1-onboard-prepare-my-service.md) <br> [<span data-ttu-id="4f9fc-135">Preparación de Mis usuarios</span><span class="sxs-lookup"><span data-stu-id="4f9fc-135">Prepare my users</span></span>](2-onboard-prepare-my-users.md) <br> [<span data-ttu-id="4f9fc-136">Implementar el servicio de mi</span><span class="sxs-lookup"><span data-stu-id="4f9fc-136">Deploy my service</span></span>](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [<span data-ttu-id="4f9fc-137">Usar mi servicio</span><span class="sxs-lookup"><span data-stu-id="4f9fc-137">Operate my service</span></span>](1-drive-value-operate-my-service.md) <br> [<span data-ttu-id="4f9fc-138">Mejorar mi servicio</span><span class="sxs-lookup"><span data-stu-id="4f9fc-138">Enhance my service</span></span>](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

<span data-ttu-id="4f9fc-139">El contenido se presenta en forma ordenada y está diseñado para guiarle a través de un viaje de implementación de extremo a extremo de principio a fin.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-139">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="4f9fc-140">Si va a implementar ya activamente, aún le animamos a hacer referencia a las áreas de contenido aplicables.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-140">If you’re already actively deploying, we still encourage you to reference the applicable content areas.</span></span>


> [!TIP]
> <span data-ttu-id="4f9fc-141">En esta guía práctica, proporcionamos da como resultado de ejemplo para cada actividad y la clave de la conversación.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-141">In this practical guidance, we provide example outputs for each activity and key discussion.</span></span> <span data-ttu-id="4f9fc-142">Los ejemplos a lo largo de este documento se incluyen dentro de las llamadas de sugerencia, y sirven como una plantilla que se puede volver a utilizar.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-142">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="4f9fc-143">Verá "TBA" (que se va a agregar) para obtener información que necesita para llevar a cabo como parte de su proceso de planeación.</span><span class="sxs-lookup"><span data-stu-id="4f9fc-143">You’ll see “TBA” (to be added) for information that you need to complete as part of your planning process.</span></span>
