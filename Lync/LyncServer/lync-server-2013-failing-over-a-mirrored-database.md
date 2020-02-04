---
title: 'Lync Server 2013: Conmutación por error de una base de datos reflejada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="92a3f-102">Conmutación por error de una base de datos reflejada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92a3f-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92a3f-103">_**Última modificación del tema:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="92a3f-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="92a3f-104">Si ha configurado la base de datos back-end para usar el reflejo sincronizado con un testigo, la conmutación por error es automática.</span><span class="sxs-lookup"><span data-stu-id="92a3f-104">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="92a3f-105">Si ha configurado el reflejo sincronizado sin un testigo, puede usar los siguientes procedimientos para realizar la conmutación por error y la recuperación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="92a3f-105">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="92a3f-106">También puede usar estos procedimientos para realizar un failover manual de las bases de datos y hacer un failback, incluso si ha configurado un testigo.</span><span class="sxs-lookup"><span data-stu-id="92a3f-106">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="92a3f-107">Para conmutar por error a la base de datos back-end</span><span class="sxs-lookup"><span data-stu-id="92a3f-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="92a3f-108">Antes de realizar la conmutación por error, determine qué base de datos back-end es el principal y cuál es el reflejo; para ello, escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="92a3f-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="92a3f-109">Si el almacén de administración central está hospedado en este grupo, escriba el siguiente cmdlet para determinar cuál es el principal y cuál es el reflejo del almacén central de administración:</span><span class="sxs-lookup"><span data-stu-id="92a3f-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="92a3f-110">Realice la conmutación por error de la base de datos de usuario:</span><span class="sxs-lookup"><span data-stu-id="92a3f-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="92a3f-111">Si el principal ha fallado y se está produciendo un error en el reflejo, escriba:</span><span class="sxs-lookup"><span data-stu-id="92a3f-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="92a3f-112">Si el reflejo ha fallado y se está conmutando por error al principal, escriba:</span><span class="sxs-lookup"><span data-stu-id="92a3f-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="92a3f-113">Si el grupo hospeda el servidor de administración central, realice la conmutación por error del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="92a3f-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="92a3f-114">Si el principal ha fallado y se está produciendo un error en el reflejo, escriba:</span><span class="sxs-lookup"><span data-stu-id="92a3f-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="92a3f-115">Si el reflejo ha fallado y se está conmutando por error al principal, escriba:</span><span class="sxs-lookup"><span data-stu-id="92a3f-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

