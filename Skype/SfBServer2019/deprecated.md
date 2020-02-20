---
title: Qué está en desuso en Skype empresarial Server 2019
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: estas características se han quitado de Skype empresarial Server 2019.'
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125223"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="e4981-103">Qué está en desuso en Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="e4981-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="e4981-104">Obtenga información sobre las características y funciones que están en desuso en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4981-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="e4981-105">Para obtener información acerca de las nuevas características de Skype empresarial Server 2019, consulte [what's in Skype for Business server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="e4981-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="e4981-106">Algunas características que se pueden recalcar se incluyen en Skype empresarial Server 2019 por compatibilidad con versiones anteriores del producto.</span><span class="sxs-lookup"><span data-stu-id="e4981-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="e4981-107">Características en desuso en Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="e4981-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="e4981-108">Puertas de enlace XMPP para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e4981-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="e4981-109">Skype empresarial Server 2015 y sus antecesores le permiten configurar un proxy de protocolo extensible de mensajería y presencia (XMPP) en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="e4981-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="e4981-110">Esta funcionalidad ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4981-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="e4981-111">Chat persistente de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e4981-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="e4981-112">El servidor de chat persistente es un rol opcional que permite que varios usuarios de la organización participen en las conversaciones del salón de chat que persisten a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="e4981-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="e4981-113">Chat persistente no se puede implementar con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4981-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="e4981-114">Este rol de servidor se quita del generador de topologías, así como del código.</span><span class="sxs-lookup"><span data-stu-id="e4981-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="e4981-115">La misma funcionalidad está disponible en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4981-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="e4981-116">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="e4981-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="e4981-117">Creación de reflejos de SQL para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e4981-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="e4981-118">La creación de reflejos de SQL no se puede implementar con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4981-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="e4981-119">También se admiten otras opciones para la alta disponibilidad y la recuperación ante desastres y debe elegir entre ellas.</span><span class="sxs-lookup"><span data-stu-id="e4981-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="e4981-120">Consulte [Plan for High Availability and Disaster Recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar las opciones.</span><span class="sxs-lookup"><span data-stu-id="e4981-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="e4981-121">Actualizaciones en el lugar</span><span class="sxs-lookup"><span data-stu-id="e4981-121">In-place upgrades</span></span> 

<span data-ttu-id="e4981-122">Las actualizaciones locales estaban disponibles en Skype empresarial Server 2015, pero ya no se admiten en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4981-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e4981-123">Se admite la coexistencia y la actualización en paralelo, consulte [migración a Skype empresarial Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e4981-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="e4981-124">Servicio de movilidad (MCX)</span><span class="sxs-lookup"><span data-stu-id="e4981-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="e4981-125">El soporte del servicio de movilidad usado por los clientes móviles heredados ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4981-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e4981-126">Esto se anunció anteriormente en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e4981-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="e4981-127">Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (mi), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="e4981-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e4981-128">Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="e4981-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="e4981-129">Para obtener más información, consulte [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile Client Feature Comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="e4981-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="e4981-130">Herramientas</span><span class="sxs-lookup"><span data-stu-id="e4981-130">Tools</span></span>

<span data-ttu-id="e4981-131">Las siguientes herramientas no estarán disponibles para su uso en la versión inicial de Skype empresarial Server 2019:</span><span class="sxs-lookup"><span data-stu-id="e4981-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="e4981-132">Calculadora de planeación de capacidad de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e4981-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="e4981-133">Herramientas de depuración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e4981-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="e4981-134">Herramientas del kit de recursos de Skype empresarial Server (se quitan algunas herramientas)</span><span class="sxs-lookup"><span data-stu-id="e4981-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="e4981-135">Llamar a Parkometer</span><span class="sxs-lookup"><span data-stu-id="e4981-135">Call Parkometer</span></span>
    - <span data-ttu-id="e4981-136">Consola del usuario de búsqueda</span><span class="sxs-lookup"><span data-stu-id="e4981-136">Lookup user console</span></span>
    - <span data-ttu-id="e4981-137">Migración del anuncio de número sin asignar</span><span class="sxs-lookup"><span data-stu-id="e4981-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="e4981-138">Las siguientes herramientas no son compatibles con Skype empresarial Server 2019:</span><span class="sxs-lookup"><span data-stu-id="e4981-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="e4981-139">Metodología de calidad de llamadas (pero no panel de calidad de llamadas)</span><span class="sxs-lookup"><span data-stu-id="e4981-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="e4981-140">Cuadro de mandos de metodología de calidad de llamadas de Microsoft, v 1.5</span><span class="sxs-lookup"><span data-stu-id="e4981-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="e4981-141">Herramienta de planeación de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e4981-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="e4981-142">Herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e4981-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="e4981-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4981-143">See also</span></span>

[<span data-ttu-id="e4981-144">Novedades de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="e4981-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="e4981-145">Migración de la Federación XMPP</span><span class="sxs-lookup"><span data-stu-id="e4981-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
