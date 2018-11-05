---
title: 'Lync Server 2013: Registros de uso de RTC'
TOCTitle: Registros de uso de RTC
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48276440
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Registros de uso de RTC en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Planear los registros de uso de RTC consiste principalmente en elaborar una lista de todos los permisos de llamada vigentes actualmente en la organización, desde los permisos del presidente hasta los de los empleados temporales, consultores y personal contingente. Este proceso también brinda la oportunidad de volver a examinar los permisos existentes y modificarlos. Solo se pueden crear registros de uso de RTC para los permisos de llamada que se aplican a los usuarios previstos de Enterprise Voice, pero una solución mejor y de gran alcance podría ser crear registros de uso de RTC para todos los permisos de llamada sin tener en cuenta que algunos pueden no ser de aplicación al grupo de usuarios que se va a habilitar para Enterprise Voice. Si cambian los permisos de llamada o se agregan usuarios nuevos con permisos de llamada diferentes, ya estarán creados los registros de uso de RTC necesarios.

A continuación se muestra una tabla de uso de RTC típica.

### Registros de uso de RTC

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo de teléfono</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>Llamadas locales</p></td>
</tr>
<tr class="even">
<td><p>De larga distancia</p></td>
<td><p>Llamadas de larga distancia</p></td>
</tr>
<tr class="odd">
<td><p>Internacional</p></td>
<td><p>Llamadas internacionales</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>Empleados de jornada completa de Delhi</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Empleados de jornada completa de Redmond</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Empleados temporales de Redmond</p></td>
</tr>
<tr class="odd">
<td><p>Zúrich</p></td>
<td><p>Empleados de jornada completa de Zúrich</p></td>
</tr>
</tbody>
</table>


Por sí mismos, los registros de uso de RTC no hacen nada. Para que funcionen, hay que asociarlos a:

  - Directivas de voz, que se asignan a los usuarios.

  - Rutas, que se asignan a los números de teléfono.

Para obtener detalles sobre las directivas de la voz y rutas, consulte [Directivas de voz en Lync Server 2013](lync-server-2013-voice-policies.md) y [Rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md). Para obtener detalles sobre cómo crearlas y configurarlas, consulte [Configuración de rutas de voz para llamadas salientes en Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

