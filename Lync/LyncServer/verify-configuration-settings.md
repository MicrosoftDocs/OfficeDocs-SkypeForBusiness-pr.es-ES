---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 931ec2c67c8cdf0d1856cce7264ee968e3ea96f0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508427"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="b62ce-102">Comprobación de los parámetros de configuración</span><span class="sxs-lookup"><span data-stu-id="b62ce-102">Verify configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b62ce-103">_**Última modificación del tema:** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="b62ce-103">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="b62ce-104">Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet **Get-CsManagementStoreReplicationStatus** de lync Server 2013 en el equipo interno en el que se encuentra el almacén de administración central, o en cualquier equipo unido al dominio en el que se hayan instalado los componentes principales de Lync Server 2013 (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="b62ce-104">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="b62ce-105">Los resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación.</span><span class="sxs-lookup"><span data-stu-id="b62ce-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="b62ce-106">Si es así, ejecute el cmdlet del **Invoke-CsManagementStoreReplication** y deje que la replicación termine antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="b62ce-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

