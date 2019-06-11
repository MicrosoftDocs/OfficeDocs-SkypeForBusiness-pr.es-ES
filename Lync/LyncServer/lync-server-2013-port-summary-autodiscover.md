---
title: 'Lync Server 2013: Resumen de puertos-detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a40d86799b4922a819642aedf2461f038330593
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="cb016-102">Resumen de puertos-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb016-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb016-103">_**Última modificación del tema:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="cb016-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="cb016-104">El servicio de detección automática de Lync Server 2013 se ejecuta en los servidores de director y de grupo de servidores front-end `lyncdiscover.<domain>` y `lyncdiscoverinternal.<domain>` , cuando se publican en DNS con los registros de host y de hospedaje, los clientes pueden usarlos para localizar las características de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cb016-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="cb016-105">Para que los dispositivos móviles que ejecutan Lync Mobile puedan usar la detección automática, es posible que primero tenga que modificar las listas de nombres alternativos del sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="cb016-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="cb016-106">Además, puede que sea necesario modificar las listas de nombres alternativos del asunto en los certificados que se usan para las reglas de publicación de servicios web externos en los proxies inversos.</span><span class="sxs-lookup"><span data-stu-id="cb016-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="cb016-107">La decisión sobre si usar o no las listas de nombres alternativos del sujeto en proxies inversos se basa en si publica el servicio de detección automática en el puerto 80 o en el puerto 443:</span><span class="sxs-lookup"><span data-stu-id="cb016-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="cb016-108">**Publicado en el puerto 80**   para dispositivos móviles, no es necesario realizar cambios en los certificados si la consulta inicial para el servicio de detección automática se realiza a través del puerto 80.</span><span class="sxs-lookup"><span data-stu-id="cb016-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="cb016-109">Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y se redirigirá a un director o servidor front-end en el puerto 8080 de forma interna.</span><span class="sxs-lookup"><span data-stu-id="cb016-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="cb016-110">**Publicado en el puerto 443**   la lista de nombres alternativos de asunto en certificados usados por la regla de publicación de servicios `lyncdiscover.<sipdomain>` web externos debe contener una entrada para cada dominio SIP de su organización.</span><span class="sxs-lookup"><span data-stu-id="cb016-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cb016-111">En el caso de instalaciones nuevas o actualizaciones de Lync Server 2010 donde ha implementado la movilidad, ya ha usado el puerto 80 para la detección automática del servicio de movilidad o ha reemitido certificados con el nombre de asunto y los nombres alternativos de asunto correctos.</span><span class="sxs-lookup"><span data-stu-id="cb016-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="cb016-112">Revise los certificados de su director y del servidor front-end para confirmar qué ruta de acceso elegida.</span><span class="sxs-lookup"><span data-stu-id="cb016-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="cb016-113">Detalles del firewall para el servidor proxy inverso: interfaz externa</span><span class="sxs-lookup"><span data-stu-id="cb016-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb016-114">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="cb016-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cb016-115">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="cb016-115">Source IP Address</span></span></th>
<th><span data-ttu-id="cb016-116">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="cb016-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="cb016-117">Notas</span><span class="sxs-lookup"><span data-stu-id="cb016-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb016-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="cb016-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="cb016-119">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cb016-119">Any</span></span></p></td>
<td><p><span data-ttu-id="cb016-120">Escucha de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="cb016-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="cb016-121">Faculta Redireccionamiento a HTTPS si el usuario&lt;escribe&gt;http://publishedSiteFQDN.</span><span class="sxs-lookup"><span data-stu-id="cb016-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="cb016-122">También se requiere si se usa Office Web Apps para conferencias y el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea modificar el certificado de regla de publicación de servicio Web externo.</span><span class="sxs-lookup"><span data-stu-id="cb016-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb016-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cb016-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cb016-124">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="cb016-124">Any</span></span></p></td>
<td><p><span data-ttu-id="cb016-125">Escucha de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="cb016-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="cb016-126">Descargas de la libreta de direcciones, servicio de consultas Web de la libreta de direcciones, detección automática, actualizaciones de cliente, contenido de la reunión, actualizaciones de dispositivos, expansión de grupos, Office Web Apps para conferencias, conferencias de acceso telefónico local y reuniones.</span><span class="sxs-lookup"><span data-stu-id="cb016-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="cb016-127">Detalles del firewall para el servidor proxy inverso: interfaz interna</span><span class="sxs-lookup"><span data-stu-id="cb016-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb016-128">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="cb016-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cb016-129">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="cb016-129">Source IP Address</span></span></th>
<th><span data-ttu-id="cb016-130">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="cb016-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="cb016-131">Notas</span><span class="sxs-lookup"><span data-stu-id="cb016-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb016-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="cb016-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="cb016-133">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="cb016-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="cb016-134">Servidor front-end, grupo front-end, Director, grupo de directores, Office Web Apps para conferencias</span><span class="sxs-lookup"><span data-stu-id="cb016-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="cb016-135">Necesario si se usa el servicio de detección automática para dispositivos móviles que ejecutan Lync, en situaciones en las que la organización no desea modificar el certificado de la regla de publicación de servicio Web externo.</span><span class="sxs-lookup"><span data-stu-id="cb016-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="cb016-136">El tráfico enviado al puerto 80 en la interfaz externa de proxy inverso se redirige a un grupo en el puerto 8080 desde la interfaz interna de proxy invertida para que los servicios web del grupo lo diferencien del tráfico web interno.</span><span class="sxs-lookup"><span data-stu-id="cb016-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb016-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="cb016-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="cb016-138">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="cb016-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="cb016-139">Servidor front-end, grupo front-end, Director, grupo de directores, Office Web Apps para conferencias</span><span class="sxs-lookup"><span data-stu-id="cb016-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="cb016-140">El tráfico enviado al puerto 443 en la interfaz externa de proxy inverso se redirige a un grupo en el puerto 4443 desde la interfaz interna de proxy invertida para que los servicios web del grupo lo diferencien del tráfico web interno.</span><span class="sxs-lookup"><span data-stu-id="cb016-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

