---
title: Configurar las llamadas de emergencia dinámicas
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Configurar las llamadas de emergencia dinámicas
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516935"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a><span data-ttu-id="7b6d6-103">Planear y configurar las llamadas de emergencia dinámicas para los planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="7b6d6-103">Plan and configure dynamic emergency calling for Calling Plans</span></span>
<span data-ttu-id="7b6d6-104">Las llamadas de emergencia dinámicas para los planes de llamadas de Microsoft proporcionan la capacidad de configurar y enrutar llamadas de emergencia basadas en la ubicación actual del cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-104">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span>  <span data-ttu-id="7b6d6-105">La capacidad de llevar a cabo el enrutamiento automático para el correspondiente punto de respuesta de seguridad pública (PSAP) o para notificar personal de escritorio de seguridad varía según el país de uso del usuario de Teams.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-105">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

> [!Note] 
> <span data-ttu-id="7b6d6-106">Las llamadas de emergencia dinámicas actualmente solo están disponibles en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-106">Dynamic emergency calling is currently available only in the United States.</span></span> <span data-ttu-id="7b6d6-107">La notificación del centro de seguridad, sin embargo, es compatible con los límites de países.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-107">Security desk notification, however, is supported across country boundaries.</span></span>

<span data-ttu-id="7b6d6-108">**Dentro de los Estados Unidos**, puede configurar el enrutamiento dinámico de llamadas de emergencia de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7b6d6-108">**Within the United States**, you can configure dynamic emergency call routing as follows:</span></span>
  
- <span data-ttu-id="7b6d6-109">Si un cliente de Teams se encuentra en una ubicación de emergencia dinámica definida por el inquilino, las llamadas de emergencia de ese cliente se enrutan automáticamente al PSAP que atiende esa ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-109">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span>  

- <span data-ttu-id="7b6d6-110">Si un cliente de Teams no se encuentra en una ubicación de emergencia dinámica definida por el inquilino, las llamadas de emergencia de ese cliente las puede filtrar un centro de atención nacional para determinar la ubicación de la persona que llama antes de transferir la llamada a la PSAP que atiende a esa ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-110">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

<span data-ttu-id="7b6d6-111">Puede configurar la notificación del servicio de seguridad de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7b6d6-111">You can configure security desk notification as follows:</span></span>

- <span data-ttu-id="7b6d6-112">Si un cliente de Teams se encuentra en un sitio de red definido por el inquilino, se notificará a los miembros del grupo de seguridad configurados para ese sitio.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-112">If a Teams client is located at a tenant-defined network site, the security group members configured for that site will be notified.</span></span>

- <span data-ttu-id="7b6d6-113">Si un cliente de Teams no se encuentra en un sitio de red definido por el inquilino, se notificará a los miembros del grupo de seguridad configurados para el usuario.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-113">If a Teams client is not located at a tenant-defined network site, the security group members configured for the user will be notified.</span></span>

<span data-ttu-id="7b6d6-114">**Fuera de los Estados Unidos, las**llamadas de emergencia se dirigen a la PSAP que está asignada al número de teléfono asignado al usuario.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-114">**Outside of the United States**, emergency calls are routed to the PSAP that is mapped to the phone number assigned to the user.</span></span>  <span data-ttu-id="7b6d6-115">Algunos países, como el gran Reino Unido y Canadá, filtran las llamadas a nivel nacional antes de transferir a la persona que llama a la PSAP adecuada, mientras que otras se dirigen directamente a la PSAP, independientemente de dónde se encuentre el usuario en ese momento.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-115">Some countries, such as the Great Britain and Canada, screen the calls nationally before transferring the caller to the appropriate PSAP, while others route directly to the PSAP regardless of where the user is currently located.</span></span> 

<span data-ttu-id="7b6d6-116">Tenga en cuenta que puede configurar una notificación de servicio de seguridad dinámica para todos los usuarios del plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-116">Note that you can configure dynamic security desk notification for all Calling Plan users.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="7b6d6-117">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="7b6d6-117">Supported clients</span></span>

<span data-ttu-id="7b6d6-118">Actualmente se admiten los siguientes clientes.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-118">The following clients are currently supported.</span></span>  <span data-ttu-id="7b6d6-119">Vuelva a consultar a menudo para ver las actualizaciones de esta lista.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-119">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="7b6d6-120">Cliente de escritorio de Teams para Windows</span><span class="sxs-lookup"><span data-stu-id="7b6d6-120">Teams desktop client for Windows</span></span>
- <span data-ttu-id="7b6d6-121">Cliente de escritorio de Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="7b6d6-121">Teams desktop client for Mac</span></span>

## <a name="configure-dynamic-emergency-calling"></a><span data-ttu-id="7b6d6-122">Configurar las llamadas de emergencia dinámicas</span><span class="sxs-lookup"><span data-stu-id="7b6d6-122">Configure dynamic emergency calling</span></span>

<span data-ttu-id="7b6d6-123">Para configurar las llamadas de emergencia dinámicas, debe realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="7b6d6-123">To configure dynamic emergency calling, you need to perform the following tasks:</span></span>

- [<span data-ttu-id="7b6d6-124">Configurar direcciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="7b6d6-124">Configure emergency addresses</span></span>](#configure-emergency-addresses)
- [<span data-ttu-id="7b6d6-125">Configurar las opciones de red</span><span class="sxs-lookup"><span data-stu-id="7b6d6-125">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="7b6d6-126">Configurar servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="7b6d6-126">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="7b6d6-127">Configurar directivas de emergencia</span><span class="sxs-lookup"><span data-stu-id="7b6d6-127">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="7b6d6-128">Habilitar usuarios y sitios</span><span class="sxs-lookup"><span data-stu-id="7b6d6-128">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="7b6d6-129">Probar las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="7b6d6-129">Test emergency calling</span></span>](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a><span data-ttu-id="7b6d6-130">Configurar direcciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="7b6d6-130">Configure emergency addresses</span></span>

<span data-ttu-id="7b6d6-131">Para admitir el enrutamiento automatizado dentro de los Estados Unidos, debe configurar completamente la dirección cívica que forma parte de las ubicaciones de emergencia asignadas a los identificadores de red e incluir los códigos geográficas asociados.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-131">To support automated routing within the United States, you must fully configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="7b6d6-132">(No se pueden asignar direcciones de emergencia sin códigos geográficas a los identificadores de red necesarios para las ubicaciones dinámicas).</span><span class="sxs-lookup"><span data-stu-id="7b6d6-132">(Emergency addresses without geo-codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

- <span data-ttu-id="7b6d6-133">Si especifica una dirección de emergencia a través del centro de administración de Microsoft Teams, los códigos geográficas se incluyen automáticamente si se encuentra una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-133">If you enter an emergency address via the Microsoft Teams admin center, the geo codes are automatically included if a match is found.</span></span>

- <span data-ttu-id="7b6d6-134">Si no se encuentra ninguna coincidencia, tendrá la oportunidad de crear manualmente una dirección de emergencia.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-134">If a match is not automatically found, you will have the opportunity to manually create an emergency address.</span></span>  

<span data-ttu-id="7b6d6-135">Esto significa que si una dirección de emergencia existente está configurada para hacer llamadas de emergencia, debe volver a crearse la misma dirección para incluir los códigos geográficas.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-135">This means that if an existing emergency address is configured for emergency calling, the same address needs to be re-created to include the geo codes.</span></span>  <span data-ttu-id="7b6d6-136">Para distinguir entre las dos direcciones, debe incluir una descripción diferente.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-136">To distinguish between the two addresses, you should include a different description.</span></span> <span data-ttu-id="7b6d6-137">La nueva dirección de emergencia se puede asignar a los usuarios que tienen la dirección antigua.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-137">The new emergency address can be assigned to the users who have the old address.</span></span> <span data-ttu-id="7b6d6-138">Cuando se realiza una migración completa, la dirección anterior puede eliminarse.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-138">When fully migrated, the old address can be deleted.</span></span> 

<span data-ttu-id="7b6d6-139">Para obtener más información sobre cómo configurar las direcciones de emergencia, vea [¿Qué son las ubicaciones de emergencia, los lugares y el enrutamiento de llamadas?](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="7b6d6-139">For more information about configuring emergency addresses, see [What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>

### <a name="configure-network-settings"></a><span data-ttu-id="7b6d6-140">Configurar las opciones de red</span><span class="sxs-lookup"><span data-stu-id="7b6d6-140">Configure network settings</span></span>

<span data-ttu-id="7b6d6-141">Debe configurar las opciones de red para obtener dinámicamente una ubicación de emergencia usada para el enrutamiento de las llamadas de emergencia y, opcionalmente, para proporcionar una configuración dinámica de las notificaciones del equipo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-141">You need to configure network settings to dynamically obtain an emergency location used for routing emergency calls and, optionally, to provide dynamic configuration of security desk notifications.</span></span> <span data-ttu-id="7b6d6-142">La experiencia de llamadas de emergencia que deseas determinará qué configuración de red debe configurarse.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-142">The emergency calling experience desired will dictate which network settings need to be configured.</span></span> 

<span data-ttu-id="7b6d6-143">Tenga en cuenta las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="7b6d6-143">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="7b6d6-144">La IP de confianza contiene una colección de las direcciones IP externas de Internet de la red de la empresa y se usan para determinar si el extremo del usuario se encuentra dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-144">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="7b6d6-145">Las ubicaciones dinámicas solo se habilitarán si la IP externa del usuario coincide con una IP de la colección de IP de confianza.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-145">Dynamic locations will only be enabled if the user’s external IP matches an IP in the Trusted IP collection.</span></span>  <span data-ttu-id="7b6d6-146">Se puede establecer una coincidencia con las direcciones IP IPv4 o IPv6, y depende del formato del paquete IP que se envía a la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-146">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>

- <span data-ttu-id="7b6d6-147">Una región de red incluye una colección de sitios de red.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-147">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="7b6d6-148">Un sitio de red representa una ubicación en la que su organización tiene un valor físico, como una oficina, un conjunto de edificios o un campus.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-148">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="7b6d6-149">Estos sitios se definen como una colección de subredes IP.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-149">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="7b6d6-150">Una subred de red debe estar asociada a un sitio de red específico.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-150">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="7b6d6-151">La ubicación de un cliente se determina en función de la subred de la red y el sitio de red asociado.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-151">A client's location is determined based on the network subnet and the associated network site.</span></span>  


<span data-ttu-id="7b6d6-152">Para los usuarios del plan de llamadas:</span><span class="sxs-lookup"><span data-stu-id="7b6d6-152">For Calling Plan users:</span></span>

- <span data-ttu-id="7b6d6-153">Si se requiere la configuración dinámica de la notificación del escritorio de seguridad, debe configurar tanto las direcciones IP de confianza como los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-153">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="7b6d6-154">Si solo se necesitan ubicaciones dinámicas, debe configurar solo direcciones IP de confianza.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-154">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="7b6d6-155">Si no es necesario, no es necesario configurar la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-155">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="7b6d6-156">Para obtener más información, vea [configuración de la red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md), que describe cómo configurar las opciones de red.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-156">For more information, see [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md), which describes how to configure network settings.</span></span> <span data-ttu-id="7b6d6-157">(La información de este artículo se aplica a los planes de llamadas y al enrutamiento directo).</span><span class="sxs-lookup"><span data-stu-id="7b6d6-157">(The information in this article applies to both Calling Plans and Direct Routing.)</span></span>


### <a name="configure-location-information-service"></a><span data-ttu-id="7b6d6-158">Configurar servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="7b6d6-158">Configure Location Information Service</span></span>

<span data-ttu-id="7b6d6-159">Un cliente de Teams obtiene las direcciones de emergencia de las ubicaciones de emergencia asociadas a diferentes identificadores de red.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-159">A Teams client obtains emergency addresses from the emergency locations associated with different network identifiers.</span></span>  <span data-ttu-id="7b6d6-160">Se admiten las subredes y los puntos de acceso inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-160">Subnets and Wireless Access Points are both supported.</span></span> <span data-ttu-id="7b6d6-161">(La compatibilidad con el conmutador/puerto Ethernet está pendiente).</span><span class="sxs-lookup"><span data-stu-id="7b6d6-161">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="7b6d6-162">Para configurar el servicio de información de ubicación (LIS) con identificadores de red y ubicaciones de emergencia, use los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7b6d6-162">To configure the Location Information Service (LIS) with network identifiers and emergency locations, use the following cmdlets:</span></span>

- <span data-ttu-id="7b6d6-163">Get, Set, Remove-CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="7b6d6-163">Get, Set, Remove -CsOnlineLisPort</span></span>
- <span data-ttu-id="7b6d6-164">Get, Set, Remove-CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="7b6d6-164">Get, Set, Remove -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="7b6d6-165">Get, Set, Remove-CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="7b6d6-165">Get, Set, Remove -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="7b6d6-166">Get, Set, Remove-CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="7b6d6-166">Get, Set, Remove -CsOnlineLisWirelessAccessPoint</span></span> 

> [!Important] 
> <span data-ttu-id="7b6d6-167">Si se usan subredes como parte de sitios de red, deben redefinirse en el servicio de información de ubicación para representar ubicaciones dinámicas.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-167">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


### <a name="configure-emergency-policies"></a><span data-ttu-id="7b6d6-168">Configurar directivas de emergencia</span><span class="sxs-lookup"><span data-stu-id="7b6d6-168">Configure emergency policies</span></span>

<span data-ttu-id="7b6d6-169">Las directivas de emergencia determinan lo que sucede cuando un usuario de su organización hace una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-169">Emergency policies determine what happens when a user in your organization makes an emergency call.</span></span>  <span data-ttu-id="7b6d6-170">Puedes establecer a quién deseas notificar y cómo se les notifica cuando un usuario llama a servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-170">You can set who to notify and how they are notified when a user calls emergency services.</span></span> <span data-ttu-id="7b6d6-171">Por ejemplo, puede configurar opciones de directiva para notificar automáticamente al escritorio de seguridad de su organización y hacer que escuchen en llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-171">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>

<span data-ttu-id="7b6d6-172">Para administrar las directivas de emergencia, use los cmdlets de directiva New-, set-and-CsTeamsEmergencyCalling.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-172">You manage emergency policies by using the New-, Set- and Grant-CsTeamsEmergencyCalling Policy cmdlets.</span></span>  <span data-ttu-id="7b6d6-173">Para obtener más información, consulte [Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7b6d6-173">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>


### <a name="enable-users-and-sites"></a><span data-ttu-id="7b6d6-174">Habilitar usuarios y sitios</span><span class="sxs-lookup"><span data-stu-id="7b6d6-174">Enable users and sites</span></span>

<span data-ttu-id="7b6d6-175">Mientras que los usuarios del plan de llamadas se habilitan automáticamente para llamadas de emergencia, debe habilitar a los usuarios para recibir notificaciones de seguridad configurando la Directiva de llamadas de emergencia, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7b6d6-175">While Calling Plan users are automatically enabled for emergency calling, you must enable users for security desk notification by configuring the emergency calling policy as shown in the following example:</span></span>


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="7b6d6-176">También puede asignar la Directiva de llamadas de emergencia a un sitio de red como se muestra en el ejemplo siguiente, que asigna una directiva denominada "Directiva de llamadas de emergencia de Contoso 1" al sitio 1:</span><span class="sxs-lookup"><span data-stu-id="7b6d6-176">You can also assign the emergency calling policy to a network site as shown in the following example, which assigns a policy called "Contoso Emergency Calling Policy 1" to Site 1:</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="7b6d6-177">Si ha asignado una directiva de llamadas de emergencia a un sitio de red y a un usuario, y si ese usuario se encuentra en el sitio de red, la directiva asignada al sitio de red reemplaza la directiva asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-177">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


### <a name="test-emergency-calling"></a><span data-ttu-id="7b6d6-178">Probar las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="7b6d6-178">Test emergency calling</span></span>

<span data-ttu-id="7b6d6-179">Para probar las llamadas de emergencia en los Estados Unidos, use el número de emergencia de prueba predefinido 933.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-179">To test emergency calling in the United States, use the predefined test emergency number 933.</span></span>  <span data-ttu-id="7b6d6-180">Este número se enruta a un bot, que después vuelve a devolverle el número de teléfono de la persona que llama (identificación de la línea de llamada), la dirección o ubicación de emergencia, y si la llamada se dirige automáticamente a la PSAP o se ha superpuesto.</span><span class="sxs-lookup"><span data-stu-id="7b6d6-180">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call is automatically routed to the PSAP or screened first.</span></span>  