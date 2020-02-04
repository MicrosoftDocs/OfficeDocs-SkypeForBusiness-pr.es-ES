---
title: 'Lync Server 2013: Lista de tablas de cumplimiento del servidor de chat persistente'
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
ms.openlocfilehash: 3c4f6e9622e839e2f1fd719b8e2d7ba95286247e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="fddb0-102">Lista de tablas de cumplimiento del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fddb0-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fddb0-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="fddb0-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="fddb0-104">El esquema de base de datos de cumplimiento de chat persistente consta de las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="fddb0-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="fddb0-105">Lista de tablas de cumplimiento del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="fddb0-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fddb0-106">Tabla</span><span class="sxs-lookup"><span data-stu-id="fddb0-106">Table</span></span></th>
<th><span data-ttu-id="fddb0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fddb0-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fddb0-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fddb0-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fddb0-109">Contiene los eventos de cumplimiento que el adaptador configurado aún no ha procesado.</span><span class="sxs-lookup"><span data-stu-id="fddb0-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="fddb0-110">Esta tabla incluye eventos persistentes relacionados con el chat, como mensajes instantáneos y descargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="fddb0-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="fddb0-111">(Los eventos de participantes se controlan en la tabla tblComplianceParticipant).</span><span class="sxs-lookup"><span data-stu-id="fddb0-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="fddb0-112">(Los servidores que procesaron los eventos de esta tabla se muestran en la tabla tblComplianceFanout).</span><span class="sxs-lookup"><span data-stu-id="fddb0-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fddb0-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fddb0-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fddb0-114">Contiene los servidores que procesaron un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="fddb0-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="fddb0-115">Esta tabla está estrechamente acoplada a la tabla tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="fddb0-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fddb0-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fddb0-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fddb0-117">Contiene participantes actuales por servicio de chat y por servidor.</span><span class="sxs-lookup"><span data-stu-id="fddb0-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="fddb0-118">Se mantiene según los eventos de conformidad con la Unión y la parte recibidos del servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fddb0-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fddb0-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fddb0-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fddb0-120">Contiene información de estado de cumplimiento para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="fddb0-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

