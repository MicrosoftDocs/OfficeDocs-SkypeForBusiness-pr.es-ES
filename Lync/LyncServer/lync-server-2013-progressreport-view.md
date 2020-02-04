---
title: 'Lync Server 2013: vista ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a>Vista ProgressReport en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La vista ProgressReport almacena información sobre las sesiones completadas. Los informes de progreso solo se escribirán para las llamadas y las sesiones que la 2013 determina Lync Server puede resultar útil para propósitos de diagnóstico. Esta vista se presentó en Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no hacen referencia a errores sino a mensajes que indican el estado de las llamadas o los mensajes.



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de error. Se usa junto con ErrorReportSeq para identificar de forma única un error.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificación para identificar el error. Se usa junto con ErrorTime para identificar de forma única un error.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>IDENTIFICADOR para identificar el informe de progreso. Se usa para distinguir los informes de progreso del mismo informe de errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>IDENTIFICADOR de diagnóstico del informe de errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Origen</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del servidor que originó el error (si el informe fue enviado desde un componente de servidor).</p></td>
</tr>
<tr class="even">
<td><p><strong>Aplicación</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre de la aplicación que originó el error (si el informe fue enviado desde un componente de servidor).</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Información de error adicional.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

