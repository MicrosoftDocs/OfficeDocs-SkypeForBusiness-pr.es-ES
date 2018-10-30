---
title: Vista de medios
TOCTitle: Vista de medios
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49888906
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista de medios

 

_**Última modificación del tema:** 2015-03-09_

La vista Medios almacena información sobre un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios. Esta vista se introdujo en Microsoft Lync Server 2013.


> [!NOTE]
> La vista Medios no debería utilizarse para calcular la duración de medios de una sesión. Esta vista contiene los detalles de señalización del intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE, y StartTime indica la hora a la que se envió la solicitud INVITE. Esta hora no implica necesariamente la hora de inicio de los medios, ya que los medios se inician solamente después de que se acepta la sesión.



La vista Medios contiene todas las columnas de la [Vista SessionDetails](lync-server-2013-sessiondetails-view.md) además de las que aparecen a continuación.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Medios</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de medio. Consulte la <a href="lync-server-2013-medialist-table.md">Tabla MediaList en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora a la que se envió la solicitud de medios.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de finalización de la sesión.</p></td>
</tr>
</tbody>
</table>

