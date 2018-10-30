---
title: 'Lync Server 2013: Resumen DNS - Director único'
TOCTitle: Resumen DNS - Director único
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48275740
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen DNS - Director único en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla siguiente contiene un resumen de los registros DNS necesarios para que el Director de un solo equipo sea compatible. El rol del Director requiere unos registros DNS similares a los del Servidor front-end. El número de registros necesarios se muestra en los nombres alternativos del tema necesarios en el certificado de Director. A diferencia del Servidor front-end, el Director no hospeda cuentas de usuario ni servicios de movilidad.

### Registros DNS requeridos para el Director

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN/Registro DNS</th>
<th>Dirección IP/FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Registro de host del Director usado para la replicación y servidor a servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Protocolo de inicio de sesión (SIP) entrante de la interfaz perimetral interna del Servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Servicios web de acceso telefónico publicados del proxy inverso</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Servicios web de reunión publicados del proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Publicados y definidos por los servicios web externos de vales web del proxy inverso para el Director</p></td>
</tr>
</tbody>
</table>

