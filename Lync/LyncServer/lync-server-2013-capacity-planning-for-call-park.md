---
title: 'Lync Server 2013: Planificar la capacidad para el estacionamiento de llamadas'
TOCTitle: Planificar la capacidad para el estacionamiento de llamadas
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48275713
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planificar la capacidad para el estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En la siguiente tabla se describe el modelo de usuario de Estacionamiento de llamadas que puede usar como base para los requisitos de planeación de la capacidad.

> [!IMPORTANT]  
> Tenga en cuenta que para la planeación de la capacidad de recuperación ante desastres, cada grupo de servidores debe poder administrar las cargas de trabajo para los servicios de Estacionamiento de llamadas en ambos grupos.



### Modelo de usuario de estacionamiento de llamadas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Métrica</th>
<th>Por Grupo de servidores front-end (con 8 servidores front-end)</th>
<th>Por Servidor Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tasa de estacionamiento</p></td>
<td><p>8 por minuto</p></td>
<td><p>1 por minuto</p></td>
</tr>
<tr class="even">
<td><p>Tasa de recuperación de llamadas estacionadas</p></td>
<td><p>8 por minuto</p></td>
<td><p>1 por minuto</p></td>
</tr>
<tr class="odd">
<td><p>Promedio de duración del estacionamiento</p></td>
<td><p>60 segundos</p></td>
<td><p>60 segundos</p></td>
</tr>
</tbody>
</table>

