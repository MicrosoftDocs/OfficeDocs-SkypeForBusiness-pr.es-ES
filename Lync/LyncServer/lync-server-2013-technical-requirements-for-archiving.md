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
ms.openlocfilehash: c388fd04ba7600aa28a142961cd5ac07f63ae7c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="210c4-102">Requisitos técnicos para el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="210c4-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="210c4-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="210c4-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="210c4-104">Los requisitos técnicos de Lync Server 2013 incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="210c4-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="210c4-105">Requisitos de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="210c4-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="210c4-106">Software como requisito previo que debe estar instalado para el archivado.</span><span class="sxs-lookup"><span data-stu-id="210c4-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="210c4-107">Requisitos de almacenamiento de datos para el archivado.</span><span class="sxs-lookup"><span data-stu-id="210c4-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="210c4-108">Requisitos y consideraciones de escalado para su implementación de archivado.</span><span class="sxs-lookup"><span data-stu-id="210c4-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="210c4-109">Requisitos y consideraciones de rendimiento para sus bases de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="210c4-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="210c4-110">La información de escala y rendimiento no está disponible en esta versión 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="210c4-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="210c4-111">Requisitos de infraestructura</span><span class="sxs-lookup"><span data-stu-id="210c4-111">Infrastructure Requirements</span></span>

<span data-ttu-id="210c4-112">Los requisitos de la infraestructura de archivado de 2013 de Lync Server son los mismos que para la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="210c4-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="210c4-113">Para obtener más información, consulte [determining Your Infrastructure Requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="210c4-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="210c4-114">Requisitos previos de archivado</span><span class="sxs-lookup"><span data-stu-id="210c4-114">Archiving Prerequisites</span></span>

<span data-ttu-id="210c4-115">Lync Server 2013 optimiza los requisitos previos para el archivado debido a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="210c4-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="210c4-p102">El servidor de archivado ya no es un rol de servidor. En su lugar, los agentes de la colección de datos unificada se ejecutan en los servidores front-end en un grupo de servidores y en servidores Standard Edition para capturar datos de archivado, por lo que no debe configurar plataformas de sistema independientes para el archivado.</span><span class="sxs-lookup"><span data-stu-id="210c4-p102">Archiving Server is no longer a server role. Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="210c4-118">El archivado usa el almacenamiento de archivos de Lync Server 2013 para el almacenamiento temporal de los archivos de contenido de reuniones, por lo que no se configura un almacén de archivos independiente para el archivado.</span><span class="sxs-lookup"><span data-stu-id="210c4-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="210c4-119">En Lync Server 2013, no se requiere Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="210c4-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="210c4-120">Requisitos de almacenamiento de datos para el archivado</span><span class="sxs-lookup"><span data-stu-id="210c4-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="210c4-p103">De manera adicional, debe configurar la infraestructura de almacenamiento de archivado. Esto incluye uno o ambos de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="210c4-p103">Additionally, you need to set up the infrastructure for Archiving storage. This includes one or both of the following:</span></span>

  - <span data-ttu-id="210c4-123">**Almacenamiento de Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="210c4-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="210c4-124">Los archivos de contenido de las reuniones, como las presentaciones de PowerPoint, se archivan como datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="210c4-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="210c4-125">Si desea usar la integración de Microsoft Exchange para que los datos de archivo de Lync se almacenen con datos de cumplimiento de Exchange, debe usar Exchange 2013 para la implementación de Exchange y asegurarse de que el tamaño máximo de almacenamiento admita el almacenamiento de los archivos de contenido de la reunión.</span><span class="sxs-lookup"><span data-stu-id="210c4-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="210c4-126">Si implementa el archivado con la opción de integración de Microsoft Exchange, los datos de archivo de Lync se almacenan con los datos de cumplimiento de Exchange 2013 solo para los usuarios hospedados en los servidores de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="210c4-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="210c4-127">Debe implementar Exchange 2013 antes de implementar y habilitar el archivado con la opción de integración de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="210c4-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="210c4-128">Si decide usar el almacenamiento de Exchange 2013, no es necesario que implemente bases de datos de SQL Server independientes para el archivado, a menos que tenga usuarios de Lync que no estén hospedados en los servidores de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="210c4-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="210c4-129">**Almacenamiento de base de datos de SQL Server para archivado**.</span><span class="sxs-lookup"><span data-stu-id="210c4-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="210c4-130">Para admitir usuarios que no están hospedados en servidores de Exchange 2013 o si no desea usar la opción de integración de Microsoft Exchange, debe implementar el almacenamiento de archivado con una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="210c4-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="210c4-131">Lync Server 2013 admite las siguientes versiones de 64 bits de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="210c4-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="210c4-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="210c4-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="210c4-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="210c4-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="210c4-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="210c4-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="210c4-135">Microsoft SQL Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="210c4-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="210c4-136">Microsoft SQL Server 2008 R2 Express y Microsoft SQL Server 2012 Express no son compatibles con el archivado.</span><span class="sxs-lookup"><span data-stu-id="210c4-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="210c4-137">no se admiten las versiones de 32 bits de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="210c4-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="210c4-138">Para obtener más información sobre las restricciones y los requisitos adicionales de SQL Server, consulte <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> en la documentación de planeación o en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="210c4-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="210c4-139">Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="210c4-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="210c4-140">Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="210c4-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="210c4-141">También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación.</span><span class="sxs-lookup"><span data-stu-id="210c4-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="210c4-142">Para obtener más información acerca de SQL Server, vea SQL Server [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)TechCenter en.</span><span class="sxs-lookup"><span data-stu-id="210c4-142">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

