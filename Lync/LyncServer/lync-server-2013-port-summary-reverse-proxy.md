---
title: 'Lync Server 2013: Resumen de puerto - Proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2944cde932413f00b5a4dcb75cd4a37bd5b3a3a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="14ee8-102">Resumen de puerto - Proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14ee8-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14ee8-103">_**Última modificación del tema:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="14ee8-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="14ee8-104">El proxy inverso tiene requisitos mínimos para el firewall y el puerto/protocolo.</span><span class="sxs-lookup"><span data-stu-id="14ee8-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="14ee8-105">Los requisitos del firewall externo son HTTPS/TCP/443 y el HTTP/TCP/80 opcional.</span><span class="sxs-lookup"><span data-stu-id="14ee8-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="14ee8-106">HTTPS se usa para comunicaciones seguras SSL y TLS a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="14ee8-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="14ee8-107">HTTP se usa si elige permitir el acceso al servicio de detección automática al modificar certificados que puede resultar difícil o no estar justificado.</span><span class="sxs-lookup"><span data-stu-id="14ee8-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="14ee8-108">Los clientes esperan ponerse en contacto con el servidor de Office Web Apps en HTTPS.</span><span class="sxs-lookup"><span data-stu-id="14ee8-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="14ee8-109">El servidor de Office Web Apps Server espera la comunicación de los clientes internos en HTTPS/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="14ee8-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="14ee8-110">La configuración recomendada es permitir HTTPS/TCP/443 desde el proxy inverso hasta el servidor de Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="14ee8-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="14ee8-111">El puerto 8080 se usa para enrutar el tráfico de la interfaz interna de proxy invertida al servidor front-end, la IP virtual de la agrupación de front-end (VIP) o el director opcional o VIP del grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="14ee8-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="14ee8-112">El puerto TCP 8080 es necesario para que los dispositivos móviles que ejecutan Lync encuentren el servicio de detección automática en situaciones en las que no es deseable modificar el certificado de la regla de publicación de servicio Web externo (por ejemplo, si tiene un gran número de dominios SIP).</span><span class="sxs-lookup"><span data-stu-id="14ee8-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="14ee8-113">Si elige adquirir certificados nuevos con las entradas de SAN necesarias, el puerto TCP 8080 no es necesario y es opcional.</span><span class="sxs-lookup"><span data-stu-id="14ee8-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="14ee8-114">El puerto 4443 se usa para el tráfico de la interfaz interna de proxy invertida al servidor front-end, la IP virtual de grupo de servidores front-end (VIP) o el director opcional o VIP del grupo de directores</span><span class="sxs-lookup"><span data-stu-id="14ee8-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="14ee8-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="14ee8-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="14ee8-116">No confunda el 4443 sobre TCP del proxy inverso en la implementación interna para el puerto 4443 sobre el tráfico TCP desde el servidor Standard Edition o el grupo de servidores front-end que administra la función de almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="14ee8-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="14ee8-117">Detalles de protocolo y puerto</span><span class="sxs-lookup"><span data-stu-id="14ee8-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="14ee8-118">Detalles del firewall para el servidor proxy inverso: interfaz externa</span><span class="sxs-lookup"><span data-stu-id="14ee8-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14ee8-119">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="14ee8-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="14ee8-120">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="14ee8-120">Source IP Address</span></span></th>
<th><span data-ttu-id="14ee8-121">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="14ee8-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="14ee8-122">Notas</span><span class="sxs-lookup"><span data-stu-id="14ee8-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14ee8-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="14ee8-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="14ee8-124">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="14ee8-124">Any</span></span></p></td>
<td><p><span data-ttu-id="14ee8-125">Escucha de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="14ee8-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="14ee8-126">Faculta Redireccionamiento a HTTPS si el usuario&lt;escribe&gt;http://publishedSiteFQDN.</span><span class="sxs-lookup"><span data-stu-id="14ee8-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="14ee8-127">También se requiere si se usa Office Web Apps para conferencias y el servicio Detección automática para dispositivos móviles que ejecutan Lync en situaciones en las que la organización no desea modificar el certificado de regla de publicación de servicio Web externo.</span><span class="sxs-lookup"><span data-stu-id="14ee8-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14ee8-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="14ee8-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="14ee8-129">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="14ee8-129">Any</span></span></p></td>
<td><p><span data-ttu-id="14ee8-130">Escucha de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="14ee8-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="14ee8-131">Descargas de la libreta de direcciones, servicio de consultas Web de la libreta de direcciones, detección automática, actualizaciones de cliente, contenido de la reunión, actualizaciones de dispositivos, expansión de grupos, Office Web Apps para conferencias, conferencias de acceso telefónico local y reuniones.</span><span class="sxs-lookup"><span data-stu-id="14ee8-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="14ee8-132">Detalles del firewall para el servidor proxy inverso: interfaz interna</span><span class="sxs-lookup"><span data-stu-id="14ee8-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14ee8-133">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="14ee8-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="14ee8-134">Dirección IP de origen</span><span class="sxs-lookup"><span data-stu-id="14ee8-134">Source IP Address</span></span></th>
<th><span data-ttu-id="14ee8-135">Dirección IP de destino</span><span class="sxs-lookup"><span data-stu-id="14ee8-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="14ee8-136">Notas</span><span class="sxs-lookup"><span data-stu-id="14ee8-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14ee8-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="14ee8-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="14ee8-138">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="14ee8-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="14ee8-139">Servidor front-end, grupo front-end, Director, grupo de directores</span><span class="sxs-lookup"><span data-stu-id="14ee8-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="14ee8-140">Necesario si se usa el servicio de detección automática para dispositivos móviles que ejecutan Lync, en situaciones en las que la organización no desea modificar el certificado de la regla de publicación de servicio Web externo.</span><span class="sxs-lookup"><span data-stu-id="14ee8-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="14ee8-141">El tráfico enviado al puerto 80 en la interfaz externa de proxy inverso se redirige a un grupo en el puerto 8080 desde la interfaz interna de proxy invertida para que los servicios web del grupo lo diferencien del tráfico web interno.</span><span class="sxs-lookup"><span data-stu-id="14ee8-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14ee8-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="14ee8-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="14ee8-143">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="14ee8-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="14ee8-144">Servidor front-end, grupo front-end, Director, grupo de directores</span><span class="sxs-lookup"><span data-stu-id="14ee8-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="14ee8-145">El tráfico enviado al puerto 443 en la interfaz externa de proxy inverso se redirige a un grupo en el puerto 4443 desde la interfaz interna de proxy invertida para que los servicios web del grupo lo diferencien del tráfico web interno.</span><span class="sxs-lookup"><span data-stu-id="14ee8-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14ee8-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="14ee8-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="14ee8-147">Interfaz interna de proxy invertida</span><span class="sxs-lookup"><span data-stu-id="14ee8-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="14ee8-148">Office Web Apps para conferencias</span><span class="sxs-lookup"><span data-stu-id="14ee8-148">Office Web Apps for conferencing</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

