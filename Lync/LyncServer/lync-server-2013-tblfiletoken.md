---
title: 'Lync Server 2013: tblFileToken'
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48275144
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblFileToken en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivos.

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
<td><p>fileToken</p></td>
<td><p>nvarchar (50), no NULL</p></td>
<td><p>Símbolo único (un GUID).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenUserID</p></td>
<td><p>int, no NULL</p></td>
<td><p>Id. de la entidad de seguridad que está transfiriendo el archivo.</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenChannelID</p></td>
<td><p>GUID, no NULL</p></td>
<td><p>GUID del nodo de la sala de chat.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenExpireDate</p></td>
<td><p>datetime, no NULL</p></td>
<td><p>Tiempo de expiración; los tokens caducan después de 30 minutos, a menos que esté anclado (vea las siguientes descripciones en esta columna).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceFileUrl</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URL del archivo transferido (para el uso del Servicio de cumplimiento).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceThumbnailUrl</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URL de la miniatura del archivo transferido (para el uso del Servicio de cumplimiento).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceTime</p></td>
<td><p>datetime2</p></td>
<td><p>Marca de tiempo para la operación de transferencia de archivo real (para el uso del Servicio de cumplimiento).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceIsUpload</p></td>
<td><p>bit</p></td>
<td><p>True si se carga; False si se descarga (para el uso del Servicio de cumplimiento).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenCompliancePinned</p></td>
<td><p>bit, no NULL</p></td>
<td><p>True si el token está anclado. Se usa para mantener el token en la tabla hasta que el Servicio de cumplimiento tenga la oportunidad de recuperar los campos relevantes de él.</p></td>
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
<th>Columna</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fileToken</p></td>
<td><p>Clave principal.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenChannelID</p></td>
<td><p>Clave externa con búsqueda en la tabla tblNode.nodeGuid.</p></td>
</tr>
</tbody>
</table>

