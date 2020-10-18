---
title: 'Lync Server 2013: tblAdminLock'
description: 'Lync Server 2013: tblAdminLock.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3313826b2c0d578c515fb25f83e713b8978ae63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573716"
---
# <a name="tbladminlock-in-lync-server-2013"></a>tblAdminLock en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-25_

La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.

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
<td><p>lockExpiresTime</p></td>
<td><p>datetime, no NULL</p></td>
<td><p>Fecha y hora de expiración del bloqueo. El propietario puede ampliar este valor de manera regular.</p></td>
</tr>
<tr class="even">
<td><p>lockServerID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador del servidor que posee el bloqueo.</p></td>
</tr>
<tr class="odd">
<td><p>lockActorID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad que posee el bloqueo.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

