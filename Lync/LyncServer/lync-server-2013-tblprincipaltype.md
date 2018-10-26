---
title: 'Lync Server 2013: tblPrincipalType'
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48274874
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalType en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblPrincipalType contiene los tipos de entidades de seguridad que se utilizan para clasificar lo que aparece en la tabla tblPrincipal.

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
<td><p>ptypeID</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Id. del tipo de entidad de seguridad</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>Descripción del tipo.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, no NULL</p></td>
<td><p>Verdadero si el tipo corresponde a las entidades de seguridad utilizadas para fines internos.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, no NULL</p></td>
<td><p>Verdadero si el tipo es un tipo de usuario.</p></td>
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
<td><p>ptypeID</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


### Valores de las entidades de seguridad

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Id.</th>
<th>Rol</th>
<th>Descripción</th>
<th>Usuario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Any</p></td>
<td><p>Entidad de seguridad genérica sin tipo conocido. No se utiliza en la tabla tblPrincipal.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>Entidad de seguridad genérica de tipo de usuario. No se utiliza en la tabla tblPrincipal.</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>Entidad de seguridad genérica con semántica de grupo. No se utiliza en la tabla tblPrincipal.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>SystemUser</p></td>
<td><p>Entidad de seguridad utilizada internamente por Servidor de chat persistente.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>User</p></td>
<td><p>Usuario habitual.</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>DC</p></td>
<td><p>Controlador del dominio Servicios de dominio de Active Directory.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>Group</p></td>
<td><p>Grupo de seguridad de Active Directory.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>Folder</p></td>
<td><p>Unidad organizativa o contenedor de Active Directory.</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Vea también

#### Conceptos

[tblPrincipal enn Lync Server 2013](lync-server-2013-tblprincipal.md)

