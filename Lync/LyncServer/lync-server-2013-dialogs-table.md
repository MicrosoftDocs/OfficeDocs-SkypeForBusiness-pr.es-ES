---
title: 'Lync Server 2013: tabla Dialogs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf2f23e9c82c1c6d4dd21519f1193b902c8e6434
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a>Tabla de cuadros de diálogo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

La tabla Dialogs es una tabla de apoyo que almacena la información sobre DialogIDs para las sesiones punto a punto.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Clave o índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principal</p></td>
<td><p>Hora de la solicitud de sesión; se usa junto con SessionIDSeq para identificar de forma única una sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Número de identificador para identificar la sesión. Se usa junto con SessionIDTime para identificar de forma única una sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalChecksum</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Suma de comprobación de ExternalID. Este campo se usa para aumentar la velocidad de las búsquedas en bases de datos.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExternalId</strong></p></td>
<td><p>varbinary (775)</p></td>
<td><p> </p></td>
<td><p>IDENTIFICADOR del cuadro de diálogo SIP, almacenado como binario. El formato del binario es:</p>
<p>Dialog; from-Tag; to-Tag</p>
<p>Estos datos pueden convertirse en formato de texto con esta sintaxis:</p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

