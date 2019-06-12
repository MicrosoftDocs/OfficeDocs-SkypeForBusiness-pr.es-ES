---
title: 'Lync Server 2013: informe de registro de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f56ffd05e677d5106552a9ebcf8a0718efbc100
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Informe de registro de usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-21_

El informe de registro de usuario proporciona una descripción general de la actividad de inicio de sesión de usuario, principalmente información sobre el número de usuarios que han iniciado sesión en Microsoft Lync Server 2013 durante un período de tiempo especificado (cada hora, diariamente, semanalmente, mensualmente). Tenga en cuenta que el informe solo indica cuántas personas han iniciado sesión. No indica *qué* personas iniciaron sesión. Los informes de supervisión no proporcionan información sobre qué usuarios concretos usan Lync Server 2013 (y cuáles no). Pero, puede usar el Informe de actividad de usuario para obtener una estimación de la información de usuarios.

Al proporcionar información sobre el inicio de sesión de los usuarios, el Informe de registro de usuario hace dos distinciones. En primer lugar, desglosa los inicios de sesión en dos categorías: inicios de sesión internos y externos. Los inicios de sesión internos corresponden a usuarios que iniciaron sesión desde dentro del firewall de la organización (es decir, mientras estaban conectados a la red corporativa). Los inicios de sesión externos representan a los usuarios que iniciaron sesión desde fuera del Firewall a través de un servidor perimetral (por ejemplo, un usuario que inició sesión desde un café de Internet cuenta como un inicio de sesión externo). Puede usar el Informe de registro de usuario para saber cuántos de sus usuarios han iniciado sesión desde fuera del firewall.

Además, el Informe de registro de usuario indica el número de usuarios *activos* presentes en un periodo determinado. Un usuario activo es un usuario que participó en una sesión de mensajería instantánea (mi), participó en una reunión de Lync, realizó o recibió una llamada de teléfono, o bien usó Lync Server durante ese período de tiempo. No tienen que confundirse este tipo de usuario con los usuarios que hayan iniciado sesión y que nunca hayan usado el sistema.

<div>

## <a name="accessing-the-user-registration-report"></a>Acceso al Informe de registro de usuario

Puede tener acceso al Informe de registros de usuario únicamente desde la página de inicio de los informes de supervisión. El Informe de registro de usuario no está vinculado a ningún otro informe.

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>Cómo sacar el máximo partido al Informe de registro de usuario

Una vez que haya implementado Lync Server, una de las preguntas más frecuentes es la siguiente: ¿Cómo sé si mis usuarios usan realmente esta nueva tecnología? Aunque existen algunas limitaciones al respecto, el Informe de registro de usuario puede ayudarle a encontrar una respuesta para esta pregunta. Para determinar si los usuarios usan Lync Server, debe hacer dos cosas. En primer lugar, tendrá que obtener el valor de la métrica Usuarios de inicios de sesión distintos del Informe de registro de usuario. Este valor indica cuántas personas distintas han iniciado sesión en Lync Server.

Por comparación, el número total de inicios de sesión métrico muestra cuántas horas totales han iniciado sesión en Lync Server. Por ejemplo, supongamos que Ken Myer ha iniciado sesión en Lync Server cinco veces distintas en un solo día. En ese caso, Ken Myer podría contar con cinco sesiones de inicio de sesión distintas para el total de inicios de sesión, pero solo un usuario de inicio de sesión para la métrica de usuarios de inicio de sesión únicos. Del mismo modo, no es raro que un usuario inicie sesión desde varios dispositivos o desde varias ubicaciones. Por ejemplo, un usuario puede iniciar sesión con su equipo de escritorio, su equipo portátil, y puede tener un teléfono IP que inicie sesión automáticamente en Lync Server. En este ejemplo, hay un usuario único con tres inicios de sesión.

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
<td><p>7/7/2012 8:45 A.M.</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8:46 A.M.</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:17 A.M.</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 9:22 A.M.</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:31 A.M.</p></td>
</tr>
</tbody>
</table>


Tenga en cuenta que existe un total de cinco inicios de sesión. Pero, solo hay dos inicios de sesión únicos: Ken Myer (que ha iniciado sesión tres veces) y Pilar Ackerman (que ha iniciado sesión dos veces). Esa es la diferencia entre inicios de sesión y usuario de inicios de sesión distinto.

Además de conocer el número de inicios de sesión únicos, necesita saber el número total de usuarios que se han habilitado para Lync Server. Ese valor se puede recuperar abriendo el shell de administración de Lync Server 2013 y ejecutando el siguiente comando de Windows PowerShell:

    (Get-CsUser).Count

Si el comando anterior devuelve un valor de 1.236 y Unique Logon users Metric devuelve un valor promedio de 667, lo que sugiere que un poco más de la mitad de los usuarios habilitados para Lync realmente está iniciando sesión en el sistema cada día (es decir, 667 dividido por 1.236 , que es aproximadamente 54%.

<div>


> [!WARNING]  
> Es necesario tener en cuenta que las métricas de inicio de sesión registran los usuarios que han iniciado sesión durante el periodo especificado. Estas métricas no registran los usuarios que ya habían iniciado sesión en el sistema. Por ejemplo, si la métrica de Usuarios de inicios de sesión distintos muestra 667 inicios de sesión y tiene 1236 usuarios, quiere decir que aproximadamente la mitad de los usuarios han iniciado sesión en el sistema. Pero, suponga que 300 usuarios ya habían iniciado sesión en el sistema en el momento en que comenzó a comprobar los datos de inicio de sesión. Eso significaría que, en realidad, casi 1.000 usuarios iniciaban sesión en Lync Server, lo que significa que cerca de 80% de los usuarios iniciaron sesión.



</div>

También es necesario comparar el valor de Usuarios de inicios de sesión distintos con el valor de la métrica Usuarios activos distintos. La métrica usuarios activos únicos le indica cuántos usuarios únicos han usado Lync Server realmente: hicieron una llamada telefónica, se unieron a una reunión de Lync o participaron en una sesión de mensajería instantánea. Esta información es útil porque Microsoft Lync 2013 se puede configurar para que se inicie automáticamente cada vez que un usuario inicie Windows. Por eso, es posible que tenga un gran número de usuarios que inician sesión automáticamente en Lync cuando inician sesión en Windows cada día, pero, en realidad, nunca usan Lync Server durante ese período de tiempo.

La métrica usuarios únicos activos también proporciona datos más significativos en una organización en la que los usuarios normalmente no cierran la sesión de Windows al final del día. En su lugar, simplemente bloquean sus equipos y dejan Windows y Lync en ejecución. En esta situación, puede registrar muy pocos inicios de sesión al día porque los usuarios simplemente iniciaron sesión hace varios días y aún mantienen la sesión iniciada. Sin embargo, los usuarios activos únicos le indican si los usuarios usan activamente Lync u otro cliente de Lync Server.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de registro de usuario le permite ver los datos de todos los grupos de registradores y servidores perimetrales o ver los datos de un grupo individual. También se puede elegir cómo agrupar los datos. En este caso, los registros se agrupan por hora, día, semana o mes.

En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de registro de usuario.

### <a name="user-registration-report-filters"></a>Filtros del informe de registro de usuario

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
<td><p><strong>De</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</p>
<p>7/7/2012 1:00 P.M.</p>
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
<p>7/7/2012 1:00 P.M.</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
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
<p>Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo de servidores individual o elegir <strong>[Todos]</strong> para ver los datos de todos los grupos de servidores. Esta lista desplegable se rellena automáticamente con los registros de la base de datos.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente, se muestra la información proporcionada en el informe de registro de usuario.

### <a name="user-registration-report-metrics"></a>Métricas del informe de registro de usuario

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
<td><p>No</p></td>
<td><p>Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo diario y hace clic en 7/7/2012, verá un desglose por hora de actividad de registro de usuario para esa fecha.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de inicios de sesión</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de sesiones de inicio correctas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Inicios de sesión internos</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de inicios de sesión en la red interna.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inicios de sesión externos</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de inicios de sesión realizados desde fuera de la red interna, por medio del servidor perimetral.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Usuarios de inicios de sesión únicos</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de usuarios con al menos una sesión de inicio. Un usuario con varias sesiones de inicio se considera un usuario, al igual que una persona con una sola sesión de inicio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Usuarios activos únicos</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de usuarios que participaron en una sesión punto a punto o de conferencia. Un usuario con varias sesiones se considera un usuario, al igual que una persona con una sola sesión.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

