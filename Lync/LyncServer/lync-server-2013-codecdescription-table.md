---
title: Tabla CodecDescription en Lync Server 2013
TOCTitle: Tabla CodecDescription en Lync Server 2013
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48274903
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla CodecDescription en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla CodecDescription asigna identificadores de códec únicos a sus códecs correspondientes. Los códecs se utilizan para codificar señales digitales para la transmisión y la difusión, así como para la posterior descodificación de dichas señales para su reproducción. Esta tabla se introdujo Microsoft Lync Server 2013.


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
<td><p><strong>CodecDescriptionKey</strong></p></td>
<td><p>smallint</p></td>
<td><p>Principal</p></td>
<td><p>Identificador único asignado a códec.</p></td>
</tr>
<tr class="even">
<td><p><strong>CodecDescription</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Único</p></td>
<td><p>Descripción única del códec que corresponde a CodecDescriptionKey.</p></td>
</tr>
</tbody>
</table>

