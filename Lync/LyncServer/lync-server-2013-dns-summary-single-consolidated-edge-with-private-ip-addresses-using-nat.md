---
title: Resumen de DNS-servidor perimetral consolidado único con direcciones IP privadas con NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9737824248ea9f7d11803be14f1c008cc51261
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="15fb9-102">Resumen de DNS-servidor perimetral consolidado único con direcciones IP privadas que usan NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15fb9-102">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15fb9-103">_**Última modificación del tema:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="15fb9-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="15fb9-104">Los requisitos de registro de DNS para el acceso remoto a Lync Server 2013 son bastante sencillos en comparación con los de certificados y puertos.</span><span class="sxs-lookup"><span data-stu-id="15fb9-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="15fb9-105">Además, muchos registros son opcionales, en función de cómo configure los clientes que ejecutan Lync 2013 y si habilita la Federación.</span><span class="sxs-lookup"><span data-stu-id="15fb9-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="15fb9-106">Para obtener más información sobre los requisitos de DNS de Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15fb9-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="15fb9-107">Para obtener más información sobre la configuración automática de clientes que ejecutan Lync 2013 si no se ha configurado el DNS de cerebro dividido, consulte "configuración automática sin DNS de cerebro dividido" en [determinar los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15fb9-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="15fb9-108">En la siguiente tabla se incluye un resumen de los registros DNS necesarios para admitir la topología perimetral consolidada de un solo equipo que se muestra en la figura Topología perimetral consolidada de un solo equipo.</span><span class="sxs-lookup"><span data-stu-id="15fb9-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="15fb9-109">Tenga en cuenta que algunos registros DNS solo son necesarios para la configuración automática de clientes de Lync 2013 y Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="15fb9-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="15fb9-110">Si planea usar objetos de directiva de grupo (GPO) para configurar los clientes de Lync, los registros de configuración automática asociados no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="15fb9-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="15fb9-111">IMPORTANTE: requisitos del adaptador de red del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="15fb9-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="15fb9-112">Para evitar problemas de enrutamiento, compruebe que hay al menos dos adaptadores de red en los servidores perimetrales y que la puerta de enlace predeterminada solo está configurada en el adaptador de red asociado con la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="15fb9-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="15fb9-113">Por ejemplo, como se muestra en la única topología perimetral consolidada que figura en el [perímetro consolidado único con direcciones IP privadas y NAT en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), la puerta de enlace predeterminada apunta al firewall externo (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="15fb9-113">For example, as shown in the Single Consolidated Edge Topology figure in [Single consolidated edge with private IP addresses and NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), the default gateway would point to the external firewall (10.45.16.1).</span></span>

<span data-ttu-id="15fb9-114">Puede configurar dos adaptadores de red en cada servidor perimetral de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="15fb9-114">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="15fb9-115">**Adaptador de red 1 (interfaz interna)**</span><span class="sxs-lookup"><span data-stu-id="15fb9-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="15fb9-116">Interfaz interna con 172.25.33.10 asignado.</span><span class="sxs-lookup"><span data-stu-id="15fb9-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="15fb9-117">No se define ninguna puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15fb9-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="15fb9-118">Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna a cualquier red que contenga servidores que ejecuten clientes de Lync Server 2013 o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="15fb9-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="15fb9-119">**Adaptador de red 2 (Interfaz externa)**</span><span class="sxs-lookup"><span data-stu-id="15fb9-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="15fb9-120">Se asignan tres direcciones IP privadas a este adaptador de red; por ejemplo 10.45.16.10 para el servidor perimetral de acceso, 10.45.16.20 para el servidor perimetral de conferencia web y 10.45.16.30 para el servidor perimetral AV.</span><span class="sxs-lookup"><span data-stu-id="15fb9-120">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="15fb9-p104">Es posible, aunque no se recomienda, usar una única dirección IP para las tres interfaces de servicios perimetrales. Aunque de este modo se ahorran direcciones IP, se requieren diferentes números de puerto para cada servicio. El número de puerto predeterminado es 443/TCP, que asegura que la mayoría de los firewalls remotos permitirán el tráfico. Cambiar los valores de los puertos a (por ejemplo) 5061/TCP para el servidor perimetral de acceso, 444/TCP para el servidor perimetral de conferencia web y 443/TCP para el servidor perimetral AV podría provocar problemas para usuarios remotos si están detrás de un firewall que no permite el tráfico sobre 5061/TCP y 444/TCP. Además, tres direcciones IP diferentes facilitan la resolución de problemas al poder filtrar sobre dirección IP.</span><span class="sxs-lookup"><span data-stu-id="15fb9-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="15fb9-126">La dirección IP perimetral de acceso es la principal, con la puerta de enlace predeterminada establecida en el enrutador integrado (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="15fb9-126">Access Edge IP address is primary with default gateway set to integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="15fb9-127">Las direcciones IP perimetrales de A/V y de conferencia web son secundarias.</span><span class="sxs-lookup"><span data-stu-id="15fb9-127">Web conferencing and A/V Edge IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="15fb9-128">La configuración del servidor perimetral con dos adaptadores de red es una de estas dos opciones.</span><span class="sxs-lookup"><span data-stu-id="15fb9-128">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="15fb9-129">La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="15fb9-129">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="15fb9-130">La ventaja principal de esta opción es un adaptador de red distinto por cada servicio de servidor perimetral y, potencialmente, una recopilación de datos más concisa para la solución de problemas es necesaria</span><span class="sxs-lookup"><span data-stu-id="15fb9-130">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="15fb9-131">Registros DNS necesarios para la topología perimetral consolidada con direcciones IP privadas que usan NAT (Ejemplo)</span><span class="sxs-lookup"><span data-stu-id="15fb9-131">DNS Records Required for Single Consolidated Edge with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15fb9-132">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="15fb9-132">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="15fb9-133">FQDN/Registro DNS</span><span class="sxs-lookup"><span data-stu-id="15fb9-133">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="15fb9-134">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="15fb9-134">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="15fb9-135">Se asigna a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="15fb9-135">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15fb9-136">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="15fb9-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="15fb9-137">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15fb9-137">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-138">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="15fb9-138">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="15fb9-139">Interfaz externa perimetral de acceso (Contoso). Repita según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="15fb9-139">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15fb9-140">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="15fb9-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="15fb9-141">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15fb9-141">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-142">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="15fb9-142">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="15fb9-143">Interfaz externa de servidor perimetral de conferencia web</span><span class="sxs-lookup"><span data-stu-id="15fb9-143">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15fb9-144">DNS externo</span><span class="sxs-lookup"><span data-stu-id="15fb9-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="15fb9-145">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15fb9-145">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-146">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="15fb9-146">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="15fb9-147">Interfaz externa de servidor perimetral de A/V</span><span class="sxs-lookup"><span data-stu-id="15fb9-147">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15fb9-148">DNS externo/SRV/443</span><span class="sxs-lookup"><span data-stu-id="15fb9-148">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="15fb9-149">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="15fb9-149">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-150">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15fb9-150">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-151">Interfaz perimetral de acceso externa.</span><span class="sxs-lookup"><span data-stu-id="15fb9-151">Access Edge external interface.</span></span> <span data-ttu-id="15fb9-152">Necesario para la configuración automática de los clientes de Lync 2013 y Lync 2010 para que funcionen de forma externa.</span><span class="sxs-lookup"><span data-stu-id="15fb9-152">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="15fb9-153">En caso necesario, repita la operación para los dominios SIP con usuarios de Lync habilitados.</span><span class="sxs-lookup"><span data-stu-id="15fb9-153">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15fb9-154">DNS externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="15fb9-154">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="15fb9-155">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="15fb9-155">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-156">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15fb9-156">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-157">Interfaz perimetral externa de acceso SIP. Requerida para la detección DNS automática de socios federados conocidos como “Dominio SIP permitido” (denominada federación ampliada en versiones anteriores). En caso necesario, repita la operación para los dominios SIP con usuarios de Lync habilitados</span><span class="sxs-lookup"><span data-stu-id="15fb9-157">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15fb9-158">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="15fb9-158">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="15fb9-159">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="15fb9-159">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="15fb9-160">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="15fb9-160">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="15fb9-161">Interfaz perimetral interna consolidada</span><span class="sxs-lookup"><span data-stu-id="15fb9-161">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="15fb9-162">Los registros que se enumeran en la tabla anterior se muestran con una extensión <EM>.net</EM> o <EM>.com</EM> para destacar en qué zona deben residir si no se utilizan DNS de partición de red.</span><span class="sxs-lookup"><span data-stu-id="15fb9-162">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="15fb9-163">Si se utilizan DNS de partición de red, todos los registros estarán en la misma zona <EM>.com</EM>, con la única distinción de si están en la versión de zona DNS interna o externa.</span><span class="sxs-lookup"><span data-stu-id="15fb9-163">If you are using split-brain DNS, all records would be in the same <EM>.com</EM> zone, with the only distinction being whether they are in the internal or external DNS zone version.</span></span> <span data-ttu-id="15fb9-164">Para obtener más información, consulte "DNS de horizonte dividido" en <A href="lync-server-2013-determine-dns-requirements.md">determine los requisitos de DNS para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="15fb9-164">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="15fb9-165">Registros requeridos para la federación</span><span class="sxs-lookup"><span data-stu-id="15fb9-165">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15fb9-166">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="15fb9-166">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="15fb9-167">FQDN</span><span class="sxs-lookup"><span data-stu-id="15fb9-167">FQDN</span></span></th>
<th><span data-ttu-id="15fb9-168">Dirección IP/Registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="15fb9-168">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="15fb9-169">Asignado a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="15fb9-169">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15fb9-170">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="15fb9-170">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="15fb9-171">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="15fb9-171">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-172">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15fb9-172">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-173">Interfaz externa de SIP Access Edge requerida para la recuperación automática de DNS de su federación a otros posibles socios de la federación, y es conocida como “Dominios SIP permitidos” (llamados federación mejorada en versiones anteriores). Repita según sea necesario para todos los dominios SIP con usuarios habilitados por Lync</span><span class="sxs-lookup"><span data-stu-id="15fb9-173">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="15fb9-174">Este registro SRV se necesita para la movilidad y compensación de notificación de inserción</span><span class="sxs-lookup"><span data-stu-id="15fb9-174">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="15fb9-175">Resumen DNS para el protocolo XMPP(Extensible Messaging y Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="15fb9-175">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15fb9-176">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="15fb9-176">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="15fb9-177">FQDN</span><span class="sxs-lookup"><span data-stu-id="15fb9-177">FQDN</span></span></th>
<th><span data-ttu-id="15fb9-178">Dirección IP/Registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="15fb9-178">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="15fb9-179">Asignado a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="15fb9-179">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15fb9-180">DNS/SRV/5269 externo</span><span class="sxs-lookup"><span data-stu-id="15fb9-180">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="15fb9-181">_xmpp-server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="15fb9-181">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-182">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15fb9-182">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15fb9-183">Interfaz externa de proxy XMPP en el servicio perimetral de acceso o el grupo de servidores perimetrales. Repita los pasos necesarios para todos los dominios SIP internos con los usuarios habilitados para Lync donde se permite el contacto con los contactos XMPP a través de la configuración de la Directiva de acceso externo a través de una directiva global, una directiva de sitio en la que se encuentra el usuario o la Directiva de usuario aplicada al Usuario habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="15fb9-183">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="15fb9-184">También debe configurarse un dominio XMPP permitido en la Directiva de socios federados XMPP.</span><span class="sxs-lookup"><span data-stu-id="15fb9-184">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="15fb9-185">Vea los temas en <strong>vea también</strong> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="15fb9-185">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15fb9-186">DNS externa/A</span><span class="sxs-lookup"><span data-stu-id="15fb9-186">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="15fb9-187">xmpp.contoso.com (por ejemplo)</span><span class="sxs-lookup"><span data-stu-id="15fb9-187">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="15fb9-188">Dirección IP del servicio perimetral de acceso en el servidor perimetral o el grupo de servidores perimetrales que hospedan el proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="15fb9-188">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="15fb9-189">Señala el servicio perimetral de acceso o el grupo de servidores perimetrales que hospeda el servicio de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="15fb9-189">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="15fb9-190">Generalmente, el registro SRV que crea llevará a este registro de host (A o AAAA)</span><span class="sxs-lookup"><span data-stu-id="15fb9-190">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

