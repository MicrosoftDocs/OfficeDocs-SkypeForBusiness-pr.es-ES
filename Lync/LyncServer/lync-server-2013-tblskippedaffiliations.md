---
title: 'Lync Server 2013: tblSkippedAffiliations'
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48274391
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblSkippedAffiliations en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (generalmente, por errores de acceso de los Servicios de dominio de Active Directory).

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
<td><p>prinID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad</p></td>
</tr>
<tr class="even">
<td><p>affDescription</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Cadena que identifica la afiliación.</p>
<p>El formato es: guid: <em>{0}</em> uri: <em>{1}</em> &gt; id: <em>{2}</em></p></td>
</tr>
<tr class="odd">
<td><p>updatedBy</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad que actualizó esta fila. Siempre es 1 (usuario del sistema) porque la sincronización de Active Directory es el único origen de estas entradas.</p></td>
</tr>
</tbody>
</table>


### Teclas

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Columnas</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinID, affDescription&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clave externa con búsqueda en la tabla Node.nodeID.</p></td>
</tr>
</tbody>
</table>

