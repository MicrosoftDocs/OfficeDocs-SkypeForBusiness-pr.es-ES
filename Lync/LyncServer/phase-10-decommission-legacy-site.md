---
title: 'Fase 10: retirar el sitio heredado'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3140e3529ec9e4c48ca41c26963f833f89d9f929
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="f96d0-102">Fase 10: retirar el sitio heredado</span><span class="sxs-lookup"><span data-stu-id="f96d0-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f96d0-103">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f96d0-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f96d0-104">En los siguientes temas se proporcionan instrucciones para retirar grupos de servidores y desactivar y quitar servidores y grupos de servidores de una implementación heredada de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f96d0-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="f96d0-105">No todos los procedimientos de esta sección son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="f96d0-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="f96d0-106">Lea la información en cada uno de estos temas para averiguar qué procedimiento de retirada debe usar.</span><span class="sxs-lookup"><span data-stu-id="f96d0-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f96d0-107">Si ha importado directorios de conferencia para las conferencias de acceso telefónico local a Lync Server 2013, es importante que cambie la propiedad del directorio de conferencia a Lync Server 2013 antes de empezar a retirar los grupos.</span><span class="sxs-lookup"><span data-stu-id="f96d0-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="f96d0-108">Si retira un grupo sin haber trasladado la propiedad de los directorios de conferencia, no funcionará más la característica de acceso telefónico para todas las reuniones migradas.</span><span class="sxs-lookup"><span data-stu-id="f96d0-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="f96d0-109">Debe realizar el traslado de la propiedad una vez para cada directorio de conferencia del grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="f96d0-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f96d0-110">Para obtener información sobre la migración y actualización de aplicaciones de la API administrada de comunicaciones unificadas de Microsoft (UCMA) antes de retirar el entorno heredado, consulte<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="f96d0-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f96d0-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f96d0-111">In This Section</span></span>

  - [<span data-ttu-id="f96d0-112">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="f96d0-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="f96d0-113">Actualizar registros DNS SRV</span><span class="sxs-lookup"><span data-stu-id="f96d0-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="f96d0-114">Retirar servidores y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="f96d0-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="f96d0-115">Quitar BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="f96d0-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

