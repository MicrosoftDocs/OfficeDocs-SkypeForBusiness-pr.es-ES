---
title: 'Lync Server 2013: Planificar la capacidad para el grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efb1b928ce7b4bafbbff20ad31872fe12735fe0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Planificar la capacidad para el grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

<div id="sectionSection0" class="section">

En la siguiente tabla se describe el modelo de usuario de grupo de respuesta que puede usar como base para los requisitos de planes de capacidad.

<div>


> [!NOTE]  
> En las cantidades de la tabla siguiente se presupone que usas archivos wave (.wav) mono de 16 bits a 16 kHz para todos los archivos de audio del grupo de respuesta. Si usas otros formatos de archivo, como audio de Windows Media (.wma), las cantidades pueden variar.



</div>

<div>


> [!IMPORTANT]  
> Ten en cuenta que, para planificar la capacidad de la recuperación ante desastres, cada grupo de un grupo emparejado necesita poder gestionar las cargas de trabajo para todos los grupos de respuesta en ambos grupos.



</div>

### <a name="response-group-user-model"></a>Modelo de usuario del grupo de respuesta

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Métrica</th>
<th>Por grupo de servidores Enterprise (con 8 servidores front-end)</th>
<th>Por servidor Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas entrantes por segundo</p></td>
<td><p>apartado</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>Llamadas simultáneas conectadas a IVR o a la música en espera</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Sesiones anónimas simultáneas (sin MI)</p></td>
<td><p>224</p></td>
<td><p>apartado</p></td>
</tr>
<tr class="even">
<td><p>Sesiones anónimas simultáneas (con MI)</p></td>
<td><p>64</p></td>
<td><p>4,8</p></td>
</tr>
<tr class="odd">
<td><p>Agentes activos (formales e informales)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>Cantidad de grupos de extensiones</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad de grupos de IVR (uso del reconocimiento de voz)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

