---
title: 'Lync Server 2013: Requisitos de DNS para el grupo de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="1af17-102">Requisitos de DNS para el grupo de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1af17-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1af17-103">_**Última modificación del tema:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="1af17-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="1af17-104">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o en miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="1af17-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="1af17-105">Debe configurar los registros de sistema de nombres de dominio (DNS) necesarios antes de publicar su topología en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="1af17-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="1af17-106">Además, algunos de los nombres de dominio completos (FQDN) que se usan en la configuración de una implementación de Lync Server 2013 son lógicos y no FQDN de servidor físico, por lo que es necesaria una configuración DNS adicional antes de la publicación.</span><span class="sxs-lookup"><span data-stu-id="1af17-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1af17-107">Lync Server 2013 no admite dominios con etiqueta única.</span><span class="sxs-lookup"><span data-stu-id="1af17-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="1af17-108">Por ejemplo, un bosque con un dominio raíz denominado <STRONG>contoso. local</STRONG> es compatible, pero no se admite un dominio raíz denominado <STRONG>local</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1af17-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="1af17-109">Para obtener más información, consulte el artículo 300684 de Microsoft Knowledge base, "información sobre la configuración de Windows para dominios con nombres DNS de etiqueta única", en <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="1af17-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1af17-110">El nombre que especifique debe ser idéntico al nombre de equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="1af17-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="1af17-111">De forma predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre corto, no un FQDN.</span><span class="sxs-lookup"><span data-stu-id="1af17-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="1af17-112">El Generador de topologías usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="1af17-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="1af17-113"><STRONG>Usar solo caracteres estándar</STRONG> (incluidos A-Z, a-z, 0-9 y guiones) al asignar FQDN de los servidores que ejecutan Lync Server, servidores perimetrales y grupos.</span><span class="sxs-lookup"><span data-stu-id="1af17-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="1af17-114">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="1af17-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="1af17-115">A menudo, los caracteres no estándar de un FQDN no son admitidos por el DNS externo y las entidades de certificación públicas (CA) (cuando se debe asignar el FQDN al SN en el certificado).</span><span class="sxs-lookup"><span data-stu-id="1af17-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="1af17-116">Antes de operar la topología después de haberla implementado, asegúrese de crear los siguientes registros de Active Directory y DNS (según las necesidades de características específicas que determinen):</span><span class="sxs-lookup"><span data-stu-id="1af17-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="1af17-117">Cada rol de servidor que existirá en la topología se publica como un objeto de Active Directory (una vez que se une el equipo con el dominio).</span><span class="sxs-lookup"><span data-stu-id="1af17-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="1af17-118">Existe un registro A de DNS para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="1af17-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="1af17-119">Existe un registro SRV de DNS para cada dominio SIP si piensa usar el inicio de sesión automático para clientes en forma \_de\_sipinternaltls TCP. \<Dominio\>SIP.</span><span class="sxs-lookup"><span data-stu-id="1af17-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="1af17-120">Si va a usar la configuración manual para clientes, este registro no es necesario.</span><span class="sxs-lookup"><span data-stu-id="1af17-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="1af17-121">Un registro A de DNS para cada dirección URL simple configurada, de la que normalmente hay cuatro: reunirse, marcación, LWA y programador.</span><span class="sxs-lookup"><span data-stu-id="1af17-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="1af17-122">Además, existe la dirección URL simple de administrador, que es una dirección URL especial para el acceso al panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1af17-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="1af17-123">El servidor que ejecuta SQL Server debe estar unido al dominio y ser accesible desde el equipo desde el que se está publicando el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="1af17-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="1af17-124">La tabla sigue las arquitecturas de referencia presentadas en la sección de planificación.</span><span class="sxs-lookup"><span data-stu-id="1af17-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="1af17-125">Para obtener más información, vea [escenarios de acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="1af17-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="1af17-126">Registros DNS necesarios para el grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="1af17-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1af17-127">Ubicación</span><span class="sxs-lookup"><span data-stu-id="1af17-127">Location</span></span></th>
<th><span data-ttu-id="1af17-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="1af17-128">Type</span></span></th>
<th><span data-ttu-id="1af17-129">FQDN</span><span class="sxs-lookup"><span data-stu-id="1af17-129">FQDN</span></span></th>
<th><span data-ttu-id="1af17-130">Se asigna a/comentarios</span><span class="sxs-lookup"><span data-stu-id="1af17-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1af17-131">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-132">A</span><span class="sxs-lookup"><span data-stu-id="1af17-132">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1af17-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1af17-134">Pool01 (equilibrio de carga de DNS).</span><span class="sxs-lookup"><span data-stu-id="1af17-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="1af17-135">Requiere un registro DNS A para la dirección IP de cada servidor front-end dentro del grupo, que se asigna al FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="1af17-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1af17-136">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-137">A</span><span class="sxs-lookup"><span data-stu-id="1af17-137">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1af17-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1af17-139">Pool01 (IP virtual (VIP) de equilibrador de carga de hardware).</span><span class="sxs-lookup"><span data-stu-id="1af17-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1af17-140">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-141">A</span><span class="sxs-lookup"><span data-stu-id="1af17-141">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1af17-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="1af17-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1af17-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="1af17-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1af17-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="1af17-145">…</span><span class="sxs-lookup"><span data-stu-id="1af17-145"></span></span></p></td>
<td><p><span data-ttu-id="1af17-146">Servidor front-end de Pool01 (nodo 1).</span><span class="sxs-lookup"><span data-stu-id="1af17-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="1af17-147">Servidor front-end Pool01 (nodo 2).</span><span class="sxs-lookup"><span data-stu-id="1af17-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="1af17-148">Servidor front-end Pool01 (nodo 3).</span><span class="sxs-lookup"><span data-stu-id="1af17-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="1af17-149">…</span><span class="sxs-lookup"><span data-stu-id="1af17-149"></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1af17-150">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-151">A</span><span class="sxs-lookup"><span data-stu-id="1af17-151">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1af17-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1af17-153">Servidor front-end Pool01 (nodo 2).</span><span class="sxs-lookup"><span data-stu-id="1af17-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1af17-154">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-155">A</span><span class="sxs-lookup"><span data-stu-id="1af17-155">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1af17-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1af17-157">Pool01 (VIP) para el tráfico web entre clientes y servidores.</span><span class="sxs-lookup"><span data-stu-id="1af17-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1af17-158">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-159">A</span><span class="sxs-lookup"><span data-stu-id="1af17-159">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1af17-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1af17-161">Servidor de Pool01 back end con SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="1af17-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1af17-162">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-163">A</span><span class="sxs-lookup"><span data-stu-id="1af17-163">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1af17-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1af17-165">Necesario para Lync Phone Edition o el inicio de sesión automático de clientes sin registros SRV de DNS y para una coincidencia de dominios estricta.</span><span class="sxs-lookup"><span data-stu-id="1af17-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="1af17-166">No se requiere en todos los casos.</span><span class="sxs-lookup"><span data-stu-id="1af17-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1af17-167">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-168">A</span><span class="sxs-lookup"><span data-stu-id="1af17-168">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1af17-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="1af17-170">Supone que se trata de un segundo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="1af17-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="1af17-171">Necesario para Lync Phone Edition, el inicio de sesión automático de clientes sin los registros SRV de DNS y para la coincidencia estricta de dominios.</span><span class="sxs-lookup"><span data-stu-id="1af17-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="1af17-172">No se requiere en todos los casos.</span><span class="sxs-lookup"><span data-stu-id="1af17-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1af17-173">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-174">A</span><span class="sxs-lookup"><span data-stu-id="1af17-174">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1af17-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1af17-176">Dirección URL simple para conferencias de acceso telefónico local publicadas internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="1af17-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1af17-177">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-178">A</span><span class="sxs-lookup"><span data-stu-id="1af17-178">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1af17-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1af17-180">Dirección URL simple para conferencias publicadas internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="1af17-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1af17-181">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-182">A</span><span class="sxs-lookup"><span data-stu-id="1af17-182">A</span></span></p></td>
<td><p><span data-ttu-id="1af17-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1af17-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="1af17-184">administradores</span><span class="sxs-lookup"><span data-stu-id="1af17-184">admin</span></span></p></td>
<td><p><span data-ttu-id="1af17-185">Registro opcional, dirección URL simple para Lync Server 2013 panel de control publicado internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="1af17-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="1af17-186">Se recomienda usar solo el nombre de host (sin nombre de dominio).</span><span class="sxs-lookup"><span data-stu-id="1af17-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="1af17-187">VIP = dirección IP virtual de equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="1af17-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="1af17-188">Registros SRV de DNS para el grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="1af17-188">DNS SRV Records for the Front End pool</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1af17-189">Ubicación</span><span class="sxs-lookup"><span data-stu-id="1af17-189">Location</span></span></th>
<th><span data-ttu-id="1af17-190">Tipo</span><span class="sxs-lookup"><span data-stu-id="1af17-190">Type</span></span></th>
<th><span data-ttu-id="1af17-191">FQDN</span><span class="sxs-lookup"><span data-stu-id="1af17-191">FQDN</span></span></th>
<th><span data-ttu-id="1af17-192">FQDN de destino</span><span class="sxs-lookup"><span data-stu-id="1af17-192">Target FQDN</span></span></th>
<th><span data-ttu-id="1af17-193">Puerto</span><span class="sxs-lookup"><span data-stu-id="1af17-193">Port</span></span></th>
<th><span data-ttu-id="1af17-194">Se asigna a/comentarios</span><span class="sxs-lookup"><span data-stu-id="1af17-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1af17-195">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-196">SRV</span><span class="sxs-lookup"><span data-stu-id="1af17-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="1af17-197">_sipinternaltls. _ TCP. contoso. com</span><span class="sxs-lookup"><span data-stu-id="1af17-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1af17-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1af17-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1af17-199">5061</span><span class="sxs-lookup"><span data-stu-id="1af17-199">5061</span></span></p></td>
<td><p><span data-ttu-id="1af17-200">Necesario para que la configuración automática de los clientes de Lync 2013 funcione internamente.</span><span class="sxs-lookup"><span data-stu-id="1af17-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1af17-201">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-202">SRV</span><span class="sxs-lookup"><span data-stu-id="1af17-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="1af17-203">_sipinternaltls. _ TCP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="1af17-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="1af17-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1af17-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="1af17-205">5061</span><span class="sxs-lookup"><span data-stu-id="1af17-205">5061</span></span></p></td>
<td><p><span data-ttu-id="1af17-206">Necesario para que la configuración automática de los clientes de Lync 2013 funcione internamente.</span><span class="sxs-lookup"><span data-stu-id="1af17-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1af17-207">DNS interno</span><span class="sxs-lookup"><span data-stu-id="1af17-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="1af17-208">SRV</span><span class="sxs-lookup"><span data-stu-id="1af17-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="1af17-209">_ntp. _ UDP. contoso. com</span><span class="sxs-lookup"><span data-stu-id="1af17-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1af17-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1af17-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1af17-211">123</span><span class="sxs-lookup"><span data-stu-id="1af17-211">123</span></span></p></td>
<td><p><span data-ttu-id="1af17-212">El origen de protocolo de tiempo de red (NTP) es necesario para los dispositivos que ejecutan Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1af17-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="1af17-213">Internamente, debe apuntar al controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="1af17-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="1af17-214">Si el controlador de dominio no está definido, intentará usar el servidor NTP time.windows.com.</span><span class="sxs-lookup"><span data-stu-id="1af17-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

