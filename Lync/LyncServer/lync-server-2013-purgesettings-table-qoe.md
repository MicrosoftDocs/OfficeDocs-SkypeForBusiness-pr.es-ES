﻿---
title: Tabla PurgeSettings (QoE) en Lync Server 2013
TOCTitle: Tabla PurgeSettings (QoE) en Lync Server 2013
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48274863
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla PurgeSettings (QoE) en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros de calidad de experiencia obsoletos se eliminarán automáticamente de la base de datos de QoE. Tenga en cuenta que la información relacionada con la depuración también se puede obtener desde dentro del Shell de administración de Microsoft Lync Server 2013 by ejecutando el siguiente comando:

    Get-CsQoEConfiguration

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
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave/Índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Identificador único para la colección de valores de depuración de QoE.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Cuando se establece en True (1) Microsoft Lync Server 2013 depurará periódicamente registros obsoletos de la base de datos de QoE. La depuración tendrá lugar todos los días en el tomo especificado por la configuración PurgeHour. Si se establece en False (0), los registros no se depurarán automáticamente desde la base de datos. El valor predeterminado es True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Especifica la antigüedad de los registros de QoE (en días) que se depurarán desde la base de datos: si la depuración está habilitada, se eliminarán de la base de datos los registros de QoE anteriores a este valor. El valor predeterminado es 60 días.</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Especifica la hora local del día en la que tendrá lugar la depuración de la base de datos. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo puede especificar la hora del día: se permite un valor de 10 (indicando 10:00 *AM) pero no se permite un valor de 10:30 de 10.5 (indicando 10:30 AM). El valor predeterminado es 1 (1:00 AM). Especifica la hora local del día en que tendrá lugar la depuración de la base de datos. La hora del día se especifica mediante un reloj de 24 horas, representando el 0 la medianoche (12:00 AM) y el 23, las 11:00 PM. Tenga en cuenta que solo puede especificar la hora del día: se permite un valor de 10 (que indica 10:00 AM) pero no se permite un valor de 10:30 de 10.5 (que indica 10:30 AM). El valor predeterminado es 1 (1:00 AM).</p></td>
</tr>
</tbody>
</table>

