---
title: 'Lync Server 2013: supervisar el rendimiento del almacenamiento de back-end de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ac4ab62bdbb9b33a7c64014433dfd4f950a6298
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Supervisar el rendimiento del almacenamiento back-end de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-02_

Las bases de datos back-end de Lync Server 2013 son una parte muy importante de la implementación de Lync Server 2013. Le recomendamos que supervise constantemente las bases de datos y los registros de transacciones respectivos para asegurarse de que el back-end de 2013 de Lync Server se ejecuta de forma óptima.

En la siguiente tabla se identifican los contadores de rendimiento que deben supervisarse para obtener información sobre el rendimiento del almacenamiento. Los valores de línea base de estos contadores deben determinarse en primer lugar (cuando el sistema está en su estado normal y previsto) para conocer los cambios de rendimiento cuando el sistema está sobrecargado.

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
<td><p>Transacciones/seg (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transacciones/seg (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transacciones por segundo (tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Vaciados del registro/seg (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Vaciados de registro/seg (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Vaciados de registro/seg (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transferencias de disco/seg (lectura y escritura)-base de datos RTC</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferencias de disco/seg: registro RTC</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transferencias de disco/seg-RTCDyn dB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferencias de disco/seg.: registro de RTCDyn</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

