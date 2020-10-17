---
title: 'Lync Server 2013: subinforme de Resumen de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddbbe3fc546010e78ee7df6aa8afb083e594ea14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502327"
---
# <a name="conference-summary-subreport-in-lync-server-2013"></a>Subinforme de Resumen de conferencia en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

El Subinforme de resumen de conferencia proporciona información general de sesiones de conferencia fallidas. Estas sesiones fallidas se dividen además por tipo de sesión: sesiones de foco y sesiones MCU.

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Subinforme de resumen de conferencia.

### <a name="conference-summary-subreport-filters"></a>Filtros del Subinforme de resumen de conferencia

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
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

La siguiente tabla contiene la información que recoge el Subinforme de resumen de conferencia.

### <a name="conference-summary-subreport-metrics"></a>Métricas del Subinforme de resumen de conferencia

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
<td><p><strong>Total de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de conferencias que ha tenido lugar.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sesiones de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones de conferencia. Una única conferencia puede tener varias sesiones; por ejemplo, una conferencia podría incluir tanto una sesión de foco como una sesión MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de sesión generales</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de todas las conferencias fallidas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones de foco</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones de foco.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de foco</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de sesiones de foco fallidas.</p></td>
</tr>
<tr class="even">
<td><p>Sesiones MCU</p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de MCU</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de sesiones MCU fallidas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones MCU por modalidad</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones MCU, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores por modalidad</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de sesiones MCU fallidas, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

