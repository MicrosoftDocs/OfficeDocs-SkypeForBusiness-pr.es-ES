---
title: Planeamiento de capacidad de la respuesta de llamadas en grupo
TOCTitle: Planeamiento de capacidad de la respuesta de llamadas en grupo
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ984297(v=OCS.15)
ms:contentKeyID: 52061591
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planeamiento de capacidad de la respuesta de llamadas en grupo

 

_**Última modificación del tema:** 2015-03-09_

En la siguiente tabla se describe el modelo de usuario de la atención de llamadas grupales que puede usar como base para los requisitos de planeación de la capacidad.

> [!IMPORTANT]  
> La atención de llamadas grupales se basa en el Aplicación de estacionamiento de llamadas. Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debe poder administrar las cargas de trabajo de los servicios de Estacionamiento de llamadas, incluida la atención de llamadas grupales, en ambos grupos.



### Modelo de usuario de la atención de llamadas grupales

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
<td><p>Número recomendado de usuarios por grupo</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Número recomendado de grupos</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Número máximo de usuarios por grupo habilitados para la atención de llamadas grupales</p></td>
<td><p>25.000</p></td>
<td><p>3.000</p></td>
</tr>
<tr class="even">
<td><p>Tasa máxima de llamadas entrantes al total de usuarios habilitados para la atención de llamadas grupales por grupo, por minuto</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Tasa máxima de llamadas recuperadas por los usuarios con la atención de llamadas grupales por grupo, por minuto</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <UL>
> <LI>
> <P>Para los Grupos de servidores front-end con menos de ocho Servidores front-end, calcule las métricas de manera lineal. Por ejemplo, si su Grupo de servidores front-end tiene un Servidor front-end, calcule la carga máxima como un octavo de los valores que se muestran en la tabla.</P>
> <LI>
> <P>Puede aumentar o disminuir el número recomendado de usuarios por grupo y el número de grupos siempre y cuando no supere el número máximo de usuarios por grupo. Por ejemplo, su Servidor Standard Edition puede tener 120 grupos con 25 usuarios por grupo porque el número de usuarios habilitados para la atención de llamadas grupales aún se encuentra dentro del máximo del modelo de usuario (es decir, 120 grupos por 25 usuarios arroja un total de 3.000 usuarios habilitados para la atención de llamadas grupales).</P></LI></UL>


