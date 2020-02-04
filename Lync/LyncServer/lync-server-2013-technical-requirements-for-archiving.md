---
title: 'Lync Server 2013: requisitos técnicos para el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cc8a64ee7a49971660e7435a51c816bd4367e26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="d65b7-102">Requisitos técnicos para archivar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d65b7-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d65b7-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="d65b7-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="d65b7-104">Entre los requisitos técnicos de Lync Server 2013 se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d65b7-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="d65b7-105">Requisitos de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="d65b7-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="d65b7-106">Requisitos previos de software que deben instalarse para el archivado.</span><span class="sxs-lookup"><span data-stu-id="d65b7-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="d65b7-107">Requisitos de almacenamiento de datos para archivar.</span><span class="sxs-lookup"><span data-stu-id="d65b7-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="d65b7-108">Las consideraciones y los requisitos de escalado para la implementación de archivado.</span><span class="sxs-lookup"><span data-stu-id="d65b7-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="d65b7-109">Consideraciones y requisitos de rendimiento para las bases de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="d65b7-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d65b7-110">La información de escalabilidad y rendimiento no está disponible en esta versión 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d65b7-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="d65b7-111">Requisitos de infraestructura</span><span class="sxs-lookup"><span data-stu-id="d65b7-111">Infrastructure Requirements</span></span>

<span data-ttu-id="d65b7-112">Los requisitos de la infraestructura de archivado de Lync Server 2013 son los mismos que para la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d65b7-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="d65b7-113">Para obtener más información, consulte [determinar los requisitos de infraestructura para Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="d65b7-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="d65b7-114">Requisitos previos de archivado</span><span class="sxs-lookup"><span data-stu-id="d65b7-114">Archiving Prerequisites</span></span>

<span data-ttu-id="d65b7-115">Lync Server 2013 optimiza los requisitos previos para el archivado debido a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d65b7-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="d65b7-116">El servidor de archivado ya no es un rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="d65b7-116">Archiving Server is no longer a server role.</span></span> <span data-ttu-id="d65b7-117">En su lugar, los agentes de recopilación de datos unificados se ejecutan en los servidores front-end de un grupo de servidores y servidores Standard Edition para capturar datos para su archivado, por lo que no se configuran plataformas de sistema independientes para archivar.</span><span class="sxs-lookup"><span data-stu-id="d65b7-117">Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="d65b7-118">El archivado usa el almacenamiento de archivos de Lync Server 2013 para almacenar temporalmente los archivos de contenido de la reunión, por lo que no se configura un almacén de archivos independiente para archivado.</span><span class="sxs-lookup"><span data-stu-id="d65b7-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="d65b7-119">En Lync Server 2013, no se necesita Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="d65b7-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="d65b7-120">Requisitos de almacenamiento de datos para archivar</span><span class="sxs-lookup"><span data-stu-id="d65b7-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="d65b7-121">Además, debe configurar la infraestructura para archivar el almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d65b7-121">Additionally, you need to set up the infrastructure for Archiving storage.</span></span> <span data-ttu-id="d65b7-122">Esto incluye una o ambas de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d65b7-122">This includes one or both of the following:</span></span>

  - <span data-ttu-id="d65b7-123">**Almacenamiento de Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="d65b7-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="d65b7-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span><span class="sxs-lookup"><span data-stu-id="d65b7-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="d65b7-125">Si desea usar la integración de Microsoft Exchange para que los datos del archivo de Lync se almacenen con datos de cumplimiento de Exchange, debe usar Exchange 2013 para su implementación de Exchange y asegurarse de que el tamaño máximo de almacenamiento admita el almacenamiento de los archivos de contenido de la reunión.</span><span class="sxs-lookup"><span data-stu-id="d65b7-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="d65b7-126">Si implementa el archivado con la opción de integración de Microsoft Exchange, los datos del archivo de Lync se almacenan con los datos de cumplimiento de Exchange 2013 solo para los usuarios alojados en los servidores de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d65b7-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="d65b7-127">Debe implementar Exchange 2013 antes de implementar y habilitar el archivado mediante la opción de integración de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="d65b7-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="d65b7-128">Si elige usar el almacenamiento de Exchange 2013, no necesita implementar bases de datos de SQL Server independientes para archivar, a menos que tenga usuarios de Lync que no estén alojados en los servidores de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d65b7-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="d65b7-129">**Almacenamiento de base de datos de SQL Server para archivar**.</span><span class="sxs-lookup"><span data-stu-id="d65b7-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="d65b7-130">Para admitir usuarios que no están alojados en servidores de Exchange 2013, o si no desea usar la opción de integración de Microsoft Exchange, debe implementar el almacenamiento de archivado con una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d65b7-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="d65b7-131">Lync Server 2013 admite las siguientes versiones de 64 bits de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="d65b7-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="d65b7-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d65b7-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="d65b7-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="d65b7-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="d65b7-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d65b7-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="d65b7-135">Microsoft SQL Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="d65b7-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d65b7-136">Microsoft SQL Server 2008 R2 Express y Microsoft SQL Server 2012 Express no son compatibles con el archivado.</span><span class="sxs-lookup"><span data-stu-id="d65b7-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="d65b7-137">no se admiten las versiones de 32 bits de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d65b7-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="d65b7-138">Para obtener más información sobre restricciones y requisitos de SQL Server, consulte <A href="lync-server-2013-database-software-support.md">compatibilidad de software de base de datos en Lync Server 2013</A> en la documentación de planeación o en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="d65b7-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="d65b7-139">Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="d65b7-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="d65b7-140">Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="d65b7-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="d65b7-141">También puede crear la base de datos más adelante, incluyendo como parte del procedimiento de instalación.</span><span class="sxs-lookup"><span data-stu-id="d65b7-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="d65b7-142">Para obtener más información sobre SQL Server, consulte SQL Server TechCenter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)en.</span><span class="sxs-lookup"><span data-stu-id="d65b7-142">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

