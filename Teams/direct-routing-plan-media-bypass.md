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
ms.openlocfilehash: 9b6624a81994c1d6797ed996fbcc233fe75f8907
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308359"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="41123-103">Planear desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="41123-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="41123-104">Acerca de la omisión de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="41123-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="41123-105">La omisión de medios le permite acortar la ruta del tráfico multimedia y reducir el número de saltos en tránsito para un mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="41123-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="41123-106">Con la omisión de medios, los medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente en lugar de enviarlo a través del sistema Teléfono Microsoft sesión.</span><span class="sxs-lookup"><span data-stu-id="41123-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="41123-107">Para configurar la omisión de medios, el SBC y el cliente deben estar en la misma ubicación o red.</span><span class="sxs-lookup"><span data-stu-id="41123-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="41123-108">Puede controlar la omisión de medios para cada SBC mediante el comando **Set-CSOnlinePSTNGateway** con el **parámetro -MediaBypass** establecido en verdadero o falso.</span><span class="sxs-lookup"><span data-stu-id="41123-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="41123-109">Si habilita la omisión de medios, esto no significa que todo el tráfico multimedia permanezca dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="41123-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="41123-110">En este artículo se describe el flujo de llamadas en diferentes escenarios.</span><span class="sxs-lookup"><span data-stu-id="41123-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="41123-111">Los diagramas siguientes ilustran la diferencia en el flujo de llamadas con y sin omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="41123-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="41123-112">Sin omisión de medios, cuando un cliente realiza o recibe una llamada, tanto la señalización como el flujo multimedia entre el SBC, el sistema Teléfono Microsoft y el cliente Teams, como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="41123-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41123-113">![Muestra la señalización y el flujo de medios sin omisión de medios](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="41123-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="41123-114">Pero supongamos que un usuario está en el mismo edificio o red que el SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="41123-115">Por ejemplo, supongamos que un usuario que se encuentra en un edificio de Fráncfort realiza una llamada a un usuario RTC:</span><span class="sxs-lookup"><span data-stu-id="41123-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="41123-116">**Sin el desvío** de medios, los medios fluirán a través de Ámsterdam o Dublín (donde se implementan los centros de datos de Microsoft) y de nuevo al SBC de Fráncfort.</span><span class="sxs-lookup"><span data-stu-id="41123-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="41123-117">El centro de datos en Europa está seleccionado porque el SBC está en Europa y Microsoft usa el centro de datos más próximo al SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="41123-118">Aunque este enfoque no afecta a la calidad de las llamadas debido a la optimización del flujo de tráfico dentro de las redes de Microsoft en la mayoría de las geografías, el tráfico tiene un bucle innecesario.</span><span class="sxs-lookup"><span data-stu-id="41123-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="41123-119">**Con la omisión** de medios, el medio se mantiene directamente entre el Teams y el SBC como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="41123-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="41123-120">![Muestra la señalización y el flujo multimedia con la omisión de medios](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="41123-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="41123-121">La omisión de medios usa protocolos denominados Establecimiento de conectividad interactiva (ICE) en el cliente Teams y ICE lite en el SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="41123-122">Estos protocolos permiten que el enrutamiento directo use la ruta multimedia más directa para obtener una calidad óptima.</span><span class="sxs-lookup"><span data-stu-id="41123-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="41123-123">ICE y ICE Lite son estándares webRTC.</span><span class="sxs-lookup"><span data-stu-id="41123-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="41123-124">Para obtener información detallada sobre estos protocolos, vea RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="41123-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="41123-125">Planificación del flujo de llamadas y del firewall</span><span class="sxs-lookup"><span data-stu-id="41123-125">Call flow and firewall planning</span></span>

<span data-ttu-id="41123-126">El flujo de llamadas y la planificación del firewall dependen de si el usuario tiene acceso directo a la dirección IP pública del SBC y de si el usuario está dentro o fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="41123-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="41123-127">Flujo de llamadas si el usuario tiene acceso directo a la dirección IP pública del SBC</span><span class="sxs-lookup"><span data-stu-id="41123-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="41123-128">Si el usuario tiene acceso directo a la dirección IP pública del SBC, el flujo de llamadas es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="41123-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="41123-129">Para la omisión de medios, Teams cliente debe tener acceso a la dirección IP pública del SBC incluso desde una red interna.</span><span class="sxs-lookup"><span data-stu-id="41123-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="41123-130">Si no se desea usar medios directos, los medios pueden fluir a través de retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="41123-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="41123-131">Esta es la solución recomendada cuando un usuario está en el mismo edificio o red que el SBC: quite los componentes de Microsoft Cloud de la ruta de acceso multimedia.</span><span class="sxs-lookup"><span data-stu-id="41123-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="41123-132">La señalización siempre fluye a través de la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="41123-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="41123-133">En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es interno y el cliente puede llegar a la dirección IP pública del SBC (medios directos):</span><span class="sxs-lookup"><span data-stu-id="41123-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="41123-134">Las flechas y los valores numéricos de las rutas de acceso se ajustan a [Microsoft Teams de llamadas.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="41123-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="41123-135">La señalización SIP siempre toma trayectorias 4 y 4' (según la dirección del tráfico).</span><span class="sxs-lookup"><span data-stu-id="41123-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="41123-136">Multimedia permanece local y toma la ruta 5b.</span><span class="sxs-lookup"><span data-stu-id="41123-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41123-137">![Muestra el flujo de llamadas con la omisión de medios habilitada, el cliente es interno](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="41123-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="41123-138">Flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC</span><span class="sxs-lookup"><span data-stu-id="41123-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="41123-139">A continuación se describe el flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="41123-140">Por ejemplo, suponga que el usuario es externo y el administrador de inquilinos decidió no abrir la dirección IP pública del SBC a todos los usuarios de Internet, sino solo a Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="41123-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="41123-141">Los componentes internos del tráfico pueden fluir a través Teams relés de transporte.</span><span class="sxs-lookup"><span data-stu-id="41123-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="41123-142">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41123-142">Consider the following:</span></span>

- <span data-ttu-id="41123-143">Teams Se usan relés de transporte.</span><span class="sxs-lookup"><span data-stu-id="41123-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="41123-144">Para la omisión de medios, Microsoft usa una versión de retransmisión de transporte que requiere abrir puertos de 50 000 a 59 999 entre las retransmisiones de transporte de Teams y el SBC (en el futuro planeamos pasar a la versión que requiere puertos 3478-3481).</span><span class="sxs-lookup"><span data-stu-id="41123-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires 3478-3481 ports).</span></span>


<span data-ttu-id="41123-145">En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente no puede llegar a la dirección IP pública del controlador de borde de sesión (los medios se retransmiten Teams Retransmisión de transporte).</span><span class="sxs-lookup"><span data-stu-id="41123-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="41123-146">Las flechas y los valores numéricos de las rutas de acceso se ajustan a [Microsoft Teams de llamadas.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="41123-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="41123-147">Los medios se retransmiten a través de las rutas 3, 3', 4 y 4'</span><span class="sxs-lookup"><span data-stu-id="41123-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41123-148">![Muestra el flujo de llamadas si el usuario no tiene acceso a la IP pública del SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="41123-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="41123-149">Flujo de llamadas si un usuario está fuera de la red y tiene acceso a la DIRECCIÓN IP pública del SBC</span><span class="sxs-lookup"><span data-stu-id="41123-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="41123-150">Esta no es una configuración recomendada porque no se aprovecha de Teams retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="41123-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="41123-151">En su lugar, debe considerar el escenario anterior en el que el usuario no tiene acceso a la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="41123-152">En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente puede llegar a la dirección IP pública del SBC (medios directos).</span><span class="sxs-lookup"><span data-stu-id="41123-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="41123-153">Las flechas y los valores numéricos de las rutas de acceso se ajustan al [artículo Microsoft Teams flujos de llamadas.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="41123-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="41123-154">La señalización SIP siempre toma trayectorias 3 y 3' (según la dirección del tráfico).</span><span class="sxs-lookup"><span data-stu-id="41123-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="41123-155">Los flujos multimedia usan la ruta 2.</span><span class="sxs-lookup"><span data-stu-id="41123-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41123-156">![Muestra el flujo de llamadas si el usuario no tiene acceso a la IP pública del SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="41123-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="41123-157">Uso de procesadores multimedia y retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="41123-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="41123-158">Hay dos componentes en microsoft cloud que pueden estar en la ruta del tráfico multimedia: procesadores multimedia y retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="41123-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="41123-159">El procesador multimedia es un componente orientado al público que controla los medios en casos que no se omiten y controla los medios para las aplicaciones de voz.</span><span class="sxs-lookup"><span data-stu-id="41123-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="41123-160">Los procesadores multimedia siempre están en la ruta de acceso para las llamadas no omitidas por el usuario final, pero nunca en la ruta de acceso para las llamadas omitida.</span><span class="sxs-lookup"><span data-stu-id="41123-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="41123-161">Los procesadores multimedia siempre están en la ruta de acceso para todas las aplicaciones de voz, como Parque de llamadas, Operador automático y Colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="41123-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="41123-162">El Retransmisión de transporte se usa para conectarse al servicio de transporte más cercano para enviar tráfico en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="41123-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="41123-163">Las retransmisiones de transporte pueden o no estar en la ruta de acceso para llamadas omitida (que proceden o están destinadas a usuarios finales), dependiendo de dónde se encuentra el usuario y de cómo esté configurada la red.</span><span class="sxs-lookup"><span data-stu-id="41123-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="41123-164">En el siguiente diagrama se muestran dos flujos de llamadas: uno con la omisión de medios habilitada y la segunda con la omisión de medios deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="41123-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="41123-165">En el diagrama solo se muestra el tráfico procedente o destinado a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="41123-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="41123-166">El controlador multimedia es un microservicio de Azure que asigna procesadores multimedia y crea ofertas del Protocolo de descripción de sesión (SDP).</span><span class="sxs-lookup"><span data-stu-id="41123-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="41123-167">El proxy SIP es un componente que traduce la señalización HTTP REST que se usa en Teams a SIP.</span><span class="sxs-lookup"><span data-stu-id="41123-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41123-168">![Muestra los flujos de llamadas con la omisión de medios habilitada y deshabilitada](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="41123-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="41123-169">En la tabla siguiente se resume la diferencia entre los procesadores multimedia y los relés de transporte.</span><span class="sxs-lookup"><span data-stu-id="41123-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="41123-170">Procesadores multimedia</span><span class="sxs-lookup"><span data-stu-id="41123-170">Media Processors</span></span> | <span data-ttu-id="41123-171">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="41123-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="41123-172">En la ruta de acceso multimedia para llamadas no omitida para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="41123-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="41123-173">Siempre</span><span class="sxs-lookup"><span data-stu-id="41123-173">Always</span></span> | <span data-ttu-id="41123-174">Si el cliente no puede ponerse en contacto directamente con el Procesador multimedia</span><span class="sxs-lookup"><span data-stu-id="41123-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="41123-175">En la ruta de acceso multimedia para llamadas omitida para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="41123-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="41123-176">Nunca</span><span class="sxs-lookup"><span data-stu-id="41123-176">Never</span></span> | <span data-ttu-id="41123-177">Si el cliente no puede llegar al SBC en la dirección IP pública</span><span class="sxs-lookup"><span data-stu-id="41123-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="41123-178">En la ruta de acceso multimedia para aplicaciones de voz</span><span class="sxs-lookup"><span data-stu-id="41123-178">In media path for voice applications</span></span> | <span data-ttu-id="41123-179">Siempre</span><span class="sxs-lookup"><span data-stu-id="41123-179">Always</span></span> | <span data-ttu-id="41123-180">Nunca</span><span class="sxs-lookup"><span data-stu-id="41123-180">Never</span></span> | 
<span data-ttu-id="41123-181">Puede realizar la transcodificación (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="41123-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="41123-182">Sí</span><span class="sxs-lookup"><span data-stu-id="41123-182">Yes</span></span> | <span data-ttu-id="41123-183">No, solo retransmite audio entre puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="41123-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="41123-184">Número de instancias en todo el mundo y ubicación</span><span class="sxs-lookup"><span data-stu-id="41123-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="41123-185">10 total: 2 en Ee. UU. Este y Oeste; 2 en Ámsterdam y Dublín; 2 en Hong Kong y Singapur; 2 en Japón; 2 en Australia Este y Sureste</span><span class="sxs-lookup"><span data-stu-id="41123-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="41123-186">Múltiplo</span><span class="sxs-lookup"><span data-stu-id="41123-186">Multiple</span></span>

<span data-ttu-id="41123-187">Los rangos IP son:</span><span class="sxs-lookup"><span data-stu-id="41123-187">The IP ranges are:</span></span>
- <span data-ttu-id="41123-188">52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="41123-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="41123-189">52.120.0.0/14 (direcciones IP de 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="41123-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="41123-190">\* Explicación de transcodificación:</span><span class="sxs-lookup"><span data-stu-id="41123-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="41123-191">El procesador multimedia es B2BUA, lo que significa que puede cambiar un códec (por ejemplo, SILK de cliente Teams a MP y G.711 entre MP y SBC).</span><span class="sxs-lookup"><span data-stu-id="41123-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="41123-192">Los relés de transporte no son B2BUA, lo que significa que el códec nunca se cambia entre el cliente y el SBC, incluso si el tráfico fluye a través de retransmisión.</span><span class="sxs-lookup"><span data-stu-id="41123-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="41123-193">Uso de Teams multimedia si el tronco está configurado para la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="41123-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="41123-194">Teams Los procesadores multimedia siempre se insertan en la ruta de acceso multimedia en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="41123-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="41123-195">La llamada se escala de 1:1 a una llamada grupal</span><span class="sxs-lookup"><span data-stu-id="41123-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="41123-196">La llamada se va a un usuario Teams federado</span><span class="sxs-lookup"><span data-stu-id="41123-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="41123-197">La llamada se reenvía o se transfiere a Skype Empresarial usuario</span><span class="sxs-lookup"><span data-stu-id="41123-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="41123-198">Asegúrese de que su SBC tiene acceso a los rangos procesadores multimedia y retransmisión de transporte como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="41123-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="41123-199">Señalización SIP: FQDN</span><span class="sxs-lookup"><span data-stu-id="41123-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="41123-200">Para la señalización SIP, los requisitos de FQDN y firewall son los mismos que para los casos no omitido.</span><span class="sxs-lookup"><span data-stu-id="41123-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="41123-201">El enrutamiento directo se ofrece en los siguientes Microsoft 365 o Office 365 entornos:</span><span class="sxs-lookup"><span data-stu-id="41123-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="41123-202">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="41123-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="41123-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="41123-203">Office 365 GCC</span></span>
- <span data-ttu-id="41123-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="41123-204">Office 365 GCC High</span></span>
- <span data-ttu-id="41123-205">Office 365 DoD Obtenga más información sobre [Office 365 entornos](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) gubernamentales de Ee. UU. como GCC, GCC high y DoD.</span><span class="sxs-lookup"><span data-stu-id="41123-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="41123-206">Microsoft 365, Office 365 y Office 365 GCC entornos</span><span class="sxs-lookup"><span data-stu-id="41123-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="41123-207">Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:</span><span class="sxs-lookup"><span data-stu-id="41123-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="41123-208">**sip.pstnhub.microsoft.com:** FQDN global, debe probarse primero.</span><span class="sxs-lookup"><span data-stu-id="41123-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="41123-209">Cuando el SBC envía una solicitud para resolver este nombre, los servidores DNS Microsoft Azure devuelven una dirección IP que apunta al centro de datos de Azure principal asignado al SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="41123-210">La tarea se basa en las métricas de rendimiento de los centros de datos y la proximidad geográfica al SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="41123-211">La dirección IP devuelta corresponde al FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="41123-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="41123-212">**sip2.pstnhub.microsoft.com:** FQDN secundario, se asigna geográficamente a la región de segunda prioridad.</span><span class="sxs-lookup"><span data-stu-id="41123-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="41123-213">**sip3.pstnhub.microsoft.com:** FQDN terciario, se asigna geográficamente a la región de tercera prioridad.</span><span class="sxs-lookup"><span data-stu-id="41123-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="41123-214">Debe colocar estos tres FQDN para:</span><span class="sxs-lookup"><span data-stu-id="41123-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="41123-215">Proporcione una experiencia óptima (menos cargada y más cercana al centro de datos de SBC asignada consultando el primer FQDN).</span><span class="sxs-lookup"><span data-stu-id="41123-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="41123-216">Proporcionar conmutación por error cuando se establece una conexión desde un SBC a un centro de datos que experimenta un problema temporal.</span><span class="sxs-lookup"><span data-stu-id="41123-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="41123-217">Para obtener más información, vea Mecanismo de conmutación por error a continuación.</span><span class="sxs-lookup"><span data-stu-id="41123-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="41123-218">Los FQDN **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** y **sip3.pstnhub.microsoft.com** se resolverán en una de las siguientes direcciones IP:</span><span class="sxs-lookup"><span data-stu-id="41123-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="41123-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="41123-219">52.114.148.0</span></span>
- <span data-ttu-id="41123-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="41123-220">52.114.132.46</span></span> 
- <span data-ttu-id="41123-221">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="41123-221">52.114.75.24</span></span> 
- <span data-ttu-id="41123-222">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="41123-222">52.114.76.76</span></span> 
- <span data-ttu-id="41123-223">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="41123-223">52.114.7.24</span></span> 
- <span data-ttu-id="41123-224">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="41123-224">52.114.14.70</span></span>
- <span data-ttu-id="41123-225">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="41123-225">52.114.16.74</span></span>
- <span data-ttu-id="41123-226">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="41123-226">52.114.20.29</span></span>
- <span data-ttu-id="41123-227">52.114.36.156</span><span class="sxs-lookup"><span data-stu-id="41123-227">52.114.36.156</span></span> 
- <span data-ttu-id="41123-228">52.114.32.169</span><span class="sxs-lookup"><span data-stu-id="41123-228">52.114.32.169</span></span>

<span data-ttu-id="41123-229">Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="41123-229">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="41123-230">Si el firewall admite nombres DNS, el FQDN **sip-all.pstnhub.microsoft.com** se resuelve en todas estas direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="41123-230">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="41123-231">Office 365 GCC doD</span><span class="sxs-lookup"><span data-stu-id="41123-231">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="41123-232">El punto de conexión para enrutamiento directo es el siguiente FQDN:</span><span class="sxs-lookup"><span data-stu-id="41123-232">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="41123-233">**sip.pstnhub.dod.teams.microsoft.us:** FQDN global.</span><span class="sxs-lookup"><span data-stu-id="41123-233">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="41123-234">Como el Office 365 DoD solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.</span><span class="sxs-lookup"><span data-stu-id="41123-234">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="41123-235">Los FQDN: sip.pstnhub.dod.teams.microsoft.us se resolverán en una de las siguientes direcciones IP:</span><span class="sxs-lookup"><span data-stu-id="41123-235">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="41123-236">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="41123-236">52.127.64.33</span></span>
- <span data-ttu-id="41123-237">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="41123-237">52.127.68.34</span></span>

<span data-ttu-id="41123-238">Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="41123-238">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="41123-239">Si el firewall admite nombres DNS, el FQDN sip.pstnhub.dod.teams.microsoft.us se resuelve en todas estas direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="41123-239">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="41123-240">Office 365 GCC high environment</span><span class="sxs-lookup"><span data-stu-id="41123-240">Office 365 GCC High environment</span></span>

<span data-ttu-id="41123-241">El punto de conexión para enrutamiento directo es el siguiente FQDN:</span><span class="sxs-lookup"><span data-stu-id="41123-241">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="41123-242">**sip.pstnhub.gov.teams.microsoft.us:** FQDN global.</span><span class="sxs-lookup"><span data-stu-id="41123-242">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="41123-243">Como el GCC high solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.</span><span class="sxs-lookup"><span data-stu-id="41123-243">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="41123-244">Los FQDN: sip.pstnhub.gov.teams.microsoft.us se resolverán en una de las siguientes direcciones IP:</span><span class="sxs-lookup"><span data-stu-id="41123-244">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="41123-245">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="41123-245">52.127.88.59</span></span>
- <span data-ttu-id="41123-246">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="41123-246">52.127.92.64</span></span>

<span data-ttu-id="41123-247">Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="41123-247">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="41123-248">Si el firewall admite nombres DNS, el FQDN sip.pstnhub.gov.teams.microsoft.us se resuelve en todas estas direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="41123-248">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="41123-249">Señalización SIP: Puertos</span><span class="sxs-lookup"><span data-stu-id="41123-249">SIP Signaling: Ports</span></span>

<span data-ttu-id="41123-250">Los requisitos de puerto son los mismos para todos los Office 365 en los que se ofrece enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="41123-250">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="41123-251">Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="41123-251">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="41123-252">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="41123-252">Office 365 GCC</span></span>
- <span data-ttu-id="41123-253">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="41123-253">Office 365 GCC High</span></span>
- <span data-ttu-id="41123-254">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="41123-254">Office 365 DoD</span></span>

<span data-ttu-id="41123-255">Debe usar los siguientes puertos:</span><span class="sxs-lookup"><span data-stu-id="41123-255">You must use the following ports:</span></span>

| <span data-ttu-id="41123-256">Tráfico</span><span class="sxs-lookup"><span data-stu-id="41123-256">Traffic</span></span> | <span data-ttu-id="41123-257">De</span><span class="sxs-lookup"><span data-stu-id="41123-257">From</span></span> | <span data-ttu-id="41123-258">Hasta</span><span class="sxs-lookup"><span data-stu-id="41123-258">To</span></span> | <span data-ttu-id="41123-259">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="41123-259">Source port</span></span> | <span data-ttu-id="41123-260">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="41123-260">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="41123-261">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="41123-261">SIP/TLS</span></span>| <span data-ttu-id="41123-262">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="41123-262">SIP Proxy</span></span> | <span data-ttu-id="41123-263">SBC</span><span class="sxs-lookup"><span data-stu-id="41123-263">SBC</span></span> | <span data-ttu-id="41123-264">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="41123-264">1024 - 65535</span></span> | <span data-ttu-id="41123-265">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="41123-265">Defined on the SBC</span></span> |
| <span data-ttu-id="41123-266">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="41123-266">SIP/TLS</span></span> | <span data-ttu-id="41123-267">SBC</span><span class="sxs-lookup"><span data-stu-id="41123-267">SBC</span></span> | <span data-ttu-id="41123-268">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="41123-268">SIP Proxy</span></span> | <span data-ttu-id="41123-269">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="41123-269">Defined on the SBC</span></span> | <span data-ttu-id="41123-270">5061</span><span class="sxs-lookup"><span data-stu-id="41123-270">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="41123-271">Tráfico multimedia: intervalos de IP y puertos</span><span class="sxs-lookup"><span data-stu-id="41123-271">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="41123-272">El tráfico multimedia fluye entre el SBC y el cliente Teams si la conectividad directa está disponible o a través de retransmisión de transporte de Teams si el cliente no puede llegar al SBC con la dirección IP pública.</span><span class="sxs-lookup"><span data-stu-id="41123-272">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="41123-273">Requisitos para el tráfico multimedia directo (entre el Teams y el SBC)</span><span class="sxs-lookup"><span data-stu-id="41123-273">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="41123-274">El cliente debe tener acceso a los puertos especificados (ver tabla) en la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-274">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="41123-275">Si el cliente se encuentra en una red interna, el medio fluye a la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-275">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="41123-276">Puede configurar la fijación de pelo en el dispositivo NAT para que el tráfico nunca salga del equipo de red empresarial.</span><span class="sxs-lookup"><span data-stu-id="41123-276">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="41123-277">Tráfico</span><span class="sxs-lookup"><span data-stu-id="41123-277">Traffic</span></span> | <span data-ttu-id="41123-278">De</span><span class="sxs-lookup"><span data-stu-id="41123-278">From</span></span> | <span data-ttu-id="41123-279">Hasta</span><span class="sxs-lookup"><span data-stu-id="41123-279">To</span></span> | <span data-ttu-id="41123-280">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="41123-280">Source port</span></span> | <span data-ttu-id="41123-281">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="41123-281">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="41123-282">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="41123-282">UDP/SRTP</span></span> | <span data-ttu-id="41123-283">Cliente</span><span class="sxs-lookup"><span data-stu-id="41123-283">Client</span></span> | <span data-ttu-id="41123-284">SBC</span><span class="sxs-lookup"><span data-stu-id="41123-284">SBC</span></span> | <span data-ttu-id="41123-285">3478-3481 y 49152 - 53247</span><span class="sxs-lookup"><span data-stu-id="41123-285">3478-3481 and 49152 – 53247</span></span>| <span data-ttu-id="41123-286">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="41123-286">Defined on the SBC</span></span> |
| <span data-ttu-id="41123-287">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="41123-287">UDP/SRTP</span></span> | <span data-ttu-id="41123-288">SBC</span><span class="sxs-lookup"><span data-stu-id="41123-288">SBC</span></span> | <span data-ttu-id="41123-289">Cliente</span><span class="sxs-lookup"><span data-stu-id="41123-289">Client</span></span> | <span data-ttu-id="41123-290">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="41123-290">Defined on the SBC</span></span> | <span data-ttu-id="41123-291">3478-3481 y 49152 - 53247</span><span class="sxs-lookup"><span data-stu-id="41123-291">3478-3481 and 49152 – 53247</span></span>  |


> [!NOTE]
> <span data-ttu-id="41123-292">Si tiene un dispositivo de red que traduce los puertos de origen del cliente, asegúrese de que los puertos traducidos se abren entre el equipo de red y el SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-292">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="41123-293">Requisitos para usar retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="41123-293">Requirements for using Transport Relays</span></span>

<span data-ttu-id="41123-294">Las retransmisión de transporte están en el mismo rango que los procesadores multimedia (para casos que no se omiten):</span><span class="sxs-lookup"><span data-stu-id="41123-294">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="41123-295">Microsoft 365, Office 365 y Office 365 GCC entornos</span><span class="sxs-lookup"><span data-stu-id="41123-295">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="41123-296">52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="41123-296">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="41123-297">Office 365 GCC doD</span><span class="sxs-lookup"><span data-stu-id="41123-297">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="41123-298">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="41123-298">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="41123-299">Office 365 GCC high environment</span><span class="sxs-lookup"><span data-stu-id="41123-299">Office 365 GCC High environment</span></span>

- <span data-ttu-id="41123-300">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="41123-300">52.127.88.0/21</span></span>


<span data-ttu-id="41123-301">El rango de puertos de Teams relés de transporte (aplicables a todos los entornos) se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="41123-301">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="41123-302">Tráfico</span><span class="sxs-lookup"><span data-stu-id="41123-302">Traffic</span></span> | <span data-ttu-id="41123-303">De</span><span class="sxs-lookup"><span data-stu-id="41123-303">From</span></span> | <span data-ttu-id="41123-304">Hasta</span><span class="sxs-lookup"><span data-stu-id="41123-304">To</span></span> | <span data-ttu-id="41123-305">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="41123-305">Source port</span></span> | <span data-ttu-id="41123-306">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="41123-306">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="41123-307">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="41123-307">UDP/SRTP</span></span> | <span data-ttu-id="41123-308">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="41123-308">Transport Relay</span></span> | <span data-ttu-id="41123-309">SBC</span><span class="sxs-lookup"><span data-stu-id="41123-309">SBC</span></span> | <span data-ttu-id="41123-310">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="41123-310">50 000 -59 999</span></span>    | <span data-ttu-id="41123-311">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="41123-311">Defined on the SBC</span></span> |
| <span data-ttu-id="41123-312">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="41123-312">UDP/SRTP</span></span> | <span data-ttu-id="41123-313">SBC</span><span class="sxs-lookup"><span data-stu-id="41123-313">SBC</span></span> | <span data-ttu-id="41123-314">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="41123-314">Transport Relay</span></span> | <span data-ttu-id="41123-315">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="41123-315">Defined on the SBC</span></span> | <span data-ttu-id="41123-316">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="41123-316">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="41123-317">Microsoft recomienda al menos dos puertos por llamada simultánea en el SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-317">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="41123-318">Dado que Microsoft tiene dos versiones de retransmisión de transporte, son necesarias las siguientes:</span><span class="sxs-lookup"><span data-stu-id="41123-318">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="41123-319">v4, que solo puede funcionar con el rango de puertos de 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="41123-319">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="41123-320">v6, que funciona con los puertos 3478 y 3479</span><span class="sxs-lookup"><span data-stu-id="41123-320">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="41123-321">En este momento, la omisión de medios solo admite la versión v4 de retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="41123-321">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="41123-322">Presentaremos compatibilidad con v6 en el futuro.</span><span class="sxs-lookup"><span data-stu-id="41123-322">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="41123-323">Debe abrir los puertos 3478 y 3479 para la transición.</span><span class="sxs-lookup"><span data-stu-id="41123-323">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="41123-324">Cuando Microsoft presenta compatibilidad con retransmisión de transporte v6 con omisión de medios, no tendrá que volver a configurar el equipo de red ni los SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-324">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="41123-325">Requisitos para usar procesadores multimedia</span><span class="sxs-lookup"><span data-stu-id="41123-325">Requirements for using media processors</span></span>

<span data-ttu-id="41123-326">Los procesadores multimedia siempre están en la ruta de acceso multimedia para aplicaciones de voz y para clientes web (por ejemplo, Teams en Edge o Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="41123-326">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="41123-327">Los requisitos son los mismos que para la configuración sin omisión.</span><span class="sxs-lookup"><span data-stu-id="41123-327">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="41123-328">El intervalo IP para el tráfico multimedia es</span><span class="sxs-lookup"><span data-stu-id="41123-328">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="41123-329">Office 365 y Office 365 GCC entornos</span><span class="sxs-lookup"><span data-stu-id="41123-329">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="41123-330">52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="41123-330">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="41123-331">Office 365 GCC doD</span><span class="sxs-lookup"><span data-stu-id="41123-331">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="41123-332">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="41123-332">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="41123-333">Office 365 GCC high environment</span><span class="sxs-lookup"><span data-stu-id="41123-333">Office 365 GCC High environment</span></span>

- <span data-ttu-id="41123-334">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="41123-334">52.127.88.0/21</span></span>

<span data-ttu-id="41123-335">El rango de puertos de los procesadores multimedia (aplicable a todos los entornos) se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="41123-335">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="41123-336">Tráfico</span><span class="sxs-lookup"><span data-stu-id="41123-336">Traffic</span></span> | <span data-ttu-id="41123-337">De</span><span class="sxs-lookup"><span data-stu-id="41123-337">From</span></span> | <span data-ttu-id="41123-338">Hasta</span><span class="sxs-lookup"><span data-stu-id="41123-338">To</span></span> | <span data-ttu-id="41123-339">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="41123-339">Source port</span></span> | <span data-ttu-id="41123-340">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="41123-340">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="41123-341">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="41123-341">UDP/SRTP</span></span> | <span data-ttu-id="41123-342">Procesador multimedia</span><span class="sxs-lookup"><span data-stu-id="41123-342">Media Processor</span></span> | <span data-ttu-id="41123-343">SBC</span><span class="sxs-lookup"><span data-stu-id="41123-343">SBC</span></span> | <span data-ttu-id="41123-344">3478, 3479 y 49 152 - 53 247</span><span class="sxs-lookup"><span data-stu-id="41123-344">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="41123-345">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="41123-345">Defined on the SBC</span></span> |
| <span data-ttu-id="41123-346">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="41123-346">UDP/SRTP</span></span> | <span data-ttu-id="41123-347">SBC</span><span class="sxs-lookup"><span data-stu-id="41123-347">SBC</span></span> | <span data-ttu-id="41123-348">Procesador multimedia</span><span class="sxs-lookup"><span data-stu-id="41123-348">Media Processor</span></span> | <span data-ttu-id="41123-349">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="41123-349">Defined on the SBC</span></span> | <span data-ttu-id="41123-350">3478, 3479 y 49 152 - 53 247</span><span class="sxs-lookup"><span data-stu-id="41123-350">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="41123-351">Configurar troncos independientes para la omisión de medios y la omisión no multimedia</span><span class="sxs-lookup"><span data-stu-id="41123-351">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="41123-352">Si va a migrar a la omisión de medios desde la omisión no multimedia y desea confirmar la funcionalidad antes de migrar todo el uso a la omisión de medios, puede crear un tronco independiente y una directiva de enrutamiento de voz en línea independiente para enrutar al tronco de omisión multimedia y asignarlo a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="41123-352">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="41123-353">Pasos de configuración de alto nivel:</span><span class="sxs-lookup"><span data-stu-id="41123-353">High-level configuration steps:</span></span>

- <span data-ttu-id="41123-354">Identificar usuarios para probar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="41123-354">Identify users to test media bypass.</span></span>

- <span data-ttu-id="41123-355">Cree dos troncos independientes con FQDN diferentes: uno habilitado para la omisión de medios; el otro no.</span><span class="sxs-lookup"><span data-stu-id="41123-355">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="41123-356">Ambos troncos apuntan al mismo SBC.</span><span class="sxs-lookup"><span data-stu-id="41123-356">Both trunks point to the same SBC.</span></span> <span data-ttu-id="41123-357">Los puertos para la señalización SIP TLS deben ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="41123-357">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="41123-358">Los puertos para medios deben ser los mismos.</span><span class="sxs-lookup"><span data-stu-id="41123-358">The ports for media must be the same.</span></span>

- <span data-ttu-id="41123-359">Cree una nueva directiva de enrutamiento de voz en línea y asigne el tronco de omisión multimedia a las rutas correspondientes asociadas con el uso de RTC para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="41123-359">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="41123-360">Asigne la nueva directiva de enrutamiento de voz en línea a los usuarios identificados para probar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="41123-360">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="41123-361">En el ejemplo siguiente se muestra esta lógica.</span><span class="sxs-lookup"><span data-stu-id="41123-361">The example below illustrates this logic.</span></span>

| <span data-ttu-id="41123-362">Conjunto de usuarios</span><span class="sxs-lookup"><span data-stu-id="41123-362">Set of users</span></span> | <span data-ttu-id="41123-363">Número de usuarios</span><span class="sxs-lookup"><span data-stu-id="41123-363">Number of users</span></span> | <span data-ttu-id="41123-364">FQDN de tronco asignado en OVRP</span><span class="sxs-lookup"><span data-stu-id="41123-364">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="41123-365">Omisión de medios habilitada</span><span class="sxs-lookup"><span data-stu-id="41123-365">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="41123-366">Usuarios con tronco de omisión no multimedia</span><span class="sxs-lookup"><span data-stu-id="41123-366">Users with non-media bypass trunk</span></span> | <span data-ttu-id="41123-367">980</span><span class="sxs-lookup"><span data-stu-id="41123-367">980</span></span> | <span data-ttu-id="41123-368">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="41123-368">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="41123-369">falso</span><span class="sxs-lookup"><span data-stu-id="41123-369">false</span></span> |
<span data-ttu-id="41123-370">Usuarios con tronco de omisión multimedia</span><span class="sxs-lookup"><span data-stu-id="41123-370">Users with media bypass trunk</span></span> | <span data-ttu-id="41123-371">20</span><span class="sxs-lookup"><span data-stu-id="41123-371">20</span></span> | <span data-ttu-id="41123-372">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="41123-372">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="41123-373">verdadero</span><span class="sxs-lookup"><span data-stu-id="41123-373">true</span></span> | 

<span data-ttu-id="41123-374">Ambos troncos pueden apuntar al mismo SBC con la misma dirección IP pública.</span><span class="sxs-lookup"><span data-stu-id="41123-374">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="41123-375">Los puertos de señalización TLS del SBC deben ser diferentes, como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="41123-375">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="41123-376">Tenga en cuenta que tendrá que asegurarse de que el certificado admite ambos troncos.</span><span class="sxs-lookup"><span data-stu-id="41123-376">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="41123-377">En SAN, debe tener dos nombres **(sbc1.contoso.com** y **sbc2.contoso.com)** o tener un certificado comodín.</span><span class="sxs-lookup"><span data-stu-id="41123-377">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41123-378">![Muestra que ambos troncos pueden apuntar al mismo SBC con la misma IP pública](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="41123-378">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="41123-379">Para obtener información sobre cómo configurar dos troncos en el mismo SBC, vea la documentación proporcionada por el proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="41123-379">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="41123-380">Documentación de implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="41123-380">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="41123-381">Documentación de implementación de Oracle</span><span class="sxs-lookup"><span data-stu-id="41123-381">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="41123-382">Documentación de implementación de Comunicaciones de la cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="41123-382">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="41123-383">Documentación de implementación de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="41123-383">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="41123-384">Extremos de cliente compatibles con la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="41123-384">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="41123-385">La omisión de medios es compatible con todos los Teams de escritorio independientes, clientes de Android e iOS y Teams Teléfono dispositivos.</span><span class="sxs-lookup"><span data-stu-id="41123-385">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="41123-386">Para todos los demás puntos de conexión que no admiten la omisión de medios, convertiremos la llamada en no omitir, incluso si se inició como una llamada de omisión.</span><span class="sxs-lookup"><span data-stu-id="41123-386">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="41123-387">Esto ocurre automáticamente y no requiere ninguna acción del administrador.</span><span class="sxs-lookup"><span data-stu-id="41123-387">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="41123-388">Esto incluye Skype Empresarial teléfonos 3PIP y clientes web Teams compatibles con las llamadas de enrutamiento directo (clientes basados en WebRTC que se ejecutan en Microsoft Edge, Google Chrome y Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="41123-388">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="41123-389">Vea también</span><span class="sxs-lookup"><span data-stu-id="41123-389">See also</span></span>

[<span data-ttu-id="41123-390">Configurar el desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="41123-390">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
