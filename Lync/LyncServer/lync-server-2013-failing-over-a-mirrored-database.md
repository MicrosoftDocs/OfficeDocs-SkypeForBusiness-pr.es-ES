---
title: 'Lync Server 2013: conmutación por error de una base de datos reflejada'
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
ms.openlocfilehash: 24aa85ea7dfdd76b20af30954ea2480fba2f21f5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="0edba-102">Conmutación por error de una base de datos reflejada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0edba-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0edba-103">_**Última modificación del tema:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="0edba-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="0edba-p101">Si ha configurado su base de datos back-end para que use la creación de reflejos sincronizados con un testigo, la conmutación por error es automática. Si ha configurado la creación de reflejos sincronizados sin testigo, puede usar los siguientes procedimientos para conmutar por error y conmutar por recuperación su base de datos. También puede usar estos procedimientos para conmutar por error y conmutar por recuperación manualmente sus bases de datos aunque haya configurado un testigo.</span><span class="sxs-lookup"><span data-stu-id="0edba-p101">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic. If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database. You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="0edba-107">Procedimiento para conmutar por error su base de datos back-end</span><span class="sxs-lookup"><span data-stu-id="0edba-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="0edba-108">Antes de la conmutación por error, determine qué base de datos back-end es la principal y cuál es la reflejada escribiendo el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0edba-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="0edba-109">Si el almacén de administración central está hospedado en este grupo de servidores, escriba el siguiente cmdlet para determinar cuál es el principal y cuál es el reflejo del almacén de administración central:</span><span class="sxs-lookup"><span data-stu-id="0edba-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="0edba-110">Realice la conmutación por error de la base de datos del usuario:</span><span class="sxs-lookup"><span data-stu-id="0edba-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="0edba-111">Si ha fallado la principal y está realizando la conmutación por error de la reflejada, escriba:</span><span class="sxs-lookup"><span data-stu-id="0edba-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="0edba-112">Si ha fallado la reflejada y está realizando la conmutación por error de la principal, escriba:</span><span class="sxs-lookup"><span data-stu-id="0edba-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="0edba-113">Si el grupo hospeda el servidor de administración central, realice la conmutación por error del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="0edba-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="0edba-114">Si ha fallado la principal y está realizando la conmutación por error de la reflejada, escriba:</span><span class="sxs-lookup"><span data-stu-id="0edba-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="0edba-115">Si ha fallado la reflejada y está realizando la conmutación por error de la principal, escriba:</span><span class="sxs-lookup"><span data-stu-id="0edba-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

