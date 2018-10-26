---
title: 'Lync Server 2013: Tabla Mcus'
TOCTitle: Tabla Mcus
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48274734
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Mcus en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Mcus es una tabla auxiliar. Cada registro almacena información acerca de uno de los servicios de conferencia. Entre ellos, se incluyen el servicio de conferencia de mensajería instantánea y el servicio de conferencia con telefonía (que se ejecutan como procesos en los servidores front-end), y el servicio de conferencia web y el servicio de conferencia A/V.


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
<td><p><strong>McuId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este servidor de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><strong>McuTypeId</strong></p></td>
<td><p>inyint</p></td>
<td><p>Externa</p></td>
<td><p>Tipo de servidor de conferencia, como conf:chat (para mensajería instantánea) o conf:audio-video. Remítase a la <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

