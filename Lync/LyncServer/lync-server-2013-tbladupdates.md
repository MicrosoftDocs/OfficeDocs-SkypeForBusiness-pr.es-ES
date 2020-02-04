---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb4b5b73fb74c2337eeaa6b065396253a2cb0be4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a>tblADUpdates en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblADUpdates contiene cambios de servicios de dominio de Active Directory que aún no han sido procesados por los pasos más recientes de sincronización de Active Directory.

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
<td><p>GUID principal del objeto que cambió.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384), not null</p></td>
<td><p>Nombre distintivo del objeto.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>bit, not null</p></td>
<td><p>True si ha cambiado al menos un atributo del objeto.</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>bit, not null</p></td>
<td><p>True si la pertenencia ha cambiado.</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>bit, not null</p></td>
<td><p>No usado.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, not null</p></td>
<td><p>True si el objeto se ha eliminado.</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>DateTime, not null</p></td>
<td><p>Marca de tiempo del momento en que se insertó la fila.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

