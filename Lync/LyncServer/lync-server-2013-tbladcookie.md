---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a>tblADCookie en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-25_

tblADCookie contiene las cookies de sincronización LDAP (Protocolo ligero de acceso a directorios) actuales.

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
<td><p>prinGuid</p></td>
<td><p>GUID, not null</p></td>
<td><p>GUID principal del dominio que se está supervisando.</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>Nombre de dominio completo (FQDN) del controlador de dominio actual usado para la sincronización de servicios de dominio de Active Directory. Tiene valor informativo.</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>imagen (binario)</p></td>
<td><p>Cookie de sincronización de Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>datetime</p></td>
<td><p>Marca de tiempo con la hora de actualización de la fila.</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>datetime</p></td>
<td><p>Tiempo hasta que se bloquean los cambios en la fila. Esto forma parte de un mecanismo de interbloqueo de software que garantiza que solo uno de los servicios de chat realiza la sincronización de Active Directory a la vez.</p></td>
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
<th>Columna (s)</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>Clave externa con la búsqueda en la tabla principal. prinGuid.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

