---
title: 'Lync Server 2013: Requisitos DNS para un servidor Standard Edition'
TOCTitle: Requisitos DNS para un servidor Standard Edition
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48275402
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos DNS para un servidor Standard Edition en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de servidores Standard Edition.

## Registros DNS para servidores Standard Edition

En la siguiente tabla se especifican los requisitos de DNS para implementar un servidor de Lync Server 2013 Standard Edition.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Escenario de implementación</th>
<th>Requisito de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor Standard Edition</p></td>
<td><p>Un registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor como su dirección IP.</p></td>
</tr>
<tr class="even">
<td><p>Inicio de sesión de clientes automático</p></td>
<td><p>Por cada dominio SIP admitido, un registro SRV para _sipinternaltls._tcp.&lt;dominio&gt; en el puerto 5061 que se asigna al FQDN del servidor Standard Edition responsable de autenticar y redirigir las solicitudes de los clientes para el inicio de sesión. Para obtener información detallada, vea <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Requisitos DNS para inicio de sesión automática del cliente en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Detección del servicio web de actualización de dispositivos por los dispositivos de comunicaciones unificadas (UC)</p></td>
<td><p>Un registro A interno con el nombre ucupdates-r2.&lt;dominio SIP&gt; que se resuelve en la dirección IP del servidor Standard Edition que hospeda el Servicio web de actualización de dispositivos. En una situación en la que un dispositivo de comunicaciones unificadas esté activado, pero nunca ningún usuario se haya registrado en él, el registro A permite al dispositivo detectar el servidor que hospeda el Servicio web de actualización de dispositivos y obtener actualizaciones. En caso contrario, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión. Para obtener información detallada, vea <a href="lync-server-2013-device-update-web-service.md">Servicio web de actualización de dispositivos en Lync Server 2013</a> en la documentación de operaciones.</p></td>
</tr>
<tr class="even">
<td><p>Un proxy inverso compatible con el tráfico HTTP</p></td>
<td><p>Un registro A externo que resuelve el FQDN externo de la granja de servidores web en la dirección IP externa del proxy inverso. Los clientes y los dispositivos de CU usan este registro para conectarse al proxy inverso. Para más información, consulte <a href="lync-server-2013-determine-dns-requirements.md">Determinar los requisitos DNS para Lync Server 2013</a> en la documentación de planeación.</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[Requisitos DNS para inicio de sesión automática del cliente en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  

#### Otros recursos

[Servicio web de actualización de dispositivos en Lync Server 2013](lync-server-2013-device-update-web-service.md)

