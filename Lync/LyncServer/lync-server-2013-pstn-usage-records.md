---
title: 'Lync Server 2013: Registros de uso de RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5909494b4e4b6901964a7642481302ca221fe086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Registros de uso de RTC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-23_

Planificar los registros de uso de RTC consiste principalmente en elaborar una lista de todos los permisos de llamada vigentes actualmente en la organización, desde los permisos del presidente hasta los de los empleados temporales, consultores y personal contingente. Este proceso también brinda la oportunidad de volver a examinar los permisos de llamada existentes y modificarlos. Puede crear registros de uso de RTC solo para los permisos de llamada que se aplican a los usuarios de voz de empresa previstos, pero una mejor solución de larga duración podría ser crear registros de uso de RTC para todos los permisos de llamadas, independientemente de si algunos usuarios no pueden aplicar al grupo de usuarios que desea habilitar para la telefonía IP empresarial. Si cambian los permisos de llamada o se agregan usuarios nuevos con permisos de llamada diferentes, ya estarán creados los registros de uso de RTC necesarios.

A continuación se muestra una tabla del uso de RTC típico.

### <a name="pstn-usage-records"></a>Registros de uso de RTC

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
<td><p>Long-Distance</p></td>
<td><p>Llamadas de larga distancia</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
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
<td><p>Zurich</p></td>
<td><p>Empleados de jornada completa de Zúrich</p></td>
</tr>
</tbody>
</table>


Por sí mismos, los registros de uso de RTC no hacen nada. Para que funcionen, hay que asociarlos a:

  - Directivas de voz, que se asignan a los usuarios.

  - Rutas, que se asignan a los números de teléfono.

Para obtener más información sobre las rutas y directivas de voz, vea [directivas de voz en Lync server 2013](lync-server-2013-voice-policies.md) y [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md). Para obtener más información sobre cómo crear y configurar estos, vea [configurar rutas de voz para llamadas salientes en Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

</div>

<span> </span>

</div>

</div>

</div>

