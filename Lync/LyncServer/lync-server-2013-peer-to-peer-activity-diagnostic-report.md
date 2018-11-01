---
title: 'Lync Server 2013: Informe de diagnóstico de actividad punto a punto'
TOCTitle: Informe de diagnóstico de actividad punto a punto
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48274246
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de diagnóstico de actividad punto a punto en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El informe de diagnósticos de actividad punto a punto proporciona información acerca del éxito y error de sus sesiones de comunicación punto a punto. Tenga en cuenta que Microsoft Lync Server 2013 distingue entre diferentes tipos de error:

  - **Error esperado**. Un error esperado es normalmente un error solo en el sentido más técnico. Por ejemplo, supongamos que llama a alguien, pero que esta persona está fuera de la oficina y no puede responder al teléfono. Dado que no se respondió la llamada, esta se considera técnicamente un error. Por otra parte, fue un error inesperado: Microsoft Lync Server 2013 no espera que responda al teléfono si no está disponible para responderlo. De la misma manera, se producirá un error inesperado si intenta enviar un mensaje instantáneo a un usuario que se encuentra fuera de línea, o ha iniciado sesión, solo en un teléfono que no admite mensajería instantánea.

  - **Error inesperado**. Un error inesperado es exactamente lo que el nombre implica; un error que, en función de las circunstancias, no esperaría que se produjera. Por ejemplo, supongamos que llama a alguien y que esa persona está disponible para responder a la llamada; sin embargo, cuando Lync Server 2013 trata de enrutar su llamada al correo de voz, se produce un error de la llamada porque se ha perdido la conectividad a la mensajería unificada de Exchange. Ese es un error inesperado; esperaría que las llamadas siempre se pudieran enrutar al correo de voz. Como regla general, los errores inesperados son errores verdaderos: hay problemas que probablemente no se pueden remediar a través de la capacitación del usuario o medidas similares.

Tenga en cuenta que es posible que las métricas de éxito, errores esperados y errores inesperados no se sumen a la métrica de sesiones totales. Por ejemplo, en la ilustración anterior, tenemos los siguientes valores:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Correctas</th>
<th>Errores esperados</th>
<th>Errores inesperados</th>
<th>Total de sesiones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16</p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Si suma 2024 + 469 + 16, obtiene un total de 2.509 sesiones, aunque la columna Total de sesiones muestra un total de 2.521 sesiones. Las 12 sesiones "que faltan" son sesiones que el sistema no puede clasificar como correctas o no correctas. Ese será a veces el caso cuando un producto de terceros introduzca un nuevo código de diagnóstico que no es familiar para Lync Server. Cuando eso sucede, las llamadas realizadas usando ese producto, y la notificación de ese código de diagnóstico, no siempre se pueden clasificar como correcto, un error esperado o un error inesperado.

## Obtener acceso al informe de diagnósticos de actividad punto a punto

Al informe de diagnósticos de actividad punto a punto se obtiene acceso desde la página principal de informes de supervisión. Para obtener acceso al [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md) haga clic en cualquiera de las siguientes métricas:

  - Volumen de errores inesperados

  - Volumen de errores esperados

## Haciendo el mejor uso del informe de diagnósticos de actividad punto a punto

Hay varias maneras para poder filtrar el informe de diagnósticos de actividad punto a punto pero, de manera predeterminada, dichas opciones de filtrado está ocultas para su visión. Para ver las opciones de filtrado disponibles para usted, haga clic en el botón Mostrar u ocultar parámetros de la esquina superior derecha de la ventana de informe. Una vez haga eso, las opciones de filtrado estarán disponibles para su uso.

## Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de diagnóstico de actividad punto a punto permite filtrar por la modalidad de sesión (por ejemplo, mensajería instantánea, transferencia de archivos o uso de aplicaciones compartidas). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.

En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de diagnóstico de actividad punto a punto.

### Filtros del informe de diagnóstico de actividad punto a punto

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
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 00:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 00:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
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
<p>Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo de servidores</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Modalidad</strong></p></td>
<td><p>Indica el tipo de actividad de comunicación que tuvo lugar. Seleccione una de las opciones siguientes:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Mensajería instantánea</p></li>
<li><p>Transferencia de archivos</p></li>
<li><p>Uso compartido de aplicaciones</p></li>
<li><p>Audio</p></li>
<li><p>Vídeo</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Métricas (por modalidad)

En la tabla siguiente, se muestra la información proporcionada en el informe de diagnóstico de actividad punto a punto para cada modalidad.

### Métricas (por modalidad)

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
<td><p><strong>Volumen de corrección</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones punto a punto correctas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de corrección</strong></p></td>
<td><p>N.º</p></td>
<td><p>Porcentaje de sesiones punto a punto que se completaron con problemas importantes. Se calcula dividiendo el volumen de corrección por el total de sesiones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volumen de errores esperados</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones en las que se produjo un &quot;error esperado&quot;.</p>
<p>Un error esperado es aquel que se prevé que vaya a producirse. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de errores esperados</strong></p></td>
<td><p>N.º</p></td>
<td><p>Porcentaje de sesiones punto a punto que experimentaron un error esperado. Se calcula dividiendo el volumen de errores esperados por el total de sesiones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volumen de errores inesperados</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones en las que se produjo un &quot;error inesperado&quot;.</p>
<p>Un error inesperado es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no debería finalizarse si el autor de la llamada está en espera. De ser así, dicha situación se identificaría como un error inesperado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de errores inesperados</strong></p></td>
<td><p>N.º</p></td>
<td><p>Porcentaje de sesiones punto a punto que experimentaron un error inesperado. Se calcula dividiendo el volumen de errores inesperados por el total de sesiones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sesiones</strong></p></td>
<td><p>N.º</p></td>
<td><p>Número total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.</p></td>
</tr>
</tbody>
</table>

