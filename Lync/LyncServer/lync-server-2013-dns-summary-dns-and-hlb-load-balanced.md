---
title: "Lync Server 2013 : Résumé des enr. DNS - Éq. de ch. DNS et matérielle"
TOCTitle: Resumen de DNS - Carga equilibrada DNS y HLB
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48276745
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de DNS - Carga equilibrada DNS y HLB en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla siguiente contiene un resumen de los registros DNS necesarios para admitir el Director con carga de DNS y carga de hardware equilibradas. El rol de Director necesita registros DNS similares al del Servidor front-end. El número de registros necesarios se refleja en los nombres alternativos de sujeto que el certificado del Director necesita. El Grupo de directores, que es diferente del Servidor front-end, no hospeda cuentas de usuario ni servicios de movilidad.

### Registros DNS necesarios para el grupo de directores que usan carga de DNS y carga de hardware equilibradas

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
<td><p>dirpool01.contoso.net</p></td>
<td><p>Grupo de directores</p></td>
<td><p>Registro host para el Grupo de directores con carga de DNS equilibrada para servidor a servidor</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Grupo de directores</p></td>
<td><p>Protocolo de inicio de sesión (SIP) entrante desde la interfaz interna del Servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>VIP del equilibrador de carga de hardware del Grupo de directores</p></td>
<td><p>Servicios web de acceso telefónico publicados con carga de hardware equilibrada desde el proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>VIP del equilibrador de carga de hardware del Grupo de directores</p></td>
<td><p>Servicios web de reunión publicados con carga de hardware equilibrada desde el proxy inverso</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>VIP del equilibrador de carga de hardware del Grupo de directores</p></td>
<td><p>Carga de hardware equilibrada publicada y definida por los servicios web externos de vale web de proxy inverso para el grupo de directores</p></td>
</tr>
</tbody>
</table>

