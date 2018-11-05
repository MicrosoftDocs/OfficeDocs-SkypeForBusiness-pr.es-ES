---
title: 'Lync Server 2013: tblADUpdates'
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48276478
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblADUpdates en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblADUpdate contiene los cambios de Servicios de dominio de Active Directory que aún no se han procesado en los últimos pasos de la sincronización de Active Directory.

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
<td><p>prinGuid</p></td>
<td><p>GUID, no NULL</p></td>
<td><p>GUID principal del objeto que ha cambiado.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384), no NULL</p></td>
<td><p>Nombre distintivo del objeto.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>bit, no NULL</p></td>
<td><p>True si ha cambiado al menos un atributo del objeto.</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>bit, no NULL</p></td>
<td><p>True si ha cambiado la pertenencia.</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>bit, no NULL</p></td>
<td><p>No se usa.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, no NULL</p></td>
<td><p>True si se ha eliminado el objeto.</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>datetime, no NULL</p></td>
<td><p>Marca de tiempo correspondiente al momento en que se insertó la fila.</p></td>
</tr>
</tbody>
</table>

