---
title: 'Lync Server 2013: requisitos de certificado para servidores internos'
description: 'Lync Server 2013: requisitos de certificado para servidores internos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1a627dd762c849b848087a96e00e19d320ef01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575216"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="6b888-103">Requisitos de certificado para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b888-103">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b888-104">_**Última modificación del tema:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="6b888-104">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="6b888-105">Los servidores internos que ejecutan Lync Server y que requieren certificados incluyen el servidor Standard Edition, el servidor front-end Enterprise Edition, el servidor de mediación y el director.</span><span class="sxs-lookup"><span data-stu-id="6b888-105">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="6b888-106">En la siguiente tabla se muestran los requisitos de certificado para estos servidores.</span><span class="sxs-lookup"><span data-stu-id="6b888-106">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="6b888-107">Puede usar el Asistente para certificados de Lync Server para solicitar estos certificados.</span><span class="sxs-lookup"><span data-stu-id="6b888-107">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="6b888-108">Los certificados comodín son compatibles con los nombres alternativos de sujeto asociados con las direcciones URL simples en el grupo de servidores front-end, el servidor front-end o el director.</span><span class="sxs-lookup"><span data-stu-id="6b888-108">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="6b888-109">Para obtener más información sobre la compatibilidad con certificados comodín, consulte <A href="lync-server-2013-wildcard-certificate-support.md">compatibilidad con certificados comodín en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6b888-109">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6b888-110">Aunque para los servidores internos se recomienda una entidad de certificación (CA) empresarial interna, también puede usar una pública.</span><span class="sxs-lookup"><span data-stu-id="6b888-110">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="6b888-111">Para obtener una lista de las entidades de certificación públicas que proporcionan certificados que cumplen los requisitos específicos para los certificados de comunicaciones unificadas (UC) y que se han asociado con Microsoft para garantizar que funcionan con el Asistente para certificados de Lync Server, vea el artículo 929395 de Microsoft Knowledge base, "asociados de certificados de comunicaciones unificadas para Exchange Server y para Communications Server" en [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="6b888-111">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="6b888-112">La comunicación con otras aplicaciones y servidores, como Exchange 2013, requiere un certificado que sea compatible con las demás aplicaciones y productos.</span><span class="sxs-lookup"><span data-stu-id="6b888-112">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="6b888-113">Para la versión 2013, Lync Server 2013 y otros productos de servidor de Microsoft, incluidos Exchange 2013 y SharePoint Server, admiten el protocolo Open Authorization (OAuth) para la autenticación y autorización de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="6b888-113">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="6b888-114">Para obtener más información, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación sobre implementación o sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="6b888-114">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="6b888-115">Para las conexiones de clientes que ejecutan el sistema operativo Windows 7, el sistema operativo Windows Server 2008, el sistema operativo Windows Server 2008 R2, el sistema operativo Windows Vista y Microsoft Lync Phone Edition, Lync Server 2013 incluye compatibilidad con certificados (pero no obligatorios) firmados con la función de hash criptográfica SHA-256.</span><span class="sxs-lookup"><span data-stu-id="6b888-115">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="6b888-116">Para permitir el acceso externo mediante SHA-256, el certificado externo lo emite una CA pública que usa SHA-256.</span><span class="sxs-lookup"><span data-stu-id="6b888-116">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="6b888-p106">En las tablas siguientes, se muestran los requisitos de certificado por rol de servidor para los grupos de servidores front-end y los servidores Standard Edition. Todos ellos son certificados de servidor web estándar, con clave privada y no exportables.</span><span class="sxs-lookup"><span data-stu-id="6b888-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="6b888-119">Tenga en cuenta que el uso mejorado de clave (EKU) del servidor se configura automáticamente al usar el asistente para certificados para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="6b888-119">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b888-120">Cada nombre descriptivo del certificado debe ser único en el almacén del equipo.</span><span class="sxs-lookup"><span data-stu-id="6b888-120">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6b888-121">Si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, tendrá que agregarlos en el nombre alternativo de sujeto del certificado.</span><span class="sxs-lookup"><span data-stu-id="6b888-121">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="6b888-122">Certificados para el servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6b888-122">Certificates for Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b888-123">Certificado</span><span class="sxs-lookup"><span data-stu-id="6b888-123">Certificate</span></span></th>
<th><span data-ttu-id="6b888-124">Nombre de sujeto/nombre común</span><span class="sxs-lookup"><span data-stu-id="6b888-124">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6b888-125">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="6b888-125">Subject alternative name</span></span></th>
<th><span data-ttu-id="6b888-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b888-126">Example</span></span></th>
<th><span data-ttu-id="6b888-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b888-127">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b888-128">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="6b888-128">Default</span></span></p></td>
<td><p><span data-ttu-id="6b888-129">Nombre de dominio completo (FQDN) del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6b888-129">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="6b888-130">FQDN del grupo de servidores y el FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="6b888-130">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="6b888-131">Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.</span><span class="sxs-lookup"><span data-stu-id="6b888-131">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="6b888-132">Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</span><span class="sxs-lookup"><span data-stu-id="6b888-132">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="6b888-133">SN = SE01. contoso. com; SAN = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-133">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="6b888-134">Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6b888-134">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="6b888-135">En el servidor Standard Edition, el FQDN del servidor es igual que el FQDN del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="6b888-135">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="6b888-136">El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.</span><span class="sxs-lookup"><span data-stu-id="6b888-136">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="6b888-137">También puede usar este certificado para la autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="6b888-137">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b888-138">Web interno</span><span class="sxs-lookup"><span data-stu-id="6b888-138">Web internal</span></span></p></td>
<td><p><span data-ttu-id="6b888-139">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="6b888-139">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6b888-140">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="6b888-140">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b888-141">FQDN web interno (que es igual que el FQDN del servidor)</span><span class="sxs-lookup"><span data-stu-id="6b888-141">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="6b888-142">URL sencillas de reunión</span><span class="sxs-lookup"><span data-stu-id="6b888-142">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="6b888-143">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="6b888-143">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-144">URL sencilla de administración</span><span class="sxs-lookup"><span data-stu-id="6b888-144">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-145">O una entrada de comodín para las direcciones URL sencillas</span><span class="sxs-lookup"><span data-stu-id="6b888-145">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b888-146">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-146">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="6b888-147">Con un certificado de comodín:</span><span class="sxs-lookup"><span data-stu-id="6b888-147">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6b888-148">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-148">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6b888-149">No puede invalidar el FQDN de la web interna en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="6b888-149">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="6b888-150">Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.</span><span class="sxs-lookup"><span data-stu-id="6b888-150">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6b888-151">Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="6b888-151">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b888-152">Web externo</span><span class="sxs-lookup"><span data-stu-id="6b888-152">Web external</span></span></p></td>
<td><p><span data-ttu-id="6b888-153">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="6b888-153">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6b888-154">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="6b888-154">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b888-155">FQDN web externo</span><span class="sxs-lookup"><span data-stu-id="6b888-155">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="6b888-156">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="6b888-156">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-157">Cumplir direcciones URL sencillas por dominio SIP</span><span class="sxs-lookup"><span data-stu-id="6b888-157">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="6b888-158">O una entrada de comodín para las direcciones URL sencillas</span><span class="sxs-lookup"><span data-stu-id="6b888-158">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b888-159">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-159">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6b888-160">Con un certificado de comodín:</span><span class="sxs-lookup"><span data-stu-id="6b888-160">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6b888-161">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-161">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6b888-162">Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.</span><span class="sxs-lookup"><span data-stu-id="6b888-162">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6b888-163">Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="6b888-163">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="6b888-164">Certificados para un servidor front-end en un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="6b888-164">Certificates for Front End Server in a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b888-165">Certificado</span><span class="sxs-lookup"><span data-stu-id="6b888-165">Certificate</span></span></th>
<th><span data-ttu-id="6b888-166">Nombre de sujeto/nombre común</span><span class="sxs-lookup"><span data-stu-id="6b888-166">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6b888-167">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="6b888-167">Subject alternative name</span></span></th>
<th><span data-ttu-id="6b888-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b888-168">Example</span></span></th>
<th><span data-ttu-id="6b888-169">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b888-169">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b888-170">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="6b888-170">Default</span></span></p></td>
<td><p><span data-ttu-id="6b888-171">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6b888-171">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6b888-172">FQDN del grupo de servidores y FQDN del servidor.</span><span class="sxs-lookup"><span data-stu-id="6b888-172">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="6b888-173">Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.</span><span class="sxs-lookup"><span data-stu-id="6b888-173">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="6b888-174">Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</span><span class="sxs-lookup"><span data-stu-id="6b888-174">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="6b888-175">SN = eepool. contoso. com; SAN = eepool. contoso. com; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-175">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="6b888-176">Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6b888-176">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="6b888-177">El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.</span><span class="sxs-lookup"><span data-stu-id="6b888-177">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="6b888-178">También puede usar este certificado para la autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="6b888-178">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b888-179">Web interno</span><span class="sxs-lookup"><span data-stu-id="6b888-179">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="6b888-180">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6b888-180">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6b888-181">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="6b888-181">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b888-182">FQDN Web interno (que no es el mismo que el FQDN del servidor)</span><span class="sxs-lookup"><span data-stu-id="6b888-182">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="6b888-183">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="6b888-183">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="6b888-184">FQDN del grupo de Lync</span><span class="sxs-lookup"><span data-stu-id="6b888-184">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="6b888-185">URL sencillas de reunión</span><span class="sxs-lookup"><span data-stu-id="6b888-185">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="6b888-186">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="6b888-186">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-187">URL sencilla de administración</span><span class="sxs-lookup"><span data-stu-id="6b888-187">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-188">O una entrada de comodín para las direcciones URL sencillas</span><span class="sxs-lookup"><span data-stu-id="6b888-188">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b888-189">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-189">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="6b888-190">Con un certificado de comodín:</span><span class="sxs-lookup"><span data-stu-id="6b888-190">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6b888-191">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-191">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6b888-192">Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.</span><span class="sxs-lookup"><span data-stu-id="6b888-192">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6b888-193">Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="6b888-193">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b888-194">Web externo</span><span class="sxs-lookup"><span data-stu-id="6b888-194">Web external</span></span></p></td>
<td><p><span data-ttu-id="6b888-195">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6b888-195">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6b888-196">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="6b888-196">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b888-197">FQDN web externo</span><span class="sxs-lookup"><span data-stu-id="6b888-197">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="6b888-198">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="6b888-198">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-199">URL sencilla de administración</span><span class="sxs-lookup"><span data-stu-id="6b888-199">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-200">O una entrada de comodín para las direcciones URL sencillas</span><span class="sxs-lookup"><span data-stu-id="6b888-200">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b888-201">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-201">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6b888-202">Con un certificado de comodín:</span><span class="sxs-lookup"><span data-stu-id="6b888-202">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="6b888-203">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-203">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6b888-204">Si dispone de varias URL simples de reunión, deberá incluirlas todas como nombres alternativos de sujeto.</span><span class="sxs-lookup"><span data-stu-id="6b888-204">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="6b888-205">Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="6b888-205">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="6b888-206">Certificados para el director</span><span class="sxs-lookup"><span data-stu-id="6b888-206">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b888-207">Certificado</span><span class="sxs-lookup"><span data-stu-id="6b888-207">Certificate</span></span></th>
<th><span data-ttu-id="6b888-208">Nombre de sujeto/nombre común</span><span class="sxs-lookup"><span data-stu-id="6b888-208">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6b888-209">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="6b888-209">Subject alternative name</span></span></th>
<th><span data-ttu-id="6b888-210">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b888-210">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b888-211">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="6b888-211">Default</span></span></p></td>
<td><p><span data-ttu-id="6b888-212">FQDN del grupo de servidores del director</span><span class="sxs-lookup"><span data-stu-id="6b888-212">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="6b888-213">FQDN del director, FQDN del grupo de servidores del director</span><span class="sxs-lookup"><span data-stu-id="6b888-213">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="6b888-214">Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</span><span class="sxs-lookup"><span data-stu-id="6b888-214">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="6b888-215">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-215">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="6b888-216">Si este grupo de servidores del director es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6b888-216">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b888-217">Web interno</span><span class="sxs-lookup"><span data-stu-id="6b888-217">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="6b888-218">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="6b888-218">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6b888-219">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="6b888-219">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b888-220">FQDN web interno (que es igual que el FQDN del servidor)</span><span class="sxs-lookup"><span data-stu-id="6b888-220">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="6b888-221">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="6b888-221">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="6b888-222">FQDN del grupo de Lync</span><span class="sxs-lookup"><span data-stu-id="6b888-222">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="6b888-223">URL sencillas de reunión</span><span class="sxs-lookup"><span data-stu-id="6b888-223">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="6b888-224">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="6b888-224">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-225">URL sencilla de administración</span><span class="sxs-lookup"><span data-stu-id="6b888-225">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-226">O una entrada de comodín para las direcciones URL sencillas</span><span class="sxs-lookup"><span data-stu-id="6b888-226">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b888-227">SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-227">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="6b888-228">SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-228">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b888-229">Web externo</span><span class="sxs-lookup"><span data-stu-id="6b888-229">Web external</span></span></p></td>
<td><p><span data-ttu-id="6b888-230">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="6b888-230">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="6b888-231">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="6b888-231">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b888-232">FQDN web externo</span><span class="sxs-lookup"><span data-stu-id="6b888-232">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="6b888-233">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="6b888-233">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-234">URL sencilla de administración</span><span class="sxs-lookup"><span data-stu-id="6b888-234">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="6b888-235">O una entrada de comodín para las direcciones URL sencillas</span><span class="sxs-lookup"><span data-stu-id="6b888-235">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b888-236">El FQDN Web externo del Director debe ser diferente del grupo de servidores front-end o del servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6b888-236">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="6b888-237">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="6b888-238">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="6b888-238">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6b888-p107">Si tiene un grupo de servidores de mediación independientes, cada uno de los servidores de mediación que incluya necesitará los certificados listados en la siguiente tabla. Si combina el servidor de mediación con los servidores front-end, bastará con los certificados enumerados anteriormente en la tabla "Certificados para un servidor front-end en un grupo de servidores front-end" de este tema.</span><span class="sxs-lookup"><span data-stu-id="6b888-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="6b888-241">Certificados para un servidor de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="6b888-241">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b888-242">Certificado</span><span class="sxs-lookup"><span data-stu-id="6b888-242">Certificate</span></span></th>
<th><span data-ttu-id="6b888-243">Nombre de sujeto/nombre común</span><span class="sxs-lookup"><span data-stu-id="6b888-243">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6b888-244">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="6b888-244">Subject alternative name</span></span></th>
<th><span data-ttu-id="6b888-245">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b888-245">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b888-246">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="6b888-246">Default</span></span></p></td>
<td><p><span data-ttu-id="6b888-247">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6b888-247">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="6b888-248">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6b888-248">FQDN of the pool</span></span></p>
<p><span data-ttu-id="6b888-249">FQDN del servidor miembro del grupo</span><span class="sxs-lookup"><span data-stu-id="6b888-249">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="6b888-250">SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="6b888-250">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="6b888-251">Certificados para una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="6b888-251">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b888-252">Certificado</span><span class="sxs-lookup"><span data-stu-id="6b888-252">Certificate</span></span></th>
<th><span data-ttu-id="6b888-253">Nombre de sujeto/nombre común</span><span class="sxs-lookup"><span data-stu-id="6b888-253">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="6b888-254">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="6b888-254">Subject alternative name</span></span></th>
<th><span data-ttu-id="6b888-255">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b888-255">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b888-256">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="6b888-256">Default</span></span></p></td>
<td><p><span data-ttu-id="6b888-257">FQDN de la aplicación</span><span class="sxs-lookup"><span data-stu-id="6b888-257">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="6b888-258">SIP. &lt; sipdomain &gt; (necesita una entrada por dominio SIP)</span><span class="sxs-lookup"><span data-stu-id="6b888-258">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="6b888-259">SN = sba01. contoso. net; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="6b888-259">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="6b888-260">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b888-260">See Also</span></span>


[<span data-ttu-id="6b888-261">Compatibilidad con certificados comodín en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b888-261">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

