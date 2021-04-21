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
description: Obtenga información sobre cómo planear la omisión de medios con enrutamiento directo del sistema telefónico, lo que le permite acortar la ruta de acceso al tráfico multimedia y mejorar el rendimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2cbe739a567588b44bef87f7b852ed8de965ad3
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899101"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="83814-103">Planear desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="83814-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="83814-104">Acerca de la omisión de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="83814-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="83814-105">La omisión de medios le permite acortar la ruta del tráfico multimedia y reducir el número de saltos en tránsito para un mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="83814-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="83814-106">Con la omisión de medios, los medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente en lugar de enviarlo a través del sistema telefónico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="83814-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="83814-107">Para configurar la omisión de medios, el SBC y el cliente deben estar en la misma ubicación o red.</span><span class="sxs-lookup"><span data-stu-id="83814-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="83814-108">Puede controlar la omisión de medios para cada SBC mediante el comando **Set-CSOnlinePSTNGateway** con el **parámetro -MediaBypass** establecido en verdadero o falso.</span><span class="sxs-lookup"><span data-stu-id="83814-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="83814-109">Si habilita la omisión de medios, esto no significa que todo el tráfico multimedia permanezca dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="83814-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="83814-110">En este artículo se describe el flujo de llamadas en diferentes escenarios.</span><span class="sxs-lookup"><span data-stu-id="83814-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="83814-111">Los diagramas siguientes ilustran la diferencia en el flujo de llamadas con y sin omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="83814-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="83814-112">Sin omisión de medios, cuando un cliente realiza o recibe una llamada, tanto la señalización como el flujo multimedia entre el SBC, microsoft phone system y el cliente de Teams, como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="83814-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83814-113">![Muestra la señalización y el flujo de medios sin omisión de medios](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="83814-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="83814-114">Pero supongamos que un usuario está en el mismo edificio o red que el SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="83814-115">Por ejemplo, supongamos que un usuario que se encuentra en un edificio de Fráncfort realiza una llamada a un usuario RTC:</span><span class="sxs-lookup"><span data-stu-id="83814-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="83814-116">**Sin el desvío** de medios, los medios fluirán a través de Ámsterdam o Dublín (donde se implementan los centros de datos de Microsoft) y de nuevo al SBC de Fráncfort.</span><span class="sxs-lookup"><span data-stu-id="83814-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="83814-117">El centro de datos en Europa está seleccionado porque el SBC está en Europa y Microsoft usa el centro de datos más próximo al SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="83814-118">Aunque este enfoque no afecta a la calidad de las llamadas debido a la optimización del flujo de tráfico dentro de las redes de Microsoft en la mayoría de las geografías, el tráfico tiene un bucle innecesario.</span><span class="sxs-lookup"><span data-stu-id="83814-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="83814-119">**Con la omisión** de medios, el contenido multimedia se mantiene directamente entre el usuario de Teams y el SBC, como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="83814-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="83814-120">![Muestra la señalización y el flujo multimedia con la omisión de medios](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="83814-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="83814-121">La omisión de medios aprovecha los protocolos denominados Establecimiento de conectividad interactiva (ICE) en el cliente de Teams y ICE lite en el SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="83814-122">Estos protocolos permiten que el enrutamiento directo use la ruta multimedia más directa para obtener una calidad óptima.</span><span class="sxs-lookup"><span data-stu-id="83814-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="83814-123">ICE y ICE Lite son estándares webRTC.</span><span class="sxs-lookup"><span data-stu-id="83814-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="83814-124">Para obtener información detallada sobre estos protocolos, vea RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="83814-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="83814-125">Planificación del flujo de llamadas y del firewall</span><span class="sxs-lookup"><span data-stu-id="83814-125">Call flow and firewall planning</span></span>

<span data-ttu-id="83814-126">El flujo de llamadas y la planificación del firewall dependen de si el usuario tiene acceso directo a la dirección IP pública del SBC y de si el usuario está dentro o fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="83814-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="83814-127">Flujo de llamadas si el usuario tiene acceso directo a la dirección IP pública del SBC</span><span class="sxs-lookup"><span data-stu-id="83814-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="83814-128">Si el usuario tiene acceso directo a la dirección IP pública del SBC, el flujo de llamadas es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="83814-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="83814-129">Para la omisión de medios, el cliente de Teams debe tener acceso a la dirección IP pública del SBC incluso desde una red interna.</span><span class="sxs-lookup"><span data-stu-id="83814-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="83814-130">Si no se desea usar medios directos, los medios pueden fluir a través de retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="83814-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="83814-131">Esta es la solución recomendada cuando un usuario está en el mismo edificio o red que el SBC: quite los componentes de Microsoft Cloud de la ruta de acceso multimedia.</span><span class="sxs-lookup"><span data-stu-id="83814-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="83814-132">La señalización siempre fluye a través de la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="83814-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="83814-133">En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es interno y el cliente puede llegar a la dirección IP pública del SBC (medios directos):</span><span class="sxs-lookup"><span data-stu-id="83814-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="83814-134">Las flechas y los valores numéricos de las rutas de acceso se ajustan a los flujos [de llamadas de Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="83814-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="83814-135">La señalización SIP siempre toma trayectorias 4 y 4' (según la dirección del tráfico).</span><span class="sxs-lookup"><span data-stu-id="83814-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="83814-136">Multimedia permanece local y toma la ruta 5b.</span><span class="sxs-lookup"><span data-stu-id="83814-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83814-137">![Muestra el flujo de llamadas con la omisión de medios habilitada, el cliente es interno](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="83814-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="83814-138">Flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC</span><span class="sxs-lookup"><span data-stu-id="83814-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="83814-139">A continuación se describe el flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="83814-140">Por ejemplo, suponga que el usuario es externo y el administrador de inquilinos decidió no abrir la dirección IP pública del SBC a todos los usuarios de Internet, sino solo a Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="83814-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="83814-141">Los componentes internos del tráfico pueden fluir a través de los Retransmisión de transporte de Teams.</span><span class="sxs-lookup"><span data-stu-id="83814-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="83814-142">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83814-142">Consider the following:</span></span>

- <span data-ttu-id="83814-143">Se usan retransmisión de transporte de Teams.</span><span class="sxs-lookup"><span data-stu-id="83814-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="83814-144">Para la omisión de medios, Microsoft usa una versión de retransmisión de transporte que requiere abrir puertos de 50 000 a 59 999 entre los retransmisión de transporte de Teams y el SBC (en el futuro planeamos pasar a la versión que solo requiere 3478 y 3479 puertos).</span><span class="sxs-lookup"><span data-stu-id="83814-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="83814-145">En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente no puede llegar a la dirección IP pública del controlador de borde de sesión (los medios se retransmiten por Teams Transport Relay).</span><span class="sxs-lookup"><span data-stu-id="83814-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="83814-146">Las flechas y los valores numéricos de las rutas de acceso se ajustan a los flujos [de llamadas de Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="83814-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="83814-147">Los medios se retransmiten a través de las rutas 3, 3', 4 y 4'</span><span class="sxs-lookup"><span data-stu-id="83814-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83814-148">![Muestra el flujo de llamadas si el usuario no tiene acceso a la IP pública del SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="83814-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="83814-149">Flujo de llamadas si un usuario está fuera de la red y tiene acceso a la DIRECCIÓN IP pública del SBC</span><span class="sxs-lookup"><span data-stu-id="83814-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="83814-150">Esta no es una configuración recomendada porque no aprovecha los retransmisión de transporte de Teams.</span><span class="sxs-lookup"><span data-stu-id="83814-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="83814-151">En su lugar, debe considerar el escenario anterior en el que el usuario no tiene acceso a la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="83814-152">En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente puede llegar a la dirección IP pública del SBC (medios directos).</span><span class="sxs-lookup"><span data-stu-id="83814-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="83814-153">Las flechas y los valores numéricos de las rutas de acceso se ajustan al artículo flujos de [llamadas de Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="83814-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="83814-154">La señalización SIP siempre toma trayectorias 3 y 3' (según la dirección del tráfico).</span><span class="sxs-lookup"><span data-stu-id="83814-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="83814-155">Los flujos multimedia usan la ruta 2.</span><span class="sxs-lookup"><span data-stu-id="83814-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83814-156">![Muestra el flujo de llamadas si el usuario no tiene acceso a la IP pública del SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="83814-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="83814-157">Uso de procesadores multimedia y retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="83814-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="83814-158">Hay dos componentes en microsoft cloud que pueden estar en la ruta del tráfico multimedia: procesadores multimedia y retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="83814-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="83814-159">El procesador multimedia es un componente orientado al público que controla los medios en casos que no se omiten y controla los medios para las aplicaciones de voz.</span><span class="sxs-lookup"><span data-stu-id="83814-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="83814-160">Los procesadores multimedia siempre están en la ruta de acceso para las llamadas no omitidas por el usuario final, pero nunca en la ruta de acceso para las llamadas omitida.</span><span class="sxs-lookup"><span data-stu-id="83814-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="83814-161">Los procesadores multimedia siempre están en la ruta de acceso para todas las aplicaciones de voz, como Parque de llamadas, Operador automático y Colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="83814-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="83814-162">El Retransmisión de transporte se usa para conectarse al servicio de transporte más cercano para enviar tráfico en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="83814-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="83814-163">Las retransmisiones de transporte pueden o no estar en la ruta de acceso para llamadas omitida (que proceden o están destinadas a usuarios finales), dependiendo de dónde se encuentra el usuario y de cómo esté configurada la red.</span><span class="sxs-lookup"><span data-stu-id="83814-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="83814-164">En el siguiente diagrama se muestran dos flujos de llamadas: uno con la omisión de medios habilitada y la segunda con la omisión de medios deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="83814-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="83814-165">En el diagrama solo se muestra el tráfico procedente o destinado a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="83814-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="83814-166">El controlador multimedia es un microservicio de Azure que asigna procesadores multimedia y crea ofertas del Protocolo de descripción de sesión (SDP).</span><span class="sxs-lookup"><span data-stu-id="83814-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="83814-167">El proxy SIP es un componente que traduce la señalización HTTP REST que se usa en Teams a SIP.</span><span class="sxs-lookup"><span data-stu-id="83814-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83814-168">![Muestra los flujos de llamadas con la omisión de medios habilitada y deshabilitada](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="83814-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="83814-169">En la tabla siguiente se resume la diferencia entre los procesadores multimedia y los relés de transporte.</span><span class="sxs-lookup"><span data-stu-id="83814-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="83814-170">Procesadores multimedia</span><span class="sxs-lookup"><span data-stu-id="83814-170">Media Processors</span></span> | <span data-ttu-id="83814-171">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="83814-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="83814-172">En la ruta de acceso multimedia para llamadas no omitida para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="83814-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="83814-173">Siempre</span><span class="sxs-lookup"><span data-stu-id="83814-173">Always</span></span> | <span data-ttu-id="83814-174">Si el cliente no puede ponerse en contacto directamente con el Procesador multimedia</span><span class="sxs-lookup"><span data-stu-id="83814-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="83814-175">En la ruta de acceso multimedia para llamadas omitida para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="83814-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="83814-176">Nunca</span><span class="sxs-lookup"><span data-stu-id="83814-176">Never</span></span> | <span data-ttu-id="83814-177">Si el cliente no puede llegar al SBC en la dirección IP pública</span><span class="sxs-lookup"><span data-stu-id="83814-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="83814-178">En la ruta de acceso multimedia para aplicaciones de voz</span><span class="sxs-lookup"><span data-stu-id="83814-178">In media path for voice applications</span></span> | <span data-ttu-id="83814-179">Siempre</span><span class="sxs-lookup"><span data-stu-id="83814-179">Always</span></span> | <span data-ttu-id="83814-180">Nunca</span><span class="sxs-lookup"><span data-stu-id="83814-180">Never</span></span> | 
<span data-ttu-id="83814-181">Puede realizar la transcodificación (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="83814-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="83814-182">Sí</span><span class="sxs-lookup"><span data-stu-id="83814-182">Yes</span></span> | <span data-ttu-id="83814-183">No, solo retransmite audio entre puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="83814-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="83814-184">Número de instancias en todo el mundo y ubicación</span><span class="sxs-lookup"><span data-stu-id="83814-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="83814-185">10 total: 2 en Ee. UU. Este y Oeste; 2 en Ámsterdam y Dublín; 2 en Hong Kong y Singapur; 2 en Japón; 2 en Australia Este y Sureste</span><span class="sxs-lookup"><span data-stu-id="83814-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="83814-186">Múltiplo</span><span class="sxs-lookup"><span data-stu-id="83814-186">Multiple</span></span>

<span data-ttu-id="83814-187">Los rangos IP son:</span><span class="sxs-lookup"><span data-stu-id="83814-187">The IP ranges are:</span></span>
- <span data-ttu-id="83814-188">52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="83814-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="83814-189">52.120.0.0/14 (direcciones IP de 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="83814-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="83814-190">\* Explicación de transcodificación:</span><span class="sxs-lookup"><span data-stu-id="83814-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="83814-191">El procesador multimedia es B2BUA, lo que significa que puede cambiar un códec (por ejemplo, SILK de cliente de Teams a MP y G.711 entre MP y SBC).</span><span class="sxs-lookup"><span data-stu-id="83814-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="83814-192">Los relés de transporte no son B2BUA, lo que significa que el códec nunca se cambia entre el cliente y el SBC, incluso si el tráfico fluye a través de retransmisión.</span><span class="sxs-lookup"><span data-stu-id="83814-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="83814-193">Uso de procesadores multimedia de Teams si el tronco está configurado para la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="83814-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="83814-194">Los procesadores multimedia de Teams siempre se insertan en la ruta de acceso multimedia en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="83814-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="83814-195">La llamada se escala de 1:1 a una llamada grupal</span><span class="sxs-lookup"><span data-stu-id="83814-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="83814-196">La llamada se va a un usuario federado de Teams</span><span class="sxs-lookup"><span data-stu-id="83814-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="83814-197">La llamada se reenvía o se transfiere a un usuario de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="83814-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="83814-198">Asegúrese de que su SBC tiene acceso a los rangos procesadores multimedia y retransmisión de transporte como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="83814-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="83814-199">Señalización SIP: FQDN</span><span class="sxs-lookup"><span data-stu-id="83814-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="83814-200">Para la señalización SIP, los requisitos de FQDN y firewall son los mismos que para los casos no omitido.</span><span class="sxs-lookup"><span data-stu-id="83814-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="83814-201">El enrutamiento directo se ofrece en los siguientes entornos de Microsoft 365 u Office 365:</span><span class="sxs-lookup"><span data-stu-id="83814-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="83814-202">Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="83814-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="83814-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="83814-203">Office 365 GCC</span></span>
- <span data-ttu-id="83814-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="83814-204">Office 365 GCC High</span></span>
- <span data-ttu-id="83814-205">Office 365 DoD Obtenga más información sobre los entornos de [Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) y del gobierno de Estados Unidos, como GCC, GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="83814-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="83814-206">Entornos GCC de Microsoft 365, Office 365 y Office 365</span><span class="sxs-lookup"><span data-stu-id="83814-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="83814-207">Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:</span><span class="sxs-lookup"><span data-stu-id="83814-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="83814-208">**sip.pstnhub.microsoft.com:** FQDN global, debe probarse primero.</span><span class="sxs-lookup"><span data-stu-id="83814-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="83814-209">Cuando el SBC envía una solicitud para resolver este nombre, los servidores DNS de Microsoft Azure devuelven una dirección IP que apunta al centro de datos de Azure principal asignado al SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="83814-210">La tarea se basa en las métricas de rendimiento de los centros de datos y la proximidad geográfica al SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="83814-211">La dirección IP devuelta corresponde al FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="83814-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="83814-212">**sip2.pstnhub.microsoft.com:** FQDN secundario, se asigna geográficamente a la región de segunda prioridad.</span><span class="sxs-lookup"><span data-stu-id="83814-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="83814-213">**sip3.pstnhub.microsoft.com:** FQDN terciario, se asigna geográficamente a la región de tercera prioridad.</span><span class="sxs-lookup"><span data-stu-id="83814-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="83814-214">Debe colocar estos tres FQDN para:</span><span class="sxs-lookup"><span data-stu-id="83814-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="83814-215">Proporcione una experiencia óptima (menos cargada y más cercana al centro de datos de SBC asignada consultando el primer FQDN).</span><span class="sxs-lookup"><span data-stu-id="83814-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="83814-216">Proporcionar conmutación por error cuando se establece una conexión desde un SBC a un centro de datos que experimenta un problema temporal.</span><span class="sxs-lookup"><span data-stu-id="83814-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="83814-217">Para obtener más información, vea Mecanismo de conmutación por error a continuación.</span><span class="sxs-lookup"><span data-stu-id="83814-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="83814-218">Los FQDN **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** y **sip3.pstnhub.microsoft.com** se resolverán en una de las siguientes direcciones IP:</span><span class="sxs-lookup"><span data-stu-id="83814-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="83814-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="83814-219">52.114.148.0</span></span>
- <span data-ttu-id="83814-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="83814-220">52.114.132.46</span></span>
- <span data-ttu-id="83814-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="83814-221">52.114.16.74</span></span>
- <span data-ttu-id="83814-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="83814-222">52.114.20.29</span></span>
- <span data-ttu-id="83814-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="83814-223">52.114.75.24</span></span>
- <span data-ttu-id="83814-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="83814-224">52.114.76.76</span></span>
- <span data-ttu-id="83814-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="83814-225">52.114.7.24</span></span>
- <span data-ttu-id="83814-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="83814-226">52.114.14.70</span></span>

<span data-ttu-id="83814-227">Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="83814-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="83814-228">Si el firewall admite nombres DNS, el FQDN **sip-all.pstnhub.microsoft.com** se resuelve en todas estas direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="83814-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="83814-229">Entorno doD de Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="83814-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="83814-230">El punto de conexión para enrutamiento directo es el siguiente FQDN:</span><span class="sxs-lookup"><span data-stu-id="83814-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="83814-231">**sip.pstnhub.dod.teams.microsoft.us:** FQDN global.</span><span class="sxs-lookup"><span data-stu-id="83814-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="83814-232">Dado que el entorno de DoD de Office 365 solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.</span><span class="sxs-lookup"><span data-stu-id="83814-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="83814-233">Los FQDN: sip.pstnhub.dod.teams.microsoft.us se resolverán en una de las siguientes direcciones IP:</span><span class="sxs-lookup"><span data-stu-id="83814-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="83814-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="83814-234">52.127.64.33</span></span>
- <span data-ttu-id="83814-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="83814-235">52.127.68.34</span></span>

<span data-ttu-id="83814-236">Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="83814-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="83814-237">Si el firewall admite nombres DNS, el FQDN sip.pstnhub.dod.teams.microsoft.us se resuelve en todas estas direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="83814-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="83814-238">Entorno alto de Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="83814-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="83814-239">El punto de conexión para enrutamiento directo es el siguiente FQDN:</span><span class="sxs-lookup"><span data-stu-id="83814-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="83814-240">**sip.pstnhub.gov.teams.microsoft.us:** FQDN global.</span><span class="sxs-lookup"><span data-stu-id="83814-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="83814-241">Como el entorno GCC High solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.</span><span class="sxs-lookup"><span data-stu-id="83814-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="83814-242">Los FQDN: sip.pstnhub.gov.teams.microsoft.us se resolverán en una de las siguientes direcciones IP:</span><span class="sxs-lookup"><span data-stu-id="83814-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="83814-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="83814-243">52.127.88.59</span></span>
- <span data-ttu-id="83814-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="83814-244">52.127.92.64</span></span>

<span data-ttu-id="83814-245">Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.</span><span class="sxs-lookup"><span data-stu-id="83814-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="83814-246">Si el firewall admite nombres DNS, el FQDN sip.pstnhub.gov.teams.microsoft.us se resuelve en todas estas direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="83814-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="83814-247">Señalización SIP: Puertos</span><span class="sxs-lookup"><span data-stu-id="83814-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="83814-248">Los requisitos de puerto son los mismos para todos los entornos de Office 365 en los que se ofrece enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="83814-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="83814-249">Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="83814-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="83814-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="83814-250">Office 365 GCC</span></span>
- <span data-ttu-id="83814-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="83814-251">Office 365 GCC High</span></span>
- <span data-ttu-id="83814-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="83814-252">Office 365 DoD</span></span>

<span data-ttu-id="83814-253">Debe usar los siguientes puertos:</span><span class="sxs-lookup"><span data-stu-id="83814-253">You must use the following ports:</span></span>

| <span data-ttu-id="83814-254">Tráfico</span><span class="sxs-lookup"><span data-stu-id="83814-254">Traffic</span></span> | <span data-ttu-id="83814-255">De</span><span class="sxs-lookup"><span data-stu-id="83814-255">From</span></span> | <span data-ttu-id="83814-256">Hasta</span><span class="sxs-lookup"><span data-stu-id="83814-256">To</span></span> | <span data-ttu-id="83814-257">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="83814-257">Source port</span></span> | <span data-ttu-id="83814-258">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="83814-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="83814-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="83814-259">SIP/TLS</span></span>| <span data-ttu-id="83814-260">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="83814-260">SIP Proxy</span></span> | <span data-ttu-id="83814-261">SBC</span><span class="sxs-lookup"><span data-stu-id="83814-261">SBC</span></span> | <span data-ttu-id="83814-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="83814-262">1024 - 65535</span></span> | <span data-ttu-id="83814-263">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="83814-263">Defined on the SBC</span></span> |
| <span data-ttu-id="83814-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="83814-264">SIP/TLS</span></span> | <span data-ttu-id="83814-265">SBC</span><span class="sxs-lookup"><span data-stu-id="83814-265">SBC</span></span> | <span data-ttu-id="83814-266">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="83814-266">SIP Proxy</span></span> | <span data-ttu-id="83814-267">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="83814-267">Defined on the SBC</span></span> | <span data-ttu-id="83814-268">5061</span><span class="sxs-lookup"><span data-stu-id="83814-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="83814-269">Tráfico multimedia: intervalos de IP y puertos</span><span class="sxs-lookup"><span data-stu-id="83814-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="83814-270">El tráfico multimedia fluye entre el SBC y el cliente de Teams si la conectividad directa está disponible o a través de retransmisión de transporte de Teams si el cliente no puede llegar al SBC con la dirección IP pública.</span><span class="sxs-lookup"><span data-stu-id="83814-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="83814-271">Requisitos para el tráfico multimedia directo (entre el cliente de Teams y el SBC)</span><span class="sxs-lookup"><span data-stu-id="83814-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="83814-272">El cliente debe tener acceso a los puertos especificados (ver tabla) en la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="83814-273">Si el cliente se encuentra en una red interna, el medio fluye a la dirección IP pública del SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-273">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="83814-274">Puede configurar la fijación de pelo en el dispositivo NAT para que el tráfico nunca salga del equipo de red empresarial.</span><span class="sxs-lookup"><span data-stu-id="83814-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="83814-275">Tráfico</span><span class="sxs-lookup"><span data-stu-id="83814-275">Traffic</span></span> | <span data-ttu-id="83814-276">De</span><span class="sxs-lookup"><span data-stu-id="83814-276">From</span></span> | <span data-ttu-id="83814-277">Hasta</span><span class="sxs-lookup"><span data-stu-id="83814-277">To</span></span> | <span data-ttu-id="83814-278">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="83814-278">Source port</span></span> | <span data-ttu-id="83814-279">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="83814-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="83814-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="83814-280">UDP/SRTP</span></span> | <span data-ttu-id="83814-281">Cliente</span><span class="sxs-lookup"><span data-stu-id="83814-281">Client</span></span> | <span data-ttu-id="83814-282">SBC</span><span class="sxs-lookup"><span data-stu-id="83814-282">SBC</span></span> | <span data-ttu-id="83814-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="83814-283">50 000 – 50 019</span></span>  | <span data-ttu-id="83814-284">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="83814-284">Defined on the SBC</span></span> |
| <span data-ttu-id="83814-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="83814-285">UDP/SRTP</span></span> | <span data-ttu-id="83814-286">SBC</span><span class="sxs-lookup"><span data-stu-id="83814-286">SBC</span></span> | <span data-ttu-id="83814-287">Cliente</span><span class="sxs-lookup"><span data-stu-id="83814-287">Client</span></span> | <span data-ttu-id="83814-288">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="83814-288">Defined on the SBC</span></span> | <span data-ttu-id="83814-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="83814-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="83814-290">Si tiene un dispositivo de red que traduce los puertos de origen del cliente, asegúrese de que los puertos traducidos se abren entre el equipo de red y el SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="83814-291">Requisitos para usar retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="83814-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="83814-292">Las retransmisión de transporte están en el mismo rango que los procesadores multimedia (para casos que no se omiten):</span><span class="sxs-lookup"><span data-stu-id="83814-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="83814-293">Entornos GCC de Microsoft 365, Office 365 y Office 365</span><span class="sxs-lookup"><span data-stu-id="83814-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="83814-294">52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="83814-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="83814-295">Entorno doD de Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="83814-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="83814-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="83814-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="83814-297">Entorno alto de Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="83814-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="83814-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="83814-298">52.127.88.0/21</span></span>


<span data-ttu-id="83814-299">En la tabla siguiente se muestra el rango de puertos de las Retransmisión de transporte de Teams (aplicable a todos los entornos):</span><span class="sxs-lookup"><span data-stu-id="83814-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="83814-300">Tráfico</span><span class="sxs-lookup"><span data-stu-id="83814-300">Traffic</span></span> | <span data-ttu-id="83814-301">De</span><span class="sxs-lookup"><span data-stu-id="83814-301">From</span></span> | <span data-ttu-id="83814-302">Hasta</span><span class="sxs-lookup"><span data-stu-id="83814-302">To</span></span> | <span data-ttu-id="83814-303">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="83814-303">Source port</span></span> | <span data-ttu-id="83814-304">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="83814-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="83814-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="83814-305">UDP/SRTP</span></span> | <span data-ttu-id="83814-306">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="83814-306">Transport Relay</span></span> | <span data-ttu-id="83814-307">SBC</span><span class="sxs-lookup"><span data-stu-id="83814-307">SBC</span></span> | <span data-ttu-id="83814-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="83814-308">50 000 -59 999</span></span>    | <span data-ttu-id="83814-309">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="83814-309">Defined on the SBC</span></span> |
| <span data-ttu-id="83814-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="83814-310">UDP/SRTP</span></span> | <span data-ttu-id="83814-311">SBC</span><span class="sxs-lookup"><span data-stu-id="83814-311">SBC</span></span> | <span data-ttu-id="83814-312">Retransmisión de transporte</span><span class="sxs-lookup"><span data-stu-id="83814-312">Transport Relay</span></span> | <span data-ttu-id="83814-313">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="83814-313">Defined on the SBC</span></span> | <span data-ttu-id="83814-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="83814-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="83814-315">Microsoft recomienda al menos dos puertos por llamada simultánea en el SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="83814-316">Dado que Microsoft tiene dos versiones de retransmisión de transporte, son necesarias las siguientes:</span><span class="sxs-lookup"><span data-stu-id="83814-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="83814-317">v4, que solo puede funcionar con el rango de puertos de 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="83814-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="83814-318">v6, que funciona con los puertos 3478 y 3479</span><span class="sxs-lookup"><span data-stu-id="83814-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="83814-319">En este momento, la omisión de medios solo admite la versión v4 de retransmisión de transporte.</span><span class="sxs-lookup"><span data-stu-id="83814-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="83814-320">Presentaremos compatibilidad con v6 en el futuro.</span><span class="sxs-lookup"><span data-stu-id="83814-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="83814-321">Debe abrir los puertos 3478 y 3479 para la transición.</span><span class="sxs-lookup"><span data-stu-id="83814-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="83814-322">Cuando Microsoft presenta compatibilidad con retransmisión de transporte v6 con omisión de medios, no tendrá que volver a configurar el equipo de red ni los SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="83814-323">Requisitos para usar procesadores multimedia</span><span class="sxs-lookup"><span data-stu-id="83814-323">Requirements for using media processors</span></span>

<span data-ttu-id="83814-324">Los procesadores multimedia siempre están en la ruta de acceso multimedia para aplicaciones de voz y para clientes web (por ejemplo, clientes de Teams en Edge o Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="83814-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="83814-325">Los requisitos son los mismos que para la configuración sin omisión.</span><span class="sxs-lookup"><span data-stu-id="83814-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="83814-326">El intervalo IP para el tráfico multimedia es</span><span class="sxs-lookup"><span data-stu-id="83814-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="83814-327">Entornos GCC de Office 365 y Office 365</span><span class="sxs-lookup"><span data-stu-id="83814-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="83814-328">52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="83814-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="83814-329">Entorno doD de Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="83814-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="83814-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="83814-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="83814-331">Entorno alto de Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="83814-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="83814-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="83814-332">52.127.88.0/21</span></span>

<span data-ttu-id="83814-333">El rango de puertos de los procesadores multimedia (aplicable a todos los entornos) se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="83814-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="83814-334">Tráfico</span><span class="sxs-lookup"><span data-stu-id="83814-334">Traffic</span></span> | <span data-ttu-id="83814-335">De</span><span class="sxs-lookup"><span data-stu-id="83814-335">From</span></span> | <span data-ttu-id="83814-336">Hasta</span><span class="sxs-lookup"><span data-stu-id="83814-336">To</span></span> | <span data-ttu-id="83814-337">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="83814-337">Source port</span></span> | <span data-ttu-id="83814-338">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="83814-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="83814-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="83814-339">UDP/SRTP</span></span> | <span data-ttu-id="83814-340">Procesador multimedia</span><span class="sxs-lookup"><span data-stu-id="83814-340">Media Processor</span></span> | <span data-ttu-id="83814-341">SBC</span><span class="sxs-lookup"><span data-stu-id="83814-341">SBC</span></span> | <span data-ttu-id="83814-342">3478, 3479 y 49 152 - 53 247</span><span class="sxs-lookup"><span data-stu-id="83814-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="83814-343">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="83814-343">Defined on the SBC</span></span> |
| <span data-ttu-id="83814-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="83814-344">UDP/SRTP</span></span> | <span data-ttu-id="83814-345">SBC</span><span class="sxs-lookup"><span data-stu-id="83814-345">SBC</span></span> | <span data-ttu-id="83814-346">Procesador multimedia</span><span class="sxs-lookup"><span data-stu-id="83814-346">Media Processor</span></span> | <span data-ttu-id="83814-347">Definido en el SBC</span><span class="sxs-lookup"><span data-stu-id="83814-347">Defined on the SBC</span></span> | <span data-ttu-id="83814-348">3478, 3479 y 49 152 - 53 247</span><span class="sxs-lookup"><span data-stu-id="83814-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="83814-349">Configurar troncos independientes para la omisión de medios y la omisión no multimedia</span><span class="sxs-lookup"><span data-stu-id="83814-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="83814-350">Si va a migrar a la omisión de medios desde la omisión no multimedia y desea confirmar la funcionalidad antes de migrar todo el uso a la omisión de medios, puede crear un tronco independiente y una directiva de enrutamiento de voz en línea independiente para enrutar al tronco de omisión multimedia y asignarlo a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="83814-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="83814-351">Pasos de configuración de alto nivel:</span><span class="sxs-lookup"><span data-stu-id="83814-351">High-level configuration steps:</span></span>

- <span data-ttu-id="83814-352">Identificar usuarios para probar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="83814-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="83814-353">Cree dos troncos independientes con FQDN diferentes: uno habilitado para la omisión de medios; el otro no.</span><span class="sxs-lookup"><span data-stu-id="83814-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="83814-354">Ambos troncos apuntan al mismo SBC.</span><span class="sxs-lookup"><span data-stu-id="83814-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="83814-355">Los puertos para la señalización SIP TLS deben ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="83814-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="83814-356">Los puertos para medios deben ser los mismos.</span><span class="sxs-lookup"><span data-stu-id="83814-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="83814-357">Cree una nueva directiva de enrutamiento de voz en línea y asigne el tronco de omisión multimedia a las rutas correspondientes asociadas con el uso de RTC para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="83814-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="83814-358">Asigne la nueva directiva de enrutamiento de voz en línea a los usuarios identificados para probar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="83814-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="83814-359">En el ejemplo siguiente se muestra esta lógica.</span><span class="sxs-lookup"><span data-stu-id="83814-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="83814-360">Conjunto de usuarios</span><span class="sxs-lookup"><span data-stu-id="83814-360">Set of users</span></span> | <span data-ttu-id="83814-361">Número de usuarios</span><span class="sxs-lookup"><span data-stu-id="83814-361">Number of users</span></span> | <span data-ttu-id="83814-362">FQDN de tronco asignado en OVRP</span><span class="sxs-lookup"><span data-stu-id="83814-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="83814-363">Omisión de medios habilitada</span><span class="sxs-lookup"><span data-stu-id="83814-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="83814-364">Usuarios con tronco de omisión no multimedia</span><span class="sxs-lookup"><span data-stu-id="83814-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="83814-365">980</span><span class="sxs-lookup"><span data-stu-id="83814-365">980</span></span> | <span data-ttu-id="83814-366">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="83814-366">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="83814-367">falso</span><span class="sxs-lookup"><span data-stu-id="83814-367">false</span></span> |
<span data-ttu-id="83814-368">Usuarios con tronco de omisión multimedia</span><span class="sxs-lookup"><span data-stu-id="83814-368">Users with media bypass trunk</span></span> | <span data-ttu-id="83814-369">20</span><span class="sxs-lookup"><span data-stu-id="83814-369">20</span></span> | <span data-ttu-id="83814-370">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="83814-370">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="83814-371">verdadero</span><span class="sxs-lookup"><span data-stu-id="83814-371">true</span></span> | 

<span data-ttu-id="83814-372">Ambos troncos pueden apuntar al mismo SBC con la misma dirección IP pública.</span><span class="sxs-lookup"><span data-stu-id="83814-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="83814-373">Los puertos de señalización TLS del SBC deben ser diferentes, como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="83814-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="83814-374">Tenga en cuenta que tendrá que asegurarse de que el certificado admite ambos troncos.</span><span class="sxs-lookup"><span data-stu-id="83814-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="83814-375">En SAN, debe tener dos nombres **(sbc1.contoso.com** y **sbc2.contoso.com)** o tener un certificado comodín.</span><span class="sxs-lookup"><span data-stu-id="83814-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83814-376">![Muestra que ambos troncos pueden apuntar al mismo SBC con la misma IP pública](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="83814-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="83814-377">Para obtener información sobre cómo configurar dos troncos en el mismo SBC, vea la documentación proporcionada por el proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="83814-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="83814-378">Documentación de implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="83814-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="83814-379">Documentación de implementación de Oracle</span><span class="sxs-lookup"><span data-stu-id="83814-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="83814-380">Documentación de implementación de Comunicaciones de la cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="83814-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="83814-381">Documentación de implementación de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="83814-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="83814-382">Extremos de cliente compatibles con la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="83814-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="83814-383">La omisión de medios es compatible con todos los clientes de escritorio independientes de Teams, los clientes android e iOS y los dispositivos telefónicos de Teams.</span><span class="sxs-lookup"><span data-stu-id="83814-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="83814-384">Para todos los demás puntos de conexión que no admiten la omisión de medios, convertiremos la llamada en no omitir, incluso si se inició como una llamada de omisión.</span><span class="sxs-lookup"><span data-stu-id="83814-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="83814-385">Esto ocurre automáticamente y no requiere ninguna acción del administrador.</span><span class="sxs-lookup"><span data-stu-id="83814-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="83814-386">Esto incluye teléfonos 3PIP de Skype Empresarial y clientes web de Teams que admiten llamadas de enrutamiento directo (clientes basados en WebRTC que se ejecutan en Microsoft Edge, Google Chrome y Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="83814-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="83814-387">Vea también</span><span class="sxs-lookup"><span data-stu-id="83814-387">See also</span></span>

[<span data-ttu-id="83814-388">Configurar el desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="83814-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
