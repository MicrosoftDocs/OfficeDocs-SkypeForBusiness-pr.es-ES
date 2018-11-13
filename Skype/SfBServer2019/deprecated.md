---
title: ¿Qué está en desuso de Skype para Business Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: Estas características se han quitado de Skype para Business Server 2019.'
ms.openlocfilehash: 926f5539a31dbcb37ff4ccb5494ccaa7be517d30
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294251"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="3ba6d-103">¿Qué está en desuso de Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3ba6d-103">What's deprecated from Skype for Business Server 2019</span></span> 

<span data-ttu-id="3ba6d-104">Obtenga información sobre las características y funciones que están en desuso en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="3ba6d-105">Para obtener información acerca de las nuevas características de Skype para Business Server 2019, consulte [Novedades en Skype para Business Server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="3ba6d-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="3ba6d-106">Algunas características desaprovisionamiento emphasised se incluyen en Skype para Business Server 2019 para la compatibilidad con versiones anteriores del producto.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-106">Some de-emphasised features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span> 

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="3ba6d-107">Características desusadas en Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3ba6d-107">Features deprecated in Skype for Business Server 2019</span></span> 

        The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="3ba6d-108">Puertas de enlace XMPP de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3ba6d-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="3ba6d-109">Skype para Business Server 2015 y sus predecesoras permite configurar un proxy de mensajería Extensible y protocolo de presencia (XMPP) en el servidor perimetral y una puerta de enlace de XMPP en el grupo de servidores Front-End o de servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="3ba6d-110">Esta funcionalidad ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>


### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="3ba6d-111">Persistent Chat de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3ba6d-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="3ba6d-112">Persistent Chat Server es un rol opcional que permite a varios usuarios de la organización participar en conversaciones de salón de chat que persisten a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="3ba6d-113">Chat en grupo no se puede implementar con Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="3ba6d-114">Esta función de servidor se ha quitado el generador de topología, así como desde el código.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="3ba6d-115">La misma funcionalidad está disponible en los equipos.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="3ba6d-116">Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="3ba6d-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span>   

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="3ba6d-117">Creación de reflejos SQL para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3ba6d-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="3ba6d-118">La creación de reflejos de SQL no se puede implementar con Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="3ba6d-119">Aún se admiten otras opciones para proporcionar alta disponibilidad y recuperación ante desastres y debe elegir entre ellos.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="3ba6d-120">Consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar las opciones.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="3ba6d-121">Actualizaciones en contexto</span><span class="sxs-lookup"><span data-stu-id="3ba6d-121">In-place upgrades</span></span> 

<span data-ttu-id="3ba6d-122">Las actualizaciones en contexto estaban disponibles en Skype para Business Server 2015, pero ya no se admiten en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3ba6d-123">En paralelo se admite la actualización y coexistencia, consulte [migración de Skype para Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

###  <a name="mobility-service-mcx"></a><span data-ttu-id="3ba6d-124">Servicio de movilidad (Mcx)</span><span class="sxs-lookup"><span data-stu-id="3ba6d-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="3ba6d-125">Compatibilidad con el servicio movilidad usado por los clientes móviles heredados ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="3ba6d-126">Anteriormente se presentó en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="3ba6d-127">Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="3ba6d-128">Los usuarios con los clientes heredados con Mcx necesitará actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="3ba6d-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="3ba6d-129">Para obtener más detalles, vea [planear para movilidad de Skype para Business Server](../SfbServer/plan-your-deployment/mobility.md) y la [comparación de características de cliente móvil de Skype para la empresa](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="3ba6d-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="3ba6d-130">Herramientas</span><span class="sxs-lookup"><span data-stu-id="3ba6d-130">Tools</span></span>

<span data-ttu-id="3ba6d-131">Las siguientes herramientas no estará disponibles para su uso en la versión inicial de Skype para Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="3ba6d-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="3ba6d-132">Skype para Calculadora de planeación de la capacidad de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="3ba6d-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="3ba6d-133">Skype para herramientas de depuración de Business Server</span><span class="sxs-lookup"><span data-stu-id="3ba6d-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="3ba6d-134">Skype para (algunas herramientas se quitará) de herramientas del Kit de recursos de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="3ba6d-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="3ba6d-135">Call Parkometer (Estacionamiento de llamadas)</span><span class="sxs-lookup"><span data-stu-id="3ba6d-135">Call Parkometer</span></span>
    - <span data-ttu-id="3ba6d-136">Consola de usuario de búsqueda</span><span class="sxs-lookup"><span data-stu-id="3ba6d-136">Lookup user console</span></span>
    - <span data-ttu-id="3ba6d-137">Migración de anuncio de número sin asignar</span><span class="sxs-lookup"><span data-stu-id="3ba6d-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="3ba6d-138">Las siguientes herramientas no son compatibles con Skype para Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="3ba6d-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="3ba6d-139">Panel de metodología de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="3ba6d-139">Call Quality Methodology Dashboard</span></span>
- <span data-ttu-id="3ba6d-140">Cuadro de mandos de metodología de calidad de llamada de Microsoft, v1.5</span><span class="sxs-lookup"><span data-stu-id="3ba6d-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="3ba6d-141">Skype for Business Server 2015 Planning Tool</span><span class="sxs-lookup"><span data-stu-id="3ba6d-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="3ba6d-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="3ba6d-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="3ba6d-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ba6d-143">See also</span></span>

[<span data-ttu-id="3ba6d-144">¿Qué es una novedad de Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3ba6d-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="3ba6d-145">Migración de la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="3ba6d-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)