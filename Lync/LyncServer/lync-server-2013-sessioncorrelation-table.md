---
title: 'Lync Server 2013: Tabla SessionCorrelation'
TOCTitle: Tabla SessionCorrelation
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48274280
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla SessionCorrelation en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla SessionCorrelation es una tabla auxiliar. Cada registro representa un CorrelationID que se utiliza para correlacionar varias sesiones.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Checksum</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este servidor de conferencia A/V.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationID</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Única</p></td>
<td><p>Las sesiones correlacionadas tendrán el mismo identificador de correlación.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>Datetime</p></td>
<td><p> </p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
</tbody>
</table>

