---
title: Configuración de Telefonía IP empresarial en Lync Server 2013
TOCTitle: Configuración de Telefonía IP empresarial en Lync Server 2013
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994041(v=OCS.15)
ms:contentKeyID: 52061662
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de Telefonía IP empresarial en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Para implementar Telefonía IP empresarial, necesitará configurar lo siguiente:

  - Crear un tronco

  - Definir una directiva de voz

  - Definir una ruta de voz

  - Habilitar usuarios para telefonía IP empresarial

## Crear un tronco

Debe definir troncos en la implementación de Telefonía IP empresarial. Para el enrutamiento según ubicación, debe crear una configuración troncal por tronco. Use Lync ServerGenerador de topologías para definir los troncos y use el comando Lync ServerWindows PowerShell, New-CsTrunkConfiguration, o Panel de control de Lync Server para definir las configuraciones troncales correspondientes. Se puede obtener más información acerca de cómo habilitar el enrutamiento según ubicación en configuraciones troncales en la sección "Habilitar el enrutamiento según ubicación en troncos", en el tema [Habilitación del enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). Para este ejemplo, la siguiente tabla ilustra los troncos utilizados en este escenario.

Para obtener más información, consulte [Definir troncos adicionales en el Generador de topologías en Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


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
<th>Nombre del tronco</th>
<th>Tipo de sistema</th>
<th>Nombre</th>
<th>Ubicación</th>
<th>Servidor de mediación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Troncal 1 DEL-GW</p></td>
<td><p>Puerta de enlace RTC</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Troncal 2 HYD-GW</p></td>
<td><p>Puerta de enlace RTC</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Troncal 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Troncal 4 HYD-PBX</p></td>
<td><p>PBX</p></td>
<td><p>HYD-PBX</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>



## Define directivas de voz

Debe definir directivas de voz para la implementación de Telefonía IP empresarial. Defina una directiva de voz para aplicar las restricciones de enrutamiento según ubicación en un subconjunto de usuarios si solo un subconjunto se requiere para usar el enrutamiento según ubicación. Para este ejemplo, la siguiente tabla ilustra las directivas de voz utilizadas en este escenario. Solo los parámetros que son específicos al enrutamiento según ubicación se incluyen en la tabla con fines meramente ilustrativos.

Para obtener más información, consulte [Configurar directivas de voz y registros de uso de la RTC para autorizar características y privilegios de llamada en Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Directiva de voz 1</th>
<th>Directiva de voz 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Id. de directiva de voz</p></td>
<td><p>Directiva de voz Delhi</p></td>
<td><p>Directiva de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso Delhi, uso PBX Del, uso PBX Hyd</p></td>
<td><p>Uso Hyderabad, uso PBX Hyd, uso PBX Del</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>



## Definir rutas de voz

Debe definir rutas de voz para la implementación de Telefonía IP empresarial. Para este ejemplo, la siguiente tabla ilustra las rutas de voz utilizadas en este escenario. Solo los parámetros que son específicos al enrutamiento según ubicación se incluyen en la tabla con fines meramente ilustrativos.

Para obtener más información, consulte [Configuración de rutas de voz para llamadas salientes en Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


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
<th></th>
<th>Ruta de voz 1</th>
<th>Ruta de voz 2</th>
<th>Ruta de voz 3</th>
<th>Ruta de voz 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre</p></td>
<td><p>Ruta Delhi</p></td>
<td><p>Ruta Hyderabad</p></td>
<td><p>Ruta PBX Del</p></td>
<td><p>Ruta PBX Hyd</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso Delhi</p></td>
<td><p>Uso Hyderabad</p></td>
<td><p>Uso PBX Del</p></td>
<td><p>Uso PBX Hyd</p></td>
</tr>
<tr class="odd">
<td><p>Troncal</p></td>
<td><p>Troncal 1 DEL-GW</p></td>
<td><p>Troncal 2 HYD-GW</p></td>
<td><p>Troncal 3 DEL-PBX</p></td>
<td><p>Troncal 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>



## Habilitar usuarios para telefonía IP empresarial

Habilite usuarios para Telefonía IP empresarial y asígnelos a una directiva de voz definida previamente. Para este ejemplo, la siguiente tabla ilustra la asignación utilizada en este escenario. Solo los parámetros que son específicos al enrutamiento según ubicación se incluyen en la tabla con fines meramente ilustrativos.

Para obtener más información, consulte [Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Usuarios ubicados en Delhi</th>
<th>Usuarios ubicados en Hyderabad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Directiva de voz asociada</p></td>
<td><p>Directiva de voz Delhi</p></td>
<td><p>Directiva de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usuarios de muestra</p></td>
<td><p>DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>



## Vea también

#### Otros recursos

[Configurar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

