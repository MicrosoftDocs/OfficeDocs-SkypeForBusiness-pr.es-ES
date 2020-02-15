---
title: 'Lync Server 2013: configuración del almacenamiento para el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a3633ee21fc26fe21557731ece31cf5a0bbb171
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="556f9-102">Configurar el almacenamiento para el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556f9-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="556f9-103">_**Última modificación del tema:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="556f9-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="556f9-104">El almacenamiento de archivado para Lync Server 2013 incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="556f9-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="556f9-105">\*\*\*\*   El almacenamiento de datos de almacenamiento de datos es necesario para almacenar el contenido de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="556f9-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="556f9-106">\*\*\*\*   El almacenamiento de archivos de almacenamiento de archivos es necesario para almacenar la Conferencia (reunión) almacenamiento de datos de contenido y almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="556f9-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="556f9-107">Configuración de almacenamiento de datos</span><span class="sxs-lookup"><span data-stu-id="556f9-107">Setting Up Data Storage</span></span>

<span data-ttu-id="556f9-108">Los requisitos para configurar el almacenamiento de datos para el archivado en Lync Server 2013 dependen de cómo desea almacenar los datos de archivado:</span><span class="sxs-lookup"><span data-stu-id="556f9-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="556f9-109">Integre el archivado de Lync Server 2013 con su implementación de Exchange para almacenar datos de archivado con el almacenamiento de Exchange.</span><span class="sxs-lookup"><span data-stu-id="556f9-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="556f9-110">Configurar servidores de base de datos de SQL Server independientes para almacenar los datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="556f9-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="556f9-111">Configuración de almacenamiento de Exchange para datos de archivado</span><span class="sxs-lookup"><span data-stu-id="556f9-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="556f9-112">La configuración de Exchange para el almacenamiento de datos de archivado requiere que la implementación de Exchange ejecute Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="556f9-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="556f9-113">Además, los buzones de correo de los usuarios deben estar hospedados en el servidor de Exchange 2013 y sus buzones se deben poner en conservación local.</span><span class="sxs-lookup"><span data-stu-id="556f9-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="556f9-114">Para obtener más información acerca de la configuración de Exchange 2013, consulte la documentación del producto de Exchange.</span><span class="sxs-lookup"><span data-stu-id="556f9-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="556f9-115">Configuración de servidores de bases de datos de SQL Server para el almacenamiento de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="556f9-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="556f9-116">El archivado en Lync Server 2013 requiere que el software de base de datos de SQL Server almacene los datos archivados, a menos que integre la implementación de con Exchange.</span><span class="sxs-lookup"><span data-stu-id="556f9-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="556f9-117">Para las bases de datos de archivado de SQL Server, debe instalar SQL Server en el equipo que va a hospedar la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="556f9-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="556f9-118">Puede usar la misma instancia de SQL que usa para la base de datos de back-end de un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="556f9-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="556f9-119">Para un mejor rendimiento, debe implementar la base de datos de archivado en un equipo que sea independiente del Almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="556f9-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="556f9-120">Para obtener más información sobre los componentes de combinar Lync Server 2013, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="556f9-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="556f9-121">Cada servidor de bases de datos debe ejecutar una versión compatible de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="556f9-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="556f9-122">Para obtener más información sobre las versiones compatibles, consulte [Technical Requirements for archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="556f9-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="556f9-123">Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="556f9-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="556f9-124">Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="556f9-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="556f9-125">También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación.</span><span class="sxs-lookup"><span data-stu-id="556f9-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="556f9-126">Para obtener más información acerca de SQL Server, vea SQL Server [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)TechCenter en.</span><span class="sxs-lookup"><span data-stu-id="556f9-126">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="556f9-127">Asegúrese de que el tipo de inicio del servicio Agente SQL Server es automático y de que el servicio Agente SQL Server se está ejecutando para la instancia de SQL que contiene la base de datos de archivado, de modo que el trabajo de mantenimiento de SQL Server de archivado predeterminado se pueda ejecutar de acuerdo a su programación en el control del servicio Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="556f9-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="556f9-128">Configuración de almacenamiento de archivos</span><span class="sxs-lookup"><span data-stu-id="556f9-128">Setting Up File Storage</span></span>

<span data-ttu-id="556f9-129">El archivado usa el recurso compartido de archivos 2013 de Lync Server que especificó al configurar el grupo de servidores front-end o el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="556f9-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="556f9-130">No se puede cambiar el recurso compartido de archivos usado para el archivado.</span><span class="sxs-lookup"><span data-stu-id="556f9-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="556f9-131">Para obtener más información sobre los sistemas de almacenamiento de archivos compatibles, consulte [File Storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="556f9-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

