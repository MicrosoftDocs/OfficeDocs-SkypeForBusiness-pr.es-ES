---
title: 'Lync Server 2013: requisitos de DNS para movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ceddef859ebc24168c12fdf0721448c6d2b658
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="45a42-102">Requisitos de DNS para la movilidad con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45a42-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45a42-103">_**Última modificación del tema:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="45a42-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="45a42-104">Al implementar la característica de movilidad de Lync Server 2013, puede usar las nuevas direcciones URL que están disponibles con el servicio Detección automática de Microsoft Lync Server 2013 o puede usar las direcciones URL de servicios Web existentes.</span><span class="sxs-lookup"><span data-stu-id="45a42-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="45a42-105">Si usa las direcciones URL existentes, los usuarios deben escribir manualmente las direcciones URL en la configuración del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="45a42-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="45a42-106">Esta opción suele usarse para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="45a42-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="45a42-107">Cuando se usan las nuevas direcciones URL, los clientes móviles pueden detectar automáticamente recursos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="45a42-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="45a42-108">Cuando admite la detección automática, necesita agregar nuevos registros del sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="45a42-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="45a42-109">En esta sección se describen los registros DNS necesarios para la detección automática.</span><span class="sxs-lookup"><span data-stu-id="45a42-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="45a42-110">Para admitir la detección automática, debe crear los siguientes registros DNS para cada dominio SIP:</span><span class="sxs-lookup"><span data-stu-id="45a42-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="45a42-111">Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización</span><span class="sxs-lookup"><span data-stu-id="45a42-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="45a42-112">Un registro DNS externo, o público,  para admitir usuarios móviles que se conectan desde Internet</span><span class="sxs-lookup"><span data-stu-id="45a42-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="45a42-113">La URL de detección automática interna no debería ser direccionable desde fuera de su red.</span><span class="sxs-lookup"><span data-stu-id="45a42-113">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="45a42-114">La URL de detección automática externa no debería ser direccionable desde dentro de su red.</span><span class="sxs-lookup"><span data-stu-id="45a42-114">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="45a42-115">Sin embargo, si no cumple este requisito para la dirección URL externa, la funcionalidad del cliente móvil no se verá afectada.</span><span class="sxs-lookup"><span data-stu-id="45a42-115">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="45a42-116">Los registros DNS pueden ser registros CNAME o registros A (host).</span><span class="sxs-lookup"><span data-stu-id="45a42-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="45a42-117">**Registros DNS internos**</span><span class="sxs-lookup"><span data-stu-id="45a42-117">**Internal DNS records**</span></span>

<span data-ttu-id="45a42-118">Debe crear uno de los siguientes registros DNS internos:</span><span class="sxs-lookup"><span data-stu-id="45a42-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45a42-119">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="45a42-119">Record type</span></span></th>
<th><span data-ttu-id="45a42-120">Nombre de host o definición SRV</span><span class="sxs-lookup"><span data-stu-id="45a42-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="45a42-121">Se resuelve en</span><span class="sxs-lookup"><span data-stu-id="45a42-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45a42-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="45a42-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="45a42-123">lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="45a42-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="45a42-124">Nombre de dominio completo (FQDN) de servicios Web internos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director</span><span class="sxs-lookup"><span data-stu-id="45a42-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45a42-125">A (host)</span><span class="sxs-lookup"><span data-stu-id="45a42-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="45a42-126">lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="45a42-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="45a42-127">Dirección IP de servicios Web internos (dirección IP virtual (VIP) si usa un equilibrador de carga) de su grupo de directores, si tiene uno o el grupo de servidores front-end si no tiene un director</span><span class="sxs-lookup"><span data-stu-id="45a42-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="45a42-128">**Registros DNS externos**</span><span class="sxs-lookup"><span data-stu-id="45a42-128">**External DNS records**</span></span>

<span data-ttu-id="45a42-129">Debe crear uno de los siguientes registros DNS externos:</span><span class="sxs-lookup"><span data-stu-id="45a42-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45a42-130">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="45a42-130">Record type</span></span></th>
<th><span data-ttu-id="45a42-131">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="45a42-131">Host name</span></span></th>
<th><span data-ttu-id="45a42-132">Se resuelve en</span><span class="sxs-lookup"><span data-stu-id="45a42-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45a42-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="45a42-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="45a42-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="45a42-134">lyncdiscover.</span></span> <span data-ttu-id="45a42-135">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="45a42-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="45a42-136">FQDN de servicios web externos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director</span><span class="sxs-lookup"><span data-stu-id="45a42-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45a42-137">A (host)</span><span class="sxs-lookup"><span data-stu-id="45a42-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="45a42-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="45a42-138">lyncdiscover.</span></span> <span data-ttu-id="45a42-139">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="45a42-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="45a42-140">Dirección IP externa o pública (dirección VIP si usa un equilibrador de carga) del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="45a42-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45a42-141">SRV</span><span class="sxs-lookup"><span data-stu-id="45a42-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="45a42-142">_sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="45a42-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="45a42-143">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="45a42-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="45a42-144">Se resuelve en un registro de host (A o AAAA) para el servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="45a42-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="45a42-145">Para admitir el servicio de notificaciones de inserción y el servicio de notificaciones de inserción de Apple, cree un registro SRV para cada dominio SIP que tenga clientes móviles de Microsoft Lync.</span><span class="sxs-lookup"><span data-stu-id="45a42-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="45a42-146">Este requisito solo se aplica a los clientes móviles de Microsoft Lync en dispositivos móviles basados en Apple o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="45a42-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="45a42-147">Los dispositivos Android y Nokia Symbian no usan la notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="45a42-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="45a42-148">Lyncdiscover, también conocida como detección automática, el tráfico pasa a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="45a42-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="45a42-149">El registro SRV apunta a un registro que se resuelve a través del servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="45a42-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

