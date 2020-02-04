---
title: 'Lync Server 2013: Configuración del hardware'
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
ms.openlocfilehash: 6831ba5f8d2afea7bddbd0c26ab4cebb2cff44f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="4dfe5-102">Configuración del hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dfe5-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dfe5-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4dfe5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4dfe5-104">La configuración del hardware y de otros componentes necesarios en la infraestructura que necesita para implementar su topología requiere que, antes de publicar su topología en el generador de topología, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4dfe5-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="4dfe5-105">Instale el hardware de cada componente en el diseño de topología que haya creado y guardado con el generador de topología, incluidos los equipos requeridos (servidores que ejecutan Lync Server 2013, servidores de base de datos, servidores de Internet Information Services (IIS) y servidores proxy inversos, según corresponda), adaptadores de red, equilibradores de carga de hardware y dispositivos de almacenamiento (como servidores de archivos).</span><span class="sxs-lookup"><span data-stu-id="4dfe5-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="4dfe5-106">Confirme que ha seguido las recomendaciones para el número y la velocidad de los adaptadores de red.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="4dfe5-107">Si va a usar equilibradores de carga de hardware, asegúrese de que tiene la información adecuada del proveedor para configurarla para su uso con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="4dfe5-108">Si va a usar un servidor de archivos u otro servidor para albergar el recurso compartido de archivos requerido por Lync Server, asegúrese de que el servidor está disponible y listo para configurar el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="4dfe5-109">Para obtener más información sobre cómo definir una topología que especifique los componentes necesarios para su implementación, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="4dfe5-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="4dfe5-110">Para obtener más información sobre los requisitos de hardware para servidores, consulte [hardware compatible para Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="4dfe5-111">Asegúrese de que la infraestructura de red cumpla con los requisitos.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="4dfe5-112">Para obtener más información, consulte [requisitos de infraestructura de red para Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="4dfe5-113">Configurar los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="4dfe5-114">La configuración de AD DS incluye la preparación de AD DS y la definición de todos los componentes que desea implementar en AD DS.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="4dfe5-115">Para obtener detalles sobre la preparación de AD DS, consulte [preparar los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="4dfe5-116">Configure los permisos necesarios para crear el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="4dfe5-117">Los permisos de uso compartido de archivos por Lync Server 2013 se configuran automáticamente mediante el generador de topología al publicar su topología.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="4dfe5-118">Sin embargo, la cuenta de usuario usada para publicar la topología debe tener control total (lectura/escritura/modificar) en el recurso compartido de archivos para que el generador de topología configure los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="4dfe5-119">Para asegurarse de que el recurso compartido de archivos se puede administrar correctamente durante el proceso de publicación del generador de topologías, el usuario o el grupo de dominio al que pertenece el usuario debe ser miembro del grupo de administradores locales en el equipo en el que se encuentra el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="4dfe5-120">En un escenario de dominios múltiples, un usuario o un grupo de dominio debe ser miembro del grupo de administradores locales en el equipo del dominio B donde estará el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="4dfe5-121">Para obtener más información sobre cómo actualizar con recursos compartidos de archivos en un sistema de archivos distribuido (DFS), vea [configurar el almacenamiento de archivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="4dfe5-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4dfe5-122">El recurso compartido de archivos de Lync Server 2013, Enterprise Edition no se puede encontrar en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="4dfe5-123">Instale y configure el equilibrador de carga de hardware para servicios Web.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="4dfe5-124">Con el equilibrio de carga del sistema de nombres de dominio (DNS) implementado, aún necesita usar equilibradores de carga de hardware para estos grupos, pero solo para el tráfico HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="4dfe5-125">El equilibrador de carga de hardware se usa para el tráfico HTTPS de los clientes en los puertos 443 y 80.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="4dfe5-126">Aunque siga necesitando equilibradores de carga de hardware para estos grupos, la configuración y la administración serán principalmente para el tráfico HTTP/HTTPS, al que los administradores de los equilibradores de carga de hardware están acostumbrados.</span><span class="sxs-lookup"><span data-stu-id="4dfe5-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="4dfe5-127">Después de completar todas las tareas de preparación según se describe en este tema, pero antes de publicar la topología, también tendrá que:</span><span class="sxs-lookup"><span data-stu-id="4dfe5-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="4dfe5-128">Instalar los sistemas operativos y el software necesario como requisito previo en los servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dfe5-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="4dfe5-129">Configurar IIS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dfe5-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="4dfe5-130">Configurar SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dfe5-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="4dfe5-131">Configurar los registros DNS para un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dfe5-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

