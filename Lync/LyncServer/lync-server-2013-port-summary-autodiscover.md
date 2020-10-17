---
title: 'Lync Server 2013: Resumen de Puerto-detección automática'
description: 'Lync Server 2013: Resumen de Puerto-detección automática.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543146"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="00a9d-103">Resumen de Puerto-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a9d-103">Port summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00a9d-104">_**Última modificación del tema:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="00a9d-104">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="00a9d-105">El servicio Detección automática de Lync Server 2013 se ejecuta en los servidores de director y de grupo de servidores front-end y, cuando se publican en DNS con los `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` registros de host y, pueden ser usados por los clientes para localizar las características de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00a9d-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="00a9d-106">Para que los dispositivos móviles que ejecutan Lync Mobile usen la detección automática, es posible que primero necesite modificar las listas de nombres alternativos de sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="00a9d-106">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="00a9d-107">Además, es posible que haya que modificar las listas de nombres alternativos de sujeto en certificados usados para las reglas de publicación de servicios web en proxies inversos.</span><span class="sxs-lookup"><span data-stu-id="00a9d-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="00a9d-108">La decisión sobre si usar listas de nombres alternativos de sujetos en servidores proxy inversos se basa en si publica el servicio Detección automática en el puerto 80 o en el puerto 443:</span><span class="sxs-lookup"><span data-stu-id="00a9d-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="00a9d-109">**Publicado en el puerto 80**     Para dispositivos móviles, no es necesario realizar cambios en los certificados si la consulta inicial al servicio Detección automática se produce a través del puerto 80.</span><span class="sxs-lookup"><span data-stu-id="00a9d-109">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="00a9d-110">Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y, a continuación, se redirigirán a un director o a un servidor front-end en el puerto 8080 de forma interna.</span><span class="sxs-lookup"><span data-stu-id="00a9d-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="00a9d-111">**Publicado en el puerto 443**     La lista de nombres alternativos de sujeto en los certificados usados por la regla de publicación de servicios web externos debe contener una `lyncdiscover.<sipdomain>` entrada para cada dominio SIP dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="00a9d-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="00a9d-112">Para instalaciones nuevas o actualizaciones de Lync Server 2010 donde se implementó la movilidad, se usó el puerto 80 para la detección automática del servicio de movilidad o se volveron a emitir certificados con el nombre de sujeto y los nombres alternativos de sujeto correctos en su lugar.</span><span class="sxs-lookup"><span data-stu-id="00a9d-112">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="00a9d-113">Revise los certificados en el director y el servidor front-end para confirmar la ruta de acceso que eligió.</span><span class="sxs-lookup"><span data-stu-id="00a9d-113">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="00a9d-114">Detalles de firewalls para servidor proxy inverso: Interfaz externa</span><span class="sxs-lookup"><span data-stu-id="00a9d-114">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00a9d-115">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="00a9d-115">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="00a9d-116">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="00a9d-116">Source IP Address</span></span></th>
<th><span data-ttu-id="00a9d-117">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="00a9d-117">Destination IP Address</span></span></th>
<th><span data-ttu-id="00a9d-118">Notas</span><span class="sxs-lookup"><span data-stu-id="00a9d-118">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00a9d-119">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="00a9d-119">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="00a9d-120">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="00a9d-120">Any</span></span></p></td>
<td><p><span data-ttu-id="00a9d-121">Escucha de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="00a9d-121">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="00a9d-122">Opcional Redirección a HTTPS si el usuario escribe http:// &lt; publishedSiteFQDN &gt; .</span><span class="sxs-lookup"><span data-stu-id="00a9d-122">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="00a9d-123">También es necesario si usa Office Web Apps para conferencias y el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea modificar el certificado de la regla de publicación de servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="00a9d-123">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00a9d-124">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="00a9d-124">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="00a9d-125">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="00a9d-125">Any</span></span></p></td>
<td><p><span data-ttu-id="00a9d-126">Escucha de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="00a9d-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="00a9d-127">Descargas de la libreta de direcciones, servicio de consulta Web de libreta de direcciones, detección automática, actualizaciones de cliente, contenido de reuniones, actualizaciones de dispositivos, expansión de grupos, Office Web Apps para conferencias, conferencias de acceso telefónico local y reuniones.</span><span class="sxs-lookup"><span data-stu-id="00a9d-127">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="00a9d-128">Detalles de firewalls para servidor proxy inverso: Interfaz interna</span><span class="sxs-lookup"><span data-stu-id="00a9d-128">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00a9d-129">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="00a9d-129">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="00a9d-130">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="00a9d-130">Source IP Address</span></span></th>
<th><span data-ttu-id="00a9d-131">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="00a9d-131">Destination IP Address</span></span></th>
<th><span data-ttu-id="00a9d-132">Notas</span><span class="sxs-lookup"><span data-stu-id="00a9d-132">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00a9d-133">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="00a9d-133">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="00a9d-134">Interfaz de proxy inverso interno</span><span class="sxs-lookup"><span data-stu-id="00a9d-134">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="00a9d-135">Servidor front-end, grupo de servidores front-end, Director, grupo de directores, Office Web Apps para conferencias</span><span class="sxs-lookup"><span data-stu-id="00a9d-135">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="00a9d-136">Es necesario si se usa el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea modificar el certificado de la regla de publicación de servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="00a9d-136">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="00a9d-137">El tráfico que se envía a 80 en la interfaz externa del proxy inverso se redirige a un grupo de servidores del puerto 8080 desde la interfaz interna del proxy inverso, para que los servicios web del grupo de servidores puedan distinguirlo del tráfico web interno.</span><span class="sxs-lookup"><span data-stu-id="00a9d-137">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00a9d-138">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="00a9d-138">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="00a9d-139">Interfaz de proxy inverso interno</span><span class="sxs-lookup"><span data-stu-id="00a9d-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="00a9d-140">Servidor front-end, grupo de servidores front-end, Director, grupo de directores, Office Web Apps para conferencias</span><span class="sxs-lookup"><span data-stu-id="00a9d-140">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="00a9d-141">El tráfico enviado al puerto 443 de la interfaz externa del proxy inverso se redirige a un grupo de servidores del puerto 4443 desde la interfaz interna del proxy inverso para que los servicios web del grupo de servidores puedan distinguirlo del tráfico web interno.</span><span class="sxs-lookup"><span data-stu-id="00a9d-141">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

