---
title: 'Lync Server 2013: Compatibilidad de certificado de comodín'
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
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="fe743-102">Compatibilidad de certificado de comodín en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe743-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe743-103">_**Última modificación del tema:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="fe743-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="fe743-104">Lync Server 2013 usa certificados para proporcionar cifrado de comunicaciones y autenticación de identidades de servidor.</span><span class="sxs-lookup"><span data-stu-id="fe743-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="fe743-105">En algunos casos, como la publicación web a través del proxy inverso, la coincidencia de entrada de nombre alternativo de asunto (SAN) con el nombre de dominio completo (FQDN) del servidor que presenta el servicio no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="fe743-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="fe743-106">En estos casos, puede usar certificados con entradas SAN con comodín (comúnmente conocidos como "certificados comodín") para reducir el costo de un certificado solicitado por una autoridad de certificación pública y para reducir la complejidad del proceso de planeación de certificados .</span><span class="sxs-lookup"><span data-stu-id="fe743-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fe743-107">Para conservar la funcionalidad de los dispositivos de comunicaciones unificadas (por ejemplo, los teléfonos de escritorio), debe probar el certificado implementado con cuidado para asegurarse de que los dispositivos funcionan correctamente después de implementar un certificado de comodín.</span><span class="sxs-lookup"><span data-stu-id="fe743-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="fe743-108">No se admite una entrada de comodín como nombre de asunto (también denominado nombre común o CN) para cualquier rol.</span><span class="sxs-lookup"><span data-stu-id="fe743-108">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role.</span></span> <span data-ttu-id="fe743-109">Los siguientes roles de servidor se admiten al usar entradas con comodín en el SAN:</span><span class="sxs-lookup"><span data-stu-id="fe743-109">The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="fe743-110">**Proxy inverso.**    La entrada San con comodín es compatible con el certificado de publicación de URL simple (reunirse y llamar).</span><span class="sxs-lookup"><span data-stu-id="fe743-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="fe743-111">**Proxy inverso.**    La entrada San con comodín es compatible con las entradas San para LyncDiscover en el certificado de publicación.</span><span class="sxs-lookup"><span data-stu-id="fe743-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="fe743-112">**Director.**    La entrada San con comodín es compatible con las direcciones URL simples (reunirse y llamar) y para las entradas de San para LyncDiscover y LyncDiscoverInternal en los componentes Web de director.</span><span class="sxs-lookup"><span data-stu-id="fe743-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="fe743-113">**Servidor front end (Standard Edition) y grupo de servidores front-end (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="fe743-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="fe743-114">La entrada SAN con comodín es compatible con las direcciones URL simples (reunirse y llamar) y para las entradas de SAN para LyncDiscover y LyncDiscoverInternal en los componentes Web front-end.</span><span class="sxs-lookup"><span data-stu-id="fe743-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="fe743-115">**Mensajería unificada de Exchange (UM).**    El servidor no usa entradas San cuando se implementa como un servidor independiente.</span><span class="sxs-lookup"><span data-stu-id="fe743-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="fe743-116">**Servidor de acceso de cliente de Microsoft Exchange Server.**    Las entradas con comodín en el San son compatibles con los clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="fe743-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="fe743-117">**Mensajería unificada de Exchange y servidor de acceso de cliente de Microsoft Exchange Server en el mismo servidor.**    Se admiten entradas San con comodín.</span><span class="sxs-lookup"><span data-stu-id="fe743-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="fe743-118">Roles de servidor que no se tratan en este tema:</span><span class="sxs-lookup"><span data-stu-id="fe743-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="fe743-119">Roles de servidor interno (incluidos, entre otros, el servidor de mediación, el servidor de archivado y el servidor de supervisión, el dispositivo de sucursal con supervivencia o el servidor de sucursal superviviente)</span><span class="sxs-lookup"><span data-stu-id="fe743-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="fe743-120">Interfaces de servidor perimetral externo</span><span class="sxs-lookup"><span data-stu-id="fe743-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="fe743-121">Servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="fe743-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe743-122">Para la interfaz de servidor perimetral interno, se puede asignar una entrada comodín a la SAN y es compatible.</span><span class="sxs-lookup"><span data-stu-id="fe743-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="fe743-123">No se consulta la SAN en el servidor perimetral interno y una entrada SAN con comodín tiene un valor limitado.</span><span class="sxs-lookup"><span data-stu-id="fe743-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="fe743-124">Para obtener más información sobre la configuración de certificados, incluido el uso de caracteres comodín en los certificados, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="fe743-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="fe743-125">Requisitos de certificado para Servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe743-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="fe743-126">Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe743-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="fe743-127">Resumen de certificado - Carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe743-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="fe743-128">Resumen de certificado - Director único en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe743-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="fe743-129">Resumen de certificado - Grupo de director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe743-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="fe743-130">Resumen de certificado - Proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe743-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="fe743-131">Instrucciones para integrar mensajería unificada local y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe743-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="fe743-132">Para obtener detalles sobre la configuración de certificados para Exchange, incluido el uso de caracteres comodín, consulte la documentación del producto Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="fe743-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

