---
title: 'Lync Server 2013: información general del proceso de copia de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94cebbc9a11e1857bed419c97f52f065326b1772
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504877"
---
# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="eb551-102">Información general sobre el proceso de copia de seguridad y restauración para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb551-102">Backup and restoration process overview for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb551-103">_**Última modificación del tema:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="eb551-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="eb551-104">En esta sección se proporciona información general sobre cómo funciona el proceso de copia de seguridad y restauración para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb551-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="eb551-105">Se usa el mismo proceso para todos los servidores Standard Edition y Enterprise, independientemente de su ubicación.</span><span class="sxs-lookup"><span data-stu-id="eb551-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="eb551-106">En general, el proceso de copia de seguridad funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="eb551-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="eb551-107">Se crea una ubicación para copias de seguridad como una carpeta compartida en un equipo independiente que no forma parte de ningún grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="eb551-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="eb551-108">La ubicación de la copia de seguridad refiere a **$Backup**.</span><span class="sxs-lookup"><span data-stu-id="eb551-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="eb551-109">De forma periódica y programada, realice una copia de seguridad de todas las bases de datos de Lync Server y de todos los almacenes de archivos que se describen en [requisitos de copia de seguridad y restauración en Lync server 2013: los datos](lync-server-2013-backup-and-restoration-requirements-data.md) siguiendo los procedimientos descritos en copia de seguridad de [Lync Server 2013](lync-server-2013-backing-up-lync-server.md) el almacén de administración central incluye todas las configuraciones y configuraciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="eb551-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="eb551-110">Cada vez que se ejecuta una copia de seguridad posterior, se crea una nueva carpeta compartida y cambia la ruta a la que hace referencia **$Backup**.</span><span class="sxs-lookup"><span data-stu-id="eb551-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="eb551-111">En general, el proceso de restauración funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="eb551-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="eb551-112">Cuando se produce un error o una interrupción, se restauran los datos en la ubicación a la que hacen referencia **$backup** a equipos nuevos o limpios.</span><span class="sxs-lookup"><span data-stu-id="eb551-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eb551-p103">Este proceso de restauración no restaura datos en un estado de servidor existente. Es decir, este proceso requiere que el servidor esté limpio o sea nuevo.</span><span class="sxs-lookup"><span data-stu-id="eb551-p103">This restoration process does not restore data onto an existing server state. That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="eb551-115">Para permitir que la información de usuarios y conferencias sea recuperable hasta el punto de error, puede implementar una topología de recuperación ante desastres con grupos de servidores front-end emparejados, tal como se describe en [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="eb551-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="eb551-116">Toda la configuración del Sistema de nombres de dominio (DNS), del Protocolo de la configuración dinámica de host (DHCP), los nombres de dominio, los nombres de dominio completos (FQDN), las rutas de almacenes de archivos, etc. deben ser los mismos al momento de la restauración que cuando se hizo la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="eb551-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="eb551-117">Si se produce un error en un servidor que ejecuta Lync Server, la recuperación incluye los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="eb551-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="eb551-118">Instalar el sistema operativo en un equipo nuevo o limpio con el mismo FQDN que había en el equipo donde se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="eb551-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="eb551-119">Reinstalar certificados.</span><span class="sxs-lookup"><span data-stu-id="eb551-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="eb551-120">Si el servidor hospedaba una base de datos, instale Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="eb551-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="eb551-121">En general, si el servidor hospedaba una base de datos, ejecute el generador de topologías para crear e instalar la base de datos y configurar las listas de control de acceso (ACL).</span><span class="sxs-lookup"><span data-stu-id="eb551-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="eb551-122">En general, si el servidor hospedaba una función de servidor, ejecute el paso 1 hasta el paso 4 del Asistente para la implementación de Lync Server para instalar los archivos de configuración locales, instalar los componentes del rol de servidor, asignar certificados e iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="eb551-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb551-123">Si el servidor hospedaba una base de datos combinada con la función de servidor, al ejecutar el paso 2 del Asistente para la implementación de Lync Server se vuelve a crear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="eb551-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="eb551-124">Si el servidor hospedaba una base de datos, restaure los datos de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="eb551-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

