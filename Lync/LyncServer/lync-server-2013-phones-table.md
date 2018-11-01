---
title: 'Lync Server 2013: Tabla Phones'
TOCTitle: Tabla Phones
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48275037
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Phones en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Teléfonos es una tabla auxiliar. Los registros de la tabla contienen información sobre un número de teléfono que ha participado en llamadas VoIP que cuentan con registros en la base de datos.


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
<td><p><strong>PhoneId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número único que identifica este teléfono.</p></td>
</tr>
<tr class="even">
<td><p><strong>PhoneUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p> </p></td>
<td><p>Número de teléfono.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>dateTime</p></td>
<td><p></p></td>
<td><p>Marca de tiempo (solo para uso interno).</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

