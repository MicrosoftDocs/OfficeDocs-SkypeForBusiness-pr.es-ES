---
title: 'Fase 10: retirar el sitio heredado'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a8a2871659747b68e7a0dec6a945c6f987219a8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533767"
---
# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="055f7-102">Fase 10: retirar el sitio heredado</span><span class="sxs-lookup"><span data-stu-id="055f7-102">Phase 10: Decommission legacy site</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="055f7-103">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="055f7-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="055f7-104">En los siguientes temas se proporcionan instrucciones para retirar grupos de servidores y desactivar y quitar servidores y grupos de servidores de una implementación heredada de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="055f7-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="055f7-105">No todos los procedimientos de esta sección son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="055f7-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="055f7-106">Lea la información en cada uno de estos temas para averiguar qué procedimiento de retirada debe usar.</span><span class="sxs-lookup"><span data-stu-id="055f7-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="055f7-107">Si ha importado directorios de conferencia para las conferencias de acceso telefónico local a Lync Server 2013, es importante que cambie la propiedad del directorio de conferencia a Lync Server 2013 antes de empezar a retirar los grupos.</span><span class="sxs-lookup"><span data-stu-id="055f7-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="055f7-108">Si retira un grupo sin haber trasladado la propiedad de los directorios de conferencia, no funcionará más la característica de acceso telefónico para todas las reuniones migradas.</span><span class="sxs-lookup"><span data-stu-id="055f7-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="055f7-109">Debe realizar el traslado de la propiedad una vez para cada directorio de conferencia del grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="055f7-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="055f7-110">Para obtener información sobre la migración y actualización de aplicaciones de la API administrada de comunicaciones unificadas de Microsoft (UCMA) antes de retirar el entorno heredado, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="055f7-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="055f7-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="055f7-111">In This Section</span></span>

  - [<span data-ttu-id="055f7-112">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="055f7-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="055f7-113">Actualizar registros SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="055f7-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="055f7-114">Retirar servidores y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="055f7-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="055f7-115">Quitar BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="055f7-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

