---
title: 'Lync Server 2013: Informe de registro de usuario'
TOCTitle: Informe de registro de usuario
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48274523
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de registro de usuario en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El Informe de registro de usuario ofrece información general acerca de la actividad de inicio de sesión de los usuarios y, sobre todo, acerca del número de usuarios que han iniciado sesión en Microsoft Lync Server 2013 durante un periodo especificado (cada hora, día, semana o mes). Tenga en cuenta que el informe solo indica cuántas personas han iniciado sesión. No indica *qué* personas iniciaron sesión. Los informes de supervisión no ofrecen información sobre los usuarios específicos que están usando Lync Server 2013 (y cuáles no lo están usando). Sin embargo, puede usar el Informe de actividad de usuario para obtener una estimación de la información de usuarios.

Al proporcionar información sobre el inicio de sesión de los usuarios, el Informe de registro de usuario hace dos distinciones. En primer lugar, desglosa los inicios de sesión en dos categorías: inicios de sesión internos y externos. Los inicios de sesión internos corresponden a usuarios que iniciaron sesión desde dentro del firewall de la organización (es decir, mientras estaban conectados a la red corporativa). Los inicios de sesión externos corresponden a usuarios que iniciaron sesión desde fuera del firewall a través de un Servidor perimetral (por ejemplo, un usuario que haya iniciado sesión desde un cibercafé contará como un inicio de sesión externo). Puede usar el Informe de registro de usuario para saber cuántos de sus usuarios han iniciado sesión desde fuera del firewall.

Además, el Informe de registro de usuario indica el número de usuarios *activos* presentes en un periodo determinado. Un usuario inactivo es un usuario que ha participado en una sesión de mensajería instantánea (MI), en una Reunión de Lync, que ha realizado o recibido una llamada de teléfono o que ha usado Lync Server durante dicho periodo. No debe confundirse este tipo de usuario con los usuarios que hayan iniciado sesión y que nunca hayan usado el sistema.

## Acceso al Informe de registro de usuario

Puede tener acceso al Informe de registros de usuario únicamente desde la página de inicio de los informes de supervisión. El Informe de registro de usuario no está vinculado a ningún otro informe.

## Cómo sacar el máximo partido al Informe de registro de usuario

Tras implementar Lync Server una de las preguntas más comunes que cabe plantearse es la siguiente: ¿cómo puedo saber si mis usuarios están realmente usando esta nueva tecnología? Aunque existen algunas limitaciones al respecto, el Informe de registro de usuario puede ayudarle a encontrar una respuesta para esta pregunta. Para determinar si los usuarios están usando o no están usando Lync Server, deberá hacer dos cosas. En primer lugar, deberá obtener el valor de la métrica Usuarios de inicios de sesión distintos del Informe de registro de usuario. Este valor indica cuántos individuos han iniciado sesión en Lync Server.

Por el contrario, la métrica Total de inicios de sesión muestra cuántas veces un individuo ha iniciado sesión en Lync Server. Por ejemplo, supongamos que Ken Myer ha iniciado sesión en Lync Server cinco veces en un día. En este caso, Ken Myer contaría como cinco inicios de sesión en la métrica Total de inicios de sesión pero solo un inicio de sesión en la métrica Usuarios de inicios de sesión distintos. Del mismo modo, es muy habitual que un usuario inicie sesión desde múltiples dispositivos o ubicaciones. Por ejemplo, un usuario puede iniciar sesión con su equipo de sobremesa o su equipo portátil. Además, el usuario también es posible que disponga de un teléfono IP capaz de iniciar sesión automáticamente en Lync Server. En este ejemplo, solo hay un único usuario con tres inicios de sesión.

Para explicar la diferencia entre inicios de sesión únicos y totales, es necesario considerar los inicios de sesión que se producen durante un periodo determinado en la tabla siguiente.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Usuario</th>
<th>Hora de inicio de sesión</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 08:45:00</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 08:46:00</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 09:17:00</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 09:22:00</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 09:31:00</p></td>
</tr>
</tbody>
</table>


Tenga en cuenta que existe un total de cinco inicios de sesión. Sin embargo, solo hay dos inicios de sesión únicos: Ken Myer (que ha iniciado sesión tres veces) y Pilar Ackerman (que ha iniciado sesión dos veces). Esa es la diferencia entre inicios de sesión y usuario de inicios de sesión distinto.

Además de saber el número de inicios de sesión únicos, es necesario saber el número total de usuarios habilitados para Lync Server. Este valor puede recuperarse abriendo el Shell de administración de Lync Server 2013 y con la ejecución del siguiente comando de Windows PowerShell:

    (Get-CsUser).Count

Si el comando anterior devuelve un valor de 1,236 y la métrica de Usuarios de inicios de sesión distintos devuelve un valor de promedio de 667, esto indica que un poco más de la mitad de los usuarios habilitados para Lync inician sesión en el sistema cada día (es decir, 667 dividido por 1,236, lo que da un resultado aproximado del 54%).

> [!WARNING]  
> Es necesario tener en cuenta que las métricas de inicio de sesión registran los usuarios que han iniciado sesión durante el periodo especificado. Estas métricas no registran los usuarios que ya habían iniciado sesión en el sistema. Por ejemplo, si la métrica de Usuarios de inicios de sesión distintos muestra 667 inicios de sesión y tiene 1.236 usuarios, quiere decir que aproximadamente la mitad de los usuarios han iniciado sesión en el sistema. Sin embargo, suponga que 300 usuarios ya habían iniciado sesión en el sistema en el momento en que comenzó a comprobar los datos de inicio de sesión. Esto implicaría que en realidad hay cerca de 1.000 usuarios que han iniciado sesión en Lync Server, lo que representa casi un 80% de los usuarios.



También debe comparar el valor de Usuarios de inicios de sesión distintos con el valor de la métrica Usuarios activos distintos. La métrica Usuarios activos distintos indica cuántos usuarios distintos han usado Lync Server en realidad: si han realizado llamadas telefónicas, si se han unido a una Reunión de Lync o si han participado en una sesión de mensajería instantánea. Esta información es de utilidad, ya que Microsoft Lync 2013 puede configurarse para que se inicie automáticamente cada vez que un usuario inicie Windows. Por ello, es posible que tenga un elevado número de usuarios que inicien sesión automáticamente en Lync al iniciar sesión en Windows cada día, aunque nunca hagan uso de Lync Server durante este periodo.

La métrica Usuarios activos distintos también proporciona datos relevantes para las organizaciones en las que los usuarios no cierren la sesión de Windows al final del día. En su lugar, bloquean los equipos y dejan Windows y Lync en ejecución. En esta situación, puede registrar muy pocos inicios de sesión al día porque los usuarios simplemente iniciaron sesión hace varios días y aún mantienen la sesión iniciada. Sin embargo, la métrica de Usuarios activos distintos indica si los usuarios están usando activamente Lync u otro cliente de Lync Server.

## Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de registro de usuario permite ver los datos de todos los Grupo de registradores y Servidores perimetrales, o ver los datos de un grupo de servidores individual. También se puede elegir cómo agrupar los datos. En este caso, los registros se agrupan por hora, día, semana o mes.

En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de registro de usuario.

### Filtros del informe de registro de usuario

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Desde</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</p>
<p>7/7/2012 13:00</p>
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 00:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>07.07.12</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>03.07.12</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
<p>7/7/2012 13:00</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 00:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>07.07.12</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>03.07.12</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tiempo. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Cada hora (se puede ver un máximo de 25 horas)</p></li>
<li><p>Cada día (se puede ver un máximo de 31 días)</p></li>
<li><p>Cada semana (se puede ver un máximo de 12 semanas)</p></li>
<li><p>Cada mes (se puede ver un máximo de 12 meses)</p></li>
</ul>
<p>Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solamente se mostrará la cantidad máxima de valores (el principio será la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/7/2012 y una fecha de finalización del 28/2/2012, aparecerán los datos correspondientes a los días entre el 8/7/2012 a las 12:00 am y el 9/7/2012 a las 12:00 am (es decir un total de 31 días de datos).</p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo de servidores</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del Grupo de registradores o Servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
</tr>
</tbody>
</table>


## Métricas

En la tabla siguiente, se muestra la información proporcionada en el informe de registro de usuario.

### Métricas del informe de registro de usuario

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos por este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Cada hora</strong></p>
<p><strong>Cada día</strong></p>
<p><strong>Cada semana</strong></p>
<p><strong>Cada mes</strong></p></td>
<td><p>N.º</p></td>
<td><p>Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 7/7/2012, verá un desglose por horas de la actividad de registro del usuario correspondiente para esa fecha.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de inicios de sesión</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones de inicio correctas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Inicios de sesión internos</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de inicios de sesión en la red interna.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inicios de sesión externos</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de inicios de sesión realizados desde fuera de la red interna, por medio del servidor perimetral.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Usuarios de inicios de sesión distintos</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de usuarios con al menos una sesión de inicio. Un usuario con varias sesiones de inicio se considera un usuario, al igual que una persona con una sola sesión de inicio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Usuarios activos distintos</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de usuarios que participaron en una sesión punto a punto o de conferencia. Un usuario con varias sesiones se considera un usuario, al igual que una persona con una sola sesión.</p></td>
</tr>
</tbody>
</table>

