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

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="3c4e6-102">Supervisar el rendimiento de almacenamiento de back end de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c4e6-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c4e6-103">_**Última modificación del tema:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="3c4e6-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="3c4e6-104">Las bases de datos back-end de Lync Server 2013 son una parte muy importante de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c4e6-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="3c4e6-105">Recomendamos supervisar constantemente las bases de datos y los registros de transacciones respectivos para asegurarse de que el back-end de 2013 de Lync Server está funcionando de manera óptima.</span><span class="sxs-lookup"><span data-stu-id="3c4e6-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="3c4e6-106">La siguiente tabla identifica los contadores de rendimiento que deben supervisarse para obtener información sobre el rendimiento del almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="3c4e6-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="3c4e6-107">Los valores de línea base de estos contadores deben determinarse en primer lugar (cuando el sistema tiene la carga normal, esperada) para comprender los cambios de rendimiento cuando el sistema está estresado.</span><span class="sxs-lookup"><span data-stu-id="3c4e6-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="3c4e6-108">Contadores de rendimiento que se van a supervisar</span><span class="sxs-lookup"><span data-stu-id="3c4e6-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c4e6-109">Contador de rendimiento</span><span class="sxs-lookup"><span data-stu-id="3c4e6-109">Performance Counter</span></span></th>
<th><span data-ttu-id="3c4e6-110">Umbrales de línea base</span><span class="sxs-lookup"><span data-stu-id="3c4e6-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c4e6-111">Transacciones/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="3c4e6-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4e6-112">Transacciones/seg (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="3c4e6-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c4e6-113">Transacciones/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="3c4e6-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4e6-114">Vaciados del registro/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="3c4e6-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c4e6-115">Vaciados del registro/seg (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="3c4e6-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4e6-116">Vaciados de registro/sec (tempdb)</span><span class="sxs-lookup"><span data-stu-id="3c4e6-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c4e6-117">Transferencias de disco/seg (lectura y escritura): base de BD de RTC</span><span class="sxs-lookup"><span data-stu-id="3c4e6-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4e6-118">Transferencias de disco/seg.</span><span class="sxs-lookup"><span data-stu-id="3c4e6-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c4e6-119">Transferencias de disco/seg-RTCDyn dB</span><span class="sxs-lookup"><span data-stu-id="3c4e6-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4e6-120">Transferencias de disco/seg: registro de RTCDyn</span><span class="sxs-lookup"><span data-stu-id="3c4e6-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

