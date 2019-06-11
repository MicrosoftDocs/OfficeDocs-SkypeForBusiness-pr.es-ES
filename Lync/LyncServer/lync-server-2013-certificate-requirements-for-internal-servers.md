---
title: 'Lync Server 2013: Requisitos de certificado para Servidores internos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a3f1eb54321c6cac7548d282bd3cea31c3f24a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="46805-102">Requisitos de certificado para Servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46805-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46805-103">_**Última modificación del tema:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="46805-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="46805-104">Los servidores internos que ejecutan Lync Server y que requieren certificados incluyen el servidor Standard Edition, el servidor front-end Enterprise Edition, el servidor de mediación y el director.</span><span class="sxs-lookup"><span data-stu-id="46805-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="46805-105">En la tabla siguiente se muestran los requisitos de certificados para estos servidores.</span><span class="sxs-lookup"><span data-stu-id="46805-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="46805-106">Puede usar el Asistente para certificados de Lync Server para solicitar estos certificados.</span><span class="sxs-lookup"><span data-stu-id="46805-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="46805-107">Los certificados comodín son compatibles con los nombres alternativos de asunto asociados con las direcciones URL simples del grupo de servidores front-end, del servidor front-end o del director.</span><span class="sxs-lookup"><span data-stu-id="46805-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="46805-108">Para obtener más información acerca de la compatibilidad con certificados comodín, consulte <A href="lync-server-2013-wildcard-certificate-support.md">compatibilidad de certificados comodín en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="46805-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="46805-109">Aunque se recomienda una entidad de certificación (CA) interna de empresa para los servidores internos, también puede usar una CA pública.</span><span class="sxs-lookup"><span data-stu-id="46805-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="46805-110">Para obtener una lista de las entidades emisoras de certificados públicas que proporcionan certificados que cumplen con los requisitos específicos para los certificados de comunicaciones unificadas y se han asociado con Microsoft para garantizar que funcionan con el Asistente para certificados de Lync Server, consulte el artículo Microsoft Knowledge Base 929395, "socios de certificados de comunicaciones unificadas para Exchange Server y Communications Server" [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)en.</span><span class="sxs-lookup"><span data-stu-id="46805-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="46805-111">La comunicación con otras aplicaciones y servidores, como Exchange 2013, requiere un certificado que sea compatible con otras aplicaciones y productos.</span><span class="sxs-lookup"><span data-stu-id="46805-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="46805-112">Para la versión 2013, Lync Server 2013 y otros productos de Microsoft Server, incluidos Exchange 2013 y SharePoint Server, admiten el protocolo de autorización abierta (OAuth) para la autenticación y la autorización de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="46805-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="46805-113">Para obtener más información, vea [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="46805-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="46805-114">Para las conexiones de clientes que ejecutan el sistema operativo Windows 7, el sistema operativo Windows Server 2008, el sistema operativo Windows Server 2008 R2, el sistema operativo Windows Vista y Microsoft Lync Phone Edition, Lync Server 2013 incluye compatibilidad con (pero no requerir) certificados firmados con la función de hash criptográfica SHA-256.</span><span class="sxs-lookup"><span data-stu-id="46805-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="46805-115">Para admitir el acceso externo mediante SHA-256, un certificado externo es emitido por una entidad de certificación pública con SHA-256.</span><span class="sxs-lookup"><span data-stu-id="46805-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="46805-116">En las tablas siguientes se muestran los requisitos de los certificados por función del servidor para los servidores front-end y los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="46805-116">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="46805-117">Todos son certificados de servidor web estándar, clave privada, no exportable.</span><span class="sxs-lookup"><span data-stu-id="46805-117">All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="46805-118">Tenga en cuenta que el uso mejorado de clave (EKU) del servidor se configura automáticamente cuando usa el Asistente para certificados para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="46805-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46805-119">Cada nombre descriptivo de certificado debe ser único en el almacén de equipos.</span><span class="sxs-lookup"><span data-stu-id="46805-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="46805-120">Si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, tendrá que agregarlos en el nombre alternativo de asunto del certificado.</span><span class="sxs-lookup"><span data-stu-id="46805-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="46805-121">Certificados para un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="46805-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="46805-122">Certificado</span><span class="sxs-lookup"><span data-stu-id="46805-122">Certificate</span></span></th>
<th><span data-ttu-id="46805-123">Nombre del asunto/nombre común</span><span class="sxs-lookup"><span data-stu-id="46805-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="46805-124">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="46805-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="46805-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46805-125">Example</span></span></th>
<th><span data-ttu-id="46805-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46805-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46805-127">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="46805-127">Default</span></span></p></td>
<td><p><span data-ttu-id="46805-128">Nombre de dominio completo (FQDN) del grupo</span><span class="sxs-lookup"><span data-stu-id="46805-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="46805-129">FQDN del grupo y el FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="46805-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="46805-130">Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.</span><span class="sxs-lookup"><span data-stu-id="46805-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="46805-131">Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).</span><span class="sxs-lookup"><span data-stu-id="46805-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="46805-132">SN=se01.contoso.com; SAN=se01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="46805-133">Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="46805-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="46805-134">En el servidor Standard Edition, el FQDN del servidor es el mismo que el FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="46805-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="46805-135">El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.</span><span class="sxs-lookup"><span data-stu-id="46805-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="46805-136">También puede usar este certificado para la autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="46805-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46805-137">Web interno</span><span class="sxs-lookup"><span data-stu-id="46805-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="46805-138">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="46805-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="46805-139">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="46805-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="46805-140">FQDN web interno (que es igual que el FQDN del servidor)</span><span class="sxs-lookup"><span data-stu-id="46805-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="46805-141">URL sencilla de reunión</span><span class="sxs-lookup"><span data-stu-id="46805-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="46805-142">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="46805-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-143">URL sencilla de administración</span><span class="sxs-lookup"><span data-stu-id="46805-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-144">O bien, una entrada comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="46805-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="46805-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="46805-146">Con un certificado de comodín:</span><span class="sxs-lookup"><span data-stu-id="46805-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="46805-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="46805-148">No puede invalidar el FQDN de la web interna en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="46805-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="46805-149">Si tiene varias direcciones URL simples, debe incluirlas como nombres alternativos de asunto.</span><span class="sxs-lookup"><span data-stu-id="46805-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="46805-150">Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="46805-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46805-151">Web externo</span><span class="sxs-lookup"><span data-stu-id="46805-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="46805-152">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="46805-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="46805-153">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="46805-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="46805-154">FQDN web externo</span><span class="sxs-lookup"><span data-stu-id="46805-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="46805-155">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="46805-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-156">Direcciones URL sencillas de reunión por dominio SIP</span><span class="sxs-lookup"><span data-stu-id="46805-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="46805-157">O bien, una entrada comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="46805-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="46805-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="46805-159">Con un certificado de comodín:</span><span class="sxs-lookup"><span data-stu-id="46805-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="46805-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="46805-161">Si tiene varias direcciones URL simples, debe incluirlas como nombres alternativos de asunto.</span><span class="sxs-lookup"><span data-stu-id="46805-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="46805-162">Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="46805-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="46805-163">Certificados para el servidor front-end en un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="46805-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="46805-164">Certificado</span><span class="sxs-lookup"><span data-stu-id="46805-164">Certificate</span></span></th>
<th><span data-ttu-id="46805-165">Nombre del asunto/nombre común</span><span class="sxs-lookup"><span data-stu-id="46805-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="46805-166">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="46805-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="46805-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46805-167">Example</span></span></th>
<th><span data-ttu-id="46805-168">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46805-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46805-169">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="46805-169">Default</span></span></p></td>
<td><p><span data-ttu-id="46805-170">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="46805-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="46805-171">FQDN del grupo y FQDN del servidor.</span><span class="sxs-lookup"><span data-stu-id="46805-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="46805-172">Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.</span><span class="sxs-lookup"><span data-stu-id="46805-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="46805-173">Si este grupo es el servidor de inicio de sesión automático para clientes y se requiere coincidencia de DNS estricta en la Directiva de grupo, también necesitarás entradas para SIP. sipdomain (para cada dominio SIP que tengas).</span><span class="sxs-lookup"><span data-stu-id="46805-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="46805-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com </span><span class="sxs-lookup"><span data-stu-id="46805-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="46805-175">Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="46805-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="46805-176">El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.</span><span class="sxs-lookup"><span data-stu-id="46805-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="46805-177">También puede usar este certificado para la autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="46805-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46805-178">Interno de la web</span><span class="sxs-lookup"><span data-stu-id="46805-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="46805-179">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="46805-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="46805-180">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="46805-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="46805-181">FQDN web interno (que NO es el mismo que el FQDN del servidor)</span><span class="sxs-lookup"><span data-stu-id="46805-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="46805-182">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="46805-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="46805-183">FQDN del grupo de Lync</span><span class="sxs-lookup"><span data-stu-id="46805-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="46805-184">URL sencilla de reunión</span><span class="sxs-lookup"><span data-stu-id="46805-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="46805-185">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="46805-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-186">URL sencilla de administración</span><span class="sxs-lookup"><span data-stu-id="46805-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-187">O bien, una entrada comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="46805-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="46805-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="46805-189">Con un certificado de comodín:</span><span class="sxs-lookup"><span data-stu-id="46805-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="46805-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="46805-191">Si tiene varias direcciones URL simples, debe incluirlas como nombres alternativos de asunto.</span><span class="sxs-lookup"><span data-stu-id="46805-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="46805-192">Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="46805-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46805-193">Web externo</span><span class="sxs-lookup"><span data-stu-id="46805-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="46805-194">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="46805-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="46805-195">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="46805-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="46805-196">FQDN web externo</span><span class="sxs-lookup"><span data-stu-id="46805-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="46805-197">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="46805-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-198">URL sencilla de administración</span><span class="sxs-lookup"><span data-stu-id="46805-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-199">O bien, una entrada comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="46805-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="46805-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="46805-201">Con un certificado de comodín:</span><span class="sxs-lookup"><span data-stu-id="46805-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="46805-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="46805-203">Si tiene varias direcciones URL simples, debe incluirlas como nombres alternativos de asunto.</span><span class="sxs-lookup"><span data-stu-id="46805-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="46805-204">Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="46805-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="46805-205">Certificados para Director</span><span class="sxs-lookup"><span data-stu-id="46805-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46805-206">Certificado</span><span class="sxs-lookup"><span data-stu-id="46805-206">Certificate</span></span></th>
<th><span data-ttu-id="46805-207">Nombre del asunto/nombre común</span><span class="sxs-lookup"><span data-stu-id="46805-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="46805-208">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="46805-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="46805-209">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46805-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46805-210">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="46805-210">Default</span></span></p></td>
<td><p><span data-ttu-id="46805-211">FQDN del grupo de directores</span><span class="sxs-lookup"><span data-stu-id="46805-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="46805-212">FQDN del Director, FQDN del grupo de directores</span><span class="sxs-lookup"><span data-stu-id="46805-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="46805-213">Si este grupo es el servidor de inicio de sesión automático para clientes y se requiere coincidencia de DNS estricta en la Directiva de grupo, también necesitarás entradas para SIP. sipdomain (para cada dominio SIP que tengas).</span><span class="sxs-lookup"><span data-stu-id="46805-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="46805-214">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="46805-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="46805-215">Si este grupo de directores es el servidor de inicio de sesión automático para clientes y se requiere una coincidencia de DNS estricta en la Directiva de grupo, también necesita SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="46805-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46805-216">Interno de la web</span><span class="sxs-lookup"><span data-stu-id="46805-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="46805-217">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="46805-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="46805-218">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="46805-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="46805-219">FQDN web interno (que es igual que el FQDN del servidor)</span><span class="sxs-lookup"><span data-stu-id="46805-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="46805-220">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="46805-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="46805-221">FQDN del grupo de Lync</span><span class="sxs-lookup"><span data-stu-id="46805-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="46805-222">URL sencilla de reunión</span><span class="sxs-lookup"><span data-stu-id="46805-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="46805-223">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="46805-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-224">URL sencilla de administración</span><span class="sxs-lookup"><span data-stu-id="46805-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-225">O bien, una entrada comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="46805-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="46805-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="46805-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46805-228">Web externo</span><span class="sxs-lookup"><span data-stu-id="46805-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="46805-229">FQDN del servidor</span><span class="sxs-lookup"><span data-stu-id="46805-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="46805-230">Cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="46805-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="46805-231">FQDN web externo</span><span class="sxs-lookup"><span data-stu-id="46805-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="46805-232">URL sencilla de marcado</span><span class="sxs-lookup"><span data-stu-id="46805-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-233">URL sencilla de administración</span><span class="sxs-lookup"><span data-stu-id="46805-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="46805-234">O bien, una entrada comodín para las direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="46805-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="46805-235">El FQDN de la web externa del Director debe ser diferente del de la aplicación front end o del servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="46805-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="46805-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="46805-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="46805-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46805-238">Si tiene un grupo de servidores de mediación independiente, cada uno de los servidores de mediación de cada uno necesita los certificados enumerados en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="46805-238">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table.</span></span> <span data-ttu-id="46805-239">Si Collocate el servidor de mediación con los servidores front-end, los certificados que figuran en la tabla "certificados para el servidor front-end en la agrupación front end" anteriormente en este tema son suficientes.</span><span class="sxs-lookup"><span data-stu-id="46805-239">If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="46805-240">Certificados para el servidor de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="46805-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46805-241">Certificado</span><span class="sxs-lookup"><span data-stu-id="46805-241">Certificate</span></span></th>
<th><span data-ttu-id="46805-242">Nombre del asunto/nombre común</span><span class="sxs-lookup"><span data-stu-id="46805-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="46805-243">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="46805-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="46805-244">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46805-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46805-245">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="46805-245">Default</span></span></p></td>
<td><p><span data-ttu-id="46805-246">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="46805-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="46805-247">FQDN del grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="46805-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="46805-248">FQDN del servidor miembro del grupo</span><span class="sxs-lookup"><span data-stu-id="46805-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="46805-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="46805-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="46805-250">Certificados para la aplicación de rama superviviente</span><span class="sxs-lookup"><span data-stu-id="46805-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46805-251">Certificado</span><span class="sxs-lookup"><span data-stu-id="46805-251">Certificate</span></span></th>
<th><span data-ttu-id="46805-252">Nombre del asunto/nombre común</span><span class="sxs-lookup"><span data-stu-id="46805-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="46805-253">Nombre alternativo de sujeto</span><span class="sxs-lookup"><span data-stu-id="46805-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="46805-254">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46805-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46805-255">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="46805-255">Default</span></span></p></td>
<td><p><span data-ttu-id="46805-256">FQDN de la aplicación</span><span class="sxs-lookup"><span data-stu-id="46805-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="46805-257">SIP. &lt;sipdomain&gt; (necesita una entrada por cada dominio SIP)</span><span class="sxs-lookup"><span data-stu-id="46805-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="46805-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="46805-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="46805-259">Vea también</span><span class="sxs-lookup"><span data-stu-id="46805-259">See Also</span></span>


[<span data-ttu-id="46805-260">Compatibilidad de certificado de comodín en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46805-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

