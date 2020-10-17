---
title: 'Lync Server 2013: estado de replicación del almacén de administración central'
description: 'Lync Server 2013: estado de replicación del almacén de administración central.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f1f9008a966040cf34ac0499c023f9dbe53a541
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544366"
---
# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="77f56-103">Almacén de administración central estado de replicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f56-103">Central management store replication status in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77f56-104">_**Última modificación del tema:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="77f56-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="77f56-105">Cuando un administrador realiza un cambio de algún tipo a Lync Server (por ejemplo, cuando un administrador crea una nueva Directiva de voz o cambia las opciones de configuración del servidor de libreta de direcciones) que el cambio se registra en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="77f56-105">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="77f56-106">A su vez, el cambio debe replicarse en todos los equipos que ejecutan los servicios o roles de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77f56-106">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="77f56-107">Para replicar datos, el replicador maestro (que se ejecuta en el servidor de administración central) crea una instantánea de los datos de configuración cambiados.</span><span class="sxs-lookup"><span data-stu-id="77f56-107">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="77f56-108">A continuación, se envía una copia de esta instantánea a cada equipo que ejecuta los servicios o roles de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77f56-108">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="77f56-109">En esos equipos, un agente de replicación recibe la instantánea y carga los datos modificados.</span><span class="sxs-lookup"><span data-stu-id="77f56-109">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="77f56-110">A continuación, el agente envía a Master Replicator un mensaje que informa del estado de replicación más reciente.</span><span class="sxs-lookup"><span data-stu-id="77f56-110">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="77f56-111">El cmdlet Get-CsManagementStoreReplicationStatus permite comprobar el estado de replicación de todos los equipos de Lync Server de la organización.</span><span class="sxs-lookup"><span data-stu-id="77f56-111">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="77f56-112">¿Quién puede ejecutar este cmdlet?</span><span class="sxs-lookup"><span data-stu-id="77f56-112">Who can run this cmdlet?</span></span> <span data-ttu-id="77f56-113">De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Get-CsManagementStoreReplicationStatus de forma local: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="77f56-113">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="77f56-114">Para devolver una lista de todos los roles RBAC a los que se asignó este cmdlet (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="77f56-114">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="77f56-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77f56-115">See Also</span></span>


[<span data-ttu-id="77f56-116">Get-CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="77f56-116">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

