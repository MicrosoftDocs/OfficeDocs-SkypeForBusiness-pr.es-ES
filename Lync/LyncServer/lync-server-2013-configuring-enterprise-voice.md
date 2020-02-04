---
title: 'Lync Server 2013: configuración de telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d6bf9f79725f1f4812ac1e1c1c3c0e3217b939b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Configurar la telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-12_

Para implementar la telefonía IP empresarial, tendrá que configurar lo siguiente:

  - Crear un tronco

  - Definir una directiva de voz

  - Definir una ruta de voz

  - Enable Users for Enterprise Voice

<div>

## <a name="create-a-trunk"></a>Crear un tronco

Debe definir los troncos en su implementación de telefonía IP empresarial. Para el enrutamiento basado en la ubicación, debe crear una configuración troncal por tronco. Use el generador de topología de Lync Server para definir sus troncos y use el comando de Windows PowerShell de Lync Server, New-CsTrunkConfiguration o el panel de control de Lync Server para definir las configuraciones de troncal correspondientes. Para obtener más información sobre cómo habilitar el enrutamiento basado en la ubicación en las configuraciones troncales, vaya a la sección habilitar el enrutamiento basado en la ubicación para los troncos, en el tema [Habilitar el enrutamiento basado en la ubicación en Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). En este ejemplo, la tabla siguiente muestra las troncos que se usan en este escenario.

Para obtener más información, vea [definir más troncos en el generador de topología en Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


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
<td><p>Tronco 1 DEL-GW</p></td>
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


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>Define directivas de voz

Debe definir directivas de voz para su implementación de telefonía IP empresarial. Defina una directiva de voz para aplicar restricciones de enrutamiento basado en la ubicación a un subconjunto de usuarios si solo se necesita un subconjunto de ellas para usar el enrutamiento basado en la ubicación. En este ejemplo, la tabla siguiente muestra las directivas de voz que se usan en este escenario. En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.

Para obtener más información, vea [configuración de directivas de voz y registros de uso de RTC para autorizar llamadas y características de Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Política de voz 1</th>
<th>Política de voz 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IDENTIFICADOR de la Directiva de voz</p></td>
<td><p>Directiva de voz de Delhi</p></td>
<td><p>Política de voz de Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso de la Delhi, PBX del uso, uso de HYD de PBX</p></td>
<td><p>Uso de Hyderabad, uso de HYD de PBX, PBX del uso</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>Falso</p></td>
<td><p>Falso</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>Definir rutas de voz

Debe definir rutas de voz para su implementación de telefonía IP empresarial. En este ejemplo, la tabla siguiente muestra las rutas de voz usadas en este escenario. En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.

Para obtener más información, consulte [configuración de rutas de voz para llamadas salientes en Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


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
<td><p>Ruta de Delhi</p></td>
<td><p>Ruta de Hyderabad</p></td>
<td><p>PBX del camino</p></td>
<td><p>Ruta de HYD PBX</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso de Delhi</p></td>
<td><p>Uso de Hyderabad</p></td>
<td><p>Uso de PBX</p></td>
<td><p>Uso de HYD de PBX</p></td>
</tr>
<tr class="odd">
<td><p>Tronco</p></td>
<td><p>Tronco 1 DEL-GW</p></td>
<td><p>Troncal 2 HYD-GW</p></td>
<td><p>Troncal 3 DEL-PBX</p></td>
<td><p>Troncal 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Enable Users for Enterprise Voice

Habilitar a los usuarios para la telefonía IP empresarial y asignarles una directiva de voz que haya definido previamente. En este ejemplo, la tabla siguiente muestra la asignación que se usa en este escenario. En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.

Para obtener más información, consulte [Habilitar usuarios para telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


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
<th>Usuarios que se encuentran en Hyderabad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Directiva de voz asociada</p></td>
<td><p>Directiva de voz de Delhi</p></td>
<td><p>Política de voz de Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usuarios de muestra</p></td>
<td><p>DE-LYNC-1, DE-LYNC-2, DE-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

