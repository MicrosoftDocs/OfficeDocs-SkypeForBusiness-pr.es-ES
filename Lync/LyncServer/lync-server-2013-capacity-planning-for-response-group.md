---
title: 'Lync Server 2013: Planificar la capacidad para el grupo de respuesta'
TOCTitle: Planificar la capacidad para el grupo de respuesta
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48276175
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planificar la capacidad para el grupo de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En la siguiente tabla se describe el modelo de usuario de Grupo de respuesta que puede usar como base para los requisitos de planeación de la capacidad.


> [!NOTE]
> En los números de la tabla siguiente se presupone que usa archivos wave mono de 16 bits a 16 kHz (.wav) para todos los archivos de audio de grupo de respuesta. Si usa otros formatos de archivo, como Windows Media Audio (.wma), los números pueden variar.



> [!IMPORTANT]  
> Tenga en cuenta que, para planear la capacidad de recuperación ante desastres, cada grupo de servidores de un grupo formado en par debe poder administrar las cargas de trabajo para todos los grupos de respuesta en ambos grupos.



### Modelo de usuario de grupo de respuesta

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Métrica</th>
<th>Por grupo de servidores Enterprise Edition (con 8 servidores front-end)</th>
<th>Por servidor Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas entrantes por segundo</p></td>
<td><p>16</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Llamadas simultáneas conectadas a la respuesta interactiva de voz (IVR) o música en espera</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Sesiones anónimas simultáneas (sin mensajería instantánea)</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>Sesiones anónimas simultáneas (con mensajería instantánea)</p></td>
<td><p>64</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>Agentes activos (formal e informal).</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>Número de grupos de búsqueda</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>Número de grupos de IVR (uso del reconocimiento de voz)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>

