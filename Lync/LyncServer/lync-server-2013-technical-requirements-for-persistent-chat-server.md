---
title: 'Lync Server 2013: requisitos técnicos para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba8e3e02efeddc1229d3616c0cdcaf4ca241bf24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42024411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="d8c5a-102">Requisitos técnicos para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8c5a-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8c5a-103">_**Última modificación del tema:** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="d8c5a-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="d8c5a-104">Cada equipo que hospede el servidor de chat persistente debe tener acceso a una topología existente de Lync Server 2013 con los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="d8c5a-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="d8c5a-105">**Lync Server 2013, servidor front-end.**  El servidor front-end es la base del enrutamiento del Protocolo de inicio de sesión (SIP), que hace posible la comunicación entre equipos que ejecutan el servidor de chat persistente y la funcionalidad de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="d8c5a-106">Antes de empezar a implementar el servidor de chat persistente, Compruebe la implementación de Lync Server 2013, Standard Edition o un grupo de servidores front-end de Lync Server y cualquier otro equipo interno que ejecute Lync Server, según corresponda a su organización.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="d8c5a-107">En las secciones siguientes se describen los requisitos específicos para el servidor de chat persistente y la base de datos que almacena los datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="d8c5a-108">Requisitos del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d8c5a-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="d8c5a-109">Para obtener información detallada sobre el hardware recomendado para la implementación de Lync Server y la versión más reciente del servidor de chat persistente, vea [plataformas de hardware de servidor para Lync server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="d8c5a-110">Para obtener más información sobre la compatibilidad del sistema operativo de servidor y herramientas con Lync Server y el servidor de chat persistente, consulte [Server and Tools Operating System support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="d8c5a-111">Para obtener más información sobre el software adicional necesario para implementar el servidor de chat persistente, vea la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="d8c5a-112">Requisitos previos del software del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d8c5a-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c5a-113">Software</span><span class="sxs-lookup"><span data-stu-id="d8c5a-113">Software</span></span></th>
<th><span data-ttu-id="d8c5a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8c5a-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c5a-115">Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="d8c5a-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="d8c5a-116">Lo usa el servidor de chat persistente y el servicio de cumplimiento de chat persistente, si se implementan.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="d8c5a-117">Requisitos de la base de datos del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d8c5a-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="d8c5a-118">El servidor de chat persistente usa la base de datos de chat persistente para almacenar los datos del historial de chats, la configuración y el aprovisionamiento de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="d8c5a-119">Opcionalmente, usa la base de datos de cumplimiento de chat persistente para almacenar datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d8c5a-120">La base de datos de chat persistente (MGC) y la base de datos de cumplimiento (mgccomp) pueden encontrarse en la misma instancia de SQL Server o en diferentes servidores SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="d8c5a-121">Para preparar una plataforma de servidor de base de datos, asegúrese de que cada equipo cumple los requisitos de hardware y, a continuación, instale el software necesario como requisito previo.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="d8c5a-122">La plataforma de servidor para los servidores de base de datos de chat persistente requiere el mismo hardware que el servidor de base de datos back-end de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="d8c5a-123">Para obtener más información, consulte [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="d8c5a-124">En el servidor de bases de datos, asegúrese de que esté instalada una de las siguientes aplicaciones de software:</span><span class="sxs-lookup"><span data-stu-id="d8c5a-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="d8c5a-125">Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="d8c5a-126">Para obtener más información sobre cómo instalar Microsoft SQL Server 2012, consulte "instalar SQL Server 2012" [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)en.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="d8c5a-127">Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="d8c5a-128">Para obtener más información sobre cómo instalar Microsoft SQL Server 2008 R2, vea "instalación de SQL Server (SQL Server 2008 R2) [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)" en.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="d8c5a-129">Requisitos de certificados del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d8c5a-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="d8c5a-130">Para obtener información detallada acerca de la adquisición de certificados, la creación de la base de datos de SQL Server y la creación de almacenes de archivos, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d8c5a-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

