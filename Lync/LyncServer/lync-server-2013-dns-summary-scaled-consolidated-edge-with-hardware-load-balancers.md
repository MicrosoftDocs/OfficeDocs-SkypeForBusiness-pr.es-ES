---
title: Resumen de DNS-servidor perimetral consolidado ampliado con equilibradores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95ab0c9b68d21af782570c850642ce7e83b996d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="88471-102">Resumen de DNS-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88471-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88471-103">_**Última modificación del tema:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="88471-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="88471-104">Los requisitos de registro de DNS para el acceso remoto a Lync Server 2013 son bastante sencillos en comparación con los de certificados y puertos.</span><span class="sxs-lookup"><span data-stu-id="88471-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="88471-105">Además, muchos registros son opcionales, en función de cómo configure los clientes que ejecutan Lync 2013 y si habilita la Federación.</span><span class="sxs-lookup"><span data-stu-id="88471-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="88471-106">Para obtener más información sobre los requisitos de DNS de Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88471-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="88471-107">Para obtener más información sobre cómo configurar automáticamente los clientes de Lync 2013 si no se ha configurado el DNS de cerebro dividido, consulte la sección "configuración automática sin DNS de cerebro dividido" en [determinar los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88471-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="88471-108">En la siguiente tabla se incluye un resumen de los registros DNS que se requieren para admitir la figura Topología perimetral consolidada (carga de hardware equilibrada).</span><span class="sxs-lookup"><span data-stu-id="88471-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="88471-109">Tenga en cuenta que algunos registros DNS solo son necesarios para la configuración automática de los clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="88471-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="88471-110">Si planea usar objetos de directiva de grupo (GPO) para configurar los clientes de Lync, los registros asociados no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="88471-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="88471-111">IMPORTANTE: requisitos del adaptador de red del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="88471-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="88471-112">Para evitar problemas de enrutamiento, compruebe que hay al menos dos adaptadores de red en los servidores perimetrales y que la puerta de enlace predeterminada solo está configurada en el adaptador de red asociado con la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="88471-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="88471-113">Por ejemplo, tal y como se muestra en la figura en el escenario perimetral consolidado escalado en [servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), la puerta de enlace predeterminada apunta al firewall externo.</span><span class="sxs-lookup"><span data-stu-id="88471-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="88471-114">Puede configurar dos adaptadores de red en cada uno de los servidores perimetrales de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="88471-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="88471-115">**Adaptador de red 1 (interfaz interna)**</span><span class="sxs-lookup"><span data-stu-id="88471-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="88471-116">Interfaz interna con 172.25.33.10 asignada.</span><span class="sxs-lookup"><span data-stu-id="88471-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="88471-117">No hay ninguna puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="88471-117">No default gateway.</span></span>
    
    <span data-ttu-id="88471-118">Asegúrese de que existe una ruta desde la red que contiene la interfaz interna del servidor perimetral a cualquier red que contenga clientes de Lync Server o servidores que ejecuten Lync Server (por ejemplo, de 172.25.33.0 a 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="88471-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="88471-119">**Adaptador de red 2 (interfaz externa)**</span><span class="sxs-lookup"><span data-stu-id="88471-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="88471-120">Se asignan tres direcciones IP públicas a este adaptador de red, por ejemplo, 131.107.155.10 para el servicio perimetral de acceso, 131.107.155.20 para el servicio perimetral de conferencia Web, 131.107.155.30 para el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="88471-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="88471-121">Las direcciones IP que se asignan a las interfaces de red externas reales del servidor perimetral pueden depender del equilibrador de carga de hardware que elija.</span><span class="sxs-lookup"><span data-stu-id="88471-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="88471-122">Consulte la documentación del equilibrador de carga de hardware para conocer los requisitos de direcciones IP reales.</span><span class="sxs-lookup"><span data-stu-id="88471-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="88471-123">Si bien no es recomendable, es posible usar una única dirección IP para las tres interfaces de servicio perimetral.</span><span class="sxs-lookup"><span data-stu-id="88471-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="88471-124">Si bien esto no guarda las direcciones IP, requiere números de puerto diferentes para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="88471-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="88471-125">El número de puerto predeterminado es 443/TCP, que garantiza que la mayoría de los firewalls remotos permitirán el tráfico.</span><span class="sxs-lookup"><span data-stu-id="88471-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="88471-126">Cambiar los valores de puerto a (por ejemplo) 5061/TCP para el servicio perimetral de acceso, 444/TCP para el servicio perimetral de conferencia web y 443/TCP para el servicio perimetral A/V puede causar problemas para los usuarios remotos donde un firewall que se encuentra detrás no permite el tráfico sobre 5061/TCP y 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="88471-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="88471-127">Además, tres direcciones IP diferentes facilitan la solución de problemas ya que es posible filtrar la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="88471-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="88471-128">La dirección IP del servicio perimetral de acceso es principal con puerta de enlace predeterminada establecida en enrutador accesible desde Internet (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="88471-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="88471-129">El servicio perimetral de conferencia web y las direcciones IP del servicio perimetral A/V secundarias.</span><span class="sxs-lookup"><span data-stu-id="88471-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="88471-130">La configuración del servidor perimetral con dos adaptadores de red es una de estas dos opciones.</span><span class="sxs-lookup"><span data-stu-id="88471-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="88471-131">La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="88471-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="88471-132">La ventaja principal de esta opción es un adaptador de red distinto por cada servicio de servidor perimetral y, potencialmente, una recopilación de datos más concisa para la solución de problemas es necesaria</span><span class="sxs-lookup"><span data-stu-id="88471-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="88471-133">Registros DNS necesarios para la Topología perimetral consolidada escalada (carga equilibrada con hardware): Topología perimetral consolidada</span><span class="sxs-lookup"><span data-stu-id="88471-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88471-134">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="88471-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="88471-135">FQDN/Registro DNS</span><span class="sxs-lookup"><span data-stu-id="88471-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="88471-136">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="88471-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="88471-137">Enruta a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="88471-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88471-138">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="88471-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="88471-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88471-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88471-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="88471-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="88471-141">Interfaz externa del servicio perimetral de acceso (contoso).</span><span class="sxs-lookup"><span data-stu-id="88471-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="88471-142">Repetir según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="88471-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88471-143">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="88471-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="88471-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88471-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88471-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="88471-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="88471-146">Interfaz externa del servicio perimetral de conferencia Web</span><span class="sxs-lookup"><span data-stu-id="88471-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88471-147">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="88471-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="88471-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88471-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88471-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="88471-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="88471-150">Interfaz externa del servicio perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="88471-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88471-151">DNS externo/SRV/443</span><span class="sxs-lookup"><span data-stu-id="88471-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="88471-152">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="88471-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88471-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88471-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88471-154">Interfaz externa del servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="88471-154">Access Edge service external interface.</span></span> <span data-ttu-id="88471-155">Necesario para la configuración automática de los clientes de Lync 2013 y Lync 2010 para que funcionen de forma externa.</span><span class="sxs-lookup"><span data-stu-id="88471-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="88471-156">En caso necesario, repita la operación para los dominios SIP con usuarios de Lync habilitados.</span><span class="sxs-lookup"><span data-stu-id="88471-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88471-157">DNS externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="88471-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="88471-158">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="88471-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88471-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88471-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="88471-160">La interfaz externa del servicio perimetral de acceso SIP es necesaria para la detección automática de DNS de los socios federados conocida como "dominio SIP permitido" (denominado Federación mejorada en versiones anteriores).</span><span class="sxs-lookup"><span data-stu-id="88471-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="88471-161">Repita el procedimiento tantas veces como sea necesario para todos los dominios SIP con usuarios habilitados para Lync y los clientes móviles de Microsoft Lync que usan el servicio de notificación de inserción o el servicio de notificaciones push de Apple</span><span class="sxs-lookup"><span data-stu-id="88471-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88471-162">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="88471-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="88471-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="88471-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="88471-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="88471-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="88471-165">Interfaz perimetral interna consolidada</span><span class="sxs-lookup"><span data-stu-id="88471-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

