---
title: Qué es en desuso de Skype empresarial Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: estas características se han eliminado de Skype empresarial Server 2019.'
ms.openlocfilehash: a342f98d1a3191064d1678190a0d4b743b40a37f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278115"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="be480-103">Qué es en desuso de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="be480-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="be480-104">Obtenga más información sobre las características y funcionalidades que ya no se usan en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="be480-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="be480-105">Para obtener información sobre las nuevas características de Skype empresarial Server 2019, consulte [novedades de Skype empresarial server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="be480-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="be480-106">Algunas características desacentuadas están incluidas en Skype empresarial Server 2019 por compatibilidad con versiones anteriores del producto.</span><span class="sxs-lookup"><span data-stu-id="be480-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="be480-107">Características desusadas en Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="be480-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="be480-108">Puertas de enlace XMPP para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="be480-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="be480-109">Skype empresarial Server 2015 y sus antecesores le permiten configurar un proxy protocolo de presencia y mensajería extensible (XMPP) en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end o en el grupo front-end.</span><span class="sxs-lookup"><span data-stu-id="be480-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="be480-110">Esta funcionalidad ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="be480-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="be480-111">Chat persistente para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="be480-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="be480-112">El servidor de chat persistente es un rol opcional que permite que varios usuarios de su organización participen en las conversaciones del salón de chat que se mantienen a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="be480-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="be480-113">El chat persistente no se puede implementar con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="be480-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="be480-114">Este rol de servidor se ha quitado de Topology Builder, así como del código.</span><span class="sxs-lookup"><span data-stu-id="be480-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="be480-115">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="be480-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="be480-116">Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="be480-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="be480-117">Reflejo de SQL para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="be480-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="be480-118">No se puede implementar la creación de reflejos de SQL con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="be480-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="be480-119">Aún se admiten otras opciones para ofrecer una alta disponibilidad y recuperación ante desastres y debe elegir entre ellas.</span><span class="sxs-lookup"><span data-stu-id="be480-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="be480-120">Consulte [planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar las opciones.</span><span class="sxs-lookup"><span data-stu-id="be480-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="be480-121">Actualizaciones locales</span><span class="sxs-lookup"><span data-stu-id="be480-121">In-place upgrades</span></span> 

<span data-ttu-id="be480-122">Las actualizaciones locales estaban disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="be480-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="be480-123">La actualización en paralelo y la coexistencia son compatibles, consulte [migración a Skype empresarial Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="be480-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="be480-124">Servicio de movilidad (MCX)</span><span class="sxs-lookup"><span data-stu-id="be480-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="be480-125">El soporte de servicio de movilidad usado por clientes móviles heredados ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="be480-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="be480-126">Esto fue anunciado anteriormente en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="be480-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="be480-127">Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="be480-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="be480-128">Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="be480-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="be480-129">Para obtener más información, consulte [plan de movilidad para Skype empresarial Server](../SfbServer/plan-your-deployment/mobility.md) y la [comparación de características de cliente móvil para Skype empresarial](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="be480-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="be480-130">Herramientas</span><span class="sxs-lookup"><span data-stu-id="be480-130">Tools</span></span>

<span data-ttu-id="be480-131">Las siguientes herramientas no estarán disponibles para su uso en la versión inicial de Skype empresarial Server 2019:</span><span class="sxs-lookup"><span data-stu-id="be480-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="be480-132">Calculadora de planeamiento de capacidad de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="be480-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="be480-133">Herramientas de depuración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="be480-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="be480-134">Herramientas del kit de recursos de Skype empresarial Server (se quitarán algunas herramientas)</span><span class="sxs-lookup"><span data-stu-id="be480-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="be480-135">Call Parkometer (Estacionamiento de llamadas)</span><span class="sxs-lookup"><span data-stu-id="be480-135">Call Parkometer</span></span>
    - <span data-ttu-id="be480-136">Consola de búsqueda de usuarios</span><span class="sxs-lookup"><span data-stu-id="be480-136">Lookup user console</span></span>
    - <span data-ttu-id="be480-137">Migración del anuncio de número no asignado</span><span class="sxs-lookup"><span data-stu-id="be480-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="be480-138">Las siguientes herramientas no son compatibles con Skype empresarial Server 2019:</span><span class="sxs-lookup"><span data-stu-id="be480-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="be480-139">Metodología de calidad de las llamadas (pero no panel de calidad de las llamadas)</span><span class="sxs-lookup"><span data-stu-id="be480-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="be480-140">Cuadro de mandos de metodología de llamadas de Microsoft, v 1.5</span><span class="sxs-lookup"><span data-stu-id="be480-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="be480-141">Herramienta de planeación de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="be480-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="be480-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="be480-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="be480-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="be480-143">See also</span></span>

[<span data-ttu-id="be480-144">Novedades de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="be480-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="be480-145">Migrar la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="be480-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
