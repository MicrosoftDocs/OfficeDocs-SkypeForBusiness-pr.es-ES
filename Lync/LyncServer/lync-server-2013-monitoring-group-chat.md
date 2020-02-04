---
title: 'Lync Server 2013: supervisión del chat grupal'
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
ms.openlocfilehash: fa350924503f430ec0494cc5e1eb17f7878084a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Supervisión de la conversación de grupo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-04_

Recomendamos encarecidamente ejecutar el [programa de instalación de actualización de servidor acumulativo](http://support.microsoft.com/kb/968802) más reciente disponible en el centro de descarga de Microsoft para mejorar el rendimiento.

Suponiendo que está ejecutando la actualización acumulativa más reciente, use la siguiente tabla de pruebas de estrés para ver si los servidores de chat de grupo se ejecutan con un estado óptimo.

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
<td><p>Tres servidores de chat grupales en un grupo de chats grupales, cada uno con memoria de 8 GB y 8 procesadores.</p></td>
</tr>
<tr class="even">
<td><p>Dos servidores front-end de Lync Server 2013 en Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60.000 usuarios simultáneos en tres servidores de chats grupales.</p></td>
</tr>
<tr class="even">
<td><p>25.000 canales alojados en un grupo de chats grupales.</p></td>
</tr>
<tr class="odd">
<td><p>Tamaño del canal:</p>
<ul>
<li><p>Tamaño de canal pequeño: 30</p></li>
<li><p>Tamaño de canal medio: 150</p></li>
<li><p>Tamaño de canal grande: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Recuento de canales:</p>
<ul>
<li><p>Canales pequeños de números: 24.000</p></li>
<li><p>Número de canales media 800</p></li>
<li><p>Número de canales grandes 24</p></li>
<li><p>Número total de canales 24.824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Canales de invitación:</p>
<ul>
<li><p>La mitad de los canales fueron invitar a canales</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Número de canales que un usuario se une:</p>
<ul>
<li><p>Pequeño: 12</p></li>
<li><p>Medio: 2</p></li>
<li><p>Grande: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Tasa de participación:</p>
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
<td><p>Tarifa de chat:</p>
<ul>
<li><p>20 en total/segundo, 6.66/segundo por servidor</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Los siguientes números de contador de rendimiento probablemente variarán cuando se usen especificaciones de hardware o perfiles de usuario diferentes.



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
<th>Los</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Proceso (ChannelService):&gt;% de tiempo de procesador</p></td>
<td><p>Mín: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

