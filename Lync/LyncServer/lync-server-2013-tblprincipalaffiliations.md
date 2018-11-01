---
title: 'Lync Server 2013: tblPrincipalAffiliations'
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48275107
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalAffiliations en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla tblPrincipalAffiliations contiene las afiliaciones principales que describen la pertenencia a grupos en ubicaciones que incluyan grupos de seguridad de Servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.

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
<td><p>principalID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Id. de la entidad de seguridad afiliada.</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Id. de la entidad de seguridad que representa la afiliación. Todas las entidades de seguridad (excepto system-user-types) tienen también una afiliación propia.</p></td>
</tr>
<tr class="odd">
<td><p>índice</p></td>
<td><p>int, no NULL</p></td>
<td><p>Índice. El valor de las afiliaciones propias es -1, mientras que para el resto de afiliaciones aumenta de forma secuencial a partir de 1 dentro de cada depósito de &lt;principalID, affiliationId&gt;.</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int, no NULL</p></td>
<td><p>Entidad de seguridad que realizó la actualización más reciente. Suele ser 1, lo que significa sincronización de Active Directory.</p></td>
</tr>
</tbody>
</table>


### Teclas

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Columnas</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID, índice, affiliationID&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>Clave externa con búsqueda en la tabla Node.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>Clave externa con búsqueda en la tabla Node.nodeID.</p></td>
</tr>
</tbody>
</table>

