---
title: 'Lync Server 2013: preparar la infraestructura y los sistemas'
description: 'Lync Server 2013: preparar la infraestructura y los sistemas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfabdda9d117af1534578c8543f9ce72808d5a53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579996"
---
# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="187ea-103">Preparación de la infraestructura y los sistemas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="187ea-103">Preparing the infrastructure and systems for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="187ea-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="187ea-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="187ea-105">La implementación de Lync Server 2013 requiere el uso del generador de topologías para definir y publicar el diseño de la topología.</span><span class="sxs-lookup"><span data-stu-id="187ea-105">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="187ea-106">Para identificar los componentes necesarios para la topología, use el generador de topologías para crear y guardar el diseño de la topología.</span><span class="sxs-lookup"><span data-stu-id="187ea-106">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="187ea-107">Antes de publicar la topología en el generador de topologías, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="187ea-107">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="187ea-108">Adquirir e instalar el hardware para cada componente en el diseño de la topología que creó y guardó mediante el generador de topologías, incluidos todos los equipos necesarios (servidores que ejecutan Lync Server 2013, servidores de bases de datos, servidores que ejecutan Internet Information Services (IIS) y servidores de proxy inverso, según corresponda), adaptadores de red, equilibradores de carga de hardware y dispositivos</span><span class="sxs-lookup"><span data-stu-id="187ea-108">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="187ea-109">Para obtener información detallada sobre cómo definir una topología que especifique los componentes necesarios para la implementación, consulte [Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="187ea-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="187ea-110">Para obtener más información sobre los requisitos de hardware para los servidores, consulte [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="187ea-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="187ea-111">Asegúrese de que la infraestructura de red cumple los requisitos.</span><span class="sxs-lookup"><span data-stu-id="187ea-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="187ea-112">Para obtener más información, consulte [requisitos de la infraestructura de red para Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="187ea-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="187ea-113">Configurar los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="187ea-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="187ea-114">Para publicar y habilitar la topología, necesita los servidores internos que se van a representar mediante cuentas de equipo en AD DS.</span><span class="sxs-lookup"><span data-stu-id="187ea-114">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="187ea-115">Esto se consigue uniendo los equipos a AD DS.</span><span class="sxs-lookup"><span data-stu-id="187ea-115">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="187ea-116">Para obtener información detallada sobre la preparación de AD DS, consulte [preparación de los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="187ea-116">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="187ea-117">Cree un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="187ea-117">Create a file share.</span></span> <span data-ttu-id="187ea-118">Los servidores Standard Edition pueden hospedar el recurso compartido de archivos para el archivo requerido, mientras que en una implementación empresarial no se puede hospedar el recurso compartido de archivos en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="187ea-118">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="187ea-119">Los permisos y pertenencias a grupos necesarios para implementar y establecer la lista de control de acceso (ACL) en la carpeta y el recurso compartido deben configurarse correctamente para que el generador de topología finalice correctamente.</span><span class="sxs-lookup"><span data-stu-id="187ea-119">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="187ea-120">Debe asegurarse de que la persona que ejecuta Topology Builder tiene los siguientes permisos y pertenencias a grupos:</span><span class="sxs-lookup"><span data-stu-id="187ea-120">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="187ea-121">Miembro de administradores locales</span><span class="sxs-lookup"><span data-stu-id="187ea-121">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="187ea-122">Miembro de usuarios de dominio</span><span class="sxs-lookup"><span data-stu-id="187ea-122">Member of Domain Users</span></span>
    
      - <span data-ttu-id="187ea-123">Control total sobre el recurso compartido y la carpeta del almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="187ea-123">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="187ea-124">Para Enterprise Edition, instale y Configure SQL Server.</span><span class="sxs-lookup"><span data-stu-id="187ea-124">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="187ea-125">Para que el programa de instalación de SQL Server funcione correctamente, el servidor basado en SQL Server debe estar en línea y la persona que publica la topología debe ser un administrador local en SQL Server y debe ser miembro del grupo sysadmin de SQL Server en la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="187ea-125">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="187ea-126">Una vez completadas todas las tareas de preparación descritas en este tema, pero antes de publicar la topología, también debe realizar el resto de tareas de preparación, incluida la instalación de los sistemas operativos Windows y otro software necesario como requisito previo, la instalación de IIS y la configuración de DNS.</span><span class="sxs-lookup"><span data-stu-id="187ea-126">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="187ea-127">Para obtener más información sobre estas tareas, vea [requisitos del sistema para servidores que ejecutan Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [configurar IIS para Lync Server 2013](lync-server-2013-configure-iis.md)y [preparar la infraestructura y los sistemas para Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="187ea-127">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="187ea-128">Asimismo, debe familiarizarse con los clientes y los requisitos de los clientes.</span><span class="sxs-lookup"><span data-stu-id="187ea-128">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="187ea-129">Para obtener más información, consulte [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="187ea-129">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="187ea-130">En esta sección</span><span class="sxs-lookup"><span data-stu-id="187ea-130">In This Section</span></span>

  - [<span data-ttu-id="187ea-131">Configuración de hardware para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="187ea-131">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="187ea-132">Configuración de software de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="187ea-132">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="187ea-133">Preparación de los servicios de dominio de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="187ea-133">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="187ea-134">Configuración de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="187ea-134">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="187ea-135">Configurar registros DNS en Lync Server 2013 para un grupo de servidores front-end o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="187ea-135">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="187ea-136">Instalación de las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="187ea-136">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

