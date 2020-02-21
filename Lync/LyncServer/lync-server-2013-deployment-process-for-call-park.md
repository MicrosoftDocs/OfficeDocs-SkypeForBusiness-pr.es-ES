---
title: 'Lync Server 2013: proceso de implementación del estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6e11f85cb929cdd3dbddcab23caaffcf434f303
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Proceso de implementación del estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

En esta sección se proporciona información general sobre los pasos necesarios para implementar la aplicación de estacionamiento de llamadas. Debe implementar Enterprise Edition o Standard Edition con Enterprise Voice antes de configurar el estacionamiento de llamadas. Los componentes requeridos por el estacionamiento de llamadas se instalan y habilitan al implementar la telefonía IP empresarial.

### <a name="call-park-deployment-process"></a>Proceso de implementación de estacionamiento de llamadas

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
<td><p>Use el panel de control de Lync Server o el cmdlet <strong>New-CSCallParkOrbit</strong> para crear intervalos de órbitas en la tabla de órbitas de estacionamiento de llamadas y asociarlos con el servicio de aplicación que hospeda la aplicación de estacionamiento de llamadas.</p>
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
<td><p>Configurar las opciones del estacionamiento de llamadas</p></td>
<td><p>Use el cmdlet <strong>set-CsCpsConfiguration</strong> para configurar las opciones de estacionamiento de llamadas. Como mínimo, se recomienda configurar la opción <strong>OnTimeoutURI</strong> para configurar el destino de reserva que se usará cuando se agote el tiempo de espera de una llamada estacionada. También puede configurar las siguientes opciones:</p>
<ul>
<li><p><strong>EnableMusicOnHold</strong> (opcional), con la que se habilita o deshabilita las música en espera.</p></li>
<li><p><strong>MaxCallPickupAttempts</strong> (opcional), que determina el número de veces que una llamada estacionada llama al teléfono de destino antes de reenviar la llamada al URI (identificador uniforme de recursos) de reserva.</p></li>
<li><p><strong>CallPickupTimeoutThreshold</strong> (opcional), que determina la cantidad de tiempo que transcurre desde que una llamada se aparca hasta que vuelve a llamar al teléfono que recibió la llamada.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Configurar las opciones del estacionamiento de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>De manera opcional, personalice la música en espera</p></td>
<td><p>Use el cmdlet <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> para personalizar y cargar un archivo de audio en caso de que no desee usar la música en espera predeterminada.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personalizar la música de estacionamiento de llamadas en espera en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar la Directiva de voz para habilitar el estacionamiento de llamadas para los usuarios</p></td>
<td><p>Use el panel de control de Lync Server o el cmdlet <strong>set-CSVoicePolicy</strong> con la opción <strong>EnableCallPark</strong> para habilitar el estacionamiento de llamadas para los usuarios en la Directiva de voz.</p>
<div>

> [!NOTE]  
> De forma predeterminada, el estacionamiento de llamadas está deshabilitado para todos los usuarios.


</div>
<div>

> [!NOTE]  
> Si existen varias directivas de voz, asegúrese de que la propiedad EnableCallPark se ha definido en todas ellas, no solo en la predeterminada.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Habilitar el estacionamiento de llamadas para los usuarios en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Comprobar reglas de normalización para el estacionamiento de llamadas</p></td>
<td><p>Las órbitas de estacionamiento de llamadas no deben estar normalizadas. Por lo tanto, compruebe que las reglas de normalización no contemplan ninguno de los intervalos de órbitas existentes. Si procede, cree más reglas de normalización con objeto de evitar que las órbitas se normalicen.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Comprobar reglas de normalización para el estacionamiento de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Comprobar la implementación del estacionamiento de llamadas</p></td>
<td><p>Pruebe el estacionamiento y la recuperación de llamadas para asegurarse de que la configuración funciona según lo esperado.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">Opcional Comprobar la implementación del estacionamiento de llamadas en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

