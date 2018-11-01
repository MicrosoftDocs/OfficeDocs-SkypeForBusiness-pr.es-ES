---
title: 'Lync Server 2013: Información general sobre la aplicación del grupo de respuesta'
TOCTitle: Información general sobre la aplicación del grupo de respuesta
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48275623
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general sobre la aplicación del grupo de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cuando el autor de la llamada llama a un grupo de respuesta, la llamada se enruta a un agente en función de un grupo de extensiones o de las respuestas que da el autor de la llamada a las preguntas de respuesta interactiva de voz (IVR). La Aplicación de grupo de respuesta usa métodos de enrutamiento de grupo de respuesta estándar para enrutar la llamada al siguiente agente disponible. Entre los métodos de enrutamiento de llamadas se incluye el enrutamiento en serie, el enrutamiento según agente libre por más tiempo, el enrutamiento en paralelo, el enrutamiento por round robin y el enrutamiento de operador (en el que se llama a todos los agentes al mismo tiempo para cada llamada entrante, sin importar su presencia actual). Si no hay ningún agente disponible, la llamada se mantiene en cola hasta que haya alguno. Mientras está en la cola, el autor de la llamada escucha música hasta que un agente disponible acepta la llamada. Si la cola está llena o si la llamada supera el tiempo de espera mientras está en la cola, el autor de la llamada oirá un mensaje y, a continuación, se desconectará la llamada o se transferirá a un destino diferente. Cuando un agente acepta la llamada, el autor de la llamada puede ver o no la identidad del agente, en función de cómo haya configurado el administrador el grupo de respuesta. Los agentes pueden ser formales, lo que significa que deberán iniciar sesión en el grupo para poder aceptar las llamadas enrutadas al grupo, o bien informales, lo que significa que no es necesario que inicien sesión y finalicen sesión en el grupo para aceptar llamadas.


> [!NOTE]
> Solo los usuarios locales pueden ser agentes. Si un agente local pasa a estar en línea, las llamadas de la Grupo de respuesta no se enrutarán a dicho agente.




> [!NOTE]
> La Aplicación de grupo de respuesta usa un servicio interno, denominado servicio de contactos, para poner en cola las llamadas y encontrar agentes disponibles. Todos los equipos que ejecutan la Aplicación de grupo de respuesta ejecutan el servicio de contactos, pero solo se activa un servicio de contactos por grupo de servidores de Lync Server a la vez; los demás son pasivos. Si el servicio de contactos activo deja de estar disponible durante una interrupción no planificada, se activará uno de los servicios de contactos pasivos. La Aplicación de grupo de respuesta se encarga de asegurar que el enrutamiento de llamadas y la puesta en cola continúen sin interrupciones. No obstante, cuando se produce la transición del servicio de contactos, todas las llamadas que se están transfiriendo en ese momento se pierden. Por ejemplo, si la transición se debe a que el Servidor front-end deja de funcionar, también se pierden las llamadas que el servicio de contactos activo está administrando en ese Servidor front-end.



En Lync Server 2013, para administrar grupos de respuestas hay disponibles dos roles de administración: Director de Grupo de respuesta y Administrador de Grupo de respuesta. Los administradores de Grupo de respuesta pueden administrar cualquier aspecto de los grupos de respuesta. Los directores de Grupo de respuesta pueden solo pueden administrar unos aspectos determinados en los grupos de respuesta de los que son propietarios. Con el nuevo rol Director se pretende reducir los costos de administración, ya que con él se pueden delegar responsabilidades limitadas de grupos de respuesta a cualquier usuario habilitado para la Telefonía IP empresarial.

Para integrar el nuevo rol Director, la Aplicación de grupo de respuesta de Lync Server 2013 introduce los **tipos de flujo de trabajo** Administrado y No administrado. En la tabla siguiente se describen los grupos de respuesta administrados y no administrados.

### Grupos de respuesta administrados y no administrados

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
<li><p>Los grupos de respuesta no administrados no tienen ningún director asignado. Solo el administrador de Grupo de respuesta puede configurar estos grupos de respuesta.</p></li>
<li><p>Varios grupos de respuesta no administrados pueden compartir un grupo de agentes o una cola.</p></li>
<li><p>Cuando se migran grupos de respuesta desde una versión anterior de Lync Server 2013, los grupos de respuesta se definen como No administrados.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Administrado</p></td>
<td><ul>
<li><p>Los administradores de Grupo de respuesta pueden configurar cualquier aspecto de los grupos de respuesta administrados.</p></li>
<li><p>Los directores de Grupo de respuesta no pueden ver ni modificar los grupos de respuesta que no se les haya asignado explícitamente.</p></li>
<li><p>Los directores de Grupo de respuesta pueden configurar solo algunas opciones de los grupos de respuesta que se les haya asignado explícitamente.</p></li>
<li><p>Los grupos de respuesta administrados no pueden compartir grupos de agentes ni colas con otros grupos de respuesta, ya sean administrados o no administrados.</p></li>
</ul></td>
</tr>
</tbody>
</table>


En la tabla siguiente se describen las acciones que los directores de Grupo de respuesta pueden y no pueden realizar en los grupos de respuesta que tienen asignados.

### Capacidad del director de grupo de respuesta

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
<li><p>Nombre del Grupo de respuesta</p></li>
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
<li><p>Modificar la configuración principal de grupos de respuesta, como el <strong>URI de SIP</strong> , el <strong>número de teléfono</strong> o el <strong>tipo de flujo de trabajo</strong> .</p></li>
</ul></td>
</tr>
</tbody>
</table>


Los directores de Grupo de respuesta pueden administrar los grupos de respuesta que tienen asignados con estas herramientas:

  - Panel de control de Lync Server
    

    > [!NOTE]
    > Los directores de Grupo de respuesta solo pueden administrar la configuración de Grupo de respuesta con esta herramienta. Los demás ajustes de Lync Server no están disponibles para los directores.



  - Herramienta de configuración de grupo de respuesta

  - Shell de administración de Lync Server

El Grupo de respuesta se escala sin problemas a entornos departamentales o de grupo de trabajo (para más información, vea [Planificar la capacidad para el grupo de respuesta en Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) y puede implementarse en instalaciones telefónicas totalmente nuevas. Admite llamadas entrantes recibidas de la implementación de la Telefonía IP empresarial y de la red del operador local. Los agentes pueden usar Lync 2013, Lync 2010, Operador de Lync 2010 o Lync Phone Edition para atender las llamadas que se les enrute.

La Aplicación de grupo de respuesta es un componente de la Telefonía IP empresarial. Al implementar la Telefonía IP empresarial, la Aplicación de grupo de respuesta se instalará y activará de forma automática.

