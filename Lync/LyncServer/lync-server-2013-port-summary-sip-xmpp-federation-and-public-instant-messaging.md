---
title: Resumen de Puerto-SIP, Federación XMPP y mensajería instantánea pública
description: Resumen de Puerto-SIP, Federación XMPP y mensajería instantánea pública.
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
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566365"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="ee2bb-103">Resumen de Puerto-SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2bb-103">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee2bb-104">_**Última modificación del tema:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="ee2bb-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="ee2bb-105">Los requisitos de puerto, protocolo y firewall para la Federación con Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server son similares a los del servidor perimetral implementado.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-105">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="ee2bb-106">Los clientes inician la comunicación con el servicio perimetral de acceso a través de TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-106">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="ee2bb-107">No obstante, los socios federados iniciarán comunicaciones con el servicio perimetral de acceso a través de MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-107">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="ee2bb-108">Para configurar el firewall para los puertos y protocolos necesarios para la conectividad de mensajería instantánea pública, en primer lugar, tenga en cuenta que SIP/MTLS/TCP 5061 es bidireccional para tener en cuenta la capacidad de los contactos en el proveedor de mi pública para ponerse en contacto con clientes de Lync o Lync para ponerse en contacto con los contactos de mi pública.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-108">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="ee2bb-109">Windows Live Messenger puede participar en las comunicaciones de audio y vídeo con los clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-109">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="ee2bb-110">Esto cuenta con una configuración de protocolos y puertos de Firewall muy similares que normalmente tendría en el firewall para admitir clientes de Lync como usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-110">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="ee2bb-111">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-111">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="ee2bb-112">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la licencia de acceso de cliente (CAL) de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-112">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="ee2bb-113">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-113">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="ee2bb-114">La Federación con los contactos del cliente de Messenger finalizará oficialmente el 15 de marzo de 2013, excepto para China continental.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-114">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="ee2bb-115">Skype se convertirá en cliente de Federación para los usuarios federados que usaron Messenger anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-115">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="ee2bb-116">Los puertos y protocolos definidos para el proxy de protocolo extensible de mensajería y presencia (XMPP) implementado en el servidor perimetral permiten las comunicaciones desde el socio federado de XMPP hasta el servidor perimetral y también permiten la comunicación desde el servidor perimetral al socio federado de XMPP.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-116">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="ee2bb-117">Una regla también se define en el Firewall orientado internamente desde el servidor front-end o el grupo de servidores front-end hasta el servidor perimetral o el grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-117">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="ee2bb-118">Resumen del servidor de seguridad-Federación SIP</span><span class="sxs-lookup"><span data-stu-id="ee2bb-118">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee2bb-119">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="ee2bb-119">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ee2bb-120">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="ee2bb-120">Source IP address</span></span></th>
<th><span data-ttu-id="ee2bb-121">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="ee2bb-121">Destination IP address</span></span></th>
<th><span data-ttu-id="ee2bb-122">Notas</span><span class="sxs-lookup"><span data-stu-id="ee2bb-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee2bb-123">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ee2bb-123">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-124">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="ee2bb-124">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-125">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ee2bb-125">Any</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-126">Para la conectividad de MI pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="ee2bb-126">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="ee2bb-127">Resumen de firewall: Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="ee2bb-127">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee2bb-128">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="ee2bb-128">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ee2bb-129">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="ee2bb-129">Source IP address</span></span></th>
<th><span data-ttu-id="ee2bb-130">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="ee2bb-130">Destination IP address</span></span></th>
<th><span data-ttu-id="ee2bb-131">Notas</span><span class="sxs-lookup"><span data-stu-id="ee2bb-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee2bb-132">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ee2bb-132">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-133">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="ee2bb-133">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-134">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ee2bb-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-135">Para la conectividad de mensajería instantánea pública y federada que usan SIP.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-135">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee2bb-136">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ee2bb-136">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-137">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ee2bb-137">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-138">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="ee2bb-138">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-139">Para la conectividad de mensajería instantánea pública y federada que usan SIP.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-139">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee2bb-140">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ee2bb-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-141">Clientes</span><span class="sxs-lookup"><span data-stu-id="ee2bb-141">Clients</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-142">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ee2bb-142">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-143">Tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-143">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee2bb-144">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ee2bb-144">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-145">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ee2bb-145">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-146">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ee2bb-146">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-147">Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-147">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee2bb-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ee2bb-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-149">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ee2bb-149">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-150">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ee2bb-150">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-151">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-151">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee2bb-152">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ee2bb-152">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-153">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ee2bb-153">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-154">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ee2bb-154">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-155">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-155">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="ee2bb-156">Resumen de firewall, protocolo extensible de mensajería y presencia (XMPP)</span><span class="sxs-lookup"><span data-stu-id="ee2bb-156">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee2bb-157">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="ee2bb-157">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ee2bb-158">Origen (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="ee2bb-158">Source (IP address)</span></span></th>
<th><span data-ttu-id="ee2bb-159">Destino (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="ee2bb-159">Destination (IP address)</span></span></th>
<th><span data-ttu-id="ee2bb-160">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee2bb-160">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee2bb-161">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ee2bb-161">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-162">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ee2bb-162">Any</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-163">Dirección IP de la interfaz del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="ee2bb-163">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-164">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-164">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ee2bb-165">Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-165">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee2bb-166">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ee2bb-166">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-167">Dirección IP de la interfaz del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="ee2bb-167">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-168">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ee2bb-168">Any</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-169">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-169">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ee2bb-170">Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="ee2bb-170">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee2bb-171">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="ee2bb-171">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-172">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="ee2bb-172">Any</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-173">IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="ee2bb-173">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="ee2bb-174">Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ee2bb-174">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ee2bb-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee2bb-175">See Also</span></span>


[<span data-ttu-id="ee2bb-176">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2bb-176">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="ee2bb-177">Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2bb-177">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="ee2bb-178">Administrar socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee2bb-178">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

