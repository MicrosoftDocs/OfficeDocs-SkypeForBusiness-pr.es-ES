---
title: Teams caso práctico de Contoso de voz
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
description: Teams caso de voz para empresas multinacionales
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786104"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="ea387-103">Caso práctico de Contoso: Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="ea387-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="ea387-104">Para comprender la disponibilidad de llamadas de emergencia y terminología relacionadas con las llamadas de emergencia Dirección de emergencia, Lugar, Ubicación de emergencia y Dirección registrada Contoso revisó Administrar llamadas de emergencia y Planear y configurar llamadas de emergencia &mdash; &mdash; [dinámicas.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="ea387-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="ea387-105">En Office 365, un usuario del Plan de llamadas se habilita automáticamente para las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ea387-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="ea387-106">Pero solo los usuarios del Plan de llamadas de Estados Unidos pueden usar ubicaciones dinámicas para enrutar llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ea387-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="ea387-107">En El enrutamiento directo, Contoso aprendió que se requiere una configuración adicional para enrutar llamadas de emergencia y posiblemente para la conectividad de partners.</span><span class="sxs-lookup"><span data-stu-id="ea387-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="ea387-108">El administrador debe configurar la conexión a un proveedor de servicios de enrutamiento de emergencia (ERSP) (Estados Unidos) O configurar el controlador de borde de sesión (SBC) para una aplicación de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="ea387-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="ea387-109">Contoso tiene oficinas en Estados Unidos y fuera de los Estados Unidos:</span><span class="sxs-lookup"><span data-stu-id="ea387-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="ea387-110">En Estados Unidos, los usuarios del Plan de llamadas contoso pueden usar ubicaciones dinámicas para enrutar llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ea387-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="ea387-111">Fuera de los Estados Unidos, Contoso tiene algunos sitios que usan planes de llamadas y algunos sitios que están conectados a Sistema telefónico mediante enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="ea387-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="ea387-112">Casos de uso de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="ea387-112">Emergency calling use cases</span></span>

<span data-ttu-id="ea387-113">Después de decidir cómo Contoso se conectará Teléfono sistema, Contoso identificó los siguientes casos de uso de llamadas de emergencia:</span><span class="sxs-lookup"><span data-stu-id="ea387-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="ea387-114">Usuario del plan de llamadas en Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="ea387-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="ea387-115">Usuario del Plan de llamadas fuera de los Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="ea387-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="ea387-116">Usuario que se conecta a Sistema telefónico mediante enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="ea387-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="ea387-117">Usuario del plan de llamadas en Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="ea387-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="ea387-118">Hay requisitos para cuando el número de teléfono debe estar asociado a una ubicación de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ea387-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="ea387-119">Para comprender estos requisitos, Contoso revisó [Consideraciones para planes de llamadas.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="ea387-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="ea387-120">En función de estos requisitos, Contoso decidió asociar la ubicación con el número de teléfono cuando se asigna un número a un usuario en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="ea387-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="ea387-121">Usuario del Plan de llamadas fuera de los Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="ea387-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="ea387-122">Para comprender cuándo un número de teléfono debe estar asociado a una ubicación de emergencia, Contoso revisó Consideraciones para [planes de llamadas.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="ea387-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="ea387-123">Según los requisitos, Contoso decidió lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ea387-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="ea387-124">Contoso asociará la ubicación con el número de teléfono cuando se asigne un número a un usuario en Canadá.</span><span class="sxs-lookup"><span data-stu-id="ea387-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="ea387-125">Contoso asignará una ubicación de emergencia cuando el número de teléfono se adquiere de Office 365 o cuando se transfiere un número de otro proveedor de servicios u operador.</span><span class="sxs-lookup"><span data-stu-id="ea387-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="ea387-126">Usuario que se conecta a Sistema telefónico mediante enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="ea387-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="ea387-127">Para planear el enrutamiento de emergencia para este caso de uso, Contoso revisó [Consideraciones para enrutamiento directo.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="ea387-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="ea387-128">Como los usuarios de Enrutamiento directo no reciben llamadas de emergencia de la misma manera que los usuarios del Plan de llamadas, Contoso tuvo que decidir cómo proporcionar llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ea387-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="ea387-129">El enrutamiento directo se puede conectar a un proveedor de servicios de enrutamiento de emergencia (ERSP).</span><span class="sxs-lookup"><span data-stu-id="ea387-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="ea387-130">El enrutamiento directo también puede tener un SBC que incluye un número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="ea387-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="ea387-131">Consideraciones del Proveedor de servicios de enrutamiento de emergencia (ERSP)</span><span class="sxs-lookup"><span data-stu-id="ea387-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="ea387-132">Los proveedores de servicios de enrutamiento de emergencia (ERSP) pueden enrutar automáticamente las llamadas de emergencia en función de la ubicación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ea387-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="ea387-133">Si un proveedor de servicios de enrutamiento de emergencia está integrado en una implementación de enrutamiento directo, las llamadas de emergencia con una ubicación adquirida dinámicamente se enruta automáticamente al Punto de respuesta de seguridad pública (PSAP) que sirve a esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="ea387-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="ea387-134">Las llamadas de emergencia sin una ubicación adquirida dinámicamente se primero se proyectan para determinar la ubicación actual del usuario antes de conectar la llamada al centro de envío adecuado en función de la ubicación actualizada.</span><span class="sxs-lookup"><span data-stu-id="ea387-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="ea387-135">Consideraciones de ELIN</span><span class="sxs-lookup"><span data-stu-id="ea387-135">ELIN considerations</span></span>

<span data-ttu-id="ea387-136">Si una aplicación ELIN de SBC está integrada en una implementación de enrutamiento directo, es necesario realizar pasos de configuración adicionales para asociar las direcciones de emergencia con números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="ea387-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="ea387-137">Contoso decidió usar controladores de borde de sesión que incluyen aplicaciones de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="ea387-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="ea387-138">Notificación de escritorio de seguridad</span><span class="sxs-lookup"><span data-stu-id="ea387-138">Security desk notification</span></span>

<span data-ttu-id="ea387-139">La capacidad de notificar al departamento de seguridad cuando se realiza una llamada de emergencia está disponible tanto para planes de llamadas de Microsoft como para Sistema telefónico enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="ea387-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="ea387-140">Contoso revisó los detalles en la notificación de escritorio de seguridad para determinar si esto se debe configurar en sus oficinas</span><span class="sxs-lookup"><span data-stu-id="ea387-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="ea387-141">Contoso decidió usar la notificación de escritorio de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ea387-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="ea387-142">Configuración</span><span class="sxs-lookup"><span data-stu-id="ea387-142">Configuration</span></span> 

<span data-ttu-id="ea387-143">Contoso siguió los pasos de [Configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md) para:</span><span class="sxs-lookup"><span data-stu-id="ea387-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="ea387-144">Asignar direcciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="ea387-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="ea387-145">Configurar la configuración de red</span><span class="sxs-lookup"><span data-stu-id="ea387-145">Configure network settings</span></span> 

- <span data-ttu-id="ea387-146">Configurar el servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="ea387-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="ea387-147">Configurar directivas de emergencia</span><span class="sxs-lookup"><span data-stu-id="ea387-147">Configure emergency policies</span></span> 

- <span data-ttu-id="ea387-148">Habilitar usuarios y sitios</span><span class="sxs-lookup"><span data-stu-id="ea387-148">Enable users and sites</span></span> 

- <span data-ttu-id="ea387-149">Probar llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="ea387-149">Test emergency calling</span></span> 

<span data-ttu-id="ea387-150">Una vez configuradas las llamadas de emergencia dinámicas, Contoso necesitaba asignar la ubicación al usuario adecuado.</span><span class="sxs-lookup"><span data-stu-id="ea387-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="ea387-151">Para agregar, cambiar o quitar una ubicación de emergencia para [su organización,](add-change-remove-emergency-location-organization.md) Contoso siguió los pasos de Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="ea387-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="ea387-152">Para crear lugares para edificios, pisos y oficinas, Contoso siguió los pasos de Agregar, cambiar o quitar un lugar para [una ubicación de emergencia.](add-change-remove-emergency-place-organization.md)</span><span class="sxs-lookup"><span data-stu-id="ea387-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="ea387-153">Para asignar una ubicación de emergencia, Contoso siguió los pasos de [Asignar o cambiar una ubicación de emergencia para un usuario.](assign-change-emergency-location-user.md)</span><span class="sxs-lookup"><span data-stu-id="ea387-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 