---
title: 'Lync Server 2013: requisitos de DNS para el grupo de servidores front-end'
description: 'Lync Server 2013: requisitos de DNS para el grupo de servidores front-end.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfce90eccb8c8dff94d4122c96c4ca68ea9150f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574336"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="efb02-103">Requisitos de DNS para el grupo de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efb02-103">DNS requirements for Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efb02-104">_**Última modificación del tema:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="efb02-104">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="efb02-105">Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o dominio, al menos, como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="efb02-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="efb02-106">Debe configurar los registros del sistema de nombres de dominio (DNS) necesarios antes de publicar la topología en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="efb02-106">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="efb02-107">Además, algunos de los nombres de dominio completos (FQDN) que se usan en la configuración de una implementación de Lync Server 2013 son los FQDN lógicos y no físicos del servidor, por lo que se necesita una configuración DNS adicional antes de la publicación.</span><span class="sxs-lookup"><span data-stu-id="efb02-107">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="efb02-108">Lync Server 2013 no admite dominios con una sola etiqueta.</span><span class="sxs-lookup"><span data-stu-id="efb02-108">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="efb02-109">Por ejemplo, se admitiría un bosque con un dominio raíz denominado <STRONG>contoso.local</STRONG>, pero no un dominio raíz denominado <STRONG>local</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="efb02-109">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="efb02-110">Para obtener más información, consulte el artículo 300684 de Microsoft Knowledge base, "información sobre la configuración de Windows para dominios con nombres DNS de etiqueta única", at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="efb02-110">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="efb02-111">El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="efb02-111">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="efb02-112">De manera predeterminada, el nombre de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="efb02-112">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="efb02-113">Topology Builder usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="efb02-113">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="efb02-114"><STRONG>Use solo caracteres estándar</STRONG> (incluidos A – z, a – z, 0 – 9 y guiones) al asignar FQDN de los servidores que ejecutan Lync Server, servidores perimetrales y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="efb02-114"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="efb02-115">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="efb02-115">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="efb02-116">Los DNS externos y las entidades de certificación (CA) públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (cuando dicho nombre debe asignarse al nombre del sujeto en el certificado).</span><span class="sxs-lookup"><span data-stu-id="efb02-116">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="efb02-117">Antes de trabajar con la topología una vez implementada, asegúrese de que se crean los siguientes registros de DNS y Active Directory (según las necesidades específicas que indiquen):</span><span class="sxs-lookup"><span data-stu-id="efb02-117">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="efb02-118">Cada rol de servidor que existirá en la topología se publica como un objeto de Active Directory (una vez que se une el equipo al dominio).</span><span class="sxs-lookup"><span data-stu-id="efb02-118">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="efb02-119">Existe un registro DNS A para cada uno de los servidores.</span><span class="sxs-lookup"><span data-stu-id="efb02-119">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="efb02-120">Existe un registro SRV de DNS para cada dominio SIP si va a usar el inicio de sesión automático para clientes con el formato \_ sipinternaltls \_ TCP. \<SIP domain\> .</span><span class="sxs-lookup"><span data-stu-id="efb02-120">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="efb02-121">Si va a usar la configuración manual para clientes, este registro no es necesario.</span><span class="sxs-lookup"><span data-stu-id="efb02-121">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="efb02-122">Un registro DNS A para cada URL sencilla configurada, de las que suelen haber cuatro: reunión, marcado, lwa y programador.</span><span class="sxs-lookup"><span data-stu-id="efb02-122">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="efb02-123">Además, existe una dirección URL sencilla de administración que es una dirección URL especial para acceder al panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efb02-123">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="efb02-124">El servidor que ejecuta SQL Server debe unirse al dominio y ser accesible por el equipo desde el que se publica el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="efb02-124">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="efb02-125">La tabla sigue las arquitecturas de referencia presentadas en la sección Planeación.</span><span class="sxs-lookup"><span data-stu-id="efb02-125">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="efb02-126">Para obtener más información, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="efb02-126">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="efb02-127">Registros DNS necesarios para el grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="efb02-127">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efb02-128">Ubicación</span><span class="sxs-lookup"><span data-stu-id="efb02-128">Location</span></span></th>
<th><span data-ttu-id="efb02-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="efb02-129">Type</span></span></th>
<th><span data-ttu-id="efb02-130">FQDN</span><span class="sxs-lookup"><span data-stu-id="efb02-130">FQDN</span></span></th>
<th><span data-ttu-id="efb02-131">Asignado a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="efb02-131">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efb02-132">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-132">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-133">A</span><span class="sxs-lookup"><span data-stu-id="efb02-133">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-134">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="efb02-134">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="efb02-135">Grupo01 (Equilibrio de carga de DNS).</span><span class="sxs-lookup"><span data-stu-id="efb02-135">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="efb02-136">Requiere un registro a de DNS para la dirección IP de cada servidor front-end dentro del grupo de servidores, asignando al FQDN del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="efb02-136">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb02-137">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-137">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-138">A</span><span class="sxs-lookup"><span data-stu-id="efb02-138">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-139">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="efb02-139">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="efb02-140">Grupo01 (IP virtual (VIP) del equilibrador de carga de hardware)</span><span class="sxs-lookup"><span data-stu-id="efb02-140">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb02-141">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-141">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-142">A</span><span class="sxs-lookup"><span data-stu-id="efb02-142">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-143">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="efb02-143">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="efb02-144">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="efb02-144">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="efb02-145">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="efb02-145">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="efb02-146">…</span><span class="sxs-lookup"><span data-stu-id="efb02-146">…</span></span></p></td>
<td><p><span data-ttu-id="efb02-147">Servidor front-end de grupo01 (nodo 1).</span><span class="sxs-lookup"><span data-stu-id="efb02-147">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="efb02-148">Servidor front-end de grupo01 (nodo 2).</span><span class="sxs-lookup"><span data-stu-id="efb02-148">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="efb02-149">Servidor front-end de grupo01 (nodo 3).</span><span class="sxs-lookup"><span data-stu-id="efb02-149">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="efb02-150">…</span><span class="sxs-lookup"><span data-stu-id="efb02-150">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb02-151">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-151">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-152">A</span><span class="sxs-lookup"><span data-stu-id="efb02-152">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-153">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="efb02-153">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="efb02-154">Servidor front-end de grupo01 (nodo 2).</span><span class="sxs-lookup"><span data-stu-id="efb02-154">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb02-155">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-155">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-156">A</span><span class="sxs-lookup"><span data-stu-id="efb02-156">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-157">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="efb02-157">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="efb02-158">Grupo01 (VIP) para el tráfico web cliente-servidor</span><span class="sxs-lookup"><span data-stu-id="efb02-158">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb02-159">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-159">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-160">A</span><span class="sxs-lookup"><span data-stu-id="efb02-160">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-161">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="efb02-161">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="efb02-162">Servidor back-end de grupo01 que ejecuta SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="efb02-162">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb02-163">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-163">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-164">A</span><span class="sxs-lookup"><span data-stu-id="efb02-164">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="efb02-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="efb02-166">Es necesario para Lync Phone Edition o el inicio de sesión automático de los clientes sin los registros SRV de DNS y para la coincidencia estricta de dominios.</span><span class="sxs-lookup"><span data-stu-id="efb02-166">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="efb02-167">No es necesario en todos los casos.</span><span class="sxs-lookup"><span data-stu-id="efb02-167">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb02-168">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-168">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-169">A</span><span class="sxs-lookup"><span data-stu-id="efb02-169">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-170">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="efb02-170">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="efb02-171">Asume un segundo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="efb02-171">Assumes a second SIP domain.</span></span> <span data-ttu-id="efb02-172">Necesario para Lync Phone Edition, el inicio de sesión automático de los clientes sin los registros SRV de DNS y para la coincidencia estricta de dominios.</span><span class="sxs-lookup"><span data-stu-id="efb02-172">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="efb02-173">No es necesario en todos los casos.</span><span class="sxs-lookup"><span data-stu-id="efb02-173">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb02-174">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-174">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-175">A</span><span class="sxs-lookup"><span data-stu-id="efb02-175">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-176">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="efb02-176">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="efb02-177">Dirección URL sencilla para las conferencias de acceso telefónico local publicadas internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="efb02-177">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb02-178">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-178">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-179">A</span><span class="sxs-lookup"><span data-stu-id="efb02-179">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-180">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="efb02-180">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="efb02-181">Dirección URL sencilla para conferencias publicadas internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="efb02-181">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb02-182">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-182">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-183">A</span><span class="sxs-lookup"><span data-stu-id="efb02-183">A</span></span></p></td>
<td><p><span data-ttu-id="efb02-184">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="efb02-184">admin.contoso.com</span></span></p>
<p><span data-ttu-id="efb02-185">administrar</span><span class="sxs-lookup"><span data-stu-id="efb02-185">admin</span></span></p></td>
<td><p><span data-ttu-id="efb02-186">Registro opcional, dirección URL sencilla para Lync Server 2013 panel de control publicado internamente: el servidor front-end (o director, si está instalado) responde a consultas de URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="efb02-186">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="efb02-187">Se recomienda usar solo el nombre de host (sin nombre de dominio).</span><span class="sxs-lookup"><span data-stu-id="efb02-187">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="efb02-188">VIP = dirección IP virtual para el equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="efb02-188">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="efb02-189">Registros SRV de DNS para el grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="efb02-189">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="efb02-190">Ubicación</span><span class="sxs-lookup"><span data-stu-id="efb02-190">Location</span></span></th>
<th><span data-ttu-id="efb02-191">Tipo</span><span class="sxs-lookup"><span data-stu-id="efb02-191">Type</span></span></th>
<th><span data-ttu-id="efb02-192">FQDN</span><span class="sxs-lookup"><span data-stu-id="efb02-192">FQDN</span></span></th>
<th><span data-ttu-id="efb02-193">FQDN de destino</span><span class="sxs-lookup"><span data-stu-id="efb02-193">Target FQDN</span></span></th>
<th><span data-ttu-id="efb02-194">Puerto</span><span class="sxs-lookup"><span data-stu-id="efb02-194">Port</span></span></th>
<th><span data-ttu-id="efb02-195">Asignado a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="efb02-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efb02-196">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-196">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-197">SRV</span><span class="sxs-lookup"><span data-stu-id="efb02-197">SRV</span></span></p></td>
<td><p><span data-ttu-id="efb02-198">_sipinternaltls _sipinternaltls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="efb02-198">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="efb02-199">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="efb02-199">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="efb02-200">5061</span><span class="sxs-lookup"><span data-stu-id="efb02-200">5061</span></span></p></td>
<td><p><span data-ttu-id="efb02-201">Necesario para la configuración automática de clientes de Lync 2013 para que funcionen internamente.</span><span class="sxs-lookup"><span data-stu-id="efb02-201">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb02-202">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-202">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-203">SRV</span><span class="sxs-lookup"><span data-stu-id="efb02-203">SRV</span></span></p></td>
<td><p><span data-ttu-id="efb02-204">_sipinternaltls _sipinternaltls._tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="efb02-204">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="efb02-205">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="efb02-205">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="efb02-206">5061</span><span class="sxs-lookup"><span data-stu-id="efb02-206">5061</span></span></p></td>
<td><p><span data-ttu-id="efb02-207">Necesario para la configuración automática de clientes de Lync 2013 para que funcionen internamente.</span><span class="sxs-lookup"><span data-stu-id="efb02-207">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb02-208">DNS interno</span><span class="sxs-lookup"><span data-stu-id="efb02-208">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="efb02-209">SRV</span><span class="sxs-lookup"><span data-stu-id="efb02-209">SRV</span></span></p></td>
<td><p><span data-ttu-id="efb02-210">_ntp _ntp._udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="efb02-210">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="efb02-211">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="efb02-211">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="efb02-212">123</span><span class="sxs-lookup"><span data-stu-id="efb02-212">123</span></span></p></td>
<td><p><span data-ttu-id="efb02-213">El origen del Protocolo de tiempo de la red (NTP) es necesario para los dispositivos que ejecutan Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="efb02-213">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="efb02-214">Internamente, esto deberá apuntar al controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="efb02-214">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="efb02-215">Si el controlador de dominio no se ha definido, intentará usar el servidor NTP time.windows.com</span><span class="sxs-lookup"><span data-stu-id="efb02-215">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

