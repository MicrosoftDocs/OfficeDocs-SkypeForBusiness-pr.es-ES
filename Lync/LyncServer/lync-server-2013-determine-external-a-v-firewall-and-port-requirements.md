---
title: 'Lync Server 2013: determinar los requisitos de los puertos y el Firewall de A/V externos'
description: 'Lync Server 2013: determinar los requisitos de los puertos y el Firewall de A/V externos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550936"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="811aa-103">Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="811aa-103">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="811aa-104">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="811aa-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="811aa-105">La comunicación de audio y vídeo (A/V) puede ser compleja.</span><span class="sxs-lookup"><span data-stu-id="811aa-105">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="811aa-106">Debido a la naturaleza de los protocolos que se usan en A/V y cómo los clientes y servidores usan los protocolos, se garantiza una sección especial para explicar las diferencias entre las versiones de cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="811aa-106">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="811aa-107">Use la siguiente tabla de puertos y firewall de a/V para determinar los requisitos de firewall y los puertos que se abrirán.</span><span class="sxs-lookup"><span data-stu-id="811aa-107">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="811aa-108">A continuación, revise la terminología de traducción de direcciones de red (NAT) porque NAT puede implementarse de formas muy distintas.</span><span class="sxs-lookup"><span data-stu-id="811aa-108">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="811aa-109">Para obtener un ejemplo detallado de la configuración del puerto del firewall, consulte las arquitecturas de referencia en [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="811aa-109">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="811aa-110">Uso de protocolos generales para UDP y TCP en el tráfico de audio, vídeo y multimedia</span><span class="sxs-lookup"><span data-stu-id="811aa-110">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="811aa-111">Transporte de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="811aa-111">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="811aa-112">Uso</span><span class="sxs-lookup"><span data-stu-id="811aa-112">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="811aa-113">UDP</span><span class="sxs-lookup"><span data-stu-id="811aa-113">UDP</span></span></p></td>
<td><p><span data-ttu-id="811aa-114">Protocolo de capa de transporte preferido para audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="811aa-114">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="811aa-115">TCP</span><span class="sxs-lookup"><span data-stu-id="811aa-115">TCP</span></span></p></td>
<td><p><span data-ttu-id="811aa-116">Protocolo de capa de transporte de reserva para audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="811aa-116">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="811aa-117">Protocolo de capa de transporte necesario para compartir aplicaciones con Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="811aa-117">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="811aa-118">Protocolo de capa de transporte necesario para la transferencia de archivos a Lync Server 2010 y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="811aa-118">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="811aa-119">Requisitos de puerto de firewall A/V para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="811aa-119">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="811aa-120">Los requisitos de puerto de Firewall para las interfaces SIP y de conferencia externas (y internas) son coherentes, independientemente de la versión de su cliente o de la versión del asociado de Federación.</span><span class="sxs-lookup"><span data-stu-id="811aa-120">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="811aa-121">No sucede lo mismo con la interfaz perimetral externa de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="811aa-121">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="811aa-122">Para la Federación con Office Communications Server 2007, el servicio perimetral A/V necesita que las reglas del firewall externo permitan que el tráfico RTP/TCP y RTP/UDP del intervalo de puertos de 50.000 a 59.999 fluya en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="811aa-122">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="811aa-123">En la tabla anterior se supone que Lync Server 2013 es el socio de Federación principal y que se ha configurado para comunicarse con uno de los otros tipos de asociados de Federación que aparecen en la lista.</span><span class="sxs-lookup"><span data-stu-id="811aa-123">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="811aa-124">La configuración del intervalo de puertos de audio y vídeo de 50000-59.999 debe tener en cuenta que el intervalo de puertos contendrá los puertos de origen para las comunicaciones con los socios de Federación.</span><span class="sxs-lookup"><span data-stu-id="811aa-124">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="811aa-125">En detalle, tenga en cuenta que se inicia una comunicación desde un socio de Federación.</span><span class="sxs-lookup"><span data-stu-id="811aa-125">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="811aa-126">La comunicación desde los puertos del servicio perimetral A/V del intervalo de 50000-59.999 se conectará al puerto TCP 443 esperado del servicio perimetral A/V del asociado.</span><span class="sxs-lookup"><span data-stu-id="811aa-126">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="811aa-127">Por el contrario, el tráfico entrante a su puerto del servicio perimetral a/V TCP 443 tendrá un puerto de origen en el rango de 50000 59.999.</span><span class="sxs-lookup"><span data-stu-id="811aa-127">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="811aa-128">Los diferentes firewalls y directivas para la administración de firewalls pueden requerir que solo se configuren reglas de destino, o bien es posible que necesite configurar tanto el origen como el destino.</span><span class="sxs-lookup"><span data-stu-id="811aa-128">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="811aa-129">Si sus requisitos son solo para puertos de destino, los requisitos de audio y vídeo son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="811aa-129">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="811aa-130">IP de origen</span><span class="sxs-lookup"><span data-stu-id="811aa-130">Source IP</span></span></th>
<th><span data-ttu-id="811aa-131">IP de destino</span><span class="sxs-lookup"><span data-stu-id="811aa-131">Destination IP</span></span></th>
<th><span data-ttu-id="811aa-132">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="811aa-132">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="811aa-133">Interfaz del servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="811aa-133">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="811aa-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="811aa-134">Any</span></span></p></td>
<td><p><span data-ttu-id="811aa-135">TCP 443</span><span class="sxs-lookup"><span data-stu-id="811aa-135">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="811aa-136">Interfaz del servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="811aa-136">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="811aa-137">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="811aa-137">Any</span></span></p></td>
<td><p><span data-ttu-id="811aa-138">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="811aa-138">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="811aa-139">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="811aa-139">Any</span></span></p></td>
<td><p><span data-ttu-id="811aa-140">Interfaz del servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="811aa-140">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="811aa-141">TCP 443</span><span class="sxs-lookup"><span data-stu-id="811aa-141">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="811aa-142">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="811aa-142">Any</span></span></p></td>
<td><p><span data-ttu-id="811aa-143">Interfaz del servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="811aa-143">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="811aa-144">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="811aa-144">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="811aa-145">Si las directivas requieren definiciones de reglas de Firewall de entrada y de salida, los requisitos de audio y vídeo son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="811aa-145">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="811aa-146">IP de origen</span><span class="sxs-lookup"><span data-stu-id="811aa-146">Source IP</span></span></th>
<th><span data-ttu-id="811aa-147">IP de destino</span><span class="sxs-lookup"><span data-stu-id="811aa-147">Destination IP</span></span></th>
<th><span data-ttu-id="811aa-148">Puerto de origen</span><span class="sxs-lookup"><span data-stu-id="811aa-148">Source Port</span></span></th>
<th><span data-ttu-id="811aa-149">Puerto de destino</span><span class="sxs-lookup"><span data-stu-id="811aa-149">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="811aa-150">Interfaz del servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="811aa-150">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="811aa-151">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="811aa-151">Any</span></span></p></td>
<td><p><span data-ttu-id="811aa-152">TCP 50000-59.999</span><span class="sxs-lookup"><span data-stu-id="811aa-152">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="811aa-153">TCP 443</span><span class="sxs-lookup"><span data-stu-id="811aa-153">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="811aa-154">Interfaz del servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="811aa-154">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="811aa-155">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="811aa-155">Any</span></span></p></td>
<td><p><span data-ttu-id="811aa-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="811aa-156">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="811aa-157">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="811aa-157">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="811aa-158">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="811aa-158">Any</span></span></p></td>
<td><p><span data-ttu-id="811aa-159">Interfaz del servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="811aa-159">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="811aa-160">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="811aa-160">Any</span></span></p></td>
<td><p><span data-ttu-id="811aa-161">TCP 443</span><span class="sxs-lookup"><span data-stu-id="811aa-161">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="811aa-162">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="811aa-162">Any</span></span></p></td>
<td><p><span data-ttu-id="811aa-163">Interfaz del servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="811aa-163">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="811aa-164">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="811aa-164">Any</span></span></p></td>
<td><p><span data-ttu-id="811aa-165">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="811aa-165">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="811aa-166">Microsoft Office Communications Server 2007 requiere una configuración ligeramente distinta.</span><span class="sxs-lookup"><span data-stu-id="811aa-166">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="811aa-167">El intervalo de puertos TCP y UDP de 50000-59.999 debe estar abierto entrante y saliente.</span><span class="sxs-lookup"><span data-stu-id="811aa-167">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="811aa-168">Este requisito es solo para Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="811aa-168">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="811aa-169">Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013 solo requieren el intervalo TCP 50000-59.999 abierto saliente.</span><span class="sxs-lookup"><span data-stu-id="811aa-169">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="811aa-170">Requisitos de NAT para el servicio perimetral</span><span class="sxs-lookup"><span data-stu-id="811aa-170">NAT requirements for the Edge service</span></span>

<span data-ttu-id="811aa-171">Si elige configurar direcciones IP privadas no enrutables para el servicio perimetral, se aplicarán los siguientes requisitos de NAT:</span><span class="sxs-lookup"><span data-stu-id="811aa-171">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="811aa-172">NAT solo se puede usar con el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="811aa-172">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="811aa-173">NAT no es compatible con una topología perimetral de equilibrio de carga de hardware (HLB).</span><span class="sxs-lookup"><span data-stu-id="811aa-173">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="811aa-174">NAT solo se puede usar en la interfaz perimetral externa.</span><span class="sxs-lookup"><span data-stu-id="811aa-174">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="811aa-175">NAT no es compatible con la interfaz perimetral interna.</span><span class="sxs-lookup"><span data-stu-id="811aa-175">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="811aa-176">La NAT debe ser simétrica para el tráfico entrante y saliente.</span><span class="sxs-lookup"><span data-stu-id="811aa-176">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="811aa-177">Para el tráfico de Internet, NAT debe cambiar la dirección IP de destino de la dirección IP pública habilitada para NAT del servicio perimetral a/V a su dirección IP externa.</span><span class="sxs-lookup"><span data-stu-id="811aa-177">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="811aa-178">La dirección IP de origen debe permanecer intacta, de modo que el servicio perimetral A/V pueda encontrar la ruta de medios óptima.</span><span class="sxs-lookup"><span data-stu-id="811aa-178">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="811aa-179">Por ejemplo, en la dirección de entrada en la figura siguiente, la dirección IP pública 131.107.155.30 se cambió a la dirección IP externa (privada) 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="811aa-179">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="811aa-180">La dirección IP de origen permanece inalterada.</span><span class="sxs-lookup"><span data-stu-id="811aa-180">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="811aa-181">Para el tráfico del servicio perimetral a/V a Internet, NAT debe cambiar la dirección IP de origen de la dirección IP externa del servicio perimetral a/V a la dirección IP pública habilitada para NAT.</span><span class="sxs-lookup"><span data-stu-id="811aa-181">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="811aa-182">Por ejemplo, en la dirección de salida de la figura siguiente, la dirección IP externa (privada) 10.45.16.10 se cambió a la dirección IP pública 131.107.155.30.</span><span class="sxs-lookup"><span data-stu-id="811aa-182">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="811aa-183">**En la siguiente figura se muestra la forma en que NAT cambia la dirección IP de destino para el tráfico entrante y la dirección IP de origen para el tráfico saliente.**</span><span class="sxs-lookup"><span data-stu-id="811aa-183">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="811aa-184">![Cambio de direcciones IP de destino/origen](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Cambio de direcciones IP de destino/origen")</span><span class="sxs-lookup"><span data-stu-id="811aa-184">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="811aa-185">Los puntos clave son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="811aa-185">The key points are:</span></span>

  - <span data-ttu-id="811aa-186">Tráfico entrante al servidor que ejecuta el servicio perimetral A/V, la dirección IP de origen no cambia, pero la dirección IP de destino cambia de 131.107.155.30 a la dirección IP traducida de 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="811aa-186">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="811aa-187">El tráfico saliente del servidor que ejecuta el servicio perimetral a/V a la estación de trabajo, la dirección IP de origen cambia desde la dirección IP pública del servidor a la dirección IP pública del servidor que ejecuta el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="811aa-187">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="811aa-188">La IP de destino sigue siendo la dirección IP pública de la estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="811aa-188">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="811aa-189">Una vez que el paquete deja el primer dispositivo NAT saliente, la regla del dispositivo NAT cambia la dirección IP de origen del servidor que ejecuta la dirección IP de la interfaz externa del servicio perimetral A/V (10.45.16.10) a su dirección IP pública (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="811aa-189">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

