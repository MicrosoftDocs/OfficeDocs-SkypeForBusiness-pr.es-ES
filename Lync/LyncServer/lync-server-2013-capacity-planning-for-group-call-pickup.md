---
title: 'Lync Server 2013: Planeación de capacidad para la recogida de llamadas grupales'
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
ms.openlocfilehash: 8d694b20d026d83b4cef37c713e38ab8066e22f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Planificación de la capacidad para la recopilación de llamadas grupales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-12_

<div id="sectionSection0" class="section">

En la siguiente tabla se describe el modelo de usuario de recogida de llamadas grupales que puede usar como base para los requisitos de planes de capacidad.

<div>


> [!IMPORTANT]  
> La recogida de llamadas grupales se basa en la aplicación de estacionamiento de llamadas. Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debería poder controlar las cargas de trabajo de los servicios de estacionamiento de llamadas, incluida la recogida de llamadas grupales, en ambos grupos.



</div>

### <a name="group-call-pickup-user-model"></a>Modelo de usuario de llamada grupal

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Métrica</th>
<th>Por grupo front-end (con 8 servidores frontales)</th>
<th>Por servidor Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cantidad recomendada de usuarios por grupo</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Cantidad recomendada de grupos</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad máxima de usuarios por grupo habilitados para la atención de llamadas grupales</p></td>
<td><p>25 000</p></td>
<td><p>3 000</p></td>
</tr>
<tr class="even">
<td><p>Tasa máxima de llamadas entrantes al total de usuarios habilitados para la atención de llamadas grupales por grupo, por minuto</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Tasa máxima de llamadas recuperadas por los usuarios con la atención de llamadas grupales por grupo, por minuto</p></td>
<td><p>200</p></td>
<td><p>veinticinco</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Para los grupos de servidores front-end que tienen menos de ocho servidores front-end, calcule las métricas linealmente. Por ejemplo, si el grupo de servidores front-end tiene un servidor front-end, calcule la carga máxima como 1/8 de los valores que se muestran en la tabla.</P>
> <LI>
> <P>Puedes aumentar o disminuir la cantidad recomendada de usuarios por grupo y la cantidad de grupos siempre y cuando no supere la cantidad máxima de usuarios por grupo. Por ejemplo, su servidor Standard Edition puede tener 120 grupos con 25 usuarios por grupo, porque la cantidad de usuarios habilitada para la recogida de llamadas grupales todavía está dentro del modelo de usuario máximo (es decir, 120 grupos de 25 usuarios es 3.000 usuarios habilitados para la recogida de llamadas grupales).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

