---
title: 'Resumen de puertos: SIP, Federación XMPP y mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae19fb2477f61c0e408ebad3a8abf97fb75b9c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="f9beb-102">Resumen de puertos: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9beb-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9beb-103">_**Última modificación del tema:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="f9beb-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="f9beb-104">Los requisitos de puertos, protocolos y firewalls para la Federación con Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server son similares a los del servidor perimetral implementado.</span><span class="sxs-lookup"><span data-stu-id="f9beb-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="f9beb-105">Los clientes inician la comunicación con el servicio perimetral de acceso a través de TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="f9beb-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="f9beb-106">Sin embargo, los socios federados iniciarán las comunicaciones con el servicio perimetral de acceso a través de MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="f9beb-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="f9beb-107">Para configurar el firewall para los puertos y protocolos necesarios para admitir la conectividad de mensajería instantánea pública, primero tenga en cuenta que los SIP/MTLS/TCP 5061 son bidireccionales para tener en cuenta la capacidad de los contactos en el proveedor de mi pública para ponerse en contacto con los clientes de Lync o para que Lync pueda comunicarse con los contactos públicos de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="f9beb-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="f9beb-108">Windows Live Messenger puede participar en comunicaciones de audio y vídeo con clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="f9beb-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="f9beb-109">Esto cuenta con una configuración de protocolo y un puerto de Firewall muy similar que normalmente tendría en el firewall para admitir clientes de Lync como usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="f9beb-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f9beb-110">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="f9beb-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f9beb-111">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la licencia de acceso de cliente (CAL) de Lync.</span><span class="sxs-lookup"><span data-stu-id="f9beb-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="f9beb-112">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="f9beb-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="f9beb-113">La Federación con los contactos de los clientes de Messenger terminará oficialmente el 15 de marzo de 2013, excepto en el caso de China continental.</span><span class="sxs-lookup"><span data-stu-id="f9beb-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="f9beb-114">Skype se convertirá en el cliente de Federación para los usuarios federados que antes usaban Messenger.</span><span class="sxs-lookup"><span data-stu-id="f9beb-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="f9beb-115">Los puertos y protocolos definidos para el proxy protocolo de presencia y mensajería extensible (XMPP) implementado en el servidor perimetral permiten las comunicaciones del socio XMPP federado hasta el servidor perimetral, y también permiten la comunicación desde el servidor perimetral al XMPP socio federado.</span><span class="sxs-lookup"><span data-stu-id="f9beb-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="f9beb-116">Una regla también se define en el Firewall de orientación interna desde el servidor front-end o el grupo front-end hasta el servidor perimetral o el grupo Edge.</span><span class="sxs-lookup"><span data-stu-id="f9beb-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="f9beb-117">Resumen del firewall: Federación SIP</span><span class="sxs-lookup"><span data-stu-id="f9beb-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9beb-118">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="f9beb-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f9beb-119">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="f9beb-119">Source IP address</span></span></th>
<th><span data-ttu-id="f9beb-120">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="f9beb-120">Destination IP address</span></span></th>
<th><span data-ttu-id="f9beb-121">Notas</span><span class="sxs-lookup"><span data-stu-id="f9beb-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9beb-122">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f9beb-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f9beb-123">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="f9beb-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f9beb-124">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="f9beb-124">Any</span></span></p></td>
<td><p><span data-ttu-id="f9beb-125">Para conectividad de mensajería instantánea pública y federada con SIP</span><span class="sxs-lookup"><span data-stu-id="f9beb-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="f9beb-126">Resumen del firewall: conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="f9beb-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9beb-127">Función/protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="f9beb-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f9beb-128">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="f9beb-128">Source IP address</span></span></th>
<th><span data-ttu-id="f9beb-129">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="f9beb-129">Destination IP address</span></span></th>
<th><span data-ttu-id="f9beb-130">Notas</span><span class="sxs-lookup"><span data-stu-id="f9beb-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9beb-131">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f9beb-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f9beb-132">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="f9beb-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="f9beb-133">Interfaz de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="f9beb-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="f9beb-134">Para la conectividad de mensajería instantánea pública y federada que usan SIP.</span><span class="sxs-lookup"><span data-stu-id="f9beb-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9beb-135">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f9beb-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f9beb-136">Interfaz de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="f9beb-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="f9beb-137">Partners de conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="f9beb-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="f9beb-138">Para la conectividad de mensajería instantánea pública y federada que usan SIP.</span><span class="sxs-lookup"><span data-stu-id="f9beb-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9beb-139">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f9beb-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f9beb-140">Clientes</span><span class="sxs-lookup"><span data-stu-id="f9beb-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="f9beb-141">Interfaz de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="f9beb-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="f9beb-142">Tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="f9beb-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9beb-143">A/V/RTP/TCP/50000-59.999 SESIONES</span><span class="sxs-lookup"><span data-stu-id="f9beb-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f9beb-144">Interfaz de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="f9beb-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="f9beb-145">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="f9beb-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="f9beb-146">Se usa para sesiones de A/V con Windows Live Messenger si está configurada la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="f9beb-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9beb-147">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f9beb-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f9beb-148">Interfaz de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="f9beb-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="f9beb-149">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="f9beb-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="f9beb-150">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="f9beb-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9beb-151">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f9beb-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f9beb-152">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="f9beb-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="f9beb-153">Interfaz de acceso al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="f9beb-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="f9beb-154">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="f9beb-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="f9beb-155">Resumen de Firewall: Protocolo de presencia y mensajería extensible (XMPP)</span><span class="sxs-lookup"><span data-stu-id="f9beb-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9beb-156">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="f9beb-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f9beb-157">Origen (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="f9beb-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="f9beb-158">Destino (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="f9beb-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="f9beb-159">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9beb-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9beb-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="f9beb-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="f9beb-161">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="f9beb-161">Any</span></span></p></td>
<td><p><span data-ttu-id="f9beb-162">Dirección IP de la interfaz de servicio perimetral de Access</span><span class="sxs-lookup"><span data-stu-id="f9beb-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="f9beb-163">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="f9beb-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="f9beb-164">Permite la comunicación con el proxy XMPP del servidor perimetral de socios de XMPP</span><span class="sxs-lookup"><span data-stu-id="f9beb-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9beb-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="f9beb-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="f9beb-166">Dirección IP de la interfaz de servicio perimetral de Access</span><span class="sxs-lookup"><span data-stu-id="f9beb-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="f9beb-167">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="f9beb-167">Any</span></span></p></td>
<td><p><span data-ttu-id="f9beb-168">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="f9beb-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="f9beb-169">Permite la comunicación desde el proxy XMPP del servidor perimetral a socios XMPP de Federación</span><span class="sxs-lookup"><span data-stu-id="f9beb-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9beb-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="f9beb-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="f9beb-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="f9beb-171">Any</span></span></p></td>
<td><p><span data-ttu-id="f9beb-172">IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="f9beb-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="f9beb-173">Tráfico de XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo front-end al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="f9beb-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9beb-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9beb-174">See Also</span></span>


[<span data-ttu-id="f9beb-175">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9beb-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="f9beb-176">Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9beb-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="f9beb-177">Administrar socios federados XMPP para su organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9beb-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

