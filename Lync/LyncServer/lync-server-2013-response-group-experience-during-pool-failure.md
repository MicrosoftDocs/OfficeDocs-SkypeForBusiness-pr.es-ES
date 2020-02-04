---
title: 'Lync Server 2013: Experiencia de grupo de respuesta durante errores del grupo de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad00afac363642106019269e86111f61eaca504e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>Experiencia de grupo de respuesta durante errores del grupo de servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

En esta sección se describe detalladamente cómo afecta la actividad de grupos de respuesta en las siguientes etapas:

  - Se produce una interrupción en el grupo principal, pero aún no se ha iniciado la conmutación por error.

  - El servicio se conmuta por error al grupo de copias de seguridad.

  - El servicio no puede recuperarse en el grupo primario.

<div>

## <a name="user-experience-when-outage-occurs"></a>Experiencia de usuario cuando se produce una interrupción

Cuando se produce una interrupción en un grupo o sitio, pero el administrador aún no ha iniciado la conmutación por error, la actividad del grupo de respuesta se controla como se describe en la tabla siguiente.

<div>


> [!NOTE]  
> Durante la recuperación de desastres, las llamadas se comportan de forma diferente en función de si los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante la recuperación. En la tabla siguiente, las referencias a grupos de respuesta importados significan que los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante el modo de recuperación de desastres.



</div>

### <a name="outage-occurs"></a>Se produce una interrupción

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de acción de usuario o llamada</th>
<th>Durante la interrupción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas conectadas a un agente</p></td>
<td><ul>
<li><p>Las llamadas regulares permanecen conectadas.</p></li>
<li><p>Las llamadas anónimas se desconectan.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamadas en curso que aún no están conectadas a un agente</p></td>
<td><p>Las llamadas se desconectan.</p></td>
</tr>
<tr class="odd">
<td><p>Llamadas nuevas</p></td>
<td><ul>
<li><p>Las llamadas se desconectan.</p></li>
<li><p>Si se importaron grupos de respuesta, las llamadas se conectan al grupo de copia de seguridad, pero no se pueden alcanzar los agentes alojados en el bloque principal.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamadas del agente en nombre del grupo de respuesta</p></td>
<td><p>La característica está deshabilitada durante este paso.</p></td>
</tr>
<tr class="odd">
<td><p>Inicio de sesión del agente e información del agente</p></td>
<td><ul>
<li><p>Los grupos de agentes que pertenecen al repositorio principal pueden verse en la consola del agente, pero los agentes no pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes que pertenecen al grupo de copia de seguridad pueden verse en la consola del agente y los agentes pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes importados no se muestran en la consola del agente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuración del grupo de respuesta</p></td>
<td><ul>
<li><p>Los grupos de respuesta que pertenecen al grupo primario se pueden ver, en función de la disponibilidad de la base de datos back-end del grupo principal, pero no se pueden modificar.</p></li>
<li><p>Los grupos de respuesta que pertenecen al grupo de copias de seguridad se pueden ver y modificar.</p></li>
<li><p>Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>Experiencia del usuario durante la conmutación por error

Cuando un administrador invoca la conmutación por error a un grupo de copia de seguridad, la actividad del grupo de respuesta se controla durante y después de la conmutación por error, tal como se describe en la tabla siguiente. En la primera columna se describe el tipo de actividad que se puede llevar a cabo. La columna central describe cómo se administra cada actividad durante el breve tiempo que se tarda en conmutar por error al grupo de copias de seguridad. La última columna describe cómo se controla la actividad durante la duración, una vez completada la conmutación por error y en la que se encuentra el grupo de copia de seguridad para el grupo primario.

<div>


> [!NOTE]  
> Durante la recuperación de desastres, las llamadas se comportan de forma diferente en función de si los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante la recuperación. En la tabla siguiente, las referencias a grupos de respuesta importados significan que los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante el modo de recuperación de desastres.



</div>

### <a name="failover-is-initiated"></a>Se inicia la conmutación por error

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de acción de usuario o llamada</th>
<th>Durante la conmutación por error</th>
<th>Después de que se complete la conmutación por error</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas conectadas a un agente</p></td>
<td><ul>
<li><p>Las llamadas regulares permanecen conectadas.</p></li>
<li><p>Las llamadas anónimas se desconectan.</p></li>
</ul></td>
<td><ul>
<li><p>Las llamadas regulares permanecen conectadas.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas anónimas que hayan llegado al grupo de backup seguirán estando conectadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamadas en curso que aún no están conectadas a un agente</p></td>
<td><p>Las llamadas se desconectan.</p></td>
<td><ul>
<li><p>Si los grupos de respuesta no se importaron, no hay llamadas en este estado.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas que hayan llegado al grupo de copia de seguridad seguirán estando conectadas.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Llamadas nuevas</p></td>
<td><ul>
<li><p>Las llamadas se desconectan.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas se conectan al grupo de copia de seguridad, pero los agentes alojados en el grupo primario son inaccesibles.</p></li>
</ul></td>
<td><ul>
<li><p>Si los grupos de respuesta no se importaron, las llamadas se desconectarán.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas se conectan al grupo de copias de seguridad.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamadas del agente en nombre del grupo de respuesta</p></td>
<td><p>La característica está deshabilitada durante esta fase</p></td>
<td><ul>
<li><p>Si los grupos de respuesta no se importaron, no se pueden realizar llamadas.</p></li>
<li><p>Para grupos de respuesta importados, las llamadas se realizarán correctamente.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Inicio de sesión del agente e información del agente</p></td>
<td><ul>
<li><p>Los grupos de agentes que pertenecen al repositorio principal pueden verse en la consola del agente, pero los agentes no pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes que pertenecen al grupo de copia de seguridad pueden verse en la consola del agente y los agentes pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes importados se muestran en la consola del agente y los agentes pueden iniciar sesión.</p></li>
</ul></td>
<td><ul>
<li><p>Los grupos de agentes que pertenecen al repositorio principal pueden verse en la consola del agente, pero los agentes no pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes que pertenecen al grupo de copia de seguridad pueden verse en la consola del agente y los agentes pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes importados se muestran en la consola del agente y los agentes pueden iniciar sesión.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuración del grupo de respuesta</p></td>
<td><ul>
<li><p>Los grupos de respuesta que pertenecen al grupo primario se pueden ver, en función de la disponibilidad de la base de datos back-end del grupo principal, pero no se pueden modificar.</p></li>
<li><p>Los grupos de respuesta que pertenecen al grupo de copias de seguridad se pueden ver y modificar.</p></li>
<li><p>Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</p></li>
</ul></td>
<td><ul>
<li><p>Los grupos de respuesta que pertenecen al grupo primario se pueden ver, dependiendo de la disponibilidad de la base de datos back-end, pero no se pueden modificar.</p></li>
<li><p>Los grupos de respuesta que pertenecen al grupo de copias de seguridad se pueden ver y modificar.</p></li>
<li><p>Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>Experiencia de usuario durante la conmutación por recuperación

Cuando un administrador invoca la conmutación por recuperación al grupo principal, la actividad del grupo de respuesta se controla durante y después de la conmutación por recuperación, como se describe en la tabla siguiente.

<div>


> [!NOTE]  
> Durante la recuperación de desastres, las llamadas se comportan de forma diferente en función de si los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante la recuperación. En la tabla siguiente, las referencias a grupos de respuesta importados significan que los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante el modo de recuperación de desastres.



</div>

### <a name="call-handling-in-failback"></a>Control de llamadas en failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de acción de usuario o llamada</th>
<th>Durante la conmutación por recuperación</th>
<th>Tras completar la conmutación por recuperación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Llamadas conectadas a un agente</p></td>
<td><ul>
<li><p>Las llamadas regulares permanecen conectadas.</p></li>
<li><p>Si los grupos de respuesta no se importaron, no hay llamadas anónimas en este estado.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas anónimas permanecen conectadas.</p></li>
</ul></td>
<td><ul>
<li><p>Las llamadas regulares permanecen conectadas.</p></li>
<li><p>Si los grupos de respuesta no se importaron, no hay llamadas anónimas en este estado.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas anónimas permanecen conectadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Llamadas en curso que aún no están conectadas a un agente</p></td>
<td><ul>
<li><p>Si los grupos de respuesta no se importaron, no hay llamadas en este estado.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas se desconectarán.</p></li>
</ul></td>
<td><ul>
<li><p>Si los grupos de respuesta no se importaron, no hay llamadas en este estado.</p></li>
<li><p>Para los grupos de respuesta importados, las llamadas se desconectarán.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Llamadas nuevas</p></td>
<td><p>Las llamadas se conectan al grupo de servidores principal, pero los agentes alojados en el grupo primario no son accesibles.</p></td>
<td><p>Las llamadas se conectan al grupo primario.</p></td>
</tr>
<tr class="even">
<td><p>Llamadas del agente en nombre del grupo de respuesta</p></td>
<td><p>La característica está deshabilitada durante este paso.</p></td>
<td><p>Las llamadas se realizaron correctamente.</p></td>
</tr>
<tr class="odd">
<td><p>Inicio de sesión del agente e información del agente</p></td>
<td><ul>
<li><p>Los grupos de agentes que pertenecen al repositorio principal pueden verse en la consola del agente, pero los agentes no pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes que pertenecen al grupo de copia de seguridad pueden verse en la consola del agente y los agentes pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes importados se muestran en la consola del agente y los agentes pueden iniciar sesión.</p></li>
</ul></td>
<td><ul>
<li><p>Los grupos de agentes que pertenecen al repositorio principal pueden verse en la consola del agente y los agentes pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes que pertenecen al grupo de copia de seguridad pueden verse en la consola del agente y los agentes pueden iniciar sesión.</p></li>
<li><p>Los grupos de agentes importados no se muestran en la consola del agente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuración del grupo de respuesta</p></td>
<td><ul>
<li><p>Los grupos de respuesta que pertenecen al grupo primario se pueden ver, en función de la disponibilidad de la base de datos back-end del grupo principal, pero no se pueden modificar.</p></li>
<li><p>Los grupos de respuesta que pertenecen al grupo de copias de seguridad se pueden ver y modificar.</p></li>
<li><p>Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</p></li>
</ul></td>
<td><ul>
<li><p>Los grupos de respuesta que pertenecen al grupo principal se pueden ver y modificar.</p></li>
<li><p>Los grupos de respuesta que pertenecen al grupo de copias de seguridad se pueden ver y modificar.</p></li>
<li><p>Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

