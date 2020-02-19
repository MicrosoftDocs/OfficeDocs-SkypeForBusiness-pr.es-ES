---
title: 'Lync Server 2013: proceso de implementación para el enrutamiento basado en ubicación'
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
ms.openlocfilehash: 46da1be1d18477d56fa4b3046557102e8771ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Proceso de implementación para el enrutamiento basado en ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

En este tema se proporciona información general sobre el proceso implicado en la configuración del enrutamiento basado en ubicación. Debe implementar Lync Server Enterprise Edition o Standard Edition con Enterprise Voice antes de configurar el enrutamiento basado en ubicación. Los componentes requeridos por el enrutamiento basado en ubicación ya están instalados y habilitados al implementar la telefonía IP empresarial.

### <a name="location-based-routing-deployment-process"></a>Proceso de implementación de enrutamiento basado en ubicación

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
<li><p>Configuración de troncos</p></li>
<li><p>Crear directivas de voz</p></li>
<li><p>Definir rutas de voz</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Implementación de telefonía IP empresarial</p></td>
</tr>
<tr class="even">
<td><p>Comprobar la implementación de la telefonía IP empresarial</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Configuración de regiones de red, sitios y subredes</p></td>
<td><ul>
<li><p>Crear regiones de red</p></li>
<li><p>Crear sitios de red</p></li>
<li><p>Asociar subredes con sitios de red</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Acerca de las regiones de red, sitios y subredes<br />
Crear o modificar una región de red<br />
Crear o modificar un sitio de red<br />
Asociar una subred a un sitio de red</p></td>
</tr>
<tr class="even">
<td><p>Configurar el enrutamiento basado en ubicación</p></td>
<td><ul>
<li><p>Crear directivas de enrutamiento de voz</p></li>
<li><p>Definir una configuración de tronco separada por tronco</p></li>
<li><p>Modificar directivas de voz</p></li>
<li><p>Habilitar la configuración de enrutamiento basada en ubicación</p></li>
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

La siguiente implementación se usa para ilustrar aún más los mecanismos habilitados por el enrutamiento basado en ubicación.

![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>Llamadas RTC entrantes

Un administrador puede habilitar el tronco definido para enrutar las llamadas a "puerta de enlace del sitio 1" para el enrutamiento basado en ubicación y asociar la "puerta de enlace del sitio 1" al sitio 1. Una vez habilitada, las llamadas que se redirigen a través de "puerta de enlace del sitio 1" solo se enrutarán a los usuarios que se encuentren en el sitio 1. Todas las llamadas enrutadas a través del tronco "puerta de enlace de sitio 1" dirigidas a los usuarios de un sitio diferente, como el sitio 2, se bloquearán para evitar el desvío de llamadas RTC.

Todas las llamadas RTC entrantes a través de la "puerta de enlace del sitio 1" solo se permitirán enrutar a extremos ubicados en el sitio 1. Por ejemplo, cuando "el usuario de Lync 1" se desplaza al sitio 2, todas las llamadas RTC entrantes a través de la "puerta de enlace del sitio 1" no se enrutarán a los puntos de conexión de "usuario de Lync 1" ubicados en el sitio 2. La misma regla de enrutamiento se aplica si "Lync User 1" se desplaza a un sitio de red desconocido en el que no se puede determinar la ubicación del usuario.

En la tabla siguiente se describe la experiencia del usuario de "Lync User 1" en este contexto.


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
<th>Extremos del usuario de Lync 1 ubicados en el sitio de red 1</th>
<th>Extremos del usuario de Lync 1 ubicados en el sitio de red 2</th>
<th>Extremos del usuario de Lync 1 ubicados en un sitio de red desconocido</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas RTC entrantes a Lync User 1</p></td>
<td><p>Las llamadas se enrutan a los extremos en esta ubicación</p></td>
<td><p>Las llamadas no se enrutan a los extremos en esta ubicación</p></td>
<td><p>Las llamadas no se enrutan a los extremos en esta ubicación</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>Llamadas RTC salientes

Se hace referencia a las rutas de voz en las dos directivas de voz asignadas directamente a los usuarios y en las directivas de enrutamiento de voz asignadas a los sitios de red. Ambas directivas contienen referencias a rutas, que se pueden usar para enrutar una llamada de forma diferente. Por ejemplo, un administrador puede definir una directiva de enrutamiento de voz para todos los usuarios ubicados en el sitio de red 1 para enrutar todas las llamadas salientes a través de la "puerta de enlace del sitio 1", mientras que la Directiva de voz de algunos usuarios define una ruta para todas las llamadas salientes a través de la "puerta de enlace del sitio 2". Mientras que estos usuarios se encuentran en el sitio de red 1, sus llamadas salientes se enrutarán a través de la "puerta de enlace del sitio 1".

Cuando un usuario se encuentra en un sitio de red configurado para el enrutamiento basado en ubicación, la ruta de la Directiva de enrutamiento de voz del sitio de red invalida la ruta de la Directiva de voz del usuario. Esta regla es especialmente útil para los usuarios que se mueven temporalmente a un sitio diferente. En este caso concreto, un usuario siempre usará una puerta de enlace local a su ubicación; Si el "usuario de Lync 3" se encuentra en "sitio 2", todas sus llamadas salientes se enrutarán a través de "puerta de enlace de sitio 2", pero si viajan al sitio 1, todas las llamadas salientes realizadas mientras se encuentre en el sitio 1 se enrutarán a través de la "puerta de enlace del sitio 1".

En la tabla siguiente se muestra la experiencia del usuario de Lync usuario 1 que realiza una llamada saliente desde los siguientes sitios de red.


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
<td><p>Directiva de voz del usuario 1 de Lync</p></td>
<td><p>Directiva de voz del usuario 1 de Lync</p></td>
<td><p>Directiva de voz del usuario 1 de Lync</p></td>
</tr>
<tr class="even">
<td><p>Enrutamiento de llamadas salientes</p></td>
<td><p>Directiva de enrutamiento de voz de sitio 1</p></td>
<td><p>Directiva de enrutamiento de voz de sitio 2</p></td>
<td><p>Directiva de voz del usuario y solo en sistemas no habilitados para el enrutamiento basado en ubicación</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>Transferencias y reenvío de llamadas

Cuando se transfieren o reenvían llamadas, el enrutamiento de las llamadas se ve afectado por el enrutamiento basado en ubicación.

La siguiente tabla muestra el usuario de Lync 1 que transfiere o reenvía una llamada RTC a otro usuario de Lync.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Inicio de la transferencia o reenvío de llamadas de usuario</th>
<th>Lync usuario 2</th>
<th>Lync usuario 4</th>
<th>El usuario de Lync del sitio de red no está habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync usuario 1</p></td>
<td><p>Se permite la transferencia o el desvío de llamadas</p></td>
<td><p>No se permite el desvío o la transferencia de llamadas</p></td>
<td><p>No se permite el desvío o la transferencia de llamadas</p></td>
</tr>
</tbody>
</table>

  
En la tabla siguiente se muestra cómo el enrutamiento basado en ubicación afecta a cómo se enruta la llamada en función de la ubicación del usuario de Lync que se está transfiriendo (Lync User 2, Lync User 4, etc.) a un punto de conexión de RTC.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Punto de conexión en el que se transfiere o reenvía una llamada</th>
<th>Lync usuario 2</th>
<th>Lync usuario 4</th>
<th>El usuario de Lync del sitio de red no está habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extremo de RTC</p></td>
<td><p>La transferencia o desvío de llamadas se enruta a través de la Directiva de enrutamiento de voz del sitio 1 y de salida a través de la puerta de enlace del sitio 1</p></td>
<td><p>La transferencia o desvío de llamadas se enruta a través de la Directiva de enrutamiento de voz del sitio 2 y de salida a través de la puerta de enlace del sitio 2</p></td>
<td><p>La transferencia o desvío de llamadas se redirige a través de la Directiva de voz de usuario de Lync y se salida a través de una puerta de enlace no habilitada para el enrutamiento basado en ubicación (si está disponible)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>Llamadas simultáneas

Una vez que se haya configurado el enrutamiento basado en ubicación en la topología de muestra, se aplican las siguientes interacciones.

En la tabla siguiente se muestra si el enrutamiento basado en ubicación permite las llamadas simultáneas para diferentes usuarios de Lync (por ejemplo, el usuario de Lync 2, el usuario de Lync 4, etc.).


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
<th>Lync usuario 2</th>
<th>Lync usuario 4</th>
<th>El usuario de Lync del sitio de red no está habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync usuario 1</p></td>
<td><p>Se permite la llamada simultánea</p></td>
<td><p>No se permite la llamada simultánea</p></td>
<td><p>No se permite la llamada simultánea</p></td>
</tr>
</tbody>
</table>

  
La siguiente tabla muestra si el enrutamiento basado en ubicación permite realizar llamadas simultáneas a un punto de conexión de RTC de diferentes usuarios de Lync (por ejemplo, el usuario de Lync 2, el usuario de Lync 4, etc.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de llamada simultánea</th>
<th>Lync usuario 2</th>
<th>Lync usuario 4</th>
<th>El usuario de Lync del sitio de red no está habilitado para el enrutamiento basado en ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuario de Lync 1 teléfono móvil (extremo de RTC)</p></td>
<td><p>Llamada enrutada a través de la Directiva de enrutamiento de voz del sitio de red 1 y salida a través de la puerta de enlace del sitio 1</p></td>
<td><p>Llamada enrutada a través de la Directiva de enrutamiento de voz del sitio 2 de red y salida a través de la puerta de enlace del sitio 2</p></td>
<td><p>Llamada enrutada a través de la Directiva de voz del autor de la llamada y se deshará a través de una puerta de enlace RTC que no está habilitada para el enrutamiento basado en ubicación</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación del enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

