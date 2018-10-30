---
title: 'Lync Server 2013: Tabla ConferenceUris'
TOCTitle: Tabla ConferenceUris
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48276392
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla ConferenceUris en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla ConferenceUris es una tabla auxiliar donde se guarda una lista de las diversas URI de conferencia que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla corresponde a una URI de conferencia.


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Principal</p></td>
<td><p>Marca de tiempo, interna utilizada.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica esta URI de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p></p></td>
<td><p>URI de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Checksum</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Suma de comprobación de ConferenceUri. Se utiliza para acelerar las búsquedas en bases de datos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Tipo de URI, como por ejemplo conf:chat para conferencia de mensajería instantánea, o conf:audio-video para conferencia A/V. Consulte la tabla <a href="lync-server-2013-uritypes-table.md">Tabla UriTypes en Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

