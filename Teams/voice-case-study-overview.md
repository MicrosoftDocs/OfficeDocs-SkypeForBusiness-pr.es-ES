---
title: Caso práctico de voz de Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudio de casos de voz de Teams para la corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786088"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="834a7-103">Caso práctico de Contoso: Introducción a la migración de voz de Teams</span><span class="sxs-lookup"><span data-stu-id="834a7-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="834a7-104">En este artículo se presenta un caso práctico para el modo en que una corporación multinacional ficticia, Contoso, ha implementado una solución de voz de Teams para su organización.</span><span class="sxs-lookup"><span data-stu-id="834a7-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="834a7-105">Contoso ha implementado Microsoft 365 Enterprise y ha abordado las decisiones de diseño más importantes y los detalles de implementación de los siguientes temas: redes, identidad, Windows 10 Enterprise, Office 365 ProPlus, administración de dispositivos móviles, protección de la información, seguridad, actualización de Skype empresarial a equipos, el sistema telefónico y las conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="834a7-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="834a7-106">Este artículo se centra en el modo en que contoso migró sus usuarios locales a Teams para la comunicación, la colaboración y la voz unificadas.</span><span class="sxs-lookup"><span data-stu-id="834a7-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="834a7-107">Para obtener información general sobre cómo contoso ha acelerado su transformación digital mediante los servicios en la nube de Microsoft, vea todos los artículos principales comenzando con la [Descripción general de casos prácticos de Contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="834a7-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="834a7-108">En los artículos principales, encontrará información sobre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="834a7-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="834a7-109">Necesidades de la infraestructura de TI de Contoso</span><span class="sxs-lookup"><span data-stu-id="834a7-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="834a7-110">Redes</span><span class="sxs-lookup"><span data-stu-id="834a7-110">Networking</span></span>
- <span data-ttu-id="834a7-111">Identidad</span><span class="sxs-lookup"><span data-stu-id="834a7-111">Identity</span></span>
- <span data-ttu-id="834a7-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="834a7-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="834a7-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="834a7-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="834a7-114">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="834a7-114">Mobile device management</span></span>
- <span data-ttu-id="834a7-115">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="834a7-115">Information protection</span></span>
- <span data-ttu-id="834a7-116">Resumen de la seguridad de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="834a7-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="834a7-117">Equipo para un proyecto de clave principal</span><span class="sxs-lookup"><span data-stu-id="834a7-117">Team for a top-secret project</span></span>
- <span data-ttu-id="834a7-118">Sitio de SharePoint Online para activos digitales altamente confidenciales</span><span class="sxs-lookup"><span data-stu-id="834a7-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="834a7-119">Para obtener información sobre cómo planear una actualización, es recomendable empezar con [la introducción a la actualización de Microsoft Teams](upgrade-start-here.md).</span><span class="sxs-lookup"><span data-stu-id="834a7-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="834a7-120">Objetivos empresariales de Contoso para equipos</span><span class="sxs-lookup"><span data-stu-id="834a7-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="834a7-121">Para migrar sus usuarios locales a Teams para la comunicación, la colaboración y la voz unificadas, contoso decidió los siguientes objetivos empresariales:</span><span class="sxs-lookup"><span data-stu-id="834a7-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="834a7-122">Habilitación de equipos</span><span class="sxs-lookup"><span data-stu-id="834a7-122">Teams enablement</span></span> 

  <span data-ttu-id="834a7-123">El equipo de colaboración y colaboración Unificado de Contoso ha habilitado a los equipos con las directivas correctas para regir y habilitar la colaboración interna y externa segura.</span><span class="sxs-lookup"><span data-stu-id="834a7-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="834a7-124">Actualización de Skype Empresarial a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="834a7-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="834a7-125">Skype empresarial se ha distribuido ampliamente en contoso.</span><span class="sxs-lookup"><span data-stu-id="834a7-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="834a7-126">Con la necesidad de desplazarse por sistemas heredados, contoso decidió actualizar los usuarios de Skype empresarial a teams.</span><span class="sxs-lookup"><span data-stu-id="834a7-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="834a7-127">Para obtener más información, vea [caso práctico de Contoso: Plan de actualización de Teams](voice-case-study-migration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="834a7-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="834a7-128">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="834a7-128">Phone System</span></span>  

  <span data-ttu-id="834a7-129">Skype empresarial con Enterprise Voice se ha implementado ampliamente en contoso.</span><span class="sxs-lookup"><span data-stu-id="834a7-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="834a7-130">Con la necesidad de cambiar de sistemas heredados que fueron el próximo paso para sus servidores de mediación, contoso migró sus usuarios de voz de Skype empresarial empresarial a un sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="834a7-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="834a7-131">Los sitios de Contoso usaban el plan de llamadas de Microsoft, el enrutamiento directo del sistema telefónico o una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="834a7-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="834a7-132">Para obtener más información, consulte [caso práctico de Contoso: Phone System](voice-case-study-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="834a7-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="834a7-133">Enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="834a7-133">Location-Based Routing</span></span> 

  <span data-ttu-id="834a7-134">Con las ubicaciones de Office en los países regulados por telefonía, contoso necesitaba volver a crear el enrutamiento basado en la ubicación que estaba presente en Skype empresarial en su implementación de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="834a7-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="834a7-135">Para obtener más información, vea [caso práctico de Contoso: enrutamiento basado en la ubicación](voice-case-study-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="834a7-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="834a7-136">Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="834a7-136">Emergency Calling</span></span> 

  <span data-ttu-id="834a7-137">Donde se implementó el enrutamiento directo, contoso configure las llamadas de emergencia con terceros aprobados.</span><span class="sxs-lookup"><span data-stu-id="834a7-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="834a7-138">Para obtener más información, consulte [caso práctico de Contoso: llamadas de emergencia](voice-case-study-emergency-calling.md).</span><span class="sxs-lookup"><span data-stu-id="834a7-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="834a7-139">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="834a7-139">Audio Conferencing</span></span> 

  <span data-ttu-id="834a7-140">Contoso configure los números del servicio de audioconferencia que se hospedaron en su enlace SIP a su proveedor PSTN.</span><span class="sxs-lookup"><span data-stu-id="834a7-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="834a7-141">Para obtener más información, vea [caso práctico de Contoso: audioconferencia](voice-case-study-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="834a7-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="834a7-142">Optimización local de medios</span><span class="sxs-lookup"><span data-stu-id="834a7-142">Local Media Optimization</span></span> 

  <span data-ttu-id="834a7-143">Contoso aprovechó la optimización local de medios en ubicaciones en las que tenían un tronco de ruta directa a Microsoft Phone System aprovechado por sitios remotos.</span><span class="sxs-lookup"><span data-stu-id="834a7-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="834a7-144">Para obtener más información, vea [planear la optimización local de medios](direct-routing-media-optimization.md) y [configurar la optimización local de medios](direct-routing-media-optimization-configure.md).</span><span class="sxs-lookup"><span data-stu-id="834a7-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="834a7-145">Operadores automáticos y colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="834a7-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="834a7-146">Como resultado de Covid-19, contoso quería proporcionar asistencia para la recepcionista mientras el personal estaba trabajando de forma remota.</span><span class="sxs-lookup"><span data-stu-id="834a7-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="834a7-147">Contoso usó operadores automáticos y colas de llamadas para administrar las llamadas entrantes a su número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="834a7-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="834a7-148">Para obtener más información, vea [caso práctico de Contoso: operadores automáticos y colas de llamadas](voice-case-study-call-queues.md).</span><span class="sxs-lookup"><span data-stu-id="834a7-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


