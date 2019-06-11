---
title: 'Lync Server 2013: cambios realizados por Grant-CsSetupPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Cambios realizados por Grant-CsSetupPermission en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-20_

Para delegar la configuración, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa de Active Directory específica, lo que permite a los miembros del grupo RTCUniversalServerAdmins de esa OU instalar Lync Server 2013 de la el dominio no es miembro del grupo de administradores de dominio.

El cmdlet **Grant-CsSetupPermission** concede los permisos de grupo RTCUniversalServerAdmins en una unidad organizativa, como se especifica en la tabla siguiente:

### <a name="permissions-granted-to-objects-in-the-ou"></a>Permisos otorgados a objetos de la OU

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Los permisos se aplican a:</th>
<th>Los permisos concedidos son los siguientes:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Leer servicePrincipalName</p></li>
<li><p>Escribir servicePrincipalName</p></li>
<li><p>Eliminar árbol</p></li>
<li><p>Replicar cambios de directorio</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos serviceConnectionPoint descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Permisos de lectura</p></li>
<li><p>Permisos de escritura</p></li>
<li><p>Crear elemento secundario</p></li>
<li><p>Eliminar hijo</p></li>
<li><p>Contenido de la lista</p></li>
<li><p>Write (propiedad)</p></li>
<li><p>Propiedad de lectura</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos descendientes msRTCSIP-Server</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Write (propiedad)</p></li>
<li><p>Propiedad de lectura</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos descendientes msRTCSIP-webcomponents</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Write (propiedad)</p></li>
<li><p>Propiedad de lectura</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos descendientes msRTCSIP-MCU</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Write (propiedad)</p></li>
<li><p>Propiedad de lectura</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos descendientes msRTCSIP-MediationServer</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Write (propiedad)</p></li>
<li><p>Propiedad de lectura</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos descendientes msRTCSIP-ApplicationServer</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Write (propiedad)</p></li>
<li><p>Propiedad de lectura</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos descendientes msRTCSIP-punto de la</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Write (propiedad)</p></li>
<li><p>Propiedad de lectura</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos de equipo descendientes</p></td>
<td><p>Acceso especial para serviceConnectionPoint:</p>
<ul>
<li><p>Crear objetos secundarios</p></li>
<li><p>Eliminar objetos secundarios</p></li>
<li><p>Eliminar árbol</p></li>
</ul>
<p>Acceso especial para información pública:</p>
<ul>
<li><p>Propiedad de lectura</p></li>
</ul>
<p>Acceso especial para el nombre de host DNS:</p>
<ul>
<li><p>Propiedad de lectura</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

