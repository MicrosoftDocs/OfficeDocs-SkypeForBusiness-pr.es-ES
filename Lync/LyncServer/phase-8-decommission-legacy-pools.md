---
title: 'Fase 8: retirar grupos heredados'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 474cc5ee3f508ed5a9069f3e8625bcc6ee451153
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="cfece-102">Fase 8: retirar grupos heredados</span><span class="sxs-lookup"><span data-stu-id="cfece-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfece-103">_**Última modificación del tema:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="cfece-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="cfece-104">En el siguiente tema se proporcionan instrucciones para actualizar entradas DNS, mover el servidor de administración de contenido, retirar grupos de servidores y desactivar y quitar servidores y grupos de servidores de una implementación heredada de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cfece-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="cfece-105">No todos los procedimientos de esta sección son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="cfece-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="cfece-106">Lea la documentación y determine qué procedimiento utilizar.</span><span class="sxs-lookup"><span data-stu-id="cfece-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="cfece-107">Para obtener una cobertura exhaustiva de la eliminación de servidores y roles de servidor de Lync Server 2010, y una guía paso a paso para retirar una implementación de Lync Server 2010, consulte "desinstalar Microsoft Lync Server 2010 y quitar roles de servidor", que se [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)puede descargar en.</span><span class="sxs-lookup"><span data-stu-id="cfece-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cfece-108">Para obtener información sobre la migración y actualización de aplicaciones de la API administrada de comunicaciones unificadas de Microsoft (UCMA) antes de retirar el entorno heredado, consulte<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="cfece-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cfece-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cfece-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="cfece-110">Actualizar registros DNS SRV</span><span class="sxs-lookup"><span data-stu-id="cfece-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="cfece-111">Mover el servidor de administración central de Lync Server 2010 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfece-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="cfece-112">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="cfece-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="cfece-113">Quitar la Asociación del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="cfece-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="cfece-114">Quitar la Asociación del servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="cfece-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="cfece-115">Quitar el servidor front-end Enterprise Edition o el servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="cfece-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="cfece-116">Quitar instancias y bases de datos de SQL Server en el servidor back-end</span><span class="sxs-lookup"><span data-stu-id="cfece-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

