---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24f963b34ef6184675e724496d7d45ca1d40d27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>tblPrincipal enn Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblPrincipal contiene todos los principales, incluidos los usuarios, las carpetas y los grupos.

### <a name="columns"></a>Columnas

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
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR principal.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID, not null</p></td>
<td><p>GUID principal. Esto se usa ampliamente como una clave principal alternativa porque su significado pasa a ser el espacio de servicios de dominio de Active Directory. (El GUID de un principal en caché es igual al GUID de objeto de Active Directory correspondiente).</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>URI principal. El esquema SIP se usa para los usuarios y el mA-GRP se usa para casi todos los demás.</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nombre común. Solo se usan los tipos de usuario.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>Nombre para mostrar. Solo se usan los tipos de usuario.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nombre de la empresa. Solo se usan los tipos de usuario.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Correo electrónico. Solo se usan los tipos de usuario.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>Nombre de dominio del objeto de Active Directory del que el principal es una versión almacenada en caché. Puede ser null para los tipos que no son objetos de Active Directory (como usuarios del sistema).</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nombre principal de usuario (UPN) del usuario. Solo lo usan los tipos de usuario normales.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint, not null</p></td>
<td><ul>
<li><p>0: la principal está activa.</p></li>
<li><p>1: la entidad de la identidad está deshabilitada porque las funciones SIP del usuario están deshabilitadas.</p></li>
<li><p>2: se eliminó el capital porque el objeto de AD asociado se ha eliminado.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, not null</p></td>
<td><p>Tipo principal (de la tabla tblPrincipalType).</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>ENT</p></td>
<td><p>Asignación de grupo de Lync para la entidad de identidad.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>ENT</p></td>
<td><p>Valor de la Directiva del servidor de chat persistente para usuario, si la Directiva de tipo de etiqueta está presente.</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>IDENTIFICADOR principal del creador.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>BIGINT, not null</p></td>
<td><p>Marca de tiempo de la hora de creación.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>IDENTIFICADOR de la entidad de identidad que la actualizó por última vez.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>BIGINT, not null</p></td>
<td><p>Marca de tiempo de la última actualización.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>DateTime, not null</p></td>
<td><p>Fecha y hora de la última actualización de sincronización de Active Directory para la entidad de identidad.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Sus

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
<td><p>Clave externa con la búsqueda en la tabla tblPrincipalType. ptypeID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

