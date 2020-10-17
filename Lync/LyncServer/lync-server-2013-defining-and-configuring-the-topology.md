---
title: 'Lync Server 2013: definir y configurar la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86f98c5961385bd2f99c0698af1b5f422abe4c60
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504547"
---
# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="a5764-102">Definición y configuración de la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5764-102">Defining and configuring the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5764-103">_**Última modificación del tema:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="a5764-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="a5764-104">Puede definir y configurar la topología con el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="a5764-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="a5764-105">El generador de topologías no requiere que usted sea miembro del grupo de administradores locales o de un grupo de dominios privilegiado (como administradores del dominio).</span><span class="sxs-lookup"><span data-stu-id="a5764-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="a5764-106">Puede definir su topología como usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="a5764-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="a5764-107">Cuando inicie el Generador de topologías, en el primer uso y en los usos posteriores se le solicitará la ubicación en la que desea que el Generador de topologías cargue el documento de configuración actual.</span><span class="sxs-lookup"><span data-stu-id="a5764-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="a5764-108">Las opciones son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="a5764-108">The choices are the following:</span></span>

  - <span data-ttu-id="a5764-109">Descargar una topología desde una implementación existente</span><span class="sxs-lookup"><span data-stu-id="a5764-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="a5764-110">Abrir una topología desde un archivo local</span><span class="sxs-lookup"><span data-stu-id="a5764-110">Open topology from a local file</span></span>

  - <span data-ttu-id="a5764-111">Nueva topología</span><span class="sxs-lookup"><span data-stu-id="a5764-111">New topology</span></span>

<span data-ttu-id="a5764-112">Si ya ha definido una topología y ha establecido el almacén de administración central, debe elegir descargar una topología de una implementación existente.</span><span class="sxs-lookup"><span data-stu-id="a5764-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="a5764-113">El Generador de topologías leerá la base de datos y recuperará la definición actual.</span><span class="sxs-lookup"><span data-stu-id="a5764-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="a5764-114">Si ya tiene un almacén de administración central, elija esta opción siempre.</span><span class="sxs-lookup"><span data-stu-id="a5764-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="a5764-115">Si no ha establecido un almacén de administración central y desea editar una configuración previamente guardada, debe optar por abrir la topología desde un archivo local.</span><span class="sxs-lookup"><span data-stu-id="a5764-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="a5764-116">El archivo que abrirá será el archivo de configuración que se guardó en una sesión anterior.</span><span class="sxs-lookup"><span data-stu-id="a5764-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="a5764-117">Puede usar esta opción para editar la topología guardada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a5764-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a5764-p104">Si ya tiene una topología publicada, no deberá cargar un archivo de configuración local. Deberá descargar la topología desde una implementación existente.</span><span class="sxs-lookup"><span data-stu-id="a5764-p104">If you already have a published topology, you should not load a local configuration file. You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="a5764-120">Elija crear una nueva topología si desea crear una nueva configuración del generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="a5764-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="a5764-121">Un diseño guardado anteriormente no se sobrescribe a no ser que elija guardarlo como el mismo archivo creado en una sesión de diseño anterior.</span><span class="sxs-lookup"><span data-stu-id="a5764-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="a5764-122">En cada una de estas opciones, se le pedirá que indique una ubicación para almacenar el archivo de configuración del generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="a5764-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="a5764-123">La ubicación del archivo podría ser una ubicación local, una ubicación compartida en un recurso compartido de archivos establecido o un medio extraíble.</span><span class="sxs-lookup"><span data-stu-id="a5764-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a5764-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a5764-124">In This Section</span></span>

  - [<span data-ttu-id="a5764-125">Definir y configurar una topología en el generador de topologías para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5764-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="a5764-126">Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5764-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="a5764-127">Implementación de grupos de servidores front-end emparejados para la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5764-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="a5764-128">Implementación de la creación de reflejos de SQL para la alta disponibilidad del servidor back-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5764-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="a5764-129">Editar o configurar direcciones URL sencillas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5764-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="a5764-130">Seleccione el servidor de administración central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5764-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

