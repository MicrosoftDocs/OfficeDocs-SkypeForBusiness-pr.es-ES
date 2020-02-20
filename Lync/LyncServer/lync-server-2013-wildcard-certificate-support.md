---
title: Compatibilidad con certificados comodín 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d48ba92ffd18e385be95d6218357303a67f892c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="0920b-102">Compatibilidad con certificados comodín en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0920b-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0920b-103">_**Última modificación del tema:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="0920b-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="0920b-104">Lync Server 2013 usa certificados para proporcionar cifrado de comunicaciones y autenticación de identidad de servidor.</span><span class="sxs-lookup"><span data-stu-id="0920b-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="0920b-105">En algunos casos, como la publicación web mediante proxy inverso, no es  necesaria la coincidencia sólida de entradas de nombre alternativo de sujeto (SAN) con el nombre de dominio completo (FQDN) del servidor que presenta el servicio.</span><span class="sxs-lookup"><span data-stu-id="0920b-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="0920b-106">En estos casos, puede usar certificados con entradas de SAN de comodín (conocidas generalmente como “certificados de comodín”) para reducir el costo de un certificado solicitado de una entidad de certificación pública y para reducir la complejidad del proceso de planeamiento para certificados.</span><span class="sxs-lookup"><span data-stu-id="0920b-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0920b-107">Para retener la funcionalidad de los dispositivos de comunicaciones unificadas (UC) (por ejemplo, teléfonos de escritorio), debe probar el certificado implementado con cuidado para garantizar que los dispositivos funcionan correctamente después de implementar un certificado de comodín.</span><span class="sxs-lookup"><span data-stu-id="0920b-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="0920b-p102">No hay compatibilidad para una entrada de comodín como nombre de sujeto (también denominado nombre común o CN) para ninguna función. Las siguientes funciones de servidor son compatibles al usar entradas de comodín en el SAN:</span><span class="sxs-lookup"><span data-stu-id="0920b-p102">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role. The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="0920b-110">**Proxy inverso.**    La entrada San comodín se admite para el certificado de publicación de dirección URL sencilla (reunirse y llamar).</span><span class="sxs-lookup"><span data-stu-id="0920b-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="0920b-111">**Proxy inverso.**    La entrada San comodín es compatible con las entradas de San para LyncDiscover en el certificado de publicación.</span><span class="sxs-lookup"><span data-stu-id="0920b-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="0920b-112">**Director.**    La entrada de San comodín se admite para las direcciones URL sencillas (reunirse y llamar) y para las entradas de San para LyncDiscover y LyncDiscoverInternal en componentes Web de director.</span><span class="sxs-lookup"><span data-stu-id="0920b-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="0920b-113">**Servidor front-end (Standard Edition) y grupo de servidores front-end (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="0920b-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="0920b-114">La entrada SAN comodín se admite para las direcciones URL sencillas (reunirse y llamar) y para las entradas de SAN para LyncDiscover y LyncDiscoverInternal en los componentes Web front-end.</span><span class="sxs-lookup"><span data-stu-id="0920b-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="0920b-115">**Mensajería unificada (MU) de Exchange.**    El servidor no usa entradas de San cuando se implementa como un servidor independiente.</span><span class="sxs-lookup"><span data-stu-id="0920b-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="0920b-116">**Servidor de acceso de cliente de Microsoft Exchange Server.**    Las entradas de comodín en el San son compatibles con los clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="0920b-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="0920b-117">**Mensajería unificada (MU) de Exchange y servidor de acceso de cliente de Microsoft Exchange Server en el mismo servidor.**    Se admiten las entradas San de comodín.</span><span class="sxs-lookup"><span data-stu-id="0920b-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="0920b-118">Funciones de servidor que no se abordan en este tema:</span><span class="sxs-lookup"><span data-stu-id="0920b-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="0920b-119">Roles de servidor interno (incluidos, entre otros, el servidor de mediación, el servidor de archivado y de supervisión, una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia)</span><span class="sxs-lookup"><span data-stu-id="0920b-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="0920b-120">Interfaces del servidor perimetral externo</span><span class="sxs-lookup"><span data-stu-id="0920b-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="0920b-121">Servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="0920b-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0920b-122">Para la interfaz del servidor perimetral interno, se puede asignar una entrada de comodín al SAN y es compatible.</span><span class="sxs-lookup"><span data-stu-id="0920b-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="0920b-123">No se consulta la SAN del servidor perimetral interno y una entrada de SAN comodín es de valor limitado.</span><span class="sxs-lookup"><span data-stu-id="0920b-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="0920b-124">Para obtener más información acerca de la configuración de certificados, incluido el uso de caracteres comodín en los certificados, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="0920b-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="0920b-125">Requisitos de certificado para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0920b-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="0920b-126">Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0920b-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="0920b-127">Resumen de certificado-carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0920b-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="0920b-128">Resumen del certificado-Director único en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0920b-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="0920b-129">Resumen de certificado-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0920b-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="0920b-130">Resumen de certificado-proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0920b-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="0920b-131">Directrices para la integración de la mensajería unificada local y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0920b-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="0920b-132">Para obtener más información acerca de la configuración de certificados para Exchange, incluido el uso de caracteres comodín, consulte la documentación del producto de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0920b-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

