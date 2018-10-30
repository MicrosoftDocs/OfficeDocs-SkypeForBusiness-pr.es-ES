---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48274397
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalMemberDifference en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblPrincipalMemberDifference contiene cambios en la pertenencia a grupos (tanto de los miembros que se agregaron como de los que se quitaron) que aún no se procesaron en los pasos de sincronización de Servicios de dominio de Active Directory posteriores.

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
<td><p>GUID de entidad de seguridad del grupo modificado.</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre distintivo del miembro.</p></td>
</tr>
<tr class="odd">
<td><p>memberRemoved</p></td>
<td><p>bit, no NULL</p></td>
<td><p>False si se agregó el miembro. True si se quitó el miembro.</p></td>
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
<td><p>&lt;prinGuid, memberADPath&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>

