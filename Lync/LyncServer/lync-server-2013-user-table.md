---
title: 'Lync Server 2013: Tabla User'
TOCTitle: Tabla User
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48275565
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla User en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla User es una tabla de apoyo donde se almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica a este usuario.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Única</p></td>
<td><p>Cadena del URI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URIType</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>1 es un tipo de URI desconocido.</p>
<p>2 es un URI de usuario.</p>
<p>4 es un URI de conferencia.</p>
<p>8 es un URI de teléfono.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Inquilino del usuario, con referencia a la tabla Tenant.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Última marca de tiempo en la que el usuario tuvo una llamada de audio de mala calidad.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>Datetime</p></td>
<td><p></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
</tbody>
</table>

