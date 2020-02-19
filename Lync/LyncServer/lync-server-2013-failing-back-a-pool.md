---
title: 'Lync Server 2013: conmutación por recuperación de un grupo de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e14cca1c42e6e8ab6a0b64c883658cfc5c6a5374
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="12c8a-102">Conmutación por recuperación de un grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12c8a-102">Failing back a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12c8a-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="12c8a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="12c8a-104">Una vez que el grupo que experimentó el desastre está de nuevo en línea (es decir, el Grupo1 en este ejemplo), siga los pasos siguientes para restaurar su implementación al estado de funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="12c8a-104">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="12c8a-p101">Tenga en cuenta que el proceso de conmutación por error tarda en completarse. Como referencia, un grupo de 20.000  usuarios suele tardar 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="12c8a-p101">Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="12c8a-107">Realice la recuperación de los usuarios que estaban hospedados originalmente en el Grupo1 y se han conmutado por error al Grupo2 escribiendo el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="12c8a-107">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="12c8a-108">No es necesario realizar otros.</span><span class="sxs-lookup"><span data-stu-id="12c8a-108">No other steps are necessary.</span></span> <span data-ttu-id="12c8a-109">Si se ha producido un error en el servidor de administración central, puede dejarlo en grupo2.</span><span class="sxs-lookup"><span data-stu-id="12c8a-109">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

