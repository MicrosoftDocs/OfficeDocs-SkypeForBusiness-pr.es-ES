---
title: 'Lync Server 2013: Configurar una ruta de conmutación por error'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e65070326c82e3a30977b3512bd2785d6bb4bd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a>Configurar una ruta de conmutación por error en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En el ejemplo siguiente se muestra cómo un administrador puede definir una ruta de conmutación por error para su uso si la GW1 de Dallas está desactivada para su mantenimiento o no está disponible. En las siguientes tablas se muestra el cambio de configuración requerido.

### <a name="table-1-user-policy"></a>Tabla 1. Directiva de usuario

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Directiva de usuario</th>
<th>Uso del teléfono</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Directiva de llamadas predeterminada</p></td>
<td><p>Local</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Directiva local de Redmond</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>Política de llamadas de Dallas</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a>Tabla 2. Redirige

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
<th>Nombre de la ruta</th>
<th>Patrón de números</th>
<th>Uso del teléfono</th>
<th>Tronco</th>
<th>Puerta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Camino local de Redmond</p></td>
<td><p>^\+1 (425 | 206 | 253) (\d{7}) $</p></td>
<td><p>Local</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>Rojo: GW1</p>
<p>Rojo: GW2</p></td>
</tr>
<tr class="even">
<td><p>Ruta local de Dallas</p></td>
<td><p>^\+1 (972 | 214 | 469) (\d{7}) $</p></td>
<td><p>Local</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
<tr class="odd">
<td><p>Ruta universal</p></td>
<td><p>^\+? (\d *) $</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>Rojo: GW1</p>
<p>Rojo: GW2</p>
<p>Dallas-GW1</p></td>
</tr>
<tr class="even">
<td><p>Ruta de usuarios de Dallas</p></td>
<td><p>^\+? (\d *) $</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas-GW1</p></td>
</tr>
</tbody>
</table>


En la tabla 1, se agrega un uso de teléfono de GlobalPSTNHopoff después del uso del teléfono DallasUsers en la política de llamadas de Dallas. Esto permite que las llamadas con la Directiva de llamadas de Dallas usen rutas configuradas para el uso del teléfono GlobalPSTNHopoff si una ruta para el uso del teléfono DallasUsers no está disponible.

</div>

<span> </span>

</div>

</div>

</div>

