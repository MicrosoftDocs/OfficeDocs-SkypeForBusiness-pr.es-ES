---
title: 'Lync Server 2013: requisitos de DNS para el inicio de sesión automático de los clientes'
description: 'Lync Server 2013: requisitos de DNS para el inicio de sesión automático de los clientes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2247c955e0a563a22fb5d0ec20735291a836cdfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574376"
---
# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="d5529-103">Requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5529-103">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5529-104">_**Última modificación del tema:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="d5529-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="d5529-105">En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para el inicio de sesión automático de clientes.</span><span class="sxs-lookup"><span data-stu-id="d5529-105">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="d5529-106">Cuando se implementan servidores Standard Edition o grupos de servidores front-end, se pueden configurar los clientes para que usen la detección automática para iniciar sesión en el servidor Standard Edition o el grupo de servidores front-end adecuado.</span><span class="sxs-lookup"><span data-stu-id="d5529-106">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="d5529-107">Si va a requerir que los clientes se conecten de forma manual a Lync Server 2013, puede omitir este tema.</span><span class="sxs-lookup"><span data-stu-id="d5529-107">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="d5529-108">Para admitir el inicio de sesión automático de los clientes, debe:</span><span class="sxs-lookup"><span data-stu-id="d5529-108">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="d5529-p102">Designar un único servidor o grupo de servidores para distribuir y autenticar las solicitudes de inicio de sesión de los clientes. Puede ser uno de los servidores o grupos de servidores existentes en la organización que hospede usuarios, o bien, puede designar un servidor o grupo de servidores dedicado para este fin que no hospede usuarios. Para lograr una alta disponibilidad, se recomienda designar un grupo de servidores front-end para esta función.</span><span class="sxs-lookup"><span data-stu-id="d5529-p102">Designate a single server or pool to distribute and authenticate client sign-in requests. This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users. For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="d5529-112">Crear un registro DNS SRV interno para admitir el inicio automático de sesión de clientes para este servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="d5529-112">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5529-p103">En los siguientes requisitos de registro, el dominio SIP hace referencia a la parte correspondiente al host de los URI de SIP asignados a los usuarios. Por ejemplo, si los URI de SIP tienen el formato \*@contoso.com, contoso.com es el dominio SIP. El dominio SIP suele ser distinto del dominio de Active Directory interno. Una organización también puede admitir varios dominios SIP.</span><span class="sxs-lookup"><span data-stu-id="d5529-p103">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users. For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain. The SIP domain is often different from the internal Active Directory domain. An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="d5529-117">Para habilitar la configuración automática de los clientes, debe crear un registro SRV de DNS interno que asigne uno de los siguientes registros al nombre de dominio completo (FQDN) del grupo de servidores front-end o del servidor Standard Edition que distribuye las solicitudes de inicio de sesión de los clientes de Lync:</span><span class="sxs-lookup"><span data-stu-id="d5529-117">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="d5529-118">\_sipinternaltls. \_ TPC.\<domain\></span><span class="sxs-lookup"><span data-stu-id="d5529-118">\_sipinternaltls.\_tcp.\<domain\></span></span> <span data-ttu-id="d5529-119">-para conexiones TLS internas</span><span class="sxs-lookup"><span data-stu-id="d5529-119">- for internal TLS connections</span></span>

<span data-ttu-id="d5529-120">Solo tiene que crear un único registro SRV para el servidor Standard Edition o el grupo de servidores front-end que distribuirá las solicitudes de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="d5529-120">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="d5529-121">En la tabla siguiente se muestran algunos registros de ejemplo que se requieren para la compañía ficticia Contoso, que admite los dominios SIP contoso.com y retail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d5529-121">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="d5529-122">Ejemplo de registros DNS necesarios para el inicio de sesión automático de los clientes con varios dominios SIP</span><span class="sxs-lookup"><span data-stu-id="d5529-122">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5529-123">FQDN del grupo de servidores front-end utilizado para distribuir las solicitudes de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="d5529-123">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="d5529-124">Dominio SIP</span><span class="sxs-lookup"><span data-stu-id="d5529-124">SIP domain</span></span></th>
<th><span data-ttu-id="d5529-125">Registro DNS SRV</span><span class="sxs-lookup"><span data-stu-id="d5529-125">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5529-126">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5529-126">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d5529-127">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5529-127">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d5529-128">Registro SRV para el dominio _sipinternaltls._tcp.contoso.com sobre el puerto 5061 que se asigna a pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5529-128">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5529-129">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5529-129">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d5529-130">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5529-130">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d5529-131">Registro SRV para el dominio _sipinternaltls._tcp.retail.contoso.com sobre el puerto 5061 que se asigna a pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5529-131">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d5529-132">De forma predeterminada, las consultas de los registros DNS observan estrictamente la coincidencia de los nombres de dominio entre el dominio del nombre de usuario y el registro SRV.</span><span class="sxs-lookup"><span data-stu-id="d5529-132">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="d5529-133">Si prefiere que las consultas DNS de los clientes usen la coincidencia de sufijos, puede configurar la directiva de grupo DisableStrictDNSNaming.</span><span class="sxs-lookup"><span data-stu-id="d5529-133">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="d5529-134">Para obtener más información, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="d5529-134">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="d5529-135">Ejemplo de los certificados y registros DNS requeridos para el inicio de sesión automático de los clientes</span><span class="sxs-lookup"><span data-stu-id="d5529-135">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="d5529-p106">En este ejemplo se utilizan los mismos nombres de ejemplo de la tabla anterior. La organización Contoso admite los dominios SIP de contoso.com y retail.contoso.com, y todos sus usuarios tienen un URI de SIP con uno de los formatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5529-p106">This example uses the same example names in the preceding table. The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="d5529-138">\<user\>@retail. contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5529-138">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="d5529-139">\<user\>@contoso. com</span><span class="sxs-lookup"><span data-stu-id="d5529-139">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

