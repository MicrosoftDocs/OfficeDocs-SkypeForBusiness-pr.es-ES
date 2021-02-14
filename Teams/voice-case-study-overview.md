---
title: Caso práctico Teams voice Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Caso práctico de voz de Teams para empresas multinacionales
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701228"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="34b6c-103">Caso práctico Contoso: Introducción a la migración de voz de Teams</span><span class="sxs-lookup"><span data-stu-id="34b6c-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="34b6c-104">En este artículo se presenta un caso práctico sobre cómo una corporación multinacional ficticia, Contoso, implementó una solución de voz de Teams para su organización.</span><span class="sxs-lookup"><span data-stu-id="34b6c-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="34b6c-105">Contoso ha implementado Microsoft 365 Enterprise y ha abordado las principales decisiones de diseño y detalles de implementación para lo siguiente: redes, identidad, Windows 10 Enterprise, Office 365 ProPlus, administración de dispositivos móviles, protección de la información, seguridad, actualización de Skype Empresarial a Teams, sistema telefónico y audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="34b6c-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="34b6c-106">Este artículo se centra en cómo Contoso ha migrado sus usuarios locales a Teams para mejorar la comunicación unificada, la colaboración y la voz.</span><span class="sxs-lookup"><span data-stu-id="34b6c-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="34b6c-107">Para obtener información básica sobre cómo Contoso acelera su transformación digital usando los servicios en la nube de Microsoft, vea todos los artículos principales que empiezan con la información general del caso práctico [Contoso.](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="34b6c-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="34b6c-108">En los artículos principales, encontrará información sobre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="34b6c-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="34b6c-109">Necesidades de infraestructura de TI de Contoso</span><span class="sxs-lookup"><span data-stu-id="34b6c-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="34b6c-110">Redes</span><span class="sxs-lookup"><span data-stu-id="34b6c-110">Networking</span></span>
- <span data-ttu-id="34b6c-111">Identidad</span><span class="sxs-lookup"><span data-stu-id="34b6c-111">Identity</span></span>
- <span data-ttu-id="34b6c-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="34b6c-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="34b6c-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="34b6c-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="34b6c-114">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="34b6c-114">Mobile device management</span></span>
- <span data-ttu-id="34b6c-115">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="34b6c-115">Information protection</span></span>
- <span data-ttu-id="34b6c-116">Resumen de la seguridad de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="34b6c-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="34b6c-117">Equipo para un proyecto de alto secreto</span><span class="sxs-lookup"><span data-stu-id="34b6c-117">Team for a top-secret project</span></span>
- <span data-ttu-id="34b6c-118">Sitio de SharePoint Online para activos digitales de alta confidencialidad</span><span class="sxs-lookup"><span data-stu-id="34b6c-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="34b6c-119">Para obtener información sobre cómo planear una actualización, debe empezar con Introducción a la [actualización de Microsoft Teams.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="34b6c-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="34b6c-120">Objetivos empresariales de Contoso para Teams</span><span class="sxs-lookup"><span data-stu-id="34b6c-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="34b6c-121">Para migrar sus usuarios locales a Teams para una comunicación unificada, colaboración y voz, Contoso decidió los siguientes objetivos empresariales:</span><span class="sxs-lookup"><span data-stu-id="34b6c-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="34b6c-122">Habilitación de Teams</span><span class="sxs-lookup"><span data-stu-id="34b6c-122">Teams enablement</span></span> 

  <span data-ttu-id="34b6c-123">El equipo de colaboración y comunicación unificada de Contoso habilitó a Teams con las directivas correctas para gobernar y habilitar la colaboración interna y externa segura.</span><span class="sxs-lookup"><span data-stu-id="34b6c-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="34b6c-124">Actualización de Skype Empresarial a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34b6c-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="34b6c-125">Skype Empresarial se implementó ampliamente en Contoso.</span><span class="sxs-lookup"><span data-stu-id="34b6c-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="34b6c-126">Con la necesidad de dejar de usar sistemas antiguos, Contoso ha decidido actualizar sus usuarios de Skype Empresarial a Teams.</span><span class="sxs-lookup"><span data-stu-id="34b6c-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="34b6c-127">Para obtener más información, vea [el caso práctico Contoso: Plan de actualización de Teams.](voice-case-study-migration-plan.md)</span><span class="sxs-lookup"><span data-stu-id="34b6c-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="34b6c-128">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="34b6c-128">Phone System</span></span>  

  <span data-ttu-id="34b6c-129">Skype Empresarial con voz empresarial se implementó ampliamente en Contoso.</span><span class="sxs-lookup"><span data-stu-id="34b6c-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="34b6c-130">Con la necesidad de desactivar los sistemas heredados que eran el próximo salto para sus servidores de mediación, Contoso ha migrado sus usuarios de voz empresarial de Skype Empresarial al sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="34b6c-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="34b6c-131">Los sitios de Contoso usaban un plan de llamadas de Microsoft, un enrutamiento directo de sistema telefónico o una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="34b6c-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="34b6c-132">Para obtener más información, vea [el caso práctico Contoso: Sistema telefónico.](voice-case-study-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="34b6c-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="34b6c-133">Enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="34b6c-133">Location-Based Routing</span></span> 

  <span data-ttu-id="34b6c-134">Con las ubicaciones de oficina en países donde se regula la telefonía, Contoso tenía que volver a crear el enrutamiento de Location-Based que estaba presente en Skype Empresarial en la implementación del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="34b6c-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="34b6c-135">Para obtener más información, vea [el caso práctico Contoso: Location-Based enrutamiento.](voice-case-study-location-based-routing.md)</span><span class="sxs-lookup"><span data-stu-id="34b6c-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="34b6c-136">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="34b6c-136">Emergency Calling</span></span> 

  <span data-ttu-id="34b6c-137">Cuando se implementó enrutamiento directo, Contoso estableció las llamadas de emergencia con terceros aprobados.</span><span class="sxs-lookup"><span data-stu-id="34b6c-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="34b6c-138">Para obtener más información, consulte [el caso práctico Contoso: Llamadas de emergencia.](voice-case-study-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="34b6c-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="34b6c-139">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="34b6c-139">Audio Conferencing</span></span> 

  <span data-ttu-id="34b6c-140">Contoso ha configurado en su proveedor de RTC los números de servicio de Audioconferencia que se hospedaron en su tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="34b6c-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="34b6c-141">Para obtener más información, vea [el caso práctico Contoso: Audioconferencia.](voice-case-study-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="34b6c-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="34b6c-142">Optimización de medios locales</span><span class="sxs-lookup"><span data-stu-id="34b6c-142">Local Media Optimization</span></span> 

  <span data-ttu-id="34b6c-143">Contoso aprovechaba la optimización de medios locales en ubicaciones donde tenía un tronco de ruta directa a Microsoft Phone System aprovechado por sitios remotos.</span><span class="sxs-lookup"><span data-stu-id="34b6c-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="34b6c-144">Para obtener más información, vea [Planear la optimización de medios locales](direct-routing-media-optimization.md) y configurar la [optimización de medios locales.](direct-routing-media-optimization-configure.md)</span><span class="sxs-lookup"><span data-stu-id="34b6c-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="34b6c-145">Operadores automáticos y colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="34b6c-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="34b6c-146">Como resultado de Covid-19, Contoso quería ofrecer soporte al recepcionista mientras su personal trabajaba de forma remota.</span><span class="sxs-lookup"><span data-stu-id="34b6c-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="34b6c-147">Contoso usaba operadores automáticos y colas de llamadas para administrar las llamadas entrantes en el número de teléfono de su recepcionista.</span><span class="sxs-lookup"><span data-stu-id="34b6c-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="34b6c-148">Para obtener más información, consulte [el caso práctico Contoso: Operadores automáticos y colas de llamadas.](voice-case-study-call-queues.md)</span><span class="sxs-lookup"><span data-stu-id="34b6c-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


