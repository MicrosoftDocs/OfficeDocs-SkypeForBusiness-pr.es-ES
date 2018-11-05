---
title: 'Lync Server 2013: Tabla Registration'
TOCTitle: Tabla Registration
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48274311
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Registration en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro representa un evento de registro de usuario.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Clave o índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Hora de la solicitud de sesión. Se usa en combinación con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal, Externa</p></td>
<td><p>Número para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> como identificación única de una sesión. Para más información, vea la <a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador de usuario. Remítase a la <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>GUID para identificar un extremo de registro. Por lo general, el evento de registro del mismo equipo y del mismo usuario tendrá el mismo identificador de extremo. Los equipos diferentes tienen un identificador de extremo distinto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Id. usado para diferenciar registros que implican al mismo usuario y al mismo extremo.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Versión de cliente del usuario actual. Remítase a la <a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del servidor registrador utilizado para el registro. Remítase a la <a href="lync-server-2013-servers-table.md">Tabla Servers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Identificador del grupo en el que se capturó la sesión. Referencia a la <a href="lync-server-2013-pools-table.md">Tabla Pools en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Servidor perimetral que se utiliza para el registro. Remítase a la <a href="lync-server-2013-edgeservers-table.md">Tabla EdgeServers en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Bit</p></td>
<td><p></p></td>
<td><p>Si el usuario inició sesión de forma interna o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Si UserService está disponible o no.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Si el registro se realizó con el registrador principal o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indica si el usuario se registra o no con una aplicación de sucursal con funciones de supervivencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Hora de registro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Hora de anulación del registro.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Código de respuesta de la solicitud de registro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Identificador de diagnóstico de la solicitud de registro. Indica ese tipo de información de diagnóstico.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dispositivo del cual proviene la solicitud de registro. Remítase a la <a href="lync-server-2013-devices-table.md">Tabla Devices en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externa</p></td>
<td><p>Motivo de la anulación del registro, como &quot;iniciado por usuario&quot;, &quot;registro expirado&quot;, &quot;error de cliente&quot;, etc. Remítase a la <a href="lync-server-2013-deregistertype-table.md">Tabla DeRegisterType en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dirección IP</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Dirección IP del extremo con el que está registrado el usuario. Esta puede ser una dirección IPv4 o una dirección IPv6.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

