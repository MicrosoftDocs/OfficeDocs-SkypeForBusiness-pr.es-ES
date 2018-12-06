---
title: 'Lync Server 2013: tblPrincipal'
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48275752
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipal enn Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla tblPrincipal contiene todas las entidades de seguridad, incluidos usuarios, carpetas y grupos.

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
<td><p>prinGuid</p></td>
<td><p>GUID, no NULL</p></td>
<td><p>GUID de la entidad de seguridad. Se usa generalmente como clave principal alternativa, ya que su significado llega al espacio de Servicios de dominio de Active Directory (el GUID de una entidad de seguridad almacenada en la memoria caché es igual que el GUID del objeto de Active Directory correspondiente).</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), no NULL</p></td>
<td><p>URI de la entidad de seguridad. El esquema SIP se usa para los usuarios, mientras que ma-grp se usa para prácticamente todo lo demás.</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre común. Usado solo por los tipos de usuario.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nombre para mostrar. Usado solo por los tipos de usuario.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre de la compañía. Usado solo por los tipos de usuario.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Correo electrónico. Usado solo por los tipos de usuario.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar(384)</p></td>
<td><p>Nombre de dominio del objeto de Active Directory del que la entidad de seguridad es una versión en caché. Puede tener un valor NULL en los tipos que no sean objetos de Active Directory (por ejemplo, usuarios de sistema).</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre principal de usuario (UPN) del usuario. Usado solo por los tipos de usuario normales.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint, no NULL</p></td>
<td><ul>
<li><p>0: la entidad de seguridad está activa.</p></li>
<li><p>1: la entidad de seguridad está deshabilitada porque las funciones SIP del usuario están deshabilitadas.</p></li>
<li><p>2: la entidad de seguridad se elimina porque el objeto de AD asociado se ha eliminado.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, no NULL</p></td>
<td><p>Tipo de la entidad de seguridad (de la tabla tblPrincipalType).</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>Asignación de grupos de servidores de Lync para la entidad de seguridad.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>Directiva del Servidor de chat persistente para el usuario, si la directiva de tipo de etiqueta está presente.</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>Int</p></td>
<td><p>Identificador de la entidad de seguridad del creador.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Marca de tiempo de la hora de creación.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>Int</p></td>
<td><p>Identificador de la entidad de seguridad que actualizó esto por última vez.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Marca de tiempo de la última actualización.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime, no NULL</p></td>
<td><p>Fecha y hora de la última actualización de sincronización de Active Directory para la entidad de seguridad.</p></td>
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
<td><p>prinTypeID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblPrincipalType.ptypeID.</p></td>
</tr>
</tbody>
</table>

