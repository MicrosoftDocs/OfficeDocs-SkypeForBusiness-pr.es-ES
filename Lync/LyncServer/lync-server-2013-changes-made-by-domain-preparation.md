---
title: 'Lync Server 2013: cambios realizados por la preparación del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b674e2c3d65aeda22838dca08ac5b016fa83359
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Cambios realizados por la preparación del dominio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2010-10-18_

En la siguiente tabla se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. A menos que se indique lo contrario, se heredan todas las ACE.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>Entradas ACE agregadas a la raíz del dominio

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ENTRADA</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-servicios</th>
<th>Autenticados: usuarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Leer contenedor (no heredado)</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Leer usuario de la PropertySet de la cuenta de usuario-restricciones</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Leer usuario PropertySet información personal</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Leer usuario de la petición general-información</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Leer usuario PropertySet Public-Information</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Leer usuario PropertySet RTCUserSearchProperty-set</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sí</strong></p></td>
</tr>
<tr class="odd">
<td><p>Leer el usuario PropertySet RTCPropertySet</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Escribir propiedad de usuario proxy: direcciones</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Escribir el usuario de la RTCUserSearchProperty</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Escribir el usuario PropertySet RTCPropertySet</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Lea el complemento de DS-replicación-obtener-cambios de todos los objetos de Active Directory</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se enumeran las ACE que crea el dominio de preparación en los tres contenedores integrados: usuarios, equipos y controladores de dominio. A menos que se indique lo contrario, se heredan todas las ACE.

### <a name="aces-added-to-built-in-containers"></a>Entradas ACE agregadas a contenedores integrados

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ENTRADA</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Leer contenedor (no heredado)</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p><strong>Sí</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

