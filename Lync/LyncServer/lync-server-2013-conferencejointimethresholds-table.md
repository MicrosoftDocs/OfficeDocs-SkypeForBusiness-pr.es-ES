---
title: 'Lync Server 2013: tabla ConferenceJoinTimeThresholds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baf29af4b9d1f2b026271b84cb54436e8f4b233f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Tabla ConferenceJoinTimeThresholds en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe Resumen de tiempo de combinación de conferencia. En el informe Resumen de tiempo de combinación de conferencia se resume la cantidad de tiempo necesario para que los usuarios se unan correctamente a una conferencia; Estos valores de hora se notifican como promedio y en una de las siguientes categorías:

  - Menos de 2 segundos.

  - Entre 2 y 5 segundos.

  - Entre 5 segundos y 10 segundos.

  - Más de 10 segundos.

La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación de 2 segundos, 5 segundos y 10 segundos.

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
<td><p><strong>ThresholdId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Identificador único de la clasificación.</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Límite superior de la clasificación. Los valores permitidos son:</p>
<ol>
<li><p>1</p></li>
<li><p>5</p></li>
<li><p>base10</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

