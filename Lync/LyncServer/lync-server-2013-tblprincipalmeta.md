---
title: 'Lync Server 2013: tblPrincipalMeta'
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48275831
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalMeta en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblPrincipalMeta contiene las entidades de seguridad que se deben actualizar en Servicios de dominio de Active Directory.

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
<td><p>prinAffiliationsDirty</p></td>
<td><p>bit, no NULL</p></td>
<td><p>True si hay que actualizar las afiliaciones de la entidad de seguridad.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesDirty</p></td>
<td><p>bit, no NULL</p></td>
<td><p>True si hay que actualizar los atributos de la entidad de seguridad.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, no NULL</p></td>
<td><p>True si la entidad de seguridad se ha eliminado.</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>Int</p></td>
<td><p>Número de intentos realizados hasta la fecha para actualizar la entidad de seguridad de AD DS.</p></td>
</tr>
<tr class="even">
<td><p>lastTry</p></td>
<td><p>Datetime</p></td>
<td><p>Marca de tiempo del último intento por actualizar la entidad de seguridad. Puede ser null si aún no se ha realizado ninguna actualización.</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>Datetime</p></td>
<td><p>Marca de tiempo de la siguiente actualización programada. Puede ser NULL si no se han programado más actualizaciones.</p></td>
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
<th>Columna</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clave externa con búsqueda en la tabla Node.nodeID.</p></td>
</tr>
</tbody>
</table>

