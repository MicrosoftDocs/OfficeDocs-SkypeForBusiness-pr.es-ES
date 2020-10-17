---
title: Validar la replicación de las opciones de configuración
description: Validar la replicación de las opciones de configuración.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26d8e9326da8b865f4e2ca3181975fb899300636
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552606"
---
# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="e0cd2-103">Validar la replicación de las opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="e0cd2-103">Validate replication of configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0cd2-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e0cd2-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e0cd2-105">Para validar la replicación de la información de configuración en el servidor perimetral, ejecute el cmdlet **Get-CsManagementStoreReplicationStatus** de lync Server 2013 en el equipo interno en el que se encuentra el almacén de administración central o en cualquier equipo unido al dominio en el que se hayan instalado los componentes principales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-105">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="e0cd2-106">Los resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación.</span><span class="sxs-lookup"><span data-stu-id="e0cd2-106">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="e0cd2-107">En ese caso, ejecute el cmdlet **Invoke-CsManagementStoreReplication** y deje tiempo para que se complete la replicación antes de ejecutar el cmdlet **Get-CsManagementStoreReplicationStatus** de nuevo .</span><span class="sxs-lookup"><span data-stu-id="e0cd2-107">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

