---
title: Lync Server 2013 Server combinación en una implementación de grupo de servidores front-end Enterprise Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74afcdd9212ebced9d93f0f699b90dd7a89edefd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="b12c0-102">Servidor combinación en una implementación de grupo de servidores front-end Enterprise Edition para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b12c0-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b12c0-103">_**Última modificación del tema:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="b12c0-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="b12c0-104">En esta sección se describen los roles de servidor, las bases de datos y los recursos compartidos de archivos que puede combinar en una implementación de grupo de servidores front-end 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b12c0-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="b12c0-105">Roles de servidor</span><span class="sxs-lookup"><span data-stu-id="b12c0-105">Server Roles</span></span>

<span data-ttu-id="b12c0-106">En Lync Server 2013, el servicio de conferencia A/V, el servicio de mediación, la supervisión y el archivado se combinan en el servidor front-end, pero se requiere una configuración adicional para habilitarlos.</span><span class="sxs-lookup"><span data-stu-id="b12c0-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="b12c0-107">Si no desea recopilar el servidor de mediación con el servidor front-end, puede implementarlo como un servidor de mediación independiente en un equipo individual.</span><span class="sxs-lookup"><span data-stu-id="b12c0-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="b12c0-108">Puede recopilar un servidor de aplicaciones de confianza con el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b12c0-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="b12c0-109">Cada uno de los siguientes roles debe implementarse en un equipo separado:</span><span class="sxs-lookup"><span data-stu-id="b12c0-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="b12c0-110">Dirección</span><span class="sxs-lookup"><span data-stu-id="b12c0-110">Director</span></span>

  - <span data-ttu-id="b12c0-111">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b12c0-111">Edge Server</span></span>

  - <span data-ttu-id="b12c0-112">Servidor de mediación (si no se combina con el servidor front-end)</span><span class="sxs-lookup"><span data-stu-id="b12c0-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="b12c0-113">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="b12c0-113">Office Web Apps Server</span></span>

<span data-ttu-id="b12c0-114">No puede combinar rol de servidor de chat persistente con el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b12c0-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="b12c0-115">Databases</span><span class="sxs-lookup"><span data-stu-id="b12c0-115">Databases</span></span>

<span data-ttu-id="b12c0-116">Puede combinar cada una de las siguientes bases de datos en el mismo servidor de base de datos:</span><span class="sxs-lookup"><span data-stu-id="b12c0-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="b12c0-117">Base de datos back-end</span><span class="sxs-lookup"><span data-stu-id="b12c0-117">Back-end database</span></span>

  - <span data-ttu-id="b12c0-118">Base de datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="b12c0-118">Monitoring database</span></span>

  - <span data-ttu-id="b12c0-119">Base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="b12c0-119">Archiving database</span></span>

  - <span data-ttu-id="b12c0-120">Base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b12c0-120">Persistent Chat database</span></span>

  - <span data-ttu-id="b12c0-121">Base de datos de cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b12c0-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="b12c0-122">Puede combinar cualquiera de estas bases de datos, o todas ellas, en una sola instancia de SQL Server o usar una instancia independiente de SQL Server para cada una, con las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="b12c0-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="b12c0-123">Cada instancia de SQL Server puede contener una sola base de datos back-end, una sola base de datos de supervisión, una sola base de datos de archivado, una sola base de datos de chat persistente y una única base de datos de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b12c0-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="b12c0-124">El servidor de base de datos no admite más de un grupo de servidores front-end, una implementación de archivado y una implementación de supervisión, pero puede admitir una de cada, independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias independientes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b12c0-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="b12c0-125">Se puede combinar un recurso compartido de archivos con las bases de datos, como se describe más adelante en este sección.</span><span class="sxs-lookup"><span data-stu-id="b12c0-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b12c0-126">En Lync Server 2013, tiene la opción de integrar el almacenamiento de archivado con el almacenamiento de Exchange 2013 para algunos o todos los usuarios de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b12c0-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="b12c0-127">No se pueden implementar servidores que ejecuten Lync Server o componentes en los mismos servidores que el almacenamiento de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b12c0-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b12c0-128">Aunque se admite la combinación de las bases de datos, el tamaño de estas puede crecer rápidamente.</span><span class="sxs-lookup"><span data-stu-id="b12c0-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="b12c0-129">Por ejemplo, si considera la combinación de la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede aumentar considerablemente.</span><span class="sxs-lookup"><span data-stu-id="b12c0-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="b12c0-130">Por este motivo, no se recomienda combinar varias bases de datos, especialmente la base de datos de archivado, la base de datos de chat persistente o la base de datos de cumplimiento de chat persistente con la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="b12c0-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="b12c0-131">Recurso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="b12c0-131">File Share</span></span>

<span data-ttu-id="b12c0-132">El recurso compartido de archivos puede estar en un servidor separado o puede combinarse en el mismo servidor que el de cualquier o todos los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="b12c0-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="b12c0-133">Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front-end de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b12c0-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="b12c0-134">Base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="b12c0-134">Archiving database</span></span>

  - <span data-ttu-id="b12c0-135">Base de datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="b12c0-135">Monitoring database</span></span>

  - <span data-ttu-id="b12c0-136">Base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b12c0-136">Persistent Chat database</span></span>

  - <span data-ttu-id="b12c0-137">Base de datos de cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="b12c0-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="b12c0-138">Un solo recurso compartido de archivos se puede usar para varios grupos de servidores front-end y servidores de Standard Edition (todos ellos en el mismo sitio).</span><span class="sxs-lookup"><span data-stu-id="b12c0-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b12c0-139">En Lync Server 2013, la supervisión y el archivado usan el recurso compartido de archivos de Lync Server como servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b12c0-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="b12c0-140">Otros componentes</span><span class="sxs-lookup"><span data-stu-id="b12c0-140">Other Components</span></span>

<span data-ttu-id="b12c0-141">No puede combinar un servidor de proxy inverso, que no es un componente 2013 de Lync Server, pero es necesario en su implementación si desea admitir el uso compartido de contenido web para los usuarios federados con cualquier rol de servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b12c0-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="b12c0-142">Sin embargo, puede implementar la compatibilidad con proxy inverso para una implementación de Lync Server 2013 mediante la configuración de la compatibilidad en un servidor proxy inverso existente en su organización que se usa para otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b12c0-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="b12c0-143">No puede combinar ningún componente de mensajería unificada (MU) de Exchange ni un componente de SharePoint con ningún rol de servidor de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b12c0-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

