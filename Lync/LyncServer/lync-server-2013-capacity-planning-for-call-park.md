---
title: 'Lync Server 2013: Planificar la capacidad para el estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe55e09c67e62676202def9e3def3454d7cbd33
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="1e10e-102">Planificar la capacidad para el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e10e-102">Capacity planning for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e10e-103">_**Última modificación del tema:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="1e10e-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="1e10e-104">En la siguiente tabla se describe el modelo de usuario de estacionamiento de llamadas que puede usar como base para los requisitos de planes de capacidad.</span><span class="sxs-lookup"><span data-stu-id="1e10e-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e10e-105">Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debería poder administrar las cargas de trabajo de los servicios de estacionamiento de llamadas en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="1e10e-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="1e10e-106">Modelo de usuario de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="1e10e-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e10e-107">Métrica</span><span class="sxs-lookup"><span data-stu-id="1e10e-107">Metric</span></span></th>
<th><span data-ttu-id="1e10e-108">Por grupo front-end (con 8 servidores frontales)</span><span class="sxs-lookup"><span data-stu-id="1e10e-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="1e10e-109">Por servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="1e10e-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e10e-110">Tasa de estacionamiento</span><span class="sxs-lookup"><span data-stu-id="1e10e-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="1e10e-111">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="1e10e-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="1e10e-112">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="1e10e-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e10e-113">Tasa de recuperación de llamadas estacionadas</span><span class="sxs-lookup"><span data-stu-id="1e10e-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="1e10e-114">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="1e10e-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="1e10e-115">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="1e10e-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e10e-116">Promedio de duración del estacionamiento</span><span class="sxs-lookup"><span data-stu-id="1e10e-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="1e10e-117">60 segundos</span><span class="sxs-lookup"><span data-stu-id="1e10e-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="1e10e-118">60 segundos</span><span class="sxs-lookup"><span data-stu-id="1e10e-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

