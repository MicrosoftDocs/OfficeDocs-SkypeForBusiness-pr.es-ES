---
title: Conmutación por error de tronco en llamadas salientes
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
description: Lea este tema para obtener información sobre cómo administrar la conmutación por error del tronco en llamadas salientes de Teams al controlador de borde de sesión (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836182"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="1f2f1-103">Conmutación por error de tronco en llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="1f2f1-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="1f2f1-104">En este tema se describe cómo evitar la conmutación por error de enlace en llamadas salientes, desde equipos hasta el controlador de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="1f2f1-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="1f2f1-105">Conmutación por error de red</span><span class="sxs-lookup"><span data-stu-id="1f2f1-105">Failover on network errors</span></span>

<span data-ttu-id="1f2f1-106">Si, por cualquier motivo, no se puede conectar un tronco, se intentará establecer la conexión con el mismo tronco desde otro centro de recursos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="1f2f1-107">Es posible que un tronco no esté conectado, por ejemplo, si se rechaza una conexión, si hay un tiempo de espera de TLS, o si hay algún otro problema de nivel de red.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="1f2f1-108">Por ejemplo, una conexión podría fallar si un administrador limita el acceso a la SBC solo de direcciones IP conocidas, pero se olvida de colocar las direcciones IP de todos los centros de información de enrutamiento directo de Microsoft en la lista de control de acceso (ACL) de la SBC.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="1f2f1-109">Conmutación por error de códigos SIP específicos recibidos del controlador de borde de sesión (SBC)</span><span class="sxs-lookup"><span data-stu-id="1f2f1-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="1f2f1-110">Si el enrutamiento directo recibe códigos de error de SIP o 6xx, como respuesta a una invitación saliente, la llamada se considera completada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="1f2f1-111">Saliente significa una llamada de un cliente de equipo a la red de telefonía pública conmutada (RTC) con el siguiente flujo de tráfico: Teams Client: > enrutamiento directo: > red de telefonía > de SBC-.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="1f2f1-112">La lista de códigos de SIP puede encontrarse en [RFC de protocolo de inicio de sesión (SIP)](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="1f2f1-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="1f2f1-113">Asumamos una situación en la que un SBC respondió en una invitación entrante con el código "408 solicitud de tiempo de espera: el servidor no pudo producir una respuesta dentro de un período de tiempo adecuado, por ejemplo, si no puede determinar la ubicación del usuario en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="1f2f1-114">El cliente puede repetir la solicitud sin realizar modificaciones en el momento en que lo desee.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="1f2f1-115">Este SBC en particular podría estar teniendo dificultades para conectar con el destinatario; quizás debido a un error de configuración de red o a otro error.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="1f2f1-116">Sin embargo, hay un más SBC en la ruta que podría llegar al destinatario.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="1f2f1-117">En el siguiente diagrama, cuando un usuario hace una llamada a un número de teléfono, hay dos SBCs en la ruta que puede entregar esta llamada.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="1f2f1-118">Inicialmente, SBC1.contoso.com está seleccionado para la llamada, pero SBC1.contoso.com no puede comunicarse con una red RTC debido a un problema de red.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="1f2f1-119">De forma predeterminada, la llamada se completará en este momento.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-119">By default, the call will be completed at this moment.</span></span> 
 
![Diagrama que muestra SBC no se puede comunicar con la RTC debido a un problema de red](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="1f2f1-121">Pero hay otra SBC en la ruta que puede entregar la llamada.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="1f2f1-122">Si configura el parámetro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, el segundo SBC se intentará--SBC2.contoso.com en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="1f2f1-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Diagrama que muestra el enrutamiento al segundo SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="1f2f1-124">El establecimiento del parámetro-FailoverResponseCodes y la especificación de códigos le ayuda a ajustar el enrutamiento y evitar posibles problemas cuando una SBC no puede realizar una llamada debido a problemas de red o de otro tipos.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="1f2f1-125">Valores predeterminados: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="1f2f1-125">Default values:  408, 503, 504</span></span>

