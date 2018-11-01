---
title: "Resumen DNS: Grupo de director escalado, equilibrador de carga de hardware"
TOCTitle: Resumen DNS - Grupo de director escalado, equilibrador de carga de hardware
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48274352
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen DNS - Grupo de director escalado, equilibrador de carga de hardware en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La tabla siguiente contiene un resumen de los registros DNS necesarios para admitir el Director con equilibrio de carga de hardware. El rolo del Director requiere registros DNS similares a los del Servidor front-end. El número de registros necesarios se refleja en los nombres alternativos de sujeto necesarios en el certificado de Director. Diferente del Servidor front-end, el Grupo de directores no hospeda cuentas de usuario de host ni los servicios de movilidad.

### Registros DNS necesarios para el Grupo de directores que usa un equilibrador de carga de hardware y equilibrio de carga DNS

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
<td><p>Registro de host de Director usado para replicación y comunicación de servidor a servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>HLB VIP de grupo de servidores de Grupo de directores</p></td>
<td><p>Registro de host para el Grupo de directores con equilibrio de carga DNS</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>VIP del equilibrador de carga de hardware del Grupo de directores</p></td>
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
<td><p>Publicados con equilibrio de carga de hardware y definidos por los servicios web externos de vale web de proxy inverso para el Grupo de directores</p></td>
</tr>
</tbody>
</table>

