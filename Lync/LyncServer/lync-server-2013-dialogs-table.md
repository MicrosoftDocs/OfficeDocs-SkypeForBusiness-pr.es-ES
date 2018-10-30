---
title: 'Lync Server 2013: Tabla Dialogs'
TOCTitle: Tabla Dialogs
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48275166
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Dialogs en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla Diálogos es una tabla de apoyo que guarda información sobre DialogIDs para sesiones punto a punto.


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
<td><p>Datetime</p></td>
<td><p>Principal</p></td>
<td><p>Tiempo de solicitud de la sesión; se usa de forma conjunta con SessionIDSeq para identificar de forma exclusiva una sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número de Id. para identificar la sesión. Se usa de forma conjunta con SessionIDTime para identificar de forma exclusiva una sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalChecksum</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Suma de comprobación del ExternalID. Este campo se utiliza para aumentar la velocidad de las búsquedas en la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExternalId</strong></p></td>
<td><p>varbinary(775)</p></td>
<td><p> </p></td>
<td><p>Id. de diálogo SIP, almacenado como binario. El formato del binario es:</p>
<p>diálogo;etiqueta-origen;etiqueta-destino</p>
<p>Estos datos pueden convertirse en formato de texto con esta sintaxis:</p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

