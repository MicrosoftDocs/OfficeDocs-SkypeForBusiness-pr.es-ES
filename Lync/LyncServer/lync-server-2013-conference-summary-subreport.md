---
title: 'Lync Server 2013: subinforme del Resumen de la Conferencia'
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
ms.openlocfilehash: 2537cbe959639baee6f0f986b3faea1ebd79b5a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a>Informe subinforme Resumen de la Conferencia en Lync Server 2013

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
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</p>
<p>7/7/2012 1:00 P.M.</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo de servidores</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todos]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
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
<th>¿Se pueden ordenar los datos por este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Total de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de conferencias que ha tenido lugar.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sesiones de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de sesiones de conferencia. Una única conferencia puede tener varias sesiones; por ejemplo, una conferencia podría incluir tanto una sesión de foco como una sesión MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de sesión generales</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de todas las conferencias fallidas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones de foco</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de sesiones de foco.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de foco</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de sesiones de foco fallidas.</p></td>
</tr>
<tr class="even">
<td><p>Sesiones MCU</p></td>
<td><p>No</p></td>
<td><p>Cantidad total de sesiones MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de MCU</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de sesiones MCU fallidas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones MCU por modalidad</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de sesiones MCU, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).</p></td>
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

