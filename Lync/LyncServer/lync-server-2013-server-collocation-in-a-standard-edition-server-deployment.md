---
title: 'Lync Server 2013: Colocación de un servidor en una implementación de servidores de Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fa25655fd9bdd2551e10d1fbbf0de617b89be64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="adb4f-102">Colocación de un servidor en una implementación de servidores de Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adb4f-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adb4f-103">_**Última modificación del tema:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="adb4f-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="adb4f-104">En esta sección se describen los roles de servidor, las bases de datos y los recursos compartidos de archivos que puede Collocate en una implementación de servidor Standard Edition de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="adb4f-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="adb4f-105">Roles de servidor</span><span class="sxs-lookup"><span data-stu-id="adb4f-105">Server Roles</span></span>

<span data-ttu-id="adb4f-106">En Lync Server 2013, el servicio conferencia A/V, servicio de mediación, supervisión y archivado están colocados en el servidor Standard Edition, pero se necesita una configuración adicional para habilitarlos.</span><span class="sxs-lookup"><span data-stu-id="adb4f-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="adb4f-107">Puede implementar el servicio de mediación en servidores diferentes.</span><span class="sxs-lookup"><span data-stu-id="adb4f-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="adb4f-108">Puede Collocate un servidor de aplicaciones de confianza con un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="adb4f-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="adb4f-109">Los siguientes roles de servidor deben implementarse en un equipo independiente:</span><span class="sxs-lookup"><span data-stu-id="adb4f-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="adb4f-110">Director</span><span class="sxs-lookup"><span data-stu-id="adb4f-110">Director</span></span>

  - <span data-ttu-id="adb4f-111">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="adb4f-111">Edge Server</span></span>

  - <span data-ttu-id="adb4f-112">Servidor de mediación (si no se ha puesto en el servidor Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="adb4f-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="adb4f-113">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="adb4f-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="adb4f-114">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="adb4f-114">Databases</span></span>

<span data-ttu-id="adb4f-115">De forma predeterminada, la base de datos back-end de SQL Server Express se encuentra en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="adb4f-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="adb4f-116">No puedes moverlo a otro equipo.</span><span class="sxs-lookup"><span data-stu-id="adb4f-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="adb4f-117">Con una excepción, no se pueden Collocate otras bases de datos en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="adb4f-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="adb4f-118">Si elige implementar un servidor de chat persistente en un servidor Standard Edition, puede Collocate la base de datos de chat persistente y la base de datos de cumplimiento de chat persistente en el mismo servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="adb4f-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="adb4f-119">Puede Collocate cada una de las siguientes bases de datos en un único servidor de base de datos:</span><span class="sxs-lookup"><span data-stu-id="adb4f-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="adb4f-120">Base de datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="adb4f-120">Monitoring database</span></span>

  - <span data-ttu-id="adb4f-121">Base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="adb4f-121">Archiving database</span></span>

  - <span data-ttu-id="adb4f-122">Una base de datos back-end para un grupo de servidores front end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="adb4f-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="adb4f-123">Puede Collocate cualquiera de estas bases de datos, o cualquiera de ellas, en una única instancia de SQL o usar una instancia de SQL diferente para cada una, con las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="adb4f-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="adb4f-124">Cada instancia de SQL puede contener una única base de datos back-end (para un grupo de servidores front end Enterprise Edition), una única base de datos de supervisión, una base de datos de archivado única, una base de datos de chat persistente y una única base de datos de cumplimiento persistente.</span><span class="sxs-lookup"><span data-stu-id="adb4f-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="adb4f-125">El servidor de base de datos no es compatible con más de un grupo de servidores front-end Enterprise Edition, un servidor que ejecuta el archivado, un servidor que ejecuta supervisión, una base de datos de chat persistente y una única base de datos de cumplimiento persistente, pero puede admitir una de cada uno. independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias independientes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="adb4f-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="adb4f-126">Puede Collocate un recurso compartido de archivos con las bases de datos, tal y como se describe más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="adb4f-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="adb4f-127">En Lync Server 2013, tiene la opción de integrar el almacenamiento de supervisión y archivado con el almacenamiento de Exchange 2013 para algunos o todos los usuarios de su implementación.</span><span class="sxs-lookup"><span data-stu-id="adb4f-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="adb4f-128">No se pueden implementar servidores que ejecuten servidores o componentes de Lync en los mismos servidores que el almacenamiento de Exchange.</span><span class="sxs-lookup"><span data-stu-id="adb4f-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="adb4f-129">Aunque se admite la collocation de bases de datos, el tamaño de las bases de datos puede crecer rápidamente.</span><span class="sxs-lookup"><span data-stu-id="adb4f-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="adb4f-130">Por ejemplo, cuando considere collocating la base de datos de archivado con otras bases de datos, tenga en cuenta que si está archivando los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer muy grande.</span><span class="sxs-lookup"><span data-stu-id="adb4f-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="adb4f-131">Por este motivo, no recomendamos que collocating varias bases de datos, especialmente la base de datos de archivado, la base de datos de chat persistente y la base de datos de cumplimiento persistente con la base de datos back-end de un grupo de empresas.</span><span class="sxs-lookup"><span data-stu-id="adb4f-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="adb4f-132">Archivos compartidos</span><span class="sxs-lookup"><span data-stu-id="adb4f-132">File Shares</span></span>

<span data-ttu-id="adb4f-133">El recurso compartido de archivos puede ser un servidor independiente o se puede incluir en el mismo servidor que cualquiera de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="adb4f-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="adb4f-134">Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="adb4f-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="adb4f-135">Base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="adb4f-135">Archiving database</span></span>

  - <span data-ttu-id="adb4f-136">Base de datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="adb4f-136">Monitoring database</span></span>

  - <span data-ttu-id="adb4f-137">Base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="adb4f-137">Persistent Chat database</span></span>

  - <span data-ttu-id="adb4f-138">Base de datos de cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="adb4f-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="adb4f-139">Un solo recurso compartido de archivos se puede usar para varios grupos front-end, servidores Standard Edition (todos en el mismo sitio).</span><span class="sxs-lookup"><span data-stu-id="adb4f-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="adb4f-140">En Lync Server 2013, la supervisión y el archivado usan el recurso compartido de archivos de Lync Server como servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="adb4f-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="adb4f-141">Otros componentes</span><span class="sxs-lookup"><span data-stu-id="adb4f-141">Other Components</span></span>

<span data-ttu-id="adb4f-142">No se puede Collocate un servidor proxy inverso, que no es un componente de 2013 de Lync Server, pero es necesario en la implementación si desea permitir el uso compartido de contenido web para usuarios federados con cualquier rol de servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="adb4f-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="adb4f-143">Sin embargo, puede implementar el soporte de proxy inverso para una implementación de Lync Server 2013 al configurar la compatibilidad en un servidor proxy inverso existente de su organización que se usa para otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="adb4f-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="adb4f-144">No puede Collocate ningún componente de mensajería unificada de Exchange o componente de SharePoint con ningún rol de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="adb4f-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

