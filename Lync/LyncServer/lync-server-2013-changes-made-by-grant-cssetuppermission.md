---
title: 'Lync Server 2013: cambios realizados por Grant-CsSetupPermission'
description: 'Lync Server 2013: cambios realizados por Grant-CsSetupPermission.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543606"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Cambios realizados por Grant-CsSetupPermission en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-20_

Para delegar la configuración, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa (OU) de Active Directory específica, habilitando a los miembros del grupo RTCUniversalServerAdmins en dicha unidad organizativa que instalen Lync Server 2013 en el dominio especificado sin ser miembros del grupo administradores del dominio.

El cmdlet **Grant-CsSetupPermission** otorga los permisos del grupo RTCUniversalServerAdmins en una unidad organizativa, como se especifica en la siguiente tabla:

### <a name="permissions-granted-to-objects-in-the-ou"></a>Permisos otorgados a los objetos en la unidad organizativa

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Los permisos se aplican a:</th>
<th>Los permisos otorgados son:</th>
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
<li><p>Cambios de directorio de replicación</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos serviceConnectionPoint descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Leer permisos</p></li>
<li><p>Escribir permisos</p></li>
<li><p>Crear elemento secundario</p></li>
<li><p>Eliminar elemento secundario</p></li>
<li><p>Mostrar contenido</p></li>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-Server descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP-WebComponents descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-MCU descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP-MediationServer descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-ApplicationServer descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
<li><p>Eliminar árbol</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP-ConnectionPoint descendientes</p></td>
<td><p>Acceso especial:</p>
<ul>
<li><p>Escribir propiedad</p></li>
<li><p>Leer propiedad</p></li>
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
<p>Acceso especial a la información pública:</p>
<ul>
<li><p>Leer propiedad</p></li>
</ul>
<p>Acceso especial para el nombre de host DNS:</p>
<ul>
<li><p>Leer propiedad</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

