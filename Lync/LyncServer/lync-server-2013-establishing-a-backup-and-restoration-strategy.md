---
title: 'Lync Server 2013: establecer una estrategia de copia de seguridad y restauración'
description: 'Lync Server 2013: establecer una estrategia de copia de seguridad y restauración.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fdefed873d1fd69d82f8ecebceeb92f06f65f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555046"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="78081-103">Establecimiento de una estrategia de copia de seguridad y restauración para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78081-103">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78081-104">_**Última modificación del tema:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="78081-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="78081-105">Antes de poder desarrollar un plan de copia de seguridad y restauración para Lync Server, debe desarrollar una estrategia que se ajuste a los objetivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="78081-105">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="78081-106">Para desarrollar una estrategia eficaz de copia de seguridad y restauración, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="78081-106">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="78081-107">Establecer prioridades empresariales.</span><span class="sxs-lookup"><span data-stu-id="78081-107">Establish business priorities.</span></span>

  - <span data-ttu-id="78081-108">Identificar los requisitos de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="78081-108">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="78081-109">Establecer las prioridades profesionales</span><span class="sxs-lookup"><span data-stu-id="78081-109">Establishing Business Priorities</span></span>

<span data-ttu-id="78081-p102">Evaluar las prioridades profesionales de la organización. Normalmente, las principales prioridades profesionales que afectan a la estrategia de copia de seguridad y restauración son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="78081-p102">Evaluate the business priorities of your organization. Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="78081-112">Requisitos de continuidad profesionales</span><span class="sxs-lookup"><span data-stu-id="78081-112">Business continuity requirements</span></span>

  - <span data-ttu-id="78081-113">Precisión de los datos</span><span class="sxs-lookup"><span data-stu-id="78081-113">Data completeness</span></span>

  - <span data-ttu-id="78081-114">Importancia de los datos</span><span class="sxs-lookup"><span data-stu-id="78081-114">Data criticality</span></span>

  - <span data-ttu-id="78081-115">Requisitos de portabilidad</span><span class="sxs-lookup"><span data-stu-id="78081-115">Portability requirements</span></span>

  - <span data-ttu-id="78081-116">Restricciones de costos</span><span class="sxs-lookup"><span data-stu-id="78081-116">Cost constraints</span></span>

<span data-ttu-id="78081-117">Necesidades empresariales como estas le ayudarán a determinar los contratos de nivel de servicio (SLA) que desarrolle con sus clientes.</span><span class="sxs-lookup"><span data-stu-id="78081-117">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="78081-118">Los contratos de nivel de servicio tienen una gran influencia en la estrategia de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="78081-118">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="78081-119">Identificar los requisitos de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="78081-119">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="78081-120">Las prioridades empresariales y los contratos de nivel de servicio actúan en la determinación de los requisitos de la organización para realizar copias de seguridad y restaurar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78081-120">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="78081-121">Identifique y documente los requisitos para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78081-121">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="78081-122">**Frecuencia de las copias de seguridad**     Para obtener más información sobre los procedimientos recomendados para la frecuencia de copia de seguridad, consulte [Best Practices for Backup and restore for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="78081-122">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="78081-123">Herramientas de copia **de seguridad y restauración**     Incluya quién va a usar las herramientas y en qué equipos.</span><span class="sxs-lookup"><span data-stu-id="78081-123">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="78081-124">Para obtener más información acerca de las herramientas descritas en este tema y los permisos necesarios, consulte [Backup and restore requirements in Lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="78081-124">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="78081-125">Ubicación de copia de **seguridad**     Identifique si las copias de seguridad se conservan de forma local o remota, teniendo en cuenta la seguridad y la accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="78081-125">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="78081-126">Especifique los medios que se utilizarán para las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="78081-126">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="78081-127">Requisitos de hardware **y software**     Identifique y documente los requisitos de hardware y software específicos, incluido el hardware para el almacenamiento de copias de seguridad y la restauración de componentes específicos y cualquier conectividad de software y red necesaria para admitir la copia de seguridad y la restauración.</span><span class="sxs-lookup"><span data-stu-id="78081-127">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="78081-128">A medida que desarrolle sus requisitos de hardware y software, tenga en cuenta los distintos escenarios de restauración que se exponen a continuación.</span><span class="sxs-lookup"><span data-stu-id="78081-128">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="78081-129">**Escenarios**     de restauración Estos son los procesos de restauración de los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="78081-129">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="78081-130">Un grupo de Lync Server produce errores.</span><span class="sxs-lookup"><span data-stu-id="78081-130">A Lync Server pool fails.</span></span> <span data-ttu-id="78081-131">Este escenario requiere volver a generar cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="78081-131">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="78081-132">Se produce un error en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="78081-132">A Standard Edition server fails.</span></span> <span data-ttu-id="78081-133">Este escenario requiere volver a generar el servidor en un equipo nuevo o limpio y restaurar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="78081-133">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="78081-134">Pérdida del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="78081-134">Loss of the Central Management store.</span></span> <span data-ttu-id="78081-135">Como mínimo, este escenario requiere restaurar y publicar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="78081-135">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="78081-136">Pérdida de un servidor back-end cuando el almacén de administración central sigue funcionando con normalidad.</span><span class="sxs-lookup"><span data-stu-id="78081-136">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="78081-137">Este escenario requiere volver a generar el servidor en un equipo nuevo o limpio y restaurar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="78081-137">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="78081-138">Se produce un error en un servidor que es miembro de un grupo de servidores de Lync.</span><span class="sxs-lookup"><span data-stu-id="78081-138">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="78081-139">Este escenario requiere volver a generar el servidor en un equipo nuevo o limpio.</span><span class="sxs-lookup"><span data-stu-id="78081-139">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="78081-140">Se produce un error en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="78081-140">A File Store fails.</span></span> <span data-ttu-id="78081-141">Este escenario requiere restaurar el servidor de archivos o el clúster de archivos.</span><span class="sxs-lookup"><span data-stu-id="78081-141">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="78081-142">Se produce un error en una base de datos de archivado, supervisión o chat persistente.</span><span class="sxs-lookup"><span data-stu-id="78081-142">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="78081-143">Este escenario requiere volver a crear las bases de datos y, si los datos son esenciales para la organización, restaurar los datos.</span><span class="sxs-lookup"><span data-stu-id="78081-143">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="78081-144">El archivado, la supervisión y los datos del chat persistente no son necesarios para que la copia de seguridad y la ejecución de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78081-144">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

