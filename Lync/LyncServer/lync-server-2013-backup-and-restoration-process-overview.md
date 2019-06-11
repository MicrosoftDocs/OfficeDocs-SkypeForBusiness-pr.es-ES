---
title: 'Lync Server 2013: información general del proceso de copia de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b01230e84c9278d5540c21d41d9af1342479e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="e9ff5-102">Descripción general del proceso de copia de seguridad y restauración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9ff5-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9ff5-103">_**Última modificación del tema:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="e9ff5-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="e9ff5-104">Esta sección proporciona información general sobre cómo funciona el proceso de copia de seguridad y restauración para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="e9ff5-105">Use el mismo proceso para todos los servidores Standard Edition y los servidores Enterprise Edition, independientemente de su ubicación.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="e9ff5-106">En general, el proceso de copia de seguridad funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e9ff5-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="e9ff5-107">Cree una ubicación de copia de seguridad como una carpeta compartida en un equipo independiente que no forme parte de ningún grupo.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="e9ff5-108">En **$backup**se hace referencia a la ubicación de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="e9ff5-109">De forma periódica y programada, haga una copia de seguridad de todas las bases de datos de Lync Server y de todos los almacenes de archivos que se describen en [los requisitos de copia de seguridad y restauración de Lync server 2013: datos](lync-server-2013-backup-and-restoration-requirements-data.md) siguiendo los procedimientos descritos en [copia de seguridad de Lync Server 2013 ](lync-server-2013-backing-up-lync-server.md)El almacén central de administración incluye todas las configuraciones y la configuración del servidor.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="e9ff5-110">Cada vez que ejecute una copia de seguridad posterior, cree una nueva carpeta compartida y cambie la ruta de acceso a la **$backup** referencias.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="e9ff5-111">En general, el proceso de restauración funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e9ff5-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="e9ff5-112">Cuando se produce un error o una interrupción, se restauran los datos en la ubicación a la que hacen referencia **$backup** a equipos nuevos o limpios.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e9ff5-113">Este proceso de restauración no restaura datos en el estado de un servidor existente.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="e9ff5-114">Es decir, este proceso requiere que el servidor esté limpio o sea nuevo.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="e9ff5-115">Para permitir que se pueda recuperar la información de usuarios y conferencias hasta el momento en que se produjo el error, puede implementar una topología de recuperación ante desastres con grupos front-end emparejados, como se describe en [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e9ff5-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="e9ff5-116">Toda la configuración del sistema de nombres de dominio (DNS), la configuración del Protocolo de configuración dinámica de host (DHCP), los nombres de dominio, los nombres de dominio completos (FQDN), las rutas de almacenamiento de archivos, etc., deben ser los mismos en el momento de la restauración que estaban en el momento de la restauración Haga una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="e9ff5-117">Si se produce un error en un servidor que ejecuta Lync Server, la recuperación incluye los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e9ff5-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="e9ff5-118">Instale el sistema operativo en un equipo nuevo o limpio con el mismo FQDN que el equipo que ha fallado.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="e9ff5-119">Reinstale certificados.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="e9ff5-120">Si el servidor ha hospedado una base de datos, instale Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="e9ff5-121">En general, si el servidor ha hospedado una base de datos, ejecute el generador de topología para crear e instalar la base de datos y configurar las listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="e9ff5-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="e9ff5-122">En general, si el servidor ha hospedado un rol de servidor, ejecute el paso 1 hasta el paso 4 del Asistente para la implementación de Lync Server para instalar los archivos de configuración local, instalar los componentes del rol de servidor, asignar certificados e iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9ff5-123">Si el servidor ha hospedado una base de datos colocada con el rol de servidor, al paso 2 del Asistente para la implementación de Lync Server se vuelve a crear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="e9ff5-124">Si el servidor ha hospedado una base de datos, restaure los datos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e9ff5-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

