---
title: 'Lync Server 2013: nuevas características de la aplicación de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4ae3ad427164d8a948130e69fd54d1e6f8c37b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536857"
---
# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="c518a-102">Nuevas características de aplicación de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c518a-102">New Response Group application features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c518a-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c518a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c518a-104">La aplicación de grupo de respuesta permite enrutar y poner en cola llamadas entrantes para personas designadas para fines especiales, como el servicio al cliente, un servicio de asistencia interno o un teléfono general de asistencia para un departamento.</span><span class="sxs-lookup"><span data-stu-id="c518a-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="c518a-105">Las siguientes características de la aplicación de grupo de respuesta son nuevas en Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="c518a-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="c518a-106">**Rol de administrador**</span><span class="sxs-lookup"><span data-stu-id="c518a-106">**Manager role**</span></span>
    
    <span data-ttu-id="c518a-107">Lync Server 2013 presenta un nuevo rol de administrador de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c518a-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="c518a-108">Ahora hay dos funciones de administración para los grupos de respuesta: administrador del grupo de respuesta y administrador del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c518a-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="c518a-109">Mientras que los administradores de grupos de respuesta pueden seguir configurando cualquier elemento para cualquier grupo de respuesta, los administradores pueden configurar únicamente determinados elementos sólo para los grupos de respuesta de los que son propietarios.</span><span class="sxs-lookup"><span data-stu-id="c518a-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="c518a-110">Esta mejora en el modelo de administración beneficia la escalabilidad del grupo de respuesta, especialmente en los escenarios de grandes implementaciones.</span><span class="sxs-lookup"><span data-stu-id="c518a-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="c518a-111">**Alta disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="c518a-111">**High availability**</span></span>
    
    <span data-ttu-id="c518a-112">La compatibilidad de alta disponibilidad para la aplicación de grupo de respuesta, en forma de reflejo de SQL Server, está habilitada como parte de la configuración general e implementación de alta disponibilidad para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c518a-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="c518a-113">Si configura para alta disponibilidad y pierde la conectividad con el servidor back-end principal, el aprovechamiento del servidor reflejado no afecta a las funciones del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c518a-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="c518a-114">La compatibilidad con la creación de reflejos de SQL Server para la aplicación de grupo de respuesta no se puede habilitar o configurar de forma individual fuera de la configuración general de alta disponibilidad de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c518a-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="c518a-115">**Recuperación ante desastres**</span><span class="sxs-lookup"><span data-stu-id="c518a-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="c518a-116">La compatibilidad de recuperación ante desastres para la aplicación de grupo de respuesta está habilitada como parte de la configuración e implementación de los grupos de servidores front-end emparejados, que forman parte de la configuración general de recuperación ante desastres de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c518a-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="c518a-117">Además, los cmdlets de importación y exportación de grupos de respuesta admiten el proceso de conmutación por error al grupo de copia de seguridad y el proceso de conmutación por recuperación al grupo principal o a un nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="c518a-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="c518a-118">Si se produce una interrupción en el grupo principal, los grupos de respuesta pueden conmutarse por error al grupo de copia de seguridad y luego conmutarse por recuperación al grupo principal o a un nuevo grupo cuando finalice la interrupción.</span><span class="sxs-lookup"><span data-stu-id="c518a-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c518a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c518a-119">See Also</span></span>


[<span data-ttu-id="c518a-120">Planeación de grupos de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c518a-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

