---
title: 'Lync Server 2013: Configurar el enrutamiento basado en ubicación'
TOCTitle: Configurar el enrutamiento basado en ubicación
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994036(v=OCS.15)
ms:contentKeyID: 52061692
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el enrutamiento basado en ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Lync Server 2013 CU1, el enrutamiento según ubicación es una característica de Telefonía IP empresarial. El enrutamiento según ubicación es una característica de administración de llamadas que controla la manera en que se enrutan las llamadas mediante Lync Server 2013 CU1. Aplica restricciones con respecto a si las llamadas se pueden enrutar a destinos PBX o RTC según la ubicación del autor de la llamada de Lync. El enrutamiento según ubicación aplica reglas de autorización de llamada a las llamadas RTC según la ubicación de la red del autor de la llamada. La ubicación del autor de la llamada se determina según el sitio de red asociado con la subred de la red a la que está conectado el autor de la llamada. La configuración del enrutamiento según ubicación requiere que primero se implemente Telefonía IP empresarial y que después se configuren las regiones de red, los sitios y las subredes. Esto establece la base para habilitar el enrutamiento según ubicación.

Antes de implementar el enrutamiento según ubicación, primero debe implementar Telefonía IP empresarial y configurar regiones de red, sitios y subredes de red asociadas a los sitios de red. Una vez completado, puede configurar el enrutamiento según ubicación. Si desea obtener los pasos para configurar regiones de red, sitios y y subredes, consulte [Implementación de características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Esta sección lo guiará a través del proceso de configuración del enrutamiento según ubicación mediante el siguiente ejemplo como ilustración.

![Ejemplo de enrutamiento basado en ubicación de Telefonía IP empresarial](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Ejemplo de enrutamiento basado en ubicación de Telefonía IP empresarial")

  
En la siguiente tabla se representan los usuarios definidos en este ejemplo.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de extremo</th>
<th>Ubicación</th>
<th>Usuarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Oficina corporativa de Delhi</p></td>
<td><p>DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Oficina corporativa de Hyderabad</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Desconocido (p. ej., hotel)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>Oficina corporativa de Delhi</p></td>
<td><p>DEL-PBX-1, DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Oficina corporativa de Hyderabad</p></td>
<td><p>HYD-PBX-1, HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>RTC</p></td>
<td><p>Desconocido</p></td>
<td><p>RTC-1, RTC-2, RTC-3</p></td>
</tr>
</tbody>
</table>

  

En la siguiente tabla se representan los sistemas ilustrados en este entorno de ejemplo.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema</th>
<th>Ubicación</th>
<th>Nombre</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Grupo de Lync Server 2013 CU1</p></td>
<td><p>cualquiera</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, Servidor de mediación</p></td>
<td><p>cualquiera</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>RTC puerta de enlace 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>RTC puerta de enlace 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>RED-PBX</p></td>
</tr>
</tbody>
</table>


## En esta sección

  - [Configuración de Telefonía IP empresarial en Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Implementación de las regiones, sitios y subsitios de red en Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Habilitación del enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

## Vea también

#### Otros recursos

[Implementación de características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

