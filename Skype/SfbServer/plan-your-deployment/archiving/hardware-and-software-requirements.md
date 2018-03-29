---
title: Requisitos de hardware y software para el archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 'Resumen: Leer este tema para obtener información acerca de los requisitos de hardware y software para archiving en Skype para Business Server 2015.'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="aaca0-103">Requisitos de hardware y software para el archivado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="aaca0-103">Hardware and software requirements for archiving in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aaca0-104">**Resumen:** Lea este tema para obtener información acerca de los requisitos de hardware y software para archiving en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="aaca0-104">**Summary:** Read this topic to learn about hardware and software requirements for archiving in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="aaca0-105">Skype para archiving empresarial servidor 2015 ahora forma parte de la función de Front-End, por lo que no necesitará instalar a un servidor independiente.</span><span class="sxs-lookup"><span data-stu-id="aaca0-105">Skype for Business Server 2015 archiving is now part of the Front End role, so you do not need to install a separate server.</span></span> <span data-ttu-id="aaca0-106">Sin embargo, debe tener en cuenta los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="aaca0-106">You do, however, need to consider the following requirements:</span></span>
  
- <span data-ttu-id="aaca0-107">Requisitos de infraestructura</span><span class="sxs-lookup"><span data-stu-id="aaca0-107">Infrastructure requirements</span></span>
    
- <span data-ttu-id="aaca0-108">Requisitos previos de software</span><span class="sxs-lookup"><span data-stu-id="aaca0-108">Prerequisite software requirements</span></span>
    
- <span data-ttu-id="aaca0-109">Requisitos de almacenamiento de datos</span><span class="sxs-lookup"><span data-stu-id="aaca0-109">Data storage requirements</span></span>
    
## <a name="infrastructure-requirements"></a><span data-ttu-id="aaca0-110">Requisitos de infraestructura</span><span class="sxs-lookup"><span data-stu-id="aaca0-110">Infrastructure requirements</span></span>

<span data-ttu-id="aaca0-111">Skype para requerimientos de infraestructura de Archiving de Business Server son los mismos que la implementación de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="aaca0-111">Skype for Business Server Archiving infrastructure requirements are the same as for deployment of Skype for Business Server.</span></span> <span data-ttu-id="aaca0-112">Para obtener más información, consulte [requisitos para su Skype para el entorno empresarial](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="aaca0-112">For details, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
## <a name="prerequisite-software-requirements"></a><span data-ttu-id="aaca0-113">Requisitos previos de software</span><span class="sxs-lookup"><span data-stu-id="aaca0-113">Prerequisite software requirements</span></span>

<span data-ttu-id="aaca0-114">Requisitos previos de archiving para Skype para Business Server son más simples que las versiones anteriores de Lync Server por los motivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aaca0-114">Archiving prerequisites for Skype for Business Server are simpler than earlier versions of Lync Server because of the following:</span></span> 
  
- <span data-ttu-id="aaca0-115">Porque ya no es una función de servidor de archivado, no es necesario instalar un servidor independiente para archiving.</span><span class="sxs-lookup"><span data-stu-id="aaca0-115">Because archiving is no longer a server role, you do not need to install a separate server for archiving.</span></span> <span data-ttu-id="aaca0-116">En cambio, los agentes unificados de recolección de datos se instalan y activan de forma automática en cada grupo de servidores front-end Enterprise Edition y en cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="aaca0-116">Instead, Unified Data Collection Agents are installed and activated automatically on every Enterprise Edition Front End pool and every Standard Edition Server.</span></span> <span data-ttu-id="aaca0-117">Necesitará habilitar y publicar la topología de archivado por medio del Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="aaca0-117">You will need to enable and publish your archiving topology by using Topology Builder.</span></span>
    
- <span data-ttu-id="aaca0-118">Archiving utiliza el Skype para almacenamiento de archivos de Business Server para el almacenamiento temporal de reunión archivos de contenido, por lo que no configurar un almacén de archivos independientes para archiving.</span><span class="sxs-lookup"><span data-stu-id="aaca0-118">Archiving uses the Skype for Business Server file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>
    
- <span data-ttu-id="aaca0-119">En Skype para Business Server, Microsoft Message Queue Server no se requiere.</span><span class="sxs-lookup"><span data-stu-id="aaca0-119">In Skype for Business Server, Microsoft Message Queuing is not required.</span></span>
    
## <a name="data-storage-requirements"></a><span data-ttu-id="aaca0-120">Requisitos de almacenamiento de datos</span><span class="sxs-lookup"><span data-stu-id="aaca0-120">Data Storage requirements</span></span>

<span data-ttu-id="aaca0-p104">Es preciso configurar la infraestructura para el almacenamiento del archivado. Esto incluye seleccionar una de las siguientes opciones o ambas:</span><span class="sxs-lookup"><span data-stu-id="aaca0-p104">You will need to set up the infrastructure for archiving storage. This includes choosing one or both of the following options:</span></span>
  
- <span data-ttu-id="aaca0-123">**Almacenamiento de información de Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="aaca0-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="aaca0-124">Los archivos del contenido de reuniones, como las presentaciones de PowerPoint, se archivan como datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="aaca0-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="aaca0-125">Si desea almacenar Skype para archivar datos de negocio con datos de cumplimiento de normas de Exchange, debe utilizar Exchange para la implementación de Exchange y asegúrese de que el tamaño máximo de almacenamiento admite el almacenamiento de los archivos de contenido de la reunión.</span><span class="sxs-lookup"><span data-stu-id="aaca0-125">If you want to store Skype for Business archive data with Exchange compliance data, you must use Exchange for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="aaca0-126">Debe implementar Exchange antes de implementar y habilitar el archivado mediante la opción de integración de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="aaca0-126">You must deploy Exchange prior to deploying and enabling archiving using the Microsoft Exchange integration option.</span></span> 
    
    <span data-ttu-id="aaca0-127">Si decide utilizar el almacenamiento de información de Exchange, no es necesario implementar bases de datos SQL Server independientes para archiving, a menos que tenga Skype para usuarios de negocios que no están alojados en los servidores de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aaca0-127">If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers.</span></span> <span data-ttu-id="aaca0-128">Si implementar archiving mediante la opción de integración de Microsoft Exchange, Skype para archivar datos de negocio se almacena con los datos de cumplimiento de normas de Exchange sólo para los usuarios que están alojados en los servidores de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aaca0-128">If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers.</span></span> 
    
- <span data-ttu-id="aaca0-129">**Skype para el almacenamiento de archiving Business Server**.</span><span class="sxs-lookup"><span data-stu-id="aaca0-129">**Skype for Business Server archiving storage**.</span></span> <span data-ttu-id="aaca0-130">Dar soporte a usuarios que no están alojados en servidores de Exchange, o si no desea utilizar la opción de integración de Microsoft Exchange, debe implementar archiving de almacenamiento utilizando una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aaca0-130">To support users who are not homed on Exchange servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy archiving storage using a SQL Server database.</span></span> <span data-ttu-id="aaca0-131">Skype para Business Server admite las siguientes versiones de 64 bits de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="aaca0-131">Skype for Business Server supports the following 64-bit versions of SQL Server:</span></span>
    
  - <span data-ttu-id="aaca0-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aaca0-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
  - <span data-ttu-id="aaca0-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="aaca0-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
  - <span data-ttu-id="aaca0-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aaca0-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
  - <span data-ttu-id="aaca0-135">Estándar de Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="aaca0-135">Microsoft SQL Server 2012 Standard</span></span>
    
  - <span data-ttu-id="aaca0-136">Microsoft SQL Server Enterprise de 2014</span><span class="sxs-lookup"><span data-stu-id="aaca0-136">Microsoft SQL Server 2014 Enterprise</span></span>
    
  - <span data-ttu-id="aaca0-137">Microsoft SQL Server Standard de 2014</span><span class="sxs-lookup"><span data-stu-id="aaca0-137">Microsoft SQL Server 2014 Standard</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aaca0-138">No se admiten las versiones de Microsoft SQL Server Express para archiving.</span><span class="sxs-lookup"><span data-stu-id="aaca0-138">Microsoft SQL Server Express versions are not supported for archiving.</span></span> <span data-ttu-id="aaca0-139">no se admiten las versiones de 32 bits de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aaca0-139">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="aaca0-140">Para los requisitos de SQL Server y restricciones adicionales, consulte [requisitos para su Skype para el entorno empresarial](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="aaca0-140">For additional SQL Server requirements and restrictions, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
    <span data-ttu-id="aaca0-141">Debe configurar las plataformas SQL Server antes de implementar y habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="aaca0-141">You must set up the SQL Server platforms prior to deploying and enabling archiving.</span></span> <span data-ttu-id="aaca0-142">Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="aaca0-142">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="aaca0-143">También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación.</span><span class="sxs-lookup"><span data-stu-id="aaca0-143">You can also create the database later, included as part of the installation procedure.</span></span> <span data-ttu-id="aaca0-144">Para obtener más información acerca de SQL Server, consulte [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).</span><span class="sxs-lookup"><span data-stu-id="aaca0-144">For details about SQL Server, see the [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).</span></span>
    
    <span data-ttu-id="aaca0-145">El aumento en la carga del archivado puede ser considerable.</span><span class="sxs-lookup"><span data-stu-id="aaca0-145">The load increase for archiving can be significant.</span></span> <span data-ttu-id="aaca0-146">Por lo tanto, debe asegurarse de que es adecuado para servidores frontales archivado está habilitado en el que espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="aaca0-146">Therefore, you should ensure that disk space is adequate for Front End Servers on which archiving is enabled.</span></span>
    

