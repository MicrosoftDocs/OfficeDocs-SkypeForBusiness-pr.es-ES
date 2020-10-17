---
title: 'Lync Server 2013: Resumen de DNS-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT'
description: 'Lync Server 2013: Resumen de DNS-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef3029323c1c2f798fddc721df832a932524c8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559406"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="fff31-103">Resumen de DNS-servidor perimetral consolidado ampliado, equilibrio de carga de DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fff31-103">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fff31-104">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="fff31-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="fff31-105">Los requisitos de registro de DNS para el acceso remoto a Lync Server 2013 son bastante sencillos en comparación con los de certificados y puertos.</span><span class="sxs-lookup"><span data-stu-id="fff31-105">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="fff31-106">Además, muchos registros son opcionales, en función de cómo configure los clientes que ejecutan Lync 2013 y si habilita la Federación.</span><span class="sxs-lookup"><span data-stu-id="fff31-106">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="fff31-107">Para obtener más información sobre los requisitos de DNS de Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fff31-107">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="fff31-108">Para obtener más información sobre cómo configurar automáticamente los clientes de Lync 2013 si no se ha configurado el DNS de cerebro dividido, consulte la sección "configuración automática sin DNS de cerebro dividido" en [determinar los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fff31-108">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="fff31-109">En la siguiente tabla se incluye un resumen de los registros DNS necesarios para admitir la topología perimetral consolidada de un solo equipo que se muestra en la figura Topología perimetral consolidada de un solo equipo.</span><span class="sxs-lookup"><span data-stu-id="fff31-109">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="fff31-110">Tenga en cuenta que algunos registros DNS solo son necesarios para la configuración automática de clientes de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fff31-110">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="fff31-111">Si planea usar objetos de directiva de grupo (GPO) para configurar los clientes de Lync, los registros asociados no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="fff31-111">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="fff31-112">IMPORTANTE: requisitos del adaptador de red del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="fff31-112">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="fff31-113">Para evitar problemas de enrutamiento, compruebe que hay al menos dos adaptadores de red en los servidores perimetrales y que la puerta de enlace predeterminada solo está configurada en el adaptador de red asociado con la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="fff31-113">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="fff31-114">Por ejemplo, tal y como se muestra en el escenario de perímetro consolidado escalado [, en servidor perimetral consolidado escalado, equilibrio de carga de DNS con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), la puerta de enlace predeterminada apunta al firewall externo.</span><span class="sxs-lookup"><span data-stu-id="fff31-114">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="fff31-115">Puede configurar dos adaptadores de red en cada servidor perimetral de la siguiente forma</span><span class="sxs-lookup"><span data-stu-id="fff31-115">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="fff31-116">**Adaptador de red 1 - Nodo 1 (Interfaz interna)**</span><span class="sxs-lookup"><span data-stu-id="fff31-116">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="fff31-117">Interfaz interna con 172.25.33.10 asignado.</span><span class="sxs-lookup"><span data-stu-id="fff31-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="fff31-118">No se define ninguna puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fff31-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="fff31-119">Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna a cualquier red que contenga servidores que ejecuten clientes de Lync Server 2013 o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="fff31-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="fff31-120">**Adaptador de red 1 - Nodo 2 (Interfaz interna)**</span><span class="sxs-lookup"><span data-stu-id="fff31-120">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="fff31-121">Interfaz interna con 172.25.33.11 asignada.</span><span class="sxs-lookup"><span data-stu-id="fff31-121">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="fff31-122">No se define ninguna puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fff31-122">No default gateway is defined.</span></span>
    
    <span data-ttu-id="fff31-123">Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna a cualquier red que contenga servidores que ejecuten clientes de Lync Server 2013 o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="fff31-123">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="fff31-124">**Adaptador de red 2 - Nodo 1 (Interfaz externa)**</span><span class="sxs-lookup"><span data-stu-id="fff31-124">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="fff31-125">Se asignan tres direcciones IP privadas a este adaptador de red, por ejemplo, 10.45.16.10 para el servidor perimetral de acceso, 10.45.16.20 para el servidor perimetral de conferencia Web, 10.45.16.30 para el servidor perimetral AV.</span><span class="sxs-lookup"><span data-stu-id="fff31-125">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fff31-p104">Si bien no es recomendable, es posible usar una única dirección IP para las tres interfaces de servicio perimetral. Si bien esto no guarda las direcciones IP, requiere números de puerto diferentes para cada servicio. El número de puerto predeterminado es 443/TCP, que garantiza que la mayoría de los firewalls remotos permitirán el tráfico. Cambiar los valores del puerto a (por ejemplo) 5061/TCP para el Servidor perimetral de acceso, 444/TCP para el Servidor perimetral de conferencia web y 443/TCP para el servidor perimetral AV puede ocasionarle problemas a los usuarios remotos si se encuentran detrás de un firewall que no permite el tráfico por 5061/TCP y 444/TCP. Además, tres direcciones IP diferentes facilitan la solución de problemas ya que es posible filtrar la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="fff31-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="fff31-131">La dirección IP pública de servidor perimetral de acceso es principal con puerta de enlace predeterminada establecida en el enrutador integrado (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="fff31-131">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="fff31-132">Las direcciones IP perimetrales de conferencia web y de A/V son direcciones IP adicionales en la sección **avanzadas** de las propiedades de **Protocolo de Internet versión 4 (TCP/IPv4)** y **Protocolo de Internet versión 6 (TCP/IPv6)** de las **propiedades de conexión de área local** en Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fff31-132">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="fff31-133">**Adaptador de red 2 - Nodo 2 (Interfaz externa)**</span><span class="sxs-lookup"><span data-stu-id="fff31-133">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="fff31-134">Se asignan tres direcciones IP privadas a este adaptador de red, por ejemplo, 10.45.16.11 para el servidor perimetral de acceso, 10.45.16.21 para el servidor perimetral de conferencia Web, 10.45.16.31 para el servidor perimetral AV.</span><span class="sxs-lookup"><span data-stu-id="fff31-134">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="fff31-135">La dirección IP pública de servidor perimetral de acceso es principal con puerta de enlace predeterminada establecida en el enrutador integrado (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="fff31-135">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="fff31-136">Las direcciones IP perimetrales de conferencia web y de A/V son direcciones IP adicionales en la sección **avanzadas** de las propiedades de **Protocolo de Internet versión 4 (TCP/IPv4)** y **Protocolo de Internet versión 6 (TCP/IPv6)** de las **propiedades de conexión de área local** en Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fff31-136">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="fff31-137">La configuración del servidor perimetral con dos adaptadores de red es una de estas dos opciones.</span><span class="sxs-lookup"><span data-stu-id="fff31-137">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="fff31-138">La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="fff31-138">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="fff31-139">La ventaja principal de esta opción es un adaptador de red distinto por cada servicio de servidor perimetral y, potencialmente, una recopilación de datos más concisa para la solución de problemas es necesaria</span><span class="sxs-lookup"><span data-stu-id="fff31-139">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="fff31-140">Registros DNS necesarios para el perímetro consolidado escalado, equilibrio de carga de DNS con direcciones IP privadas mediante NAT (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="fff31-140">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fff31-141">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="fff31-141">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="fff31-142">FQDN/Registro DNS</span><span class="sxs-lookup"><span data-stu-id="fff31-142">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="fff31-143">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="fff31-143">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="fff31-144">Enruta a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="fff31-144">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fff31-145">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="fff31-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fff31-146">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fff31-146">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-147">131.107.155.10 y 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="fff31-147">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="fff31-148">Interfaz perimetral de acceso externa (Contoso) En caso necesario, repita la operación para los dominios SIP con usuarios de Lync habilitados</span><span class="sxs-lookup"><span data-stu-id="fff31-148">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fff31-149">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="fff31-149">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fff31-150">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fff31-150">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-151">131.107.155.20 y 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="fff31-151">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="fff31-152">Interfaz externa de servidor perimetral de conferencia web</span><span class="sxs-lookup"><span data-stu-id="fff31-152">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fff31-153">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="fff31-153">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fff31-154">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fff31-154">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-155">131.107.155.30 y 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="fff31-155">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="fff31-156">Interfaz externa de servidor perimetral de A/V</span><span class="sxs-lookup"><span data-stu-id="fff31-156">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fff31-157">DNS externo/SRV/443</span><span class="sxs-lookup"><span data-stu-id="fff31-157">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="fff31-158">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="fff31-158">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fff31-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-160">Interfaz perimetral de acceso externa.</span><span class="sxs-lookup"><span data-stu-id="fff31-160">Access Edge external interface.</span></span> <span data-ttu-id="fff31-161">Necesario para la configuración automática de los clientes de Lync 2013 y Lync 2010 para que funcionen de forma externa.</span><span class="sxs-lookup"><span data-stu-id="fff31-161">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="fff31-162">En caso necesario, repita la operación para los dominios SIP con usuarios de Lync habilitados.</span><span class="sxs-lookup"><span data-stu-id="fff31-162">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fff31-163">DNS externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="fff31-163">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="fff31-164">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="fff31-164">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fff31-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-166">Interfaz perimetral externa de acceso SIP.</span><span class="sxs-lookup"><span data-stu-id="fff31-166">SIP Access Edge external interface.</span></span> <span data-ttu-id="fff31-167">Necesario para la detección automática de DNS de socios federados conocida como "dominio SIP permitido" (denominado Federación mejorada en versiones anteriores).</span><span class="sxs-lookup"><span data-stu-id="fff31-167">Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="fff31-168">Repetir según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="fff31-168">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fff31-169">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="fff31-169">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fff31-170">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fff31-170">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fff31-171">172.25.33.10 y 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="fff31-171">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="fff31-172">Interfaz perimetral interna consolidada</span><span class="sxs-lookup"><span data-stu-id="fff31-172">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="fff31-173">Registros necesarios para la federación</span><span class="sxs-lookup"><span data-stu-id="fff31-173">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fff31-174">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="fff31-174">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="fff31-175">FQDN</span><span class="sxs-lookup"><span data-stu-id="fff31-175">FQDN</span></span></th>
<th><span data-ttu-id="fff31-176">Dirección IP/Registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="fff31-176">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="fff31-177">Enruta a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="fff31-177">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fff31-178">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="fff31-178">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="fff31-179">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="fff31-179">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-180">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fff31-180">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-181">Interfaz externa de SIP Access Edge requerida para la recuperación automática de DNS de su federación a otros posibles socios de la federación, y es conocida como “Dominios SIP permitidos” (llamados federación mejorada en versiones anteriores). Repita según sea necesario para todos los dominios SIP con usuarios habilitados por Lync</span><span class="sxs-lookup"><span data-stu-id="fff31-181">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="fff31-182">Este registro SRV se necesita para la movilidad y compensación de notificación de inserción</span><span class="sxs-lookup"><span data-stu-id="fff31-182">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="fff31-183">Resumen DNS – Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="fff31-183">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fff31-184">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="fff31-184">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="fff31-185">FQDN/Registro DNS</span><span class="sxs-lookup"><span data-stu-id="fff31-185">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="fff31-186">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="fff31-186">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="fff31-187">Enruta a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="fff31-187">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fff31-188">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="fff31-188">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fff31-189">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fff31-189">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-190">Interfaz del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="fff31-190">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="fff31-191">Interfaz externa de Access Edge (Contoso) Repita según necesite para todos los dominios SIP con usuarios habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="fff31-191">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="fff31-192">Resumen DNS para el protocolo XMPP(Extensible Messaging y Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="fff31-192">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fff31-193">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="fff31-193">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="fff31-194">FQDN</span><span class="sxs-lookup"><span data-stu-id="fff31-194">FQDN</span></span></th>
<th><span data-ttu-id="fff31-195">Dirección IP/Registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="fff31-195">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="fff31-196">Enruta a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="fff31-196">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fff31-197">DNS/SRV/5269 externo</span><span class="sxs-lookup"><span data-stu-id="fff31-197">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="fff31-198">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="fff31-198">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-199">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fff31-199">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fff31-200">Interfaz externa de proxy XMPP en el servicio perimetral de acceso o el grupo de servidores perimetrales. Repita los pasos necesarios para todos los dominios SIP internos con los usuarios habilitados para Lync, donde se permite el contacto con los contactos XMPP a través de la configuración de la Directiva de acceso externo a través de una directiva global, una directiva de sitio donde se encuentra el usuario o la Directiva de usuario que se aplica al usuario habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="fff31-200">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="fff31-201">También debe configurarse un dominio XMPP permitido en la Directiva de socios federados XMPP.</span><span class="sxs-lookup"><span data-stu-id="fff31-201">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="fff31-202">Vea los temas en <strong>vea también</strong> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fff31-202">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fff31-203">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="fff31-203">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fff31-204">xmpp.contoso.com (por ejemplo)</span><span class="sxs-lookup"><span data-stu-id="fff31-204">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="fff31-205">Dirección IP del servicio perimetral de acceso en el servidor perimetral o el grupo de servidores perimetrales que hospedan el proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="fff31-205">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="fff31-206">Señala el servicio perimetral de acceso o el grupo de servidores perimetrales que hospeda el servicio de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="fff31-206">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="fff31-207">Generalmente, el registro SRV que crea llevará a este registro de host (A o AAAA)</span><span class="sxs-lookup"><span data-stu-id="fff31-207">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

