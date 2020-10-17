---
title: 'Lync Server 2013: tabla ConferenceJoinTimeThresholds'
description: 'Lync Server 2013: tabla ConferenceJoinTimeThresholds.'
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
ms.openlocfilehash: 5e38c8b99f444e16309882b6a8885d166fdceb9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561676"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Tabla ConferenceJoinTimeThresholds en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia. El informe de resumen de hora de incorporación a la conferencia resume el tiempo que necesitaron los usuarios para unirse a la conferencia. Estos valores de tiempo se registran como promedio y en una de las categorías siguientes:

  - Menos de 2 segundos.

  - Entre 2 y 5 segundos.

  - Entre 5 y 10 segundos.

  - Más de 10 segundos.

La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación 2 segundos, 5 segundos y 10 segundos.

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
<td><p>entero</p></td>
<td><p>Principal</p></td>
<td><p>Identificador único de la clasificación.</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>entero</p></td>
<td></td>
<td><p>Límite máximo de la clasificación. Los valores permitidos son:</p>
<ol>
<li><p>segundo</p></li>
<li><p>5 </p></li>
<li><p>10  </p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

