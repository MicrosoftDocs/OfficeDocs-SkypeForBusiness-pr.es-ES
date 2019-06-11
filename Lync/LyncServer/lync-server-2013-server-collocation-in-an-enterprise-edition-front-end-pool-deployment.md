---
title: 'Lync Server 2013: Colocación de un servidor en una implementación de grupo de servidores front-end Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="d5636-102">Colocación de un servidor en una implementación de grupo de servidores front-end Enterprise Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5636-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5636-103">_**Última modificación del tema:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="d5636-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="d5636-104">En esta sección se describen los roles de servidor, las bases de datos y los recursos compartidos de archivos que puede Collocate en una implementación de grupo front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5636-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="d5636-105">Roles de servidor</span><span class="sxs-lookup"><span data-stu-id="d5636-105">Server Roles</span></span>

<span data-ttu-id="d5636-106">En Lync Server 2013, el servicio de conferencia A/V, el servicio de mediación, la supervisión y el archivado se colocan en el servidor front-end, pero se necesita una configuración adicional para habilitarlos.</span><span class="sxs-lookup"><span data-stu-id="d5636-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="d5636-107">Si no desea Collocate el servidor de mediación con el servidor front-end, puede implementarlo como un servidor de mediación independiente en un equipo independiente.</span><span class="sxs-lookup"><span data-stu-id="d5636-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="d5636-108">Puede Collocate un servidor de aplicaciones de confianza con el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d5636-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="d5636-109">Los siguientes roles de servidor deben implementarse en un equipo independiente:</span><span class="sxs-lookup"><span data-stu-id="d5636-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="d5636-110">Director</span><span class="sxs-lookup"><span data-stu-id="d5636-110">Director</span></span>

  - <span data-ttu-id="d5636-111">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d5636-111">Edge Server</span></span>

  - <span data-ttu-id="d5636-112">Servidor de mediación (si no se ha puesto en el servidor front-end)</span><span class="sxs-lookup"><span data-stu-id="d5636-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="d5636-113">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="d5636-113">Office Web Apps Server</span></span>

<span data-ttu-id="d5636-114">No puede Collocate rol de servidor de chat persistente con el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d5636-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="d5636-115">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="d5636-115">Databases</span></span>

<span data-ttu-id="d5636-116">Puede Collocate cada una de las siguientes bases de datos en el mismo servidor de base de datos:</span><span class="sxs-lookup"><span data-stu-id="d5636-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="d5636-117">Base de datos back-end</span><span class="sxs-lookup"><span data-stu-id="d5636-117">Back-end database</span></span>

  - <span data-ttu-id="d5636-118">Base de datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="d5636-118">Monitoring database</span></span>

  - <span data-ttu-id="d5636-119">Base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="d5636-119">Archiving database</span></span>

  - <span data-ttu-id="d5636-120">Base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d5636-120">Persistent Chat database</span></span>

  - <span data-ttu-id="d5636-121">Base de datos de cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d5636-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="d5636-122">Puede Collocate cualquiera de estas bases de datos o cualquiera de ellas en una sola instancia de SQL Server o usar una instancia independiente de SQL Server para cada una, con las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="d5636-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="d5636-123">Cada instancia de SQL Server puede contener una única base de datos back-end, una única base de datos de supervisión, una única base de datos de archivado, una única base de datos de chat persistente y una única base de datos de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d5636-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="d5636-124">El servidor de base de datos no admite más de un grupo de servidores front-end, una implementación de archivado y una implementación de supervisión, pero puede admitir una de cada uno, independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias independientes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d5636-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="d5636-125">Puede Collocate un recurso compartido de archivos con las bases de datos, tal y como se describe más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="d5636-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5636-126">En Lync Server 2013, tiene la opción de integrar el almacenamiento de archivado con el almacenamiento de Exchange 2013 para algunos o todos los usuarios de su implementación.</span><span class="sxs-lookup"><span data-stu-id="d5636-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="d5636-127">No se pueden implementar servidores que ejecuten servidores o componentes de Lync en los mismos servidores que el almacenamiento de Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5636-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5636-128">Aunque se admite la collocation de bases de datos, el tamaño de las bases de datos puede crecer rápidamente.</span><span class="sxs-lookup"><span data-stu-id="d5636-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="d5636-129">Por ejemplo, cuando considere collocating la base de datos de archivado con otras bases de datos, tenga en cuenta que si está archivando los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer muy grande.</span><span class="sxs-lookup"><span data-stu-id="d5636-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="d5636-130">Por este motivo, no recomendamos que collocating varias bases de datos, especialmente la base de datos de archivado, la base de datos de chat persistente o la base de datos de cumplimiento de chat persistente con la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="d5636-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="d5636-131">Recurso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="d5636-131">File Share</span></span>

<span data-ttu-id="d5636-132">El recurso compartido de archivos puede ser un servidor independiente o se puede incluir en el mismo servidor que cualquiera de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5636-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="d5636-133">Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="d5636-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="d5636-134">Base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="d5636-134">Archiving database</span></span>

  - <span data-ttu-id="d5636-135">Base de datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="d5636-135">Monitoring database</span></span>

  - <span data-ttu-id="d5636-136">Base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d5636-136">Persistent Chat database</span></span>

  - <span data-ttu-id="d5636-137">Base de datos de cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d5636-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="d5636-138">Un solo recurso compartido de archivos se puede usar para varios grupos front-end, servidores Standard Edition (todos en el mismo sitio).</span><span class="sxs-lookup"><span data-stu-id="d5636-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5636-139">En Lync Server 2013, la supervisión y el archivado usan el recurso compartido de archivos de Lync Server como servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d5636-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="d5636-140">Otros componentes</span><span class="sxs-lookup"><span data-stu-id="d5636-140">Other Components</span></span>

<span data-ttu-id="d5636-141">No se puede Collocate un servidor proxy inverso, que no es un componente de 2013 de Lync Server, pero es necesario en la implementación si desea permitir el uso compartido de contenido web para usuarios federados con cualquier rol de servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5636-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="d5636-142">Sin embargo, puede implementar el soporte de proxy inverso para una implementación de Lync Server 2013 al configurar la compatibilidad en un servidor proxy inverso existente de su organización que se usa para otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d5636-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="d5636-143">No puede Collocate ningún componente de mensajería unificada (UM) de Exchange o componente de SharePoint con ningún rol de servidor de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5636-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

