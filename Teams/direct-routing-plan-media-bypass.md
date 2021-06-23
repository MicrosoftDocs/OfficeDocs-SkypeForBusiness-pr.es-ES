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
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo planear la omisión de medios con Sistema telefónico enrutamiento directo, lo que le permite acortar la ruta del tráfico multimedia y mejorar el rendimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d60513dbcf1128d303102f494600a67335b366d
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075403"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="5ebf1-103">Planear desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="5ebf1-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="5ebf1-104">Acerca de la omisión de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="5ebf1-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="5ebf1-105">La omisión de medios le permite acortar la ruta del tráfico multimedia y reducir el número de saltos en tránsito para un mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="5ebf1-106">Con la omisión de medios, los medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente en lugar de enviarlo a través del sistema Teléfono Microsoft sesión.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="5ebf1-107">Para configurar la omisión de medios, el SBC y el cliente deben estar en la misma ubicación o red.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="5ebf1-108">Puede controlar la omisión de medios para cada SBC mediante el comando **Set-CSOnlinePSTNGateway** con el **parámetro -MediaBypass** establecido en verdadero o falso.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="5ebf1-109">Si habilita la omisión de medios, esto no significa que todo el tráfico multimedia permanezca dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="5ebf1-110">En este artículo se describe el flujo de llamadas en diferentes escenarios.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="5ebf1-111">Los diagramas siguientes ilustran la diferencia en el flujo de llamadas con y sin omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="5ebf1-112">Sin omisión de medios, cuando un cliente realiza o recibe una llamada, tanto la señalización como el flujo multimedia entre el SBC, el sistema Teléfono Microsoft y el cliente Teams, como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ebf1-113">![Muestra la señalización y el flujo de medios sin omisión de medios](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="5ebf1-114">Pero supongamos que un usuario está en el mismo edificio o red que el SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="5ebf1-115">Por ejemplo, supongamos que un usuario que se encuentra en un edificio de Fráncfort realiza una llamada a un usuario RTC:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="5ebf1-116">**Sin el desvío** de medios, los medios fluirán a través de Ámsterdam o Dublín (donde se implementan los centros de datos de Microsoft) y de nuevo al SBC de Fráncfort.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="5ebf1-117">El centro de datos en Europa está seleccionado porque el SBC está en Europa y Microsoft usa el centro de datos más próximo al SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="5ebf1-118">Aunque este enfoque no afecta a la calidad de las llamadas debido a la optimización del flujo de tráfico dentro de las redes de Microsoft en la mayoría de las geografías, el tráfico tiene un bucle innecesario.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="5ebf1-119">**Con la omisión** de medios, el medio se mantiene directamente entre el Teams y el SBC como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="5ebf1-120">![Muestra la señalización y el flujo multimedia con la omisión de medios](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="5ebf1-121">La omisión de medios usa protocolos denominados Establecimiento de conectividad interactiva (ICE) en el cliente Teams y ICE lite en el SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="5ebf1-122">Estos protocolos permiten que el enrutamiento directo use la ruta multimedia más directa para obtener una calidad óptima.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="5ebf1-123">ICE y ICE Lite son estándares webRTC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="5ebf1-124">Para obtener información detallada sobre estos protocolos, vea RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="5ebf1-125">Planificación del flujo de llamadas y del firewall</span><span class="sxs-lookup"><span data-stu-id="5ebf1-125">Call flow and firewall planning</span></span>

<span data-ttu-id="5ebf1-126">El flujo de llamadas y la planificación del firewall dependen de si el usuario tiene acceso directo a la dirección IP pública del SBC y de si el usuario está dentro o fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="5ebf1-127">Flujo de llamadas si el usuario tiene acceso directo a la dirección IP pública del SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="5ebf1-128">Si el usuario tiene acceso directo a la dirección IP pública del SBC, el flujo de llamadas es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="5ebf1-129">Para la omisión de medios, Teams cliente debe tener acceso a la dirección IP pública del SBC incluso desde una red interna.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="5ebf1-130">Si no se desea usar medios directos, los medios pueden fluir a través de retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="5ebf1-131">Esta es la solución recomendada cuando un usuario está en el mismo edificio o red que el SBC: quite los componentes de Microsoft Cloud de la ruta de acceso multimedia.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="5ebf1-132">La señalización siempre fluye a través de la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="5ebf1-133">En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es interno y el cliente puede llegar a la dirección IP pública del SBC (medios directos):</span><span class="sxs-lookup"><span data-stu-id="5ebf1-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="5ebf1-134">Las flechas y los valores numéricos de las rutas de acceso se ajustan a [Microsoft Teams de llamadas.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="5ebf1-135">La señalización SIP siempre toma trayectorias 4 y 4' (según la dirección del tráfico).</span><span class="sxs-lookup"><span data-stu-id="5ebf1-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="5ebf1-136">Multimedia permanece local y toma la ruta 5b.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ebf1-137">![Muestra el flujo de llamadas con la omisión de medios habilitada, el cliente es interno](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="5ebf1-138">Flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="5ebf1-139">A continuación se describe el flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="5ebf1-140">Por ejemplo, suponga que el usuario es externo y el administrador de inquilinos decidió no abrir la dirección IP pública del SBC a todos los usuarios de Internet, sino solo a Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="5ebf1-141">Los componentes internos del tráfico pueden fluir a través Teams relés de transporte.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="5ebf1-142">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-142">Consider the following:</span></span>

- <span data-ttu-id="5ebf1-143">Teams Se usan relés de transporte.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="5ebf1-144">Para la omisión de medios, Microsoft usa una versión de retransmisión de transporte que requiere abrir puertos de 50 000 a 59 999 entre las retransmisiones de transporte de Teams y el SBC (en el futuro planeamos pasar a la versión que requiere puertos 3478-3481).</span><span class="sxs-lookup"><span data-stu-id="5ebf1-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires 3478-3481 ports).</span></span>


<span data-ttu-id="5ebf1-145">En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente no puede llegar a la dirección IP pública del controlador de borde de sesión (los medios se retransmiten Teams Retransmisión de transporte).</span><span class="sxs-lookup"><span data-stu-id="5ebf1-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="5ebf1-146">Las flechas y los valores numéricos de las rutas de acceso se ajustan a [Microsoft Teams de llamadas.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="5ebf1-147">Los medios se retransmiten a través de las rutas 3, 3', 4 y 4'</span><span class="sxs-lookup"><span data-stu-id="5ebf1-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ebf1-148">![Muestra el flujo de llamadas si el usuario no tiene acceso a la IP pública del SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="5ebf1-149">Flujo de llamadas si un usuario está fuera de la red y tiene acceso a la DIRECCIÓN IP pública del SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="5ebf1-150">Esta no es una configuración recomendada porque no se aprovecha de Teams retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="5ebf1-151">En su lugar, debe considerar el escenario anterior en el que el usuario no tiene acceso a la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="5ebf1-152">En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente puede llegar a la dirección IP pública del SBC (medios directos).</span><span class="sxs-lookup"><span data-stu-id="5ebf1-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="5ebf1-153">Las flechas y los valores numéricos de las rutas de acceso se ajustan al [artículo Microsoft Teams flujos de llamadas.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="5ebf1-154">La señalización SIP siempre toma trayectorias 3 y 3' (según la dirección del tráfico).</span><span class="sxs-lookup"><span data-stu-id="5ebf1-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="5ebf1-155">Los flujos multimedia usan la ruta 2.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ebf1-156">![Muestra el flujo de llamadas si el usuario no tiene acceso a la IP pública del SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="5ebf1-157">Uso de procesadores multimedia y retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="5ebf1-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="5ebf1-158">Hay dos componentes en microsoft cloud que pueden estar en la ruta del tráfico multimedia: procesadores multimedia y retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="5ebf1-159">El procesador multimedia es un componente orientado al público que controla los medios en casos que no se omiten y controla los medios para las aplicaciones de voz.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="5ebf1-160">Los procesadores multimedia siempre están en la ruta de acceso para las llamadas no omitidas por el usuario final, pero nunca en la ruta de acceso para las llamadas omitida.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="5ebf1-161">Los procesadores multimedia siempre están en la ruta de acceso para todas las aplicaciones de voz, como Parque de llamadas, Operador automático y Colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="5ebf1-162">El Retransmisión de transporte se usa para conectarse al servicio de transporte más cercano para enviar tráfico en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="5ebf1-163">Las retransmisiones de transporte pueden o no estar en la ruta de acceso para llamadas omitida (que proceden o están destinadas a usuarios finales), dependiendo de dónde se encuentra el usuario y de cómo esté configurada la red.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="5ebf1-164">En el siguiente diagrama se muestran dos flujos de llamadas: uno con la omisión de medios habilitada y la segunda con la omisión de medios deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="5ebf1-165">En el diagrama solo se muestra el tráfico procedente o destinado a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="5ebf1-166">El controlador multimedia es un microservicio de Azure que asigna procesadores multimedia y crea ofertas del Protocolo de descripción de sesión (SDP).</span><span class="sxs-lookup"><span data-stu-id="5ebf1-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="5ebf1-167">El proxy SIP es un componente que traduce la señalización HTTP REST que se usa en Teams a SIP.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ebf1-168">![Muestra los flujos de llamadas con la omisión de medios habilitada y deshabilitada](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="5ebf1-169">En la tabla siguiente se resume la diferencia entre los procesadores multimedia y los relés de transporte.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="5ebf1-170">Procesadores multimedia</span><span class="sxs-lookup"><span data-stu-id="5ebf1-170">Media Processors</span></span> | <span data-ttu-id="5ebf1-171">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="5ebf1-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="5ebf1-172">En la ruta de acceso multimedia para llamadas no omitida para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="5ebf1-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="5ebf1-173">Siempre</span><span class="sxs-lookup"><span data-stu-id="5ebf1-173">Always</span></span> | <span data-ttu-id="5ebf1-174">Si el cliente no puede ponerse en contacto directamente con el Procesador multimedia</span><span class="sxs-lookup"><span data-stu-id="5ebf1-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="5ebf1-175">En la ruta de acceso multimedia para llamadas omitida para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="5ebf1-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="5ebf1-176">Nunca</span><span class="sxs-lookup"><span data-stu-id="5ebf1-176">Never</span></span> | <span data-ttu-id="5ebf1-177">Si el cliente no puede llegar al SBC en la dirección IP pública</span><span class="sxs-lookup"><span data-stu-id="5ebf1-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="5ebf1-178">En la ruta de acceso multimedia para aplicaciones de voz</span><span class="sxs-lookup"><span data-stu-id="5ebf1-178">In media path for voice applications</span></span> | <span data-ttu-id="5ebf1-179">Siempre</span><span class="sxs-lookup"><span data-stu-id="5ebf1-179">Always</span></span> | <span data-ttu-id="5ebf1-180">Nunca</span><span class="sxs-lookup"><span data-stu-id="5ebf1-180">Never</span></span> | 
<span data-ttu-id="5ebf1-181">Puede realizar la transcodificación (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="5ebf1-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="5ebf1-182">Sí</span><span class="sxs-lookup"><span data-stu-id="5ebf1-182">Yes</span></span> | <span data-ttu-id="5ebf1-183">No, solo retransmite audio entre puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="5ebf1-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="5ebf1-184">Número de instancias en todo el mundo y ubicación</span><span class="sxs-lookup"><span data-stu-id="5ebf1-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="5ebf1-185">10 total: 2 en Ee. UU. Este y Oeste; 2 en Ámsterdam y Dublín; 2 en Hong Kong y Singapur; 2 en Japón; 2 en Australia Este y Sureste</span><span class="sxs-lookup"><span data-stu-id="5ebf1-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="5ebf1-186">Múltiplo</span><span class="sxs-lookup"><span data-stu-id="5ebf1-186">Multiple</span></span>

<span data-ttu-id="5ebf1-187">Los rangos IP son:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-187">The IP ranges are:</span></span>
- <span data-ttu-id="5ebf1-188">52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="5ebf1-189">52.120.0.0/14 (direcciones IP de 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="5ebf1-190">\* Explicación de transcodificación:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="5ebf1-191">El procesador multimedia es B2BUA, lo que significa que puede cambiar un códec (por ejemplo, SILK de cliente Teams a MP y G.711 entre MP y SBC).</span><span class="sxs-lookup"><span data-stu-id="5ebf1-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="5ebf1-192">Los relés de transporte no son B2BUA, lo que significa que el códec nunca se cambia entre el cliente y el SBC, incluso si el tráfico fluye a través de retransmisión.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="5ebf1-193">Uso de Teams multimedia si el tronco está configurado para la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="5ebf1-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="5ebf1-194">Teams Los procesadores multimedia siempre se insertan en la ruta de acceso multimedia en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="5ebf1-195">La llamada se escala de 1:1 a una llamada grupal</span><span class="sxs-lookup"><span data-stu-id="5ebf1-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="5ebf1-196">La llamada se va a un usuario Teams federado</span><span class="sxs-lookup"><span data-stu-id="5ebf1-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="5ebf1-197">La llamada se reenvía o se transfiere a Skype Empresarial usuario</span><span class="sxs-lookup"><span data-stu-id="5ebf1-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="5ebf1-198">Asegúrese de que su SBC tiene acceso a los rangos procesadores multimedia y retransmisión de transporte como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="5ebf1-199">Señalización SIP: FQDN</span><span class="sxs-lookup"><span data-stu-id="5ebf1-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="5ebf1-200">Para la señalización SIP, los requisitos de FQDN y firewall son los mismos que para los casos no omitido.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="5ebf1-201">El enrutamiento directo se ofrece en los siguientes Microsoft 365 o Office 365 entornos:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="5ebf1-202">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="5ebf1-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="5ebf1-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-203">Office 365 GCC</span></span>
- <span data-ttu-id="5ebf1-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="5ebf1-204">Office 365 GCC High</span></span>
- <span data-ttu-id="5ebf1-205">Office 365 DoD Obtenga más información sobre [Office 365 entornos](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) gubernamentales de Ee. UU. como GCC, GCC high y DoD.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5ebf1-206">Microsoft 365, Office 365 y Office 365 GCC entornos</span><span class="sxs-lookup"><span data-stu-id="5ebf1-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="5ebf1-207">Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="5ebf1-208">**sip.pstnhub.microsoft.com:** FQDN global, debe probarse primero.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="5ebf1-209">Cuando el SBC envía una solicitud para resolver este nombre, los servidores DNS Microsoft Azure devuelven una dirección IP que apunta al centro de datos de Azure principal asignado al SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="5ebf1-210">La tarea se basa en las métricas de rendimiento de los centros de datos y la proximidad geográfica al SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="5ebf1-211">La dirección IP devuelta corresponde al FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="5ebf1-212">**sip2.pstnhub.microsoft.com:** FQDN secundario, se asigna geográficamente a la región de segunda prioridad.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="5ebf1-213">**sip3.pstnhub.microsoft.com:** FQDN terciario, se asigna geográficamente a la región de tercera prioridad.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="5ebf1-214">Debe colocar estos tres FQDN para:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="5ebf1-215">Proporcione una experiencia óptima (menos cargada y más cercana al centro de datos de SBC asignada consultando el primer FQDN).</span><span class="sxs-lookup"><span data-stu-id="5ebf1-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="5ebf1-216">Proporcionar conmutación por error cuando se establece una conexión desde un SBC a un centro de datos que experimenta un problema temporal.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="5ebf1-217">Para obtener más información, vea Mecanismo de conmutación por error a continuación.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="5ebf1-218">Los FQDN **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** y **sip3.pstnhub.microsoft.com** se resolverán en direcciones IP de las siguientes subredes:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to IP addresses from the following subnets:</span></span>
- <span data-ttu-id="5ebf1-219">52.112.0.0/14</span><span class="sxs-lookup"><span data-stu-id="5ebf1-219">52.112.0.0/14</span></span>
- <span data-ttu-id="5ebf1-220">52.120.0.0/14</span><span class="sxs-lookup"><span data-stu-id="5ebf1-220">52.120.0.0/14</span></span>

<span data-ttu-id="5ebf1-221">Debe abrir puertos para todos estos intervalos IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-221">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="5ebf1-222">Si el firewall admite nombres DNS, el FQDN **sip-all.pstnhub.microsoft.com** se resuelve en todas estas subredes IP.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-222">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP subnets.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5ebf1-223">Office 365 GCC doD</span><span class="sxs-lookup"><span data-stu-id="5ebf1-223">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="5ebf1-224">El punto de conexión para enrutamiento directo es el siguiente FQDN:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-224">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="5ebf1-225">**sip.pstnhub.dod.teams.microsoft.us:** FQDN global.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-225">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="5ebf1-226">Como el Office 365 DoD solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-226">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="5ebf1-227">El fqdn sip.pstnhub.dod.teams.microsoft.us se resolverá en una dirección IP de la siguiente subred:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-227">The FQDN sip.pstnhub.dod.teams.microsoft.us will be resolved to an IP address from the following subnet:</span></span>

- <span data-ttu-id="5ebf1-228">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5ebf1-228">52.127.64.0/21</span></span>

<span data-ttu-id="5ebf1-229">Debe abrir puertos para todos estos intervalos IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-229">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="5ebf1-230">Si el firewall admite nombres DNS, el FQDN sip.pstnhub.dod.teams.microsoft.us se resuelve en todas estas subredes IP.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-230">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP subnets.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5ebf1-231">Office 365 GCC high environment</span><span class="sxs-lookup"><span data-stu-id="5ebf1-231">Office 365 GCC High environment</span></span>

<span data-ttu-id="5ebf1-232">El punto de conexión para enrutamiento directo es el siguiente FQDN:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-232">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="5ebf1-233">**sip.pstnhub.gov.teams.microsoft.us:** FQDN global.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-233">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="5ebf1-234">Como el GCC high solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-234">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="5ebf1-235">El fqdn sip.pstnhub.gov.teams.microsoft.us se resolverá en una dirección IP de la siguiente subred:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-235">The FQDN sip.pstnhub.gov.teams.microsoft.us will be resolved to an IP address from the following subnet:</span></span>

- <span data-ttu-id="5ebf1-236">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5ebf1-236">52.127.64.0/21</span></span>

<span data-ttu-id="5ebf1-237">Debe abrir puertos para todos estos intervalos IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-237">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="5ebf1-238">Si el firewall admite nombres DNS, el FQDN sip.pstnhub.gov.teams.microsoft.us se resuelve en todas estas subredes IP.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-238">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP subnets.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="5ebf1-239">Señalización SIP: Puertos</span><span class="sxs-lookup"><span data-stu-id="5ebf1-239">SIP Signaling: Ports</span></span>

<span data-ttu-id="5ebf1-240">Los requisitos de puerto son los mismos para todos los Office 365 en los que se ofrece enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-240">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="5ebf1-241">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="5ebf1-241">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="5ebf1-242">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-242">Office 365 GCC</span></span>
- <span data-ttu-id="5ebf1-243">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="5ebf1-243">Office 365 GCC High</span></span>
- <span data-ttu-id="5ebf1-244">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="5ebf1-244">Office 365 DoD</span></span>

<span data-ttu-id="5ebf1-245">Debe usar los siguientes puertos:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-245">You must use the following ports:</span></span>

| <span data-ttu-id="5ebf1-246">Tráfico</span><span class="sxs-lookup"><span data-stu-id="5ebf1-246">Traffic</span></span> | <span data-ttu-id="5ebf1-247">De</span><span class="sxs-lookup"><span data-stu-id="5ebf1-247">From</span></span> | <span data-ttu-id="5ebf1-248">Hasta</span><span class="sxs-lookup"><span data-stu-id="5ebf1-248">To</span></span> | <span data-ttu-id="5ebf1-249">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="5ebf1-249">Source port</span></span> | <span data-ttu-id="5ebf1-250">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="5ebf1-250">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5ebf1-251">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="5ebf1-251">SIP/TLS</span></span>| <span data-ttu-id="5ebf1-252">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="5ebf1-252">SIP Proxy</span></span> | <span data-ttu-id="5ebf1-253">SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-253">SBC</span></span> | <span data-ttu-id="5ebf1-254">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="5ebf1-254">1024 - 65535</span></span> | <span data-ttu-id="5ebf1-255">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-255">Defined on the SBC</span></span> |
| <span data-ttu-id="5ebf1-256">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="5ebf1-256">SIP/TLS</span></span> | <span data-ttu-id="5ebf1-257">SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-257">SBC</span></span> | <span data-ttu-id="5ebf1-258">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="5ebf1-258">SIP Proxy</span></span> | <span data-ttu-id="5ebf1-259">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-259">Defined on the SBC</span></span> | <span data-ttu-id="5ebf1-260">5061</span><span class="sxs-lookup"><span data-stu-id="5ebf1-260">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="5ebf1-261">Tráfico multimedia: intervalos de IP y puertos</span><span class="sxs-lookup"><span data-stu-id="5ebf1-261">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="5ebf1-262">El tráfico multimedia fluye entre el SBC y el cliente Teams si la conectividad directa está disponible o a través de retransmisión de transporte de Teams si el cliente no puede llegar al SBC con la dirección IP pública.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-262">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="5ebf1-263">Requisitos para el tráfico multimedia directo (entre el Teams y el SBC)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-263">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="5ebf1-264">El cliente debe tener acceso a los puertos especificados (ver tabla) en la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-264">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="5ebf1-265">Si el cliente se encuentra en una red interna, el medio fluye a la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-265">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="5ebf1-266">Puede configurar la fijación de pelo en el dispositivo NAT para que el tráfico nunca salga del equipo de red empresarial.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-266">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="5ebf1-267">Tráfico</span><span class="sxs-lookup"><span data-stu-id="5ebf1-267">Traffic</span></span> | <span data-ttu-id="5ebf1-268">De</span><span class="sxs-lookup"><span data-stu-id="5ebf1-268">From</span></span> | <span data-ttu-id="5ebf1-269">Hasta</span><span class="sxs-lookup"><span data-stu-id="5ebf1-269">To</span></span> | <span data-ttu-id="5ebf1-270">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="5ebf1-270">Source port</span></span> | <span data-ttu-id="5ebf1-271">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="5ebf1-271">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5ebf1-272">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ebf1-272">UDP/SRTP</span></span> | <span data-ttu-id="5ebf1-273">Cliente</span><span class="sxs-lookup"><span data-stu-id="5ebf1-273">Client</span></span> | <span data-ttu-id="5ebf1-274">SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-274">SBC</span></span> | <span data-ttu-id="5ebf1-275">3478-3481 y 49152 - 53247</span><span class="sxs-lookup"><span data-stu-id="5ebf1-275">3478-3481 and 49152 – 53247</span></span>| <span data-ttu-id="5ebf1-276">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-276">Defined on the SBC</span></span> |
| <span data-ttu-id="5ebf1-277">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ebf1-277">UDP/SRTP</span></span> | <span data-ttu-id="5ebf1-278">SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-278">SBC</span></span> | <span data-ttu-id="5ebf1-279">Cliente</span><span class="sxs-lookup"><span data-stu-id="5ebf1-279">Client</span></span> | <span data-ttu-id="5ebf1-280">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-280">Defined on the SBC</span></span> | <span data-ttu-id="5ebf1-281">3478-3481 y 49152 - 53247</span><span class="sxs-lookup"><span data-stu-id="5ebf1-281">3478-3481 and 49152 – 53247</span></span>  |


> [!NOTE]
> <span data-ttu-id="5ebf1-282">Si tiene un dispositivo de red que traduce los puertos de origen del cliente, asegúrese de que los puertos traducidos se abren entre el equipo de red y el SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-282">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="5ebf1-283">Requisitos para usar retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="5ebf1-283">Requirements for using Transport Relays</span></span>

<span data-ttu-id="5ebf1-284">Las retransmisión de transporte están en el mismo rango que los procesadores multimedia (para casos que no se omiten):</span><span class="sxs-lookup"><span data-stu-id="5ebf1-284">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5ebf1-285">Microsoft 365, Office 365 y Office 365 GCC entornos</span><span class="sxs-lookup"><span data-stu-id="5ebf1-285">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="5ebf1-286">52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-286">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5ebf1-287">Office 365 GCC doD</span><span class="sxs-lookup"><span data-stu-id="5ebf1-287">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="5ebf1-288">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5ebf1-288">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5ebf1-289">Office 365 GCC high environment</span><span class="sxs-lookup"><span data-stu-id="5ebf1-289">Office 365 GCC High environment</span></span>

- <span data-ttu-id="5ebf1-290">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="5ebf1-290">52.127.88.0/21</span></span>


<span data-ttu-id="5ebf1-291">El rango de puertos de Teams relés de transporte (aplicables a todos los entornos) se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-291">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="5ebf1-292">Tráfico</span><span class="sxs-lookup"><span data-stu-id="5ebf1-292">Traffic</span></span> | <span data-ttu-id="5ebf1-293">De</span><span class="sxs-lookup"><span data-stu-id="5ebf1-293">From</span></span> | <span data-ttu-id="5ebf1-294">Hasta</span><span class="sxs-lookup"><span data-stu-id="5ebf1-294">To</span></span> | <span data-ttu-id="5ebf1-295">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="5ebf1-295">Source port</span></span> | <span data-ttu-id="5ebf1-296">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="5ebf1-296">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5ebf1-297">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ebf1-297">UDP/SRTP</span></span> | <span data-ttu-id="5ebf1-298">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="5ebf1-298">Transport Relay</span></span> | <span data-ttu-id="5ebf1-299">SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-299">SBC</span></span> | <span data-ttu-id="5ebf1-300">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="5ebf1-300">50 000 -59 999</span></span>    | <span data-ttu-id="5ebf1-301">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-301">Defined on the SBC</span></span> |
| <span data-ttu-id="5ebf1-302">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ebf1-302">UDP/SRTP</span></span> | <span data-ttu-id="5ebf1-303">SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-303">SBC</span></span> | <span data-ttu-id="5ebf1-304">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="5ebf1-304">Transport Relay</span></span> | <span data-ttu-id="5ebf1-305">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-305">Defined on the SBC</span></span> | <span data-ttu-id="5ebf1-306">50 000 – 59 999, 3478-3481</span><span class="sxs-lookup"><span data-stu-id="5ebf1-306">50 000 – 59 999, 3478-3481</span></span>     |


> [!NOTE]
> <span data-ttu-id="5ebf1-307">Microsoft recomienda al menos dos puertos por llamada simultánea en el SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-307">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="5ebf1-308">Dado que Microsoft tiene dos versiones de retransmisión de transporte, son necesarias las siguientes:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-308">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="5ebf1-309">v4, que solo puede funcionar con el rango de puertos de 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="5ebf1-309">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="5ebf1-310">v6, que funciona con los puertos 3478-3481</span><span class="sxs-lookup"><span data-stu-id="5ebf1-310">v6, which works with ports 3478-3481</span></span>

<span data-ttu-id="5ebf1-311">En este momento, la omisión de medios solo admite la versión v4 de retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-311">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="5ebf1-312">Presentaremos compatibilidad con v6 en el futuro.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-312">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="5ebf1-313">Debe abrir los puertos 3478-3481 para la transición.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-313">You need to open ports 3478-3481 for transitioning.</span></span> <span data-ttu-id="5ebf1-314">Cuando Microsoft presenta compatibilidad con retransmisión de transporte v6 con omisión de medios, no tendrá que volver a configurar el equipo de red ni los SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-314">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="5ebf1-315">Requisitos para usar procesadores multimedia</span><span class="sxs-lookup"><span data-stu-id="5ebf1-315">Requirements for using media processors</span></span>

<span data-ttu-id="5ebf1-316">Los procesadores multimedia siempre están en la ruta de acceso multimedia para aplicaciones de voz y para clientes web (por ejemplo, Teams en Edge o Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="5ebf1-316">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="5ebf1-317">Los requisitos son los mismos que para la configuración sin omisión.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-317">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="5ebf1-318">El intervalo IP para el tráfico multimedia es</span><span class="sxs-lookup"><span data-stu-id="5ebf1-318">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5ebf1-319">Office 365 y Office 365 GCC entornos</span><span class="sxs-lookup"><span data-stu-id="5ebf1-319">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="5ebf1-320">52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-320">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5ebf1-321">Office 365 GCC doD</span><span class="sxs-lookup"><span data-stu-id="5ebf1-321">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="5ebf1-322">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5ebf1-322">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5ebf1-323">Office 365 GCC high environment</span><span class="sxs-lookup"><span data-stu-id="5ebf1-323">Office 365 GCC High environment</span></span>

- <span data-ttu-id="5ebf1-324">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="5ebf1-324">52.127.88.0/21</span></span>

<span data-ttu-id="5ebf1-325">El rango de puertos de los procesadores multimedia (aplicable a todos los entornos) se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-325">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="5ebf1-326">Tráfico</span><span class="sxs-lookup"><span data-stu-id="5ebf1-326">Traffic</span></span> | <span data-ttu-id="5ebf1-327">De</span><span class="sxs-lookup"><span data-stu-id="5ebf1-327">From</span></span> | <span data-ttu-id="5ebf1-328">Hasta</span><span class="sxs-lookup"><span data-stu-id="5ebf1-328">To</span></span> | <span data-ttu-id="5ebf1-329">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="5ebf1-329">Source port</span></span> | <span data-ttu-id="5ebf1-330">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="5ebf1-330">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5ebf1-331">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ebf1-331">UDP/SRTP</span></span> | <span data-ttu-id="5ebf1-332">Procesador multimedia</span><span class="sxs-lookup"><span data-stu-id="5ebf1-332">Media Processor</span></span> | <span data-ttu-id="5ebf1-333">SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-333">SBC</span></span> | <span data-ttu-id="5ebf1-334">3478-3481 y 49 152 - 53 247</span><span class="sxs-lookup"><span data-stu-id="5ebf1-334">3478-3481 and 49 152 – 53 247</span></span>    | <span data-ttu-id="5ebf1-335">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-335">Defined on the SBC</span></span> |
| <span data-ttu-id="5ebf1-336">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ebf1-336">UDP/SRTP</span></span> | <span data-ttu-id="5ebf1-337">SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-337">SBC</span></span> | <span data-ttu-id="5ebf1-338">Procesador multimedia</span><span class="sxs-lookup"><span data-stu-id="5ebf1-338">Media Processor</span></span> | <span data-ttu-id="5ebf1-339">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="5ebf1-339">Defined on the SBC</span></span> | <span data-ttu-id="5ebf1-340">3478-3481 y 49 152 - 53 247</span><span class="sxs-lookup"><span data-stu-id="5ebf1-340">3478-3481 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="5ebf1-341">Configurar troncos independientes para la omisión de medios y la omisión no multimedia</span><span class="sxs-lookup"><span data-stu-id="5ebf1-341">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="5ebf1-342">Si va a migrar a la omisión de medios desde la omisión no multimedia y desea confirmar la funcionalidad antes de migrar todo el uso a la omisión de medios, puede crear un tronco independiente y una directiva de enrutamiento de voz en línea independiente para enrutar al tronco de omisión multimedia y asignarlo a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-342">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="5ebf1-343">Pasos de configuración de alto nivel:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-343">High-level configuration steps:</span></span>

- <span data-ttu-id="5ebf1-344">Identificar usuarios para probar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-344">Identify users to test media bypass.</span></span>

- <span data-ttu-id="5ebf1-345">Cree dos troncos independientes con FQDN diferentes: uno habilitado para la omisión de medios; el otro no.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-345">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="5ebf1-346">Ambos troncos apuntan al mismo SBC.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-346">Both trunks point to the same SBC.</span></span> <span data-ttu-id="5ebf1-347">Los puertos para la señalización SIP TLS deben ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-347">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="5ebf1-348">Los puertos para medios deben ser los mismos.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-348">The ports for media must be the same.</span></span>

- <span data-ttu-id="5ebf1-349">Cree una nueva directiva de enrutamiento de voz en línea y asigne el tronco de omisión multimedia a las rutas correspondientes asociadas con el uso de RTC para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-349">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="5ebf1-350">Asigne la nueva directiva de enrutamiento de voz en línea a los usuarios identificados para probar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-350">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="5ebf1-351">En el ejemplo siguiente se muestra esta lógica.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-351">The example below illustrates this logic.</span></span>

| <span data-ttu-id="5ebf1-352">Conjunto de usuarios</span><span class="sxs-lookup"><span data-stu-id="5ebf1-352">Set of users</span></span> | <span data-ttu-id="5ebf1-353">Número de usuarios</span><span class="sxs-lookup"><span data-stu-id="5ebf1-353">Number of users</span></span> | <span data-ttu-id="5ebf1-354">FQDN de tronco asignado en OVRP</span><span class="sxs-lookup"><span data-stu-id="5ebf1-354">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="5ebf1-355">Omisión de medios habilitada</span><span class="sxs-lookup"><span data-stu-id="5ebf1-355">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="5ebf1-356">Usuarios con tronco de omisión no multimedia</span><span class="sxs-lookup"><span data-stu-id="5ebf1-356">Users with non-media bypass trunk</span></span> | <span data-ttu-id="5ebf1-357">980</span><span class="sxs-lookup"><span data-stu-id="5ebf1-357">980</span></span> | <span data-ttu-id="5ebf1-358">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="5ebf1-358">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="5ebf1-359">falso</span><span class="sxs-lookup"><span data-stu-id="5ebf1-359">false</span></span> |
<span data-ttu-id="5ebf1-360">Usuarios con tronco de omisión multimedia</span><span class="sxs-lookup"><span data-stu-id="5ebf1-360">Users with media bypass trunk</span></span> | <span data-ttu-id="5ebf1-361">20</span><span class="sxs-lookup"><span data-stu-id="5ebf1-361">20</span></span> | <span data-ttu-id="5ebf1-362">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="5ebf1-362">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="5ebf1-363">verdadero</span><span class="sxs-lookup"><span data-stu-id="5ebf1-363">true</span></span> | 

<span data-ttu-id="5ebf1-364">Ambos troncos pueden apuntar al mismo SBC con la misma dirección IP pública.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-364">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="5ebf1-365">Los puertos de señalización TLS del SBC deben ser diferentes, como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-365">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="5ebf1-366">Tenga en cuenta que tendrá que asegurarse de que el certificado admite ambos troncos.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-366">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="5ebf1-367">En SAN, debe tener dos nombres **(sbc1.contoso.com** y **sbc2.contoso.com)** o tener un certificado comodín.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-367">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ebf1-368">![Muestra que ambos troncos pueden apuntar al mismo SBC con la misma IP pública](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-368">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="5ebf1-369">Para obtener información sobre cómo configurar dos troncos en el mismo SBC, vea la documentación proporcionada por el proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="5ebf1-369">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="5ebf1-370">Documentación de implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="5ebf1-370">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="5ebf1-371">Documentación de implementación de Oracle</span><span class="sxs-lookup"><span data-stu-id="5ebf1-371">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="5ebf1-372">Documentación de implementación de Comunicaciones de la cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="5ebf1-372">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="5ebf1-373">Documentación de implementación de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="5ebf1-373">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="5ebf1-374">Extremos de cliente compatibles con la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="5ebf1-374">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="5ebf1-375">La omisión de medios es compatible con todos los Teams de escritorio independientes, clientes de Android e iOS y Teams Teléfono dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-375">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="5ebf1-376">Para todos los demás puntos de conexión que no admiten la omisión de medios, convertiremos la llamada en no omitir, incluso si se inició como una llamada de omisión.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-376">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="5ebf1-377">Esto ocurre automáticamente y no requiere ninguna acción del administrador.</span><span class="sxs-lookup"><span data-stu-id="5ebf1-377">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="5ebf1-378">Esto incluye Skype Empresarial teléfonos 3PIP y clientes web Teams compatibles con las llamadas de enrutamiento directo (clientes basados en WebRTC que se ejecutan en Microsoft Edge, Google Chrome y Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="5ebf1-378">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="5ebf1-379">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ebf1-379">See also</span></span>

[<span data-ttu-id="5ebf1-380">Configurar el desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="5ebf1-380">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
