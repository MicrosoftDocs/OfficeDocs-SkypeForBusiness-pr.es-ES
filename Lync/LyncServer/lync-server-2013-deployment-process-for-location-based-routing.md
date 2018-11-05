---
title: 'Lync Server 2013: Proceso de implementación para el enrutamiento basado en ubicación'
TOCTitle: Proceso de implementación para el enrutamiento basado en ubicación
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994055(v=OCS.15)
ms:contentKeyID: 52061739
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proceso de implementación para el enrutamiento basado en ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Este tema contiene una introducción al proceso de configurar el enrutamiento basado en ubicación. Antes de configurar el enrutamiento basado en ubicación, debe implementar Lync ServerEnterprise Edition o Standard Edition con Telefonía IP empresarial. Los componentes que necesita el enrutamiento basado en ubicación ya se instalan y se habilitan al implementar Telefonía IP empresarial.

### Proceso de implementación del enrutamiento basado en ubicación

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Grupos y roles necesarios</th>
<th>Documentación de implementación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Implementar Telefonía IP empresarial</p></td>
<td><ul>
<li><p>Configurar troncos</p></li>
<li><p>Crear directivas de voz</p></li>
<li><p>Definir rutas de voz</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Implementar Telefonía IP empresarial</p></td>
</tr>
<tr class="even">
<td><p>Comprobar la implementación de Telefonía IP empresarial</p></td>
<td><p></p></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Configurar regiones de red, sitios y subredes</p></td>
<td><ul>
<li><p>Crear regiones de red</p></li>
<li><p>Crear sitios de red</p></li>
<li><p>Asociar subredes a sitios de red</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Acerca de las regiones de red, los sitios y las subredes<br />
Crear o modificar una región de red<br />
Crear o modificar un sitio de red<br />
Asociar una subred a un sitio de red</p></td>
</tr>
<tr class="even">
<td><p>Configurar el enrutamiento basado en ubicación</p></td>
<td><ul>
<li><p>Crear directivas de enrutamiento de voz</p></li>
<li><p>Definir una configuración de troncos independiente para cada tronco</p></li>
<li><p>Modificar directivas de voz</p></li>
<li><p>Habilitar la configuración del enrutamiento basado en ubicación</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Ejemplo de implementación

La siguiente implementación se incluye para ilustrar aún más los mecanismos habilitados por el enrutamiento basado en ubicación.

![Topología de enrutamiento basado en ubicación](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "Topología de enrutamiento basado en ubicación")

## Llamadas de RTC entrantes

Los administradores pueden habilitar el tronco definido para redirigir las llamadas a “Puerta de enlace del sitio 1” para el enrutamiento basado en ubicación y asociar la “Puerta de enlace del sitio 1” al sitio 1. Una vez habilitado, las llamadas redirigidas a través de la “Puerta de enlace del sitio 1” se redirigirán solamente a los usuarios ubicados en el sitio 1. Todas las llamadas redirigidas a través del tronco “Puerta de enlace del sitio 1” y destinadas a usuarios de otros sitios, como el sitio 2, se bloquearán para evitar que se omita el número de pago de RTC.

Todas las llamadas de RTC entrantes que lleguen a través de la “Puerta de enlace del sitio 1” solo tendrán permiso para redirigirse a extremos ubicados en el sitio 1. Por ejemplo, cuando “Usuario de Lync 1” viaje al sitio 2, todas las llamadas de RTC entrantes que lleguen a través de la “Puerta de enlace del sitio 1” no se redirigirán a los extremos de “Usuario de Lync 1” ubicados en el sitio 2. Se aplicará la misma regla de enrutamiento si “Usuario de Lync 1” viaja a un sitio de red desconocido donde no se pueda determinar la ubicación del usuario.

En la siguiente tabla, se describe a grandes rasgos la experiencia del usuario de “Usuario de Lync 1” en este contexto.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Extremos de Usuario de Lync 1 ubicados en el sitio de red 1</th>
<th>Extremos de Usuario de Lync 1 ubicados en el sitio de red 2</th>
<th>Extremos de Usuario de Lync 1 ubicados en un sitio de red desconocido</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas de RTC entrantes a Usuario de Lync 1</p></td>
<td><p>Las llamadas se redirigen a los extremos situados en esta ubicación</p></td>
<td><p>Las llamadas no se redirigen a los extremos situados en esta ubicación</p></td>
<td><p>Las llamadas no se redirigen a los extremos situados en esta ubicación</p></td>
</tr>
</tbody>
</table>


## Llamadas de RTC salientes

Se hace referencia a las rutas de voz en las directivas de voz asignadas directamente a los usuarios y, también, en las directivas de enrutamiento de voz asignadas a los sitios de red. Ambas directivas contienen referencias a rutas, que se pueden usar para redirigir una llamada de diferentes formas. Por ejemplo, un administrador puede definir una directiva de enrutamiento de voz para todos los usuarios ubicados en el sitio de red 1, para redirigir todas las llamadas salientes a través de la “Puerta de enlace del sitio 1”, mientras que la directiva de voz de algunos usuarios define una ruta para todas las llamadas salientes a través de la “Puerta de enlace del sitio 2”. Mientras estos usuarios se encuentren en el sitio de red 1, sus llamadas salientes se redirigirán a través de la “Puerta de enlace del sitio 1”.

Cuando un usuario se encuentra en un sitio de red configurado para el enrutamiento basado en ubicación, la ruta de la directiva de enrutamiento de voz del sitio de red reemplaza a la ruta de la directiva de voz del usuario. Esta regla es especialmente útil para los usuarios que se trasladan temporalmente a otro sitio. En este caso concreto, los usuarios utilizarán siempre una puerta de enlace local de su ubicación; si “Usuario de Lync 3” se encuentra en “Sitio 2”, todas sus llamadas salientes se redirigirán mediante la “Puerta de enlace del sitio 2” pero, si viaja al sitio 1, todas las llamadas salientes que realice mientras esté en el sitio 1 se redirigirán a través de la “Puerta de enlace del sitio 1”.

La siguiente tabla representa la experiencia del usuario de Usuario de Lync 1 al realizar una llamada saliente desde los siguientes sitios de red.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Sitio de red 1</th>
<th>Sitio de red 2</th>
<th>Sitio de red desconocido o no habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorización de llamadas salientes</p></td>
<td><p>Directiva de voz de Usuario de Lync 1</p></td>
<td><p>Directiva de voz de Usuario de Lync 1</p></td>
<td><p>Directiva de voz de Usuario de Lync 1</p></td>
</tr>
<tr class="even">
<td><p>Enrutamiento de llamadas salientes</p></td>
<td><p>Directiva de enrutamiento de voz del sitio 1</p></td>
<td><p>Directiva de enrutamiento de voz del sitio 2</p></td>
<td><p>La directiva de voz del usuario y solo a los sistemas no habilitados para el enrutamiento basado en ubicación</p></td>
</tr>
</tbody>
</table>


## Transferencias y desvíos de llamada

Al transferir o desviar llamadas, al enrutamiento de llamadas le afecta el enrutamiento basado en ubicación.

La siguiente tabla representa a Usuario de Lync 1 transfiriendo o desviando una llamada de RTC a otro usuario de Lync.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Usuario iniciando transferencia o desvío de llamada</th>
<th>Usuario de Lync 2</th>
<th>Usuario de Lync 4</th>
<th>Usuario de Lync en un sitio de red no habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario de Lync 1</p></td>
<td><p>Se permite el desvío o la transferencia de la llamada</p></td>
<td><p>No se permite el desvío ni la transferencia de la llamada</p></td>
<td><p>No se permite el desvío ni la transferencia de la llamada</p></td>
</tr>
</tbody>
</table>

  
La siguiente tabla ilustra cómo afecta el enrutamiento basado en ubicación a la manera de redirigir la llamada, según la ubicación del usuario de Lync al que se transfiere (Usuario de Lync 2, Usuario de Lync 4, etc.) a un extremo de RTC


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Extremo al que se transfiere o se desvía la llamada</th>
<th>Usuario de Lync 2</th>
<th>Usuario de Lync 4</th>
<th>Usuario de Lync en un sitio de red no habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extremo RTC</p></td>
<td><p>El desvío o la transferencia de llamada se redirige a través de la directiva de enrutamiento de voz del sitio 1 y sale a través de la Puerta de enlace del sitio 1</p></td>
<td><p>El desvío o la transferencia de llamada se redirige a través de la directiva de enrutamiento de voz del sitio 2 y sale a través de la Puerta de enlace del sitio 2</p></td>
<td><p>El desvío o la transferencia de llamada se redirige a través de la directiva de voz del usuario de Lync y sale a través de una puerta de enlace no habilitada para el enrutamiento basado en ubicación (si hay alguna disponible)</p></td>
</tr>
</tbody>
</table>


## Tono de llamada simultáneo

Una vez configurado el enrutamiento basado en ubicación en la topología de ejemplo, se exigen las siguientes interacciones.

La siguiente tabla ilustra si el enrutamiento basado en ubicación permite el tono de llamada simultáneo de diferentes usuarios de Lync (es decir, Usuario de Lync 2, Usuario de Lync 4, etc.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de llamada de RTC entrante</th>
<th>Usuario de Lync 2</th>
<th>Usuario de Lync 4</th>
<th>Usuario de Lync en un sitio de red no habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario de Lync 1</p></td>
<td><p>Se permite el tono de llamada simultáneo</p></td>
<td><p>No se permite el tono de llamada simultáneo</p></td>
<td><p>No se permite el tono de llamada simultáneo</p></td>
</tr>
</tbody>
</table>

  
La siguiente tabla ilustra si el enrutamiento basado en ubicación permite el tono de llamada simultáneo a un extremo de RTC desde diferentes usuarios de Lync (es decir, Usuario de Lync 2, Usuario de Lync 4, etc.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de llamadas simultáneas</th>
<th>Usuario de Lync 2</th>
<th>Usuario de Lync 4</th>
<th>Usuario de Lync en un sitio de red no habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Teléfono móvil de Usuario de Lync 1 (extremo de RTC)</p></td>
<td><p>La llamada se redirige a través de la directiva de enrutamiento de voz del sitio de red 1 y sale a través de la puerta de enlace del sitio 1</p></td>
<td><p>La llamada se redirige a través de la directiva de enrutamiento de voz del sitio de red 2 y sale a través de la puerta de enlace del sitio 2</p></td>
<td><p>La llamada se redirige a través de la directiva de voz del autor de la llamada y sale a través de una puerta de enlace de RTC no habilitada para el enrutamiento basado en ubicación</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Otros recursos

[Planificar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

