---
title: "Experiencia de estacionamiento de llamadas durante un error del grupo de servidores"
TOCTitle: Experiencia de estacionamiento de llamadas durante un error del grupo de servidores
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48277183
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Experiencia de estacionamiento de llamadas durante un error del grupo de servidores en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cuando un Grupo de servidores front-end deja de estar disponible debido a un incidente no planeado, las llamadas que se han estacionado pero aún no se han recuperado se desconectan. Durante la conmutación por error a un grupo de servidores de copia de seguridad, los usuarios son redirigidos al grupo de servidores de copia de seguridad y están en modo de resistencia. En el modo de resistencia, los usuarios no pueden estacionar llamadas, pero pueden realizar llamadas en espera y transferirlas. Cuando finaliza la conmutación por error, las llamadas se pueden volver a estacionar y recuperar como de costumbre. Durante la conmutación por recuperación, los usuarios no pueden estacionar llamadas hasta que estén fuera del modo de resistencia.

Durante la recuperación ante desastres, los usuarios que han sido redirigidos al grupo de servidores de copia de seguridad como parte del proceso de recuperación por error usan la aplicación Aplicación de estacionamiento de llamadas que está implementada en el grupo de servidores de copia de seguridad. Por lo tanto, los usuarios que son redirigidos al grupo de servidores de copia de seguridad usan los parámetros de estacionamiento de llamadas que están configurados para la aplicación Aplicación de estacionamiento de llamadas en el grupo de servidores de copia de seguridad.

La tabla siguiente resume la experiencia del Estacionamiento de llamadas a través de las fases de la recuperación ante desastres.

### Experiencia del usuario durante la recuperación ante desastres

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Estado de la llamada</th>
<th>Cuando se produce la interrupción</th>
<th>Durante la conmutación por error</th>
<th>Durante la conmutación por recuperación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamada no estacionada aún</p></td>
<td><p>La llamada permanece conectada pero no se puede estacionar.</p></td>
<td><ul>
<li><p>Durante la conmutación por error, la llamada no se puede estacionar mientras los usuarios están en modo de resistencia, pero se puede poner en espera y transferirse.</p></li>
<li><p>Cuando se completa la conmutación por error, la llamada se puede estacionar y recuperar.</p></li>
</ul></td>
<td><ul>
<li><p>Durante la conmutación por recuperación, la llamada no se puede estacionar mientras los usuarios están en modo de resistencia, pero se puede poner en espera y transferirse</p></li>
<li><p>Cuando se completa la conmutación por recuperación, la llamada se puede estacionar y recuperar.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamada estacionada pero no recuperada aún</p></td>
<td><p>La llamada está desconectada.</p></td>
<td><p>No hay llamadas en este estado.</p></td>
<td><p>La llamada permanece estacionada.</p></td>
</tr>
<tr class="odd">
<td><p>Llamada estacionada ya recuperada</p></td>
<td><p>La llamada permanece conectada.</p></td>
<td><p>La llamada permanece conectada.</p></td>
<td><p>La llamada permanece conectada.</p></td>
</tr>
</tbody>
</table>

