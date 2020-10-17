---
title: 'Lync Server 2013: proceso de implementación para movilidad'
description: 'Lync Server 2013: proceso de implementación para movilidad.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b49d69af899f6d9f2ac1db5040d017a9d62ce9eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551046"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="7d1ba-103">Proceso de implementación para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d1ba-103">Deployment process for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d1ba-104">_**Última modificación del tema:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="7d1ba-104">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="7d1ba-105">En esta sección se describe la secuencia de pasos necesarios para implementar la característica de movilidad de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-105">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="7d1ba-106">Proceso de implementación de movilidad</span><span class="sxs-lookup"><span data-stu-id="7d1ba-106">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d1ba-107">Fase</span><span class="sxs-lookup"><span data-stu-id="7d1ba-107">Phase</span></span></th>
<th><span data-ttu-id="7d1ba-108">Pasos</span><span class="sxs-lookup"><span data-stu-id="7d1ba-108">Steps</span></span></th>
<th><span data-ttu-id="7d1ba-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="7d1ba-109">Permissions</span></span></th>
<th><span data-ttu-id="7d1ba-110">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="7d1ba-110">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d1ba-111">Crear registros del sistema de nombre de domino (DNS)</span><span class="sxs-lookup"><span data-stu-id="7d1ba-111">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7d1ba-112">Cree un registro CNAME de DNS interno o un (host, si IPv6, AAAA) para resolver la dirección URL interna del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-112">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-113">Cree un registro CNAME de DNS externo o un registro (host, si IPv6, AAAA) para resolver la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-113">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d1ba-114">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="7d1ba-114">Domain Admins</span></span></p>
<p><span data-ttu-id="7d1ba-115">Administradores</span><span class="sxs-lookup"><span data-stu-id="7d1ba-115">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-116"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creación de registros DNS para el servicio Detección automática en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d1ba-116"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d1ba-117">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="7d1ba-117">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-118">Agregue entradas de nombre alternativo de sujeto a los siguientes certificados para admitir conexiones seguras para usuarios móviles:</span><span class="sxs-lookup"><span data-stu-id="7d1ba-118">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d1ba-119">Certificado de Director</span><span class="sxs-lookup"><span data-stu-id="7d1ba-119">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-120">Certificado del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="7d1ba-120">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-121">Certificado de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="7d1ba-121">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d1ba-122">Administrador local</span><span class="sxs-lookup"><span data-stu-id="7d1ba-122">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-123"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modificación de certificados para movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d1ba-123"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d1ba-124">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="7d1ba-124">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7d1ba-125">Asigne certificados actualizados con nombres alternativos de sujeto a la escucha de la capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="7d1ba-125">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-126">Vuelva a configurar la regla de publicación web para la dirección URL externa del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-126">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-127">Asegúrese de que existe una regla de publicación web para la URL externa de servicios Web de Lync Server 2013 en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-127">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="7d1ba-128">O bien:</span><span class="sxs-lookup"><span data-stu-id="7d1ba-128">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="7d1ba-129">Si decide usar HTTP para la solicitud de detección automática inicial y no actualiza las listas de nombres alternativos del sujeto en los certificados, configure una nueva regla de publicación web o vuelva a configurar una regla de publicación existente para el puerto 80 HTTP.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-129">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d1ba-130">Administrador local</span><span class="sxs-lookup"><span data-stu-id="7d1ba-130">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-131"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuración del proxy inverso para movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d1ba-131"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d1ba-132">Probar la implementación de la movilidad para Lync 2010 Mobile mediante el servicio de movilidad MCX</span><span class="sxs-lookup"><span data-stu-id="7d1ba-132">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-133">Ejecute <strong>Test-CsMcxP2PIM</strong> para probar el envío de un mensaje instantáneo de una persona a otra.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-133">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="7d1ba-134">Consulte la documentación del cmdlet del shell de administración de Lync Server para <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> para obtener una lista completa de las opciones.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-134">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-135">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7d1ba-135">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-136"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Comprobar la implementación de la movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d1ba-136"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d1ba-137">Probar la implementación de la movilidad para clientes móviles de Lync 2013 mediante UCWA Web Components</span><span class="sxs-lookup"><span data-stu-id="7d1ba-137">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-138">Use el cmdlet <strong>Test-CsUcwaConference</strong> para probar y comprobar que los usuarios de prueba predefinidos o un par de usuarios reales pueden usar UCWA para crear y participar en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-138">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="7d1ba-139">Consulte la documentación del cmdlet del shell de administración de Lync Server para <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> para obtener una lista completa de las opciones.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-139">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7d1ba-140">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-141"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Comprobar la implementación de la movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d1ba-141"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d1ba-142">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="7d1ba-142">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7d1ba-143">Para los servidores perimetrales de Lync Server 2013, agregue un proveedor de hospedaje de Lync Server online y configure la Federación del proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-143">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-144">Para los servidores perimetrales de Lync Server 2010, agregue un proveedor de hospedaje de Lync Server online y configure la Federación del proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-144">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-145">Para los servidores perimetrales de Office Communications Server 2007 R2, agregue un socio federado.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-145">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-146">Si desea admitir notificaciones de inserción a través de una red Wi-Fi, configure una regla de firewall de salida para el puerto TCP 5223.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-146">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-147">Use el cmdlet <strong>Set-CsPushNotificationConfiguration</strong> para habilitar notificaciones de inserción para el servicio de notificación de inserción de Apple (APNS) y el servicio de notificación de inserción de Microsoft (MPNS).</span><span class="sxs-lookup"><span data-stu-id="7d1ba-147">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="7d1ba-148">Esta característica está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-148">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-149">Use el cmdlet <strong>Test-CsFederatedPartner</strong> para probar la configuración de federación y el cmdlet <strong>Test-CsMCXPushNotification</strong> para probar las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="7d1ba-149">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7d1ba-150">Las notificaciones de inserción se usan para clientes móviles de Lync 2010 en dispositivos Apple y Windows Phone</span><span class="sxs-lookup"><span data-stu-id="7d1ba-150">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="7d1ba-151">La notificación de inserción es necesaria para clientes móviles de Lync 2013 en Windows Phone solo</span><span class="sxs-lookup"><span data-stu-id="7d1ba-151">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="7d1ba-152">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7d1ba-152">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-153"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuración de notificaciones de inserción en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d1ba-153"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d1ba-154">Configurar la directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="7d1ba-154">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-155">Use el cmdlet <strong>set-CsMobilityPolicy</strong> para permitir o deshabilitar:</span><span class="sxs-lookup"><span data-stu-id="7d1ba-155">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d1ba-156">Llamar a través del trabajo</span><span class="sxs-lookup"><span data-stu-id="7d1ba-156">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-157">Habilitar el audio IP y el vídeo IP</span><span class="sxs-lookup"><span data-stu-id="7d1ba-157">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="7d1ba-158">Requerir WiFi para el audio IP y/o el vídeo IP</span><span class="sxs-lookup"><span data-stu-id="7d1ba-158">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d1ba-159">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7d1ba-159">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7d1ba-160"><a href="lync-server-2013-configuring-mobility-policy.md">Configuración de la Directiva de movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7d1ba-160"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

