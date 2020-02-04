---
title: 'Lync Server 2013: Proceso de implementación para el enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e09106bc9d96fbfab2935aec07f3c472f49d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Proceso de implementación para el enrutamiento basado en ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Este tema proporciona una descripción general del proceso implicado en la configuración del enrutamiento basado en la ubicación. Debe implementar Lync Server Enterprise Edition o Standard Edition con Enterprise Voice antes de configurar el enrutamiento basado en la ubicación. Los componentes requeridos por el enrutamiento basado en la ubicación ya están instalados y habilitados al implementar la telefonía IP empresarial.

### <a name="location-based-routing-deployment-process"></a>Proceso de implementación de enrutamiento basado en la ubicación

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
<td><p>Implementar la telefonía IP empresarial</p></td>
<td><ul>
<li><p>Configurar los troncos</p></li>
<li><p>Crear directivas de voz</p></li>
<li><p>Definir rutas de voz</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Implementación de telefonía IP empresarial</p></td>
</tr>
<tr class="even">
<td><p>Comprobar la implementación de telefonía IP empresarial</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Configurar regiones, sitios y subredes de redes</p></td>
<td><ul>
<li><p>Crear regiones de red</p></li>
<li><p>Crear sitios de red</p></li>
<li><p>Asociar subredes con sitios de red</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Acerca de las regiones, sitios y subredes de la red<br />
Crear o modificar una región de red<br />
Crear o modificar un sitio de red<br />
Asociar una subred a un sitio de red</p></td>
</tr>
<tr class="even">
<td><p>Configurar el enrutamiento basado en la ubicación</p></td>
<td><ul>
<li><p>Crear directivas de enrutamiento de voz</p></li>
<li><p>Definir una configuración troncal separada por tronco</p></li>
<li><p>Modificar directivas de voz</p></li>
<li><p>Habilitar la configuración de enrutamiento basada en la ubicación</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>Implementación de ejemplo

La siguiente implementación se usa para ilustrar aún más los mecanismos habilitados por el enrutamiento basado en la ubicación.

![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>Llamadas RTC entrantes

Un administrador puede habilitar el tronco definido para enrutar llamadas a "puerta de enlace del sitio 1" para el enrutamiento basado en la ubicación y asociar la "puerta de enlace del sitio 1" al sitio 1. Una vez habilitadas, las llamadas que se dirigen a través de "puerta de enlace del sitio 1" solo se redirigirán a los usuarios que se encuentren en el sitio 1. Todas las llamadas dirigidas a través del "enlace de la puerta de enlace del sitio 1" dirigidas a usuarios de otro sitio, como el sitio 2, se bloquearán para evitar el bypass de llamadas RTC.

Todas las llamadas de RTC entrantes a través de "puerta de enlace del sitio 1" solo podrán enrutar a los puntos de conexión que se encuentren en el sitio 1. Por ejemplo, cuando "usuario de Lync 1" se desplaza al sitio 2, todas las llamadas RTC entrantes a través de "puerta de enlace del sitio 1" no se enrutarán a los puntos de conexión de "usuario de Lync 1" ubicados en el sitio 2. La misma regla de enrutamiento se aplica si "Lync User 1" se desplaza a un sitio de red desconocido en el que no se puede determinar la ubicación del usuario.

En la siguiente tabla se describe la experiencia del usuario de "Lync User 1" en este contexto.


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
<th>Puntos de conexión del usuario 1 de Lync ubicados en el sitio de red 1</th>
<th>Puntos de conexión del usuario 1 de Lync ubicados en el sitio de red 2</th>
<th>Puntos de conexión del usuario 1 de Lync ubicados en un sitio de red desconocido</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas RTC entrantes a usuarios de Lync 1</p></td>
<td><p>Las llamadas se enrutan a los puntos de conexión de esta ubicación</p></td>
<td><p>Las llamadas no se enrutan a los puntos de conexión de esta ubicación</p></td>
<td><p>Las llamadas no se enrutan a los puntos de conexión de esta ubicación</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>Llamadas RTC salientes

Las rutas de voz se mencionan en las dos directivas de voz asignadas directamente a los usuarios y las directivas de enrutamiento de voz asignadas a sitios de red. Ambas directivas contienen referencias a rutas, que se pueden usar para enrutar una llamada de otra manera. Por ejemplo, un administrador puede definir una directiva de enrutamiento de voz para todos los usuarios ubicados en el sitio de red 1 para enrutar todas las llamadas salientes a través de la "puerta de enlace del sitio 1", mientras que la Directiva de voz de algunos usuarios define una ruta para todas las llamadas salientes a través de la "puerta de enlace del sitio 2". Mientras estos usuarios se encuentren en el sitio 1 de la red, sus llamadas salientes se redirigirán a través de la "puerta de enlace del sitio 1".

Cuando un usuario se encuentra en un sitio de red configurado para el enrutamiento basado en la ubicación, la ruta de la Directiva de enrutamiento de voz del sitio de red invalida la ruta de la Directiva de voz del usuario. Esta regla es particularmente útil para los usuarios que se mueven temporalmente a un sitio diferente. En este caso concreto, un usuario siempre usará una puerta de enlace local a su ubicación; Si "el usuario de Lync 3" se encuentra en "sitio 2", todas sus llamadas salientes se enrutarán a través de "puerta de enlace del sitio 2", pero si viajan al sitio 1, todas sus llamadas salientes realizadas mientras está en el sitio 1 se dirigirán a través de la "puerta de enlace del sitio 1".

La tabla siguiente muestra la experiencia de usuario del usuario de Lync 1 que realiza una llamada saliente desde los siguientes sitios de red.


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
<th>Sitio de red desconocido o no habilitado para enrutamiento basado en la ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorización de llamadas salientes</p></td>
<td><p>Directiva de voz de usuario 1 de Lync</p></td>
<td><p>Directiva de voz de usuario 1 de Lync</p></td>
<td><p>Directiva de voz de usuario 1 de Lync</p></td>
</tr>
<tr class="even">
<td><p>Enrutamiento de llamadas salientes</p></td>
<td><p>Directiva de enrutamiento de voz del sitio 1</p></td>
<td><p>Directiva de enrutamiento de voz del sitio 2</p></td>
<td><p>Directiva de voz del usuario y solo en sistemas no habilitados para el enrutamiento basado en la ubicación</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>Transferencia de llamadas y reenvíos

Cuando se transfieren o desvian las llamadas, el enrutamiento de las llamadas se ve afectado por el enrutamiento basado en la ubicación.

En la tabla siguiente se muestra cómo el usuario de Lync 1 está transfiriendo o reenviando una llamada RTC a otro usuario de Lync.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>El usuario está iniciando la transferencia de llamadas o el reenvío</th>
<th>Usuario de Lync 2</th>
<th>Usuario de Lync 4</th>
<th>El usuario de Lync en el sitio de red no está habilitado para el enrutamiento basado en la ubicación</th>
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

  
La tabla siguiente muestra cómo el enrutamiento basado en la ubicación afecta al modo en que se enruta la llamada en función de la ubicación del usuario de Lync que se transfiere (Lync User 2, Lync User 4, etc.) a un punto final de RTC


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Punto final en el que se transfiere o reenvía una llamada</th>
<th>Usuario de Lync 2</th>
<th>Usuario de Lync 4</th>
<th>El usuario de Lync en el sitio de red no está habilitado para el enrutamiento basado en la ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>El desvío de llamadas o la transferencia se dirige a través de la Directiva de enrutamiento de voz del sitio 1 y de salida a través de la puerta de enlace del sitio 1</p></td>
<td><p>El desvío de llamadas o la transferencia se dirige a través de la Directiva de enrutamiento de voz del sitio 2 y de salida a través de la puerta de enlace del sitio 2</p></td>
<td><p>El desvío de llamadas o la transferencia se dirige a través de la Directiva de voz de usuario de Lync y se salida a través de una puerta de enlace no habilitada para enrutamiento basado en la ubicación (si está disponible)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>Tono de llamada simultáneo

Una vez que se configura el enrutamiento basado en la topología de muestra, se aplican las siguientes interacciones.

La siguiente tabla muestra si el enrutamiento basado en la ubicación permite llamadas simultáneas a diferentes usuarios de Lync (por ejemplo, usuario de Lync 2, usuario de Lync 4, etc.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de llamada RTC entrante</th>
<th>Usuario de Lync 2</th>
<th>Usuario de Lync 4</th>
<th>El usuario de Lync en el sitio de red no está habilitado para el enrutamiento basado en la ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario de Lync 1</p></td>
<td><p>Se permiten las llamadas simultáneas</p></td>
<td><p>No se permiten llamadas simultáneas</p></td>
<td><p>No se permiten llamadas simultáneas</p></td>
</tr>
</tbody>
</table>

  
En la tabla siguiente se muestra si el enrutamiento basado en la ubicación permite la llamada simultánea a un punto final de RTC de diferentes usuarios de Lync (por ejemplo, usuario de Lync 2, usuario de Lync 4, etc.).


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
<th>El usuario de Lync en el sitio de red no está habilitado para el enrutamiento basado en la ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario de Lync 1 teléfono móvil (punto final de la RTC)</p></td>
<td><p>Llamada dirigida a través de la Directiva de enrutamiento de voz del sitio de red 1 y salida a través de la puerta de enlace del sitio 1</p></td>
<td><p>Llamada dirigida a través de la Directiva de enrutamiento de voz del sitio de red 2 y salida a través de la puerta de enlace del sitio 2</p></td>
<td><p>Llamada enrutada a través de la Directiva de voz de la persona que llama y se dará de salida a través de una puerta de enlace RTC no habilitada para enrutamiento basado en la ubicación</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planificar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

