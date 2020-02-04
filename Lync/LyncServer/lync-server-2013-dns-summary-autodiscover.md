---
title: 'Lync Server 2013: Resumen de DNS-detección automática'
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
ms.openlocfilehash: 6ed7d6edb44ebca8656a50aec432fe3c0ac669d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="f4295-102">Resumen de DNS-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4295-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4295-103">_**Última modificación del tema:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="f4295-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="f4295-104">Detección automática es un servicio flexible, ya que acepta la comunicación a través de HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f4295-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="f4295-105">Para ello, el sistema de nombres de dominio (DNS) y los certificados usados por los servidores que hospedan el servicio Detección automática deben estar configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4295-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="f4295-106">Los requisitos de certificado se tratan en [Resumen del certificado: detección automática en Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span><span class="sxs-lookup"><span data-stu-id="f4295-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f4295-107">La lógica de búsqueda DNS para los clientes de Lync Server usa un orden específico de resolución.</span><span class="sxs-lookup"><span data-stu-id="f4295-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="f4295-108">Siempre debes incluir el lyncdiscoverinternal. &lt;dominio&gt; y el lyncdiscover. &lt;dominio&gt; en el DNS.</span><span class="sxs-lookup"><span data-stu-id="f4295-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="f4295-109">Excluyendo la lyncdiscoverinternal. &lt;Registro&gt; de dominio hará que los clientes internos no se conecten a los servicios previstos o reciban la respuesta incorrecta de detección automática.</span><span class="sxs-lookup"><span data-stu-id="f4295-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="f4295-110">Registros DNS internos</span><span class="sxs-lookup"><span data-stu-id="f4295-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4295-111">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="f4295-111">Record type</span></span></th>
<th><span data-ttu-id="f4295-112">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="f4295-112">Host name</span></span></th>
<th><span data-ttu-id="f4295-113">Se resuelve en</span><span class="sxs-lookup"><span data-stu-id="f4295-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4295-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="f4295-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="f4295-115">Lyncdiscoverinternal. &lt;nombre de dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="f4295-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="f4295-116">El FQDN de los servicios Web internos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director.</span><span class="sxs-lookup"><span data-stu-id="f4295-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4295-117">A (host, si IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="f4295-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="f4295-118">lyncdiscoverinternal. &lt;nombre de dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="f4295-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="f4295-119">Dirección IP de los servicios Web internos (dirección IP virtual (VIP) si usa un equilibrador de carga) de su grupo de directores, si tiene uno o el grupo de servidores front-end, si no tiene un director.</span><span class="sxs-lookup"><span data-stu-id="f4295-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f4295-120">Cree uno de los siguientes registros de DNS externos:</span><span class="sxs-lookup"><span data-stu-id="f4295-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="f4295-121">Registros DNS externos</span><span class="sxs-lookup"><span data-stu-id="f4295-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4295-122">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="f4295-122">Record type</span></span></th>
<th><span data-ttu-id="f4295-123">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="f4295-123">Host name</span></span></th>
<th><span data-ttu-id="f4295-124">Se resuelve en</span><span class="sxs-lookup"><span data-stu-id="f4295-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4295-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="f4295-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="f4295-126">lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="f4295-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="f4295-127">El FQDN de servicios web externos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director.</span><span class="sxs-lookup"><span data-stu-id="f4295-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4295-128">A (host, si IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="f4295-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="f4295-129">lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="f4295-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="f4295-130">Dirección IP externa o pública del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f4295-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f4295-131">El tráfico externo pasa por el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f4295-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f4295-132">Los clientes de dispositivos móviles no admiten varios certificados de capa de sockets seguros (SSL) de diferentes dominios.</span><span class="sxs-lookup"><span data-stu-id="f4295-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="f4295-133">Por lo tanto, no se admite la redirección CNAME a dominios diferentes a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f4295-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="f4295-134">Por ejemplo, un registro CNAME de DNS para lyncdiscover.contoso.com que redirige a una dirección de director.contoso.net no es compatible con HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f4295-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="f4295-135">En una topología de este tipo, un cliente de dispositivo móvil debe usar HTTP para la primera solicitud, de modo que la redirección CNAME se resuelva por HTTP.</span><span class="sxs-lookup"><span data-stu-id="f4295-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="f4295-136">Después, las solicitudes posteriores usan HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f4295-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="f4295-137">Para admitir este escenario, debe configurar el proxy inverso con una regla de publicación web para el puerto 80 (HTTP).</span><span class="sxs-lookup"><span data-stu-id="f4295-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="f4295-138">Para obtener más información, consulte "para crear una regla de publicación web para el puerto 80" en <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configurar el proxy inverso para la movilidad en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f4295-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="f4295-139">El redireccionamiento CNAME para el mismo dominio es compatible con HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f4295-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="f4295-140">En este caso, el certificado del dominio de destino cubre el dominio de origen.</span><span class="sxs-lookup"><span data-stu-id="f4295-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4295-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4295-141">See Also</span></span>


[<span data-ttu-id="f4295-142">Configuración del proxy inverso para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4295-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="f4295-143">Resumen del certificado: detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4295-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

