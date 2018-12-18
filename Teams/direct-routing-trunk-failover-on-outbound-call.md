---
title: Conmutación por error de tronco en las llamadas salientes
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lea este tema para obtener información sobre cómo controlar las conmutaciones por error de tronco en las llamadas salientes desde los equipos para el controlador de borde de sesión (SBC).
ms.openlocfilehash: 620230ca3be07bb54386f54a983539716d07b2e9
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297812"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="3f0b2-103">Conmutación por error de tronco en las llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="3f0b2-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="3f0b2-104">En este tema se describe cómo evitar tronco conmutaciones por error en las llamadas salientes--desde los equipos para el controlador de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="3f0b2-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="3f0b2-105">Conmutación por error en los errores de red</span><span class="sxs-lookup"><span data-stu-id="3f0b2-105">Failover on network errors</span></span>

<span data-ttu-id="3f0b2-106">Si no se puede conectar un tronco por cualquier motivo, se intentará la conexión con el mismo tronco desde un Microsoft Datacenter diferentes.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="3f0b2-107">Un tronco que no esté conectado, por ejemplo, si se ha rechazado una conexión si no hay un tiempo de espera TLS, o si hay otros problemas de nivel de red.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="3f0b2-108">Por ejemplo, una conexión puede producirse un error si un administrador limita el acceso a la SBC únicamente desde las direcciones IP conocidas, pero se olvida poner las direcciones IP de todos los centros de datos enrutamiento directo de Microsoft en la lista de Control de acceso (ACL) de la SBC.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="3f0b2-109">Conmutación por error de códigos específicos de SIP recibidos desde el controlador de borde de sesión (SBC)</span><span class="sxs-lookup"><span data-stu-id="3f0b2-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="3f0b2-110">Si el enrutamiento directo recibe los códigos de error 4xx o 6xx SIP en respuesta a una invitación saliente, la llamada se considera completada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="3f0b2-111">Saliente significa una llamada desde un cliente de los equipos a la pública teléfono red conmutada (RTC) con el siguiente flujo de tráfico: los equipos cliente -> enrutamiento directo -> SBC -> red de telefonía.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="3f0b2-112">La lista de códigos de SIP puede encontrarse en el [Protocolo de inicio de sesión (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="3f0b2-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="3f0b2-113">Se supone una situación donde un SBC respondió una invitación entrante con el código "408 tiempo de espera de solicitud: el servidor no puede crear una respuesta dentro de una cantidad adecuada de tiempo, por ejemplo, si no puede determinar la ubicación del usuario en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="3f0b2-114">El cliente puede repetir la solicitud sin modificaciones en cualquier momento."</span><span class="sxs-lookup"><span data-stu-id="3f0b2-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="3f0b2-115">Es posible que tenga las dificultades de conexión con el destinatario de la llamada--quizás debido a un error de configuración de red o a otro error este SBC determinada.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="3f0b2-116">Sin embargo, hay una SBC más en la ruta que es posible que pueda ponerse en contacto con el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="3f0b2-117">En el diagrama siguiente, cuando un usuario realiza una llamada a un número de teléfono, hay dos SBCs en la ruta que puede suministrar esta llamada.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="3f0b2-118">Inicialmente, se selecciona SBC1.contoso.com para la llamada, pero SBC1.contoso.com no puede ponerse en contacto con una red PTSN debido a un problema de red.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="3f0b2-119">De forma predeterminada, la llamada se completará en este momento.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-119">By default, the call will be completed at this moment.</span></span> 
 
![Muestra SBC no puede alcanzar RTC debido a problemas de red](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="3f0b2-121">Pero hay una SBC más en la ruta que potencialmente puede ofrecer la llamada.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="3f0b2-122">Si configura el parámetro Set-CSOnlinePSTNGateway-Identity sbc1.contoso.com - ReinviteResponceCode "408", será el segundo SBC probado--SBC2.contoso.com en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="3f0b2-122">If you configure the parameter Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -ReinviteResponceCode "408", the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Muestra el enrutamiento al segundo SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="3f0b2-124">Si se establece el parámetro - FailoverResponceCodes y especificando los códigos de le ayuda a no pasa nada, ajuste el enrutamiento y evitar posibles problemas cuando un SBC no puede realizar una llamada debido a la red u otros problemas.</span><span class="sxs-lookup"><span data-stu-id="3f0b2-124">Setting the parameter -FailoverResponceCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="3f0b2-125">Valores predeterminados: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="3f0b2-125">Default values:  408, 503, 504</span></span>

