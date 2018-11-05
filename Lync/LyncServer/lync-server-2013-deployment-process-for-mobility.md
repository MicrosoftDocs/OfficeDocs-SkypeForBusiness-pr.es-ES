---
title: 'Lync Server 2013: Proceso de implementación para movilidad'
TOCTitle: Proceso de implementación para movilidad
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48275355
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proceso de implementación para movilidad en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

En esta sección se describe la secuencia de pasos necesarios para implementar la característica de movilidad de Lync Server 2013.

### Proceso de implementación de movilidad

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
<td><p>Crear registros del sistema de nombre de domino (DNS)</p></td>
<td><ul>
<li><p>Crear un registro CNAME o A (host, si IPv6, AAAA) de DNS interno para resolver la URL del servicio de Detección automática interna.</p></li>
<li><p>Crear un registro CNAME o A (host, si IPv6, AAAA) de DNS interno para resolver la URL del servicio de Detección automática externa.</p></li>
</ul></td>
<td><p>Administradores de dominio</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creación de registros DNS para el servicio Detección automática en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Modificar certificados</p></td>
<td><p>Agregue entradas de nombre alternativo de sujeto a los siguientes certificados para admitir conexiones seguras para usuarios móviles:</p>
<ul>
<li><p>Certificado de Director</p></li>
<li><p>Certificado de Grupo de servidores front-end</p></li>
<li><p>Certificado de proxy inverso</p></li>
</ul></td>
<td><p>Administrador local</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modificación de certificados para movilidad en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurar el proxy inverso</p></td>
<td><ul>
<li><p>Asigne certificados actualizados con nombres alternativos de sujeto a la escucha de la capa de sockets seguros (SSL).</p></li>
<li><p>Vuelva a configurar la regla de publicación web para la URL del servicio Detección automática externo.</p></li>
<li><p>Asegúrese de que haya una regla de publicación web para la URL de servicios web externos de Lync Server 2013 en su Grupo de servidores front-end.</p></li>
</ul>
<p>O bien</p>
<ul>
<li><p>Si opta por usar HTTP para la solicitud inicial de Detección automática y no actualiza las listas de nombres alternativos del sujeto en los certificados, configure una nueva regla de publicación web para el puerto 80 HTTP o vuelva a configurar una existente.</p></li>
</ul></td>
<td><p>Administrador local</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuración del proxy inverso para movilidad en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Probar la implementación de movilidad de Lync 2010 Mobile mediante el servicio de movilidad Mcx</p></td>
<td><p>Ejecute <strong>Test-CsMcxP2PIM</strong> para probar el envío de un mensaje instantáneo de una persona a otra.</p>
<p>Consulte la documentación sobre el cmdlet Shell de administración de Lync Server para <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> para obtener una lista completa de opciones.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Comprobar la implementación de la movilidad en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Probar la implementación de movilidad de los clientes móviles de Lync 2013 mediante los componentes web de UCWA</p></td>
<td><p>Use el cmdlet <strong>Test-CsUcwaConference</strong> para probar y comprobar que usuarios de prueba predefinidos o un par de usuarios reales pueden usar UCWA para crear una conferencia y participar en ella.</p>
<p>Consulte la documentación sobre el cmdlet Shell de administración de Lync Server para <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> para obtener una lista completa de opciones.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Comprobar la implementación de la movilidad en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar notificaciones de inserción</p></td>
<td><ul>
<li><p>Para Lync Server 2013Servidores perimetrales, agregue un proveedor de hospedaje en línea de Lync Server y configure la federación del proveedor de hospedaje.</p></li>
<li><p>Para Lync Server 2010  Servidores perimetrales, agregue un proveedor de hospedaje en línea de Lync Server y configure la federación del proveedor de hospedaje.</p></li>
<li><p>Para Office Communications Server 2007 R2Servidores perimetrales, agregue un socio federado.</p></li>
<li><p>Si desea admitir notificaciones de inserción a través de una red Wi-Fi, configure una regla de salida del firewall para el puerto TCP 5223.</p></li>
<li><p>Use el cmdlet <strong>Set-CsPushNotificationConfiguration</strong> para habilitar notificaciones de inserción para el servicio de notificación de inserción de Apple (APNS) y el servicio de notificación de inserción de Microsoft (MPNS). Esta característica está deshabilitada de forma predeterminada.</p></li>
<li><p>Use el cmdlet <strong>Test-CsFederatedPartner</strong> para probar la configuración de federación y el cmdlet <strong>Test-CsMCXPushNotification</strong> para probar las notificaciones de inserción.</p>
<div>

> [!NOTE]
> Las notificaciones de inserción se usan para los clientes de Lync 2010 Mobile en dispositivos Apple y en Windows Phone<BR>La característica de notificación de inserción es necesaria para los clientes móviles de Lync 2013 solo en Windows Phone


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Configurar las notificaciones de inserción en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurar la directiva de movilidad</p></td>
<td><p>Use el cmdlet <strong>Set-CsMobilityPolicy</strong> para permitir o no permitir lo siguiente:</p>
<ul>
<li><p>Vía trabajo</p></li>
<li><p>Habilitar audio IP y vídeo IP</p></li>
<li><p>Requerir WiFi para audio IP y/o vídeo IP</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Configuración de la directiva de movilidad en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

