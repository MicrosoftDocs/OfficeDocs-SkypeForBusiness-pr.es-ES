---
title: 'Lync Server 2013: Proceso de implementación del estacionamiento de llamadas'
TOCTitle: Proceso de implementación del estacionamiento de llamadas
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48274654
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proceso de implementación del estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En esta sección se describe de forma general el proceso necesario para implementar la Aplicación de estacionamiento de llamadas. Para poder configurar el Estacionamiento de llamadas, debe implementar Enterprise Edition o Standard Edition con Telefonía IP empresarial. Los componentes que el Estacionamiento de llamadas necesita se instalan y habilitan cuando Telefonía IP empresarial se implementa.

### Proceso de implementación de estacionamiento de llamadas

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
<td><p>Configurar los intervalos de órbitas del estacionamiento de llamadas en la tabla de órbitas</p></td>
<td><p>Use el Panel de control de Lync Server o el cmdlet <strong>New-CSCallParkOrbit</strong> para crear los intervalos de órbitas en la tabla de órbitas de estacionamiento de llamadas y asócielos al Servicio de aplicaciones que hospeda la Aplicación de estacionamiento de llamadas.</p>
<div>

> [!NOTE]
> A fin de lograr una integración sin fisuras con los planes de marcado existentes, los intervalos de órbitas se suelen configurar como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de órbita.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Establecer la configuración del Estacionamiento de llamadas</p></td>
<td><p>Use el cmdlet <strong>Set-CsCpsConfiguration</strong> para establecer la configuración del Estacionamiento de llamadas. Como mínimo, se recomienda definir la opción <strong>OnTimeoutURI</strong> para configurar el destino de reserva que se va a usar cuando se agota el tiempo de una llamada estacionada. También se pueden configurar las siguientes opciones:</p>
<ul>
<li><p><strong>EnableMusicOnHold</strong> (opcional), con la que se habilita o deshabilita las música en espera.</p></li>
<li><p><strong>MaxCallPickupAttempts</strong> (opcional), que determina el número de veces que una llamada estacionada llama al teléfono de destino antes de reenviar la llamada al URI (identificador uniforme de recursos) de reserva.</p></li>
<li><p><strong>CallPickupTimeoutThreshold</strong> (opcional), que determina la cantidad de tiempo que transcurre desde que una llamada se aparca hasta que vuelve a llamar al teléfono que recibió la llamada.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Configuración del Estacionamiento de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>De manera opcional, personalice la música en espera</p></td>
<td><p>Use el cmdlet <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> para personalizar y cargar un archivo de audio en caso de que no desee usar la música en espera predeterminada.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personalización de la música de espera para el estacionamiento de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar la directiva de voz para habilitar el Estacionamiento de llamadas para los usuarios</p></td>
<td><p>Use el Panel de control de Lync Server o el cmdlet <strong>Set-CSVoicePolicy</strong> con la opción <strong>EnableCallPark</strong> para habilitar el Estacionamiento de llamadas para los usuarios en la directiva de voz.</p>
<div>

> [!NOTE]
> De forma predeterminada, la aplicación Estacionamiento de llamadas está deshabilitada para todos los usuarios.


</div>
<div>

> [!NOTE]
> Si existen varias directivas de voz, asegúrese de que la propiedad EnableCallPark se ha definido en todas ellas, no solo en la predeterminada.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Habilitar estacionamiento de llamadas para los usuarios en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Comprobar las reglas de normalización del Estacionamiento de llamadas</p></td>
<td><p>Las órbitas de estacionamiento de llamadas no deben estar normalizadas. Por lo tanto, compruebe que las reglas de normalización no contemplan ninguno de los intervalos de órbitas existentes. Si procede, cree más reglas de normalización con objeto de evitar que las órbitas se normalicen.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Comprobar las reglas de normalización para el estacionamiento de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Comprobar la implementación del Estacionamiento de llamadas</p></td>
<td><p>Pruebe el estacionamiento y recuperación de llamadas para asegurarse de que la configuración funcione del modo deseado.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Opcional) Comprobar la implementación del estacionamiento de llamadas en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

