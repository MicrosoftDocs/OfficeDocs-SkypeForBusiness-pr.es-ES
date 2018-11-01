---
title: Tabla Categoría de error en Lync Server 2013
TOCTitle: Tabla Categoría de error en Lync Server 2013
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48274454
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Categoría de error en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla ErrorCategory contiene el nombre descriptivo de cada clasificación de diagnóstico de Microsoft Lync Server 2013. De manera predeterminada, Lync Server 2013 utiliza las siguientes clasificaciones:

  - 0 -- Éxito

  - 1 -- Error esperado

  - 2 – Error inesperado

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
<th>Clave/índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CategoryId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Identificador único de la clasificación.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>Valor y nombre descriptivo asignados a la clasificación. Los valores permitidos son:</p>
<ul>
<li><p>0 -- Éxito</p></li>
<li><p>1 -- Error esperado</p></li>
<li><p>2 – Error inesperado</p></li>
</ul></td>
</tr>
</tbody>
</table>

