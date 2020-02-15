---
title: 'Lync Server 2013: cambios realizados por la preparación del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Cambios realizados por la preparación del dominio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2010-10-18_

En la tabla siguiente se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. Todas las ACE se heredan, salvo que se indique lo contrario.

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
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-servicios</th>
<th>Usuarios autenticados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Container (no se hereda)</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet User-Account-Restrictions</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet Personal-Information</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet General-Information</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet Public-Information</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sí</strong></p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet RTCPropertySet</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Write User Property Proxy-Addresses</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Write User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Write User PropertySet RTCPropertySet</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Read PropertySet DS-Replication-Get-Changes de todos los objetos de Active Directory</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sí</strong></p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se enumeran las ACE que crea la preparación del dominio en los tres contenedores integrados: usuarios, equipos y controladores de dominio. Todas las ACE se heredan, salvo que se indique lo contrario.

### <a name="aces-added-to-built-in-containers"></a>Entradas ACE agregadas a los contenedores integrados

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Container (no se hereda)</p></td>
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

