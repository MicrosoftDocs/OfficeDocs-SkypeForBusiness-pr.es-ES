---
title: 'Lync Server 2013: Proceso de implementación para movilidad'
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
ms.openlocfilehash: c6f9f7994981a860aaa02d4674d6a3248c3593d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="6ab7c-102">Proceso de implementación para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ab7c-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ab7c-103">_**Última modificación del tema:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="6ab7c-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="6ab7c-104">En esta sección se describe la secuencia de pasos necesarios para implementar la característica de movilidad de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="6ab7c-105">Proceso de implementación de movilidad</span><span class="sxs-lookup"><span data-stu-id="6ab7c-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ab7c-106">Fase</span><span class="sxs-lookup"><span data-stu-id="6ab7c-106">Phase</span></span></th>
<th><span data-ttu-id="6ab7c-107">Pasos</span><span class="sxs-lookup"><span data-stu-id="6ab7c-107">Steps</span></span></th>
<th><span data-ttu-id="6ab7c-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="6ab7c-108">Permissions</span></span></th>
<th><span data-ttu-id="6ab7c-109">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="6ab7c-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ab7c-110">Crear registros del sistema de nombres de dominio (DNS)</span><span class="sxs-lookup"><span data-stu-id="6ab7c-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6ab7c-111">Cree un registro CNAME de DNS interno o un (host, si IPv6, AAAA) para resolver la dirección URL interna del servicio de detección automática.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-112">Cree un CNAME DNS externo o un registro (host, si IPv6, AAAA) para resolver la dirección URL del servicio de detección automática externa.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ab7c-113">Administradores de dominio</span><span class="sxs-lookup"><span data-stu-id="6ab7c-113">Domain Admins</span></span></p>
<p><span data-ttu-id="6ab7c-114">Administradores</span><span class="sxs-lookup"><span data-stu-id="6ab7c-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creación de registros DNS para el servicio Detección automática en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6ab7c-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab7c-116">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="6ab7c-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-117">Agregar entradas de nombre alternativo de asunto a los siguientes certificados para admitir conexiones seguras para usuarios móviles:</span><span class="sxs-lookup"><span data-stu-id="6ab7c-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ab7c-118">Certificado de Director</span><span class="sxs-lookup"><span data-stu-id="6ab7c-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-119">Certificado del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="6ab7c-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-120">Certificado de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="6ab7c-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ab7c-121">Administrador local</span><span class="sxs-lookup"><span data-stu-id="6ab7c-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modificación de certificados para movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6ab7c-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ab7c-123">Configurar el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="6ab7c-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6ab7c-124">Asigne certificados actualizados con nombres alternativos de asunto a la escucha de capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="6ab7c-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-125">Vuelva a configurar la regla de publicación web para la dirección URL del servicio de detección automática externa.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-126">Asegúrese de que existe una regla de publicación web para la URL externa de servicios Web de Lync Server 2013 en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="6ab7c-127">O bien</span><span class="sxs-lookup"><span data-stu-id="6ab7c-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="6ab7c-128">Si elige usar HTTP para la solicitud de detección automática inicial y no actualiza las listas de nombres alternativos de asunto en los certificados, configure una nueva regla de publicación de web o vuelva a configurar una regla de publicación existente para el puerto 80 HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ab7c-129">Administrador local</span><span class="sxs-lookup"><span data-stu-id="6ab7c-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuración del proxy inverso para movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6ab7c-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab7c-131">Pruebe su implementación de movilidad para Lync 2010 Mobile con el servicio de movilidad de MCX</span><span class="sxs-lookup"><span data-stu-id="6ab7c-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-132">Ejecuta <strong>Test-CsMcxP2PIM</strong> para probar el envío de un mensaje instantáneo de una persona a otra.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="6ab7c-133">Consulte la documentación del cmdlet del shell de administración de Lync Server para <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> para obtener una lista completa de las opciones.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6ab7c-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Comprobar la implementación de la movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6ab7c-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ab7c-136">Pruebe su implementación de movilidad para clientes móviles de Lync 2013 mediante el componente Web de UCWA</span><span class="sxs-lookup"><span data-stu-id="6ab7c-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-137">Use el cmdlet <strong>Test-CsUcwaConference</strong> para probar y comprobar que los usuarios de prueba predefinidos o un par de usuarios reales pueden usar UCWA para crear y participar en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="6ab7c-138">Consulte la documentación del cmdlet del shell de administración de Lync Server para <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> para obtener una lista completa de las opciones.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6ab7c-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Comprobar la implementación de la movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6ab7c-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ab7c-141">Configurar notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="6ab7c-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6ab7c-142">Para servidores perimetrales de Lync Server 2013, agregue un proveedor de hospedaje de Lync Server online y configure la Federación de proveedores de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-143">Para servidores perimetrales de Lync Server 2010, agregue un proveedor de hospedaje de Lync Server online y configure la Federación de proveedores de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-144">Para los servidores perimetrales de Office Communications Server 2007 R2, agregue un socio federado.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-145">Si desea admitir notificaciones de inserción en una red Wi-Fi, configure una regla de Firewall entrante para el puerto TCP 5223.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-146">Use el cmdlet <strong>set-CsPushNotificationConfiguration</strong> para habilitar las notificaciones de inserción en el servicio de notificaciones push de Apple (APNS) y el servicio de notificaciones push de Microsoft (MPNS).</span><span class="sxs-lookup"><span data-stu-id="6ab7c-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="6ab7c-147">Esta característica está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-148">Use el cmdlet <strong>Test-CsFederatedPartner</strong> para probar la configuración de Federación y el cmdlet <strong>Test-CsMCXPushNotification</strong> para probar las notificaciones Push.</span><span class="sxs-lookup"><span data-stu-id="6ab7c-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6ab7c-149">Las notificaciones push se usan para clientes móviles de Lync 2010 en dispositivos Apple y Windows Phone</span><span class="sxs-lookup"><span data-stu-id="6ab7c-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="6ab7c-150">La notificación push es necesaria para los clientes móviles de Lync 2013 en Windows Phone solo</span><span class="sxs-lookup"><span data-stu-id="6ab7c-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="6ab7c-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6ab7c-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configurar las notificaciones de inserción en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6ab7c-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ab7c-153">Configurar la Directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="6ab7c-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-154">Use el cmdlet <strong>set-CsMobilityPolicy</strong> para permitir o impedir:</span><span class="sxs-lookup"><span data-stu-id="6ab7c-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ab7c-155">Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="6ab7c-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-156">Habilitar el audio IP y el video IP</span><span class="sxs-lookup"><span data-stu-id="6ab7c-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="6ab7c-157">Requerir Wi-Fi para audio IP y/o video IP</span><span class="sxs-lookup"><span data-stu-id="6ab7c-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ab7c-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6ab7c-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6ab7c-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuración de la directiva de movilidad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6ab7c-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

