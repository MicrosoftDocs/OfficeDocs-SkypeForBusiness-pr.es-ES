---
title: 'Lync Server 2013: realización de una conmutación por error de grupo de servidores front-end ABC'
description: 'Lync Server 2013: realización de una conmutación por error de grupo de servidores front-end ABC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing an ABC Front End pool failover
ms:assetid: 81ecd26d-49e3-4c72-a66e-02748efb513b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945637(v=OCS.15)
ms:contentKeyID: 51541489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c1aa7a18bc1f1126bcb942a0b3a21283637dcb6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557226"
---
# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="a4c8d-103">Realizar la conmutación por error de un grupo de servidores front-end ABC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4c8d-103">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4c8d-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a4c8d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a4c8d-105">En los dos temas de esta sección se describe el procedimiento para realizar una conmutación por error del grupo de ABC en Lync Server 2013, donde hay grupos de servidores front-end de Lync Server emparejados A y B, y el grupo A no es recuperable.</span><span class="sxs-lookup"><span data-stu-id="a4c8d-105">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="a4c8d-106">Mediante este procedimiento, se crea un nuevo grupo de servidores front-end C con un nuevo nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="a4c8d-106">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="a4c8d-107">El grupo C se construye a partir de la información del grupo A al que se produjo un error. El procedimiento también incluye el emparejamiento entre grupos B y C.</span><span class="sxs-lookup"><span data-stu-id="a4c8d-107">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="a4c8d-108">Requisitos previos de copia de seguridad para la conmutación por error del grupo ABC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4c8d-108">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="a4c8d-109">Procedimiento de conmutación por error ABC del grupo de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4c8d-109">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

