---
title: 'Lync Server 2013: configurar la telefonía IP empresarial'
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
ms.openlocfilehash: 76105b9bee5ce35801196b5a4cd20b2a1feed3e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Configurar la telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-12_

Para implementar la telefonía IP empresarial, deberá configurar lo siguiente:

  - Crear un tronco

  - Definir una directiva de voz

  - Definir una ruta de voz

  - Habilitar usuarios para Enterprise Voice

<div>

## <a name="create-a-trunk"></a>Crear un tronco

Debe definir troncos en su implementación de telefonía IP empresarial. Para el enrutamiento basado en ubicación, debe crear una configuración de tronco por tronco. Use el generador de topologías de Lync Server para definir los troncos y use el comando de Windows PowerShell de Lync Server, New-CsTrunkConfiguration o el panel de control de Lync Server para definir las configuraciones de tronco correspondientes. Encontrará más información sobre cómo habilitar el enrutamiento basado en ubicación en las configuraciones de tronco en la sección, habilitar el enrutamiento basado en ubicación a troncos, en el tema [Habilitar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). En este ejemplo, en la tabla siguiente se muestran los troncos que se usan en este escenario.

Para obtener más información, consulte [definir troncos adicionales en el generador de topologías en Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


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
<td><p>Una puerta de enlace RTC</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Tronco 2 HYD-GW</p></td>
<td><p>Una puerta de enlace RTC</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Tronco 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Tronco 4 HYD-PBX</p></td>
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

Debe definir directivas de voz para la implementación de telefonía IP empresarial. Definir una directiva de voz para aplicar restricciones de enrutamiento basadas en la ubicación a un subconjunto de usuarios si solo se requiere un subconjunto de ellas para usar el enrutamiento basado en la ubicación. En este ejemplo, la tabla siguiente muestra las directivas de voz usadas en este escenario. Solo la configuración específica para el enrutamiento basado en ubicación se incluye en la tabla con fines ilustrativos.

Para obtener más información, vea [configuración de directivas de voz y registros de uso de RTC para autorizar características y privilegios de llamada en Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


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
<td><p>IDENTIFICADOR de la Directiva de voz</p></td>
<td><p>Directiva de voz de Delhi</p></td>
<td><p>Directiva de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso de Delhi, PBX del uso, uso de HYD de PBX</p></td>
<td><p>Uso de Hyderabad, uso de HYD de PBX, PBX del uso</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>Definir rutas de voz

Debe definir rutas de voz para la implementación de telefonía IP empresarial. En este ejemplo, la tabla siguiente muestra las rutas de voz usadas en este escenario. Solo la configuración específica para el enrutamiento basado en ubicación se incluye en la tabla con fines ilustrativos.

Para obtener más información, consulte [configurar rutas de voz para llamadas salientes en Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


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
<td><p>Ruta Hyderabad</p></td>
<td><p>PBX del camino</p></td>
<td><p>Ruta de HYD de PBX</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso de Delhi</p></td>
<td><p>Uso de Hyderabad</p></td>
<td><p>PBX del uso</p></td>
<td><p>Uso de HYD de PBX</p></td>
</tr>
<tr class="odd">
<td><p>Tronco</p></td>
<td><p>Tronco 1 DEL-GW</p></td>
<td><p>Tronco 2 HYD-GW</p></td>
<td><p>Tronco 3 DEL-PBX</p></td>
<td><p>Tronco 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Habilitar usuarios para Enterprise Voice

Habilite a los usuarios para la telefonía IP empresarial y asígneles una directiva de voz que haya definido previamente. En este ejemplo, en la tabla siguiente se muestra la asignación que se usa en este escenario. Solo la configuración específica para el enrutamiento basado en ubicación se incluye en la tabla con fines ilustrativos.

Para obtener más información, consulte [enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


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
<td><p>Directiva de voz de Delhi</p></td>
<td><p>Directiva de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usuarios de muestra</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración del enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

