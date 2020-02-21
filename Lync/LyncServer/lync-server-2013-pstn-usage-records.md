---
title: 'Lync Server 2013: registros de uso de RTC'
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
ms.openlocfilehash: 81f459c7ae6b581dedc5843fd2a89568a2f755a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Registros de uso de RTC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-23_

La planeación de los registros de uso de RTC consiste principalmente en enumerar todos los permisos de llamada que hay actualmente en vigor en la organización, desde el CEO hasta trabajadores temporales, consultores y personal contingente. Este proceso también ofrece la oportunidad de volver a examinar los permisos de llamada existentes y revisarlos. Puede crear registros de uso de RTC solo para los permisos de llamada que se aplican a los usuarios de voz de empresa que se prevén, pero una mejor solución de largo alcance puede ser crear registros de uso de RTC para todos los permisos de llamadas, independientemente de si algunos no se encuentran se aplican al grupo de usuarios que se van a habilitar para la telefonía IP empresarial. Si los permisos de llamada cambian o se agregan nuevos usuarios con permisos de llamada diferentes, ya habrá creado los registros de uso de RTC necesarios.

En la tabla siguiente se muestra una tabla típica de uso de RTC.

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
<td><p>A larga distancia</p></td>
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
<td><p>Zúrich</p></td>
<td><p>Zurich empleados a tiempo completo</p></td>
</tr>
</tbody>
</table>


Por sí mismos, los registros de uso de RTC no hacen nada. Para que funcionen, debe asociarlos con lo siguiente:

  - Directivas de voz, que se asignan a los usuarios.

  - Rutas, que se asignan a números de teléfono.

Para obtener más información sobre las rutas y directivas de voz, consulte [directivas de voz en Lync server 2013](lync-server-2013-voice-policies.md) y [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md). Para obtener más información sobre cómo crear y configurar estas rutas de voz, consulte [Configuring Voice Routes for Outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

</div>

<span> </span>

</div>

</div>

</div>

