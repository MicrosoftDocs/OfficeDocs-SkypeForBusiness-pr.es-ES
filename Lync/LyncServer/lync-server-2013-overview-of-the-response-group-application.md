---
title: 'Lync Server 2013: información general sobre la aplicación de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b523a05509b0043effb8cb2b761d7ee06fd36751
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Información general de la aplicación de grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

Cuando el autor de una llamada llama a un grupo de respuesta, la llamada se redirige a un agente de acuerdo con un grupo de extensiones o las respuestas del autor de la llamada frente a las preguntas de la respuesta interactiva de voz (IVR). La aplicación de grupo de respuesta usa métodos de enrutamiento de grupo de respuesta estándar para dirigir la llamada al siguiente agente disponible. Los métodos de enrutamiento de llamadas incluyen el enrutamiento en serie, más tiempo de inactividad, paralelo, Round Robin y operador (es decir, se llama a todos los agentes al mismo tiempo para todas las llamadas entrantes, independientemente de su presencia actual). Si no hay ningún agente disponible, la llamada se mantiene en una cola hasta que haya alguno. Mientras se encuentra en la cola, el autor de la llamada escucha música hasta que un agente disponible acepte la llamada. Si la cola está llena o la llamada supera el tiempo de espera mientras está en la cola, es posible que la persona que llama oiga un mensaje y, después, se desconecte o se transfiera a un destino diferente. Cuando un agente acepta la llamada, el autor de la llamada puede ver o no la identidad del agente, en función de cómo haya configurado el administrador el grupo de respuesta. Los agentes pueden ser formales, lo que significa que necesitan iniciar sesión en el grupo para poder aceptar las llamadas redirigidas al grupo, o bien informales, lo que significa que no es necesario que inicien sesión y finalicen sesión en el grupo para aceptar llamadas.

<div>


> [!NOTE]  
> Solo los usuarios locales pueden ser agentes. Si un agente se mueve de local a conectado, las llamadas a grupos de respuesta no se dirigirán a ese agente.



</div>

<div>


> [!NOTE]  
> La aplicación de grupo de respuesta usa un servicio interno, denominado creación de coincidencias, para poner en cola las llamadas y buscar agentes disponibles. Cada equipo que ejecuta la aplicación de grupo de respuesta ejecuta la función coincidir con el servicio, pero solo se activa una coincidencia con el servicio por grupo de servidores de Lync. Si el servicio de contactos activo deja de estar disponible durante una interrupción no planificada, se activará uno de los servicios de contactos pasivos. La aplicación de grupo de respuesta hace todo lo posible para asegurarse de que el enrutamiento de llamadas y la cola no se interrumpan. Pero, cuando se produce la transición del servicio de contactos, todas las llamadas que se están transfiriendo en ese momento se pierden. Por ejemplo, si la transición se debe a que el servidor de aplicaciones para el usuario se baja, también se perderán las llamadas que el servicio de coincidencia activo en ese servidor de Front-End está administrando actualmente.



</div>

En Lync Server 2013, hay dos roles de administración disponibles para administrar grupos de respuesta: administrador de grupos de respuesta y administrador de grupos de respuesta. Los administradores de grupos de respuesta pueden administrar cualquier aspecto de cualquier grupo de respuesta. Los administradores de grupos de respuesta solo pueden administrar determinados aspectos, y solo para los grupos de respuesta de los que son propietarios. La nueva función de administrador puede ayudar a reducir los costos de administración, ya que puede delegar responsabilidades limitadas para grupos de respuesta específicos a cualquier usuario que tenga habilitada la telefonía IP empresarial.

Para dar cabida a la nueva función de administrador, la aplicación de grupo de respuesta de Lync Server 2013 introduce un **tipo de flujo de trabajo** administrado o no administrado. En la tabla siguiente se describen los grupos de respuesta administrados y no administrados.

### <a name="managed-and-unmanaged-response-groups"></a>Grupos de respuesta administrados y no administrados

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de grupo de respuesta</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>No administrado</p></td>
<td><ul>
<li><p>Los grupos de respuesta no administrados no tienen ningún director asignado. Solo el administrador del grupo de respuesta puede configurar estos grupos de respuesta.</p></li>
<li><p>Varios grupos de respuesta no administrados pueden compartir un grupo de agentes o una cola.</p></li>
<li><p>Al migrar grupos de respuesta de una versión anterior a Lync Server 2013, el tipo se establece en no administrado.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Administrado</p></td>
<td><ul>
<li><p>Los administradores de grupos de respuesta pueden configurar cualquier aspecto de los grupos de respuesta administrados.</p></li>
<li><p>Los administradores de grupos de respuesta no pueden ver ni modificar grupos de respuesta que no estén asignados de forma explícita.</p></li>
<li><p>Los administradores de grupos de respuesta solo pueden configurar algunos valores para los grupos de respuesta que se les hayan asignado explícitamente.</p></li>
<li><p>Los grupos de respuesta administrados no pueden compartir grupos de agentes ni colas con otros grupos de respuesta, ya sean administrados o no administrados.</p></li>
</ul></td>
</tr>
</tbody>
</table>


En la siguiente tabla se describen las acciones que los administradores de grupos de respuesta pueden o no pueden realizar para los grupos de respuesta que tengan asignados.

### <a name="response-group-manager-capabilities"></a>Capacidades del director del grupo de respuesta

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Puede configurar:</th>
<th>Puede crear, eliminar o configurar:</th>
<th>No puede:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Agentes</p></li>
<li><p>Mensajes de bienvenida</p></li>
<li><p>Nombre del grupo de respuesta</p></li>
<li><p>Descripción</p></li>
<li><p>Número para mostrar</p></li>
<li><p>Horario comercial</p></li>
<li><p>Música en espera</p></li>
<li><p>Estado (activo/inactivo)</p></li>
<li><p>Flujos de trabajo del grupo de extensiones o flujos de trabajo de la respuesta interactiva de voz (IVR)</p></li>
</ul></td>
<td><ul>
<li><p>Grupos de agentes</p></li>
<li><p>Colas</p></li>
<li><p>Conjuntos de vacaciones</p></li>
</ul></td>
<td><ul>
<li><p>Crear o eliminar ningún tipo de flujo de trabajo</p></li>
<li><p>Modificar la configuración principal de los grupos de respuesta, como el <strong>URI de SIP</strong>, el <strong>número de teléfono</strong> o el <strong>tipo de flujo de trabajo</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Los administradores de grupos de respuesta pueden usar las siguientes herramientas para administrar los grupos de respuesta designados.

  - Panel de control de Lync Server
    
    <div>
    

    > [!NOTE]  
    > Los administradores de grupos de respuesta solo pueden administrar la configuración del grupo de respuesta con esta herramienta. Otras opciones de configuración de Lync Server no están disponibles para los administradores.

    
    </div>

  - Herramienta de configuración de grupo de respuesta

  - Shell de administración de Communications Server

El grupo de respuesta se adapta bien a entornos departamentales o de grupo de trabajo (para obtener información detallada, consulte [planear la capacidad de un grupo de respuesta en Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) y puede implementarse en instalaciones de telefonía completamente nuevas. Es compatible con las llamadas entrantes desde la implementación de telefonía IP empresarial y desde la red del operador local. Los agentes pueden usar Lync 2013, Lync 2010, operador de Lync 2010 o Lync Phone Edition para tomar las llamadas dirigidas a ellos.

La aplicación de grupo de respuesta es un componente de telefonía IP empresarial. Al implementar la telefonía IP empresarial, la aplicación de grupo de respuesta se instala y activa automáticamente.

</div>

<span> </span>

</div>

</div>

</div>

