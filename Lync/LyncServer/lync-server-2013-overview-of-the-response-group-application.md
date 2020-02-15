---
title: 'Lync Server 2013: información general sobre la aplicación de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d63f13442588a84039fee6e1147a9c29e821e14a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Información general sobre la aplicación grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

Cuando el autor de la llamada llama a un grupo de respuesta, la llamada se enruta a un agente en función de un grupo de extensiones o de las respuestas que da el autor de la llamada a las preguntas de respuesta interactiva de voz (IVR). La aplicación grupo de respuesta utiliza métodos de enrutamiento de grupo de respuesta estándar para redirigir la llamada al siguiente agente disponible. Entre los métodos de enrutamiento de llamadas se incluye el enrutamiento en serie, el enrutamiento según agente libre por más tiempo, el enrutamiento en paralelo, el enrutamiento por round robin y el enrutamiento de operador (en el que se llama a todos los agentes al mismo tiempo para cada llamada entrante, sin importar su presencia actual). Si no hay ningún agente disponible, la llamada se mantiene en cola hasta que haya alguno. Mientras está en la cola, el autor de la llamada escucha música hasta que un agente disponible acepta la llamada. Si la cola está llena o si la llamada supera el tiempo de espera mientras está en la cola, el autor de la llamada oirá un mensaje y, a continuación, se desconectará la llamada o se transferirá a un destino diferente. Cuando un agente acepta la llamada, el autor de la llamada puede ver o no la identidad del agente, en función de cómo haya configurado el administrador el grupo de respuesta. Los agentes pueden ser formales, lo que significa que deberán iniciar sesión en el grupo para poder aceptar las llamadas enrutadas al grupo, o bien informales, lo que significa que no es necesario que inicien sesión y finalicen sesión en el grupo para aceptar llamadas.

<div>


> [!NOTE]  
> Solo los usuarios locales pueden ser agentes. Si un agente deja de ser local para estar en línea, las llamadas al grupo de respuesta no se enrutarán a dicho agente.



</div>

<div>


> [!NOTE]  
> La aplicación de grupo de respuesta usa un servicio interno, denominado realización de coincidencia, para poner en cola las llamadas y buscar agentes disponibles. Cada equipo que ejecuta la aplicación de grupo de respuesta ejecuta el servicio de coincidencia, pero solo se activa un servicio de coincidencia por grupo de Lync Server a la vez que los demás son pasivos. Si el servicio de contactos activo deja de estar disponible durante una interrupción no planificada, se activará uno de los servicios de contactos pasivos. La aplicación de grupo de respuesta es la mejor opción para asegurarse de que el enrutamiento de llamadas y la puesta en cola continúen sin interrupciones. No obstante, cuando se produce la transición del servicio de contactos, todas las llamadas que se están transfiriendo en ese momento se pierden. Por ejemplo, si la transición se debe al servidor front-end en funcionamiento, también se perderán las llamadas que el servicio de coincidencia activa en ese servidor front-end esté controlando en ese momento.



</div>

En Lync Server 2013, hay disponibles dos roles de administración para administrar los grupos de respuesta: administrador del grupo de respuesta y administrador del grupo de respuesta. Los administradores de grupos de respuesta pueden administrar cualquier aspecto de cualquier grupo de respuesta. Los administradores del grupo de respuesta solo pueden administrar determinados aspectos y solo para los grupos de respuesta de los que son propietarios. El nuevo rol de administrador puede ayudar a reducir los costos de administración, ya que puede delegar responsabilidades limitadas para grupos de respuesta específicos a cualquier usuario que esté habilitado para telefonía IP empresarial.

Para acomodar el nuevo rol de administrador, la aplicación de grupo de respuesta de Lync Server 2013 introduce un **tipo de flujo de trabajo** administrado o no administrado. En la tabla siguiente se describen los grupos de respuesta administrados y no administrados.

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
<td><p>No administrados</p></td>
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
<li><p>Los administradores del grupo de respuesta no pueden ver ni modificar los grupos de respuesta que no se les haya asignado explícitamente.</p></li>
<li><p>Los administradores del grupo de respuesta solo pueden configurar algunas opciones para los grupos de respuesta que se les haya asignado explícitamente.</p></li>
<li><p>Los grupos de respuesta administrados no pueden compartir grupos de agentes ni colas con otros grupos de respuesta, ya sean administrados o no administrados.</p></li>
</ul></td>
</tr>
</tbody>
</table>


En la tabla siguiente se describen las acciones que los administradores del grupo de respuesta pueden y no pueden realizar para los grupos de respuesta que tienen asignados.

### <a name="response-group-manager-capabilities"></a>Capacidad del director de grupo de respuesta

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
<th>Puedan</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Gelifica</p></li>
<li><p>Mensajes de bienvenida</p></li>
<li><p>Nombre del grupo de respuesta</p></li>
<li><p>Descripción</p></li>
<li><p>Número para mostrar</p></li>
<li><p>Horario comercial</p></li>
<li><p>Música en espera</p></li>
<li><p>Estado (activo/inactivo)</p></li>
<li><p>Flujos de trabajo de grupo de extensiones o flujos de trabajo de respuesta interactiva de voz (IVR)</p></li>
</ul></td>
<td><ul>
<li><p>Grupos de agentes</p></li>
<li><p>Colas</p></li>
<li><p>Conjuntos de vacaciones</p></li>
</ul></td>
<td><ul>
<li><p>Crear o eliminar ningún tipo de flujo de trabajo</p></li>
<li><p>Modificar la configuración principal de grupos de respuesta, como el <strong>URI de SIP</strong>, el <strong>número de teléfono</strong> o el <strong>tipo de flujo de trabajo</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Los administradores del grupo de respuesta pueden usar las siguientes herramientas para administrar sus grupos de respuesta designados.

  - Panel de Control de Lync Server
    
    <div>
    

    > [!NOTE]  
    > Los administradores del grupo de respuesta solo pueden administrar la configuración del grupo de respuesta con esta herramienta. Otras opciones de configuración de Lync Server no están disponibles para los administradores.

    
    </div>

  - Herramienta de configuración de grupo de respuesta

  - Shell de administración de Communications Server

El grupo de respuesta se ajusta bien a los entornos departamentales o de grupo de trabajo (para obtener más información, consulte [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) y puede implementarse en instalaciones de telefonía completamente nuevas. Admite llamadas entrantes de la implementación de Enterprise Voice y de la red de operador local. Los agentes pueden usar Lync 2013, Lync 2010, el operador Lync 2010 o Lync Phone Edition para realizar las llamadas enrutadas a ellos.

La aplicación de grupo de respuesta es un componente de la telefonía IP empresarial. Al implementar la telefonía IP empresarial, la aplicación de grupo de respuesta se instala y activa automáticamente.

</div>

<span> </span>

</div>

</div>

</div>

