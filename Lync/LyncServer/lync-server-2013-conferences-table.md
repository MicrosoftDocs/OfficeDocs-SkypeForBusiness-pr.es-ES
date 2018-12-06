---
title: 'Lync Server 2013: Tabla Conferences'
TOCTitle: Tabla Conferences
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48276585
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Conferences en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro de esta tabla contiene detalles de llamadas sobre una conferencia.


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
<td><p>Hora en que el agente CDR capturó la solicitud de conferencia. Se usa solo como clave principal para identificar de manera única una instancia de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Número para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> para identificar de manera única una instancia de conferencia.*</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>URI de conferencia. Consulte <a href="lync-server-2013-conferenceuris-table.md">Tabla ConferenceUris en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p> </p></td>
<td><p>Útil para conferencias periódicas. Cada instancia de una conferencia periódica tiene el mismo <strong>ConferenceUri</strong> , pero tendrá un <strong>ConfInstance</strong> diferente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p> </p></td>
<td><p>Hora de inicio de la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p> </p></td>
<td><p>Hora de inicio de la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Número para identificar al grupo en el que se capturó la conferencia. Consulte <a href="lync-server-2013-pools-table.md">Tabla Pools en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Número para identificar el URI de organizador de esta conferencia. Consulte <a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a> para más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Máscara de bits que contiene atributos de la conferencia. Los valores posibles son:</p>
<ul>
<li><p>0X01</p></li>
<li><p>Sintética</p></li>
<li><p>Transacción</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Procesado</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Campo interno que usa el servicio de supervisión.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si dos sesiones se inician exactamente a la misma hora, el valor de SessionIdSeq para una de ellas será 1 y para la otra será 2 (y así sucesivamente).

