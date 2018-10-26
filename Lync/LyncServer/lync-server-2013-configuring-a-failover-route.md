---
title: 'Lync Server 2013: Configurar una ruta de conmutación por error'
TOCTitle: Configurar una ruta de conmutación por error
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48275725
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar una ruta de conmutación por error en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En el siguiente ejemplo se muestra cómo puede un administrador definir una ruta de conmutación por error para usarla en caso de que se desconecte Dallas-GW1 por motivos de mantenimiento o no esté disponible. En las tablas siguientes se muestra el cambio de configuración necesario.

### Tabla 1. Directiva de usuario

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Directiva de usuario</th>
<th>Uso de teléfono</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Directiva de llamada predeterminada</p></td>
<td><p>Local</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Directiva local de Redmond</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>Directiva de llamada de Dallas</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### Tabla 2. Rutas

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de ruta</th>
<th>Modelo de número</th>
<th>Uso de teléfono</th>
<th>Troncal</th>
<th>Puerta de enlace</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ruta local de Redmond</p></td>
<td><p>^\+1(425|206|253)(\d{7})$</p></td>
<td><p>Local</p>
<p>RedmondLocal</p></td>
<td><p>Troncal1</p>
<p>Troncal2</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p></td>
</tr>
<tr class="even">
<td><p>Ruta local de Dallas</p></td>
<td><p>^\+1(972|214|469)(\d{7})$</p></td>
<td><p>Local</p></td>
<td><p>Troncal3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
<tr class="odd">
<td><p>Ruta universal</p></td>
<td><p>^\+?(\d*)$</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Troncal1</p>
<p>Troncal2</p>
<p>Troncal3</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p>
<p>Dallas-GW1</p></td>
</tr>
<tr class="even">
<td><p>Ruta de usuarios de Dallas</p></td>
<td><p>^\+?(\d*)$</p></td>
<td><p>DallasUsers</p></td>
<td><p>Troncal3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
</tbody>
</table>


En la Tabla 1, se agrega el uso de teléfono GlobalPSTNHopoff después del uso de teléfono DallasUsers en la directiva de llamada de Dallas. Esto permite que las llamadas con la directiva de llamada de Dallas usen las rutas configuradas para el uso de teléfono GlobalPSTNHopoff en caso de que una ruta para el uso telefónico DallasUsers no esté disponible.

