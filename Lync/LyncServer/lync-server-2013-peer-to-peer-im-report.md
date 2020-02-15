---
title: 'Lync Server 2013: informe de mensajería instantánea punto a punto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b74f22e422539a8d7de1f2f7bad29a72d43646a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Informe de mensajería instantánea punto a punto en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El informe de mensajería instantánea punto a punto ofrece información de tendencias acerca de las sesiones de mensajería instantánea (MI) punto a punto, desglosadas por grupo de servidores y por tipo de autenticación. El informe puede mostrar el número total de sesiones mantenidas durante el período de tiempo especificado (por ejemplo, día a día u hora a hora) o bien, puede mostrar el número total de mensajes instantáneos enviados durante ese período de tiempo.

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>Obtener acceso al informe de mensajería instantánea de punto a punto

Solo puede obtener acceso al informe de mensajería instantánea punto a punto abriendo el [Informe de Resumen de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) y, a continuación, haciendo clic en cualquiera de las siguientes métricas:

  - Total de sesiones de MI punto a punto

  - Total de mensajes instantáneos punto a punto

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Aprovechar al máximo el informe de mensajería instantánea de punto a punto

De manera predeterminada, el informe de mensajería instantánea de punto a punto le muestra el recuento de mensajes por hora (o día, en función de su configuración). Sin embargo, también puede elegir ver el día por sesiones por hora. Para ello, haga clic en **Mostrar u ocultar parámetros** en la esquina superior derecha de la ventana informes y, a continuación, haga clic en **Recuento de sesiones** en la lista **Informe por**.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de mensajería instantánea punto a punto.

### <a name="peer-to-peer-im-report-filters"></a>Filtros del informe de mensajería instantánea punto a punto

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
<td><p><strong>From</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</p>
<p>7/7/2012 1:00 pm</p>
<p>Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre empiezan en domingo y terminan en sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
<p>7/7/2012 13:00</p>
<p>Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo de</strong></p></td>
<td><p>Intervalo de tiempo. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Cada hora (se puede ver un máximo de 25 horas)</p></li>
<li><p>Cada día (se puede ver un máximo de 31 días)</p></li>
<li><p>Cada semana (se puede ver un máximo de 12 semanas)</p></li>
<li><p>Cada mes (se puede ver un máximo de  12 meses)</p></li>
</ul>
<p>Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio 7/7/2012 y una fecha de finalización 28/2/2012, se mostrarán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</p></td>
</tr>
<tr class="even">
<td><p><strong>Informe por</strong></p></td>
<td><p>Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes:</p>
<ul>
<li><p>Recuento de sesiones</p></li>
<li><p>Recuento de mensajes</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Métricas para la mensajería instantánea punto a punto por grupo

En la tabla siguiente, se muestra la información proporcionada en el informe de mensajería instantánea punto a punto.

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Métricas para la mensajería instantánea punto a punto por grupo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos en este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>No</p></td>
<td><p>Nombre del grupo de registrador o servidor perimetral.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fecha y hora</strong></p></td>
<td><p>No</p></td>
<td><p>Fecha y hora en las que tuvo lugar la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones o recuento total de mensajes.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Métricas para la mensajería instantánea punto a punto por tipo de autenticación

En la tabla siguiente, se muestra la información proporcionada en el informe de mensajería instantánea punto a punto para cada tipo de autenticación utilizado por los participantes de una sesión punto a punto.

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Métricas para la mensajería instantánea punto a punto por tipo de autenticación

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos en este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Tipo de autenticación</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo de autenticación utilizado por los participantes de la sesión. Los valores suelen ser los siguientes:</p>
<ul>
<li><p>Empresa</p></li>
<li><p>Federadas</p></li>
<li><p>IMG</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Fecha y hora</strong></p></td>
<td><p>No</p></td>
<td><p>Fecha y hora en las que tuvo lugar la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones o recuento total de mensajes.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

