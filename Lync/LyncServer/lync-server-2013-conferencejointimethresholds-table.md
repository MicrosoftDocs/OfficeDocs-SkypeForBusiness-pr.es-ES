---
title: Tabla ConferenceJoinTimeThresholds en Lync Server 2013
TOCTitle: Tabla ConferenceJoinTimeThresholds en Lync Server 2013
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48274951
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla ConferenceJoinTimeThresholds en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

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
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Identificador único de la clasificación.</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Límite máximo de la clasificación. Los valores permitidos son:</p>
<ol>
<li><p>2</p></li>
<li><p>5</p></li>
<li><p>10</p></li>
</ol></td>
</tr>
</tbody>
</table>

