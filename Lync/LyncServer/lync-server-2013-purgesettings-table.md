---
title: 'Lync Server 2013: tabla PurgeSettings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32522f0818b95e829bbb643dea8749e2f91d1f31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Tabla PurgeSettings en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

La tabla PurgeSettings contiene información que especifica si los registros de detalles de llamadas obsoletos se eliminarán automáticamente de la base de datos de CDR (y, en caso de que sí, cuándo). Tenga en cuenta que también se puede obtener información relacionada con la purga desde el shell de administración de Microsoft Lync Server 2013 ejecutando el siguiente comando:

    Get-CsCdrConfiguration

Los administradores deben tratar la tabla PurgeSettings como de solo lectura: los cambios en la configuración de depuración de detalles de llamadas solo deben realizarse con los cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) o [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

Esta tabla se introdujo en Microsoft Lync Server 2013.


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
<td><p><strong>Id</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Identificador único de la recopilación de opciones de configuración para depuración de CDR.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Cuando se establece en true (1), Microsoft Lync Server 2013 purgará periódicamente los registros obsoletos de la base de datos de CDR. La depuración tendrá lugar todos los días en el tomo especificado por la configuración PurgeHour. Si se establece en False (0), los registros no se depurarán automáticamente desde la base de datos. El valor predeterminado es True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica la antigüedad de los registros de CDR (en días) que se depurarán de la base de datos: si se habilita la depuración, los registros de CDR cuya antigüedad sea mayor que este valor se eliminarán de la base de datos. El valor predeterminado es 60 días.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica la antigüedad de los registros de informe de errores (en días) que se depurarán de la base de datos: si se habilita la depuración, los registros de informe de errores cuya antigüedad sea mayor que este valor se eliminarán de la base de datos. El valor predeterminado es 60 días.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica la hora local del día a la que se realizará la depuración de la base de datos. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo se pueden especificar horas en formato convencional: se permite un valor 10 (que indicaría las 10:00 a.m.), pero no un valor 10:30 o 10.5 (que indicaría las 10:30 a.m.). El valor predeterminado es 2 (2:00 AM).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

