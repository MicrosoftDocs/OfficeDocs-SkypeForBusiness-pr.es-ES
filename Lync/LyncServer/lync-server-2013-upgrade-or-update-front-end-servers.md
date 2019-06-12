---
title: 'Lync Server 2013: actualizar o actualizar servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99c91a4f5fcae9f8d78bf01b19a17795916fb660
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="0577e-102">Upgrade or update Front End Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0577e-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0577e-103">_**Última modificación del tema:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="0577e-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="0577e-104">Los servidores front-end de un grupo de servidores Enterprise Edition se organizan en *dominios de actualización*.</span><span class="sxs-lookup"><span data-stu-id="0577e-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="0577e-105">Estos son subconjuntos de servidores front-end en el grupo.</span><span class="sxs-lookup"><span data-stu-id="0577e-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="0577e-106">El generador de topología crea automáticamente los dominios de actualización.</span><span class="sxs-lookup"><span data-stu-id="0577e-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="0577e-107">Al actualizar los servidores, debe hacerlo a un dominio de actualización cada vez.</span><span class="sxs-lookup"><span data-stu-id="0577e-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="0577e-108">Vuelva a poner cada servidor en un dominio de actualización, actualícelo y, a continuación, reinícielo antes de pasar a otro dominio de actualización.</span><span class="sxs-lookup"><span data-stu-id="0577e-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="0577e-109">Asegúrese de realizar un seguimiento de los dominios de actualización y los servidores que ha actualizado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="0577e-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="0577e-110">Use el siguiente diagrama de diagrama de flujo al actualizar cada servidor.</span><span class="sxs-lookup"><span data-stu-id="0577e-110">Use the following flowchart diagram when upgrading each server.</span></span>

<span data-ttu-id="0577e-111">![42ed59a4-1c26-49f7-ade4-a5a788457ab9] (images/JJ204736.42ed59a4-1c26-49f7-ade4-a5a788457ab9(OCS.15).jpg "42ed59a4-1c26-49f7-ade4-a5a788457ab9")</span><span class="sxs-lookup"><span data-stu-id="0577e-111">![42ed59a4-1c26-49f7-ade4-a5a788457ab9](images/JJ204736.42ed59a4-1c26-49f7-ade4-a5a788457ab9(OCS.15).jpg "42ed59a4-1c26-49f7-ade4-a5a788457ab9")</span></span>

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="0577e-112">Para aplicar una actualización a los servidores front-end de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="0577e-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="0577e-113">En un servidor front-end del grupo, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0577e-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="0577e-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="0577e-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="0577e-115">Si el valor de *PoolUpgradeState* está **ocupado**, espera 10 minutos y vuelve a probar **Get-CsPoolUpgradeReadinessState** .</span><span class="sxs-lookup"><span data-stu-id="0577e-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="0577e-116">Si ve **ocupado** durante al menos tres veces consecutivas, después de esperar 10 minutos entre cada intento, o si ve cualquier resultado de **InsufficientActiveFrontEnds** para **PoolUpgradeState,** entonces hay un problema con el grupo.</span><span class="sxs-lookup"><span data-stu-id="0577e-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="0577e-117">Si este grupo está emparejado con otro grupo de servidores front-end en una topología de recuperación ante desastres, debe dar error a la agrupación y, a continuación, actualizar los servidores de este grupo.</span><span class="sxs-lookup"><span data-stu-id="0577e-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="0577e-118">Para obtener más información, consulte [errores en un grupo en Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="0577e-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="0577e-119">Si el valor de *PoolUpgradeState* está **listo**, vaya al paso 2.</span><span class="sxs-lookup"><span data-stu-id="0577e-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="0577e-120">El cmdlet **Get-CsPoolUpgradeReadinessState** también devuelve información acerca de cada dominio de actualización del grupo y acerca de qué servidores front-end se encuentran en cada uno de los dominios de actualización.</span><span class="sxs-lookup"><span data-stu-id="0577e-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="0577e-121">Si el valor **ReadyforUpgrade** es **verdadero** para el dominio de actualización que contiene el servidor o los servidores que desea actualizar, puede actualizarlos de forma segura ahora.</span><span class="sxs-lookup"><span data-stu-id="0577e-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="0577e-122">Para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0577e-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="0577e-123">Detenga las nuevas conexiones a los servidores front-end que va a actualizar con el `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0577e-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="0577e-124">Si va a realizar estas actualizaciones del servidor durante un tiempo de inactividad del servidor programado, puede ejecutar este cmdlet<STRONG></STRONG>sin el parámetro "-acNormal", de la siguiente manera: <STRONG>Stop-CsWindowsService</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0577e-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="0577e-125">Esto cerrará inmediatamente los servicios, sin tener que esperar a que se completen todas las solicitudes de servicio existentes.</span><span class="sxs-lookup"><span data-stu-id="0577e-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="0577e-126">Actualice los servidores asociados con este dominio de actualización.</span><span class="sxs-lookup"><span data-stu-id="0577e-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="0577e-127">Reinicie los servidores y asegúrese de que acepten nuevas conexiones.</span><span class="sxs-lookup"><span data-stu-id="0577e-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="0577e-128">Repita los pasos 1 y 2 para cada uno de los dominios de actualización del grupo, hasta que se hayan actualizado todos los servidores de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="0577e-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

