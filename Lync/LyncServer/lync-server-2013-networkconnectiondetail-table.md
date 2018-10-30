---
title: Tabla NetworkConnectionDetail en Lync Server 2013
TOCTitle: Tabla NetworkConnectionDetail en Lync Server 2013
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48276418
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla NetworkConnectionDetail en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red usados en otra parte de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.


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
<th><strong>Clave/Índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>NetworkConnectionDetailKey</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Identificador único del tipo de conexión de red.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkConnectionDetail</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Único</p></td>
<td><p>Tipo de conexión de red que se corresponde con NetworkConnectionDetailKey. Los valores permitidos son:</p>
<ol>
<li><p>0: cableada</p></li>
<li><p>1: Wi-Fi</p></li>
<li><p>2: Ethernet</p></li>
</ol></td>
</tr>
</tbody>
</table>

