---
title: Caso práctico de Teams voice Contoso
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
description: Caso práctico de voz de Teams para una corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786104"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="55d25-103">Caso práctico Contoso: Llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="55d25-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="55d25-104">Para comprender la disponibilidad de las llamadas de emergencia y la terminología relacionada con las llamadas de emergencia: Dirección de emergencia, Lugar, Ubicación de emergencia y Dirección registrada, Contoso revisó Administrar llamadas de emergencia y Planear y configurar las llamadas de emergencia &mdash; &mdash; [dinámicas.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="55d25-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="55d25-105">En Office 365, se habilita automáticamente un usuario del plan de llamadas para llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="55d25-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="55d25-106">Pero solo los usuarios del plan de llamadas en Estados Unidos pueden usar ubicaciones dinámicas para enrutar llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="55d25-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="55d25-107">En el caso del enrutamiento directo, Contoso aprendió que se requiere configuración adicional para enrutar llamadas de emergencia y, posiblemente, para la conectividad con asociados.</span><span class="sxs-lookup"><span data-stu-id="55d25-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="55d25-108">El administrador debe configurar la conexión a un Proveedor de servicios de enrutamiento de emergencia (ERSP) (Estados Unidos) O configurar el controlador de borde de sesión (SBC) para una aplicación de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="55d25-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="55d25-109">Contoso tiene oficinas en los Estados Unidos y fuera de estos:</span><span class="sxs-lookup"><span data-stu-id="55d25-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="55d25-110">En los Estados Unidos, los usuarios del plan de llamadas Contoso pueden usar ubicaciones dinámicas para enrutar llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="55d25-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="55d25-111">Fuera de los Estados Unidos, Contoso tiene algunos sitios que usan planes de llamadas y algunos sitios que están conectados a Sistema telefónico a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="55d25-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="55d25-112">Casos de uso de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="55d25-112">Emergency calling use cases</span></span>

<span data-ttu-id="55d25-113">Después de decidir cómo contoso se conectará al sistema telefónico, Contoso identificó los siguientes casos de uso de las llamadas de emergencia:</span><span class="sxs-lookup"><span data-stu-id="55d25-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="55d25-114">Usuario del plan de llamadas en Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="55d25-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="55d25-115">Usuario del plan de llamadas fuera de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="55d25-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="55d25-116">Usuario que se conecta al sistema telefónico a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="55d25-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="55d25-117">Usuario del plan de llamadas en Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="55d25-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="55d25-118">Hay requisitos para cuando el número de teléfono debe estar asociado a una ubicación de emergencia.</span><span class="sxs-lookup"><span data-stu-id="55d25-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="55d25-119">Para entender estos requisitos, Contoso ha revisado [consideraciones para los planes de llamadas.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="55d25-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="55d25-120">Tras cumplir estos requisitos, Contoso decidió asociar la ubicación con el número de teléfono cuando se asignó un número a un usuario en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="55d25-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="55d25-121">Usuario del plan de llamadas fuera de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="55d25-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="55d25-122">Para entender cuándo un número de teléfono debe estar asociado a una ubicación de emergencia, Contoso revisó [consideraciones para planes de llamadas.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="55d25-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="55d25-123">En función de los requisitos, Contoso decidió lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55d25-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="55d25-124">Contoso asociará la ubicación con el número de teléfono cuando se asigne un número a un usuario de Canadá.</span><span class="sxs-lookup"><span data-stu-id="55d25-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="55d25-125">Contoso asignará una ubicación de emergencia cuando el número de teléfono se adquiera de Office 365 o cuando un número se transfiera de otro proveedor de servicios u operador.</span><span class="sxs-lookup"><span data-stu-id="55d25-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="55d25-126">Usuario que se conecta al sistema telefónico a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="55d25-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="55d25-127">Para planear el enrutamiento de emergencia para este caso de uso, Contoso revisó [las consideraciones de enrutamiento directo.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="55d25-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="55d25-128">Como los usuarios de enrutamiento directo no reciben llamadas de emergencia de la misma manera que los usuarios del plan de llamadas, Contoso tuvo que decidir cómo proporcionar llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="55d25-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="55d25-129">El enrutamiento directo se puede conectar a un proveedor de servicios de enrutamiento de emergencia (ERSP).</span><span class="sxs-lookup"><span data-stu-id="55d25-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="55d25-130">El enrutamiento directo también puede tener un SBC que incluya un número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="55d25-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="55d25-131">Consideraciones del Proveedor de servicios de enrutamiento de emergencia (ERSP)</span><span class="sxs-lookup"><span data-stu-id="55d25-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="55d25-132">Los proveedores de servicios de enrutamiento de emergencia (ERSP) pueden enrutar automáticamente las llamadas de emergencia en función de la ubicación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="55d25-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="55d25-133">Si se integra un proveedor de servicios de enrutamiento de emergencia en una implementación de enrutamiento directo, las llamadas de emergencia con una ubicación adquirida dinámicamente se enruta automáticamente al punto de respuesta de seguridad pública (PSAP) que sirve a esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="55d25-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="55d25-134">Las llamadas de emergencia sin una ubicación adquirida dinámicamente se pantallan primero para determinar la ubicación actual del usuario antes de conectar la llamada al centro de emergencias adecuado según la ubicación actualizada.</span><span class="sxs-lookup"><span data-stu-id="55d25-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="55d25-135">Consideraciones de ELIN</span><span class="sxs-lookup"><span data-stu-id="55d25-135">ELIN considerations</span></span>

<span data-ttu-id="55d25-136">Si una aplicación de ELIN SBC está integrada en una implementación de enrutamiento directo, es necesario seguir pasos de configuración adicionales para asociar las direcciones de emergencia con los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="55d25-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="55d25-137">Contoso ha decidido usar controladores de borde de sesión que incluyen aplicaciones de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="55d25-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="55d25-138">Notificación del servicio de seguridad</span><span class="sxs-lookup"><span data-stu-id="55d25-138">Security desk notification</span></span>

<span data-ttu-id="55d25-139">La capacidad de notificar al servicio de seguridad cuando se realiza una llamada de emergencia está disponible tanto para planes de llamadas de Microsoft como para enrutamiento directo de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="55d25-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="55d25-140">Contoso revisó los detalles de la notificación del servicio de seguridad para determinar si debería configurarse en sus oficinas.</span><span class="sxs-lookup"><span data-stu-id="55d25-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="55d25-141">Contoso ha decidido usar una notificación del servicio de seguridad.</span><span class="sxs-lookup"><span data-stu-id="55d25-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="55d25-142">Configuración</span><span class="sxs-lookup"><span data-stu-id="55d25-142">Configuration</span></span> 

<span data-ttu-id="55d25-143">Contoso siguió los pasos de [Configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md) para:</span><span class="sxs-lookup"><span data-stu-id="55d25-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="55d25-144">Asignar direcciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="55d25-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="55d25-145">Configurar las opciones de red</span><span class="sxs-lookup"><span data-stu-id="55d25-145">Configure network settings</span></span> 

- <span data-ttu-id="55d25-146">Configurar el servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="55d25-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="55d25-147">Configurar directivas de emergencia</span><span class="sxs-lookup"><span data-stu-id="55d25-147">Configure emergency policies</span></span> 

- <span data-ttu-id="55d25-148">Habilitar usuarios y sitios</span><span class="sxs-lookup"><span data-stu-id="55d25-148">Enable users and sites</span></span> 

- <span data-ttu-id="55d25-149">Probar llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="55d25-149">Test emergency calling</span></span> 

<span data-ttu-id="55d25-150">Una vez configuradas las llamadas de emergencia dinámicas, Contoso necesita asignar la ubicación al usuario adecuado.</span><span class="sxs-lookup"><span data-stu-id="55d25-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="55d25-151">Para agregar, cambiar o quitar una ubicación de emergencia de [su organización,](add-change-remove-emergency-location-organization.md) Contoso siguió los pasos descritos en Agregar, cambiar o quitar una ubicación de emergencia de su organización</span><span class="sxs-lookup"><span data-stu-id="55d25-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="55d25-152">Para crear lugares para edificios, pisos y oficinas, Contoso siguió los pasos de Agregar, cambiar o quitar un lugar [para una ubicación de emergencia.](add-change-remove-emergency-place-organization.md)</span><span class="sxs-lookup"><span data-stu-id="55d25-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="55d25-153">Para asignar una ubicación de emergencia, Contoso ha seguido los pasos indicados en [Asignar o cambiar una ubicación de emergencia para un usuario.](assign-change-emergency-location-user.md)</span><span class="sxs-lookup"><span data-stu-id="55d25-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 