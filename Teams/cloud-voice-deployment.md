---
title: Implementar voz en la nube
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 12/13/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Guía práctica para implementar características de voz en la nube en Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45528d71dc04b96d77b454d5db402648779c1ac9
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
#<a name="cloud-voice-deployment"></a><span data-ttu-id="d5fa1-103">Implementar voz en la nube</span><span class="sxs-lookup"><span data-stu-id="d5fa1-103">Cloud voice deployment</span></span>

<span data-ttu-id="d5fa1-104">Microsoft Teams, el centro de trabajo en equipo y comunicaciones de Office 365, proporciona ahora funcionalidades de audioconferencia y de sistema de llamadas con planes de llamada. De este modo, satisface los requisitos empresariales adicionales al ampliar la experiencia de las reuniones y las llamadas de Microsoft Teams e incluir participantes externos conectados a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="d5fa1-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the Public Switched Telephone Network (PSTN).</span></span>
 
<span data-ttu-id="d5fa1-105">Esta página se irá actualizando conforme se vayan publicando características de voz en la nube adicionales en Teams.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>


##<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="d5fa1-106">Guía práctica para implementar Audioconferencia en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-106">Practical guidance for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="d5fa1-107">Audioconferencia en Office 365 permite a los participantes unirse a las reuniones desde cualquier teléfono.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="d5fa1-108">Esto es lo que conseguirá con [Audioconferencia](https://go.microsoft.com/fwlink/?linkid=858992) en Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

<span data-ttu-id="d5fa1-109">En esta guía práctica se detallan el recorrido que sigue el cliente con FastTrack para Office 365 y las tres fases que lo conforman (Enfoque, Incorporación y Nuevos valores) para ayudarle a planificar, entregar y utilizar una implementación correcta de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-109">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases, Envision, Onboard, and Drive Value, to help you plan, deliver, and operate an Audio Conferencing implementation towards succesful business outcomes.</span></span>

> [!TIP]
> <span data-ttu-id="d5fa1-110">En esta guía práctica ofreceremos ejemplos de respuestas para todas las actividades y discusiones clave.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-110">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="d5fa1-111">Los ejemplos de este documento se muestran dentro de recuadros de CONSEJO y se pueden utilizar como plantillas.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-111">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="d5fa1-112">La frase "Por añadir" indica que falta por completar con información como parte del proceso de planificación.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-112">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

##<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="d5fa1-113">Guía práctica para Sistema telefónico con planes de llamada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d5fa1-113">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="d5fa1-114">Sistema telefónico es una funcionalidad de Office 365 que permite administrar el enrutamiento de llamadas, las directivas y el aprovisionamiento de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-114">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="d5fa1-115">Aquí se incluye el sistema de administración de llamadas, el enrutamiento de llamadas y el control de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-115">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="d5fa1-116">Planes de llamada de Office 365 es un servicio complementario para la función Sistema telefónico que se proporciona a través de Microsoft Teams y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-116">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="d5fa1-117">Planes de llamada proporciona a los usuarios de su empresa un número de teléfono principal y les permite realizar llamadas fuera de la organización y recibirlas a través de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="d5fa1-117">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="d5fa1-118">Para obtener más información, consulte [Esto es lo que conseguirá con Sistema telefónico en Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) y [¿Qué son los Planes de llamada en Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span><span class="sxs-lookup"><span data-stu-id="d5fa1-118">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>

<span data-ttu-id="d5fa1-119">En esta guía práctica se detallan el recorrido que sigue el cliente con FastTrack para Office 365 y las tres fases que lo conforman (Enfoque, Incorporación y Nuevos valores) para ayudarle a planificar, entregar y utilizar una implementación correcta de Sistema telefónico con Planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-119">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases - Envision, Onboard, and Drive Value - to help you plan, deliver, and operate a successful Phone System with Calling Plans implementation.</span></span>

> [!TIP]
> <span data-ttu-id="d5fa1-120">En esta guía práctica ofreceremos ejemplos de respuestas para todas las actividades y discusiones clave.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-120">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="d5fa1-121">Los ejemplos de este documento se muestran dentro de recuadros de CONSEJO y se pueden utilizar como plantillas.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-121">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="d5fa1-122">La frase "Por añadir" indica que falta por completar con información como parte del proceso de planificación.</span><span class="sxs-lookup"><span data-stu-id="d5fa1-122">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>