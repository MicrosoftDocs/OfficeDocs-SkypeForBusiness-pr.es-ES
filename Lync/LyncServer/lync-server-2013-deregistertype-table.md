---
title: 'Lync Server 2013: Tabla DeRegisterType'
TOCTitle: Tabla DeRegisterType
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48274359
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla DeRegisterType en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de anulación del registro de usuario, como "iniciado por cliente", "registro expirado" o "respuesta de cliente interrumpida".


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
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valores permitidos:</p>
<ul>
<li><p>0 - Desconocido</p></li>
<li><p>1 - Anulación del registro iniciada por el cliente</p></li>
<li><p>2 - Registro expirado</p></li>
<li><p>3 – Cliente bloqueado</p></li>
<li><p>4 - Atributos de usuario modificados</p></li>
<li><p>5 – Registrador preferido modificado</p></li>
<li><p>6 - Cliente heredado en modo de supervivencia</p></li>
</ul></td>
</tr>
</tbody>
</table>

