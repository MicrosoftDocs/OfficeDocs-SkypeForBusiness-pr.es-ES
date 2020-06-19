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
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786104"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="fb5eb-103">Caso práctico de Contoso: llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="fb5eb-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="fb5eb-104">Para comprender la disponibilidad de las llamadas de emergencia y la terminología relacionada con las llamadas de emergencia &mdash; , lugar, ubicación de emergencia y dirección registrada &mdash; contoso revisada [administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md) y [planificar y configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).</span><span class="sxs-lookup"><span data-stu-id="fb5eb-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="fb5eb-105">En Office 365, un usuario del plan de llamadas se habilita automáticamente para las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="fb5eb-106">Pero solo los usuarios del plan de llamadas de Estados Unidos pueden usar ubicaciones dinámicas para el enrutamiento de llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="fb5eb-107">Para el enrutamiento directo, contoso aprendió que es necesaria una configuración adicional para enrutar llamadas de emergencia y posiblemente para conectividad de socios.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="fb5eb-108">El administrador debe configurar la conexión a un proveedor de servicios de enrutamiento de emergencia (ERSP) (Estados Unidos) o configurar el controlador de borde de sesión (SBC) para una aplicación de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="fb5eb-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="fb5eb-109">Contoso tiene oficinas en los Estados Unidos y fuera de los Estados Unidos:</span><span class="sxs-lookup"><span data-stu-id="fb5eb-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="fb5eb-110">En los Estados Unidos, los usuarios del plan de llamadas de Contoso pueden usar ubicaciones dinámicas para el enrutamiento de llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="fb5eb-111">Fuera de los Estados Unidos, Contoso tiene algunos sitios que usan planes de llamadas y algunos sitios que están conectados al sistema telefónico a través del enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="fb5eb-112">Casos de uso de llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="fb5eb-112">Emergency calling use cases</span></span>

<span data-ttu-id="fb5eb-113">Después de decidir cómo contoso se conectará al sistema telefónico, contoso identificó los siguientes casos de uso de llamadas de emergencia:</span><span class="sxs-lookup"><span data-stu-id="fb5eb-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="fb5eb-114">Usuario del plan de llamadas en los Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="fb5eb-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="fb5eb-115">Usuario del plan de llamadas fuera de los Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="fb5eb-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="fb5eb-116">Usuario que se conecta al sistema telefónico a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fb5eb-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="fb5eb-117">Usuario del plan de llamadas en los Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="fb5eb-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="fb5eb-118">Existen requisitos para cuando el número de teléfono debe asociarse con una ubicación de emergencia.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="fb5eb-119">Para comprender estos requisitos, contoso revisó las [consideraciones para las llamadas a planes](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="fb5eb-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="fb5eb-120">En función de estos requisitos, contoso decidió asociar la ubicación con el número de teléfono cuando se asigna un número a un usuario de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="fb5eb-121">Usuario del plan de llamadas fuera de los Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="fb5eb-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="fb5eb-122">Para entender cuándo un número de teléfono debe asociarse a una ubicación de emergencia, contoso revisó las [consideraciones para las llamadas a planes](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="fb5eb-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="fb5eb-123">En función de los requisitos, contoso decidió lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb5eb-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="fb5eb-124">Contoso asociará la ubicación con el número de teléfono cuando se asigne un número a un usuario de Canadá.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="fb5eb-125">Contoso asignará una ubicación de emergencia cuando se adquiera el número de teléfono de Office 365 o cuando se transfiera un número de otro proveedor de servicios u operador.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="fb5eb-126">Usuario que se conecta al sistema telefónico a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fb5eb-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="fb5eb-127">Para planear la enrutamiento de emergencia para este caso de uso, contoso revisó las [consideraciones para el enrutamiento directo](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="fb5eb-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="fb5eb-128">Dado que los usuarios de enrutamiento directo no reciben llamadas de emergencia de la misma manera que los usuarios del plan de llamadas, contoso tuvo que decidir sobre cómo proporcionar llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="fb5eb-129">El enrutamiento directo se puede conectar a un proveedor de servicios de enrutamiento de emergencia (ERSP).</span><span class="sxs-lookup"><span data-stu-id="fb5eb-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="fb5eb-130">El enrutamiento directo también puede tener un SBC que incluya un número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="fb5eb-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="fb5eb-131">Consideraciones sobre el proveedor de servicios de enrutamiento de emergencia (ERSP)</span><span class="sxs-lookup"><span data-stu-id="fb5eb-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="fb5eb-132">Los proveedores de servicios de enrutamiento de emergencia (ERSPs) pueden enrutar llamadas de emergencia automáticamente según la ubicación de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="fb5eb-133">Si un proveedor de servicios de enrutamiento de emergencia se integra en una implementación de enrutamiento directo, las llamadas de emergencia con una ubicación de adquisición dinámica se dirigirán automáticamente al punto de respuesta de seguridad pública (PSAP) que atiende esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="fb5eb-134">Para determinar la ubicación actual del usuario antes de conectar la llamada al centro de distribución adecuado, deberás hacer llamadas de emergencia sin una ubicación de adquisición dinámica</span><span class="sxs-lookup"><span data-stu-id="fb5eb-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="fb5eb-135">Consideraciones de ELIN</span><span class="sxs-lookup"><span data-stu-id="fb5eb-135">ELIN considerations</span></span>

<span data-ttu-id="fb5eb-136">Si una aplicación de ELIN de SBC se integra en una implementación de enrutamiento directo, deben realizarse pasos de configuración adicionales para asociar las direcciones de emergencia a los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="fb5eb-137">Contoso decidió usar controladores de borde de sesión que incluyen aplicaciones de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="fb5eb-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="fb5eb-138">Notificación del centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="fb5eb-138">Security desk notification</span></span>

<span data-ttu-id="fb5eb-139">La capacidad de notificar al escritorio cuando se realiza una llamada de emergencia está disponible tanto para los planes de llamadas de Microsoft como para el enrutamiento directo del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="fb5eb-140">Contoso revisó los detalles de la notificación del centro de seguridad para determinar si debe configurarse en su oficina.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="fb5eb-141">Contoso decidió usar la notificación del servicio de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="fb5eb-142">Configuración</span><span class="sxs-lookup"><span data-stu-id="fb5eb-142">Configuration</span></span> 

<span data-ttu-id="fb5eb-143">Contoso siguió los pasos de [configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md) a:</span><span class="sxs-lookup"><span data-stu-id="fb5eb-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="fb5eb-144">Asignar direcciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="fb5eb-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="fb5eb-145">Configurar las opciones de red</span><span class="sxs-lookup"><span data-stu-id="fb5eb-145">Configure network settings</span></span> 

- <span data-ttu-id="fb5eb-146">Configurar servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="fb5eb-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="fb5eb-147">Configurar directivas de emergencia</span><span class="sxs-lookup"><span data-stu-id="fb5eb-147">Configure emergency policies</span></span> 

- <span data-ttu-id="fb5eb-148">Habilitar usuarios y sitios</span><span class="sxs-lookup"><span data-stu-id="fb5eb-148">Enable users and sites</span></span> 

- <span data-ttu-id="fb5eb-149">Probar las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="fb5eb-149">Test emergency calling</span></span> 

<span data-ttu-id="fb5eb-150">Después de configurar las llamadas de emergencia dinámicas, contoso necesitaba asignar la ubicación al usuario correspondiente.</span><span class="sxs-lookup"><span data-stu-id="fb5eb-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="fb5eb-151">Para agregar, cambiar o quitar una ubicación de emergencia para su organización, contoso siguió los pasos indicados en [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="fb5eb-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="fb5eb-152">Para crear lugares para edificios, plantas y oficinas, contoso siguió los pasos indicados en [Agregar, cambiar o quitar un lugar para una ubicación de emergencia](add-change-remove-emergency-place-organization.md) .</span><span class="sxs-lookup"><span data-stu-id="fb5eb-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="fb5eb-153">Para asignar una ubicación de emergencia, contoso siguió los pasos que se indican en [asignar o cambiar una ubicación de emergencia para un usuario](assign-change-emergency-location-user.md).</span><span class="sxs-lookup"><span data-stu-id="fb5eb-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 