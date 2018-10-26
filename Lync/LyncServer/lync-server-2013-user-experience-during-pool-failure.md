---
title: 'Lync Server 2013: Experiencia durante conmutación por error del grupo de servidores'
TOCTitle: Experiencia del usuario durante la conmutación por error del grupo de servidores
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48276390
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Experiencia del usuario durante la conmutación por error del grupo de servidores en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Si se produce un error en un grupo de servidores y se invoca la conmutación por error, todos los usuarios del grupo de servidores afectado están obligados a cerrar la sesión y luego iniciar sesión en el grupo de servidores de reserva. Durante un período breve los usuarios que inicien sesión en el grupo de servidores de reserva pueden estar en modo de resistencia. En el modo de resistencia, los usuarios no pueden realizar tareas que provoquen un cambio permanente en Lync Server, como agregar un contacto. Una vez finalizada la conmutación por error, todos los usuarios pueden obtener todos los servicios desde el grupo de servidores de reserva.

Se interrumpen las sesiones que tenga un usuario cuando se produce un error en el grupo de servidores, y el usuario debe volver a establecer esas sesiones después de la conmutación por error para continuar.

No se vuelven a ubicar los usuarios durante la conmutación por error o conmutación por recuperación. Los usuarios que están hospedados en el grupo de servidores donde se produce un error se hospedarán temporalmente en el grupo de servidores de reserva. Cuando se restaura el grupo de servidores principal, esos usuarios vuelven a hospedarse en su grupo de servidores original.

Tenga en cuenta que, en Lync 2013, no se replica la base de datos del servidor de información de ubicación en el grupo de servidores de reserva. Como práctica recomendada, el administrador debe copiar esta base de datos periódicamente y usar la última copia de seguridad para restaurar la base de datos en el grupo de servidores de reserva tras la conmutación por error.

## Experiencia del usuario durante la conmutación por error

Cuando un usuario está en un grupo donde se produce un error, se cierra la sesión del usuario. Se finaliza cualquier sesión punto a punto en la que participe el usuario, como las conferencias organizadas por ese usuario. El usuario no podrá volver a iniciar sesión hasta que caduque el temporizador de resistencia del registrador o el administrador inicie los procedimientos de conmutación por error, lo que ocurra primero. Cuando el usuario vuelve a iniciar sesión, iniciará la sesión en el grupo de servidores de reserva. Si inicia sesión antes de que finalice la conmutación por error, estará en modo de resistencia hasta que finalice la conmutación por error. Solamente entonces el usuario podrá establecer nuevas sesiones o restablecer las sesiones anteriores.

## Experiencia del usuario durante la conmutación por recuperación

La conmutación por recuperación de un grupo puede ocurrir cuando un usuario afectado ha iniciado sesión en el grupo de servidores de reserva y el usuario permanece conectado y sigue trabajando durante la conmutación por recuperación. Tenga en cuenta que el proceso de conmutación por recuperación tarda varios minutos en completarse. Como referencia, se espera que tarde 60 minutos como máximo para un grupo de servidores con 20.000 usuarios.

Las siguientes tablas muestran más detalles sobre cómo un usuario con un cliente de Lync 2013 o un cliente de Microsoft Lync 2010 se ve afectado durante y después de la conmutación por recuperación, y también cómo los usuarios de otros grupos ven e interactúan con un usuario de un grupo en el que se realiza una conmutación por recuperación. Los usuarios con clientes de Microsoft Office Communicator 2007 R2 no podrán iniciar sesión hasta que la conmutación por recuperación del grupo de servidores front-end haya finalizado.

El término *usuario afectado* hace referencia a cualquier usuario que sufrió una conmutación por error en el grupo principal y esté hospedado ahora en el grupo de servidores de reserva. Por definición, cualquier usuario originalmente hospedado en el grupo de servidores de reserva no es un usuario afectado.

### Experiencia de un usuario afectado en un grupo de conmutación por recuperación

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarea o estado de usuario</th>
<th>Durante la conmutación por recuperación</th>
<th>Una vez finalizada la conmutación por recuperación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Estado del usuario que ya ha iniciado sesión</p></td>
<td><p>El usuario permanece en su sesión y sigue conectado al grupo de servidores de reserva. En algún momento, se cerrará la sesión del usuario y volverá a la sesión en el grupo principal original, en el modo de resistencia.</p></td>
<td><p>El usuario continúa en su sesión y se coloca en modo normal.</p></td>
</tr>
<tr class="even">
<td><p>Inicio de sesión de un nuevo usuario</p></td>
<td><p>El usuario puede iniciar sesión en el grupo principal en el modo de resistencia.</p></td>
<td><p>El usuario puede iniciar sesión en el grupo principal original en modo normal.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencias en curso organizadas por un usuario afectado</p></td>
<td><p>Se terminan todas las modalidades de conferencia. Se mostrará el botón Unirse de nuevo, pero ningún usuario puede volver a unirse mientras el usuario afectado está en modo de resistencia.</p></td>
<td><p>Ahora funcionan todas las modalidades. Cada participante debe hacer clic para volver a unirse a la conferencia.</p></td>
</tr>
<tr class="even">
<td><p>Conferencias en curso organizadas por un usuario no afectado</p></td>
<td><p>La conferencia continúa y el usuario afectado puede permanecer en la conferencia. El usuario afectado está limitado a lo que se puede hacer en el modo de resistencia.</p></td>
<td><p>La conferencia continúa y el usuario afectado puede permanecer en la conferencia y todas las modalidades funcionan después de que el usuario sale del modo de resistencia.</p></td>
</tr>
<tr class="odd">
<td><p>Programación o modificación de las reuniones programadas, creación de conferencias ad-hoc</p></td>
<td><p>No son posibles mientras el usuario está en modo de resistencia.</p></td>
<td><p>Disponibles para todas las modalidades.</p></td>
</tr>
<tr class="even">
<td><p>Presencia según otros usuarios en el mismo grupo</p></td>
<td><p>Presencia desconocida mientras el usuario está conectado al grupo de servidores de reserva durante el modo de resistencia.</p></td>
<td><p>Muestra el último estado de presencia establecido por el usuario, y los cambios de presencia ahora se reflejarán.</p></td>
</tr>
<tr class="odd">
<td><p>Disponibilidad del servicio de libreta de direcciones y lista de contactos</p></td>
<td><p>No disponible</p></td>
<td><p>Disponible</p></td>
</tr>
<tr class="even">
<td><p>Todas las sesiones punto a punto y las modalidades</p></td>
<td><p>Disponible</p></td>
<td><p>Disponible</p></td>
</tr>
</tbody>
</table>


### Experiencia de un usuario hospedado en un grupo de servidores no afectado durante la conmutación por recuperación de otro grupo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarea de usuario</th>
<th>Durante la conmutación por recuperación</th>
<th>Una vez finalizada la conmutación por recuperación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Visualización de la presencia del usuario afectado</p></td>
<td><p>Muestra el último estado de presencia establecido por el usuario afectado.</p></td>
<td><p>En funcionamiento. Los usuarios no afectados verán las actualizaciones realizadas por los usuarios afectados.</p></td>
</tr>
<tr class="even">
<td><p>Conferencias en curso organizadas por un usuario afectado</p></td>
<td><p>Se terminan todas las modalidades de conferencia.</p></td>
<td><p>Ahora funcionan todas las modalidades. Cada participante debe hacer clic para volver a unirse a la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencias en curso organizadas por un usuario no afectado</p></td>
<td><p>La conferencia continúa, el usuario afectado puede permanecer en la conferencia y funcionan todas las modalidades.</p></td>
<td><p>La conferencia continúa, el usuario afectado puede permanecer en la conferencia y funcionan todas las modalidades.</p></td>
</tr>
<tr class="even">
<td><p>Todas las sesiones punto a punto y las modalidades</p></td>
<td><p>Disponible</p></td>
<td><p>Disponible</p></td>
</tr>
</tbody>
</table>

