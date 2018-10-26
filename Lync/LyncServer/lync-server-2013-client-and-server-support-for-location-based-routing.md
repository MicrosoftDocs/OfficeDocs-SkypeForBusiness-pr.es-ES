---
title: "Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación"
TOCTitle: Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994024(v=OCS.15)
ms:contentKeyID: 52061610
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El enrutamiento según ubicación se aplica mediante Lync Server. Lync Server puede identificar los sitios de red desde los que se conectan los usuarios dentro de la red corporativa. Dado que los usuarios remotos están fuera de la red corporativa, su ubicación se considera como desconocida.

## Compatibilidad con Lync Server

El enrutamiento según ubicación necesita que Lync Server 2013 CU1 se implemente en todos los Grupos de servidores front-end y Servidores Standard Edition de una topología determinada. Si Lync Server 2013 CU1 no está instalado en determinados componentes de Lync de la topología, las restricciones de enrutamiento según ubicación no se podrán aplicar por completo.

En la siguiente tabla se identifica la combinación de roles de servidor y versiones que son compatibles con el enrutamiento según ubicación.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Versión del grupo</th>
<th>Versión de Servidor de mediación</th>
<th>Compatible</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Actualización acumulativa de Lync Server 2013 de febrero de 2013</p></td>
<td><p>Actualización acumulativa de Lync Server 2013 de febrero de 2013</p></td>
<td><p>sí</p></td>
</tr>
<tr class="even">
<td><p>Actualización acumulativa de Lync Server 2013 de febrero de 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p>Actualización acumulativa de Lync Server 2013 de febrero de 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p>Actualización acumulativa de Lync Server 2013 de febrero de 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>cualquiera</p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>cualquiera</p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>cualquiera</p></td>
<td><p>no</p></td>
</tr>
</tbody>
</table>


## Compatibilidad con clientes de Lync

En la siguiente tabla se identifican los clientes compatibles con el enrutamiento según ubicación.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de cliente</th>
<th>Compatible</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>sí</p></td>
<td><p>Incluida la actualización acumulativa de Lync 2013 de febrero de 2013</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>sí</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>no</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>sí</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Operador</p></td>
<td><p>sí</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync para Windows 8</p></td>
<td><p>no</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>no</p></td>
<td><p>Se debe deshabilitar VoIP para los clientes de Lync Mobile 2013 si lo utilizan usuarios que tienen habilitado el enrutamiento según ubicación.</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>sí</p></td>
<td> </td>
</tr>
</tbody>
</table>

  


> [!NOTE]
> Para deshabilitar VoIP para los clientes de Lync Mobile 2013, asigne una directiva de movilidad con la configuración, audio y vídeo IP, deshabilitada para todos los usuarios y habilitada para el enrutamiento según ubicación. Para obtener más detalles acerca de la directiva de movilidad, consulte <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



## Vea también

#### Otros recursos

[Planificar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

