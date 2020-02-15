---
title: 'Lync Server 2013: supervisión del chat en grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb82eedd9d9578aeb4120136c1896267cde35392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Supervisión del chat en grupo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-04_

Se recomienda ejecutar el [programa de instalación de actualización de servidor acumulativa](http://support.microsoft.com/kb/968802) más reciente disponible en el centro de descarga de Microsoft para mejorar el rendimiento.

Suponiendo que ejecuta la actualización acumulativa más reciente, use la siguiente tabla de pruebas de esfuerzo para obtener información sobre las métricas para comprender si los servidores de chat en grupo se ejecutan con un estado óptimo.

### <a name="test-environment-and-user-model"></a>Entorno de prueba y modelo de usuario

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tres servidores de chat en grupo en un grupo de chats en grupo, cada uno con 8 GB de memoria y 8 procesadores.</p></td>
</tr>
<tr class="even">
<td><p>Dos front-ends de Lync Server 2013 en Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60.000 usuarios simultáneos en tres servidores de chat en grupo.</p></td>
</tr>
<tr class="even">
<td><p>25.000 canales hospedados por un grupo de servidores de chat.</p></td>
</tr>
<tr class="odd">
<td><p>Tamaño de canal:</p>
<ul>
<li><p>Tamaño de canal pequeño: 30</p></li>
<li><p>Tamaño de canal medio: 150</p></li>
<li><p>Tamaño de canal grande: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Número de canales:</p>
<ul>
<li><p>Número de canales pequeños: 24.000</p></li>
<li><p>Número medio canales 800</p></li>
<li><p>Número de canales grandes 24</p></li>
<li><p>Número total de canales 24.824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Canales de invitación:</p>
<ul>
<li><p>La mitad de los canales fueron invitaciones a canales</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Número de canales que un usuario ha incorporado:</p>
<ul>
<li><p>Pequeño: 12</p></li>
<li><p>Medio: 2</p></li>
<li><p>Grande: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Tasa de combinaciones:</p>
<ul>
<li><p>10 en total/segundo, 3,33/segundo por servidor</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Tasa de cierre de sesión:</p>
<ul>
<li><p>10 en total/segundo, 3,33/segundo por servidor</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Tasa de chat:</p>
<ul>
<li><p>20 en total/segundo, 6.66/segundo por servidor</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Los siguientes números de contadores de rendimiento probablemente variarán cuando se usen diferentes especificaciones de hardware o perfiles de usuario.



</div>

### <a name="performance-counter-to-be-monitored"></a>Contador de rendimiento que se va a supervisar

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contador de rendimiento</th>
<th>Umbrales</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Proceso (ChannelService)-&gt;% de tiempo de procesador</p></td>
<td><p>Min: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

