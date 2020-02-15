---
title: Resumen de Puerto-SIP, Federación XMPP y mensajería instantánea pública
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
ms.openlocfilehash: 2512b49f9e0bcdc092354a5f43cb234c7e4d5445
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="3ace6-102">Resumen de Puerto-SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ace6-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ace6-103">_**Última modificación del tema:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="3ace6-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="3ace6-104">Los requisitos de puerto, protocolo y firewall para la Federación con Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server son similares a los del servidor perimetral implementado.</span><span class="sxs-lookup"><span data-stu-id="3ace6-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="3ace6-105">Los clientes inician la comunicación con el servicio perimetral de acceso a través de TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="3ace6-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="3ace6-106">No obstante, los socios federados iniciarán comunicaciones con el servicio perimetral de acceso a través de MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="3ace6-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="3ace6-107">Para configurar el firewall para los puertos y protocolos necesarios para la conectividad de mensajería instantánea pública, en primer lugar, tenga en cuenta que SIP/MTLS/TCP 5061 es bidireccional para tener en cuenta la capacidad de los contactos en el proveedor de mi pública para ponerse en contacto con clientes de Lync o Lync para ponerse en contacto con los contactos de mi pública.</span><span class="sxs-lookup"><span data-stu-id="3ace6-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="3ace6-108">Windows Live Messenger puede participar en las comunicaciones de audio y vídeo con los clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="3ace6-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="3ace6-109">Esto cuenta con una configuración de protocolos y puertos de Firewall muy similares que normalmente tendría en el firewall para admitir clientes de Lync como usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="3ace6-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3ace6-110">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="3ace6-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="3ace6-111">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la licencia de acceso de cliente (CAL) de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="3ace6-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="3ace6-112">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="3ace6-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="3ace6-113">La Federación con los contactos del cliente de Messenger finalizará oficialmente el 15 de marzo de 2013, excepto para China continental.</span><span class="sxs-lookup"><span data-stu-id="3ace6-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="3ace6-114">Skype se convertirá en cliente de Federación para los usuarios federados que usaron Messenger anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3ace6-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="3ace6-115">Los puertos y protocolos definidos para el proxy de protocolo extensible de mensajería y presencia (XMPP) implementado en el servidor perimetral permiten las comunicaciones desde el socio federado de XMPP hacia el servidor perimetral y también permiten la comunicación desde el servidor perimetral al XMPP socio federado.</span><span class="sxs-lookup"><span data-stu-id="3ace6-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="3ace6-116">Una regla también se define en el Firewall orientado internamente desde el servidor front-end o el grupo de servidores front-end hasta el servidor perimetral o el grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="3ace6-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="3ace6-117">Resumen del servidor de seguridad-Federación SIP</span><span class="sxs-lookup"><span data-stu-id="3ace6-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ace6-118">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="3ace6-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3ace6-119">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="3ace6-119">Source IP address</span></span></th>
<th><span data-ttu-id="3ace6-120">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="3ace6-120">Destination IP address</span></span></th>
<th><span data-ttu-id="3ace6-121">Notas</span><span class="sxs-lookup"><span data-stu-id="3ace6-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ace6-122">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3ace6-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3ace6-123">Dirección IP pública del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="3ace6-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3ace6-124">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ace6-124">Any</span></span></p></td>
<td><p><span data-ttu-id="3ace6-125">Para la conectividad de MI pública y federada mediante SIP</span><span class="sxs-lookup"><span data-stu-id="3ace6-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="3ace6-126">Resumen de firewall: Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="3ace6-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ace6-127">Rol/Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="3ace6-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3ace6-128">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="3ace6-128">Source IP address</span></span></th>
<th><span data-ttu-id="3ace6-129">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="3ace6-129">Destination IP address</span></span></th>
<th><span data-ttu-id="3ace6-130">Notas</span><span class="sxs-lookup"><span data-stu-id="3ace6-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ace6-131">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3ace6-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3ace6-132">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="3ace6-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3ace6-133">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ace6-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="3ace6-134">Para la conectividad de mensajería instantánea pública y federada que usan SIP.</span><span class="sxs-lookup"><span data-stu-id="3ace6-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ace6-135">Acceso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3ace6-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3ace6-136">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ace6-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="3ace6-137">Socios de conectividad de MI pública</span><span class="sxs-lookup"><span data-stu-id="3ace6-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3ace6-138">Para la conectividad de mensajería instantánea pública y federada que usan SIP.</span><span class="sxs-lookup"><span data-stu-id="3ace6-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ace6-139">Acceso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3ace6-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3ace6-140">Clientes</span><span class="sxs-lookup"><span data-stu-id="3ace6-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="3ace6-141">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ace6-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="3ace6-142">Tráfico SIP de cliente a servidor para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="3ace6-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ace6-143">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3ace6-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3ace6-144">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ace6-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="3ace6-145">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3ace6-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3ace6-146">Usado para sesiones de A/V con Windows Live Messenger si se ha configurado la conectividad de MI.</span><span class="sxs-lookup"><span data-stu-id="3ace6-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ace6-147">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3ace6-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3ace6-148">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ace6-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="3ace6-149">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3ace6-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3ace6-150">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="3ace6-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ace6-151">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3ace6-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3ace6-152">Clientes de Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3ace6-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3ace6-153">Interfaz de acceso del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ace6-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="3ace6-154">Necesario para la conectividad de mensajería instantánea pública con Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="3ace6-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="3ace6-155">Resumen de firewall, protocolo extensible de mensajería y presencia (XMPP)</span><span class="sxs-lookup"><span data-stu-id="3ace6-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ace6-156">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="3ace6-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3ace6-157">Origen (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="3ace6-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="3ace6-158">Destino (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="3ace6-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="3ace6-159">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ace6-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ace6-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3ace6-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3ace6-161">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ace6-161">Any</span></span></p></td>
<td><p><span data-ttu-id="3ace6-162">Dirección IP de la interfaz del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="3ace6-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3ace6-163">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="3ace6-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3ace6-164">Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="3ace6-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ace6-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3ace6-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3ace6-166">Dirección IP de la interfaz del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="3ace6-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3ace6-167">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ace6-167">Any</span></span></p></td>
<td><p><span data-ttu-id="3ace6-168">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="3ace6-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3ace6-169">Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="3ace6-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ace6-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="3ace6-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="3ace6-171">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="3ace6-171">Any</span></span></p></td>
<td><p><span data-ttu-id="3ace6-172">IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="3ace6-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="3ace6-173">Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="3ace6-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ace6-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ace6-174">See Also</span></span>


[<span data-ttu-id="3ace6-175">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ace6-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="3ace6-176">Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ace6-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="3ace6-177">Administrar socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ace6-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

