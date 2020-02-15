---
title: 'Lync Server 2013: Planeación de la capacidad para el grupo de respuesta'
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
ms.openlocfilehash: 4e5724978347b50db2790e4d5798aace8489acbb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Planeación de la capacidad para el grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

<div id="sectionSection0" class="section">

En la tabla siguiente se describe el modelo de usuario del grupo de respuesta que puede usar como base para los requisitos de planeación de capacidad.

<div>


> [!NOTE]  
> Los números de la tabla siguiente suponen que usa archivos de onda de 16 bits (. wav) de 16 kHz para todos los archivos de audio del grupo de respuesta. Si usa otros formatos de archivo, como audio de Windows Media (. WMA), los números pueden variar.



</div>

<div>


> [!IMPORTANT]  
> Tenga en cuenta que para la planeación de la capacidad de recuperación ante desastres, cada grupo de servidores emparejados debe poder administrar las cargas de trabajo de todos los grupos de respuesta en ambos grupos.



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
<th>Biometría</th>
<th>Por grupo de servidores Enterprise Edition (con 8 servidores front-end)</th>
<th>Por servidor Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas entrantes por segundo</p></td>
<td><p>16 </p></td>
<td><p>2 </p></td>
</tr>
<tr class="even">
<td><p>Llamadas simultáneas conectadas a IVR o música</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Sesiones anónimas simultáneas (sin mi)</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>Sesiones anónimas simultáneas (con mi)</p></td>
<td><p>64</p></td>
<td><p>8 </p></td>
</tr>
<tr class="odd">
<td><p>Agentes activos (formales e informales)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>Número de grupos de extensiones</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>Número de grupos IVR (usar el reconocimiento de voz)</p></td>
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

