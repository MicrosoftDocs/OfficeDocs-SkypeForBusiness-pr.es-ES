---
title: Requisitos DNS para servidores Standard Edition
TOCTitle: Requisitos DNS para servidores Standard Edition
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48275009
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos DNS para servidores Standard Edition

 

_**Última modificación del tema:** 2015-03-09_

En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para la implementación de servidores Standard Edition.

## Registros DNS para los servidores Standard Edition

En la tabla siguiente se especifican los requisitos de DNS para la implementación de un servidor Lync Server 2013 Standard Edition.

### Requisitos de DNS para un servidor Standard Edition

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
<td><p>Inicio de sesión automático de los clientes</p></td>
<td><p>Para cada dominio SIP admitido, un registro SRV para _sipinternaltls._tcp.<em>&lt;domain&gt;</em> por el puerto 5061 que asigna el FQDN del servidor Standard Edition que autentica y redirige las solicitudes de inicio de sesión del cliente. Para obtener más información, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Requisitos DNS para inicio de sesión automática del cliente en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Detección del servicio web de actualización de dispositivos mediante dispositivos de comunicaciones unificadas (UC)</p></td>
<td><p>Un registro A interno con el nombre ucupdates-r2.<em>&lt;SIP domain&gt;</em> que se resuelve como la dirección IP del servidor Standard Edition que hospeda el servicio web de actualización de dispositivos. En una situación en la que un dispositivo de comunicaciones unificadas esté activado, pero ningún usuario se haya registrado nunca en él, el registro A permite al dispositivo detectar el servidor que hospeda el servicio web de actualización de dispositivos y obtener actualizaciones. En caso contrario, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.</p></td>
</tr>
<tr class="even">
<td><p>Un proxy inverso que admita tráfico HTTP</p></td>
<td><p>Un registro A externo que resuelva el FQDN externo de la granja de servidores web en la dirección IP externa del proxy inverso. Los clientes y los dispositivos de comunicaciones unificadas usan este registro para conectarse al proxy inverso. Para obtener más información, consulte <a href="lync-server-2013-determine-dns-requirements.md">Determinar los requisitos DNS para Lync Server 2013</a> en la documentación sobre planeación.</p></td>
</tr>
</tbody>
</table>

