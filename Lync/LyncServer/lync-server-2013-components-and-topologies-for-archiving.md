---
title: 'Lync Server 2013: componentes y topologías para archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec153b237df086f3622acc70c104bddc64fef28a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502617"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="843a8-102">Componentes y topologías para el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="843a8-102">Components and topologies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="843a8-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="843a8-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="843a8-104">Si desea archivar el contenido de mi y Conferencia de Lync Server 2013, puede implementar el archivado en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="843a8-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="843a8-105">Componentes de archivado</span><span class="sxs-lookup"><span data-stu-id="843a8-105">Archiving Components</span></span>

<span data-ttu-id="843a8-106">La característica Archivado incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="843a8-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="843a8-p101">**Agentes de archivado**   Los agentes de archivado (también llamados agentes de colección de datos unificada) se instalan y activan automáticamente en cada grupo de servidores front-end y en el servidor Standard Edition. Aunque los agentes de archivado se activan automáticamente, no se capturan realmente mensajes hasta que se habilite y configure correctamente el archivado.</span><span class="sxs-lookup"><span data-stu-id="843a8-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="843a8-110">**Almacenamiento de datos de archivado**.</span><span class="sxs-lookup"><span data-stu-id="843a8-110">**Archiving data storage**.</span></span> <span data-ttu-id="843a8-111">El almacenamiento de datos para Lync Server 2013 puede ser cualquiera de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="843a8-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="843a8-112">Almacenamiento de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="843a8-112">Exchange 2013 storage.</span></span> <span data-ttu-id="843a8-113">Si habilita la opción de integración de Microsoft Exchange, los buzones de correo de usuario hospedados en el servidor Exchange 2013 usan el almacenamiento de Exchange 2013 para los datos archivados, pero solo si los buzones se han puesto en retención de In-Place.</span><span class="sxs-lookup"><span data-stu-id="843a8-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="843a8-114">Almacenamiento de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="843a8-114">SQL Server storage.</span></span> <span data-ttu-id="843a8-115">Si tiene usuarios en su implementación hospedados en Lync Server 2013, puede configurar las bases de datos de archivado que ejecutan una versión compatible de SQL Server para habilitar el archivado para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="843a8-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="843a8-116">El archivado también requiere almacenamiento de archivos, pero el archivado usa el mismo almacenamiento de archivos que los servidores front-end o que el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="843a8-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="843a8-117">Para obtener una lista de requisitos de hardware y software para el archivado, consulte Supported [hardware for Lync server 2013](lync-server-2013-supported-hardware.md) y [Server Software and Infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="843a8-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="843a8-118">Topologías admitidas</span><span class="sxs-lookup"><span data-stu-id="843a8-118">Supported Topologies</span></span>

<span data-ttu-id="843a8-119">Implemente el archivado en cada grupo que tenga usuarios que requieran compatibilidad de archivado.</span><span class="sxs-lookup"><span data-stu-id="843a8-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="843a8-120">El archivado se ejecuta en los servidores front-end de los grupos de servidores Enterprise Edition y en los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="843a8-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="843a8-121">El almacenamiento de datos de archivado puede ser el siguiente:</span><span class="sxs-lookup"><span data-stu-id="843a8-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="843a8-122">Integrada con el almacenamiento de Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="843a8-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="843a8-123">Implementación mediante bases de datos de SQL Server independientes</span><span class="sxs-lookup"><span data-stu-id="843a8-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="843a8-124">Si su implementación de Exchange 2013 no incluye a todos los usuarios de su implementación de Lync Server, debe usar la integración de Microsoft Exchange para los usuarios cuyos buzones se encuentran en servidores de Exchange 2013 y debe implementar bases de datos de SQL Server independientes para el resto de los usuarios de Lync que se vayan a usar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="843a8-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="843a8-125">Escenarios de instalación compatibles</span><span class="sxs-lookup"><span data-stu-id="843a8-125">Supported Collocation</span></span>

<span data-ttu-id="843a8-126">Lync Server 2013 admite una amplia variedad de escenarios de combinación, lo que le permite ahorrarse los costos de hardware mediante la ejecución de varios componentes en un servidor (si tiene una organización pequeña) o para ejecutar componentes individuales en diferentes servidores (si tiene una organización más grande que necesita escalabilidad y rendimiento).</span><span class="sxs-lookup"><span data-stu-id="843a8-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="843a8-127">Los factores de escalabilidad se deben tener en cuenta antes de decidir si los componentes se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="843a8-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="843a8-128">El archivado se implementa en los servidores front-end de un grupo de servidores o servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="843a8-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="843a8-129">Para obtener más información sobre los componentes que se pueden combinar allí, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="843a8-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="843a8-130">Si usa bases de datos de SQL Server independientes para el archivado, en lugar de integrar el almacenamiento con el almacenamiento de Exchange 2013, puede combinar la base de datos de archivado con cualquiera de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="843a8-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="843a8-131">Base de datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="843a8-131">Monitoring database</span></span>

  - <span data-ttu-id="843a8-132">Base de datos back-end de un grupo de servidores front-end de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="843a8-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="843a8-p108">El servidor que hospeda la base de datos de archivado puede hospedar otras bases de datos. Sin embargo, si piensa combinar la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer mucho. Por este motivo, no se recomienda la combinación de la base de datos de archivado con la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="843a8-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="843a8-136">Si combina la base de datos de archivado con la base de datos de supervisión, la base de datos back-end, o con ambas, puede usar una sola instancia de SQL para cualquiera de las bases de datos o pude usar una instancia SQL independiente para cada base de datos, con la siguiente limitación:</span><span class="sxs-lookup"><span data-stu-id="843a8-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="843a8-137">Cada instancia de SQL puede contener únicamente una sola base de datos back-end, una sola base de datos de supervisión y una sola base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="843a8-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="843a8-138">Para obtener más información sobre la combinación de todos los roles de servidor y las bases de datos, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="843a8-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

