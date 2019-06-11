---
title: Resumen DNS - Servidor perimetral consolidado simple con direcciones IP públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50aae14309e55919eb3f65560cd7cd0e7f1b1283
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="bff58-102">Resumen DNS - Servidor perimetral consolidado simple con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bff58-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bff58-103">_**Última modificación del tema:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="bff58-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="bff58-104">Los requisitos de registro DNS para el acceso remoto a Lync Server 2013 son bastante sencillos en comparación con los de certificados y puertos.</span><span class="sxs-lookup"><span data-stu-id="bff58-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="bff58-105">Además, muchos registros son opcionales, en función de cómo configure los clientes que ejecutan Lync 2013 y si habilita la Federación.</span><span class="sxs-lookup"><span data-stu-id="bff58-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="bff58-106">Para obtener más información sobre los requisitos de DNS de Lync 2013, consulte [determinar los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bff58-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="bff58-107">Para obtener más información sobre la configuración automática de clientes que ejecutan Lync 2013 si no se ha configurado el servidor DNS de horizonte dividido, consulte "configuración automática sin DNS de horizonte dividido" en [determinar los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bff58-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="bff58-108">La tabla siguiente contiene un resumen de los registros DNS necesarios para admitir la única topología de arista consolidada que se muestra en la ilustración de una única topología de borde consolidado.</span><span class="sxs-lookup"><span data-stu-id="bff58-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="bff58-109">Tenga en cuenta que algunos registros DNS solo son necesarios para la configuración automática de clientes de Lync 2013 y Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="bff58-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="bff58-110">Si planea usar objetos de directiva de grupo (GPO) para configurar clientes de Lync, los registros de configuración automática asociados no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="bff58-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="bff58-111">IMPORTANTE: requisitos del adaptador de red del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="bff58-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="bff58-112">Para evitar problemas de enrutamiento, compruebe que hay al menos dos adaptadores de red en los servidores perimetrales y que la puerta de enlace predeterminada solo está configurada en el adaptador de red asociado a la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="bff58-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="bff58-113">Por ejemplo, como se muestra en la única topología de borde consolidado con direcciones IP públicas figura en [un solo borde consolidado con direcciones IP públicas en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), la puerta de enlace predeterminada apunta al enrutador externo del perímetro de Internet o Firewall que puede proporcionar direcciones IP públicas.</span><span class="sxs-lookup"><span data-stu-id="bff58-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="bff58-114">La relación de red para las interfaces de servidor perimetral es una relación de enrutamiento en lugar de una relación de NAT.</span><span class="sxs-lookup"><span data-stu-id="bff58-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="bff58-115">Puede configurar dos adaptadores de red en el servidor perimetral de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="bff58-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="bff58-116">**Adaptador de red 1 (interfaz interna)**</span><span class="sxs-lookup"><span data-stu-id="bff58-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="bff58-117">Interfaz interna con 172.25.33.10 asignado.</span><span class="sxs-lookup"><span data-stu-id="bff58-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="bff58-118">No hay ninguna puerta de enlace predeterminada definida.</span><span class="sxs-lookup"><span data-stu-id="bff58-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="bff58-119">Asegúrese de que haya una ruta desde la red que contenga la interfaz interna perimetral a cualquier red que contenga servidores que ejecuten Lync Server 2013 o clientes de Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="bff58-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="bff58-120">**Adaptador de red 2 (interfaz externa)**</span><span class="sxs-lookup"><span data-stu-id="bff58-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="bff58-121">Se asignan tres direcciones IP públicas a este adaptador de red, por ejemplo, 131.107.155.10 para Edge de Access, 131.107.155.20 para Edge de conferencias web, 131.107.155.30 para Edge AV.</span><span class="sxs-lookup"><span data-stu-id="bff58-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bff58-122">Es posible, aunque no recomendable, usar una única dirección IP para las tres interfaces de servicio perimetral.</span><span class="sxs-lookup"><span data-stu-id="bff58-122">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="bff58-123">Aunque esto sí guarda las direcciones IP, requiere números de Puerto diferentes para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="bff58-123">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="bff58-124">El número de puerto predeterminado es 443/TCP, lo que garantiza que la mayoría de los firewalls remotos permitan el tráfico.</span><span class="sxs-lookup"><span data-stu-id="bff58-124">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="bff58-125">Cambiar los valores del puerto a (por ejemplo) 5061/TCP para el extremo de Access, 444/TCP para el perímetro de la conferencia web y 443/TCP para la periferia AV puede causar problemas a los usuarios remotos en los que un firewall que estén detrás no permite el tráfico por encima de 5061/TCP y 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="bff58-125">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="bff58-126">Además, tres direcciones IP distintas hacen que la solución de problemas sea más fácil, ya que es posible filtrar por dirección IP.</span><span class="sxs-lookup"><span data-stu-id="bff58-126">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="bff58-127">La dirección IP pública perimetral de acceso es principal con la puerta de enlace predeterminada establecida para el enrutador público (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="bff58-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="bff58-128">Las conferencias web y las direcciones IP públicas de los bordes A/V son direcciones IP adicionales en la sección **avanzadas** de las propiedades del **Protocolo de Internet versión 4 (TCP/IPv4)** y el **Protocolo de Internet versión 6 (TCP/IPv6)** del **área local Propiedades de conexión** en Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bff58-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="bff58-129">La configuración del servidor perimetral con dos adaptadores de red es una de dos opciones.</span><span class="sxs-lookup"><span data-stu-id="bff58-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="bff58-130">La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="bff58-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="bff58-131">La principal ventaja de esta opción es un adaptador de red distinto por cada servicio de servidor perimetral, así como una recopilación de datos potencialmente más concisa cuando se necesita la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="bff58-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="bff58-132">Registros DNS necesarios para un solo borde consolidado con direcciones IP públicas (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="bff58-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bff58-133">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="bff58-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="bff58-134">FQDN/registro DNS</span><span class="sxs-lookup"><span data-stu-id="bff58-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="bff58-135">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="bff58-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="bff58-136">Se asigna a/comentarios</span><span class="sxs-lookup"><span data-stu-id="bff58-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bff58-137">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="bff58-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bff58-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="bff58-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="bff58-140">Interfaz externa de perimetral de acceso (contoso) repite según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="bff58-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff58-141">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="bff58-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bff58-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="bff58-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="bff58-144">Interfaz externa perimetral de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="bff58-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff58-145">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="bff58-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bff58-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="bff58-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="bff58-148">Interfaz externa de borde A/V</span><span class="sxs-lookup"><span data-stu-id="bff58-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff58-149">DNS/SRV/443 externo</span><span class="sxs-lookup"><span data-stu-id="bff58-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="bff58-150">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-152">Interfaz externa perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="bff58-152">Access Edge external interface.</span></span> <span data-ttu-id="bff58-153">Necesario para que la configuración automática de los clientes de Lync 2013 y Lync 2010 funcione de forma externa.</span><span class="sxs-lookup"><span data-stu-id="bff58-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="bff58-154">Repita el procedimiento según sea necesario para todos los dominios SIP con usuarios habilitados para Lync.</span><span class="sxs-lookup"><span data-stu-id="bff58-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff58-155">DNS externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="bff58-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="bff58-156">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-158">Interfaz externa perimetral de acceso SIP requerida para la detección automática de DNS de los socios federados, conocido como "dominio SIP permitido" (denominado Federación mejorada en versiones anteriores). Repetir según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="bff58-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff58-159">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="bff58-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bff58-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bff58-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bff58-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="bff58-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="bff58-162">Interfaz interna de Edge consolidado</span><span class="sxs-lookup"><span data-stu-id="bff58-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="bff58-163">Los registros que aparecen en la tabla anterior se muestran con una extensión <EM>.net</EM> o una extensión <EM>. com</EM> para resaltar de qué zona deben residir si no usa DNS de horizonte dividido.</span><span class="sxs-lookup"><span data-stu-id="bff58-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="bff58-164">Si usa DNS de horizonte dividido, todos los registros estarán en la misma zona, con la única diferencia de si están en la versión interna o externa.</span><span class="sxs-lookup"><span data-stu-id="bff58-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="bff58-165">Para obtener más información, consulte "DNS de horizonte dividido" en <A href="lync-server-2013-determine-dns-requirements.md">determinar los requisitos de DNS para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bff58-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="bff58-166">Registros necesarios para la Federación</span><span class="sxs-lookup"><span data-stu-id="bff58-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bff58-167">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="bff58-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="bff58-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="bff58-168">FQDN</span></span></th>
<th><span data-ttu-id="bff58-169">Dirección IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="bff58-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="bff58-170">Se asigna a/comentarios</span><span class="sxs-lookup"><span data-stu-id="bff58-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bff58-171">DNS externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="bff58-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="bff58-172">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-174">Interfaz externa perimetral de acceso SIP necesaria para la detección automática de DNS de su Federación a otros posibles socios de Federación, y se conoce como "dominios SIP permitidos" (denominada Federación mejorada en versiones anteriores). Repetir según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="bff58-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="bff58-175">Este registro SRV es necesario para la movilidad y el centro de enrutamiento de notificaciones push</span><span class="sxs-lookup"><span data-stu-id="bff58-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="bff58-176">Resumen de DNS para el protocolo de presencia y mensajería extensible</span><span class="sxs-lookup"><span data-stu-id="bff58-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bff58-177">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="bff58-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="bff58-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="bff58-178">FQDN</span></span></th>
<th><span data-ttu-id="bff58-179">Dirección IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="bff58-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="bff58-180">Se asigna a/comentarios</span><span class="sxs-lookup"><span data-stu-id="bff58-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bff58-181">DNS/SRV/5269 externo</span><span class="sxs-lookup"><span data-stu-id="bff58-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="bff58-182">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bff58-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bff58-184">Interfaz externa de proxy XMPP en el servicio perimetral de acceso o grupo perimetral. Repita el procedimiento según sea necesario para todos los dominios SIP internos con los usuarios habilitados para Lync donde se permite el contacto con los contactos XMPP a través de la configuración de la Directiva de acceso externo a través de una directiva global, una directiva de sitio donde se encuentra el usuario o la Directiva de usuario aplicada al Usuario habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="bff58-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="bff58-185">También se debe configurar un dominio XMPP permitido en la Directiva del socio XMPP federado.</span><span class="sxs-lookup"><span data-stu-id="bff58-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="bff58-186">Vea temas en <strong>vea también</strong> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bff58-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff58-187">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="bff58-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bff58-188">xmpp.contoso.com (por ejemplo)</span><span class="sxs-lookup"><span data-stu-id="bff58-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="bff58-189">Dirección IP del servicio perimetral de acceso en el servidor perimetral o grupo perimetral que aloja el proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="bff58-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="bff58-190">Señala el servicio perimetral de Access o el grupo de límites que alberga el servicio de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="bff58-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="bff58-191">Normalmente, el registro SRV que cree apuntará a este registro de host (A o AAAA).</span><span class="sxs-lookup"><span data-stu-id="bff58-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

