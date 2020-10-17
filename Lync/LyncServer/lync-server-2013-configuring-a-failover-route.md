---
title: 'Lync Server 2013: configurar una ruta de conmutación por error'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0a3a0d3b2eb2d505ff345af66ae8ccbcc551ee8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520067"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a>Configurar una ruta de conmutación por error en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En el siguiente ejemplo se muestra cómo puede un administrador definir una ruta de conmutación por error para usarla en caso de que se desconecte Dallas-GW1 por motivos de mantenimiento o no esté disponible. En las tablas siguientes se muestra el cambio de configuración necesario.

### <a name="table-1-user-policy"></a>Tabla 1. Directiva de usuario

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Directiva de usuario</th>
<th>Uso de teléfono</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Directiva de llamada predeterminada</p></td>
<td><p>Local</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Directiva local de Redmond</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>Directiva de llamada de Dallas</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a>Tabla 2. Rutas

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
<th>Nombre de ruta</th>
<th>Modelo de número</th>
<th>Uso de teléfono</th>
<th>Tronco</th>
<th>Puerta de enlace</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ruta local de Redmond</p></td>
<td><p>^\+1 (425 | 206 | 253) (\d {7} ) $</p></td>
<td><p>Local</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>Rojo-GW1</p>
<p>Rojo-GW2</p></td>
</tr>
<tr class="even">
<td><p>Ruta local de Dallas</p></td>
<td><p>^\+1 (972 | 214 | 469) (\d {7} ) $</p></td>
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
<td><p>Rojo-GW1</p>
<p>Rojo-GW2</p>
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


En la Tabla 1, se agrega el uso de teléfono GlobalPSTNHopoff después del uso de teléfono DallasUsers en la directiva de llamada de Dallas. Esto permite que las llamadas con la directiva de llamada de Dallas usen las rutas configuradas para el uso de teléfono GlobalPSTNHopoff en caso de que una ruta para el uso telefónico DallasUsers no esté disponible.

</div>

<span> </span>

</div>

</div>

</div>

