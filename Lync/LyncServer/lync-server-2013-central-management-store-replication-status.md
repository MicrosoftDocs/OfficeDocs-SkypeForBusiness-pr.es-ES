---
title: 'Lync Server 2013: estado de replicación del almacén de administración central'
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
ms.openlocfilehash: 4212e8616916f6a2a256530a7a0b74c9811f166d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="ae4fa-102">Estado de replicación del almacén de administración central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae4fa-102">Central management store replication status in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae4fa-103">_**Última modificación del tema:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="ae4fa-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="ae4fa-104">Cuando un administrador realiza un cambio de algún tipo en Lync Server (por ejemplo, cuando un administrador crea una nueva Directiva de voz o cambia la configuración del servidor de la libreta de direcciones), el cambio se registra en el almacén central de administración.</span><span class="sxs-lookup"><span data-stu-id="ae4fa-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="ae4fa-105">A su vez, el cambio se debe replicar a todos los equipos que ejecutan los servicios de Lync Server o los roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="ae4fa-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="ae4fa-106">Para replicar datos, el replicador maestro (que se ejecuta en el servidor de administración central) crea una instantánea de los datos de configuración cambiados.</span><span class="sxs-lookup"><span data-stu-id="ae4fa-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="ae4fa-107">A continuación, se envía una copia de esta instantánea a cada equipo que ejecute los roles de servidor o los servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ae4fa-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="ae4fa-108">En estos equipos, un agente de replicación recibe la instantánea y carga los datos cambiados.</span><span class="sxs-lookup"><span data-stu-id="ae4fa-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="ae4fa-109">Después, el agente envía un mensaje al replicador maestro para informar del estado de replicación más reciente.</span><span class="sxs-lookup"><span data-stu-id="ae4fa-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="ae4fa-110">El cmdlet Get-CsManagementStoreReplicationStatus le permite comprobar el estado de replicación de cualquiera (o de todos) los equipos de Lync Server de su organización.</span><span class="sxs-lookup"><span data-stu-id="ae4fa-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="ae4fa-111">¿Quién puede ejecutar este cmdlet?</span><span class="sxs-lookup"><span data-stu-id="ae4fa-111">Who can run this cmdlet?</span></span> <span data-ttu-id="ae4fa-112">De forma predeterminada, los miembros de los siguientes grupos están autorizados a ejecutar localmente el cmdlet Get-CsManagementStoreReplicationStatus: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ae4fa-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="ae4fa-113">Para devolver una lista de todos los roles RBAC a los que se asignó este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae4fa-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="ae4fa-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae4fa-114">See Also</span></span>


[<span data-ttu-id="ae4fa-115">Get-CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="ae4fa-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

