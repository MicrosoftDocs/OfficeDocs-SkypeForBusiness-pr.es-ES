---
title: 'Lync Server 2013: Planeación de la capacidad para el estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1192ef9b5b30c722a4f62973cf4992da3ca7300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Planeación de la capacidad para el estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-13_

<div id="sectionSection0" class="section">

En la tabla siguiente se describe el modelo de usuario de estacionamiento de llamadas que puede usar como base para los requisitos de planeación de capacidad.

<div>


> [!IMPORTANT]  
> Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de servidores emparejados debe poder administrar las cargas de trabajo para los servicios de estacionamiento de llamadas en ambos grupos.



</div>

### <a name="call-park-user-model"></a>Modelo de usuario de estacionamiento de llamadas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Biometría</th>
<th>Por grupo de servidores front-end (con 8 servidores front-end)</th>
<th>Por servidor Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tasa de estacionamiento</p></td>
<td><p>8 por minuto</p></td>
<td><p>1 por minuto</p></td>
</tr>
<tr class="even">
<td><p>Recuperar la tasa de llamadas estacionadas</p></td>
<td><p>8 por minuto</p></td>
<td><p>1 por minuto</p></td>
</tr>
<tr class="odd">
<td><p>Duración media del estacionamiento</p></td>
<td><p>60 segundos</p></td>
<td><p>60 segundos</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

