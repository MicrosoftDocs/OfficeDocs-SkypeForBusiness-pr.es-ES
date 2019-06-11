---
title: 'Lync Server 2013: Preparación de la infraestructura y los sistemas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e724dd3b6105be3f4601c523dbbf558c91ca9f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="e9c2d-102">Preparación de la infraestructura y los sistemas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c2d-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9c2d-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e9c2d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e9c2d-104">La implementación de Lync Server 2013 requiere el uso de Topology Builder para definir y publicar el diseño de la topología.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="e9c2d-105">Para identificar los componentes necesarios para su topología, use el generador de topología para crear y guardar un diseño de topología.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="e9c2d-106">Antes de publicar su topología en el generador de topología, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9c2d-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="e9c2d-107">Adquiera e instale el hardware de cada componente en el diseño de topología que ha creado y guardado mediante el generador de topología, incluidos todos los equipos necesarios (servidores que ejecutan Lync Server 2013, servidores de bases de datos, servidores que ejecutan servicios de Internet Information Server (). IIS), así como servidores proxy inversos, según corresponda), adaptadores de red, equilibradores de carga de hardware y dispositivos de almacenamiento (como servidores de archivos).</span><span class="sxs-lookup"><span data-stu-id="e9c2d-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="e9c2d-108">Para obtener más información sobre cómo definir una topología que especifique los componentes necesarios para su implementación, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="e9c2d-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="e9c2d-109">Para obtener más información sobre los requisitos de hardware para servidores, consulte [hardware compatible para Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="e9c2d-110">Asegúrese de que la infraestructura de red cumpla con los requisitos.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="e9c2d-111">Para obtener más información, consulte [requisitos de infraestructura de red para Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="e9c2d-112">Configurar los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="e9c2d-113">Para publicar y habilitar la topología, necesita que los servidores internos estén representados por cuentas de equipos en AD DS.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="e9c2d-114">Esto se logra al unir los equipos a AD DS.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="e9c2d-115">Para obtener detalles sobre la preparación de AD DS, consulte [preparar los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="e9c2d-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="e9c2d-116">Crear un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-116">Create a file share.</span></span> <span data-ttu-id="e9c2d-117">Los servidores Standard Edition pueden hospedar el recurso compartido de archivos para el archivo requerido, mientras que en una implementación empresarial el recurso compartido de archivos no se puede hospedar en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="e9c2d-118">Los permisos y pertenencias a grupos necesarios para implementar y establecer la lista de control de acceso (ACL) en la carpeta y el recurso compartido deben establecerse correctamente para que el generador de topología se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="e9c2d-119">Debe asegurarse de que la persona que ejecuta el generador de topología tenga los siguientes permisos y pertenencias a grupos:</span><span class="sxs-lookup"><span data-stu-id="e9c2d-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="e9c2d-120">Miembro de administradores locales</span><span class="sxs-lookup"><span data-stu-id="e9c2d-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="e9c2d-121">Miembro de usuarios del dominio</span><span class="sxs-lookup"><span data-stu-id="e9c2d-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="e9c2d-122">Control total sobre el recurso compartido y la carpeta del almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="e9c2d-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="e9c2d-123">Para Enterprise Edition, instale y Configure SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-123">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="e9c2d-124">Para que el programa de instalación de SQL Server funcione correctamente, el servidor basado en SQL Server debe estar en línea y la persona que publica la topología es un administrador local en SQL Server y debe ser miembro del grupo de administradores de SQL Server en la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-124">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="e9c2d-125">Después de completar todas las tareas de preparación según se describe en este tema, pero antes de publicar la topología, también tendrá que realizar otras tareas de preparación, como instalar los sistemas operativos de Windows y otro software necesario, configurar IIS y configuración de DNS.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="e9c2d-126">Para obtener más información sobre estas tareas, consulte [requisitos del sistema para servidores que ejecutan Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [configurar IIS para Lync Server 2013](lync-server-2013-configure-iis.md)y [preparar la infraestructura y los sistemas para Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="e9c2d-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="e9c2d-127">Además, debe familiarizarse con los requisitos de clientes y clientes.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="e9c2d-128">Para obtener más información, consulte [implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="e9c2d-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9c2d-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e9c2d-129">In This Section</span></span>

  - [<span data-ttu-id="e9c2d-130">Configuración del hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c2d-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="e9c2d-131">Configuración del software para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c2d-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="e9c2d-132">Preparar Servicios de dominio de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c2d-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="e9c2d-133">Configurar SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c2d-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="e9c2d-134">Configurar los registros DNS para un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c2d-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="e9c2d-135">Instalar las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c2d-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

