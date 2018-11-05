---
title: "Experiencia de grupo de respuesta durante errores del grupo de servidores"
TOCTitle: Experiencia de grupo de respuesta durante errores del grupo de servidores
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48275186
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Experiencia de grupo de respuesta durante errores del grupo de servidores en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En este apartado se describe con detalle cómo la actividad del grupo de respuesta se ve afectada en las siguientes etapas:

  - Se produce una interrupción en el grupo principal pero aún no se ha iniciado la conmutación por error.

  - El servicio se conmuta por error en el grupo de reserva.

  - El servicio se conmuta por recuperación en el grupo principal.

## Experiencia del usuario cuando se produce la interrupción

Cuando se produce una interrupción del grupo o del sitio, pero el administrador aún no ha iniciado la conmutación por error, la actividad del grupo de respuesta se administra tal como se describe en la tabla siguiente.


> [!NOTE]
> Durante la recuperación de desastres, las llamadas se comportan de manera diferente en función de si los grupos de respuesta del grupo principal se han importado al grupo de reserva durante la recuperación o no. En la tabla siguiente, las referencias a los grupos de respuesta importados indican que los grupos de respuesta del grupo principal se han importado al grupo de reserva durante el modo de recuperación de desastres.



### Se produce la interrupción

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de llamada o intervención de usuario</th>
<th>Durante la interrupción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas conectadas a un agente</p></td>
<td><ul>
<li><p>Las llamadas regulares permanecen conectadas.</p></li>
<li><p>Las llamadas anónimas se desconectarán.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Las llamadas en curso aún no se conectaron a un agente</p></td>
<td><p>Las llamadas se desconectarán.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas nuevas</p></td>
<td><ul>
<li><p>Las llamadas se desconectarán.</p></li>
<li><p>Si los grupos de respuesta se han importado, las llamadas se conectarán al grupo de reserva pero no se podrá acceder a los agentes hospedados en el grupo principal.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamadas de agentes en nombre de un grupo de respuesta</p></td>
<td><p>La característica se deshabilita durante esta etapa.</p></td>
</tr>
<tr class="odd">
<td><p>Inicio de sesión e información de los agentes</p></td>
<td><ul>
<li><p>Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes importados no se muestran en la consola de los agentes.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuración de grupos de respuesta</p></td>
<td><ul>
<li><p>Los grupos de respuesta que pertenecen al grupo principal pueden verse, en función de la disponibilidad de la base de datos de back-end del grupo principal, pero no pueden modificarse.</p></li>
<li><p>Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</p></li>
<li><p>Los grupos de respuesta importados no pueden verse con el Panel de control de Lync Server o el Herramienta de configuración de grupo de respuesta, pero pueden configurarse con cmdlets de Shell de administración de Lync Server.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Experiencia del usuario durante la conmutación por error

Cuando un administrador invoca la conmutación por error a un grupo de copia de seguridad, la actividad del grupo de respuesta se controla durante y después de la conmutación por error como se describe en la siguiente tabla. La primera columna describe el tipo de actividad que podría estar ocurriendo. La columna central describe cómo se controla cada actividad durante el breve tiempo que se tarda en conmutar por error al grupo de copia de seguridad. La última columna describe cómo se controla la actividad de la duración, después de finalizar el proceso de conmutación por error y el grupo de copia de seguridad se mantiene en el grupo principal.


> [!NOTE]
> Durante la recuperación de desastres, las llamadas se comportan de manera diferente en función de si los grupos de respuesta del grupo principal se han importado al grupo de reserva durante la recuperación o no. En la tabla siguiente, las referencias a los grupos de respuesta importados indican que los grupos de respuesta del grupo principal se han importado al grupo de reserva durante el modo de recuperación de desastres.



### Se ha iniciado la conmutación por error

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de llamada o intervención de usuario</th>
<th>Durante la conmutación por error</th>
<th>Después de que finalice la conmutación por error</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas conectadas a un agente</p></td>
<td><ul>
<li><p>Las llamadas regulares permanecen conectadas.</p></li>
<li><p>Las llamadas anónimas se desconectarán.</p></li>
</ul></td>
<td><ul>
<li><p>Las llamadas regulares permanecen conectadas.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas anónimas que han alcanzado el grupo de reserva permanecen conectadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Las llamadas en curso aún no se conectaron a un agente</p></td>
<td><p>Las llamadas se desconectarán.</p></td>
<td><ul>
<li><p>Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada en este estado.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas que han alcanzado el grupo de reserva permanecen conectadas.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Llamadas nuevas</p></td>
<td><ul>
<li><p>Las llamadas se desconectarán.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas se conectan al grupo de reserva, pero no se pueden alcanzar los agentes hospedados en el grupo principal</p></li>
</ul></td>
<td><ul>
<li><p>Si los grupos de respuesta no se importaron, las llamadas se desconectan.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas se conectan al grupo de reserva.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamadas de agentes en nombre de un grupo de respuesta</p></td>
<td><p>La característica se deshabilita durante esta etapa</p></td>
<td><ul>
<li><p>Si los grupos de respuesta no se han importado, la llamada fallará.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas se realizan con éxito.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Inicio de sesión e información de los agentes</p></td>
<td><ul>
<li><p>Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes importados se muestran en la consola de los agentes y estos pueden iniciar sesión.</p></li>
</ul></td>
<td><ul>
<li><p>Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes importados se muestran en la consola de los agentes y estos pueden iniciar sesión.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuración de grupos de respuesta</p></td>
<td><ul>
<li><p>Los grupos de respuesta que pertenecen al grupo principal pueden verse, en función de la disponibilidad de la base de datos de back-end del grupo principal, pero no pueden modificarse.</p></li>
<li><p>Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</p></li>
<li><p>Los grupos de respuesta importados no pueden verse con el Panel de control de Lync Server o el Herramienta de configuración de grupo de respuesta, pero pueden configurarse con cmdlets de Shell de administración de Lync Server.</p></li>
</ul></td>
<td><ul>
<li><p>Los grupos de respuesta del grupo principal se pueden visualizar, en función de la disponibilidad de la base de datos de back-end, pero no se pueden modificar.</p></li>
<li><p>Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</p></li>
<li><p>Los grupos de respuesta importados no pueden verse con el Panel de control de Lync Server o el Herramienta de configuración de grupo de respuesta, pero pueden configurarse con cmdlets de Shell de administración de Lync Server.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Experiencia del usuario durante la conmutación por recuperación

Cuando un administrador invoca la conmutación por recuperación al grupo principal, la actividad del grupo de respuesta se administra durante y después de la conmutación por recuperación tal como se describe en la tabla siguiente.


> [!NOTE]
> Durante la recuperación de desastres, las llamadas se comportan de manera diferente en función de si los grupos de respuesta del grupo principal se han importado al grupo de reserva durante la recuperación o no. En la tabla siguiente, las referencias a los grupos de respuesta importados indican que los grupos de respuesta del grupo principal se han importado al grupo de reserva durante el modo de recuperación de desastres.



### Administración de llamadas en la conmutación por recuperación

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de llamada o intervención de usuario</th>
<th>Durante la conmutación por recuperación</th>
<th>Después de que la conmutación por recuperación haya finalizado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas conectadas a un agente</p></td>
<td><ul>
<li><p>Las llamadas regulares permanecen conectadas.</p></li>
<li><p>Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada anónima en este estado.</p></li>
<li><p>Para los grupos de respuestas importados, las llamadas anónimas permanecen conectadas.</p></li>
</ul></td>
<td><ul>
<li><p>Las llamadas regulares permanecen conectadas.</p></li>
<li><p>Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada anónima en este estado.</p></li>
<li><p>Para los grupos de respuestas importados, las llamadas anónimas permanecen conectadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Las llamadas en curso aún no se conectaron a un agente</p></td>
<td><ul>
<li><p>Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada en este estado.</p></li>
<li><p>Para los grupos de respuestas importados, las llamadas se desconectarán.</p></li>
</ul></td>
<td><ul>
<li><p>Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada en este estado.</p></li>
<li><p>Para los grupos de respuestas importados, las llamadas se desconectarán.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Llamadas nuevas</p></td>
<td><p>Las llamadas se conectan al grupo principal, pero no se puede alcanzar a los agentes hospedados en el grupo principal.</p></td>
<td><p>Las llamadas se conectan al grupo principal</p></td>
</tr>
<tr class="even">
<td><p>Llamadas de agentes en nombre de un grupo de respuesta</p></td>
<td><p>La característica se deshabilita durante esta etapa.</p></td>
<td><p>Las llamadas se realizan con éxito.</p></td>
</tr>
<tr class="odd">
<td><p>Inicio de sesión e información de los agentes</p></td>
<td><ul>
<li><p>Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes importados se muestran en la consola de los agentes y estos pueden iniciar sesión.</p></li>
</ul></td>
<td><ul>
<li><p>Los grupos de agentes del grupo principal se pueden ver en la consola de los agentes y estos pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes importados no se muestran en la consola de los agentes.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuración de grupos de respuesta</p></td>
<td><ul>
<li><p>Los grupos de respuesta que pertenecen al grupo principal pueden verse, en función de la disponibilidad de la base de datos de back-end del grupo principal, pero no pueden modificarse.</p></li>
<li><p>Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</p></li>
<li><p>Los grupos de respuesta importados no pueden verse con el Panel de control de Lync Server o el Herramienta de configuración de grupo de respuesta, pero pueden configurarse con cmdlets de Shell de administración de Lync Server.</p></li>
</ul></td>
<td><ul>
<li><p>Los grupos de respuesta del grupo principal se pueden ver y modificar.</p></li>
<li><p>Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</p></li>
<li><p>Los grupos de respuesta importados no pueden verse con el Panel de control de Lync Server o el Herramienta de configuración de grupo de respuesta, pero pueden configurarse con cmdlets de Shell de administración de Lync Server.</p></li>
</ul></td>
</tr>
</tbody>
</table>

