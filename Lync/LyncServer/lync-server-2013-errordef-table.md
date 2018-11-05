---
title: 'Lync Server 2013: Tabla ErrorDef'
TOCTitle: Tabla ErrorDef
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48275595
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla ErrorDef en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla ErrorDef almacena información sobre todos los tipos de error que pueden producirse. Cada registro es un tipo de error.


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
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Número de identificador único que identifica este tipo de error.</p></td>
</tr>
<tr class="even">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Código de respuesta SIP estándar asociado a este error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Identificador de diagnóstico de Microsoft.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Externa</p></td>
<td><p>Tipo de la llamada. Referencia a <a href="lync-server-2013-calltype-table.md">Tabla CallType en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varbinary(33)</p></td>
<td><p> </p></td>
<td><p>Tipo de solicitud que ha generado errores.</p>
<p>Estos datos pueden convertirse en formato de texto con esta sintaxis:</p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varbinary(257)</p></td>
<td><p> </p></td>
<td><p>Tipo de contenido de la solicitud que ha generado errores.</p>
<p>Estos datos pueden convertirse a formato de texto utilizando: cast(cast(ContentType as varbinary(max)) as varchar(max))</p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

