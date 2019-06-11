---
title: 'Lync Server 2013: requisitos de DNS para el inicio de sesión automático de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afd8ac315222a5582bde9802c22ab7b4911ddfe3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="75b21-102">Requisitos de DNS para el inicio de sesión automático de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75b21-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75b21-103">_**Última modificación del tema:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="75b21-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="75b21-104">En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para el inicio de sesión automático de los clientes.</span><span class="sxs-lookup"><span data-stu-id="75b21-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="75b21-105">Cuando se implementan servidores Standard Edition o grupos de servidores front-end, se pueden configurar los clientes para que usen la detección automática para iniciar sesión en el servidor Standard Edition o en el grupo de servidores front-end adecuado.</span><span class="sxs-lookup"><span data-stu-id="75b21-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="75b21-106">Si tiene previsto exigir que sus clientes se conecten manualmente a Lync Server 2013, puede omitir este tema.</span><span class="sxs-lookup"><span data-stu-id="75b21-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="75b21-107">Para admitir el inicio de sesión automático de los clientes, necesita:</span><span class="sxs-lookup"><span data-stu-id="75b21-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="75b21-p102">Designar un único servidor o grupo de servidores para distribuir y autenticar las solicitudes de inicio de sesión de los clientes. Puede ser uno de los servidores o grupos de servidores existentes en la organización que hospede usuarios, o bien, puede designar un servidor o grupo de servidores dedicado para este fin que no hospede usuarios. Para lograr una alta disponibilidad, recomendamos designar un grupo de servidores front-end para esta función.</span><span class="sxs-lookup"><span data-stu-id="75b21-p102">Designate a single server or pool to distribute and authenticate client sign-in requests. This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users. For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="75b21-111">Crear un registro SRV de DNS interno para admitir el inicio de sesión automático de los clientes para este servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="75b21-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75b21-p103">En los siguientes requisitos de registro, el dominio SIP hace referencia a la parte correspondiente al host de los URI de SIP asignados a los usuarios. Por ejemplo, si los URI de SIP tienen el formato \*@contoso.com, contoso.com es el dominio SIP. El dominio SIP suele ser distinto del dominio de Active Directory interno. Una organización también puede admitir varios dominios SIP.</span><span class="sxs-lookup"><span data-stu-id="75b21-p103">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users. For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain. The SIP domain is often different from the internal Active Directory domain. An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="75b21-116">Para habilitar la configuración automática para sus clientes, debe crear un registro SRV de DNS interno que asigne uno de los siguientes registros al nombre de dominio completo (FQDN) del grupo de servidores front-end o el servidor Standard Edition que distribuye las solicitudes de inicio de sesión de Lync. cliente</span><span class="sxs-lookup"><span data-stu-id="75b21-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="75b21-117">\_sipinternaltls. \_TCP. \<dominio\> : para conexiones TLS internas</span><span class="sxs-lookup"><span data-stu-id="75b21-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="75b21-118">Solo tiene que crear un único registro SRV para el grupo de servidores front-end o el servidor Standard Edition o que distribuirá solicitudes de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="75b21-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="75b21-119">En la tabla siguiente se muestran algunos registros de ejemplo necesarios para la compañía ficticia Contoso, que admite los dominios SIP de contoso.com y retail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="75b21-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="75b21-120">Ejemplo de registros de DNS necesarios para el inicio de sesión automático de los clientes con varios dominios SIP</span><span class="sxs-lookup"><span data-stu-id="75b21-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75b21-121">FQDN del grupo de servidores front-end utilizado para distribuir las solicitudes de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="75b21-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="75b21-122">Dominio SIP</span><span class="sxs-lookup"><span data-stu-id="75b21-122">SIP domain</span></span></th>
<th><span data-ttu-id="75b21-123">Registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="75b21-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75b21-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="75b21-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="75b21-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="75b21-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="75b21-126">Registro SRV para el dominio _sipinternaltls._tcp.contoso.com por el puerto 5061 que se asigna a pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="75b21-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75b21-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="75b21-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="75b21-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="75b21-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="75b21-129">Registro SRV para el dominio _sipinternaltls._tcp.retail.contoso.com por el puerto 5061 que se asigna a pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="75b21-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="75b21-130">De forma predeterminada, las consultas de los registros de DNS observan estrictamente los resultados de los nombres de dominio entre el dominio del nombre de usuario y el registro SRV.</span><span class="sxs-lookup"><span data-stu-id="75b21-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="75b21-131">Si prefiere que las consultas de DNS de los clientes usen los resultados de sufijos, puede configurar la directiva de grupo DisableStrictDNSNaming.</span><span class="sxs-lookup"><span data-stu-id="75b21-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="75b21-132">Para obtener más información, vea <A href="lync-server-2013-planning-for-clients-and-devices.md">planificación de clientes y dispositivos en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="75b21-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="75b21-133">Ejemplo de los certificados y registros de DNS necesarios para el inicio de sesión automático de los clientes</span><span class="sxs-lookup"><span data-stu-id="75b21-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="75b21-p105">En este ejemplo se utilizan los mismos nombres de ejemplo de la tabla anterior. La organización Contoso admite los dominios SIP de contoso.com y retail.contoso.com, y todos sus usuarios tienen un URI de SIP con uno de los formatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="75b21-p105">This example uses the same example names in the preceding table. The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="75b21-136">\<usuario\>@retail. contoso.com</span><span class="sxs-lookup"><span data-stu-id="75b21-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="75b21-137">\<@contoso\>de usuario. com</span><span class="sxs-lookup"><span data-stu-id="75b21-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

