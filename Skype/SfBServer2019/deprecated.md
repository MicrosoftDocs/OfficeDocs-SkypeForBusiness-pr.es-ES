---
title: Qué está en desuso de Skype Empresarial Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: estas características se han quitado de Skype Empresarial Server 2019.'
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808730"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="a8e3c-103">Qué está en desuso de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="a8e3c-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="a8e3c-104">Obtenga información sobre las características y funciones que están en desuso en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="a8e3c-105">Para obtener información sobre las nuevas características de Skype Empresarial Server 2019, consulte [What's in Skype for Business Server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="a8e3c-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="a8e3c-106">Algunas características que no se destacan se incluyen en Skype Empresarial Server 2019 para la compatibilidad con versiones anteriores del producto.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="a8e3c-107">Características en desuso en Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="a8e3c-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="a8e3c-108">Puertas de enlace XMPP para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a8e3c-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="a8e3c-109">Skype Empresarial Server 2015 y sus predecesores le permitían configurar un proxy del Protocolo extensible de mensajería y presencia (XMPP) en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end o grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="a8e3c-110">Esta funcionalidad ya no está disponible en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="a8e3c-111">Chat persistente para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a8e3c-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="a8e3c-112">El servidor de chat persistente es un rol opcional que permite a varios usuarios de su organización participar en conversaciones de salón de chat que persisten con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="a8e3c-113">El chat persistente no se puede implementar con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="a8e3c-114">Este rol de servidor se ha quitado del Generador de topologías, así como del código.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="a8e3c-115">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="a8e3c-116">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="a8e3c-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="a8e3c-117">SQL creación de reflejos para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a8e3c-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="a8e3c-118">SQL la creación de reflejo no se puede implementar con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="a8e3c-119">Aún se admiten otras opciones para proporcionar alta disponibilidad y recuperación ante desastres, entre las que debe elegir entre ellas.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="a8e3c-120">Vea [plan de alta disponibilidad y recuperación ante desastres en Skype Empresarial Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar las opciones.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="a8e3c-121">Actualizaciones locales</span><span class="sxs-lookup"><span data-stu-id="a8e3c-121">In-place upgrades</span></span> 

<span data-ttu-id="a8e3c-122">Las actualizaciones locales estaban disponibles en Skype Empresarial Server 2015, pero ya no son compatibles con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a8e3c-123">Para obtener más información, consulte Migración a [Skype Empresarial Server 2019.](migration/migration-to-skype-for-business-server-2019.md)</span><span class="sxs-lookup"><span data-stu-id="a8e3c-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="a8e3c-124">Mobility Service (Mcx)</span><span class="sxs-lookup"><span data-stu-id="a8e3c-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="a8e3c-125">La compatibilidad con el servicio de movilidad que usan los clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a8e3c-126">Esto se anunció anteriormente en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="a8e3c-127">Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a8e3c-128">Los usuarios con clientes heredados que usen Mcx tendrán que actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="a8e3c-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="a8e3c-129">Para obtener más información, consulte [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for [Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="a8e3c-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="a8e3c-130">Herramientas</span><span class="sxs-lookup"><span data-stu-id="a8e3c-130">Tools</span></span>

<span data-ttu-id="a8e3c-131">Las siguientes herramientas no estarán disponibles para su uso en la versión inicial de Skype Empresarial Server 2019:</span><span class="sxs-lookup"><span data-stu-id="a8e3c-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="a8e3c-132">Calculadora de planeamiento de capacidad de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a8e3c-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="a8e3c-133">Herramientas de depuración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a8e3c-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="a8e3c-134">Herramientas del kit de recursos de Skype Empresarial Server (se quitarán algunas herramientas)</span><span class="sxs-lookup"><span data-stu-id="a8e3c-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="a8e3c-135">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="a8e3c-135">Call Parkometer</span></span>
    - <span data-ttu-id="a8e3c-136">Consola de usuario de búsqueda</span><span class="sxs-lookup"><span data-stu-id="a8e3c-136">Lookup user console</span></span>
    - <span data-ttu-id="a8e3c-137">Migración de anuncios de número sin signo</span><span class="sxs-lookup"><span data-stu-id="a8e3c-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="a8e3c-138">Las siguientes herramientas no son compatibles con Skype Empresarial Server 2019:</span><span class="sxs-lookup"><span data-stu-id="a8e3c-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="a8e3c-139">Metodología de calidad de llamadas (pero no panel de calidad de llamadas)</span><span class="sxs-lookup"><span data-stu-id="a8e3c-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="a8e3c-140">Cuadro de mandos de metodología de calidad de llamadas de Microsoft, v1.5</span><span class="sxs-lookup"><span data-stu-id="a8e3c-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="a8e3c-141">Herramienta de planeación de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a8e3c-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="a8e3c-142">Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a8e3c-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="a8e3c-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8e3c-143">See also</span></span>

[<span data-ttu-id="a8e3c-144">Novedades de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="a8e3c-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="a8e3c-145">Migrar la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="a8e3c-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
