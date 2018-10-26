---
title: Tabla SIPResponseMetaData en Lync Server 2013
TOCTitle: Tabla SIPResponseMetaData en Lync Server 2013
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48276727
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla SIPResponseMetaData en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y definición de cada uno de estos códigos. Estos códigos se generan como respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza responderla.

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
<th>Clave/Índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Valor numérico que representa el código de respuesta SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Clase</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Clasificación general para el código de respuesta. Las clasificaciones incluyen:</p>
<ul>
<li><p>1 – Respuestas de tipo informativo</p></li>
<li><p>2 – Respuestas correctas</p></li>
<li><p>3 – Respuestas de redirección</p></li>
<li><p>4 – Respuestas de error de cliente</p></li>
<li><p>5 -- Respuestas de error del servidor</p></li>
<li><p>6 – Respuesta de error global</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Descripción</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Descripción del código de respuesta SIP. Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:</p>
<p>Se está desviando la llamada</p></td>
</tr>
</tbody>
</table>

