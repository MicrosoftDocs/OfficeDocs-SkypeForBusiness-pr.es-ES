---
title: 'Lync Server 2013: configuración de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d55ac04a06984889a3038aceee7fd0f311efcfb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="0bc0e-102">Configuración de hardware para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc0e-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bc0e-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0bc0e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0bc0e-104">La configuración del hardware y de otros componentes necesarios en la infraestructura necesaria para implementar la topología requiere que, antes de publicar la topología en el generador de topologías, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bc0e-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="0bc0e-105">Instale el hardware para cada componente del diseño de la topología que ha creado y guardado mediante el generador de topologías, incluidos todos los equipos necesarios (servidores que ejecutan Lync Server 2013, servidores de bases de datos, servidores que ejecutan Internet Information Services (IIS) y los servidores proxy inversos, según corresponda, los adaptadores de red, los equilibradores de carga de hardware y los dispositivos de almacenamiento (por ejemplo, los servidores de archivos).</span><span class="sxs-lookup"><span data-stu-id="0bc0e-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="0bc0e-106">Confirme que ha seguido las recomendaciones sobre el número y la velocidad de los adaptadores de red.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="0bc0e-107">Si va a usar equilibradores de carga de hardware, asegúrese de que dispone de la información adecuada del proveedor para configurarlos para su uso con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="0bc0e-108">Si va a usar un servidor de archivos u otro servidor para hospedar el recurso compartido de archivos necesario para Lync Server, asegúrese de que el servidor esté disponible y listo para la configuración del recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="0bc0e-109">Para obtener información detallada sobre cómo definir una topología que especifique los componentes necesarios para la implementación, consulte [Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="0bc0e-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="0bc0e-110">Para obtener más información sobre los requisitos de hardware para los servidores, consulte [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="0bc0e-111">Asegúrese de que la infraestructura de red cumple los requisitos.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="0bc0e-112">Para obtener más información, consulte [requisitos de la infraestructura de red para Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="0bc0e-113">Configurar los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="0bc0e-114">La configuración de AD DS incluye la preparación de AD DS y la definición de todos los componentes que desea implementar en AD DS.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="0bc0e-115">Para obtener información detallada sobre la preparación de AD DS, consulte preparación de los [servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="0bc0e-116">Configure los permisos necesarios para crear el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="0bc0e-117">El generador de topologías configura automáticamente los permisos para el uso de recursos compartidos de archivos en Lync Server 2013 al publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="0bc0e-118">Sin embargo, la cuenta de usuario usada para publicar la topología debe tener control total (lectura/escritura/modificación) en el recurso compartido de archivos para que el generador de topologías configure los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="0bc0e-119">Para asegurarse de que el recurso compartido de archivos se puede administrar correctamente durante el proceso de publicación del generador de topologías, el usuario o el grupo de dominio al que pertenece el usuario debe ser miembro del grupo de administradores locales en el equipo en el que se encuentra el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="0bc0e-120">En un escenario con varios dominios, el usuario o el grupo del dominio A debería convertirse en miembro del grupo de administradores locales en el equipo en el dominio B donde se ubicará el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="0bc0e-121">Para obtener más información sobre cómo actualizar con recursos compartidos de archivos en un sistema de archivos distribuido (DFS), consulte [configurar el almacenamiento de archivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="0bc0e-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0bc0e-122">El recurso compartido de archivos de Lync Server 2013, Enterprise Edition no se encuentra en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="0bc0e-123">Instale y configure el equilibrador de carga de hardware para los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="0bc0e-124">Con el equilibrio de carga del Sistema de nombres de dominio (DNS) implementado, aún debe usar equilibradores de carga de hardware para estos grupos de servidores, pero solo para el tráfico de HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="0bc0e-125">El equilibrador de carga de hardware se usa para el tráfico HTTPS procedente de clientes a través de los puertos 443 y 80.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="0bc0e-126">Aunque siga siendo necesario usar equilibradores de carga de hardware para estos grupos de servidores, su configuración y administración será sobre todo para el tráfico HTTP/HTTPS, a lo que están acostumbrados los administradores de los equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="0bc0e-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="0bc0e-127">Cuando haya completado todas las tareas de preparación que se describen en este tema, pero antes de publicar la topología, también es necesario realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="0bc0e-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="0bc0e-128">Instalar los sistemas operativos y el software necesario como requisito previo en los servidores para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc0e-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="0bc0e-129">Configurar IIS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc0e-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="0bc0e-130">Configuración de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc0e-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="0bc0e-131">Configurar registros DNS en Lync Server 2013 para un grupo de servidores front-end o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0bc0e-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

