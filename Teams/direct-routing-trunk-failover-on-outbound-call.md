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
description: Lea este tema para obtener información sobre cómo controlar las conmutación por error en las llamadas salientes desde Teams al controlador de borde de sesión (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836182"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="2d5c5-103">Conmutación por error de tronco en llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="2d5c5-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="2d5c5-104">En este tema se describe cómo evitar conmutación por error en las llamadas salientes desde Teams al controlador de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="2d5c5-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="2d5c5-105">Conmutación por error en errores de red</span><span class="sxs-lookup"><span data-stu-id="2d5c5-105">Failover on network errors</span></span>

<span data-ttu-id="2d5c5-106">Si, por algún motivo, no se puede conectar un tronco, se probará la conexión con el mismo tronco desde otro centro de datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="2d5c5-107">Es posible que un tronco no esté conectado, por ejemplo, si se rechaza una conexión, si se sobresalte el tiempo de espera de TLS o si hay otros problemas de nivel de red.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="2d5c5-108">Por ejemplo, una conexión puede fallar si un administrador limita el acceso a la SBC solo desde direcciones IP conocidas, pero se olvida de poner las direcciones IP de todos los centros de datos de enrutamiento directo de Microsoft en la lista de control de acceso (ACL) de la SBC.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="2d5c5-109">Conmutación por error de códigos SIP específicos recibidos del controlador de borde de sesión (SBC)</span><span class="sxs-lookup"><span data-stu-id="2d5c5-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="2d5c5-110">Si el enrutamiento directo recibe códigos de error 4xx o 6xx SIP en respuesta a una invitación saliente, la llamada se considerará completada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="2d5c5-111">Saliente significa una llamada desde un cliente de Teams a la red telefónica conmutada (RTC) con el siguiente flujo de tráfico: Cliente de Teams -> Enrutamiento directo -> SBC -> Telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="2d5c5-112">La lista de códigos SIP se encuentra en RFC del Protocolo de inicio de [sesión (SIP).](https://tools.ietf.org/html/rfc3261)</span><span class="sxs-lookup"><span data-stu-id="2d5c5-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="2d5c5-113">Suponga una situación en la que un SBC respondió en una invitación entrante con el código "Tiempo de espera de la solicitud 408: El servidor no pudo producir una respuesta en un período de tiempo adecuado, por ejemplo, si no podía determinar la ubicación del usuario a tiempo.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="2d5c5-114">El cliente PUEDE repetir la solicitud sin modificarla en cualquier momento posterior".</span><span class="sxs-lookup"><span data-stu-id="2d5c5-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="2d5c5-115">Es posible que esta SBC en particular tenga dificultades para conectarse al destinatario de la llamada, quizás debido a un error de configuración de la red u otro error.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="2d5c5-116">Sin embargo, hay otro SBC en la ruta que podría llegar al destinatario.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="2d5c5-117">En el siguiente diagrama, cuando un usuario realiza una llamada a un número de teléfono, hay dos sbcs en la ruta que puede llegar a entregar esta llamada.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="2d5c5-118">Al principio, SBC1.contoso.com seleccionado para la llamada, SBC1.contoso.com no puede alcanzar una red PTSN debido a un problema de red.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="2d5c5-119">De forma predeterminada, la llamada se completará en este momento.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-119">By default, the call will be completed at this moment.</span></span> 
 
![Diagrama que muestra que SBC no puede llegar a RTC debido a un problema de red](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="2d5c5-121">Sin embargo, hay otro SBC más en la ruta que podría entregar la llamada.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="2d5c5-122">Si configura el parámetro, se `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` probará el segundo SBC SBC2.contoso.com en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="2d5c5-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Diagrama que muestra el enrutamiento a un segundo SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="2d5c5-124">Establecer el parámetro -FailoverResponseCodes y especificar los códigos le ayuda a ajustar el enrutamiento y evitar posibles problemas cuando un SBC no puede realizar una llamada debido a problemas de red u otros.</span><span class="sxs-lookup"><span data-stu-id="2d5c5-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="2d5c5-125">Valores predeterminados: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="2d5c5-125">Default values:  408, 503, 504</span></span>

