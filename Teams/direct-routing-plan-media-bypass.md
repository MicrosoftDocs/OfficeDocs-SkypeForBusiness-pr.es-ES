---
title: Planear desvío de medios con enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Lea este tema para obtener información sobre cómo planear la omisión de medios con enrutamiento directo de sistema telefónico.
ms.openlocfilehash: cdfeb5313416730c703a1d0f10e2c7ccdddee1cc
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572162"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="aae6e-103">Planear desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="aae6e-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="aae6e-104">Acerca de la omisión de elementos multimedia con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="aae6e-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="aae6e-105">La omisión de elementos multimedia le permite acortar la ruta de acceso al tráfico multimedia y reducir el número de saltos en tránsito para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="aae6e-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="aae6e-106">Con la omisión de medios, los medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente, en lugar de enviarlo a través del sistema telefónico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aae6e-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="aae6e-107">Para configurar la omisión de medios, la SBC y el cliente deben estar en la misma ubicación o red.</span><span class="sxs-lookup"><span data-stu-id="aae6e-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="aae6e-108">Puede controlar la omisión de elementos multimedia para cada SBC con el comando **set-CSOnlinePSTNGateway** con el parámetro **-MediaBypass** establecido en true o false.</span><span class="sxs-lookup"><span data-stu-id="aae6e-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="aae6e-109">Si habilita la omisión de medios, esto no significa que todo el tráfico multimedia permanecerá dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="aae6e-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="aae6e-110">En este artículo se describe el flujo de llamadas en diferentes escenarios.</span><span class="sxs-lookup"><span data-stu-id="aae6e-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="aae6e-111">Los diagramas siguientes ilustran la diferencia en el flujo de llamadas con y sin omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="aae6e-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="aae6e-112">Sin omisión de medios, cuando un cliente realiza o recibe una llamada, tanto la señalización como el flujo de medios entre el SBC, el sistema telefónico de Microsoft y el cliente de equipos, tal y como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="aae6e-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![Muestra el flujo de señales y medios sin omisión de medios](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="aae6e-114">Pero supongamos que un usuario está en el mismo edificio o en la misma red que la SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="aae6e-115">Por ejemplo, supongamos que un usuario de un edificio de Frankfurt hace una llamada a un usuario de la RTC:</span><span class="sxs-lookup"><span data-stu-id="aae6e-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="aae6e-116">**Sin omisión de medios**, los medios se transmiten a través de Amsterdam o Dublín (donde se implementan los centros de datos de Microsoft) y de vuelta al SBC en Frankfurt.</span><span class="sxs-lookup"><span data-stu-id="aae6e-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="aae6e-117">El centro de recursos de Europa está seleccionado porque SBC está en Europa y Microsoft usa el centro de la Datacenter más cercano a SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="aae6e-118">A pesar de que este enfoque no afecta la calidad de las llamadas debido a la optimización del flujo de tráfico dentro de las redes Microsoft en la mayoría de los lugares, el tráfico tiene un bucle innecesario.</span><span class="sxs-lookup"><span data-stu-id="aae6e-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="aae6e-119">**Con la omisión de elementos multimedia**, los medios se mantienen directamente entre el usuario de los equipos y el SBC, tal y como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="aae6e-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![Muestra el flujo de señales y medios con omisión de medios](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="aae6e-121">La omisión de multimedia aprovecha los protocolos denominados establecimiento de conectividad interactiva (ICE) en el cliente de Teams y ICE Lite en la SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="aae6e-122">Estos protocolos permiten el enrutamiento directo para usar la ruta de medios más directa para una calidad óptima.</span><span class="sxs-lookup"><span data-stu-id="aae6e-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="aae6e-123">ICE y ICE Lite son estándares de WebRTC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="aae6e-124">Para obtener información detallada sobre estos protocolos, consulte RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="aae6e-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="aae6e-125">Planificación de flujo de llamadas y firewall</span><span class="sxs-lookup"><span data-stu-id="aae6e-125">Call flow and firewall planning</span></span>

<span data-ttu-id="aae6e-126">El flujo de llamadas y el plan de Firewall depende de si el usuario tiene acceso directo a la dirección IP pública de SBC y si el usuario está dentro o fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="aae6e-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="aae6e-127">Flujo de llamadas si el usuario tiene acceso directo a la dirección IP pública de la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="aae6e-128">Si el usuario tiene acceso directo a la dirección IP pública de la SBC, el flujo de llamadas es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="aae6e-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="aae6e-129">Para la omisión de elementos multimedia, el cliente de Teams debe tener acceso a la dirección IP pública de SBC incluso desde una red interna.</span><span class="sxs-lookup"><span data-stu-id="aae6e-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="aae6e-130">Si no desea usar medios directos, los medios pueden fluir a través de transmisiones de transporte.</span><span class="sxs-lookup"><span data-stu-id="aae6e-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="aae6e-131">Esta es la solución recomendada cuando un usuario está en el mismo edificio o en la misma red que el SBC, quite los componentes de la nube de Microsoft de la ruta de medios.</span><span class="sxs-lookup"><span data-stu-id="aae6e-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="aae6e-132">La señalización siempre fluye a través de la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aae6e-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="aae6e-133">El siguiente diagrama muestra el flujo de llamadas cuando la omisión de elementos multimedia está habilitada, el cliente es interno y el cliente puede comunicarse con la dirección IP pública de la SBC (medios directos):</span><span class="sxs-lookup"><span data-stu-id="aae6e-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="aae6e-134">Las flechas y los valores numéricos de los trazados se ajustan al artículo [flujos de llamada de Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="aae6e-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="aae6e-135">La señalización del SIP siempre tiene las rutas 4 y 4 (según la dirección del tráfico).</span><span class="sxs-lookup"><span data-stu-id="aae6e-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="aae6e-136">El medio permanece local y toma la ruta de acceso 5B.</span><span class="sxs-lookup"><span data-stu-id="aae6e-136">Media stays local and takes path 5b.</span></span>

![Muestra el flujo de llamadas con omisión de medios habilitado, el cliente es interno](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="aae6e-138">Flujo de llamadas si el usuario no tiene acceso a la dirección IP pública de la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="aae6e-139">A continuación, se describe el flujo de llamadas si el usuario no tiene acceso a la dirección IP pública de la SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="aae6e-140">Por ejemplo, supongamos que el usuario es externo y el administrador de inquilinos decidió no abrir la dirección IP pública de SBC a todos los usuarios de Internet, pero solo a la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aae6e-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="aae6e-141">Los componentes internos del tráfico pueden fluir a través de los transmisores de transporte de los equipos.</span><span class="sxs-lookup"><span data-stu-id="aae6e-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="aae6e-142">Esta es la configuración recomendada para los usuarios de fuera de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="aae6e-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="aae6e-143">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aae6e-143">Consider the following:</span></span>

- <span data-ttu-id="aae6e-144">Se usan los transmisores de transporte de Teams.</span><span class="sxs-lookup"><span data-stu-id="aae6e-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="aae6e-145">Para la omisión de medios, Microsoft usa una versión de los relés de transporte que requiere que se abran los puertos 50 000 a 59 999 entre los equipos de transporte de transporte y la SBC (en el futuro se planea ir a la versión que solo requiere puertos 3478 y 3479).</span><span class="sxs-lookup"><span data-stu-id="aae6e-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="aae6e-146">Para fines de optimización de multimedia, Microsoft recomienda abrir la dirección IP pública de SBC solo para los grupos de transporte de transporte.</span><span class="sxs-lookup"><span data-stu-id="aae6e-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="aae6e-147">Para los clientes fuera de la red corporativa, Microsoft recomienda usar relés de transporte en lugar de alcanzar directamente la dirección IP pública de SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="aae6e-148">El siguiente diagrama muestra el flujo de llamadas cuando la omisión de medios está habilitada, el cliente es externo y el cliente no puede comunicarse con la dirección IP pública del controlador de borde de la sesión (los medios son retransmitidos por la retransmisión de transporte de Teams).</span><span class="sxs-lookup"><span data-stu-id="aae6e-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="aae6e-149">Las flechas y los valores numéricos de los trazados se ajustan al artículo [flujos de llamada de Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="aae6e-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="aae6e-150">Los medios se retransmiten a través de las rutas 3, 3 ', 4 y 4 '.</span><span class="sxs-lookup"><span data-stu-id="aae6e-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![Muestra el flujo de llamadas si el usuario no tiene acceso a la IP pública de la SBC](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="aae6e-152">Flujo de llamadas si un usuario está fuera de la red y tiene acceso a la IP pública de la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="aae6e-153">Esta no es una configuración recomendada porque no aprovecha las retransmisiones de transporte de Teams.</span><span class="sxs-lookup"><span data-stu-id="aae6e-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="aae6e-154">En su lugar, debe considerar el escenario anterior en el que el usuario no tiene acceso a la dirección IP pública de SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="aae6e-155">El siguiente diagrama muestra el flujo de llamadas cuando la omisión de elementos multimedia está habilitada, el cliente es externo y el cliente puede comunicarse con la dirección IP pública de la SBC (soporte directo).</span><span class="sxs-lookup"><span data-stu-id="aae6e-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="aae6e-156">Las flechas y los valores numéricos de los trazados se ajustan al artículo [flujos de llamada de Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="aae6e-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="aae6e-157">La señalización SIP siempre toma las rutas 3 y 3 ' (según la dirección del tráfico).</span><span class="sxs-lookup"><span data-stu-id="aae6e-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="aae6e-158">Los flujos multimedia usan la ruta 2.</span><span class="sxs-lookup"><span data-stu-id="aae6e-158">Media flows using path 2.</span></span>

![Muestra el flujo de llamadas si el usuario no tiene acceso a la IP pública de la SBC](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="aae6e-160">Uso de procesadores de medios y transmisiones de transporte</span><span class="sxs-lookup"><span data-stu-id="aae6e-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="aae6e-161">Hay dos componentes en la nube de Microsoft que pueden estar en la ruta de tráfico de multimedia: procesadores de medios y transmisiones de transporte.</span><span class="sxs-lookup"><span data-stu-id="aae6e-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="aae6e-162">El procesador multimedia es un componente público que controla los elementos multimedia en casos de no omisión y controla medios para las aplicaciones de voz.</span><span class="sxs-lookup"><span data-stu-id="aae6e-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="aae6e-163">Los procesadores multimedia siempre están en la ruta de acceso para las llamadas sin ignorar del usuario final, pero nunca en la ruta de acceso para las llamadas omitidas.</span><span class="sxs-lookup"><span data-stu-id="aae6e-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="aae6e-164">Los procesadores de medios siempre están en la ruta de todas las aplicaciones de voz, como estacionamiento de llamadas, operador automático de la organización y colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="aae6e-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="aae6e-165">La retransmisión de transporte se usa para conectarse al servicio de transporte más cercano para enviar tráfico en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="aae6e-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="aae6e-166">Los relés de transporte pueden estar o no en la ruta de acceso para las llamadas omitidas, que proceden de o se destinan a usuarios finales, en función de dónde se encuentra el usuario y de la configuración de la red.</span><span class="sxs-lookup"><span data-stu-id="aae6e-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="aae6e-167">En el siguiente diagrama se muestran dos flujos de llamada: uno con la omisión de elementos multimedia habilitado y el segundo con omisión de medios deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="aae6e-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="aae6e-168">Nota el diagrama solo ilustra el tráfico que se origina en los usuarios finales o que se destinan a ellos.</span><span class="sxs-lookup"><span data-stu-id="aae6e-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="aae6e-169">El controlador de medios es un microservicio en Azure que asigna procesadores de medios y crea ofertas de protocolo de descripción de sesiones (SDP).</span><span class="sxs-lookup"><span data-stu-id="aae6e-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="aae6e-170">El proxy SIP es un componente que traduce las señales de REST HTTP usadas en Teams a SIP.</span><span class="sxs-lookup"><span data-stu-id="aae6e-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![Muestra los flujos de llamadas con omisión de medios habilitados y deshabilitados](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="aae6e-172">En la tabla siguiente se resume la diferencia entre los procesadores multimedia y los relés de transporte.</span><span class="sxs-lookup"><span data-stu-id="aae6e-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="aae6e-173">Procesadores de medios</span><span class="sxs-lookup"><span data-stu-id="aae6e-173">Media Processors</span></span> | <span data-ttu-id="aae6e-174">Transmisiones de transporte</span><span class="sxs-lookup"><span data-stu-id="aae6e-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="aae6e-175">En la ruta multimedia de las llamadas no omitidas para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="aae6e-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="aae6e-176">Constantemente</span><span class="sxs-lookup"><span data-stu-id="aae6e-176">Always</span></span> | <span data-ttu-id="aae6e-177">Sin</span><span class="sxs-lookup"><span data-stu-id="aae6e-177">Never</span></span> | 
<span data-ttu-id="aae6e-178">En la ruta multimedia de las llamadas omitidas para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="aae6e-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="aae6e-179">Sin</span><span class="sxs-lookup"><span data-stu-id="aae6e-179">Never</span></span> | <span data-ttu-id="aae6e-180">Si el cliente no puede alcanzar la SBC en la dirección IP pública</span><span class="sxs-lookup"><span data-stu-id="aae6e-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="aae6e-181">En la ruta multimedia de las aplicaciones de voz</span><span class="sxs-lookup"><span data-stu-id="aae6e-181">In media path for voice applications</span></span> | <span data-ttu-id="aae6e-182">Constantemente</span><span class="sxs-lookup"><span data-stu-id="aae6e-182">Always</span></span> | <span data-ttu-id="aae6e-183">Sin</span><span class="sxs-lookup"><span data-stu-id="aae6e-183">Never</span></span> | 
<span data-ttu-id="aae6e-184">Puede realizar transcodificación (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="aae6e-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="aae6e-185">Sí</span><span class="sxs-lookup"><span data-stu-id="aae6e-185">Yes</span></span> | <span data-ttu-id="aae6e-186">No, solo retransmite audio entre puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="aae6e-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="aae6e-187">Cantidad de instancias en todo el mundo y ubicación</span><span class="sxs-lookup"><span data-stu-id="aae6e-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="aae6e-188">8 total: 2 en Oriente de EE. UU. y oeste; 2 en Amsterdam y Dublín; 2 en Hong Kong y Singapur; 2 en Japón (se agrega en Q1CY2019)</span><span class="sxs-lookup"><span data-stu-id="aae6e-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan (being added in Q1CY2019)</span></span>  | <span data-ttu-id="aae6e-189">Multiple</span><span class="sxs-lookup"><span data-stu-id="aae6e-189">Multiple</span></span>

<span data-ttu-id="aae6e-190">El intervalo IP es 52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254).</span><span class="sxs-lookup"><span data-stu-id="aae6e-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="aae6e-191">\*Explicación de transcodificación:</span><span class="sxs-lookup"><span data-stu-id="aae6e-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="aae6e-192">El procesador multimedia es B2BUA, lo que significa que puede cambiar un códec (por ejemplo, seda del cliente de Teams al panel de administración y G. 711 entre MP y SBC).</span><span class="sxs-lookup"><span data-stu-id="aae6e-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="aae6e-193">Los relés de transporte no son B2BUA, lo que significa que el códec nunca cambia entre el cliente y SBC, aunque el tráfico fluya por medio de retransmisiones.</span><span class="sxs-lookup"><span data-stu-id="aae6e-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="aae6e-194">Uso de los equipos de transporte de equipos en escenarios de escalado si el tronco está configurado para la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="aae6e-194">Use of Teams Transport Relays in escalation scenarios if trunk is configured for media bypass</span></span>

<span data-ttu-id="aae6e-195">Los transmisores de transporte de los equipos siempre están en la ruta multimedia en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="aae6e-195">Teams Transport Relays are always in the media path in the following scenarios:</span></span>

- <span data-ttu-id="aae6e-196">La llamada se transfiere de 1:1 a una llamada grupal</span><span class="sxs-lookup"><span data-stu-id="aae6e-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="aae6e-197">La llamada va a un usuario de equipos federados</span><span class="sxs-lookup"><span data-stu-id="aae6e-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="aae6e-198">La llamada se desvía o se transfiere a un usuario de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="aae6e-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="aae6e-199">Asegúrese de que su SBC tenga acceso a los relés de transporte como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="aae6e-199">Ensure your SBC has access to the Transport Relays as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="aae6e-200">Señalización SIP: FQDN</span><span class="sxs-lookup"><span data-stu-id="aae6e-200">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="aae6e-201">Para las señales SIP, los requisitos de FQDN y firewall son los mismos que para los casos no omitidos.</span><span class="sxs-lookup"><span data-stu-id="aae6e-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="aae6e-202">El enrutamiento directo se ofrece en los siguientes entornos de Office 365:</span><span class="sxs-lookup"><span data-stu-id="aae6e-202">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="aae6e-203">Office 365</span><span class="sxs-lookup"><span data-stu-id="aae6e-203">Office 365</span></span>
- <span data-ttu-id="aae6e-204">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="aae6e-204">Office 365 GCC</span></span>
- <span data-ttu-id="aae6e-205">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="aae6e-205">Office 365 GCC High</span></span>
- <span data-ttu-id="aae6e-206">Office 365 DoD más información sobre los [entornos gubernamentales de office 365 y de EE. UU.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) , como GCC, GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="aae6e-206">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="aae6e-207">Entornos de Office 365 y Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="aae6e-207">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="aae6e-208">Los puntos de conexión para el enrutamiento directo son los tres FQDN siguientes:</span><span class="sxs-lookup"><span data-stu-id="aae6e-208">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="aae6e-209">**SIP.pstnhub.Microsoft.com** (FQDN global) debe probarse en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="aae6e-209">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="aae6e-210">Cuando la SBC envía una solicitud para resolver este nombre, los servidores DNS de Microsoft Azure devuelven una dirección IP que apunta al centro de información principal de Azure asignado a SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-210">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="aae6e-211">La asignación se basa en las métricas de rendimiento de los centros de trabajo y la proximidad geográfica a la SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-211">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="aae6e-212">La dirección IP devuelta corresponde al FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="aae6e-212">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="aae6e-213">**SIP2.pstnhub.Microsoft.com** : FQDN secundario: se asigna geográficamente a la segunda región prioritaria.</span><span class="sxs-lookup"><span data-stu-id="aae6e-213">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="aae6e-214">**sip3.pstnhub.Microsoft.com** – terciario FQDN: se asigna geográficamente a la tercera región prioritaria.</span><span class="sxs-lookup"><span data-stu-id="aae6e-214">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="aae6e-215">Debe colocar estos tres FQDN para:</span><span class="sxs-lookup"><span data-stu-id="aae6e-215">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="aae6e-216">Proporciona una experiencia óptima (menos cargadas y más cercana al centro de proceso de la la de SBC asignado consultando el primer FQDN).</span><span class="sxs-lookup"><span data-stu-id="aae6e-216">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="aae6e-217">Proporcione conmutación por error cuando se establezca una conexión de SBC a un centro de información que esté experimentando un problema temporal.</span><span class="sxs-lookup"><span data-stu-id="aae6e-217">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="aae6e-218">Para obtener más información, vea mecanismo de conmutación por error a continuación.</span><span class="sxs-lookup"><span data-stu-id="aae6e-218">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="aae6e-219">Los FQDN **SIP.pstnhub.Microsoft.com**, **SIP2.pstnhub.Microsoft.com**y **sip3.pstnhub.Microsoft.com** se resolverán en una de las siguientes direcciones IP:</span><span class="sxs-lookup"><span data-stu-id="aae6e-219">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="aae6e-220">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="aae6e-220">52.114.148.0</span></span>
- <span data-ttu-id="aae6e-221">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="aae6e-221">52.114.132.46</span></span>
- <span data-ttu-id="aae6e-222">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="aae6e-222">52.114.75.24</span></span>
- <span data-ttu-id="aae6e-223">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="aae6e-223">52.114.76.76</span></span>
- <span data-ttu-id="aae6e-224">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="aae6e-224">52.114.7.24</span></span>
- <span data-ttu-id="aae6e-225">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="aae6e-225">52.114.14.70</span></span>

<span data-ttu-id="aae6e-226">Necesitas abrir puertos para todas estas direcciones IP en tu firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="aae6e-226">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="aae6e-227">Si su Firewall admite nombres DNS, el FQDN **SIP-ALL.pstnhub.Microsoft.com** se resuelve en todas estas direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="aae6e-227">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="aae6e-228">Entorno DoD de Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="aae6e-228">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="aae6e-229">El punto de conexión para enrutamiento directo es el siguiente FQDN:</span><span class="sxs-lookup"><span data-stu-id="aae6e-229">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="aae6e-230">**SIP.pstnhub.DoD.Teams.Microsoft.US** : FQDN global.</span><span class="sxs-lookup"><span data-stu-id="aae6e-230">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="aae6e-231">Puesto que el entorno de Office 365 DoD solo existe en los centros de datos de los Estados Unidos, no hay FQDN secundarios ni terciarios.</span><span class="sxs-lookup"><span data-stu-id="aae6e-231">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="aae6e-232">Los FQDN-sip.pstnhub.dod.teams.microsoft.us se resolverán en una de las siguientes direcciones IP:</span><span class="sxs-lookup"><span data-stu-id="aae6e-232">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="aae6e-233">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="aae6e-233">52.127.64.33</span></span>
- <span data-ttu-id="aae6e-234">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="aae6e-234">52.127.68.34</span></span>

<span data-ttu-id="aae6e-235">Necesitas abrir puertos para todas estas direcciones IP en tu firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="aae6e-235">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="aae6e-236">Si su Firewall admite nombres DNS, el FQDN sip.pstnhub.dod.teams.microsoft.us se resuelve en todas estas direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="aae6e-236">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="aae6e-237">Office 365 GCC de gran entorno</span><span class="sxs-lookup"><span data-stu-id="aae6e-237">Office 365 GCC High environment</span></span>

<span data-ttu-id="aae6e-238">El punto de conexión para enrutamiento directo es el siguiente FQDN:</span><span class="sxs-lookup"><span data-stu-id="aae6e-238">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="aae6e-239">**SIP.pstnhub.gov.Teams.Microsoft.US** : FQDN global.</span><span class="sxs-lookup"><span data-stu-id="aae6e-239">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="aae6e-240">Puesto que el entorno alto de GCC solo existe en los centros de datos de los Estados Unidos, no hay FQDN secundarios ni terciarios.</span><span class="sxs-lookup"><span data-stu-id="aae6e-240">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="aae6e-241">Los FQDN-sip.pstnhub.gov.teams.microsoft.us se resolverán en una de las siguientes direcciones IP:</span><span class="sxs-lookup"><span data-stu-id="aae6e-241">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="aae6e-242">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="aae6e-242">52.127.88.59</span></span>
- <span data-ttu-id="aae6e-243">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="aae6e-243">52.127.92.64</span></span>

<span data-ttu-id="aae6e-244">Necesitas abrir puertos para todas estas direcciones IP en tu firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="aae6e-244">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="aae6e-245">Si su Firewall admite nombres DNS, el FQDN sip.pstnhub.gov.teams.microsoft.us se resuelve en todas estas direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="aae6e-245">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="aae6e-246">Señalización SIP: puertos</span><span class="sxs-lookup"><span data-stu-id="aae6e-246">SIP Signaling: Ports</span></span>

<span data-ttu-id="aae6e-247">Los requisitos de puerto son los mismos para todos los entornos de Office 365 donde se ofrece enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="aae6e-247">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="aae6e-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="aae6e-248">Office 365</span></span>
- <span data-ttu-id="aae6e-249">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="aae6e-249">Office 365 GCC</span></span>
- <span data-ttu-id="aae6e-250">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="aae6e-250">Office 365 GCC High</span></span>
- <span data-ttu-id="aae6e-251">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="aae6e-251">Office 365 DoD</span></span>

<span data-ttu-id="aae6e-252">Debe usar los siguientes puertos:</span><span class="sxs-lookup"><span data-stu-id="aae6e-252">You must use the following ports:</span></span>

| <span data-ttu-id="aae6e-253">Transmisión</span><span class="sxs-lookup"><span data-stu-id="aae6e-253">Traffic</span></span> | <span data-ttu-id="aae6e-254">De</span><span class="sxs-lookup"><span data-stu-id="aae6e-254">From</span></span> | <span data-ttu-id="aae6e-255">Hasta</span><span class="sxs-lookup"><span data-stu-id="aae6e-255">To</span></span> | <span data-ttu-id="aae6e-256">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="aae6e-256">Source port</span></span> | <span data-ttu-id="aae6e-257">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="aae6e-257">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="aae6e-258">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="aae6e-258">SIP/TLS</span></span>| <span data-ttu-id="aae6e-259">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="aae6e-259">SIP Proxy</span></span> | <span data-ttu-id="aae6e-260">SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-260">SBC</span></span> | <span data-ttu-id="aae6e-261">1024-65535</span><span class="sxs-lookup"><span data-stu-id="aae6e-261">1024 - 65535</span></span> | <span data-ttu-id="aae6e-262">Definido en la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-262">Defined on the SBC</span></span> |
| <span data-ttu-id="aae6e-263">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="aae6e-263">SIP/TLS</span></span> | <span data-ttu-id="aae6e-264">SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-264">SBC</span></span> | <span data-ttu-id="aae6e-265">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="aae6e-265">SIP Proxy</span></span> | <span data-ttu-id="aae6e-266">Definido en la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-266">Defined on the SBC</span></span> | <span data-ttu-id="aae6e-267">5061</span><span class="sxs-lookup"><span data-stu-id="aae6e-267">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="aae6e-268">Tráfico de medios: IP y intervalos de Puerto</span><span class="sxs-lookup"><span data-stu-id="aae6e-268">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="aae6e-269">El tráfico multimedia fluye entre el cliente de SBC y Teams si está disponible una conexión directa o a través de los equipos de transporte de transporte si el cliente no puede comunicarse con el SBC mediante la dirección IP pública.</span><span class="sxs-lookup"><span data-stu-id="aae6e-269">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="aae6e-270">Requisitos para el tráfico de medios directos (entre el cliente de Teams y el SBC)</span><span class="sxs-lookup"><span data-stu-id="aae6e-270">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="aae6e-271">El cliente debe tener acceso a los puertos especificados (vea la tabla) en la dirección IP pública de SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-271">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="aae6e-272">Nota: Si el cliente se encuentra en una red interna, los medios fluyen a la dirección IP pública de la SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-272">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="aae6e-273">Puede configurar hairpinning en su dispositivo NAT para que el tráfico nunca salga del equipo de red empresarial.</span><span class="sxs-lookup"><span data-stu-id="aae6e-273">You can configure hairpinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="aae6e-274">Transmisión</span><span class="sxs-lookup"><span data-stu-id="aae6e-274">Traffic</span></span> | <span data-ttu-id="aae6e-275">De</span><span class="sxs-lookup"><span data-stu-id="aae6e-275">From</span></span> | <span data-ttu-id="aae6e-276">Hasta</span><span class="sxs-lookup"><span data-stu-id="aae6e-276">To</span></span> | <span data-ttu-id="aae6e-277">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="aae6e-277">Source port</span></span> | <span data-ttu-id="aae6e-278">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="aae6e-278">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="aae6e-279">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="aae6e-279">UDP/SRTP</span></span> | <span data-ttu-id="aae6e-280">Cliente</span><span class="sxs-lookup"><span data-stu-id="aae6e-280">Client</span></span> | <span data-ttu-id="aae6e-281">SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-281">SBC</span></span> | <span data-ttu-id="aae6e-282">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="aae6e-282">50 000 – 50 019</span></span>  | <span data-ttu-id="aae6e-283">Definido en la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-283">Defined on the SBC</span></span> |
| <span data-ttu-id="aae6e-284">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="aae6e-284">UDP/SRTP</span></span> | <span data-ttu-id="aae6e-285">SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-285">SBC</span></span> | <span data-ttu-id="aae6e-286">Cliente</span><span class="sxs-lookup"><span data-stu-id="aae6e-286">Client</span></span> | <span data-ttu-id="aae6e-287">Definido en la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-287">Defined on the SBC</span></span> | <span data-ttu-id="aae6e-288">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="aae6e-288">50 000 – 50 019</span></span>  |


<span data-ttu-id="aae6e-289">Nota: Si tiene un dispositivo de red que traduce los puertos de origen del cliente, asegúrese de que los puertos traducidos estén abiertos entre el equipo de red y el SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-289">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="aae6e-290">Requisitos para usar transmisiones de transporte</span><span class="sxs-lookup"><span data-stu-id="aae6e-290">Requirements for using Transport Relays</span></span>

<span data-ttu-id="aae6e-291">Los relés de transporte están en el mismo intervalo que los procesadores de medios (para casos de no omisión):</span><span class="sxs-lookup"><span data-stu-id="aae6e-291">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="aae6e-292">Entornos de Office 365 y Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="aae6e-292">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="aae6e-293">-52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="aae6e-293">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="aae6e-294">Entorno DoD de Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="aae6e-294">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="aae6e-295">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="aae6e-295">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="aae6e-296">Office 365 GCC de gran entorno</span><span class="sxs-lookup"><span data-stu-id="aae6e-296">Office 365 GCC High environment</span></span>

- <span data-ttu-id="aae6e-297">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="aae6e-297">52.127.88.0/21</span></span>


<span data-ttu-id="aae6e-298">En la siguiente tabla se muestra el intervalo de puertos de los transmisores de transporte de los equipos (aplicables a todos los entornos):</span><span class="sxs-lookup"><span data-stu-id="aae6e-298">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="aae6e-299">Transmisión</span><span class="sxs-lookup"><span data-stu-id="aae6e-299">Traffic</span></span> | <span data-ttu-id="aae6e-300">De</span><span class="sxs-lookup"><span data-stu-id="aae6e-300">From</span></span> | <span data-ttu-id="aae6e-301">Hasta</span><span class="sxs-lookup"><span data-stu-id="aae6e-301">To</span></span> | <span data-ttu-id="aae6e-302">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="aae6e-302">Source port</span></span> | <span data-ttu-id="aae6e-303">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="aae6e-303">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="aae6e-304">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="aae6e-304">UDP/SRTP</span></span> | <span data-ttu-id="aae6e-305">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="aae6e-305">Transport Relay</span></span> | <span data-ttu-id="aae6e-306">SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-306">SBC</span></span> | <span data-ttu-id="aae6e-307">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="aae6e-307">50 000 -59 999</span></span>    | <span data-ttu-id="aae6e-308">Definido en la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-308">Defined on the SBC</span></span> |
| <span data-ttu-id="aae6e-309">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="aae6e-309">UDP/SRTP</span></span> | <span data-ttu-id="aae6e-310">SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-310">SBC</span></span> | <span data-ttu-id="aae6e-311">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="aae6e-311">Transport Relay</span></span> | <span data-ttu-id="aae6e-312">Definido en la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-312">Defined on the SBC</span></span> | <span data-ttu-id="aae6e-313">50 000:59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="aae6e-313">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="aae6e-314">Nota: Microsoft recomienda al menos dos puertos por llamada simultánea en la SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-314">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="aae6e-315">Como Microsoft tiene dos versiones de transmisores de transporte, se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aae6e-315">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="aae6e-316">V4, que solo puede funcionar con el intervalo de puertos 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="aae6e-316">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="aae6e-317">V6, que funciona con los puertos 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="aae6e-317">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="aae6e-318">En este momento, la omisión de elementos multimedia solo admite la versión v4 de retransmisiones de transporte.</span><span class="sxs-lookup"><span data-stu-id="aae6e-318">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="aae6e-319">Presentaremos la compatibilidad de V6 en el futuro.</span><span class="sxs-lookup"><span data-stu-id="aae6e-319">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="aae6e-320">Para realizar la transición, debe abrir los puertos 3478 y 3479.</span><span class="sxs-lookup"><span data-stu-id="aae6e-320">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="aae6e-321">Cuando Microsoft introduce compatibilidad con los relés de transporte de V6 con omisión de medios, no tendrá que volver a configurar su equipo de red ni SBCs.</span><span class="sxs-lookup"><span data-stu-id="aae6e-321">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="aae6e-322">Requisitos para usar procesadores multimedia</span><span class="sxs-lookup"><span data-stu-id="aae6e-322">Requirements for using media processors</span></span>

<span data-ttu-id="aae6e-323">Los procesadores de medios siempre están en la ruta multimedia de las aplicaciones de voz y de los clientes Web (por ejemplo, los clientes de Teams en Edge o Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="aae6e-323">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="aae6e-324">Los requisitos son los mismos que para la configuración sin omisión.</span><span class="sxs-lookup"><span data-stu-id="aae6e-324">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="aae6e-325">El intervalo IP para el tráfico de medios es</span><span class="sxs-lookup"><span data-stu-id="aae6e-325">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="aae6e-326">Entornos de Office 365 y Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="aae6e-326">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="aae6e-327">-52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="aae6e-327">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="aae6e-328">Entorno DoD de Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="aae6e-328">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="aae6e-329">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="aae6e-329">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="aae6e-330">Office 365 GCC de gran entorno</span><span class="sxs-lookup"><span data-stu-id="aae6e-330">Office 365 GCC High environment</span></span>

- <span data-ttu-id="aae6e-331">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="aae6e-331">52.127.88.0/21</span></span>

<span data-ttu-id="aae6e-332">El intervalo de puertos de los procesadores de medios (aplicables a todos los entornos) se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="aae6e-332">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="aae6e-333">Transmisión</span><span class="sxs-lookup"><span data-stu-id="aae6e-333">Traffic</span></span> | <span data-ttu-id="aae6e-334">De</span><span class="sxs-lookup"><span data-stu-id="aae6e-334">From</span></span> | <span data-ttu-id="aae6e-335">Hasta</span><span class="sxs-lookup"><span data-stu-id="aae6e-335">To</span></span> | <span data-ttu-id="aae6e-336">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="aae6e-336">Source port</span></span> | <span data-ttu-id="aae6e-337">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="aae6e-337">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="aae6e-338">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="aae6e-338">UDP/SRTP</span></span> | <span data-ttu-id="aae6e-339">Procesador de medios</span><span class="sxs-lookup"><span data-stu-id="aae6e-339">Media Processor</span></span> | <span data-ttu-id="aae6e-340">SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-340">SBC</span></span> | <span data-ttu-id="aae6e-341">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="aae6e-341">49 152 – 53 247</span></span>    | <span data-ttu-id="aae6e-342">Definido en la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-342">Defined on the SBC</span></span> |
| <span data-ttu-id="aae6e-343">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="aae6e-343">UDP/SRTP</span></span> | <span data-ttu-id="aae6e-344">SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-344">SBC</span></span> | <span data-ttu-id="aae6e-345">Procesador de medios</span><span class="sxs-lookup"><span data-stu-id="aae6e-345">Media Processor</span></span> | <span data-ttu-id="aae6e-346">Definido en la SBC</span><span class="sxs-lookup"><span data-stu-id="aae6e-346">Defined on the SBC</span></span> | <span data-ttu-id="aae6e-347">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="aae6e-347">49 152 – 53 247</span></span>     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a><span data-ttu-id="aae6e-348">Consideraciones si tiene teléfonos de Skype empresarial en su red</span><span class="sxs-lookup"><span data-stu-id="aae6e-348">Considerations if you have Skype for Business phones in your network</span></span>  

<span data-ttu-id="aae6e-349">Si tiene algún punto final de Skype empresarial en su red que usa enrutamiento directo, por ejemplo, un usuario de equipos puede tener un teléfono 3PIP basado en el cliente de Skype empresarial, la omisión de medios en el tronco que sirve a estos usuarios debe estar desactivada.</span><span class="sxs-lookup"><span data-stu-id="aae6e-349">If you have any Skype for Business end points in your network that are using Direct Routing--for example, a Teams user can have a 3PIP phone that is based on Skype for Business client--the media bypass on the trunk that serves these users must be turned off.</span></span>

<span data-ttu-id="aae6e-350">Puede crear un tronco separado para estos usuarios y asignarle una directiva de enrutamiento de voz en línea.</span><span class="sxs-lookup"><span data-stu-id="aae6e-350">You can create a separate trunk for these users and assign it an Online Voice Routing policy.</span></span>

<span data-ttu-id="aae6e-351">Pasos de configuración de alto nivel:</span><span class="sxs-lookup"><span data-stu-id="aae6e-351">High-level configuration steps:</span></span>

- <span data-ttu-id="aae6e-352">Divida los usuarios por tipo (dependiendo de si el usuario tiene un teléfono de 3PIP o no).</span><span class="sxs-lookup"><span data-stu-id="aae6e-352">Split users by type – depending on whether the user has a 3PIP phone or not.</span></span>

- <span data-ttu-id="aae6e-353">Cree dos troncos independientes con diferentes FQDN: uno habilitado para la omisión de medios; el otro no.</span><span class="sxs-lookup"><span data-stu-id="aae6e-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="aae6e-354">Ambos troncos apuntan a la misma SBC.</span><span class="sxs-lookup"><span data-stu-id="aae6e-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="aae6e-355">Los puertos para la señalización TLS SIP deben ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="aae6e-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="aae6e-356">Los puertos para los medios deben ser los mismos.</span><span class="sxs-lookup"><span data-stu-id="aae6e-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="aae6e-357">Asigne el tronco correcto según el tipo de usuario de la Directiva de enrutamiento de voz en línea.</span><span class="sxs-lookup"><span data-stu-id="aae6e-357">Assign the correct trunk depending on the type of the user in the Online Voice Routing policy.</span></span>

<span data-ttu-id="aae6e-358">En el ejemplo siguiente se muestra esta lógica.</span><span class="sxs-lookup"><span data-stu-id="aae6e-358">The example below illustrates this logic.</span></span>

| <span data-ttu-id="aae6e-359">Conjunto de usuarios</span><span class="sxs-lookup"><span data-stu-id="aae6e-359">Set of users</span></span> | <span data-ttu-id="aae6e-360">Número de usuarios</span><span class="sxs-lookup"><span data-stu-id="aae6e-360">Number of users</span></span> | <span data-ttu-id="aae6e-361">FQDN de tronco asignado en OVRP</span><span class="sxs-lookup"><span data-stu-id="aae6e-361">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="aae6e-362">Omisión de medios habilitado</span><span class="sxs-lookup"><span data-stu-id="aae6e-362">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="aae6e-363">Usuarios con clientes de equipos y teléfonos 3PIP</span><span class="sxs-lookup"><span data-stu-id="aae6e-363">Users with Teams clients and 3PIP phones</span></span> | <span data-ttu-id="aae6e-364">veinte</span><span class="sxs-lookup"><span data-stu-id="aae6e-364">20</span></span> | <span data-ttu-id="aae6e-365">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="aae6e-365">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="aae6e-366">falso</span><span class="sxs-lookup"><span data-stu-id="aae6e-366">false</span></span> | 
<span data-ttu-id="aae6e-367">Usuarios con solo los puntos finales de los equipos (incluidos los nuevos teléfonos certificados para Teams)</span><span class="sxs-lookup"><span data-stu-id="aae6e-367">Users with only Teams end points (including new phones certified for Teams)</span></span> | <span data-ttu-id="aae6e-368">980</span><span class="sxs-lookup"><span data-stu-id="aae6e-368">980</span></span> | <span data-ttu-id="aae6e-369">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="aae6e-369">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="aae6e-370">verdadero</span><span class="sxs-lookup"><span data-stu-id="aae6e-370">true</span></span>

<span data-ttu-id="aae6e-371">Ambos troncos pueden apuntar al mismo SBC con la misma dirección IP pública.</span><span class="sxs-lookup"><span data-stu-id="aae6e-371">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="aae6e-372">Los puertos de señalización TLS en la SBC deben ser diferentes, tal como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="aae6e-372">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="aae6e-373">Nota tendrá que asegurarse de que su certificado admite ambos troncos.</span><span class="sxs-lookup"><span data-stu-id="aae6e-373">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="aae6e-374">En SAN, debe tener dos nombres (**sbc1.contoso.com** y **sbc2.contoso.com**) o tener un certificado comodín.</span><span class="sxs-lookup"><span data-stu-id="aae6e-374">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![Muestra que ambos troncos pueden apuntar al mismo SBC con la misma IP pública](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="aae6e-376">Para obtener más información sobre cómo configurar dos troncos en el mismo SBC, consulte la documentación proporcionada por el proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="aae6e-376">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="aae6e-377">Documentación de la implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="aae6e-377">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="aae6e-378">Documentación de implementación de Oracle</span><span class="sxs-lookup"><span data-stu-id="aae6e-378">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="aae6e-379">Documentación de implementación de comunicaciones de la cinta</span><span class="sxs-lookup"><span data-stu-id="aae6e-379">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="aae6e-380">Documentación de la implementación de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="aae6e-380">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="aae6e-381">Extremos de cliente compatibles con la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="aae6e-381">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="aae6e-382">La omisión de elementos multimedia es compatible con todos los puntos de conexión de Teams.</span><span class="sxs-lookup"><span data-stu-id="aae6e-382">Media bypass is supported with all Teams endpoints.</span></span>

<span data-ttu-id="aae6e-383">Nota para los clientes Web (Teams Web App en Microsoft Edge, Google Chrome o Mozilla Firefox) se hará la llamada a no omitir aunque se haya iniciado como una llamada de omisión.</span><span class="sxs-lookup"><span data-stu-id="aae6e-383">Note for web clients (Teams Web app in Microsoft Edge, Google Chrome or Mozilla Firefox) we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="aae6e-384">Esto sucede automáticamente y no requiere ninguna acción del administrador.</span><span class="sxs-lookup"><span data-stu-id="aae6e-384">This happens automatically and does not require any actions from the administrator.</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="aae6e-385">Vea también</span><span class="sxs-lookup"><span data-stu-id="aae6e-385">See also</span></span>

[<span data-ttu-id="aae6e-386">Configurar el desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="aae6e-386">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



