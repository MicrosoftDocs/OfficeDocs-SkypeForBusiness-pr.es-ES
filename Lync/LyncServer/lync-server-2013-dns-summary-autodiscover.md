---
title: 'Lync Server 2013: Resumen de DNS-detección automática'
description: 'Lync Server 2013: Resumen de DNS-detección automática.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574286"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="eb835-103">Resumen de DNS-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb835-103">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb835-104">_**Última modificación del tema:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="eb835-104">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="eb835-105">La detección automática es un servicio flexible en el que aceptará la comunicación a través de HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="eb835-105">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="eb835-106">Para ello, el sistema de nombres de dominio (DNS) y los certificados que usan los servidores que hospedan el servicio Detección automática deben estar configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="eb835-106">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="eb835-107">Los requisitos de certificado se tratan en [Resumen de certificado-detección automática en Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span><span class="sxs-lookup"><span data-stu-id="eb835-107">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eb835-108">La lógica de búsqueda DNS para los clientes de Lync Server usa un orden de resolución específico.</span><span class="sxs-lookup"><span data-stu-id="eb835-108">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="eb835-109">Siempre debe incluir la lyncdiscoverinternal. &lt; domain &gt; y lyncdiscover. &lt; dominio &gt; en el DNS.</span><span class="sxs-lookup"><span data-stu-id="eb835-109">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="eb835-110">Excluir lyncdiscoverinternal. &lt; &gt; el registro de dominio hará que los clientes internos no puedan conectarse a los servicios previstos o reciban la respuesta de detección automática incorrecta.</span><span class="sxs-lookup"><span data-stu-id="eb835-110">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="eb835-111">Registros DNS internos</span><span class="sxs-lookup"><span data-stu-id="eb835-111">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb835-112">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="eb835-112">Record type</span></span></th>
<th><span data-ttu-id="eb835-113">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="eb835-113">Host name</span></span></th>
<th><span data-ttu-id="eb835-114">Se resuelve en</span><span class="sxs-lookup"><span data-stu-id="eb835-114">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb835-115">CNAME</span><span class="sxs-lookup"><span data-stu-id="eb835-115">CNAME</span></span></p></td>
<td><p><span data-ttu-id="eb835-116">Lyncdiscoverinternal. &lt; nombre de dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="eb835-116">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="eb835-117">El FQDN de servicios Web internos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director.</span><span class="sxs-lookup"><span data-stu-id="eb835-117">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb835-118">A (host, si IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="eb835-118">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="eb835-119">lyncdiscoverinternal. &lt; nombre de dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="eb835-119">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="eb835-120">Dirección IP de servicios Web internos (dirección IP virtual (VIP) si usa un equilibrador de carga) de su grupo de directores, si tiene uno o el grupo de servidores front-end si no tiene un director.</span><span class="sxs-lookup"><span data-stu-id="eb835-120">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eb835-121">Debe crear uno de los siguientes registros DNS externos:</span><span class="sxs-lookup"><span data-stu-id="eb835-121">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="eb835-122">Registros DNS externos</span><span class="sxs-lookup"><span data-stu-id="eb835-122">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb835-123">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="eb835-123">Record type</span></span></th>
<th><span data-ttu-id="eb835-124">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="eb835-124">Host name</span></span></th>
<th><span data-ttu-id="eb835-125">Se resuelve en</span><span class="sxs-lookup"><span data-stu-id="eb835-125">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb835-126">CNAME</span><span class="sxs-lookup"><span data-stu-id="eb835-126">CNAME</span></span></p></td>
<td><p><span data-ttu-id="eb835-127">lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="eb835-127">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="eb835-128">El FQDN de servicios web externos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director.</span><span class="sxs-lookup"><span data-stu-id="eb835-128">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb835-129">A (host, si IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="eb835-129">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="eb835-130">lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="eb835-130">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="eb835-131">Dirección IP externa o pública del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="eb835-131">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="eb835-132">El tráfico externo circula a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="eb835-132">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="eb835-133">Los clientes de dispositivos móviles no admiten varios certificados de capa de sockets seguros (SSL) de distintos dominios.</span><span class="sxs-lookup"><span data-stu-id="eb835-133">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="eb835-134">Por lo tanto, la redirección de CNAME a distintos dominios no se admite a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="eb835-134">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="eb835-135">Por ejemplo, un registro CNAME de DNS para lyncdiscover.contoso.com que se redirige a una dirección de director.contoso.net no se admite a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="eb835-135">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="eb835-136">En una topología así, un cliente de dispositivo móvil necesita usar HTTP para la primera solicitud, de modo que la redirección de CNAME se resuelva a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="eb835-136">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="eb835-137">A continuación, las solicitudes posteriores usan HTTPS.</span><span class="sxs-lookup"><span data-stu-id="eb835-137">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="eb835-138">Para admitir este escenario, debe configurar el proxy inverso con una regla de publicación web para el puerto 80 (HTTP).</span><span class="sxs-lookup"><span data-stu-id="eb835-138">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="eb835-139">Para obtener información detallada, consulte "para crear una regla de publicación web para el puerto 80" en <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the inverso proxy for Mobility in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="eb835-139">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="eb835-140">La redirección de CNAME al mismo dominio se admite a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="eb835-140">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="eb835-141">En este caso, el certificado del dominio de destino cubre el dominio de origen.</span><span class="sxs-lookup"><span data-stu-id="eb835-141">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb835-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb835-142">See Also</span></span>


[<span data-ttu-id="eb835-143">Configuración del proxy inverso para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb835-143">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="eb835-144">Resumen de certificado-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb835-144">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

