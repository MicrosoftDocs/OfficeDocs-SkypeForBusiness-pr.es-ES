---
title: Lync Server 2013 Server combinación en una implementación de servidor Standard Edition
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
ms.openlocfilehash: 428f666ade00d2f809f25cb7eb9ef1525d7f835c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="6934e-102">Combinación de servidor en una implementación de servidor Standard Edition para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6934e-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6934e-103">_**Última modificación del tema:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="6934e-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="6934e-104">En esta sección se describen los roles de servidor, las bases de datos y los recursos compartidos de archivos que puede combinar en una implementación de servidor de Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6934e-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="6934e-105">Roles de servidor</span><span class="sxs-lookup"><span data-stu-id="6934e-105">Server Roles</span></span>

<span data-ttu-id="6934e-106">En Lync Server 2013, el servicio de conferencia A/V, el servicio de mediación, la supervisión y el archivado están combinados en el servidor Standard Edition, pero se requiere una configuración adicional para habilitarlos.</span><span class="sxs-lookup"><span data-stu-id="6934e-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="6934e-107">Puede implementar el servicio de mediación en servidores distintos.</span><span class="sxs-lookup"><span data-stu-id="6934e-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="6934e-108">Puede recopilar un servidor de aplicaciones de confianza con el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6934e-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="6934e-109">Cada uno de los siguientes roles de servidor deben implementarse en un equipo aparte:</span><span class="sxs-lookup"><span data-stu-id="6934e-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="6934e-110">Dirección</span><span class="sxs-lookup"><span data-stu-id="6934e-110">Director</span></span>

  - <span data-ttu-id="6934e-111">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="6934e-111">Edge Server</span></span>

  - <span data-ttu-id="6934e-112">Servidor de mediación (si no se combina con el servidor de Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="6934e-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="6934e-113">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="6934e-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="6934e-114">Databases</span><span class="sxs-lookup"><span data-stu-id="6934e-114">Databases</span></span>

<span data-ttu-id="6934e-115">De manera predeterminada, la base de datos back-end de SQL Server Express se combina con el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6934e-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="6934e-116">No se puede mover a otro equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="6934e-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="6934e-117">Con una excepción, no puede combinar otras bases de datos en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6934e-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="6934e-118">Si opta por implementar el servidor de chat persistente en un servidor Standard Edition, puede combinar la base de datos de chat persistente y la base de datos de cumplimiento de chat persistente en el mismo servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6934e-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="6934e-119">Se puede combinar cada una de las siguientes bases de datos en un único servidor de base de datos:</span><span class="sxs-lookup"><span data-stu-id="6934e-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="6934e-120">Base de datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="6934e-120">Monitoring database</span></span>

  - <span data-ttu-id="6934e-121">Base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="6934e-121">Archiving database</span></span>

  - <span data-ttu-id="6934e-122">Una base de datos back-end para un grupo de servidores front-end de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="6934e-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="6934e-123">Se puede combinar cualquiera de estas bases de datos, o todas ellas, en una única instancia de SQL o usar una instancia de SQL diferente para cada una, con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="6934e-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="6934e-124">Cada instancia de SQL puede contener únicamente una base de datos back-end (para un grupo de servidores front-end de Enterprise Edition), una sola base de datos de supervisión, una sola base de datos de archivado, una sola base de datos de chat persistente o una sola base de datos de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6934e-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="6934e-125">El servidor de base de datos no admite más de un grupo de servidores front-end Enterprise Edition, un servidor que ejecuta el archivado, un servidor que ejecuta la supervisión, una base de datos de chat persistente y una base de datos de cumplimiento de chat persistente, pero puede admitir uno de cada uno de ellos. independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias independientes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6934e-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="6934e-126">Se puede combinar un recurso compartido de archivos con las bases de datos, como se describe más adelante en este sección.</span><span class="sxs-lookup"><span data-stu-id="6934e-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6934e-127">En Lync Server 2013, tiene la opción de integrar el almacenamiento de la supervisión y el archivado con el almacenamiento de Exchange 2013 para algunos o todos los usuarios de la implementación.</span><span class="sxs-lookup"><span data-stu-id="6934e-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="6934e-128">No se pueden implementar servidores que ejecuten Lync Server o componentes en los mismos servidores que el almacenamiento de Exchange.</span><span class="sxs-lookup"><span data-stu-id="6934e-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6934e-129">Aunque se admite la combinación de las bases de datos, el tamaño de estas puede crecer rápidamente.</span><span class="sxs-lookup"><span data-stu-id="6934e-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="6934e-130">Por ejemplo, si considera la combinación de la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede aumentar considerablemente.</span><span class="sxs-lookup"><span data-stu-id="6934e-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="6934e-131">Por este motivo, no se recomienda combinar varias bases de datos, especialmente la base de datos de archivado, la base de datos de chat persistente y la base de datos de cumplimiento de chat persistente con la base de datos back-end de un grupo de servidores Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6934e-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="6934e-132">Recursos compartidos de archivos</span><span class="sxs-lookup"><span data-stu-id="6934e-132">File Shares</span></span>

<span data-ttu-id="6934e-133">El recurso compartido de archivo puede ser un servidor aparte o se puede combinar en el mismo servidor que cualquiera de los siguientes, o todos ellos:</span><span class="sxs-lookup"><span data-stu-id="6934e-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="6934e-134">Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front-end de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="6934e-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="6934e-135">Base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="6934e-135">Archiving database</span></span>

  - <span data-ttu-id="6934e-136">Base de datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="6934e-136">Monitoring database</span></span>

  - <span data-ttu-id="6934e-137">Base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="6934e-137">Persistent Chat database</span></span>

  - <span data-ttu-id="6934e-138">Base de datos de cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="6934e-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="6934e-139">Un solo recurso compartido de archivos se puede usar para varios grupos de servidores front-end y servidores de Standard Edition (todos ellos en el mismo sitio).</span><span class="sxs-lookup"><span data-stu-id="6934e-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6934e-140">En Lync Server 2013, la supervisión y el archivado usan el recurso compartido de archivos de Lync Server como servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6934e-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="6934e-141">Otros componentes</span><span class="sxs-lookup"><span data-stu-id="6934e-141">Other Components</span></span>

<span data-ttu-id="6934e-142">No puede combinar un servidor de proxy inverso, que no es un componente 2013 de Lync Server, pero es necesario en su implementación si desea admitir el uso compartido de contenido web para los usuarios federados con cualquier rol de servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6934e-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="6934e-143">Sin embargo, puede implementar la compatibilidad con proxy inverso para una implementación de Lync Server 2013 mediante la configuración de la compatibilidad en un servidor proxy inverso existente en su organización que se usa para otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6934e-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="6934e-144">No puede combinar ningún componente de mensajería unificada de Exchange o componente de SharePoint con ningún rol de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6934e-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

