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
ms.openlocfilehash: aad04524df22c9d299b4a871b580330052d2aa5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531957"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="be500-102">Supervisar el rendimiento del almacenamiento back-end de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be500-102">Monitoring back end Lync Server 2013 storage performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be500-103">_**Última modificación del tema:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="be500-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="be500-104">Las bases de datos back-end de Lync Server 2013 son una parte muy importante de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be500-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="be500-105">Le recomendamos que supervise constantemente las bases de datos y los registros de transacciones respectivos para asegurarse de que el back-end de 2013 de Lync Server se ejecuta de forma óptima.</span><span class="sxs-lookup"><span data-stu-id="be500-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="be500-106">En la siguiente tabla se identifican los contadores de rendimiento que deben supervisarse para obtener información sobre el rendimiento del almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="be500-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="be500-107">Los valores de línea base de estos contadores deben determinarse en primer lugar (cuando el sistema está en su estado normal y previsto) para conocer los cambios de rendimiento cuando el sistema está sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="be500-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="be500-108">Contadores de rendimiento que se van a supervisar</span><span class="sxs-lookup"><span data-stu-id="be500-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be500-109">Contador de rendimiento</span><span class="sxs-lookup"><span data-stu-id="be500-109">Performance Counter</span></span></th>
<th><span data-ttu-id="be500-110">Umbrales de línea base</span><span class="sxs-lookup"><span data-stu-id="be500-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be500-111">Transacciones/seg (RTC)</span><span class="sxs-lookup"><span data-stu-id="be500-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be500-112">Transacciones/seg (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="be500-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be500-113">Transacciones por segundo (tempdb)</span><span class="sxs-lookup"><span data-stu-id="be500-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be500-114">Vaciados del registro/seg (RTC)</span><span class="sxs-lookup"><span data-stu-id="be500-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be500-115">Vaciados de registro/seg (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="be500-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be500-116">Vaciados de registro/seg (tempdb)</span><span class="sxs-lookup"><span data-stu-id="be500-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be500-117">Transferencias de disco/seg (lectura y escritura)-base de datos RTC</span><span class="sxs-lookup"><span data-stu-id="be500-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be500-118">Transferencias de disco/seg: registro RTC</span><span class="sxs-lookup"><span data-stu-id="be500-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be500-119">Transferencias de disco/seg-RTCDyn dB</span><span class="sxs-lookup"><span data-stu-id="be500-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be500-120">Transferencias de disco/seg.: registro de RTCDyn</span><span class="sxs-lookup"><span data-stu-id="be500-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

