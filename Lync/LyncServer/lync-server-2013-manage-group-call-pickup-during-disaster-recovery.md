---
title: Administrar la respuesta de llamadas en grupo durante la recuperación ante desastres
TOCTitle: Administrar la respuesta de llamadas en grupo durante la recuperación ante desastres
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945618(v=OCS.15)
ms:contentKeyID: 52061625
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar la respuesta de llamadas en grupo durante la recuperación ante desastres

 

_**Última modificación del tema:** 2015-03-09_

Cuando un Grupo de servidores front-end deja de estar disponible debido a un incidente no planeado, se realiza la conmutación por error del servicio en el grupo de copia de seguridad. Durante la conmutación por error en el grupo de servidores de copia de seguridad, los usuarios se redirigen al grupo de servidores de copia de seguridad y están en modo de resistencia. Mientras se encuentran en modo de resistencia, los usuarios no pueden atender las llamadas de otros usuarios. Una vez completada la conmutación por error, pueden volver a usar la atención de llamadas grupales como de costumbre.

Durante la conmutación por recuperación en el grupo principal, los usuarios se redirigen al grupo principal y están en modo de resistencia. La funcionalidad de atención de llamadas grupales no está disponible hasta que los usuarios salen del modo de resistencia.

En esta sección se abordan algunas consideraciones sobre la atención de llamadas grupales durante la recuperación ante desastres y se describe la experiencia del usuario.

## Consideraciones sobre la atención de llamadas grupales durante la recuperación ante desastres

Durante la recuperación ante desastres, los usuarios que se han redirigido al grupo de copia de seguridad como parte del proceso de conmutación por error usan el Aplicación de estacionamiento de llamadas que se ejecuta en este grupo para los números del grupo de atención de llamadas. En consecuencia, la compatibilidad con la atención de llamadas grupales durante la recuperación ante desastres requiere que el Aplicación de estacionamiento de llamadas esté implementado y habilitado tanto en el grupo principal como en el de copia de seguridad.

Los intervalos de números de atención de llamadas grupales de la tabla de órbitas de estacionamiento de llamadas deben redirigirse al grupo de copia de seguridad una vez completado el proceso de conmutación por error en el grupo de copia de seguridad. Los intervalos de números deben redirigirse de vuelta al grupo principal una vez completado el proceso de conmutación por recuperación en el grupo principal. Para redirigir los intervalos de atención de llamadas grupales, use el cmdlet **Set-CsCallParkOrbit**.

Si implementa un grupo nuevo con un nombre de dominio completo (FQDN) diferente para sustituir al principal, tendrá que volver a asignar todos los intervalos de números de atención de llamadas grupales asociados con el grupo principal al FQDN del grupo nuevo. Para ello, puede usar el cmdlet **Set-CsCallParkOrbit**. Para obtener detalles sobre el cmdlet **Set-CsCallParkOrbit**, consulte [Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit).

## Experiencia de atención de llamadas grupales durante un error en el grupo

La tabla siguiente resume la experiencia de la atención de llamadas grupales a través de las fases de la recuperación ante desastres.

### Experiencia del usuario durante la recuperación ante desastres

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Estado de la llamada</th>
<th>Conmutación por error en el grupo de copia de seguridad</th>
<th>Conmutación por recuperación en el grupo principal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas nuevas</p></td>
<td><p><strong>Durante el proceso de conmutación por error:</strong></p>
<ul>
<li><p>La atención de llamadas grupales no está disponible para los usuarios en modo de resistencia</p></li>
</ul>
<p><strong>Una vez completada la conmutación por error:</strong></p>
<ul>
<li><p>La atención de llamadas grupales está disponible cuando los usuarios salen del modo de resistencia y los intervalos de números de atención de llamadas grupales de redirigen al grupo de copia de seguridad</p></li>
</ul></td>
<td><p><strong>Durante el proceso de conmutación por recuperación:</strong></p>
<ul>
<li><p>La atención de llamadas grupales no está disponible para los usuarios en modo de resistencia</p></li>
</ul>
<p><strong>Una vez completada la conmutación por recuperación:</strong></p>
<ul>
<li><p>La atención de llamadas grupales está disponible cuando los usuarios salen del modo de resistencia y los intervalos de números de atención de llamadas grupales de redirigen de vuelta al grupo principal</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamadas en la cola de atención de llamadas grupales</p></td>
<td><p><strong>Durante el proceso de conmutación por error:</strong></p>
<ul>
<li><p>Las llamadas en cola no se pueden responder mediante la atención de llamadas grupales.</p></li>
</ul>
<p><strong>Una vez completada la conmutación por error:</strong></p>
<ul>
<li><p>No hay llamadas en este estado</p></li>
</ul></td>
<td><p><strong>Durante el proceso de conmutación por recuperación:</strong></p>
<ul>
<li><p>Las llamadas en cola no se pueden responder mediante la atención de llamadas grupales.</p></li>
</ul>
<p><strong>Una vez completada la conmutación por recuperación:</strong></p>
<ul>
<li><p>Las llamadas en cola no se pueden responder mediante la atención de llamadas grupales.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Llamada establecida</p></td>
<td><p><strong>Durante el proceso de conmutación por error:</strong></p>
<ul>
<li><p>Las llamadas siguen conectadas</p></li>
</ul>
<p><strong>Una vez completada la conmutación por error:</strong></p>
<ul>
<li><p>Las llamadas siguen conectadas</p></li>
</ul></td>
<td><p><strong>Durante el proceso de conmutación por recuperación:</strong></p>
<ul>
<li><p>Las llamadas siguen conectadas</p></li>
</ul>
<p><strong>Una vez completada la conmutación por recuperación:</strong></p>
<ul>
<li><p>Las llamadas siguen conectadas</p></li>
</ul></td>
</tr>
</tbody>
</table>

