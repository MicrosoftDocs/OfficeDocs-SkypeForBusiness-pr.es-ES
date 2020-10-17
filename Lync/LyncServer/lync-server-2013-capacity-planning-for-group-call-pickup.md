---
title: 'Lync Server 2013: Planeación de la capacidad para la recogida de llamadas de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c073ea360e00b196e6cf30b6bb6f204d37532ae0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512817"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Planeación de la capacidad para la recogida de llamadas grupales en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-12_

<div id="sectionSection0" class="section">

En la tabla siguiente se describe el modelo de usuario de llamada de grupo que puede usar como base para los requisitos de planeación de capacidad.

<div>


> [!IMPORTANT]  
> La recogida de llamadas de grupo se basa en la aplicación de estacionamiento de llamadas. Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de servidores emparejados debe poder administrar las cargas de trabajo para los servicios de estacionamiento de llamadas, incluida la atención de llamadas grupales, en ambos grupos.



</div>

### <a name="group-call-pickup-user-model"></a>Modelo de usuario de llamada de grupo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Métrica</th>
<th>Por grupo de servidores front-end (con 8 servidores front-end)</th>
<th>Por servidor Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Número recomendado de usuarios por grupo</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Número de grupos recomendados</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Número máximo de usuarios por grupo de servidores habilitados para la recogida de llamadas de grupo</p></td>
<td><p>25 000</p></td>
<td><p>3,000</p></td>
</tr>
<tr class="even">
<td><p>Tasa máxima de llamadas entrantes a los usuarios totales habilitados para la atención de llamadas grupales por grupo por minuto</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Tasa máxima de llamadas recuperadas por los usuarios con la atención de llamadas grupales por grupo por minuto</p></td>
<td><p>200</p></td>
<td><p>IVA</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Para los grupos de servidores front-end que tienen menos de ocho servidores front-end, calcule las métricas linealmente. Por ejemplo, si el grupo de servidores front-end tiene un servidor front-end, calcule la carga máxima como 1/8 de los valores que se muestran en la tabla.</P>
> <LI>
> <P>Puede aumentar o disminuir el número recomendado de usuarios por grupo y el número de grupos siempre que no supere el número máximo de usuarios por grupo de servidores. Por ejemplo, el servidor Standard Edition puede tener 120 grupos con 25 usuarios por grupo, ya que el número de usuarios habilitados para la atención de llamadas grupales está todavía dentro del modelo de usuario máximo (es decir, 120 grupos de 25 usuarios es 3.000 usuarios habilitados para la atención de llamadas grupales).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

