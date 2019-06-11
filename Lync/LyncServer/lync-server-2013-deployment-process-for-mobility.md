---
title: 'Lync Server 2013: Proceso de implementación para movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dec6f1e089a9418db3d8ece1f390615226687cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Proceso de implementación para movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

En esta sección se describe la secuencia de pasos necesarios para implementar la característica de movilidad de Lync Server 2013.

### <a name="mobility-deployment-process"></a>Proceso de implementación de movilidad

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Permisos</th>
<th>Documentación de implementación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Crear registros del sistema de nombres de dominio (DNS)</p></td>
<td><ul>
<li><p>Cree un registro CNAME de DNS interno o un (host, si IPv6, AAAA) para resolver la dirección URL interna del servicio de detección automática.</p></li>
<li><p>Cree un CNAME DNS externo o un registro (host, si IPv6, AAAA) para resolver la dirección URL del servicio de detección automática externa.</p></li>
</ul></td>
<td><p>Administradores de dominio</p>
<p>Administradores</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creación de registros DNS para el servicio Detección automática en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Modificar certificados</p></td>
<td><p>Agregar entradas de nombre alternativo de asunto a los siguientes certificados para admitir conexiones seguras para usuarios móviles:</p>
<ul>
<li><p>Certificado de Director</p></li>
<li><p>Certificado del grupo de servidores front-end</p></li>
<li><p>Certificado de proxy inverso</p></li>
</ul></td>
<td><p>Administrador local</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modificación de certificados para movilidad en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurar el proxy inverso</p></td>
<td><ul>
<li><p>Asigne certificados actualizados con nombres alternativos de asunto a la escucha de capa de sockets seguros (SSL).</p></li>
<li><p>Vuelva a configurar la regla de publicación web para la dirección URL del servicio de detección automática externa.</p></li>
<li><p>Asegúrese de que existe una regla de publicación web para la URL externa de servicios Web de Lync Server 2013 en el grupo de servidores front-end.</p></li>
</ul>
<p>O bien</p>
<ul>
<li><p>Si elige usar HTTP para la solicitud de detección automática inicial y no actualiza las listas de nombres alternativos de asunto en los certificados, configure una nueva regla de publicación de web o vuelva a configurar una regla de publicación existente para el puerto 80 HTTP.</p></li>
</ul></td>
<td><p>Administrador local</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuración del proxy inverso para movilidad en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Pruebe su implementación de movilidad para Lync 2010 Mobile con el servicio de movilidad de MCX</p></td>
<td><p>Ejecuta <strong>Test-CsMcxP2PIM</strong> para probar el envío de un mensaje instantáneo de una persona a otra.</p>
<p>Consulte la documentación del cmdlet del shell de administración de Lync Server para <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> para obtener una lista completa de las opciones.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Comprobar la implementación de la movilidad en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Pruebe su implementación de movilidad para clientes móviles de Lync 2013 mediante el componente Web de UCWA</p></td>
<td><p>Use el cmdlet <strong>Test-CsUcwaConference</strong> para probar y comprobar que los usuarios de prueba predefinidos o un par de usuarios reales pueden usar UCWA para crear y participar en una conferencia.</p>
<p>Consulte la documentación del cmdlet del shell de administración de Lync Server para <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> para obtener una lista completa de las opciones.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Comprobar la implementación de la movilidad en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar notificaciones de inserción</p></td>
<td><ul>
<li><p>Para servidores perimetrales de Lync Server 2013, agregue un proveedor de hospedaje de Lync Server online y configure la Federación de proveedores de hospedaje.</p></li>
<li><p>Para servidores perimetrales de Lync Server 2010, agregue un proveedor de hospedaje de Lync Server online y configure la Federación de proveedores de hospedaje.</p></li>
<li><p>Para los servidores perimetrales de Office Communications Server 2007 R2, agregue un socio federado.</p></li>
<li><p>Si desea admitir notificaciones de inserción en una red Wi-Fi, configure una regla de Firewall entrante para el puerto TCP 5223.</p></li>
<li><p>Use el cmdlet <strong>set-CsPushNotificationConfiguration</strong> para habilitar las notificaciones de inserción en el servicio de notificaciones push de Apple (APNS) y el servicio de notificaciones push de Microsoft (MPNS). Esta característica está deshabilitada de forma predeterminada.</p></li>
<li><p>Use el cmdlet <strong>Test-CsFederatedPartner</strong> para probar la configuración de Federación y el cmdlet <strong>Test-CsMCXPushNotification</strong> para probar las notificaciones Push.</p>
<div>

> [!NOTE]  
> Las notificaciones push se usan para clientes móviles de Lync 2010 en dispositivos Apple y Windows Phone<BR>La notificación push es necesaria para los clientes móviles de Lync 2013 en Windows Phone solo


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Configurar las notificaciones de inserción en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurar la Directiva de movilidad</p></td>
<td><p>Use el cmdlet <strong>set-CsMobilityPolicy</strong> para permitir o impedir:</p>
<ul>
<li><p>Vía trabajo</p></li>
<li><p>Habilitar el audio IP y el video IP</p></li>
<li><p>Requerir Wi-Fi para audio IP y/o video IP</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Configuración de la directiva de movilidad en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

