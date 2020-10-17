---
title: 'Lync Server 2013: lista de tablas de cumplimiento del servidor de chat persistente'
description: 'Lync Server 2013: lista de tablas de cumplimiento del servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47cb28a0ca4180327c2adc48d80e9e41171a7bfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550076"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="667b2-103">Lista de tablas de cumplimiento del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="667b2-103">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="667b2-104">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="667b2-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="667b2-105">El esquema de la base de datos de cumplimiento de chat persistente consta de las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="667b2-105">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="667b2-106">Lista de tablas de cumplimiento del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="667b2-106">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="667b2-107">Table</span><span class="sxs-lookup"><span data-stu-id="667b2-107">Table</span></span></th>
<th><span data-ttu-id="667b2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="667b2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="667b2-109"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="667b2-109"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="667b2-110">Contiene los eventos de cumplimiento que aún no fueron procesados por el adaptador configurado.</span><span class="sxs-lookup"><span data-stu-id="667b2-110">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="667b2-111">Esta tabla incluye eventos relacionados con el chat persistente, como mensajes de chat y descargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="667b2-111">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="667b2-112">(Los eventos participantes son seguidos por la tabla tblComplianceParticipant).</span><span class="sxs-lookup"><span data-stu-id="667b2-112">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="667b2-113">(Los servidores que procesaron los eventos en esta tabla se enumeran en la tabla tblComplianceFanout).</span><span class="sxs-lookup"><span data-stu-id="667b2-113">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="667b2-114"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="667b2-114"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="667b2-115">Contiene los servidores que procesaron un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="667b2-115">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="667b2-116">Esta tabla está fuertemente vinculada con la tabla tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="667b2-116">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="667b2-117"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="667b2-117"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="667b2-118">Contiene los participantes actuales por servicio de chat y por servidor.</span><span class="sxs-lookup"><span data-stu-id="667b2-118">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="667b2-119">Se mantiene en función de los eventos de conformidad de Unión y parte recibidos del servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="667b2-119">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="667b2-120"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="667b2-120"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="667b2-121">Contiene información de estado de cumplimiento de todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="667b2-121">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

