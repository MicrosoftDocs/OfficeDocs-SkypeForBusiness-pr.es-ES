---
title: 'Lync Server 2013: tblADCookie'
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48274380
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblADCookie en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

tblADCookie contiene las cookies actuales de sincronización del Protocolo ligero de acceso a directorios (LDAP).

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
<td><p>prinGuid</p></td>
<td><p>GUID, no NULL</p></td>
<td><p>GUID de entidad de seguridad del dominio supervisado.</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar(255)</p></td>
<td><p>Nombre de dominio completo (FQDN) del controlador de dominio actual utilizado para la sincronización de los Servicios de dominio de Active Directory. Tiene valor informativo.</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>imagen (binario)</p></td>
<td><p>Cookie de sincronización de Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>Datetime</p></td>
<td><p>Marca de tiempo con la hora de actualización de la fila.</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>Datetime</p></td>
<td><p>Fecha/hora en que finalizará el bloqueo de la fila para efectuar cambios. Esto forma parte del mecanismo de bloqueo de software que garantiza que solo uno de los servicios de chat realice una sincronización de Active Directory por vez.</p></td>
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
<td><p>prinGuid</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>Clave externa con búsqueda en la tabla Principal.prinGuid.</p></td>
</tr>
</tbody>
</table>

