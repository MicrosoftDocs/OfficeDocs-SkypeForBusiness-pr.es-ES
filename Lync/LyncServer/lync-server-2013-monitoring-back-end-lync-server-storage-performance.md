---
title: 'Lync Server 2013: supervisar el rendimiento del almacenamiento de back-end de Lync Server'
description: 'Lync Server 2013: supervisar el rendimiento del almacenamiento de back-end de Lync Server.'
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
ms.openlocfilehash: e7501418d3589b941b7e92d2b414492c1d27a3ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562076"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="4b32a-103">Supervisar el rendimiento del almacenamiento back-end de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b32a-103">Monitoring back end Lync Server 2013 storage performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b32a-104">_**Última modificación del tema:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="4b32a-104">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="4b32a-105">Las bases de datos back-end de Lync Server 2013 son una parte muy importante de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b32a-105">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="4b32a-106">Le recomendamos que supervise constantemente las bases de datos y los registros de transacciones respectivos para asegurarse de que el back-end de 2013 de Lync Server se ejecuta de forma óptima.</span><span class="sxs-lookup"><span data-stu-id="4b32a-106">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="4b32a-107">En la siguiente tabla se identifican los contadores de rendimiento que deben supervisarse para obtener información sobre el rendimiento del almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4b32a-107">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="4b32a-108">Los valores de línea base de estos contadores deben determinarse en primer lugar (cuando el sistema está en su estado normal y previsto) para conocer los cambios de rendimiento cuando el sistema está sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="4b32a-108">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="4b32a-109">Contadores de rendimiento que se van a supervisar</span><span class="sxs-lookup"><span data-stu-id="4b32a-109">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b32a-110">Contador de rendimiento</span><span class="sxs-lookup"><span data-stu-id="4b32a-110">Performance Counter</span></span></th>
<th><span data-ttu-id="4b32a-111">Umbrales de línea base</span><span class="sxs-lookup"><span data-stu-id="4b32a-111">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b32a-112">Transacciones/seg (RTC)</span><span class="sxs-lookup"><span data-stu-id="4b32a-112">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b32a-113">Transacciones/seg (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="4b32a-113">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b32a-114">Transacciones por segundo (tempdb)</span><span class="sxs-lookup"><span data-stu-id="4b32a-114">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b32a-115">Vaciados del registro/seg (RTC)</span><span class="sxs-lookup"><span data-stu-id="4b32a-115">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b32a-116">Vaciados de registro/seg (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="4b32a-116">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b32a-117">Vaciados de registro/seg (tempdb)</span><span class="sxs-lookup"><span data-stu-id="4b32a-117">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b32a-118">Transferencias de disco/seg (lectura y escritura)-base de datos RTC</span><span class="sxs-lookup"><span data-stu-id="4b32a-118">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b32a-119">Transferencias de disco/seg: registro RTC</span><span class="sxs-lookup"><span data-stu-id="4b32a-119">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b32a-120">Transferencias de disco/seg-RTCDyn dB</span><span class="sxs-lookup"><span data-stu-id="4b32a-120">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b32a-121">Transferencias de disco/seg.: registro de RTCDyn</span><span class="sxs-lookup"><span data-stu-id="4b32a-121">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

