---
title: 'Lync Server 2013: establecimiento de una estrategia de copia de seguridad y restauración'
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
ms.openlocfilehash: 5ee1a13667e28ad374f538d61f6cfd941d31fade
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="52f27-102">Establecer una estrategia de copia de seguridad y restauración para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52f27-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52f27-103">_**Última modificación del tema:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="52f27-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="52f27-104">Para poder desarrollar un plan de copia de seguridad y restauración de Lync Server, necesita desarrollar una estrategia que se ajuste a los objetivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="52f27-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="52f27-105">Para desarrollar una estrategia de copia de seguridad y restauración eficaz, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="52f27-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="52f27-106">Establecer prioridades empresariales.</span><span class="sxs-lookup"><span data-stu-id="52f27-106">Establish business priorities.</span></span>

  - <span data-ttu-id="52f27-107">Identifique los requisitos de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="52f27-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="52f27-108">Establecer prioridades empresariales</span><span class="sxs-lookup"><span data-stu-id="52f27-108">Establishing Business Priorities</span></span>

<span data-ttu-id="52f27-109">Evaluar las prioridades empresariales de su organización.</span><span class="sxs-lookup"><span data-stu-id="52f27-109">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="52f27-110">Normalmente, las prioridades empresariales principales que afectan a la copia de seguridad y la estrategia de restauración son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="52f27-110">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="52f27-111">Requisitos de continuidad empresarial</span><span class="sxs-lookup"><span data-stu-id="52f27-111">Business continuity requirements</span></span>

  - <span data-ttu-id="52f27-112">Integridad de los datos</span><span class="sxs-lookup"><span data-stu-id="52f27-112">Data completeness</span></span>

  - <span data-ttu-id="52f27-113">Criticidad de los datos</span><span class="sxs-lookup"><span data-stu-id="52f27-113">Data criticality</span></span>

  - <span data-ttu-id="52f27-114">Requisitos de portabilidad</span><span class="sxs-lookup"><span data-stu-id="52f27-114">Portability requirements</span></span>

  - <span data-ttu-id="52f27-115">Restricciones de costo</span><span class="sxs-lookup"><span data-stu-id="52f27-115">Cost constraints</span></span>

<span data-ttu-id="52f27-116">Necesidades empresariales, como estas ayudan a determinar los contratos de nivel de servicio (SLA) que usted desarrolla con sus clientes.</span><span class="sxs-lookup"><span data-stu-id="52f27-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="52f27-117">Los acuerdos de nivel de servicio influyen considerablemente en su estrategia de copia de seguridad y recuperación.</span><span class="sxs-lookup"><span data-stu-id="52f27-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="52f27-118">Identificar los requisitos de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="52f27-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="52f27-119">Las prioridades empresariales y los acuerdos de nivel de servicio actúan en la determinación de los requisitos de las organizaciones para realizar copias de seguridad y restaurar el servidor de Lync.</span><span class="sxs-lookup"><span data-stu-id="52f27-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="52f27-120">Identifique y documente sus requisitos para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52f27-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="52f27-121">**Frecuencia de las copias**   de seguridad para obtener detalles sobre los procedimientos recomendados para la frecuencia de copia de seguridad, vea [procedimientos recomendados para copias de seguridad y restauración de Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="52f27-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="52f27-122">\*\*\*\*   Entre las herramientas de copia de seguridad y restauración se incluye quién va a usar las herramientas y en qué equipos.</span><span class="sxs-lookup"><span data-stu-id="52f27-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="52f27-123">Para obtener más información sobre las herramientas descritas en este tema y los permisos necesarios, consulte [requisitos de copia de seguridad y restauración en Lync Server 2013: herramientas y permisos](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="52f27-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="52f27-124">**Ubicación**   de la copia de seguridad identifique si las copias de seguridad se guardan de forma local o remota, teniendo en cuenta la seguridad y la accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="52f27-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="52f27-125">Especifique el medio que se va a usar para las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="52f27-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="52f27-126">**Los requisitos**   de hardware y software identifican y documentan los requisitos específicos de hardware y software, incluido el hardware para el almacenamiento de copias de seguridad y la restauración de componentes específicos y cualquier software y conectividad de red necesarios para admitir la copia de seguridad y la restauración.</span><span class="sxs-lookup"><span data-stu-id="52f27-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="52f27-127">A medida que desarrolla los requisitos de hardware y software, tenga en cuenta los distintos escenarios de restauración que siguen.</span><span class="sxs-lookup"><span data-stu-id="52f27-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="52f27-128">**Escenarios de restauración**   a continuación se muestran los procesos de restauración de los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="52f27-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="52f27-129">Se produce un error en un grupo de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52f27-129">A Lync Server pool fails.</span></span> <span data-ttu-id="52f27-130">Este escenario requiere que se Recompile cada servidor del grupo.</span><span class="sxs-lookup"><span data-stu-id="52f27-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="52f27-131">Se produce un error en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="52f27-131">A Standard Edition server fails.</span></span> <span data-ttu-id="52f27-132">Este escenario requiere que se recompile el servidor en un equipo nuevo o limpio, y el restore de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="52f27-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="52f27-133">Pérdida del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="52f27-133">Loss of the Central Management store.</span></span> <span data-ttu-id="52f27-134">Como mínimo, este escenario requiere restaurar y publicar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="52f27-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="52f27-135">Pérdida de un servidor back-end cuando el almacén de administración central sigue funcionando con normalidad.</span><span class="sxs-lookup"><span data-stu-id="52f27-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="52f27-136">Este escenario requiere que se recompile el servidor en un equipo nuevo o limpio, y el restore de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="52f27-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="52f27-137">Se produce un error en un servidor que es miembro de un grupo de servidores de Lync.</span><span class="sxs-lookup"><span data-stu-id="52f27-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="52f27-138">Este escenario requiere que se recompile el servidor en un equipo nuevo o limpio.</span><span class="sxs-lookup"><span data-stu-id="52f27-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="52f27-139">Se produce un error en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="52f27-139">A File Store fails.</span></span> <span data-ttu-id="52f27-140">Este escenario requiere restaurar el servidor de archivos o el clúster de archivos.</span><span class="sxs-lookup"><span data-stu-id="52f27-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="52f27-141">Se produce un error en un archivo, supervisión o base de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="52f27-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="52f27-142">Este escenario requiere volver a crear las bases de datos y, si los datos son críticos para su organización, restaurar los datos.</span><span class="sxs-lookup"><span data-stu-id="52f27-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="52f27-143">El archivado, la supervisión y los datos persistentes del chat no son necesarios para obtener la copia de seguridad y la ejecución de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52f27-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

