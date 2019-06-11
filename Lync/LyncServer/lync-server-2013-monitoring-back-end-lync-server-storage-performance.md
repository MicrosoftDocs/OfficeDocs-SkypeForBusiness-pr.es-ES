---
title: 'Lync Server 2013: supervisar el rendimiento de almacenamiento de back end de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c63956cebc7f532f92b6e0729bdfe811d0fdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Supervisar el rendimiento de almacenamiento de back end de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-02_

Las bases de datos back-end de Lync Server 2013 son una parte muy importante de la implementación de Lync Server 2013. Recomendamos supervisar constantemente las bases de datos y los registros de transacciones respectivos para asegurarse de que el back-end de 2013 de Lync Server está funcionando de manera óptima.

La siguiente tabla identifica los contadores de rendimiento que deben supervisarse para obtener información sobre el rendimiento del almacenamiento. Los valores de línea base de estos contadores deben determinarse en primer lugar (cuando el sistema tiene la carga normal, esperada) para comprender los cambios de rendimiento cuando el sistema está estresado.

### <a name="performance-counters-to-be-monitored"></a>Contadores de rendimiento que se van a supervisar

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contador de rendimiento</th>
<th>Umbrales de línea base</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transacciones/s (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transacciones/seg (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transacciones/s (tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Vaciados del registro/s (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Vaciados del registro/seg (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Vaciados de registro/sec (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transferencias de disco/seg (lectura y escritura): base de BD de RTC</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferencias de disco/seg.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transferencias de disco/seg-RTCDyn dB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferencias de disco/seg: registro de RTCDyn</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

