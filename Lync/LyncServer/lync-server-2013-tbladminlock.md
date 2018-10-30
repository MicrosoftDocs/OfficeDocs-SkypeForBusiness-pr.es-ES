---
title: 'Lync Server 2013: tblAdminLock'
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48275743
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblAdminLock en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.

### Columnas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>lockExpiresTime</p></td>
<td><p>datetime, no NULL</p></td>
<td><p>Fecha y hora de expiración del bloqueo. El propietario puede ampliar este valor de manera regular.</p></td>
</tr>
<tr class="even">
<td><p>lockServerID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador del servidor que posee el bloqueo.</p></td>
</tr>
<tr class="odd">
<td><p>lockActorID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad que posee el bloqueo.</p></td>
</tr>
</tbody>
</table>

