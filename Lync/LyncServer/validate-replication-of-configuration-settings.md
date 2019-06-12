---
title: Validar la replicación de las opciones de configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cde1f3a96f249e98bc4e48c2e6d9c40adaad526
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="b3b9a-102">Validar la replicación de las opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="b3b9a-102">Validate replication of configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3b9a-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b3b9a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b3b9a-104">Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet **Get-CsManagementStoreReplicationStatus** de Lync Server 2013 en el equipo interno en el que se encuentra el almacén central de administración o en cualquier dominio equipo unido en el que se instalan los componentes principales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3b9a-104">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="b3b9a-105">Los resultados iniciales pueden indicar que el estado es "false" en lugar de "true" para la replicación.</span><span class="sxs-lookup"><span data-stu-id="b3b9a-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="b3b9a-106">En ese caso, ejecute el cmdlet **Invoke-CsManagementStoreReplication** y deje que se complete la replicación antes de volver a ejecutar el cmdlet **Get-CsManagementStoreReplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="b3b9a-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

