---
title: 'Lync Server 2013: tblPreference'
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48277258
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPreference en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblPreference contiene las preferencias de cliente de los usuarios. Normalmente, la utilizan los clientes antes de Lync 2013.

### Columnas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prefLabel</p></td>
<td><p>nvarchar (255), no NULL</p></td>
<td><p>Etiqueta con un formato como: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</p></td>
</tr>
<tr class="even">
<td><p>prefSeqID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Número secuencial (por etiqueta) para el control de versiones.</p></td>
</tr>
<tr class="odd">
<td><p>prefContent</p></td>
<td><p>nvarchar(max)</p></td>
<td><p>Contenido codificado.</p></td>
</tr>
<tr class="even">
<td><p>lastModifiedBy</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad que ha actualizado la preferencia.</p></td>
</tr>
</tbody>
</table>


### Tecla

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prefLabel, prefSeqID&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>

